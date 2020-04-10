---
title: Tworzenie prognozy bazowej
description: Planista produkcji można utworzyć bazową prognozę przy użyciu modeli prognozowania serii czasowych lub przez skopiowanie historycznego popytu.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 85d687c0c21112f815bb5cf28b0af5501d299c12
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148131"
---
# <a name="create-a-baseline-forecast"></a>Tworzenie prognozy bazowej

[!include [banner](../../includes/banner.md)]

Planista produkcji można utworzyć bazową prognozę przy użyciu modeli prognozowania serii czasowych lub przez skopiowanie historycznego popytu. W tej procedurze pokazano sposób kopiowania historycznego popytu w celu utworzenia prognozy bazowej dla wszystkich produktów za pomocą jednego klucza alokacji produktów. 


## <a name="set-up-an-item-allocation-key"></a>Ustawianie klucza alokacji towaru
1. Wybierz kolejno opcje Planowanie główne > Ustawienia > Grupy planowania międzyfirmowego.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa z wartością „10”.
    * Prognozowanie popytu odbywa się wśród podmiotów prawnych. Dlatego wszystkie firmy, dla których chcesz wygenerować prognozy, należy umieścić w jednej międzyfirmowej grupie planowania.  
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Kliknij opcję kluczy alokacji produktów.
    * Wybierz wszystkie klucze alokacji produktów, dla których chcesz utworzyć prognozy.  
5. Na liście oznacz wybrany wiersz.
    * Wybierz klucz alokacji produktów D_Aloc.  
6. Kliknij >.
7. Zamknij stronę.
8. Zamknij stronę.

## <a name="set-up-the-demand-forecasting-paramters"></a>Konfigurowanie parametrów prognozowania popytu
1. Wybierz kolejno opcje Planowanie główne > Ustawienia > Prognozowanie popytu > Parametry prognozowania popytu.
2. Rozwiń sekcję Parametry algorytmu prognozy.
3. W polu Strategia generowania prognozy wybierz opcję „Kopiuj na popycie historycznym”.
4. Kliknij przycisk Zapisz.

## <a name="create-a-baseline-forecast"></a>Tworzenie prognozy bazowej
1. Wybierz kolejno opcje Planowanie główne > Prognozowanie > Prognozowanie popytu > Generuj bazową prognozę statystyczną.
2. W polu Od dnia wprowadź datę.
    * Jeśli masz zamówienia sprzedaży rozpoczynające się od 1 stycznia 2015 r., należy wprowadzić tę datę. W przeciwnym wypadku wprowadź najwcześniejszą datę zamówień sprzedaży.  
3. Wprowadź datę w polu Do dnia.
    * Wprowadź ostatnią datę swoich zamówień sprzedaży, np. „2015-03-31”.  
4. W polu Od dnia wprowadź datę.
    * Wprowadź „2015-04-01”. Data ta będzie obliczana automatycznie jako data rozpoczęcia następnego przedziału prognozowania.  
5. Rozwiń sekcję Rekordy do uwzględnienia.
6. Kliknij przycisk Filtr.
7. Na liście oznacz wybrany wiersz.
    * Zaznacz wiersz, gdzie Pole = Grupa planowania międzyfirmowego.  
8. W polu Kryteria wpisz wartość.
    * Wpisz grupę planowania międzyfirmowego, na przykład 10, której użyto w pierwszym zadaniu.  
9. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wiersz, gdzie Pole = Klucz alokacji produktów.  
10. W polu Kryteria wpisz wartość.
11. Kliknij przycisk OK.
12. Rozwiń sekcję Parametry zaawansowane.
13. W polu Przedział prognozy zaznacz wartość „Miesiąc”.
14. W polu Horyzont prognozy wpisz wartość „3”.
15. W polu Horyzont czasowy zamrożenia wpisz „1”.
16. Kliknij przycisk OK.

## <a name="visualize-the-demand-forecast"></a>Wizualizacja prognozy popytu
1. Wybierz kolejno opcje Planowanie główne > Prognozowanie > Prognozowanie popytu > Skorygowana prognoza popytu.
2. W tabeli zagregowanego widoku zaznacz komórkę w wierszu 1 w kolumnie 2. Jest to drugi miesiąc, dla którego utworzono prognozę.
3. W atrybucie QtyCell ustaw wartość „400”.
    * W komórce wprowadź liczbę inną niż prognozowana, na przykład 400.  
4. Dokonano ręcznego dopasowania do prognozy. Zwróć uwagę na wskazanie graficzne w kolejnym kroku.
5. Kliknij opcję Szczegóły wiersza prognozy.
    * Na tej stronie można wyświetlić wartości dokładności, popyt historyczny i prognozę. Można także modyfikować prognozę.  

