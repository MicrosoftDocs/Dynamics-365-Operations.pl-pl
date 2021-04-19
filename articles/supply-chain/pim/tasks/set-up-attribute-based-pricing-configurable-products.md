---
title: Konfigurowanie opartej na atrybutach wyceny konfigurowalnych produktów
description: W tym temacie pokazano sposób konfigurowania wyceny opartej na atrybutach.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f54d0ea87d8ce5ffdf5600995004e558ddd86fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833264"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="11fb4-103">Konfigurowanie opartej na atrybutach wyceny konfigurowalnych produktów</span><span class="sxs-lookup"><span data-stu-id="11fb4-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="11fb4-104">W tym temacie pokazano sposób konfigurowania wyceny opartej na atrybutach.</span><span class="sxs-lookup"><span data-stu-id="11fb4-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="11fb4-105">Warunkiem wstępnym jest istnienie modelu konfiguracji produktu, który ma jeden lub więcej składników i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="11fb4-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="11fb4-106">W przykładzie użyto modelu produktu Głośnik o wysokiej jakości zawartego w danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="11fb4-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="11fb4-107">Zazwyczaj procedurę wykonuje menedżer produktu.</span><span class="sxs-lookup"><span data-stu-id="11fb4-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="11fb4-108">Tworzenie nowego modelu ceny</span><span class="sxs-lookup"><span data-stu-id="11fb4-108">Create a new price model</span></span>
1. <span data-ttu-id="11fb4-109">Wybierz **Definicja modelu wariantu produktu** na stronie głównej.</span><span class="sxs-lookup"><span data-stu-id="11fb4-109">Select **Product variant model definition** on the home page.</span></span>
2. <span data-ttu-id="11fb4-110">Wybierz **Modele konfiguracji produktu** w sekcji **łącza**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-110">Select **Product configuration models** in the **links** section.</span></span>
3. <span data-ttu-id="11fb4-111">Na liście zaznacz wiersz **Głośnik o wysokiej jakości**, ale nie wybieraj łącza z nazwą.</span><span class="sxs-lookup"><span data-stu-id="11fb4-111">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
4. <span data-ttu-id="11fb4-112">W okienku akcji kliknij pozycję **Model**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-112">On the Action Pane, select **Model**.</span></span>
5. <span data-ttu-id="11fb4-113">Wybierz **Modele ceny**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-113">Select **Price models**.</span></span>
6. <span data-ttu-id="11fb4-114">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-114">Select **New**.</span></span>
7. <span data-ttu-id="11fb4-115">W polu **Nazwa modelu ceny** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="11fb4-115">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="11fb4-116">Użyj nazwy, która sprawi, że model będzie łatwy do zidentyfikowania.</span><span class="sxs-lookup"><span data-stu-id="11fb4-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="11fb4-117">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="11fb4-117">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="11fb4-118">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-118">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="11fb4-119">Dodawanie elementów ceny</span><span class="sxs-lookup"><span data-stu-id="11fb4-119">Add price elements</span></span>
1. <span data-ttu-id="11fb4-120">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-120">Select **Edit**.</span></span> <span data-ttu-id="11fb4-121">Każdy składnik w modelu produktu może mieć element ceny podstawowej i dowolną liczbę reguł wyrażenia ceny.</span><span class="sxs-lookup"><span data-stu-id="11fb4-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="11fb4-122">Można również dodawać ceny w różnych walutach.</span><span class="sxs-lookup"><span data-stu-id="11fb4-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="11fb4-123">W polu **Wyrażenie podstawy ceny** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="11fb4-123">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="11fb4-124">Na przykład wpisz 100.</span><span class="sxs-lookup"><span data-stu-id="11fb4-124">For example, type 100.</span></span> <span data-ttu-id="11fb4-125">Wyrażenie ceny podstawowej może być wartością liczbową lub mieć formę obliczenia arytmetycznego, w którym występuje jeden lub więcej atrybutów.</span><span class="sxs-lookup"><span data-stu-id="11fb4-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="11fb4-126">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-126">Select **Add**.</span></span>
4. <span data-ttu-id="11fb4-127">W polu **Nazwa** wpisz `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="11fb4-127">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="11fb4-128">Nazwa wyrażenia ceny pomaga stwierdzić, co reprezentuje element ceny.</span><span class="sxs-lookup"><span data-stu-id="11fb4-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="11fb4-129">W tym przykładzie tworzymy element ceny dla opcji wykończenie głośnika palisandrem.</span><span class="sxs-lookup"><span data-stu-id="11fb4-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="11fb4-130">Wybierz **Edytuj warunek**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-130">Select **Edit condition**.</span></span> <span data-ttu-id="11fb4-131">Warunek cenowy pomaga zagwarantować, że element wyrażenia ceny jest uwzględniany w cenie sprzedaży tylko wtedy, gdy występuje określona kombinacja atrybutów.</span><span class="sxs-lookup"><span data-stu-id="11fb4-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="11fb4-132">W polu **ConstraintBody** wpisz `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="11fb4-132">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="11fb4-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="11fb4-133">Select **OK**.</span></span>
8. <span data-ttu-id="11fb4-134">W polu **Wyrażenie** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="11fb4-134">In the **Expression** field, type a value.</span></span> <span data-ttu-id="11fb4-135">Na przykład wpisz `50`.</span><span class="sxs-lookup"><span data-stu-id="11fb4-135">For example, type `50`.</span></span> 
9. <span data-ttu-id="11fb4-136">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="11fb4-136">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]