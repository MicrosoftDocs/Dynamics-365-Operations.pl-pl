---
title: Kody NMFC (National Motor Freight Classification)
description: W tym temacie opisano sposób pracy z kodami National Motor Freight Classification (NMFC) w systemie Microsoft Dynamics 365 Supply Chain Management
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0307437d3868f7ac34fa16a0913907a046ac14d4
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941889"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a><span data-ttu-id="d282d-103">Kody NMFC (National Motor Freight Classification)</span><span class="sxs-lookup"><span data-stu-id="d282d-103">National Motor Freight Classification (NMFC) codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d282d-104">Kody National Motor Freight Classification (NMFC) pomagają w klasyfikacji towarów, które mogą zostać wysłane.</span><span class="sxs-lookup"><span data-stu-id="d282d-104">National Motor Freight Classification (NMFC) codes help you classify items that can be shipped.</span></span> <span data-ttu-id="d282d-105">Kod NMFC jest oznaczeniem używanym do grupowania towarów.</span><span class="sxs-lookup"><span data-stu-id="d282d-105">The NMFC code is a designation that is used to group commodities.</span></span> <span data-ttu-id="d282d-106">Umożliwia on firmom transportowym ocenianie towarów do wysyłki przez klasyfikowanie towarów na podstawie czynników takich jak dopasowanie ciężarówki, łatwość przeładunku i trwałość.</span><span class="sxs-lookup"><span data-stu-id="d282d-106">It enables transport companies to evaluate goods for shipment by classifying items based on considerations such as truck fit, loading issues, handling issues, and perishability.</span></span> <span data-ttu-id="d282d-107">Towary są grupowane w 18 klasach frachtu przy użyciu zakresu numerów od 50 do 500.</span><span class="sxs-lookup"><span data-stu-id="d282d-107">Commodities are grouped into one of 18 freight classes by using a range of numbers from 50 to 500.</span></span> <span data-ttu-id="d282d-108">Klasa przypisana do towaru opiera się na analizie czterech charakterystyk transportowych: gęstości, wymiarów, łatwości przeładunku i odpowiedzialności.</span><span class="sxs-lookup"><span data-stu-id="d282d-108">The class that a commodity is grouped into is based on an evaluation of four transportation characteristics: density, stowability, handling, and liability.</span></span> <span data-ttu-id="d282d-109">Te cechy razem decydują o możliwości transportu towaru.</span><span class="sxs-lookup"><span data-stu-id="d282d-109">Together, these characteristics establish the commodity's transportability.</span></span>

<span data-ttu-id="d282d-110">Kod NMFC jest kojarzony z każdą pozycji wysyłki mniejszą niż ładunek ciężarówki (Less Than Truckload — LTL).</span><span class="sxs-lookup"><span data-stu-id="d282d-110">An NMFC code is associated with every less than truckload (LTL) shipping item.</span></span> <span data-ttu-id="d282d-111">Na przykład komputer przenośny może mieć przypisaną klasę NMFC o klasie 2.5, a przewody elektryczne mogą mieć klasy NMFC o klasie 65.</span><span class="sxs-lookup"><span data-stu-id="d282d-111">For example, a laptop might be assigned an NMFC that is classed at 2.5, whereas electrical cords might be assigned an NMFC that is classed at 65.</span></span>

<span data-ttu-id="d282d-112">Ta funkcja może ułatwić pracownikom używanie kodów NMFC do klasyfikowania pozycji wysyłki LTL.</span><span class="sxs-lookup"><span data-stu-id="d282d-112">This feature can help workers use NMFC codes to classify LTL shipping items.</span></span> <span data-ttu-id="d282d-113">Oto kilka przykładów:</span><span class="sxs-lookup"><span data-stu-id="d282d-113">Here are some examples:</span></span>

- <span data-ttu-id="d282d-114">Jeśli firma umieszcza opis frachtu w liście przewozowym, przewoźnik będzie mieć pojęcie, co transportuje.</span><span class="sxs-lookup"><span data-stu-id="d282d-114">If your company includes a freight description on the bill of lading (BOL), the carrier will have some idea what the freight is.</span></span> <span data-ttu-id="d282d-115">Fracht jest ważną klasyfikacją, ponieważ wiele firm transportowych opiera cały swój model biznesowy na typach frachtu, które przewożą.</span><span class="sxs-lookup"><span data-stu-id="d282d-115">Freight is an important classification because many transportation companies base their whole business model on the types of freight that they ship.</span></span>
- <span data-ttu-id="d282d-116">Ta klasyfikacja może być kluczowa dla firmy, ponieważ służy do określania kosztu danego ładunku.</span><span class="sxs-lookup"><span data-stu-id="d282d-116">This classification might be essential to your company because it's used to determine the cost of a given load.</span></span>
- <span data-ttu-id="d282d-117">Firma może identyfikować rentowność firmy zajmującej się logistyką i transportem LTL.</span><span class="sxs-lookup"><span data-stu-id="d282d-117">Your company can identify the profitability of an LTL logistics and transportation company.</span></span>

<span data-ttu-id="d282d-118">W tym temacie opisano, jak pracować z kodami NMFC w systemie Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d282d-118">This topic describes how to work with NMFC codes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d282d-119">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="d282d-119">Prerequisites</span></span>

<span data-ttu-id="d282d-120">Aby było można tworzyć kody NMFC, trzeba skonfigurować wszystkie klasy frachtu LTL, które muszą być mapowane na nie.</span><span class="sxs-lookup"><span data-stu-id="d282d-120">Before you can create NMFC codes, you must set up all the LTL freight classes that must be mapped to them.</span></span> <span data-ttu-id="d282d-121">Klasy frachtu LTL reprezentują kategorie towarów, podczas gdy kody NMFC są związane z określonymi towarami w każdej z 18 klas frachtu.</span><span class="sxs-lookup"><span data-stu-id="d282d-121">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span> <span data-ttu-id="d282d-122">Aby uzyskać więcej informacji na temat pracy z klasami LTL, zobacz [Klasy Less than truckload (LTL)](ltl-class.md).</span><span class="sxs-lookup"><span data-stu-id="d282d-122">For more information about how to work with LTL classes, see [Less than truckload (LTL) classes](ltl-class.md).</span></span>

## <a name="create-an-nmfc-code"></a><span data-ttu-id="d282d-123">Tworzenie kodu NMFC</span><span class="sxs-lookup"><span data-stu-id="d282d-123">Create an NMFC code</span></span>

<span data-ttu-id="d282d-124">Aby utworzyć kod NMFC, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="d282d-124">To create an NMFC code, follow these steps.</span></span>

1. <span data-ttu-id="d282d-125">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="d282d-125">Follow one of these steps:</span></span>

    - <span data-ttu-id="d282d-126">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Kody NMFC**.</span><span class="sxs-lookup"><span data-stu-id="d282d-126">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
    - <span data-ttu-id="d282d-127">Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Standardy transportu \> Kody NMFC**.</span><span class="sxs-lookup"><span data-stu-id="d282d-127">Go to **Transportation management \> Setup \> Transportation standards \> NMFC codes**.</span></span>

1. <span data-ttu-id="d282d-128">Wybierz pozycję **Nowy**, aby utworzyć kod NMFC.</span><span class="sxs-lookup"><span data-stu-id="d282d-128">Select **New** to create an NMFC code.</span></span> <span data-ttu-id="d282d-129">Następnie ustaw wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="d282d-129">Then set the following fields:</span></span>

    - <span data-ttu-id="d282d-130">**Kod NMFC** — wprowadź kod NMFC typu towaru.</span><span class="sxs-lookup"><span data-stu-id="d282d-130">**NMFC code** – Enter the NMFC code for the commodity type.</span></span>
    - <span data-ttu-id="d282d-131">**Nazwa** — wprowadź nazwę kodu NMFC.</span><span class="sxs-lookup"><span data-stu-id="d282d-131">**Name** – Enter a name for the NMFC code.</span></span>
    - <span data-ttu-id="d282d-132">**Klasa LTL** — umożliwia wybór klasy LTL skojarzonej z kodem NMFC.</span><span class="sxs-lookup"><span data-stu-id="d282d-132">**LTL class** – Select the LTL class that is associated with the NMFC code.</span></span>
    - <span data-ttu-id="d282d-133">**jednostka załadunkowa BOL** — umożliwia określenie domyślnego typu załadunku wysyłki.</span><span class="sxs-lookup"><span data-stu-id="d282d-133">**BOL handling unit** – Define the default handling type for the shipment.</span></span>

## <a name="example-set-up-nmfc-codes"></a><span data-ttu-id="d282d-134">Przykładowa konfiguracja kodów NMFC</span><span class="sxs-lookup"><span data-stu-id="d282d-134">Example: Set up NMFC codes</span></span>

<span data-ttu-id="d282d-135">W poniższym przykładzie pokazano, jak skonfigurować dwa różne kody NMFC, które mogą być używane z różnymi produktami.</span><span class="sxs-lookup"><span data-stu-id="d282d-135">The following example shows how to set up two different NMFC codes that can be used with different products.</span></span>

1. <span data-ttu-id="d282d-136">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Zapasy \> Kody NMFC**.</span><span class="sxs-lookup"><span data-stu-id="d282d-136">Go to **Warehouse management \> Setup \> Inventory \> NMFC codes**.</span></span>
1. <span data-ttu-id="d282d-137">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d282d-137">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d282d-138">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="d282d-138">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d282d-139">**Kod NMFC:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="d282d-139">**NMFC code:** *92.5*</span></span>
    - <span data-ttu-id="d282d-140">**Nazwa:** *komputery*</span><span class="sxs-lookup"><span data-stu-id="d282d-140">**Name:** *Computers*</span></span>
    - <span data-ttu-id="d282d-141">**Klasa LTL:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="d282d-141">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="d282d-142">**Jednostka załadunkowa BOL:** *jednostka*</span><span class="sxs-lookup"><span data-stu-id="d282d-142">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="d282d-143">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d282d-143">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="d282d-144">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d282d-144">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="d282d-145">W nowym wierszu ustaw następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="d282d-145">On the new line, set the following values:</span></span>

    - <span data-ttu-id="d282d-146">**Kod NMFC:** *125*</span><span class="sxs-lookup"><span data-stu-id="d282d-146">**NMFC code:** *125*</span></span>
    - <span data-ttu-id="d282d-147">**Nazwa:** *telefony*</span><span class="sxs-lookup"><span data-stu-id="d282d-147">**Name:** *Phones*</span></span>
    - <span data-ttu-id="d282d-148">**Klasa LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="d282d-148">**LTL class:** *125*</span></span>
    - <span data-ttu-id="d282d-149">**Jednostka załadunkowa BOL:** *jednostka*</span><span class="sxs-lookup"><span data-stu-id="d282d-149">**BOL handling unit:** *Unit*</span></span>

1. <span data-ttu-id="d282d-150">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d282d-150">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d282d-151">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="d282d-151">Additional resources</span></span>

- [<span data-ttu-id="d282d-152">Klasy ładunków częściowych (LTL)</span><span class="sxs-lookup"><span data-stu-id="d282d-152">Less than truckload (LTL) classes</span></span>](ltl-class.md)
- [<span data-ttu-id="d282d-153">Tworzenie listu przewozowego</span><span class="sxs-lookup"><span data-stu-id="d282d-153">Create a bill of landing</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
