---
title: Obsługa marszruty modelu produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24419cb9bad4b4344fe23789750387de6cca3796
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203538"
---
# <a name="maintain-route-for-a-product-model"></a><span data-ttu-id="9a71c-103">Obsługa marszruty modelu produktu</span><span class="sxs-lookup"><span data-stu-id="9a71c-103">Maintain route for a product model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9a71c-104">Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="9a71c-104">Running this procedure requires that a product configuration model exists.</span></span> <span data-ttu-id="9a71c-105">Ta procedura wykorzystuje w kolejnych krokach model Głośnik o wysokiej jakości zdefiniowany w firmie demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="9a71c-105">This procedure uses the High end speaker model in the demo company USMF to walk you through the process.</span></span>


## <a name="add-a-route-operation"></a><span data-ttu-id="9a71c-106">Dodawanie operacji marszruty</span><span class="sxs-lookup"><span data-stu-id="9a71c-106">Add a route operation</span></span>
1. <span data-ttu-id="9a71c-107">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="9a71c-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="9a71c-108">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="9a71c-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="9a71c-109">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="9a71c-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9a71c-110">Do tego ćwiczenia wybierz model Głośnik o wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="9a71c-110">Select the High end speaker model for this exercise.</span></span>  
4. <span data-ttu-id="9a71c-111">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="9a71c-111">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="9a71c-112">Rozwiń sekcję Operacje marszruty.</span><span class="sxs-lookup"><span data-stu-id="9a71c-112">Expand the Route operations section.</span></span>
6. <span data-ttu-id="9a71c-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9a71c-113">Click Add.</span></span>
7. <span data-ttu-id="9a71c-114">W polu Nazwa wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="9a71c-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="9a71c-115">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="9a71c-115">In the Description field, type a value.</span></span>
9. <span data-ttu-id="9a71c-116">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9a71c-116">Click Save.</span></span>

## <a name="enter-route-operation-details"></a><span data-ttu-id="9a71c-117">Wprowadzanie szczegółów operacji marszruty</span><span class="sxs-lookup"><span data-stu-id="9a71c-117">Enter route operation details</span></span>
1. <span data-ttu-id="9a71c-118">Kliknij opcję Szczegóły operacji marszruty.</span><span class="sxs-lookup"><span data-stu-id="9a71c-118">Click Route operation details.</span></span>
2. <span data-ttu-id="9a71c-119">W polu Operacja wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9a71c-119">In the Operation field, enter or select a value.</span></span>
3. <span data-ttu-id="9a71c-120">W polu Nr operacji</span><span class="sxs-lookup"><span data-stu-id="9a71c-120">In the Oper.</span></span> <span data-ttu-id="9a71c-121">Nr</span><span class="sxs-lookup"><span data-stu-id="9a71c-121">No.</span></span> <span data-ttu-id="9a71c-122">wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="9a71c-122">field, enter a number.</span></span>
    * <span data-ttu-id="9a71c-123">Numery operacji decydują o kolejności czynności w marszrucie.</span><span class="sxs-lookup"><span data-stu-id="9a71c-123">Operation numbers determine the route sequence.</span></span>  
    * <span data-ttu-id="9a71c-124">Każda właściwość operacji marszruty może przybierać wartość statyczną lub być zmapowana do atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9a71c-124">Each property on a route operation can get a static value or be mapped to an attribute.</span></span> <span data-ttu-id="9a71c-125">Mapowanie do atrybutu spowoduje ustawianie wartość w trakcie konfigurowania.</span><span class="sxs-lookup"><span data-stu-id="9a71c-125">Mapping to an attribute will result in the value being set as part of the configuration.</span></span>  
4. <span data-ttu-id="9a71c-126">W polu Grupa marszruty wpisz lub wprowadź wartość.</span><span class="sxs-lookup"><span data-stu-id="9a71c-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="9a71c-127">Grupa marszrut określa podstawowe zachowania dotyczące wyceny, zużycia i konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="9a71c-127">The route group determines essential behavior for costing, consumption, and setup.</span></span>  
5. <span data-ttu-id="9a71c-128">Kliknij kartę Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="9a71c-128">Click the Setup tab.</span></span>
6. <span data-ttu-id="9a71c-129">Kliknij kartę Czasy.</span><span class="sxs-lookup"><span data-stu-id="9a71c-129">Click the Times tab.</span></span>
7. <span data-ttu-id="9a71c-130">W polu Ilość z procesu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="9a71c-130">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="9a71c-131">Określ, ile będzie przetwarzanych w jednej operacji.</span><span class="sxs-lookup"><span data-stu-id="9a71c-131">Determine how many will be processed during one operation.</span></span>  
8. <span data-ttu-id="9a71c-132">W polu Godziny/czas wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="9a71c-132">In the Hours/time field, enter a number.</span></span>
    * <span data-ttu-id="9a71c-133">Wprowadź współczynnik czasu.</span><span class="sxs-lookup"><span data-stu-id="9a71c-133">Enter the time ratio.</span></span>  
9. <span data-ttu-id="9a71c-134">Zaznacz pole wyboru Ustaw.</span><span class="sxs-lookup"><span data-stu-id="9a71c-134">Select the Set check box.</span></span>
10. <span data-ttu-id="9a71c-135">W polu Czas procesu wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="9a71c-135">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="9a71c-136">Określ czas przetwarzania dla podanej ilości.</span><span class="sxs-lookup"><span data-stu-id="9a71c-136">Determine the processing time for the quantity that you have specified.</span></span>  
11. <span data-ttu-id="9a71c-137">Kliknij kartę Zapotrzebowanie na zasoby.</span><span class="sxs-lookup"><span data-stu-id="9a71c-137">Click the Resource requirements tab.</span></span>
12. <span data-ttu-id="9a71c-138">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="9a71c-138">Click Add.</span></span>
13. <span data-ttu-id="9a71c-139">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="9a71c-139">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="9a71c-140">W polu Typ wymagania wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="9a71c-140">In the Requirement type field, select an option.</span></span>
    * <span data-ttu-id="9a71c-141">Zdecyduj, czy chcesz określić konkretne zasoby czy możliwości, które muszą posiadać.</span><span class="sxs-lookup"><span data-stu-id="9a71c-141">Decide if you want to specify specific resources or capabilities that they must possess.</span></span>  
15. <span data-ttu-id="9a71c-142">W polu Zapotrzebowanie wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="9a71c-142">In the Requirement field, enter or select a value.</span></span>
16. <span data-ttu-id="9a71c-143">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9a71c-143">Click OK.</span></span>

