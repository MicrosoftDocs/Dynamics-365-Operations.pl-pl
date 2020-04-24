---
title: Wskaźniki KPI składnika majątku
description: W tym temacie objaśniono wskaźniki KPI składnika majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0cd83bf70d867f40bca018386cb3f8c581e162ce
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216397"
---
# <a name="asset-kpis"></a>Wskaźniki KPI składnika majątku

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku można obliczać różne kluczowe wskaźniki wydajności (KPI) dla składników majątku i typów składników majątku. Wskaźniki KPI służą do uzyskiwania przeglądu wydajności składników majątku w odniesieniu do, na przykład, przestoju, czasu przestoju, czasu naprawy i średniego czasu między awariami (MTBF).

1. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Wskaźniki KPI składnika majątku**.

2. W oknie dialogowym **Oblicz wskaźniki KPI składnika majątku** wybrać **Skala czasu**, która ma być używana w obliczeniach, oraz okres w polach **Od dnia** i **Do dnia**. 

3. Na skróconej karcie **Rekordy do uwzględnienia** można wybrać określone składniki majątku i typy składników majątku, które mają zostać uwzględnione w obliczeniach.

4. Kliknij przycisk **OK**, aby rozpocząć obliczanie.

5. Na karcie skróconej **Przegląd** wyniki obliczeń są wyświetlane w widoku siatki. Każdy składnik majątku jest wyświetlany w osobnym wierszu.

6. Na skróconej karcie **Wskaźniki KPI dla wybranego wiersza** wyświetlane są obliczenia dotyczące składnika majątku wybranego na skróconej karcie **Przegląd**. Wartości wskaźników KPI są klasyfikowane w zależności od **Czasu**, **Dostępności**, **Zleceń pracy**, **Konserwacji**, **Usterek**, **Przerw konserwacyjnych** i **Kosztu**.

W poniższej tabeli znajdziesz opisy pól na stronie **Wskaźniki KPI składnika majątku**.

| Pole                   | Opis                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Składnik majątku                   | Identyfikator składnika majątku.                                                                                                                                                                                                                                                                                             |
| Łączny czas              | Całkowity czas ustawiony w kalendarzu używanym w obliczeniach. Jeśli składnik majatku jest powiązany z zasobem, używany jest odpowiedni kalendarz zasobu. Jeśli składnik majątku nie jest powiązany z zasobem, zostanie użyty kalendarz wybrany w polu **Kalendarz** w **Parametry zarządzania składnikami majątku**. |
| Czas sprawności                  | Całkowity czas pomniejszony o przestoje.                                                                                                                                                                                                                                                                            |
| Przestój                | Rejestracje przestojów konserwacyjnych wykonanych na składniku majątku w wybranym okresie.                                                                                                                                                                                                                              |
| Czas naprawiania             | Całkowita liczba godzin pracy zużytych przy naprawieniu zlecenia pracy.                                                                                                                                                                                                                                            |
| Dostępność w %          | Czas przestoju podzielony przez całkowity czas i pomnożony przez 100.                                                                                                                                                                                                                                                   |
| Liczba usterek        | Liczba błędów powodujących awarie zarejestrowana w składniku majątku w wybranym okresie.                                                                                                                                                                                                             |
| MTBF                    | Średni czas między awariami, który jest łącznym czasem podzielonym o liczbę usterek zarejestrowanych dla składnika majątku w wybranym okresie. Jeśli liczba usterek wynosi zero, MTBF pokazuje całkowity czas.                                                                                                                   |
| Stopa usterek               | 1 podzielone przez MTBF.                                                                                                                                                                                                                                                                                    |
| MRT                     | Średni czas naprawiania, który jest czasem naprawiania podzielonym o liczbę usterek zarejestrowanych dla składnika majątku w wybranym okresie. Jeśli liczba usterek wynosi zero, MRT pokazuje czas naprawiania.                                                                                                                           |
| Liczba zatrzymań         | Liczba rejestracji przestojów konserwacji stworzonych na składniku majątku.                                                                                                                                                                                                                                     |
| MTBS                    | Średni czas między zatrzymaniami, który jest łącznym czasem podzielonym przez liczbę rejestracji przestojów konserwacji. Jeśli liczba rejestracji przerw konserwacyjnych wynosi zero w wybranym okresie, wartość MTBS jest ustawiana jako całkowity czas.                                                                                      |
| Koszt działań zapobiegawczych         | Koszty zaksięgowane dla składnika majątku związanego z typem kosztu „Zapobiegawcze” w wybranym okresie Typy kosztów są ustawiane dla typów zleceń pracy.                                                                                                                                                                       |
| Koszt działań korygujących         | Koszty zaksięgowane dla składnika majątku związanego z typem kosztu „Korygujące” w wybranym okresie. Typy kosztów są ustawiane dla typów zleceń pracy.                                                                                                                                                                       |
| Wartość zastępcza       | Wartość zdefiniowana dla składnika majątku jako koszt wymiany.                                                                                                                                                                                                                                                  |
| Typ składnika majątku             | Identyfikacja typu składnika majątku wybranego składnika majątku.                                                                                                                                                                                                                                             |
| Producent           | Identyfikacja producenta wybranego dla składnika majątku.                                                                                                                                                                                                                                                 |
| Model                   | Identyfikacja modelu producenta wybranego dla składnika majątku.                                                                                                                                                                                                                                           |
| Data Od               | Data początkowa obliczania KPI. Jeśli składnik majątku został utworzony po dacie początkowej wybranej dla obliczenia, w tym polu jest wyświetlana data początkowa składnika majątku.                                                                                                                                  |
| Data Do                 | Data końcowa obliczania KPI. Jeśli składnik majątku został zarejestrowany jako nieaktywny przed datą zakończenia wybraną do obliczania, w tym polu jest wyświetlana data, od której składnik majątku przestał być aktywny.                                                                                               |
| Skala czasu              | Podczas obliczania kluczowych wskaźników KPI należy wybrać skalę czasu, która ma być używana: godziny, dni lub tygodnie.                                                                                                                                                                                                            |
| Dostępność            | Czas przestoju podzielony przez całkowity czas.                                                                                                                                                                                                                                                                         |
| Zlecenia pracy             | Łączna liczba zleceń pracy w obliczeniach KPI.                                                                                                                                                                                                                                          |
| Czas zlecenia pracy         | Całkowita liczba godzin pracy zużytych przy naprawieniu zlecenia pracy.                                                                                                                                                                                                                                               |
| Główne zlecenia pracy     | Łączna liczba głównych zleceń pracy w obliczeniach KPI.                                                                                                                                                                                                                                        |
| Dodatkowe zlecenia pracy   | Łączna liczba dodatkowych zleceń pracy w obliczeniach KPI.                                                                                                                                                                                                                                      |
| Zlecenia pracy konserwacji | Łączna liczba dodatkowych zleceń pracy konserwacji w obliczeniach KPI. Zlecenie prac konserwacyjnych jest zleceniem pracy bez pokrewnych przyczyn usterki.                                                                                                                                                             |
| Czas konserwacji        | Całkowita liczba godzin pracy zużytych przy zlecenia pracy konserwacji.                                                                                                                                                                                                                                       |
| Zlecenia pracy naprawy      | Łączna liczba zleceń pracy naprawy w obliczeniach KPI. Zlecenie pracy naprawy jest zleceniem pracy z pokrewną przyczyną usterki.                                                                                                                                                                        |
| Niezawodność w %           | Obliczanie na podstawie oczekiwanego wykładniczego rozwoju w rejestracjach usterek na składniku majątku oznacza, że w czasie, gdy składnik majątku staje się mniej niezawodny z powodu zużycia. Obliczanie tego wskaźnika KPI opiera się na MTBF i łącznym czasie.                                                            |
| MTPS                    | Średni czas przerw w produkcji, który jest czasem przerw konserwacyjnych podzielonym przez liczbę rejestracji przerw konserwacyjnych. Jeśli liczba rejestracji przerw konserwacyjnych wynosi zero w wybranym okresie, wartość MTPS jest ustawiana jako zero.                                                                               |
| Łączny koszt              | Suma kosztów zaksięgowanych składnika majątku w wybranym okresie.                                                                                                                                                                                                                                              |
| Koszt inwestycji         | Koszty zaksięgowane dla składnika majątku związanego z typem kosztu „Inwestycje” w wybranym okresie. Typy kosztów są ustawiane dla typów zleceń pracy.                                                                                                                                                                       |

Na poniższym rysunku przedstawiono zrzut ekranu obliczania KPI dla czterech składników majątku.

![Zrzut ekranu obliczenia wskaźnika KPI dla czterech składników majątku](media/11-controlling-and-reporting.png)

- Można wybrać wiele składników majątku w obszarze **Wszystkie składniki majątku** i kliknąć przycisk **Wskaźniki KPI składnika majątku** na karcie **Ogólne**. Następnie kliknij przycisk **OK** w oknie dialogowym **Oblicz wskaźniki KPI składnika majątku**, aby obliczyć wskaźniki KPI wybranych składników majątku.  
- Wyniki obliczeń wskaźnika KPI mogą obejmować [rejestracje przerw konserwacyjnych](../work-orders/maintenance-downtime.md), w zależności od konfiguracji i użycia kodów przyczyn przestojów związanych z konserwacją. 

