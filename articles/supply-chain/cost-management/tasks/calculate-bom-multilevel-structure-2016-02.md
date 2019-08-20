---
title: Obliczanie BOM przy użyciu struktury wielopoziomowej (luty 2016)
description: W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu wielopoziomowego rozłożenia opartego na arkuszu wyceny.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0834baf42ed6aa10acec6529513e44ff52ab754
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845649"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a><span data-ttu-id="d3750-103">Obliczanie BOM przy użyciu struktury wielopoziomowej (luty 2016)</span><span class="sxs-lookup"><span data-stu-id="d3750-103">Calculate a BOM by using a multilevel structure (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d3750-104">W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu wielopoziomowego rozłożenia opartego na arkuszu wyceny.</span><span class="sxs-lookup"><span data-stu-id="d3750-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="d3750-105">Jest to siódme zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="d3750-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="d3750-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d3750-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="d3750-107">Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="d3750-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="d3750-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d3750-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d3750-109">Wybierz produkt BOM_1.</span><span class="sxs-lookup"><span data-stu-id="d3750-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="d3750-110">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="d3750-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="d3750-111">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="d3750-111">Click Item price.</span></span>
5. <span data-ttu-id="d3750-112">Kliknij opcję Oblicz koszt pozycji.</span><span class="sxs-lookup"><span data-stu-id="d3750-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="d3750-113">Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.</span><span class="sxs-lookup"><span data-stu-id="d3750-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="d3750-114">W polu Wersja wyceny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="d3750-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="d3750-115">Wybierz wersję wyceny 20, ponieważ ma ona typ Koszt planowany, a w ustawieniu Tryb rozłożenia wartość Wiele poziomów.</span><span class="sxs-lookup"><span data-stu-id="d3750-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="d3750-116">Tryb rozłożenia Wiele poziomów jest przeznaczony dla planowanych kosztów i symulacji.</span><span class="sxs-lookup"><span data-stu-id="d3750-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="d3750-117">Nie jest używany do kosztu standardowego.</span><span class="sxs-lookup"><span data-stu-id="d3750-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="d3750-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d3750-118">Click OK.</span></span>
8. <span data-ttu-id="d3750-119">Kliknij opcję Wyświetl szczegóły obliczeń.</span><span class="sxs-lookup"><span data-stu-id="d3750-119">Click View calculation details.</span></span>
    * <span data-ttu-id="d3750-120">Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.</span><span class="sxs-lookup"><span data-stu-id="d3750-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="d3750-121">W tym przypadku zauważ, jak koszt towaru BOM_2 został obliczony z uwzględnieniem kosztów surowca, przetwarzania i ogólnych na łączną kwotę 29,40 zamiast według kosztu standardowego 10, który był włączony w pierwszym przewodniku po zadaniu w tej serii.</span><span class="sxs-lookup"><span data-stu-id="d3750-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="d3750-122">Kliknij kartę Arkusz wyceny.</span><span class="sxs-lookup"><span data-stu-id="d3750-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="d3750-123">Przejdźmy do karty Arkusz wyceny. Sumy dla każdej grupy kosztów są różne w porównaniu do obliczenia przeprowadzonego w poprzednim przewodniku po zadaniu.</span><span class="sxs-lookup"><span data-stu-id="d3750-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="d3750-124">W polu Poziom wybierz wartość „Wiele”.</span><span class="sxs-lookup"><span data-stu-id="d3750-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="d3750-125">Po wybraniu opcji wielu poziomów koszty są klasyfikowane według składu BOM_2, gdzie wartość 10 jest ustalana na podstawie grupy kosztów M1 (ITEM_C), a wartość 15,60 jest ustalana na podstawie produkcji, w której grupą kosztów jest L2.</span><span class="sxs-lookup"><span data-stu-id="d3750-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="d3750-126">Koszty pośrednie również się różnią.</span><span class="sxs-lookup"><span data-stu-id="d3750-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="d3750-127">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3750-127">Close the page.</span></span>
12. <span data-ttu-id="d3750-128">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d3750-128">Close the page.</span></span>

