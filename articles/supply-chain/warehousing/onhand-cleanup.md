---
title: Zadanie oczyszczania wpisów towarów na stanie w zarządzaniu magazynem
description: W tym artykule opisano zadanie czyszczenia wpisów dostępnych zapasów, które ułatwia poprawę wydajności systemu przez identyfikowanie i usuwanie powiązanych z nimi rekordów.
author: perlynne
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: df20f00a639d237bf8446f24a2ad4cbbfcf36615
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334394"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>Zadanie czyszczenia wpisów dostępnych zapasów do zarządzania magazynem

[!include [banner](../includes/banner.md)]

Na wydajność zapytań używanych do obliczania dostępnych zapasów ma wpływ liczba rekordów w zaangażowanych tabelach. Jednym ze sposobów zwiększenia wydajności jest zmniejszenie liczby rekordów, które musi uwzględnić baza danych.

W tym artykule opisano zadanie czyszczenia wpisów dostępnych zapasów, które usuwa niepotrzebne rekordy z tabel `InventSum` i `WHSInventReserve`. Te tabele służą do przechowywania informacji o dostępnych zapasach dla towarów, które są włączone dla przetwarzania zarządzania magazynem. (Te elementy są określane mianem pozycji WMS.) Usunięcie tych rekordów może znacząco poprawić wydajność obliczeń dostępnych zapasów.

## <a name="what-the-cleanup-job-does"></a>Co robi zadanie oczyszczania

Zadanie oczyszczania wpisów dostępnych zapasów usuwa wszystkie rekordy z tabel `WHSInventReserve` i `InventSum`, w których wszystkie wartości pól są równe *0* (zero). Te rekordy można usunąć, ponieważ nie przyczyniły się do informacji o dostępnych zapasach. Zadanie usuwa tylko rekordy znajdujące się poniżej poziomu **Lokalizacji**.

Jeśli jest dozwolone ujemne zapasy fizyczne, zadanie oczyszczania może nie być w stanie usunąć wszystkich odpowiednich wpisów. Powodem tego ograniczenia jest to, że zadanie musi pozwalać na specjalny scenariusz, w którym numer identyfikacyjny ma wiele numerów seryjnych, a jeden z tych numerów seryjnych staje się ujemny. Na przykład system będzie miał wartość zero na poziomie numeru identyfikacyjnego, gdy numer seryjny jest przypisany do + 1 komputerów PC o numerze seryjnym 1 i -1 sztuk o numerze fabrycznym 2. W przypadku tego specjalnego scenariusza zadanie wykonuje w pierwszej kolejności usunięcie o szerokości, z którego najpierw będzie próbował usunąć dane z niższych poziomów.

## <a name="schedule-and-configure-the-cleanup-job"></a>Planowanie i Konfigurowanie zadania oczyszczania

Zadanie czyszczenia wpisów dostępnych zapasów jest dostępne w **Zarządzanie zapasami \> Zadania okresowe \> Wyczyść \> Oczyszczenie wpisów dostępnych zapasów do zarządzania magazynem**. Standardowe ustawienia zadania służą do sterowania zakresem i harmonogramem uruchamiania zadania. Ponadto zaoferowano następujące ustawienia:

- **Usuń, jeśli nie zaktualizowano przez tę liczbę dni** — wprowadź minimalną liczbę dni oczekiwania zadania przed usunięciem wpisu zapasów, który został porzucony do zerowej ilości. To ustawienie umożliwia zredukowanie ryzyka usuwania nieużywanych wpisów dostępnych zapasów. Jeśli chcesz, aby Oczyszczanie było wykonywane jak najszybciej, wprowadź *0* (zero) lub pozostaw to pole puste.
- **Maksymalny czas wykonywania (godziny)** — umożliwia wprowadzenie maksymalnego czasu wykonywania zadania oczyszczania (w godzinach). Jeśli zadanie nie zostanie ukończone przed upływem tego czasu, zapisze pracę, którą wykonał do tej pory, a następnie się zamknie. Ta możliwość jest szczególnie przydatna w przypadku implementacji z dużym użyciem zapasów. W takich przypadkach należy zaplanować zadanie, aby było uruchamiane w godzinach, gdy obciążenie systemu jest możliwie jak najbardziej jasne. Jeśli zadanie wsadowe ma kontynuować działanie, dopóki nie zostanie zakończone, należy wprowadzić wartość *0* (zero) lub pozostawić to pole puste. To ustawienie jest dostępne tylko wtedy, gdy funkcja pokrewna została [włączona dla systemu](#max-execution-time).

Chociaż można uruchamiać zadanie w zwykłych godzinach pracy, zaleca się, aby był on uruchamiany poza godzinami pracy. Dzięki temu można zapobiec konfliktom, które mogą wystąpić, jeśli użytkownik pracuje z rekordem, który jest również czyszczony.

Jeśli zadanie próbuje usunąć rekord dla towaru, gdy ten rekord jest używany przez innego użytkownika, wystąpi błąd zakleszczenia dla zadania oczyszczania lub użytkownika.

Po uruchomieniu zadania ma on przydzielony rozmiar 100. Innymi słowy podejmie próbę jednokrotnej rezerwacji każdego z 100. Ponieważ jednak niektóre operacje usuwania są ustawione na podstawie ustawionych, mogą wystąpić scenariusze, w których w tej samej transakcji można usunąć tylko rekordy większe niż 100. Dlatego eskalacja blokad może czasami wystąpić.

## <a name="possible-user-impact"></a>Możliwy wpływ użytkownika

Użytkownicy mogą mieć wpływ na to, jeśli zadanie oczyszczania wpisów dostępnych zapasów usunie wszystkie rekordy dla danego poziomu (np. na poziomie numeru identyfikacyjnego). W takim przypadku funkcja umożliwiająca wyświetlanie zapasów, które były wcześniej dostępne na numerze identyfikacyjnym, może nie działać zgodnie z oczekiwaniami, ponieważ odpowiednie wpisy stanu zapasów nie są już dostępne. Może stać się tak na przykład w następujących sytuacjach:

- Na liście **dostępnych zapasów**, gdy użytkownik usuwa warunek **Ilość \<\>0** lub wybiera warunek **Zamknięte transakcje** w ustawieniach **wyświetlania wymiarów**.
- W raporcie **Zapasy fizyczne według wymiarów magazynowych** dla przeszłych okresów, gdy użytkownik ustawia parametr **Na dzień**.

Jednak poprawa wydajności zapewniana przez zadanie oczyszczania powinna nadrobić te małe straty w funkcjonalności.

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>Umożliwia ustawienie maksymalnego czasu wykonywania

Ustawienie **Maksymalny czas wykonania** jest dostępne tylko wtedy, gdy jest włączony *maksymalny czas wykonywania* dla funkcji czyszczenia wpisów dostępnych zapasów w zarządzaniu magazynem. Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując *maksymalny czas wykonania zadania oczyszczania wpisów stanu zapasów* w zarządzaniu magazynem w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]