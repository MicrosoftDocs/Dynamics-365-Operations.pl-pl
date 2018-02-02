--- 
title: "Opracowywanie struktury i planu pensji/wynagrodzeń"
description: "W tym przewodniku po zadaniu pokazano kolejne etapy procesu tworzenia planu stałych wynagrodzeń oraz włączania pracowników do planu za pomocą reguł uprawnienia."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 63a02a64ff28531bae950f1b61d9167eaa0b0373
ms.openlocfilehash: 7fd32467cfbc8c30b398659d16b268f183b6b3d3
ms.contentlocale: pl-pl
ms.lasthandoff: 11/01/2017

---
# <a name="develop-salarycompensation-structure-and-plans"></a>Opracowywanie struktury i planu pensji/wynagrodzeń

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniu pokazano kolejne etapy procesu tworzenia planu stałych wynagrodzeń oraz włączania pracowników do planu za pomocą reguł uprawnienia. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF, a zadanie jest przeznaczone dla menedżerów ds. wynagrodzenia i świadczeń.


## <a name="create-fixed-compensation-plan"></a>Tworzenie planu stałych wynagrodzeń
1. Kliknij opcję Zarządzanie wynagrodzeniami.
2. Kliknij Systemy stałych wynagrodzeń.
3. Kliknij przycisk Nowy.
4. W polu Plan wpisz wartość.
5. Wypełnij pole Opis.
6. W polu Data obowiązywania wprowadź datę.
7. W polu Typ określ typ planu stałych wynagrodzeń: Pasmo, Kategoria lub Krok.
8. Pole wyboru Rekomendacje dozwolone służy jako wartość domyślna dla wszystkich czynności dodawanych do tego planu w zdarzeniu procesowym.  Zezwolenie na rekomendacje umożliwi zastąpienie obliczonej kwoty podstawowej podczas przetwarzania wynagrodzeń.
9. Opcja Tolerancja wyjścia poza zakres pozwala określić sposób postępowania z kwotami wynagrodzeń, które nie mieszczą się w zakresie podanej struktury wynagrodzeń dla danego poziomu.  Wartość Brak umożliwi korzystanie z wszystkich kwot wynagrodzenia.  Wartość Wstępna spowoduje ostrzeganie użytkownika, jeśli kwota wynagrodzenia jest niższa niż kwota w minimalnym punkcie odniesienia dla tego poziomu albo większa niż kwota maksymalna dla tego poziomu. Użytkownik może zignorować ostrzeżenie i kontynuować.  Tolerancja Ostateczna spowoduje generowanie błędu, jeśli wynagrodzenie pracownika zostanie ustawione poza punktami odniesienia minimalnym i maksymalnym dla poziomu, oraz automatycznie dopasowanie wynagrodzenia pracownika, aby się mieściło w tym zakresie.
10. Pole Reguła zatrudnienia jest używane podczas wykonywania zdarzenie procesu związanego z wynagrodzeniem w celu obliczenia wynagrodzenia pracownika.  Reguła zatrudnienia Procent oblicza wzrost proporcjonalny do długości czasu zatrudnienia pracownika w cyklu.
11. W polu Waluta wpisz wartość.
12. W polu Konwersja stawki płacy wprowadź lub wybierz wartość.
13. Rozwiń sekcję Macierz zakresów wykorzystania.
    * Opcjonalnie dodaj rekordy zakresu wykorzystania, aby umożliwić pracownikom szybsze dotarcie ich punktów środkowych, a spowolnić osiągnięcie wartości maksymalnej w zakresie.  
14. W tym momencie należy zapisać plan stałych wynagrodzeń, aby włączyć przycisk Konfiguruj wynagrodzenie i umożliwić kontynuowanie określania struktury wynagrodzeń dla planu.  Kliknij przycisk Zapisz.
15. Kliknij przycisk Konfiguruj wynagrodzenie.
    * Istnieją trzy sposoby tworzenia struktury wynagrodzeń. 1: Utworzenie całkowicie nowej struktury przez wybranie zbioru punktów odniesienia i dodanie poziomów, aby utworzyć własną strukturę. 2: Skopiowanie struktury wynagrodzeń z istniejącego planu i jej zmodyfikowanie dla nowego planu. 3: Wybór istniejącej siatki wynagrodzeń. Jeśli siatka wynagrodzeń jest już używana przez inny plan, wszelkie zmiany dokonane w siatce zostaną odzwierciedlone w drugim planie.  
16. Zaznacz opcję Utwórz nową na podstawie istniejącej macierzy wynagrodzeń.
17. W polu Kopiuj z siatki wprowadź lub wybierz wartość.
    * Opcjonalnie można zmienić nazwę nowej siatki wynagrodzeń, która zostanie utworzona jako kopia wybranej siatki.  
18. Kliknij przycisk OK.
19. Kliknij opcję Zmiana masowa.
    * Funkcja zmiany masowej pozwala zachować kwoty macierzy wynagrodzeń poprzez zastosowanie wzrostu procentowego lub o stałej kwocie do jednego lub więcej poziomów i/lub punktów odniesienia.  
20. W polu Kwota korekty wpisz liczbę.
21. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
22. Kliknij przycisk Zastosuj do siatki.
23. Zamknij stronę.
    * Gdy struktura wynagrodzeń zostanie utworzona lub wybrana, można wskazać, które punkty odniesienia powinny być używane jako punkt kontrolny dla planu stałych wynagrodzeń.  Punkt kontrolny służy do obliczania wskaźnika porównawczego pracownika.  
24. W polu Punkt kontrolny wprowadź lub wybierz wartość.
25. Zamknij stronę.

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a>Tworzenie reguły uprawnienia dla nowego planu stałych wynagrodzeń
    * Nowego planu stałych wynagrodzeń nie można przypisać pracownikowi, dopóki nie zostaną zdefiniowane reguły uprawnienia dla planu.  
1. Kliknij opcję Reguły uprawnienia.
2. Kliknij przycisk Nowy.
3. W polu Uprawnienie wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Data obowiązywania wprowadź datę.
    * Reguły uprawnienia mają zastosowanie do planów wynagrodzeń stałych i o zmiennej wysokości.  W polu Typ wybierz typ planu, dla którego będzie konfigurowany ten zbiór reguł uprawnienia.  
6. W polu Plan wprowadź lub wybierz wartość.
    * Wybierz kryteria, które pracownik musi spełnić, aby kwalifikować się do planu wynagrodzeń. Kryteria mogą obejmować dział, związek zawodowy, lokalizację (region wynagrodzeń), zadanie, funkcję, typ zadania lub poziom wynagrodzeń. Aby kwalifikować się do planu wynagrodzeń, pracownik musi spełniać wszystkie kryteria. W razie nieokreślenia kryteriów wszyscy pracownicy kwalifikują się do planu wynagrodzeń. Jeśli pracownik nie spełnia kryteriów określonych w regule uprawnienia lub jeśli nie określono reguły uprawnienia dla planu wynagrodzeń, plan wynagrodzeń nie pojawi się w wynikach wyszukiwania podczas tworzenia rekordu stałego wynagrodzenia dla pracownika.  
7. Zamknij stronę.
8. Zamknij stronę.


