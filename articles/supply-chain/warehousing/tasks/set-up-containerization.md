---
title: Konfigurowanie konteneryzacji
description: W tym temacie opisano sposób zautomatyzowania konteneryzacji ładunków w module Zarządzanie magazynem.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/19
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b5ad1bdd91a2fb9109f29400f082e9a8af009ba
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216949"
---
# <a name="set-up-containerization"></a>Konfigurowanie konteneryzacji

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób zautomatyzowania konteneryzacji ładunków w module Zarządzanie magazynem. Podczas przetwarzania grupy czynności funkcja automatycznej konteneryzacji tworzy kontenery i pracę pobrania dla wysyłek, a wiersze pracy można podzielić na ilości mieszczące się w kontenerach. W ten sposób pracownicy magazynu mogą pobierać towary bezpośrednio do wybranego kontenera. W porównaniu do ręcznego procesu pakowania zadania takie jak tworzenie kontenerów, przypisywania towarów i zamykanie kontenerów są zautomatyzowane przez system. Ta procedura używa firmy demonstracyjnej USMF i jest wykonywana przez kierownika magazynu.


## <a name="set-up-a-wave-template"></a>Konfigurowanie szablonu grupy czynności
1. W okienku nawigacji przejdź do **Moduły > zarządzanie magazynem > Ustawienia > Grupy czynności > Szablony grupy czynności**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa szablonu grupy czynności** wpisz wartość.
4. W polu **Opis szablonu grupy czynności** wpisz wartość.
5. W polu **Oddział** wprowadź lub wybierz wartość.
6. W polu **Magazyn** wprowadź lub wybierz wartość.
7. Rozwiń sekcję **Metody**. W okienku **Wybrane metody** są wyświetlane metody dla wybranego typu szablonu grupy czynności. Szablon grupy czynności musi zawierać metodę konteneryzacji.  
8. W polu **Kod kroku grupy czynności** wpisz wartość. Wprowadź kod kroku grupy czynności dla dodanej metody. Może to być dowolny kod. Istnieje możliwość dodania metody więcej niż jeden raz oraz przypisania różnych kodów kroków grupy czynności. Aby to zrobić, zaznacz dla tej metody opcję **Cykliczny** na stronie **Metody przetwarzania grupy czynności**.  
9. Wybierz opcję **Zapisz**.
10. Zamknij stronę.

## <a name="set-up-a-container-type"></a>Konfigurowanie typu kontenera
1. W okienku nawigacji przejdź do **Moduły > zarządzanie magazynem > Ustawienia > Kontenery > Typy kontenerów**. Kontenery można zdefiniować na stronie **Typy kontenerów**. Można skonfigurować wymiary fizyczne kontenera, w tym tarę, maksymalną wagę, maksymalną objętość, długość, szerokość i wysokość. W tym przykładzie mamy trzy różne rozmiary skrzynek.  
2. Wybierz pozycję **Nowy**.
3. W polu **Kod typu kontenera** wpisz wartość.
4. W polu **Waga tara** wpisz liczbę.
5. W polu **Maksymalna waga** wpisz liczbę.
6. W polu **Objętość** wpisz liczbę.
7. W polu **Długość** wpisz liczbę.
8. W polu **Szerokość** wprowadź liczbę.
9. W polu **Wysokość** wprowadź liczbę.
10. W polu **Opis** wpisz wartość.
11. Wybierz opcję **Zapisz**.
13. Powtórz kroki 2-11 jeszcze dwa razy, aby utworzyć trzy typy kontenerów ogółem.
14. Zamknij stronę.

## <a name="set-up-a-container-group"></a>Ustawianie grupy kontenera
1. W okienku nawigacji przejdź do **Moduły > zarządzanie magazynem > Ustawienia > Kontenery > Grupy kontenerów**.
2. W okienku akcji wybierz opcję **Nowy**. Można skonfigurować logiczne grupy typów kontenerów. Dla każdej grupy można określić kolejność, w jakiej mają być pakowane kontenery, i procent wypełnienia kontenerów. Wymiary rozmiaru towaru są używane w celu ustalenia, czy zmieści się on do kontenera. Używany jest kontener, którym wymiarami jest najbardziej zbliżony do towaru. Jeśli masz wiele typów kontenerów w grupie, zaleca się rozmieszczenie kolejności według rozmiarów, tak, aby największy kontener był pierwszy, numer 1 w sekwencji, a najmniejszy kontener ostatni.    
3. W polu **Identyfikator grupy** kontenerów wpisz utworzoną wcześniej wartość.
4. W polu **Opis** wpisz wartość.
5. Powtórz kroki 2-4 dla wszystkich trzech typów kontenerów utworzonych wcześniej.
6. Wybierz opcję **Zapisz**.
7. Zamknij stronę.

## <a name="set-up-a-container-build-template"></a>Ustawianie szablonu kompilacji kontenera
1. W okienku nawigacji przejdź do **Moduły > zarządzanie magazynem > Ustawienia > Kontenery > Szablony kompilacji kontenerów**.
2. Wybierz pozycję **Nowy**. Szablon kompilacji kontenera bazuje na doborze wykonywanych procesów konteneryzacji. Każdy szablon kompilacji kontenera definiuje jeden proces konteneryzacji, który będzie używany przez szablon grupy czynności. Opcja **Edytuj kwerendę** umożliwia określenie warunków, w oparciu o które będzie przetwarzany wybrany szablon. Na przykład można uruchomić konteneryzację tylko dla określonych odbiorców, produktów lub magazynów albo też dodać odpowiednie zakresy zapytań do szablonu. Wartość w polu **Kod kroku grupy czynności** określa, jak szablon kompilacji kontenera jest powiązany z krokami w szablonie grupy czynności. Podczas wykonywania grupy czynności system ustala, które szablony kompilacji kontenera są używane do inicjowania konteneryzacji. Wartość w polu Rodzaje podstawowej kwerendy określa, co należy zapakować i na czym należy oprzeć filtr zapytania. 
3. W polu **Identyfikator szablonu kontenera** wpisz wartość.
4. W polu **Identyfikator grupy kontenerów** wprowadź lub wybierz wartość.
5. W polu **Kod kroku grupy czynności** wpisz wartość.
6. Zaznacz pole wyboru **Zezwalaj na dzielenie pobierania**.
7. Wybierz opcję **Zapisz**.
8. Wybierz opcję **Ograniczenia mieszające kontenera**. Funkcja Przerwy logiki łączenia pozwala skonfigurować reguły dla wierszy alokacji pakowania w kontenerach. Na przykład jeśli dodasz pole **Numer pozycji**, podczas przypisywania towarów do kontenerów będą tworzone nowe kontenery dla nowych numerów towarów. Uniemożliwi to pracownikom pakowanie wierszy alokacji dla dwóch różnych odbiorców w tym samym kontenerze.  
9. Wybierz pozycję **Nowy**.
10. W polu **Tabela** wybierz opcję.
11. W polu **Wybór pola** wprowadź lub wybierz wartość.
12. Kliknij przycisk **OK**.

