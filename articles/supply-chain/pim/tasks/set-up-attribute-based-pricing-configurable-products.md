--- 
title: "Konfigurowanie wyceny konfigurowalnych produktów opartej na atrybutach"
description: "W tej procedurze pokazano sposób konfigurowania wyceny opartej na atrybutach."
author: YuyuScheller
manager: AnnBe
ms.date: 10/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: 88402bef6fd5dad38a74795cd31a4046085d6db7
ms.contentlocale: pl-pl
ms.lasthandoff: 09/14/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="40d50-103">Konfigurowanie wyceny konfigurowalnych produktów opartej na atrybutach</span><span class="sxs-lookup"><span data-stu-id="40d50-103">Set up attribute-based pricing for configurable products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="40d50-104">W tej procedurze pokazano sposób konfigurowania wyceny opartej na atrybutach.</span><span class="sxs-lookup"><span data-stu-id="40d50-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="40d50-105">Warunkiem wstępnym jest istnienie modelu konfiguracji produktu, który ma jeden lub więcej składników i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="40d50-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="40d50-106">W przykładzie użyto modelu produktu Głośnik o wysokiej jakości zawartego w danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="40d50-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="40d50-107">Zazwyczaj procedurę wykonuje menedżer produktu.</span><span class="sxs-lookup"><span data-stu-id="40d50-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="40d50-108">Tworzenie nowego modelu ceny</span><span class="sxs-lookup"><span data-stu-id="40d50-108">Create a new price model</span></span>
1. <span data-ttu-id="40d50-109">Kliknij opcję Definicja modelu wariantu produktu.</span><span class="sxs-lookup"><span data-stu-id="40d50-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="40d50-110">Kliknij opcję Modele konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="40d50-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="40d50-111">Na liście zaznacz wiersz Głośnik o wysokiej jakości, ale nie klikaj łącza z nazwą.</span><span class="sxs-lookup"><span data-stu-id="40d50-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="40d50-112">W okienku akcji kliknij pozycję Model.</span><span class="sxs-lookup"><span data-stu-id="40d50-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="40d50-113">Kliknij opcję Modele ceny.</span><span class="sxs-lookup"><span data-stu-id="40d50-113">Click Price models.</span></span>
6. <span data-ttu-id="40d50-114">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="40d50-114">Click New.</span></span>
7. <span data-ttu-id="40d50-115">W polu Nazwa modelu ceny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="40d50-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="40d50-116">Użyj nazwy, która sprawi, że model będzie łatwy do zidentyfikowania.</span><span class="sxs-lookup"><span data-stu-id="40d50-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="40d50-117">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="40d50-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="40d50-118">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="40d50-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="40d50-119">Dodawanie elementów ceny</span><span class="sxs-lookup"><span data-stu-id="40d50-119">Add price elements</span></span>
1. <span data-ttu-id="40d50-120">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="40d50-120">Click Edit.</span></span>
    * <span data-ttu-id="40d50-121">Każdy składnik w modelu produktu może mieć element ceny podstawowej i dowolną liczbę reguł wyrażenia ceny.</span><span class="sxs-lookup"><span data-stu-id="40d50-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="40d50-122">Można również dodawać ceny w różnych walutach.</span><span class="sxs-lookup"><span data-stu-id="40d50-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="40d50-123">W polu Wyrażenie podstawy ceny wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="40d50-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="40d50-124">Na przykład wpisz 100.</span><span class="sxs-lookup"><span data-stu-id="40d50-124">For example, type 100.</span></span>   <span data-ttu-id="40d50-125">Wyrażenie ceny podstawowej może być wartością liczbową lub mieć formę obliczenia arytmetycznego, w którym występuje jeden lub więcej atrybutów.</span><span class="sxs-lookup"><span data-stu-id="40d50-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="40d50-126">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="40d50-126">Click Add.</span></span>
4. <span data-ttu-id="40d50-127">W polu Nazwa wpisz „Rosewood”.</span><span class="sxs-lookup"><span data-stu-id="40d50-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="40d50-128">Nazwa wyrażenia ceny pomaga stwierdzić, co reprezentuje element ceny.</span><span class="sxs-lookup"><span data-stu-id="40d50-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="40d50-129">W tym przykładzie tworzymy element ceny dla opcji wykończenie głośnika palisandrem.</span><span class="sxs-lookup"><span data-stu-id="40d50-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="40d50-130">Kliknij opcję Edytuj warunek.</span><span class="sxs-lookup"><span data-stu-id="40d50-130">Click Edit condition.</span></span>
    * <span data-ttu-id="40d50-131">Warunek cenowy pomaga zagwarantować, że element wyrażenia ceny jest uwzględniany w cenie sprzedaży tylko wtedy, gdy występuje określona kombinacja atrybutów.</span><span class="sxs-lookup"><span data-stu-id="40d50-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="40d50-132">W polu ConstraintBody wpisz „CabinetFinish=="Rosewood"”.</span><span class="sxs-lookup"><span data-stu-id="40d50-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="40d50-133">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="40d50-133">Click OK.</span></span>
8. <span data-ttu-id="40d50-134">W polu Wyrażenie wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="40d50-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="40d50-135">Na przykład wpisz 50.</span><span class="sxs-lookup"><span data-stu-id="40d50-135">For example, type 50.</span></span>  
9. <span data-ttu-id="40d50-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="40d50-136">Close the page.</span></span>
10. <span data-ttu-id="40d50-137">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="40d50-137">Close the page.</span></span>


