---
title: Klasy ładunków częściowych (LTL)
description: W tym temacie objaśniono, czym są klasy ładunków częściowych (LTL) i jak je skonfigurować w systemie Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941817"
---
# <a name="less-than-truckload-ltl-classes"></a><span data-ttu-id="0d1e6-103">Klasy ładunków częściowych (LTL)</span><span class="sxs-lookup"><span data-stu-id="0d1e6-103">Less than truckload (LTL) classes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d1e6-104">Klasa ładunków częściowych (LTL) jest klasą wysyłki frachtu używaną do klasyfikacji towarów, które mogą zostać wysłane.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-104">A less than truckload (LTL) class is a freight shipping class that is used to classify items that can be shipped.</span></span> <span data-ttu-id="0d1e6-105">Każdy typ produktu lub asortymentu powinien mieć kod National Motor Freight Classification (NMFC) odpowiadający określonemu numerowi klasy frachtu dla wysyłek LTL.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-105">Generally, every type of product or commodity has a National Motor Freight Classification (NMFC) code that corresponds to a specific freight class number for LTL shipments.</span></span> <span data-ttu-id="0d1e6-106">Klasy frachtu LTL reprezentują kategorie towarów, podczas gdy kody NMFC są związane z określonymi towarami w każdej z 18 klas frachtu.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-106">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span>

<span data-ttu-id="0d1e6-107">Ta funkcja pozwala wykonać następujące zadania w systemie:</span><span class="sxs-lookup"><span data-stu-id="0d1e6-107">This feature lets you use your system to perform the following tasks:</span></span>

- <span data-ttu-id="0d1e6-108">Definiowanie klas frachtu LTL używanych w firmie.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-108">Define the LTL freight classes that are used at your company.</span></span>
- <span data-ttu-id="0d1e6-109">Przypisywanie klas LTL do kodu NMFC na stronie **Kody NMFC**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-109">Assign each LTL class to an NMFC code on the **NMFC Codes** page.</span></span> <span data-ttu-id="0d1e6-110">Aby uzyskać więcej informacji, zobacz temat [Kody National Motor Freight Classification (NMFC)](nmfc-codes.md).</span><span class="sxs-lookup"><span data-stu-id="0d1e6-110">For more information, see [National Motor Freight Classification (NMFC) codes](nmfc-codes.md).</span></span>
- <span data-ttu-id="0d1e6-111">Przypisywanie kodu NMFC (razem ze skojarzonym z nim kodem LTL) do produktów na stronie **Produkty**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-111">Assign an NMFC code (and therefore its associated LTL code) to each product on the **Products** page.</span></span>
- <span data-ttu-id="0d1e6-112">Precyzyjne ocenianie klasy LTL produktu, do którego jest przypisany kod NMFC.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-112">Accurately assess the LTL class of each product that an NMFC code is assigned to.</span></span>
- <span data-ttu-id="0d1e6-113">Określanie wymagań dotyczących pakowania klas LTL na podstawie międzynarodowych standardów LTL.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-113">Determine packing requirements for each LTL class by checking the international LTL standards.</span></span> <span data-ttu-id="0d1e6-114">W ten sposób zapewniasz, że twoje produkty będą dobrze chronione i na pewno zostaną wysłane.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-114">In this way, you ensure that your products will be well protected and safely shipped.</span></span>
- <span data-ttu-id="0d1e6-115">Dokładne szacowane kosztów wysyłki oparte na klasie frachtu LTL produktu.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-115">Get accurate shipping estimates, based on the LTL freight class for each product.</span></span>

<span data-ttu-id="0d1e6-116">W tym temacie opisano, jak tworzyć klasy LTL w systemie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-116">This topic describes how to create LTL classes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="create-an-ltl-class"></a><span data-ttu-id="0d1e6-117">Tworzenie klasy LTL</span><span class="sxs-lookup"><span data-stu-id="0d1e6-117">Create an LTL class</span></span>

<span data-ttu-id="0d1e6-118">Aby utworzyć klasę LTL, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-118">To create an LTL class, follow these steps.</span></span>

1. <span data-ttu-id="0d1e6-119">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="0d1e6-119">Follow one of these steps:</span></span>

    - <span data-ttu-id="0d1e6-120">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Klasy LTL**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-120">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
    - <span data-ttu-id="0d1e6-121">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Standardy transportu \> Klasy LTL**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-121">Go to **Transportation management \> Setup \> Transportation standards \> LTL classes**.</span></span>

2. <span data-ttu-id="0d1e6-122">W okienku akcji wybierz opcję **Nowe**, aby utworzyć klasę LTL.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-122">On the Action Pane, select **New** to create an LTL class.</span></span> <span data-ttu-id="0d1e6-123">Następnie ustaw wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="0d1e6-123">Then set the following fields:</span></span>

    - <span data-ttu-id="0d1e6-124">**Klasa LTL** — służy do wprowadzania identyfikatora klasy LTL typu towaru.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-124">**LTL class** – Enter your company's internal LTL class identifier (ID) for the commodity type.</span></span> <span data-ttu-id="0d1e6-125">Większość firm korzysta ze standardu międzynarodowego.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-125">Most companies use the international standard.</span></span> <span data-ttu-id="0d1e6-126">W takim przypadku wartość w tym polu będzie odpowiadać wartości w polu **Klasa**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-126">In that case, the value of this field will match the value of the **Class** field.</span></span> <span data-ttu-id="0d1e6-127">Jeśli jednak firma używa własnego standardu, należy wprowadzić kod zgodny z tym standardem.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-127">However, if your company uses its own standard, enter a code that conforms to that standard.</span></span>
    - <span data-ttu-id="0d1e6-128">**Nazwa** — umożliwia wprowadzenie opisowej nazwy, która pomoże użytkownikom wybierać poprawną klasę LTL dla kodu NMFC.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-128">**Name** – Enter a descriptive name that will help you and other users select the correct LTL class for each NMFC code.</span></span>
    - <span data-ttu-id="0d1e6-129">**Klasa** — umożliwia wprowadzenie identyfikatora klasy LTL typu towaru zgodnej z międzynarodowym standardem.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-129">**Class** – Enter the international standard LTL class ID for the commodity type.</span></span> <span data-ttu-id="0d1e6-130">Wprowadzany tutaj kod musi być zgodny z oficjalnym standardem.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-130">The code that you enter here must conform to the official standard.</span></span>

## <a name="example-set-up-ltl-classes"></a><span data-ttu-id="0d1e6-131">Przykładowa konfiguracja klas LTL</span><span class="sxs-lookup"><span data-stu-id="0d1e6-131">Example: Set up LTL classes</span></span>

<span data-ttu-id="0d1e6-132">W poniższym przykładzie pokazano, jak skonfigurować dwie różne klasy LTL, które mogą być używane z różnymi typami produktów.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-132">The following example shows how to set up two different LTL classes that you can use with different types of products.</span></span>

1. <span data-ttu-id="0d1e6-133">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Klasy LTL**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-133">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
1. <span data-ttu-id="0d1e6-134">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-134">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0d1e6-135">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="0d1e6-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0d1e6-136">**Klasa LTL:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="0d1e6-136">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="0d1e6-137">**Nazwa:** *komputery, monitory, lodówki*</span><span class="sxs-lookup"><span data-stu-id="0d1e6-137">**Name:** *Computers, monitors, refrigerators*</span></span>
    - <span data-ttu-id="0d1e6-138">**Klasa:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="0d1e6-138">**Class:** *92.5*</span></span>

1. <span data-ttu-id="0d1e6-139">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-139">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="0d1e6-140">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-140">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0d1e6-141">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="0d1e6-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0d1e6-142">**Klasa LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="0d1e6-142">**LTL class:** *125*</span></span>
    - <span data-ttu-id="0d1e6-143">**Nazwa:** *małe artykuły gospodarstwa domowego*</span><span class="sxs-lookup"><span data-stu-id="0d1e6-143">**Name:** *Small household appliances*</span></span>
    - <span data-ttu-id="0d1e6-144">**Klasa:** *125*</span><span class="sxs-lookup"><span data-stu-id="0d1e6-144">**Class:** *125*</span></span>

1. <span data-ttu-id="0d1e6-145">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="0d1e6-145">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d1e6-146">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0d1e6-146">Additional resources</span></span>

- [<span data-ttu-id="0d1e6-147">Kody NMFC (National Motor Freight Classification)</span><span class="sxs-lookup"><span data-stu-id="0d1e6-147">National Motor Freight Classification (NMFC) codes</span></span>](nmfc-codes.md)
- [<span data-ttu-id="0d1e6-148">Tworzenie listu przewozowego</span><span class="sxs-lookup"><span data-stu-id="0d1e6-148">Create a bill of lading</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
