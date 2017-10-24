--- 
title: Konfigurowanie konteneryzacji
description: "W tej procedurze opisano sposób zautomatyzowania konteneryzacji ładunków w module Zarządzanie magazynem."
author: YuyuScheller
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
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: aeb7d956560c513c08d5e20dcf20989b49137a52
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-containerization"></a>Konfigurowanie konteneryzacji

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze opisano sposób zautomatyzowania konteneryzacji ładunków w module Zarządzanie magazynem. Podczas przetwarzania grupy czynności funkcja automatycznej konteneryzacji tworzy kontenery i pracę pobrania dla wysyłek, a wiersze pracy można podzielić na ilości mieszczące się w kontenerach. W ten sposób pracownicy magazynu mogą pobierać towary bezpośrednio do wybranego kontenera. W porównaniu do ręcznego procesu pakowania zadania takie jak tworzenie kontenerów, przypisywania towarów i zamykanie kontenerów są zautomatyzowane przez system. Ta procedura używa firmy demonstracyjnej USMF i jest wykonywana przez kierownika magazynu.


## <a name="set-up-a-wave-template"></a>Konfigurowanie szablonu grupy czynności
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Grupy czynności > Szablony grupy czynności.
2. Kliknij przycisk Nowy.
3. W polu Nazwa szablonu grupy czynności wpisz wartość.
4. W polu Opis szablonu grupy czynności wpisz wartość.
5. W polu Oddział wprowadź lub wybierz wartość.
6. W polu Magazyn wprowadź lub wybierz wartość.
7. Rozwiń sekcję Metody.
    * W okienku Wybrane metody są wyświetlane metody dla wybranego typu szablonu grupy czynności. Szablon grupy czynności musi zawierać metodę konteneryzacji.  
8. Na liście znajdź i zaznacz odpowiedni rekord.
9. W polu Kod kroku grupy czynności wpisz wartość.
    * Wprowadź kod kroku grupy czynności dla dodanej metody. Może to być dowolny kod. Istnieje możliwość dodania metody więcej niż jeden raz oraz przypisania różnych kodów kroków grupy czynności. Aby to zrobić, zaznacz dla tej metody opcję Cykliczny na stronie Metody przetwarzania grupy czynności.  
10. Kliknij przycisk Zapisz.
11. Zamknij stronę.

## <a name="set-up-a-container-type"></a>Konfigurowanie typu kontenera
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Typy kontenerów.
    * Kontenery można zdefiniować na stronie Typy kontenerów. Można skonfigurować wymiary fizyczne kontenera, w tym tarę, maksymalną wagę, maksymalną objętość, długość, szerokość i wysokość. W tym przykładzie mamy trzy różne rozmiary skrzynek.  
2. Kliknij przycisk Nowy.
3. W polu Kod typu kontenera wpisz wartość.
4. W polu Waga tara wpisz liczbę.
5. W polu Maksymalna waga wpisz liczbę.
6. W polu Objętość wpisz liczbę.
7. W polu Długość wpisz liczbę.
8. W polu Szerokość wprowadź liczbę.
9. W polu Wysokość wprowadź liczbę.
10. Wypełnij pole Opis.
11. Kliknij przycisk Zapisz.
12. Kliknij przycisk Nowy.
13. W polu Kod typu kontenera wpisz wartość.
14. Wypełnij pole Opis.
15. W polu Waga tara wpisz liczbę.
16. W polu Maksymalna waga wpisz liczbę.
17. W polu Objętość wpisz liczbę.
18. W polu Długość wpisz liczbę.
19. W polu Szerokość wprowadź liczbę.
20. W polu Wysokość wprowadź liczbę.
21. Kliknij przycisk Zapisz.
22. Kliknij przycisk Nowy.
23. W polu Kod typu kontenera wpisz wartość.
24. Wypełnij pole Opis.
25. W polu Waga tara wpisz liczbę.
26. W polu Maksymalna waga wpisz liczbę.
27. W polu Objętość wpisz liczbę.
28. W polu Długość wpisz liczbę.
29. W polu Szerokość wprowadź liczbę.
30. W polu Wysokość wprowadź liczbę.
31. Kliknij przycisk Zapisz.
32. Zamknij stronę.

## <a name="set-up-a-container-group"></a>Ustawianie grupy kontenera
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Grupy kontenerów.
2. Kliknij przycisk Nowy.
    * Można skonfigurować logiczne grupy typów kontenerów. Dla każdej grupy można określić kolejność, w jakiej mają być pakowane kontenery, i procent wypełnienia kontenerów. Wymiary rozmiaru towaru są używane w celu ustalenia, czy zmieści się on do kontenera. Używany jest kontener, którym wymiarami jest najbardziej zbliżony do towaru. Jeśli masz wiele typów kontenerów w grupie, zaleca się rozmieszczenie kolejności według rozmiarów, tak, aby największy kontener był pierwszy, numer 1 w sekwencji, a najmniejszy kontener ostatni.    
3. W polu Identyfikator grupy kontenerów wpisz wartość.
4. Wypełnij pole Opis.
5. Kliknij przycisk Nowy.
6. Na liście oznacz wybrany wiersz.
7. W polu Typ kontenera wprowadź lub wybierz wartość.
8. Kliknij przycisk Nowy.
9. Na liście oznacz wybrany wiersz.
10. W polu Typ kontenera wprowadź lub wybierz wartość.
11. Kliknij przycisk Nowy.
12. Na liście oznacz wybrany wiersz.
13. W polu Typ kontenera wprowadź lub wybierz wartość.
14. Kliknij przycisk Zapisz.
15. Zamknij stronę.

## <a name="set-up-a-container-build-template"></a>Ustawianie szablonu kompilacji kontenera
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Szablony kompilacji kontenerów.
2. Kliknij przycisk Nowy.
    * Szablon kompilacji kontenera bazuje na doborze wykonywanych procesów konteneryzacji. Każdy szablon kompilacji kontenera definiuje jeden proces konteneryzacji, który będzie używany przez szablon grupy czynności. Opcja Edytuj kwerendę umożliwia określenie warunków, w oparciu o które będzie przetwarzany wybrany szablon. Na przykład można uruchomić konteneryzację tylko dla określonych odbiorców, produktów lub magazynów albo też dodać odpowiednie zakresy zapytań do szablonu. Wartość w polu Kod kroku grupy czynności określa, jak szablon kompilacji kontenera jest powiązany z krokami w szablonie grupy czynności. Podczas wykonywania grupy czynności system ustala, które szablony kompilacji kontenera są używane do inicjowania konteneryzacji. Wartość w polu Rodzaje podstawowej kwerendy określa, co należy zapakować i na czym należy oprzeć filtr zapytania.  
3. Na liście oznacz wybrany wiersz.
4. W polu Identyfikator szablonu kontenera wpisz wartość.
5. W polu Identyfikator grupy kontenerów wprowadź lub wybierz wartość.
6. W polu Kod kroku grupy czynności wpisz wartość.
7. Zaznacz pole wyboru Zezwalaj na dzielenie pobierania.
8. Kliknij przycisk Zapisz.
9. Kliknij opcję Ograniczenia mieszające kontenera.
    * Funkcja Przerwy logiki łączenia pozwala skonfigurować reguły dla wierszy alokacji pakowania w kontenerach. Na przykład jeśli dodasz pole Numer pozycji, podczas przypisywania towarów do kontenerów będą tworzone nowe kontenery dla nowych numerów towarów. Uniemożliwi to pracownikom pakowanie wierszy alokacji dla dwóch różnych odbiorców w tym samym kontenerze.  
10. Kliknij przycisk Nowy.
11. W polu Tabela wybierz opcję.
12. W polu Wybór pola wprowadź lub wybierz wartość.
13. Kliknij przycisk OK.


