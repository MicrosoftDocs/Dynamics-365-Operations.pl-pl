---
title: Obsługa marszruty modelu produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 45c6b1e6e75645bb17ce4defa0bca0e6d2131b6e
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921272"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="4c158-103">Obsługa marszruty modelu produktu</span><span class="sxs-lookup"><span data-stu-id="4c158-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4c158-104">Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="4c158-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="4c158-105">Ta procedura wykorzystuje w kolejnych krokach model Głośnik o wysokiej jakości zdefiniowany w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4c158-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>

## <a name="add-a-route-operation"></a><span data-ttu-id="4c158-106">Dodawanie operacji marszruty</span><span class="sxs-lookup"><span data-stu-id="4c158-106">Add a route operation</span></span>

1. <span data-ttu-id="4c158-107">Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.</span><span class="sxs-lookup"><span data-stu-id="4c158-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="4c158-108">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4c158-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4c158-109">Do tego ćwiczenia wybierz model Głośnik o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="4c158-109">Select the High end speaker model for this exercise.</span></span>  
1. <span data-ttu-id="4c158-110">Na liście wybierz łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4c158-110">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="4c158-111">Rozwiń sekcję **Operacje marszruty**.</span><span class="sxs-lookup"><span data-stu-id="4c158-111">Expand the **Route operations** section.</span></span>
1. <span data-ttu-id="4c158-112">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4c158-112">Select **Add**.</span></span>
1. <span data-ttu-id="4c158-113">W polu **Nazwa** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c158-113">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="4c158-114">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c158-114">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="4c158-115">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4c158-115">Select **Save**.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="4c158-116">Wprowadzanie szczegółów operacji marszruty</span><span class="sxs-lookup"><span data-stu-id="4c158-116">Enter route operation details</span></span>

1. <span data-ttu-id="4c158-117">Wybierz opcję **Szczegóły operacji marszruty**.</span><span class="sxs-lookup"><span data-stu-id="4c158-117">Select **Route operation details**.</span></span>
1. <span data-ttu-id="4c158-118">W polu **Operacja** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c158-118">In the **Operation** field, enter or select a value.</span></span>
1. <span data-ttu-id="4c158-119">W polu **Nr operacji**</span><span class="sxs-lookup"><span data-stu-id="4c158-119">In the **Oper. No.**</span></span> <span data-ttu-id="4c158-120">wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4c158-120">field, enter a number.</span></span>
    * <span data-ttu-id="4c158-121">Numery operacji decydują o kolejności czynności w marszrucie.</span><span class="sxs-lookup"><span data-stu-id="4c158-121">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="4c158-122">Każda właściwość operacji marszruty może przybierać wartość statyczną lub być zmapowana do atrybutu.</span><span class="sxs-lookup"><span data-stu-id="4c158-122">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="4c158-123">Mapowanie do atrybutu spowoduje ustawianie wartość w trakcie konfigurowania.</span><span class="sxs-lookup"><span data-stu-id="4c158-123">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
1. <span data-ttu-id="4c158-124">W polu **Grupa marszruty** wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="4c158-124">In the **Route group** field, enter or select a value.</span></span>
    * <span data-ttu-id="4c158-125">Grupa marszrut określa podstawowe zachowania dotyczące wyceny, zużycia i konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="4c158-125">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
1. <span data-ttu-id="4c158-126">Kliknij kartę **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="4c158-126">Select the **Setup** tab.</span></span>
1. <span data-ttu-id="4c158-127">Kliknij kartę **Czasy**.</span><span class="sxs-lookup"><span data-stu-id="4c158-127">Select the **Times** tab.</span></span>
1. <span data-ttu-id="4c158-128">W polu **Ilość z procesu** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4c158-128">In the **Process qty.** field, enter a number.</span></span>
    * <span data-ttu-id="4c158-129">Określ, ile będzie przetwarzanych w jednej operacji.</span><span class="sxs-lookup"><span data-stu-id="4c158-129">Determine how many will be processed during one operation.</span></span>  
1. <span data-ttu-id="4c158-130">W polu **Godziny/czas** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4c158-130">In the **Hours/time** field, enter a number.</span></span>
    * <span data-ttu-id="4c158-131">Wprowadź współczynnik czasu.</span><span class="sxs-lookup"><span data-stu-id="4c158-131">Enter the time ratio.</span></span>  
1. <span data-ttu-id="4c158-132">Zaznacz pole wyboru **Ustaw**.</span><span class="sxs-lookup"><span data-stu-id="4c158-132">Select the **Set** check box.</span></span>
1. <span data-ttu-id="4c158-133">W polu **Czas procesu** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="4c158-133">In the **Run time** field, enter a number.</span></span>
    * <span data-ttu-id="4c158-134">Określ czas przetwarzania dla podanej ilości.</span><span class="sxs-lookup"><span data-stu-id="4c158-134">Determine the processing time for the quantity that you have specified.</span></span>  
1. <span data-ttu-id="4c158-135">Kliknij kartę **Zapotrzebowanie na zasoby**.</span><span class="sxs-lookup"><span data-stu-id="4c158-135">Select the **Resource requirements** tab.</span></span>
1. <span data-ttu-id="4c158-136">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4c158-136">Select **Add**.</span></span>
1. <span data-ttu-id="4c158-137">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="4c158-137">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="4c158-138">W polu **Typ wymagania** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="4c158-138">In the **Requirement type** field, select an option.</span></span>
    * <span data-ttu-id="4c158-139">Zdecyduj, czy chcesz określić konkretne zasoby czy możliwości, które muszą posiadać.</span><span class="sxs-lookup"><span data-stu-id="4c158-139">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
1. <span data-ttu-id="4c158-140">W polu **Zapotrzebowanie** wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="4c158-140">In the **Requirement** field, enter or select a value.</span></span>
1. <span data-ttu-id="4c158-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c158-141">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]