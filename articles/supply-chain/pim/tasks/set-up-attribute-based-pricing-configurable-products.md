---
title: Konfigurowanie wyceny konfigurowalnych produktów opartej na atrybutach
description: W tej procedurze pokazano sposób konfigurowania wyceny opartej na atrybutach.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba84fa4de660d16b266763fff5b0b794ed327c81
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844208"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="1beb5-103">Konfigurowanie wyceny konfigurowalnych produktów opartej na atrybutach</span><span class="sxs-lookup"><span data-stu-id="1beb5-103">Set up attribute-based pricing for configurable products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1beb5-104">W tej procedurze pokazano sposób konfigurowania wyceny opartej na atrybutach.</span><span class="sxs-lookup"><span data-stu-id="1beb5-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="1beb5-105">Warunkiem wstępnym jest istnienie modelu konfiguracji produktu, który ma jeden lub więcej składników i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="1beb5-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="1beb5-106">W przykładzie użyto modelu produktu Głośnik o wysokiej jakości zawartego w danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="1beb5-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="1beb5-107">Zazwyczaj procedurę wykonuje menedżer produktu.</span><span class="sxs-lookup"><span data-stu-id="1beb5-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="1beb5-108">Tworzenie nowego modelu ceny</span><span class="sxs-lookup"><span data-stu-id="1beb5-108">Create a new price model</span></span>
1. <span data-ttu-id="1beb5-109">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="1beb5-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="1beb5-110">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="1beb5-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="1beb5-111">Na liście zaznacz wiersz Głośnik o wysokiej jakości, ale nie klikaj łącza z nazwą.</span><span class="sxs-lookup"><span data-stu-id="1beb5-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="1beb5-112">W okienku akcji kliknij pozycję Model.</span><span class="sxs-lookup"><span data-stu-id="1beb5-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="1beb5-113">Kliknij opcję Modele ceny.</span><span class="sxs-lookup"><span data-stu-id="1beb5-113">Click Price models.</span></span>
6. <span data-ttu-id="1beb5-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="1beb5-114">Click New.</span></span>
7. <span data-ttu-id="1beb5-115">W polu Nazwa modelu ceny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1beb5-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="1beb5-116">Użyj nazwy, która sprawi, że model będzie łatwy do zidentyfikowania.</span><span class="sxs-lookup"><span data-stu-id="1beb5-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="1beb5-117">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="1beb5-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="1beb5-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="1beb5-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="1beb5-119">Dodawanie elementów ceny</span><span class="sxs-lookup"><span data-stu-id="1beb5-119">Add price elements</span></span>
1. <span data-ttu-id="1beb5-120">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="1beb5-120">Click Edit.</span></span>
    * <span data-ttu-id="1beb5-121">Każdy składnik w modelu produktu może mieć element ceny podstawowej i dowolną liczbę reguł wyrażenia ceny.</span><span class="sxs-lookup"><span data-stu-id="1beb5-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="1beb5-122">Można również dodawać ceny w różnych walutach.</span><span class="sxs-lookup"><span data-stu-id="1beb5-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="1beb5-123">W polu Wyrażenie podstawy ceny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1beb5-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="1beb5-124">Na przykład wpisz 100.</span><span class="sxs-lookup"><span data-stu-id="1beb5-124">For example, type 100.</span></span>   <span data-ttu-id="1beb5-125">Wyrażenie ceny podstawowej może być wartością liczbową lub mieć formę obliczenia arytmetycznego, w którym występuje jeden lub więcej atrybutów.</span><span class="sxs-lookup"><span data-stu-id="1beb5-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="1beb5-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="1beb5-126">Click Add.</span></span>
4. <span data-ttu-id="1beb5-127">W polu Nazwa wpisz „Rosewood”.</span><span class="sxs-lookup"><span data-stu-id="1beb5-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="1beb5-128">Nazwa wyrażenia ceny pomaga stwierdzić, co reprezentuje element ceny.</span><span class="sxs-lookup"><span data-stu-id="1beb5-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="1beb5-129">W tym przykładzie tworzymy element ceny dla opcji wykończenie głośnika palisandrem.</span><span class="sxs-lookup"><span data-stu-id="1beb5-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="1beb5-130">Kliknij opcję Edytuj warunek.</span><span class="sxs-lookup"><span data-stu-id="1beb5-130">Click Edit condition.</span></span>
    * <span data-ttu-id="1beb5-131">Warunek cenowy pomaga zagwarantować, że element wyrażenia ceny jest uwzględniany w cenie sprzedaży tylko wtedy, gdy występuje określona kombinacja atrybutów.</span><span class="sxs-lookup"><span data-stu-id="1beb5-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="1beb5-132">W polu ConstraintBody wpisz „CabinetFinish=="Rosewood"”.</span><span class="sxs-lookup"><span data-stu-id="1beb5-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="1beb5-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1beb5-133">Click OK.</span></span>
8. <span data-ttu-id="1beb5-134">W polu Wyrażenie wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1beb5-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="1beb5-135">Na przykład wpisz 50.</span><span class="sxs-lookup"><span data-stu-id="1beb5-135">For example, type 50.</span></span>  
9. <span data-ttu-id="1beb5-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1beb5-136">Close the page.</span></span>
10. <span data-ttu-id="1beb5-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1beb5-137">Close the page.</span></span>

