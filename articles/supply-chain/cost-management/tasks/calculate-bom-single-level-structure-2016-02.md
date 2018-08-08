--- 
title: "Obliczanie BOM przy użyciu struktury jednopoziomowej (tylko luty 2016)"
description: "W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu jednopoziomowego rozłożenia opartego na arkuszu wyceny."
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1def2baf6a42ae4f8d117b4c06f402397b83bf88
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016-only"></a><span data-ttu-id="ff01b-103">Obliczanie BOM przy użyciu struktury jednopoziomowej (tylko luty 2016)</span><span class="sxs-lookup"><span data-stu-id="ff01b-103">Calculate a BOM by using a single level structure (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff01b-104">W tej procedurze pokazano, jak obliczyć koszt wyrobu gotowego przy użyciu jednopoziomowego rozłożenia opartego na arkuszu wyceny.</span><span class="sxs-lookup"><span data-stu-id="ff01b-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="ff01b-105">Jest to szóste zadanie w serii zadań obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="ff01b-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="ff01b-106">Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="ff01b-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="ff01b-107">Przejdź do okna Zwolnione produkty.</span><span class="sxs-lookup"><span data-stu-id="ff01b-107">Go to Released products.</span></span>
2. <span data-ttu-id="ff01b-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ff01b-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ff01b-109">Wybierz produkt BOM_1.</span><span class="sxs-lookup"><span data-stu-id="ff01b-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="ff01b-110">W okienku akcji kliknij pozycję Zarządzanie kosztami.</span><span class="sxs-lookup"><span data-stu-id="ff01b-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="ff01b-111">Kliknij opcję Cena pozycji.</span><span class="sxs-lookup"><span data-stu-id="ff01b-111">Click Item price.</span></span>
5. <span data-ttu-id="ff01b-112">Kliknij opcję Oblicz koszt pozycji.</span><span class="sxs-lookup"><span data-stu-id="ff01b-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="ff01b-113">Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.</span><span class="sxs-lookup"><span data-stu-id="ff01b-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="ff01b-114">W polu Wersja wyceny kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="ff01b-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="ff01b-115">W tej demonstracji wybierz opcję 10.</span><span class="sxs-lookup"><span data-stu-id="ff01b-115">For this demo, select 10.</span></span> <span data-ttu-id="ff01b-116">Jest to ta sama wersja wyceny, jak używana w celu dodania kosztu własnego do składników.</span><span class="sxs-lookup"><span data-stu-id="ff01b-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="ff01b-117">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="ff01b-117">Click OK.</span></span>
8. <span data-ttu-id="ff01b-118">Kliknij opcję Wyświetl szczegóły obliczeń.</span><span class="sxs-lookup"><span data-stu-id="ff01b-118">Click View calculation details.</span></span>
    * <span data-ttu-id="ff01b-119">Może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić tę opcję w górnym menu.</span><span class="sxs-lookup"><span data-stu-id="ff01b-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="ff01b-120">Oto elementy składowe kosztu:  •    10 pochodzi z opcji ITEM_A, 10 z opcji ITEM_B i 10 z opcji BOM_2.</span><span class="sxs-lookup"><span data-stu-id="ff01b-120">Here's the composition of the cost:  •    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="ff01b-121">W tym przypadku opcja BOM_2 nie ma żadnych szczegółów, ponieważ tę wartość ręcznie wpisano jako koszt standardowy 10, tzn. nie jest to wynik obliczenia.</span><span class="sxs-lookup"><span data-stu-id="ff01b-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="ff01b-122">•  Wartość 7 została ustalona na podstawie czasu przezbrajania i jest kosztem stałym, a dodatkowa wartość 7 została ustalona na podstawie czasu procesu (wykonywania operacji).</span><span class="sxs-lookup"><span data-stu-id="ff01b-122">•  7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="ff01b-123">•   Istnieją również inne kwoty, które odpowiadają kosztom pośrednim.</span><span class="sxs-lookup"><span data-stu-id="ff01b-123">•   There are also other amounts that correspond to indirect costs.</span></span>  
9. @SysTaskRecorder:_RequestClose


