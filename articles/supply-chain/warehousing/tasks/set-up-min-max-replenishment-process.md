--- 
title: "Konfigurowanie procesu uzupełnienia minimalnej i maksymalnej ilości"
description: "W tej procedurze pokazano sposób konfigurowania nowego procesu uzupełniania zapasów, który wykorzystuje strategię minimalnej/maksymalnej ilości uzupełniania."
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 02af5d1beb2d4eb6a7162b47c42854725fbdbec2
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-min-max-replenishment-process"></a>Konfigurowanie procesu uzupełnienia minimalnej i maksymalnej ilości

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób konfigurowania nowego procesu uzupełniania zapasów, który wykorzystuje strategię minimalnej/maksymalnej ilości uzupełniania. Jeśli ilość zapasów spadnie poniżej minimalnego poziomu, zostanie utworzona praca uzupełnienia lokalizacji. W procedurze pokazano również, jak używać stałych lokalizacji pobrania, aby pozwolić na uzupełnianie zapasów nawet gdy ilość zapasów spadnie poniżej minimalnego poziomu, oraz jak włączyć regularne wykonywanie procesu uzupełniania przy użyciu zadania wsadowego. Te zadania zazwyczaj wykonuje kierownik magazynu. Tę procedurę można wykonać na danych firmy demonstracyjnych USMF przy użyciu przykładowych wartości z notatek albo na faktycznych danych swojej firmy. Jeśli korzystasz z własnych danych, upewnij się, że masz magazyn, w którym włączono obsługę procesów zarządzania magazynem.


## <a name="create-a-fixed-picking-location"></a>Tworzenie stałej lokalizacji pobrania
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Magazyn > Stałe lokalizacje.
    * Jest to opcjonalne zadanie minimalnego i maksymalnego uzupełniania zapasów, ale jeśli używasz stałej lokalizacji pobrania, pozwoli ono uzupełniać zapasy nawet jeśli spadną poniżej poziomu minimalnego, ponieważ system może określić, które towary należy uzupełnić, nawet jeśli żadnych nie zostało.  
2. Kliknij przycisk Nowy.
3. W polu Numer towaru wprowadź lub wybierz wartość.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać towar A0001.  
4. W polu Oddział wprowadź lub wybierz wartość.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać oddział 2.  
5. W polu Magazyn wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, można wybrać magazyn 24.  
6. W polu Lokalizacja wprowadź lub wybierz wartość.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać opcję CP-003.  
7. Zamknij stronę.

## <a name="create-a-replenishment-location-directive"></a>Tworzenie dyrektywy lokalizacji uzupełniania zapasów
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Dyrektywy lokalizacji.
    * Dyrektywy lokalizacji służą do określania, skąd towary mają być pobierane w procesie uzupełnienia zapasów.  
2. W polu Typ zlecenia wybierz opcję „Uzupełnienie”.
3. Kliknij przycisk Nowy.
4. W polu Nazwa wpisz wartość.
5. W polu Typ pracy zaznacz opcję „Pobranie”.
6. W polu Oddział wprowadź lub wybierz wartość.
    * Jeśli używasz firmy demonstracyjnej USMF, można wybrać oddział 2.  
7. W polu Magazyn wprowadź lub wybierz wartość.
    * Jeśli używasz firmy USMF, można wybrać magazyn 24.  
8. Kliknij przycisk Zapisz.
9. Kliknij przycisk Nowy.
10. Na liście oznacz wybrany wiersz.
11. W polu Do ilości wprowadź liczbę.
    * Na przykład można ustawić wartość 9999.  
12. Zaznacz pole wyboru Zezwalaj na podział.
    * Jeśli zostanie wybrana ta opcja, proces tworzenia pracy umożliwi podzielenie ilości wierszy pracy między wiele lokalizacji.  
13. Kliknij przycisk Zapisz.
14. Kliknij przycisk Nowy.
15. Na liście oznacz wybrany wiersz.
16. W polu Nazwa wpisz wartość.
17. Kliknij przycisk Zapisz.
18. Kliknij opcję Edytuj kwerendę.
    * Można edytować to zapytanie, aby dodać ograniczenia mówiące o tym, skąd można wybierać zapasy w procesie uzupełnienia zapasów. Na przykład można określić, że zapasów można używać tylko z obszaru materiałów luzem.  
19. Kliknij przycisk OK.
20. Zamknij stronę.

## <a name="create-a-replenishment-work-template"></a>Tworzenie szablonu roboczego uzupełniania zapasów
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy.
    * Szablon pracy służy do instruowania systemu, jak należy utworzyć pracę minimalnego/maksymalnego uzupełniania zapasów. Jako minimum musi istnieć wiersz szablonu pracy dotyczący pobrania i odłożenia. Szablon pracy będzie wyświetlany jako nieprawidłowy do momentu, aż zostaną w nim wprowadzone wszystkie wymagane informacje.  
2. W polu Typ zlecenia wybierz opcję „Uzupełnienie”.
3. Kliknij przycisk Nowy.
4. W polu Szablon pracy wpisz wartość.
5. Kliknij przycisk Zapisz.
6. Kliknij przycisk Nowy.
7. W polu Typ pracy zaznacz opcję „Pobranie”.
8. W polu Identyfikator klasy roboczej wprowadź lub wybierz wartość.
    * Powinna to być klasa pracy związana z uzupełnianiem zapasów. Jeśli używasz firmy USMF, zaznacz opcję Uzupełnianie zapasów.  
9. Kliknij przycisk Nowy.
10. Na liście oznacz wybrany wiersz.
11. W polu Typ pracy zaznacz opcję „Odłożenie”.
12. W polu Identyfikator klasy roboczej wprowadź lub wybierz wartość.
13. Kliknij przycisk Zapisz.
14. Zamknij stronę.

## <a name="create-a-new-replenishment-template"></a>Tworzenie nowego szablonu uzupełniania zapasów
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Uzupełnianie zapasów > Szablony uzupełniania zapasów.
    * Szablon uzupełnienia zapasów służy do definiowania towarów i ilości oraz lokalizacji, która ma być uzupełniana.  
2. Kliknij przycisk Nowy.
3. W polu Szablon uzupełniania zapasów wpisz wartość.
    * Nadaj szablonowi nazwę wskazującą, że dotyczy on uzupełnienia minimalnej/maksymalnej ilości.  
4. Wypełnij pole Opis.
5. Zaznacz pole wyboru Zezwalaj na używanie niezarezerwowanych ilości z powodu popytu grupy czynności.
    * Zaznaczenie tej opcji spowoduje, że uzupełnianie popytu grupy czynności będzie mogło zużywać ilości związane minimalnym/maksymalnym uzupełnieniem. Może to być na przykład przydatne, jeśli praca minimalnego/maksymalnego uzupełniania ilości nie jest przetwarzana natychmiast, ponieważ pozwoli to uniknąć tworzenia niepotrzebnej pracy uzupełnienia zapasów dla popytu.  
6. Kliknij przycisk Nowy.
7. W polu Numer sekwencyjny wpisz liczbę.
8. Wypełnij pole Opis.
9. Na liście oznacz wybrany wiersz.
10. W polu Jednostka uzupełnienia zapasów wprowadź lub wybierz wartość.
    * Na przykład zaznacz opcję „szt.”. To ustawienie jest obowiązkowe. Umożliwia określenie innej jednostki miary dla pracy uzupełniania zapasów w porównaniu z jednostką określoną dla minimalnych i maksymalnych poziomów zapasów w tym szablonie.  
11. W polu Szablon pracy wprowadź lub wybierz wartość.
    * Zaznacz utworzony wcześniej szablon pracy.  
12. W polu Ilość minimalna wprowadź liczbę.
    * Wybierz minimalną ilość, która powinna uruchamiać uzupełnianie zapasów. Na przykład ustaw wartość 50. Istnieje możliwość pozostawienia wartości zero, jeśli jest uzupełniania stała lokalizacja, a w opcji Uzupełnij zapasy w pustych stałych lokalizacjach zaznaczono wartość Tak. Ponadto zaleca się zaznaczenie opcji Uzupełniaj tylko stałe lokalizacje ze względu na wydajność.  
13. W polu Ilość maksymalna wprowadź liczbę.
    * Na przykład ustaw wartość 100.  
14. W polu Jednostka wprowadź lub wybierz wartość.
    * Przypisz jednostkę dla ilości minimalnej i maksymalnej. Na przykład ustaw wartość „szt.”.  
15. Zaznacz pole wyboru Uzupełnij zapasy w pustych stałych lokalizacjach.
    * Zaznacz to pole wyboru, aby uzupełniać stałe lokalizacje, gdy są puste. W przeciwnym razie tylko lokalizacje z tą ilością będą uzupełniane.  
16. Zaznacz pole wyboru Uzupełniaj tylko stałe lokalizacje.
17. Kliknij opcję Wybierz produkty.
    * W tym miejscu należy zdefiniować, które produkty powinny być uzupełniane. Jeśli jest zaznaczona opcja stałych lokalizacji pobrania, należy zdefiniować lokalizacje również w tym zapytaniu. Dostępne są zapytania specyficzne dla wariantów i dla produktów.  
18. Zaznacz wiersz Pozycje.
19. W polu Kryteria wpisz wartość.
    * Wybierz towary, które mają być uzupełniane w stałych lokalizacjach. Na przykład wpisz A *, aby wybrać wszystkie numery towarów rozpoczynające się literą A.  
20. Kliknij przycisk Dodaj.
    * Dodaj jednostkę lokalizacji (chyba że już istnieje), aby móc ograniczyć pracę uzupełniania zapasów do stałych lokalizacji pobrania w określonym obszarze magazynu.  
21. Na liście oznacz wybrany wiersz.
22. W polu Tabela ustaw wartość Lokalizacje.
23. W polu Pole wybierz wartość Identyfikator profilu lokalizacji.
24. W polu Kryteria wprowadź lub wybierz wartość.
25. Kliknij przycisk OK.
26. Zamknij stronę.

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a>Ustawianie wykonywanie procesu uzupełniania zapasów jako zadania wsadowego
1. Wybierz kolejno opcje Zarządzanie magazynem > Uzupełnianie zapasów > Uzupełnienia zapasów.
    * Strona Uzupełnienia zapasów umożliwia skonfigurowanie wykonywania uzupełnienia jako zadania wsadowego lub określenie, że ma ono być uruchamiane ręcznie.  
2. Kliknij przycisk Filtr.
3. Na liście oznacz wybrany wiersz.
4. W polu Kryteria wprowadź lub wybierz wartość.
5. Kliknij przycisk OK.
6. Rozwiń sekcję Uruchom w tle.
7. W opcji Przetwarzanie wsadowe ustaw wartość Tak.
8. Kliknij przycisk Cykl.
9. Wybierz opcję Brak daty zakończenia.
10. Ustaw wzorzec cyklu.
    * Na przykład zaznacz opcję „Dni”.  
11. Kliknij przycisk OK.
12. Kliknij przycisk OK.


