---
title: Obliczanie BOM przy użyciu struktury jednopoziomowej (luty 2016)
description: W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu jednopoziomowego rozłożenia opartego na arkuszu wyceny.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7c2c34474cada787b7a7ba720ba177aa8dc125f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214363"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a><span data-ttu-id="bb408-103">Obliczanie BOM przy użyciu struktury jednopoziomowej (luty 2016)</span><span class="sxs-lookup"><span data-stu-id="bb408-103">Calculate a BOM by using a single level structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bb408-104">W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu jednopoziomowego rozłożenia opartego na arkuszu wyceny.</span><span class="sxs-lookup"><span data-stu-id="bb408-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="bb408-105">Jest to szóste zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="bb408-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="bb408-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="bb408-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="bb408-107">Przejdź do okna Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="bb408-107">Go to Released products.</span></span>
2. <span data-ttu-id="bb408-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bb408-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bb408-109">Wybierz produkt BOM_1.</span><span class="sxs-lookup"><span data-stu-id="bb408-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="bb408-110">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="bb408-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="bb408-111">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="bb408-111">Click Item price.</span></span>
5. <span data-ttu-id="bb408-112">Kliknij opcję Oblicz koszt pozycji.</span><span class="sxs-lookup"><span data-stu-id="bb408-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="bb408-113">Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.</span><span class="sxs-lookup"><span data-stu-id="bb408-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="bb408-114">W polu Wersja wyceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="bb408-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="bb408-115">W tej demonstracji wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="bb408-115">For this demo, select 10.</span></span> <span data-ttu-id="bb408-116">Jest to ta sama wersja wyceny, jak używana w celu dodania kosztu własnego do składników.</span><span class="sxs-lookup"><span data-stu-id="bb408-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="bb408-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="bb408-117">Click OK.</span></span>
8. <span data-ttu-id="bb408-118">Kliknij opcję Wyświetl szczegóły obliczeń.</span><span class="sxs-lookup"><span data-stu-id="bb408-118">Click View calculation details.</span></span>
    * <span data-ttu-id="bb408-119">Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.</span><span class="sxs-lookup"><span data-stu-id="bb408-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="bb408-120">Oto elementy składowe kosztu:  \*   10 pochodzi z opcji ITEM_A, 10 z opcji ITEM_B i 10 z opcji BOM_2.</span><span class="sxs-lookup"><span data-stu-id="bb408-120">Here's the composition of the cost:  \*    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="bb408-121">W tym przypadku opcja BOM_2 nie ma żadnych szczegółów, ponieważ tę wartość ręcznie wpisano jako koszt standardowy 10, tzn. nie jest to wynik obliczenia.</span><span class="sxs-lookup"><span data-stu-id="bb408-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="bb408-122">\*  Wartość 7 została ustalona na podstawie czasu przezbrajania i jest kosztem stałym, a dodatkowa wartość 7 została ustalona na podstawie czasu procesu (wykonywania operacji).</span><span class="sxs-lookup"><span data-stu-id="bb408-122">\*    7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="bb408-123">\*   Istnieją również inne kwoty, które odpowiadają kosztom pośrednim.</span><span class="sxs-lookup"><span data-stu-id="bb408-123">\*    There are also other amounts that correspond to indirect costs.</span></span>  
9. <span data-ttu-id="bb408-124">@SysTaskRecorder:_RequestClose</span><span class="sxs-lookup"><span data-stu-id="bb408-124">@SysTaskRecorder:_RequestClose</span></span>

