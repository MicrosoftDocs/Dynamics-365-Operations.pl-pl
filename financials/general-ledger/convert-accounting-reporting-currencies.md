---
title: Konwersja waluty rozliczeniowej lub raportowania
description: 
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 78223
ms.assetid: 31c56f9a-9c64-40a2-90e3-1969a760614b
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: c738207f3088da151ec2317ce2b445f83278ec79
ms.contentlocale: pl-pl
ms.lasthandoff: 08/01/2017

---

# <a name="convert-accounting-or-reporting-currencies"></a>Konwersja waluty rozliczeniowej lub raportowania

[!include[banner](../includes/banner.md)]


Firma, która musi zmienić walutę rozliczeniową lub walutę raportowania, ma 2 opcje: Pierwszą opcją jest utworzenie nowej firmy i rozpoczęcie pracy od nowa. Druga opcja to uruchomienie procesu konwersji waluty raportowania i księgowania. Jest to bardzo długotrwały proces, zmieniający wszystkie transakcje w systemie. Wymagana jest także konfiguracja procesu przed jego uruchomieniem.

## <a name="preparing-the-legal-entity-for-currency-conversion"></a>Przygotowywanie podmiotu prawnego na konwersję walut
Aby przekonwertować walutę podmiotu prawnego, należy przywrócić wszelkie kwoty przeszacowania w walucie obcej dla kont odbiorców i dostawców oraz zamknąć poprzednie lata obrachunkowe. Należy również przygotować bazę danych do konwersji, a następnie dokonać wymaganych zmian na koncie podmiotu prawnego, który jest poddany konwersji waluty. Po zakończeniu konwersji waluty, należy wykonać kilka dodatkowych procedur. Należy uzgodnić różnice zaokrąglania przekonwertowanych kwot, obliczyć ponownie statystyki firmy, zapisać w arkuszu transakcje księgi, ograniczyć dostęp do narzędzia do konwertowania oraz przeliczyć kwoty w walucie obcej na kontach odbiorców i dostawców.

## <a name="setting-up-accounts-for-automatic-transactions"></a>Konfiguracja konta dla transakcji automatycznych
Podczas procesu konwersji waluty zyski i straty lub różnice groszowe są księgowane na kontach zdefiniowanych na stronie **kont dla transakcji automatycznych**. Konta główne muszą być przypisane do następujących typów transakcji przed uruchomieniem procesu konwersji:

-   Zysk na konwersji waluty rozliczeniowej
-   Strata na konwersji waluty rozliczeniowej
-   Różnice groszowe w walucie rozliczeniowej
-   Różnice groszowe w walucie raportowania
-   Wynik na koniec roku

## <a name="posting-rounding-differences-and-sum-recalculations"></a>Księgowanie różnic zaokrągleń i ponownie obliczonych sum
Następujące informacje wyjaśniają, gdzie może występować różnica zaokrągleń:

-   Jeżeli ceny produktów zostały przekonwertowane do wartości zero, generowany jest raport, który zawiera numer produktu, typ modułu, cenę przed konwersją oraz jednostkę.
-   Różnice księgowania między podatkami i wpisami w księdze głównej są księgowane w arkuszu finansowym.
-   Ponowne obliczenie kwot przeszacowania w walucie obcej powoduje ponowne obliczenie kwot transakcji odbiorcy i dostawcy.
-   Rejestry rozliczeń odbiorców i dostawców są tworzone dla różnic księgowania dla każdej transakcji odbiorcy i dostawcy.
-   Różnice księgowania dla odbiorców i dostawców są księgowane w arkuszu finansowym.
-   Następuje ponowne obliczenie kwoty kosztów rozliczonych i kwoty korekt kosztu w zamkniętych transakcjach magazynowych.
-   Różnice księgowania w module zarządzania Zapasami są księgowane w arkuszu finansowym.
-   Następuje obliczanie dostępnych zapasów.
-   Sumy kwot w arkuszach księgi zostaną ponownie obliczone.
-   Następuje ponowne obliczenie arkuszy zakończenia księgi.
-   Następuje ponowne obliczenie bilansu księgi.
-   Różnice księgowania w księdze głównej są księgowane w arkuszu finansowym.
-   Następuje ponowne obliczenie transakcji otwarcia księgi.
-   Obliczana jest ostateczna kwota salda księgi.

Jeśli w przypadku konwersji na nową walutę rozliczeniową księgi i podczas ponownego obliczania sum i księgowania różnic zaokrąglania wystąpił błąd, należy zamknąć stronę **Konwersja waluty rozliczeniowej w księgach**. Łączne kwoty zostaną ponownie obliczone i zaksięgowane zostaną różnice zaokrągleń.

## <a name="processing-the-currency-conversion"></a>Przetwarzanie konwersji waluty
Po uruchomieniu procesu konwersji walut wszyscy użytkownicy muszą być wylogowani z systemu. Należy zdefiniować nową księgę lub walutę raportowania oraz kursy wymiany. Po kliknięciu przycisku **OK** proces jest uruchamiany i aktualizuje każdą transakcję w systemie. Konwersja walut jest bardzo długim procesem. Po jego zakończeniu zobaczysz, że waluta rozliczeniowa lub raportowania została zaktualizowana na stronie **księgi**.

## <a name="completing-the-currency-conversion"></a>Kończenie konwersji waluty
Po konwersji waluty należy wygenerować wszystkie raporty dot. uzgodnień, aby upewnić się, że wszystkie przeliczone kwoty są prawidłowe.

-   Jeśli konwersja waluty rozliczeniowej księgi powoduje różnice zaokrągleń, różnice te nie są księgowane za pomocą załącznika, w którym wystąpiła różnica zaokrąglenia. Zamiast tego różnice są księgowane za pomocą załącznika wprowadzonego do księgowania konwersji. Tak więc po konwersji na wszystkich raportach sprawdzonych wg załącznika i daty wystąpią te różnice zaokrągleń. Nie oznaczają one nieprawidłowości i mogą zostać zignorowane.
-   Jeżeli raporty uzgadniania odbiory i dostawcy wykazują różnice kwoty w wierszu sum, a żadna różnica nie występowała przed konwersją, kwotę różnicy należy zaksięgować. Konto jest kontem rozrachunkowym dla odbiorców i dostawców. Konto przeciwstawne jest kontem księgowym dla strata z konwersji lub zysków z konwersji.

Jeśli wszystkie arkusze transakcji finansowych zostały usunięte, możesz ponownie wpisać transakcje finansowe do arkusza. Kliknij kolejno opcje **Księga główna** &gt; **Okresowe** &gt; **Arkusze** &gt; **Generowanie arkuszy**. Można przeliczyć kwoty w walucie obcej po konwersji waluty, jeśli jest wymagane przeszacowanie. Aby przeszacować kwoty w walucie obcej, wybierz opcję **standardowa** w polu **metoda**.

Aby uzyskać więcej informacji, zobacz [Zapisywanie zaksięgowanych zapisów arkusza w arkuszu](tasks/journalize-posted-journal-entries.md).


