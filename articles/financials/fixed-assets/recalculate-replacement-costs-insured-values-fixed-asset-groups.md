---
title: Ponowne obliczanie kosztów wymiany i wartości ubezpieczenia dla grup środków trwałych
description: W tym artykule wyjaśniono proces aktualizowania kosztów wymiany i wartości ubezpieczenia środków trwałych.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3261
ms.assetid: b8876f83-8772-4f2a-b277-12724e2a0c44
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0756287406ad12237632ffbd455dbc6ba15d9915
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563372"
---
# <a name="recalculate-replacement-costs-and-insured-values-for-fixed-asset-groups"></a>Ponowne obliczanie kosztów wymiany i wartości ubezpieczenia dla grup środków trwałych

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono proces aktualizowania kosztów wymiany i wartości ubezpieczenia środków trwałych.

Okresowo możesz otrzymywać powiadomienie, że koszt wymiany lub ubezpieczenia określonych środków trwałych uległ zmianie. Na przykład, Twój menedżer może poinformować Cię, że w zeszłym roku inflacja wynosiła 3%, więc musisz zwiększyć koszt wymiany wszystkich środków trwałych o 3%. 

Mimo że można edytować koszty wymiany oraz wartości ubezpieczenia dla poszczególnych środków trwałych na stronie **Środki trwałe**, można użyć strony **Zaktualizuj koszty wymiany i wartości ubezpieczenia** w celu aktualizacji tych wartości dla całej grupy środków trwałych jednocześnie. Ta informacja wskazuje, jak aktualizować wartości dla grup środków trwałych lub określonych środków w grupach.

## <a name="how-values-are-updated"></a> Sposób aktualizacji wartości
Aby ponownie obliczyć koszty wymiany oraz wartości ubezpieczenia grup środków trwałych, należy w pierwszej kolejności określić wartość procentową, o jaką mają się zmienić obecne koszty wymiany i wartości ubezpieczenia, a następnie przeprowadzić okresową aktualizację w celu ponownego obliczenia wartości. Można określić wartość procentową w polach **Współczynnik kosztu wymiany** i **Współczynnik wartości ubezpieczenia** na stronie **Grupy środków trwałych**. Mimo że współczynniki te podaje się dla całej grupy środków trwałych, w przypadku korzystania ze strony **Zaktualizuj koszty wymiany i wartości ubezpieczenia** można wybrać opcję ponownego obliczania kosztów wymiany oraz wartości ubezpieczenia dla określonych środków trwałych w danej grupie. 

W przypadku korzystania ze strony **Zaktualizuj koszty wymiany i wartości ubezpieczenia** w celu ponownego obliczania kosztów wymiany oraz wartości ubezpieczenia dla środków trwałych, system korzysta z następujących wzorów:

-   \[(Współczynnik kosztów wymiany grupy środków trwałych / 100) + 1\] \* Obecny koszt wymiany środków trwałych
-   \[(Współczynnik wartości ubezpieczenia grupy środków trwałych / 100) + 1\] \* Obecna wartość ubezpieczenia środków trwałych

> [!NOTE] 
> Gdy używana jest strona **Zaktualizuj koszty wymiany i wartości ubezpieczenia**, koszt wymiany oraz wartość ubezpieczenia są aktualizowane dla wybranych środków trwałych; nie można określić, aby tylko jedna wartość została zaktualizowana. Aby pozostawić jedną wartość taką samą i jednocześnie zaktualizować drugą wartość, wprowadź 0 (zero) jako współczynnik na stronie **Grupy środków trwałych**. Współczynnik równy zero lub brak wartości powodują pominięcie obliczania podczas aktualizacji. Wartość księgowa oraz wartość księgowa netto środków trwałych nie są objęte okresową aktualizacją. 

## <a name="how-to-use-a-date-to-select-which-items-to-update"></a> Korzystanie z daty w celu wybrania elementów do aktualizacji
Domyślnie proces aktualizacji aktualizuje wybrane środki trwałe, które nie zostały zaktualizowane bieżącego dnia, ale które mogły być zaktualizowane poprzedniego dnia. Na przykład &lt; bieżąca data oznacza „przed dniem dzisiejszym”. Można zmienić datę na stronie **Zaktualizuj koszty wymiany i wartości ubezpieczenia**, klikając przycisk **Wybierz**. Określone kryteria daty są porównywane z datą ostatniej okresowej aktualizacji dla środków trwałych (pole **Ostatnia okresowa aktualizacja wartości/kosztu** na stronie **Środki trwałe**). Za każdym razem, gdy zostaje pomyślnie zaktualizowany koszt wymiany lub wartość ubezpieczenia dla środków trwałych, system automatycznie aktualizuje pole **Ostatnia okresowa aktualizacja wartości/kosztu** bieżącą datą. 

Przykład 

Zaktualizowano wczoraj o 5 procent koszt wymiany grup pojazdów, mebli biurowych oraz budynków, a teraz stwierdzasz, że te środki trwałe zostały prawidłowo zaktualizowane. Aby wykluczyć te środki trwałe z dzisiejszej aktualizacji pozostałych środków trwałych, wprowadzasz datę w polu **Ostatnia okresowa aktualizacja wartości/kosztu**, która jest datą wcześniejszą niż wczorajsza (&lt; data wczorajsza), ponieważ ostatnia okresowa aktualizacja dla grup **Pojazdy**, **Meble biurowe** i **Budynki** wystąpiła poza wprowadzonym kryterium daty.

## <a name="cumulative-effect-of-each-update"></a> Skumulowane skutki każdej aktualizacji
Każda aktualizacja ma skutki skumulowane. Dlatego należy ostrożnie planować aktualizacje. Na przykład, jeśli zwiększysz środki trwałe w czwartek o 3%, a następnie zwiększysz w piątek ilość mebli biurowych o 4%, wartość mebli wzrośnie łącznie o 7,12%.

## <a name="scenario"></a>Scenariusz
Twój menedżer powiadamia Cię o następujących zmianach w środkach trwałych:
-   Zwiększyć koszt wymiany wszystkich środków trwałych oprócz komputerów o 3,25%.
-   Zwiększyć koszt wymiany wszystkich mebli biurowych dodatkowo o 1%.
-   Obniżyć koszt wymiany oraz wartość ubezpieczenia wszystkich komputerów o 10%.

Można dokonać następujących zmian:
1.  Na stronie **Grupy środków trwałych** dla wszystkich grup środków trwałych, poza grupami **Meble biurowe** i **Komputery**, wpisujemy 3,25 w polu **Współczynnik kosztu wymiany** i 0 w polu **Współczynnik wartości ubezpieczenia**.
2.  Dla grupy **Meble biurowe** wpisujemy 4,25 w polu **Współczynnik kosztu wymiany** i 0 w polu **Współczynnik wartości ubezpieczenia**.
3.  Dla grupy **Komputery wpisujemy** -10 w polu **Współczynnik kosztu wymiany** i -10 w polu **Współczynnik wartości ubezpieczenia**.
4.  Na stronie **Zaktualizuj koszty wymiany i wartości ubezpieczenia** kliknij przycisk **OK**, aby wykonać ponowne wyliczenie dla wszystkich środków trwałych.

Następnego dnia menedżer informuje Cię, że komputery spadły o 8% zamiast 10%, więc musisz poprawić koszty wymiany oraz wartości ubezpieczenia. Aby poprawić ten błąd, można użyć jednej z dwóch metod:
-   Ręcznie zmień zawartość pól **Wartość ubezpieczenia** i **Koszt wymiany** na stronie **Środki trwałe** dla każdego środka trwałego w grupie środków trwałych **Komputery**. Oblicz i ręcznie wprowadź wartości, tak jakby początkowa kwota została obniżona o 8%. Korzystając z tej metody nie używa się strony **Zaktualizuj koszty wymiany i wartości ubezpieczenia**.
-   Wprowadź koszt wymiany i wartości ubezpieczenia dla grupy **Komputery** w polach **Współczynnik kosztu wymiany** i **Współczynnik wartości ubezpieczenia** na stronie **Grupy środków trwałych**. Spowoduje to zresetowanie środków trwałych do wartości początkowej (przed obniżeniem wartości o 10%) i zastosowanie 8% obniżenia wartości początkowej. Następnie użyj strony **Zaktualizuj koszty wymiany i wartości ubezpieczenia** do ponownego obliczenia wartości, w zależności od współczynników, które zostały wprowadzone.

> [!NOTE]  
> Można wycofać współczynnik –10 poprzez wprowadzenie dodatniego współczynnika 10 (lub współczynnika 2, czyli różnicy między –10 i –8), ponieważ kwoty nie zostaną obliczone zgodnie z zamierzeniem. 





