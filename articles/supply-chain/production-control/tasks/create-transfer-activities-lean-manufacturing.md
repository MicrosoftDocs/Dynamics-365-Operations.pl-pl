---
title: Tworzenie działań przeniesienia produkcji lean manufacturing
description: Tworzenie działania przeniesienia dla produkcji oszczędnej.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae31cca96825665f9482b4523b66586415504b65
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210808"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>Tworzenie działań przeniesienia produkcji lean manufacturing

[!include [banner](../../includes/banner.md)]

Tworzenie działania przeniesienia dla produkcji oszczędnej. 

Wymagania wstępne: 

1. Musi być utworzony przepływ produkcji i wersja, która nie jest aktywna.

2. Muszą być utworzone magazyny i lokalizacje źródłowe oraz docelowe. Opcjonalnie można utworzyć uzupełnienie lub komórkę roboczą uzupełnienia.


## <a name="find-the-production-flow-version"></a>Znajdowanie wersji przepływu produkcji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Należy zauważyć, że przepływ produkcji musi mieć wersję roboczą.  
3. Na liście kliknij łącze w wybranym wierszu.

## <a name="create-a-new-activity"></a>Tworzenie nowego działania
1. Kliknij opcję Działania.
    * Upewnij się, że wybrany przepływ produkcji ma wersję roboczą, i zaznacz tę wersję.  
2. Kliknij opcję Utwórz nowe działanie planu.
3. Kliknij przycisk Dalej.
4. W polu Nazwa wpisz wartość.
5. W polu Typ działania wybierz opcję „Przeniesienie”.
6. W polu Ilość dla procesu wprowadź liczbę.
7. Kliknij przycisk Dalej.

## <a name="select-the-work-cells"></a>Wybór komórek roboczych
1. W polu Uzupełnienie kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Aby użyć lokalizacji wyjściowej komórki roboczej jako lokalizacji źródłowej w działaniu przeniesienia, zaznacz komórkę roboczą. To samo można zrobić z uzupełnioną komórką roboczą, co ustawi lokalizację docelową działania przeniesienia.  
2. Na liście kliknij łącze w wybranym wierszu.

## <a name="define-the-inventory-updates"></a>Definiowanie aktualizacji zapasów
1. W polu Typ produktu wybierz opcję.
    * Należy zwrócić uwagę, że przeniesienie nie zmienia typu produktu. Można przenosić wyroby gotowe lub półprodukty (przenoszenie między dwoma działaniami w przepływie produkcji i ewentualnie w przepływie Kanban).     Podczas przenoszenia wyrobów gotowych można określić, czy transakcja magazynowa będzie efektem pobrania czy przyjęcia.  

## <a name="define-the-transfer-locations"></a>Definiowanie lokalizacji przeniesienia
1. Kliknij przycisk Dalej.
2. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij łącze w wybranym wierszu.
7. W polu Transportowane przez wybierz opcję „Spedytor”.
    * Dostępne są następujące opcje: Spedytor — organizacja prowadząca magazyn wysyłki, Adresat — organizacja prowadząca magazyn przyjęcia, Przewoźnik — zewnętrzny dostawca. Jeśli organizacją realizującą jest dostawcą, działanie przeniesienia wymaga umowy podwykonawstwa.  
8. Kliknij przycisk Dalej.

## <a name="define-the-activity-times"></a>Definiowanie czasów działań
1. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zdefiniowanie czasu wykonywania jest wymagane. Czas wykonywania jest używany do obliczania kosztów i czasów produktywności w zadaniach w systemie Kanban. Czasy wykonywania nie są używane do obliczania obciążenia zdolności produkcyjnych i zużycia. Do obliczania tych parametrów służy czas cyklu pochodzący z zadania w wersji przepływu produkcji.  
2. W polu Czas wpisz liczbę.
3. W polu Jednostka wpisz wartość.
4. Wybierz jednostkę czasu.
5. W polu Na ilość wprowadź liczbę.
6. Na liście znajdź i zaznacz odpowiedni rekord.
    * Czasy oczekiwania są opcjonalne.  
7. W polu Czas wpisz liczbę.
8. W polu Jednostka wpisz wartość.
9. Wybierz jednostkę czasu.
10. W polu Na ilość wprowadź liczbę.
11. Kliknij przycisk Dalej.
12. Kliknij przycisk Zakończ.
13. Zamknij stronę.

