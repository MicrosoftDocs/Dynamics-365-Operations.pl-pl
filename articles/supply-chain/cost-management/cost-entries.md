---
title: Wpisy kosztów
description: Ten artykuł zawiera informacje o wpisach kosztów i sytuacjach, kiedy są tworzone. Wpis kosztu to rekord, w którym są rejestrowane ilość i koszt danego zdarzenia.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ddd263852fc328756a6dc06bc3f02c661cbd40f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228642"
---
# <a name="cost-entries"></a><span data-ttu-id="f20d3-104">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="f20d3-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f20d3-105">Ten artykuł zawiera informacje o wpisach kosztów i sytuacjach, kiedy są tworzone.</span><span class="sxs-lookup"><span data-stu-id="f20d3-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="f20d3-106">Wpis kosztu to rekord, w którym są rejestrowane ilość i koszt danego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="f20d3-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="f20d3-107">Wpisy kosztów są agregacjami dla transakcji magazynowych, które są rejestrowane w aktywnych wymiarach magazynu finansowego.</span><span class="sxs-lookup"><span data-stu-id="f20d3-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="f20d3-108">Przykłady</span><span class="sxs-lookup"><span data-stu-id="f20d3-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="f20d3-109">Przykład 1: Nie są tworzone żadne wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="f20d3-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="f20d3-110">Rejestrowane jest zdarzenie arkusza przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="f20d3-110">A transfer journal event is registered.</span></span> <span data-ttu-id="f20d3-111">Zdarzenie przenosi jedną sztukę towaru A z lokalizacji A do lokalizacji B. Wymiar magazynowy Lokalizacja nie jest traktowany jako część obiektu kosztu.</span><span class="sxs-lookup"><span data-stu-id="f20d3-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="f20d3-112">Z tego względu zdarzenie tworzy dwie transakcje magazynowe i żadnych wpisów kosztów.</span><span class="sxs-lookup"><span data-stu-id="f20d3-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="f20d3-113">Przykład 2: Wpisy kosztów są tworzone</span><span class="sxs-lookup"><span data-stu-id="f20d3-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="f20d3-114">Rejestrowane jest zdarzenie arkusza przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="f20d3-114">A transfer journal event is registered.</span></span> <span data-ttu-id="f20d3-115">Zdarzenie przenosi jedną sztukę towaru A z oddziału 1 do oddziału 2.</span><span class="sxs-lookup"><span data-stu-id="f20d3-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="f20d3-116">Wymiar magazynowy Oddział jest traktowany jako część obiektu kosztu.</span><span class="sxs-lookup"><span data-stu-id="f20d3-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="f20d3-117">Z tego względu zdarzenie tworzy dwie transakcje magazynowe i dwa wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="f20d3-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="f20d3-118">Przykład 3: Tworzony jest jeden wpis kosztów</span><span class="sxs-lookup"><span data-stu-id="f20d3-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="f20d3-119">Zdarzenie przyjęcia produktów jest rejestrowane w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="f20d3-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="f20d3-120">Zdarzenia rejestruje 100 sztuk towaru A z kosztem jednostkowym 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="f20d3-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="f20d3-121">Ponieważ towar A używa numeru seryjnego do śledzenia celu zarządzania magazynem, tworzony jest unikatowy numer seryjny dla każdego przyjętego towaru.</span><span class="sxs-lookup"><span data-stu-id="f20d3-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="f20d3-122">Z tego względu zdarzenie tworzy 100 transakcji magazynowych i jeden wpisz kosztu.</span><span class="sxs-lookup"><span data-stu-id="f20d3-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="f20d3-123">Strona Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="f20d3-123">Cost entries page</span></span>
<span data-ttu-id="f20d3-124">Nowa strona **Wpisy kosztów** umożliwia przeglądanie i kontrolowanie rejestracji kosztów i ilości.</span><span class="sxs-lookup"><span data-stu-id="f20d3-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="f20d3-125">Ta strona stanowi uzupełnienie stron **Transakcje magazynowe** i **Rozliczenia zapasów**.</span><span class="sxs-lookup"><span data-stu-id="f20d3-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="f20d3-126">Rekordy są rejestrowane w porządku chronologicznym dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="f20d3-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="f20d3-127">W związku z tym można szybko znajdować i kontrolować zakumulowane koszty określonego zdarzenia lub wszystkie zdarzenia, które są powiązane z dokumentem.</span><span class="sxs-lookup"><span data-stu-id="f20d3-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="f20d3-128">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="f20d3-128">Here is an example:</span></span>

-   <span data-ttu-id="f20d3-129">Zdarzenie przyjęcia produktów jest rejestrowane dla towaru A. Przyjmowanych jest 100 sztuk z kosztem jednostkowym 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="f20d3-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="f20d3-130">Kilka dni po zarejestrowaniu zdarzenia faktury, koszt wzrasta do 11,00 USD.</span><span class="sxs-lookup"><span data-stu-id="f20d3-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="f20d3-131">Dlatego łączna suma wynosi 1100 USD.</span><span class="sxs-lookup"><span data-stu-id="f20d3-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="f20d3-132">Tworzony jest drugi załącznik, aby uwzględnić różnicę 100 USD.</span><span class="sxs-lookup"><span data-stu-id="f20d3-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="f20d3-133">Kilka dni później opłata dodatkowa w wysokości 15,00 USD na pokrycie kosztów transportu jest rejestrowana na zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="f20d3-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="f20d3-134">Załącznik</span><span class="sxs-lookup"><span data-stu-id="f20d3-134">Voucher</span></span> | <span data-ttu-id="f20d3-135">Data</span><span class="sxs-lookup"><span data-stu-id="f20d3-135">Date</span></span>       | <span data-ttu-id="f20d3-136">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="f20d3-136">Reference</span></span>      | <span data-ttu-id="f20d3-137">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="f20d3-137">Number</span></span> | <span data-ttu-id="f20d3-138">Identyfikator partii</span><span class="sxs-lookup"><span data-stu-id="f20d3-138">Lot ID</span></span>  | <span data-ttu-id="f20d3-139">Ilość</span><span class="sxs-lookup"><span data-stu-id="f20d3-139">Quantity</span></span> | <span data-ttu-id="f20d3-140">Ilość</span><span class="sxs-lookup"><span data-stu-id="f20d3-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="f20d3-141">00001</span><span class="sxs-lookup"><span data-stu-id="f20d3-141">00001</span></span>   | <span data-ttu-id="f20d3-142">01-01-2015</span><span class="sxs-lookup"><span data-stu-id="f20d3-142">01-01-2015</span></span> | <span data-ttu-id="f20d3-143">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="f20d3-143">Purchase order</span></span> | <span data-ttu-id="f20d3-144">100001</span><span class="sxs-lookup"><span data-stu-id="f20d3-144">100001</span></span> | <span data-ttu-id="f20d3-145">0000101</span><span class="sxs-lookup"><span data-stu-id="f20d3-145">0000101</span></span> | <span data-ttu-id="f20d3-146">100,00</span><span class="sxs-lookup"><span data-stu-id="f20d3-146">100.00</span></span>   | <span data-ttu-id="f20d3-147">1000.00</span><span class="sxs-lookup"><span data-stu-id="f20d3-147">1000.00</span></span> |
| <span data-ttu-id="f20d3-148">00002</span><span class="sxs-lookup"><span data-stu-id="f20d3-148">00002</span></span>   | <span data-ttu-id="f20d3-149">20-01-2015</span><span class="sxs-lookup"><span data-stu-id="f20d3-149">20-01-2015</span></span> | <span data-ttu-id="f20d3-150">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="f20d3-150">Purchase order</span></span> | <span data-ttu-id="f20d3-151">100001</span><span class="sxs-lookup"><span data-stu-id="f20d3-151">100001</span></span> | <span data-ttu-id="f20d3-152">0000101</span><span class="sxs-lookup"><span data-stu-id="f20d3-152">0000101</span></span> |          | <span data-ttu-id="f20d3-153">100,00</span><span class="sxs-lookup"><span data-stu-id="f20d3-153">100.00</span></span>  |
| <span data-ttu-id="f20d3-154">00003</span><span class="sxs-lookup"><span data-stu-id="f20d3-154">00003</span></span>   | <span data-ttu-id="f20d3-155">31-01-2015</span><span class="sxs-lookup"><span data-stu-id="f20d3-155">31-01-2015</span></span> | <span data-ttu-id="f20d3-156">Korekta</span><span class="sxs-lookup"><span data-stu-id="f20d3-156">Adjustment</span></span>     | <span data-ttu-id="f20d3-157">100001</span><span class="sxs-lookup"><span data-stu-id="f20d3-157">100001</span></span> | <span data-ttu-id="f20d3-158">0000101</span><span class="sxs-lookup"><span data-stu-id="f20d3-158">0000101</span></span> |          | <span data-ttu-id="f20d3-159">15,00</span><span class="sxs-lookup"><span data-stu-id="f20d3-159">15.00</span></span>   |

<span data-ttu-id="f20d3-160">Strona **Wpisy kosztu** umożliwia filtrowanie według identyfikatora dokumentu i daty dokumentu.</span><span class="sxs-lookup"><span data-stu-id="f20d3-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="f20d3-161">Wpisy kosztów są dostępne tylko dla [obiektów kosztów](cost-object.md) lub zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="f20d3-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="f20d3-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f20d3-162">Additional resources</span></span>
--------

[<span data-ttu-id="f20d3-163">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="f20d3-163">Cost objects</span></span>](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]