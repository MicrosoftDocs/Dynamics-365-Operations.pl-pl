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
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921248"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="bc119-103">Konfigurowanie opartej na atrybutach wyceny konfigurowalnych produktów</span><span class="sxs-lookup"><span data-stu-id="bc119-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bc119-104">W tym temacie pokazano sposób konfigurowania wyceny opartej na atrybutach.</span><span class="sxs-lookup"><span data-stu-id="bc119-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="bc119-105">Warunkiem wstępnym jest istnienie modelu konfiguracji produktu, który ma jeden lub więcej składników i atrybutów.</span><span class="sxs-lookup"><span data-stu-id="bc119-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="bc119-106">W przykładzie użyto modelu produktu Głośnik o wysokiej jakości zawartego w danych firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="bc119-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="bc119-107">Zazwyczaj procedurę wykonuje menedżer produktu.</span><span class="sxs-lookup"><span data-stu-id="bc119-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="bc119-108">Tworzenie nowego modelu ceny</span><span class="sxs-lookup"><span data-stu-id="bc119-108">Create a new price model</span></span>

1. <span data-ttu-id="bc119-109">Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.</span><span class="sxs-lookup"><span data-stu-id="bc119-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="bc119-110">Na liście zaznacz wiersz **Głośnik o wysokiej jakości**, ale nie wybieraj łącza z nazwą.</span><span class="sxs-lookup"><span data-stu-id="bc119-110">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
1. <span data-ttu-id="bc119-111">W okienku akcji kliknij pozycję **Model**.</span><span class="sxs-lookup"><span data-stu-id="bc119-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="bc119-112">Wybierz **Modele ceny**.</span><span class="sxs-lookup"><span data-stu-id="bc119-112">Select **Price models**.</span></span>
1. <span data-ttu-id="bc119-113">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bc119-113">Select **New**.</span></span>
1. <span data-ttu-id="bc119-114">W polu **Nazwa modelu ceny** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc119-114">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="bc119-115">Użyj nazwy, która sprawi, że model będzie łatwy do zidentyfikowania.</span><span class="sxs-lookup"><span data-stu-id="bc119-115">Use a name that makes the model easy to identify.</span></span>  
1. <span data-ttu-id="bc119-116">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc119-116">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="bc119-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bc119-117">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="bc119-118">Dodawanie elementów ceny</span><span class="sxs-lookup"><span data-stu-id="bc119-118">Add price elements</span></span>

1. <span data-ttu-id="bc119-119">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="bc119-119">Select **Edit**.</span></span> <span data-ttu-id="bc119-120">Każdy składnik w modelu produktu może mieć element ceny podstawowej i dowolną liczbę reguł wyrażenia ceny.</span><span class="sxs-lookup"><span data-stu-id="bc119-120">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="bc119-121">Można również dodawać ceny w różnych walutach.</span><span class="sxs-lookup"><span data-stu-id="bc119-121">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="bc119-122">W polu **Wyrażenie podstawy ceny** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc119-122">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="bc119-123">Na przykład wpisz 100.</span><span class="sxs-lookup"><span data-stu-id="bc119-123">For example, type 100.</span></span> <span data-ttu-id="bc119-124">Wyrażenie ceny podstawowej może być wartością liczbową lub mieć formę obliczenia arytmetycznego, w którym występuje jeden lub więcej atrybutów.</span><span class="sxs-lookup"><span data-stu-id="bc119-124">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="bc119-125">Wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="bc119-125">Select **Add**.</span></span>
4. <span data-ttu-id="bc119-126">W polu **Nazwa** wpisz `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="bc119-126">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="bc119-127">Nazwa wyrażenia ceny pomaga stwierdzić, co reprezentuje element ceny.</span><span class="sxs-lookup"><span data-stu-id="bc119-127">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="bc119-128">W tym przykładzie tworzymy element ceny dla opcji wykończenie głośnika palisandrem.</span><span class="sxs-lookup"><span data-stu-id="bc119-128">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="bc119-129">Wybierz **Edytuj warunek**.</span><span class="sxs-lookup"><span data-stu-id="bc119-129">Select **Edit condition**.</span></span> <span data-ttu-id="bc119-130">Warunek cenowy pomaga zagwarantować, że element wyrażenia ceny jest uwzględniany w cenie sprzedaży tylko wtedy, gdy występuje określona kombinacja atrybutów.</span><span class="sxs-lookup"><span data-stu-id="bc119-130">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="bc119-131">W polu **ConstraintBody** wpisz `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="bc119-131">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="bc119-132">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc119-132">Select **OK**.</span></span>
8. <span data-ttu-id="bc119-133">W polu **Wyrażenie** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="bc119-133">In the **Expression** field, type a value.</span></span> <span data-ttu-id="bc119-134">Na przykład wpisz `50`.</span><span class="sxs-lookup"><span data-stu-id="bc119-134">For example, type `50`.</span></span> 
9. <span data-ttu-id="bc119-135">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="bc119-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]