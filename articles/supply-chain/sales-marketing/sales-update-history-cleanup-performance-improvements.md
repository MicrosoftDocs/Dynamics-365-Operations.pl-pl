---
title: Planowanie czyszczenia danych historii sprzedaży
description: W tym artykule opisano, w jaki sposób można poprawić wydajność systemu, planując okresowe wykonywanie zadania czyszczenia historii aktualizacji sprzedaży w regularnych odstępach czasu.
author: myvakalo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e9a4dd5372afa8a0452449d1cb9121107e6e1610
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335512"
---
# <a name="schedule-sales-history-data-cleanup"></a>Planowanie czyszczenia danych historii sprzedaży

[!include [banner](../includes/banner.md)]

W ramach swojej standardowej działalności Microsoft Dynamics 365 Supply Chain Management na bieżąco generuje i przechowuje dane aktualizujące historię sprzedaży. Z czasem w systemie może skumulować się duża ilość nieaktualnych danych historii sprzedaży. Skumulowane dane mogą powodować problemy z wydajnością i funkcjonalnością podczas księgowana dokumentów związanych z zamówieniami sprzedaży. (Te dokumenty obejmują potwierdzenia zamówień sprzedaży, dokumenty dostawy sprzedaży, listy pobrań sprzedaży i faktury). Dlatego należy skonfigurować i zaplanować okresowe zadanie *Czyszczenie historii aktualizacji sprzedaży* , które będzie wykonywane w regularnych odstępach czasu. To zadanie spowoduje usunięcie wszystkich danych aktualizacji historii sprzedaży, które nie są już potrzebne.

W przypadku korzystania z zadania okresowego *Czyszczenie historii aktualizacji sprzedaży* zaleca się włączenie funkcji *Ulepszenia wydajności czyszczenia historii sprzedaży* , która zwiększa wydajność tego zadania. (Mimo tego zadanie można uruchomić bez włączania tej funkcji)

## <a name="turn-on-the-sales-history-cleanup-features"></a>Włącz funkcje oczyszczania historii sprzedaży

Aby skonfigurować i używać zadania okresowego *Czyszczenie historii aktualizacji sprzedaży* wraz ze wszystkimi funkcjami opisanymi w tym artykule, należy włączyć funkcje *Poprawa wydajności czyszczenia historii sprzedaży* oraz *Czyszczenie historii aktualizacji sprzedaży na podstawie wieku* w Zarządzaniu funkcjami, jak opisano w poniższych podrozdziałach.

### <a name="sales-history-cleanup-performance-improvements"></a>Ulepszenia wydajności oczyszczania historii sprzedaży

Okresowe zadanie wsadowe **Czyszczenie historii sprzedaży** może trwać długo, jeśli jest wykonywane rzadko w środowiskach z dużą ilością aktualizacji sprzedaży. W takich sytuacjach funkcja *Ulepszeń wydajności oczyszczania historii sprzedaży* może pomóc w skróceniu czasu trwania działania i poprawieniu niezawodności.

Ta funkcja usprawnia istniejące zadanie oczyszczania w następujący sposób:

- Proces oczyszczania jest dzielony na partie (rozmiar partii można zmieniać za pomocą dostosowań).
- Będzie on uruchamiany maksymalnie na 2 godziny (można zmienić czas trwania za pomocą dostosowań).
- Tam, gdzie to możliwe, będą wykorzystane możliwości bazy danych, aby zminimalizować rywalizację o blokowanie i uniknąć łączenia tabel transakcyjnych podczas czyszczenia.

Po włączeniu tej funkcji zadanie wsadowe **Oczyszczania historii aktualizacji sprzedaży** (**Sprzedaż i marketing \> Zadania okresowe \> Czyszczenie \> Oczyszczanie historii aktualizacji sprzedaży**) będzie uruchamiane tak jak poprzednio, ale z lepszą wydajnością i przez maksymalnie 2 godziny. Oznacza to, że może być konieczne uruchomienie go kilka razy w celu oczyszczenia wszystkich danych w określonym horyzoncie czasowym przechowywania.

Aby używać tej funkcji, należy ją włączyć dla systemu. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Sprzedaż i marketing*
- **Nazwa funkcji:** *Ulepszenie wydajności oczyszczania historii sprzedaży*

### <a name="clean-up-sales-update-history-based-on-age"></a>Oczyszczanie historii aktualizacji sprzedaży na podstawie wieku

Funkcja *Oczyszczanie historii aktualizacji sprzedaży na podstawie wieku* umożliwia określenie maksymalnego wieku rekordów, które mają być zachowywane podczas wykonywania okresowego zadania *oczyszczania historii aktualizacji sprzedaży*. Starsze rekordy zostaną usunięte. Ta funkcja jest przydatna, gdy zadanie ma być wykonywane okresowo, ponieważ wiek jest zawsze obliczany względem daty wykonania zadania. Jeśli nie korzystasz z tej funkcji, możesz ustawić tylko określoną datę przechowywania najstarszych rekordów.

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.29 Supply Chain Management funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.29, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Oczyszczanie historii aktualizacji sprzedaży na podstawie wieku* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-and-schedule-the-sales-history-cleanup-periodic-task"></a>Konfigurowanie i planowanie zadania okresowego czyszczenia historii sprzedaży

Aby skonfigurować i zaplanować okresowe zadanie *Czyszczenie historii sprzedaży*, należy wykonać poniższe kroki.

1. Przeanalizuj potrzeby biznesowe, aby ustalić, ile dni musi przechowywać dane księgowania historycznych zamówień sprzedaży. Zazwyczaj zaleca się uruchamianie zadania oczyszczania co trzy miesiące, a maksymalnie co sześć miesięcy.
1. Przejdź do **Sprzedaż i marketing \> Zadania okresowe \> Czyszczenie \> Czyszczenie historii aktualizacji sprzedaży**.
1. W oknie dialogowym **Czyszczenie historii aktualizacji sprzedaży** na skróconej karcie **Parametry** ustaw następujące pola:

    - **Oczyszczanie** — Wybierz jedną z następujących wartości, aby określić typ rekordów do oczyszczania:

        - **Wykonane** — usuwanie tylko rekordów, które zostały w pełni przetworzone. Ponieważ nie chcesz już korzystać z tych rekordów, ta opcja jest najbezpieczniejsze.
        - **Wykonane i błędne** — usuń w pełni przetworzone rekordy i rekordy, w których wystąpił błąd. Jest to najczęściej używana opcja. Zamiast ich automatycznego czyszczenia konieczne może być sprawdzenie, a nawet ustalenie błędnych rekordów. Jednak wiele firm decyduje się te rekordy również po około miesiącu, ponieważ prawdopodobnie nie są już istotne z tego powodu.
        - **Wszystko** — usuwanie wykonanych, błędnych i oczekujących rekordów. Rekordy oczekujące są prawidłowe, ale nie zostały jeszcze w pełni przetworzone. W większości przypadków prawdopodobnie nie chcesz ich usuwać automatycznie. W pewnych sytuacjach można jednak wybrać opcję automatycznego ich usunięcia po upływie określonego czasu.

    - **Zachowywanie rekordów na podstawie wieku** — umożliwia określenie, czy rekordy mają być oczyszczania w oparciu o ich wiek w dniu uruchomienia zadania, czy też usunięcie rekordów utworzonych przed stałą datą. W przypadku planowania oczyszczania jako zadania cyklicznego należy ustawić tę opcję na Wartość *Tak*, ponieważ wiek jest zawsze obliczany względem daty rozpoczęcia zadania.

        - Ustaw tę opcję na *Tak*, aby włączyć pole **Maksymalny wiek**. To pole umożliwia określenie maksymalnego wieku rekordów, które mają być zachować po każdym uruchomieniu zadania. Pole **Utworzone do** jest ignorowane.
        - Ustaw tę opcję na *Nie*, aby włączyć pole **Utworzone do**. Pole to służy do określenia najstarszej daty utworzenia rekordów, które mają być zachowane podczas wykonywania zadania. Pole **Maksymalny wiek** jest ignorowane.

    - **Utworzone do** — to ustawienie ma zastosowanie tylko w przypadku, gdy ustawienie **Zachowaj rekordy na podstawie wieku** ma wartość *Nie*. Określić najstarszą datę utworzenia rekordów, które mają być zachowane podczas wykonywania zadania. Rekordy utworzone przed tą datą zostaną usunięte.
    - **Maksymalny wiek** — to ustawienie ma zastosowanie tylko w przypadku, gdy ustawienie **Zachowaj rekordy na podstawie wieku** ma wartość *Tak*. Określa maksymalny wiek (w dniach) rekordów, które mają być przechowywane przy każdym uruchomieniu zadania. Starsze rekordy zostaną usunięte.

1. Na skróconej karcie **Uruchom w tle** określ sposób, czas i częstotliwość uruchamiania zadania. Użyj tych ustawień, aby zaimplementować harmonogram określony w kroku 1. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań wsadowych](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko dialogowe.
