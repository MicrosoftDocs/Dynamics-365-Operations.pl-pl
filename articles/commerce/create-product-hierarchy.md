---
title: Utwórz nową hierarchię produktu
description: W tym temacie opisano, jak dodać utworzyć nową hierarchię produktu w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 724ec2e5af7837d574298d662911cd9c6ee9e9f2
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070428"
---
# <a name="create-a-new-product-hierarchy"></a><span data-ttu-id="e074c-103">Utwórz nową hierarchię produktu</span><span class="sxs-lookup"><span data-stu-id="e074c-103">Create a new product hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e074c-104">W tym temacie opisano, jak dodać utworzyć nową hierarchię produktu w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e074c-104">This topic describes how to create a new product hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e074c-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="e074c-105">Overview</span></span>

<span data-ttu-id="e074c-106">Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="e074c-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="e074c-107">Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi).</span><span class="sxs-lookup"><span data-stu-id="e074c-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="e074c-108">Każdy kanał sklepu detalicznego ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel.</span><span class="sxs-lookup"><span data-stu-id="e074c-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="e074c-109">Wszystkie te elementy kanału sklepu detalicznego należy skonfigurować przed jego utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="e074c-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="e074c-110">Hierarchia produktów Commerce pozwala zdefiniować ogólną hierarchę produktów dla Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="e074c-110">A Commerce product hierarchy is used to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="e074c-111">Hierarchia produktu Commerce sprawdza się w merchandisingu, wycenach i promocjach, raportowaniu i planowaniu asortymentu.</span><span class="sxs-lookup"><span data-stu-id="e074c-111">You can use a Commerce product hierarchy for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="e074c-112">Dla każdej organizacji można przypisać tylko jedną hierarchię produktów Commerce.</span><span class="sxs-lookup"><span data-stu-id="e074c-112">Only one Commerce product hierarchy can be assigned per organization.</span></span>

## <a name="create-and-configure-a-product-hierarchy"></a><span data-ttu-id="e074c-113">Tworzenie i konfiguracja hierarchii klasyfikacji produktów</span><span class="sxs-lookup"><span data-stu-id="e074c-113">Create and configure a product hierarchy</span></span>

<span data-ttu-id="e074c-114">Aby utworzyć i skonfigurować hierarchię produktów w Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e074c-114">To create and configure a Commerce product hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="e074c-115">W okienku nawigacji przejdź do **Moduły \> Retail i Commerce \> Produkty i kategorie \> Hierarchia produktu w Commerce**.</span><span class="sxs-lookup"><span data-stu-id="e074c-115">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
1. <span data-ttu-id="e074c-116">Jeśli jeszcze nie hierachy, w **okienku akcji** wybierz opcję **nowy**, aby utworzyć katalog główny hierarchii.</span><span class="sxs-lookup"><span data-stu-id="e074c-116">If no hierachy exists yet, on the **Action pane**, select **New** to create the root of the hierarchy.</span></span>
1. <span data-ttu-id="e074c-117">W **Ogólne**:</span><span class="sxs-lookup"><span data-stu-id="e074c-117">Under **General**:</span></span>
    1. <span data-ttu-id="e074c-118">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="e074c-118">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="e074c-119">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="e074c-119">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="e074c-120">W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="e074c-120">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="e074c-121">Ustaw wartość **Aktywni** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e074c-121">Set **Active** to **Yes**.</span></span>

## <a name="add-hierarchy-nodes"></a><span data-ttu-id="e074c-122">Dodaj węzły hierarchii</span><span class="sxs-lookup"><span data-stu-id="e074c-122">Add hierarchy nodes</span></span>

<span data-ttu-id="e074c-123">Aby dodać węzły hierarchii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="e074c-123">To add hierarchy nodes, follow these steps.</span></span>

1. <span data-ttu-id="e074c-124">W okienku akcji kliknij pozycję **Edytuj hierarchię kategorii**.</span><span class="sxs-lookup"><span data-stu-id="e074c-124">On the action pane, select **Edit category hierarchy**.</span></span>
1. <span data-ttu-id="e074c-125">Wybierz węzeł nadrzędny, do którego chcesz dodać nowy węzeł, a następnie wybierz **Nowa węzeł kategorii**.</span><span class="sxs-lookup"><span data-stu-id="e074c-125">Select the parent node you want to add a new node to, and then select **New category node**.</span></span>
1. <span data-ttu-id="e074c-126">W sekcji **Ogólne** należy podać **Nazwę**, **Opis**, **Wyświetlaną nazwę** i **Słowa kluczowe**.</span><span class="sxs-lookup"><span data-stu-id="e074c-126">In the **General** section provide a **Name**, **Description**, **Friendly name** and **Keywords**.</span></span>
1. <span data-ttu-id="e074c-127">W **Ogólne**:</span><span class="sxs-lookup"><span data-stu-id="e074c-127">Under **General**:</span></span>
    1. <span data-ttu-id="e074c-128">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="e074c-128">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="e074c-129">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="e074c-129">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="e074c-130">W polu **Nazwa wyświetlana** wprowadź wyświetlaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="e074c-130">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="e074c-131">W polu **Słowa kluczowe** wprowadź odpowiednie słowa kluczowe.</span><span class="sxs-lookup"><span data-stu-id="e074c-131">In the **Keywords** box, enter relevant keywords.</span></span>
    1. <span data-ttu-id="e074c-132">W polu **Kolejność wyświetlania** wprowadź numer kolejności wyświetlania (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="e074c-132">In the **Display order**box, enter a number for the display order (optional).</span></span>
1. <span data-ttu-id="e074c-133">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e074c-133">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="e074c-134">Powtórz powyższe kroki, aby dodać kolejne węzły.</span><span class="sxs-lookup"><span data-stu-id="e074c-134">Repeat the steps above to add additional nodes.</span></span>

<span data-ttu-id="e074c-135">Poniższy rysunek przedstawia utworzenie nowego węzła hierarchii produktu.</span><span class="sxs-lookup"><span data-stu-id="e074c-135">The following image shows the creation of a new product hierarchy node.</span></span>

![Utwórz hierarchię produktu](media/create-product-hierarchy.png)

## <a name="other-settings"></a><span data-ttu-id="e074c-137">Inne ustawienia</span><span class="sxs-lookup"><span data-stu-id="e074c-137">Other settings</span></span>

<span data-ttu-id="e074c-138">Grupy atrybutów kategorii można również przypisać do każdej grupy w zależności od potrzeb.</span><span class="sxs-lookup"><span data-stu-id="e074c-138">Category attribute groups can also be assigned to each group as required.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="e074c-139">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e074c-139">Additional resources</span></span>

[<span data-ttu-id="e074c-140">Hierarchie handlu</span><span class="sxs-lookup"><span data-stu-id="e074c-140">commerce hierarchies</span></span>](retail-hierarchies.md)

[<span data-ttu-id="e074c-141">Zarządzanie kategoriami produktów i produktami </span><span class="sxs-lookup"><span data-stu-id="e074c-141">Manage product categories and products </span></span>](category-management-product-creation.md)

[<span data-ttu-id="e074c-142">Zmiana porządku sortowania dla podmiotów merchandisingowych</span><span class="sxs-lookup"><span data-stu-id="e074c-142">Change the sort order for merchandizing entities</span></span>](custom-order-categories-nav-retail-prod-hierarchy.md)
