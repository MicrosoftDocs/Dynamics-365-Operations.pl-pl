--- 
title: "Tworzenie działań procesu produkcji lean manufacturing"
description: "Tworzenie działania procesu dla produkcji oszczędnej."
author: cvocph
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: dd77c20b622fd8a14e1cdf77883043699f9a6317
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-process-activities-for-lean-manufacturing"></a>Tworzenie działań procesu produkcji lean manufacturing

[!include [task guide banner](../../includes/task-guide-banner.md)]

Tworzenie działania procesu dla produkcji oszczędnej. 

Wymagania wstępne: 

1. Musi być utworzony przepływ produkcji i wersja, która nie jest aktywna.

2. Musi być utworzona komórka robocza.


## <a name="find-the-production-flow-version"></a>Znajdowanie wersji przepływu produkcji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.

## <a name="create-a-new-activity"></a>Tworzenie nowego działania
1. Kliknij opcję Działania.
    * Upewnij się, że wybrany przepływ produkcji ma wersję roboczą, i zaznacz tę wersję.  
2. Kliknij opcję Utwórz nowe działanie planu.
3. Kliknij przycisk Dalej.
4. W polu Nazwa wpisz wartość.
5. W polu Nazwa wpisz wartość.
    * Należy zauważyć, że wszystkie wersje przepływu produkcji muszą mieć unikatowe nazwy.  
6. W polu Ilość dla procesu wprowadź liczbę.
    * Należy zauważyć, że niezależnie od tego, jaka ilość zadania będzie przetwarzana, jest to minimalna ilość w zadaniu, dla jakiej będą obliczane koszty robocizny. Jeśli ilości w zadaniu różnią się od tej ilości, zostanie utworzone odchylenie kosztów robocizny.  
7. Kliknij przycisk Dalej.

## <a name="select-the-work-cell"></a>Wybór komórki roboczej
1. W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
2. Na liście kliknij łącze w wybranym wierszu.

## <a name="define-the-inventory-updates"></a>Definiowanie aktualizacji zapasów
1. Zaznacz lub wyczyść pole wyboru Aktualizuj przychód dostępnych zapasów.
    * Jeśli opcja Aktualizuj dostępne zapasy ma wartość Nie, można określić działanie przyjęcia półproduktu (działania nie osiąga następnego poziomu BOM).    Można również wybrać opcję zużywania półproduktów.  

## <a name="define-the-picking-activities"></a>Definiowanie działań pobrania
1. Kliknij przycisk Dalej.
2. Na liście oznacz wybrany wiersz.
    * Dla lokalizacji wejściowej wybranej komórki roboczej jest tworzone domyślne działanie pobrania.  
3. Kliknij przycisk Dodaj.
    * Można utworzyć dodatkowe działania pobrania dla określonych produktów, które nie są przygotowywane w działaniu wprowadzenia do komórki roboczej.  
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. W polu Numer towaru wpisz wartość.
6. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * W przypadku tej definicji wszystkie materiały zużywane w działaniu są pobierane z domyślnego magazynu wejściowego i lokalizacji, z wyjątkiem towaru, który jest zdefiniowany w drugim działaniu pobrania. Ten towar będzie pobierany z innego magazynu i lokalizacji.  
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. Zaznacz lub wyczyść pole wyboru Zarejestruj braki.
10. Kliknij przycisk Dalej.

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


