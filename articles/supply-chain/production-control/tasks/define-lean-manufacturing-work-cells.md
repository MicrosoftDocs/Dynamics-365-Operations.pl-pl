---
title: Definiowanie komórek roboczych produkcji lean manufacturing
description: Komórka robocza to specjalna postać grupy zasobów, które mogą być używane w działaniach procesu produkcji oszczędnej.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, InventLocationIdLookup, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 068f87d4fcbee95227bb51ea6b7fdcbef8547d06
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257274"
---
# <a name="define-lean-manufacturing-work-cells"></a>Definiowanie komórek roboczych produkcji lean manufacturing

[!include [banner](../../includes/banner.md)]

Komórka robocza to specjalna postać grupy zasobów, które mogą być używane w działaniach procesu produkcji oszczędnej. Komórki robocze mają lokalizacje wejściowe i wyjściowe oraz definicje zdolności produkcyjnych oparte na modelu przepływu produkcji. Aby dowiedzieć się więcej o podstawowych pojęciach dotyczących komórek roboczych i obliczania zdolności produkcyjnych w produkcji oszczędnej, zobacz oficjalne dokumenty o produkcji oszczędnej. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-work-cell"></a>Tworzenie komórki roboczej 
1. Wybierz kolejno opcje Administrowanie organizacją > Zasoby > Grupy zasobów.
2. Kliknij przycisk Nowy.
3. W polu Grupa zasobów wpisz wartość.
    * Identyfikator komórki roboczej jest zazwyczaj systematycznym kodem i musi być unikatowy dla firmy.  
4. Wypełnij pole Opis.
    * Opis zawiera nazwę lub tytuł komórki roboczej.  
5. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Komórka robocza znajduje się w jednym określonym oddziale. Magazyn i lokalizacje wejściowe i wyjściowe muszą się znajdować w tym samym oddziale.  
6. Na liście kliknij łącze w wybranym wierszu.
7. W polu Jednostka produkcyjna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz jednostkę produkcyjną, do której należy ta komórka robocza.  
9. Zaznacz pole wyboru Komórka robocza.
    * Aby użyć grupy zasobów jako komórki roboczej produkcji oszczędnej, należy zaznaczyć pole wyboru Komórka robocza.  Należy zauważyć, że tej właściwości nie można zmodyfikować po utworzeniu grupy zasobów.  
10. W polu Magazyn wejściowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście kliknij łącze w wybranym wierszu.
    * Na potrzeby księgowania i kontroli materiału materiał przygotowany na wydziale produkcji jest zazwyczaj przydzielany do określonego magazynu wirtualnego. Jednak jeśli chcesz uzupełniać lokalizacje przy użyciu pracy magazynowej, materiał musi być częścią magazynu przyjmującego surowce.  
12. W polu Lokalizacja wejściowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
13. Na liście kliknij łącze w wybranym wierszu.
    * Należy zwrócić uwagę, że dla działania procesu lokalizacja wejściowa może zostać zastąpiona ogólnie albo dla określonego produktu lub wariantu produktu przez zdefiniowanie działań pobrania, które zasilają działanie procesu. Lokalizacje wejściowe komórki roboczej nie mogą być kontrolowane przez numery identyfikacyjne.  
14. W polu Magazyn wyjściowy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
15. Na liście znajdź i zaznacz odpowiedni rekord.
    * W przepływach produkcji lub wierszach produkcji z wieloma działaniami często jest to magazyn wejściowy następnej komórki roboczej albo magazyn sprzedaży lub tranzytowy, do którego produkt jest zwykle przenoszony po procesie produkcji. Podczas modelowania procesów produkcji oszczędnej należy pamiętać, że transport jest zazwyczaj odpadem, podobnie jak zgłaszanie transportu.  
16. Na liście kliknij łącze w wybranym wierszu.
17. W polu Lokalizacja wyjściowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * W przepływie produkcji z wieloma działaniami procesu jest to często lokalizacja wejściowa następnej komórki roboczej.  
18. Na liście znajdź i zaznacz odpowiedni rekord.
19. Na liście kliknij łącze w wybranym wierszu.
20. Rozwiń lub zwiń sekcję Operacja.
    * Aby można było obliczać koszty i przetwarzać zadania produkcji oszczędnej w systemie Kanban, należy określić kategorię czasu procesu.  
21. W polu Kategoria czasu procesu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
22. Na liście znajdź i zaznacz odpowiedni rekord.
    * Kategoria kosztu czasu procesu jest używana w obliczeniach kosztów standardowych i wycenie wstecznej.  
23. Na liście kliknij łącze w wybranym wierszu.
24. Rozwiń lub zwiń sekcję Kalendarze.
25. Kliknij przycisk Dodaj.
26. W polu Kalendarz kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
27. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zazwyczaj komórki robocze danego oddziału używają tego samego kalendarza czasu pracy. Jeśli komórki robocze mogą mieć indywidualne czasy pracy, może być konieczne utworzenie osobnego kalendarza czasu pracy dla komórki roboczej. Należy zwrócić uwagę, że kalendarz powinien mieć zdefiniowany standardowy czas pracy, gdy jest używany w komórce roboczej produkcji oszczędnej, ponieważ definicja zdolności produkcyjnych jest zwykle powiązana ze standardowym czasem pracy dnia roboczego.  
28. Na liście kliknij łącze w wybranym wierszu.
29. Rozwiń lub zwiń sekcję Zdolności produkcyjne komórki roboczej.
30. Kliknij przycisk Dodaj.
31. W polu Model przepływu produkcji kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
32. Na liście znajdź i zaznacz odpowiedni rekord.
    * Ta procedura wymaga przepływu produkcji o typie modelu Produktywność, aby pokazywać definicję produktywności.  
33. Na liście kliknij łącze w wybranym wierszu.
34. W polu Okres zdolności produkcyjnych wybierz opcję.
    * Dostępne opcje:   Standardowy dzień roboczy — Zdolności produkcyjne są wyrażane przez długość standardowego dnia roboczego w kalendarzu czasu pracy dla komórki roboczej. Dla każdego dnia rzeczywisty czas pracy jest ustalany na podstawie kalendarza i na tej podstawie oblicza się efektywnie dostępne zdolności produkcyjne.   Tydzień — Zdolności produkcyjne w ujęciu tygodniowym. Nie ma żadnej korekty o rzeczywisty czas pracy.   Miesiąc — Zdolności produkcyjne w ujęciu miesięcznym. Nie ma żadnej korekty o rzeczywiste zdolności produkcyjne.   Na ogół standardowy dzień roboczy jest używany dla okresów dziennych, a tygodniowe zdolności produkcyjnych są używane dla tygodniowych okresów zdolności produkcyjnych.  
35. W polu Średnia produktywność (ilość) wprowadź liczbę.
    * Należy zauważyć, że produkcja oszczędna nigdy nie jest konfigurowana pod kątem maksymalnych możliwych zdolności produkcyjnych w środowisku idealnym. Zamiast tego zdolności produkcyjne zawsze powinny być definiowane dla operacji wykonywanych w typowych warunkach.  
36. W polu Jednostka kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
37. Na liście kliknij łącze w wybranym wierszu.
38. Rozstrzygnij zmiany w jednostce.

## <a name="add-a-financial-dimension"></a>Dodawanie wymiaru finansowego
1. Rozwiń lub zwiń sekcję Wymiary finansowe.
    * Należy zwrócić uwagę, że wymiary finansowe zdefiniowane w przepływie produkcji zastępują wymiary finansowe komórek roboczych.    Wymiary finansowe dostępne do wyboru zależą od konfiguracji wymiarów finansowych w systemie. Poniższe kroki odpowiadają zbiorowi danych demonstracyjnych w firmie USMF. Gdy są używane inne dane, kroki mogą nie mieć zastosowania.  
2. W polu CostCenter kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wymiary, które muszą być zaznaczone w komórkach roboczych produkcji oszczędnej, zależą od implementacji wymiarów finansowych w modelu księgowania w określonej firmie.  
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu ItemGroup kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.

## <a name="save"></a>Zapisz
1. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]