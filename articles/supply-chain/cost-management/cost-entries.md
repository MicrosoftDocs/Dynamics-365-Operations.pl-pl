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
ms.search.scope: Core, Operations
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3116f9fd2d1fe6a0967b114a069f495cea6217a1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434890"
---
# <a name="cost-entries"></a><span data-ttu-id="4192f-104">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="4192f-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4192f-105">Ten artykuł zawiera informacje o wpisach kosztów i sytuacjach, kiedy są tworzone.</span><span class="sxs-lookup"><span data-stu-id="4192f-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="4192f-106">Wpis kosztu to rekord, w którym są rejestrowane ilość i koszt danego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4192f-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="4192f-107">Wpisy kosztów są agregacjami dla transakcji magazynowych, które są rejestrowane w aktywnych wymiarach magazynu finansowego.</span><span class="sxs-lookup"><span data-stu-id="4192f-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="4192f-108">Przykłady</span><span class="sxs-lookup"><span data-stu-id="4192f-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="4192f-109">Przykład 1: Nie są tworzone żadne wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="4192f-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="4192f-110">Rejestrowane jest zdarzenie arkusza przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="4192f-110">A transfer journal event is registered.</span></span> <span data-ttu-id="4192f-111">Zdarzenie przenosi jedną sztukę towaru A z lokalizacji A do lokalizacji B. Wymiar magazynowy Lokalizacja nie jest traktowany jako część obiektu kosztu.</span><span class="sxs-lookup"><span data-stu-id="4192f-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="4192f-112">Z tego względu zdarzenie tworzy dwie transakcje magazynowe i żadnych wpisów kosztów.</span><span class="sxs-lookup"><span data-stu-id="4192f-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="4192f-113">Przykład 2: Wpisy kosztów są tworzone</span><span class="sxs-lookup"><span data-stu-id="4192f-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="4192f-114">Rejestrowane jest zdarzenie arkusza przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="4192f-114">A transfer journal event is registered.</span></span> <span data-ttu-id="4192f-115">Zdarzenie przenosi jedną sztukę towaru A z oddziału 1 do oddziału 2.</span><span class="sxs-lookup"><span data-stu-id="4192f-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="4192f-116">Wymiar magazynowy Oddział jest traktowany jako część obiektu kosztu.</span><span class="sxs-lookup"><span data-stu-id="4192f-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="4192f-117">Z tego względu zdarzenie tworzy dwie transakcje magazynowe i dwa wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="4192f-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="4192f-118">Przykład 3: Tworzony jest jeden wpis kosztów</span><span class="sxs-lookup"><span data-stu-id="4192f-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="4192f-119">Zdarzenie przyjęcia produktów jest rejestrowane w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="4192f-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="4192f-120">Zdarzenia rejestruje 100 sztuk towaru A z kosztem jednostkowym 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="4192f-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="4192f-121">Ponieważ towar A używa numeru seryjnego do śledzenia celu zarządzania magazynem, tworzony jest unikatowy numer seryjny dla każdego przyjętego towaru.</span><span class="sxs-lookup"><span data-stu-id="4192f-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="4192f-122">Z tego względu zdarzenie tworzy 100 transakcji magazynowych i jeden wpisz kosztu.</span><span class="sxs-lookup"><span data-stu-id="4192f-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="4192f-123">Strona Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="4192f-123">Cost entries page</span></span>
<span data-ttu-id="4192f-124">Nowa strona **Wpisy kosztów** umożliwia przeglądanie i kontrolowanie rejestracji kosztów i ilości.</span><span class="sxs-lookup"><span data-stu-id="4192f-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="4192f-125">Ta strona stanowi uzupełnienie stron **Transakcje magazynowe** i **Rozliczenia zapasów**.</span><span class="sxs-lookup"><span data-stu-id="4192f-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="4192f-126">Rekordy są rejestrowane w porządku chronologicznym dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4192f-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="4192f-127">W związku z tym można szybko znajdować i kontrolować zakumulowane koszty określonego zdarzenia lub wszystkie zdarzenia, które są powiązane z dokumentem.</span><span class="sxs-lookup"><span data-stu-id="4192f-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="4192f-128">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="4192f-128">Here is an example:</span></span>

-   <span data-ttu-id="4192f-129">Zdarzenie przyjęcia produktów jest rejestrowane dla towaru A. Przyjmowanych jest 100 sztuk z kosztem jednostkowym 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="4192f-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="4192f-130">Kilka dni po zarejestrowaniu zdarzenia faktury, koszt wzrasta do 11,00 USD.</span><span class="sxs-lookup"><span data-stu-id="4192f-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="4192f-131">Dlatego łączna suma wynosi 1100 USD.</span><span class="sxs-lookup"><span data-stu-id="4192f-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="4192f-132">Tworzony jest drugi załącznik, aby uwzględnić różnicę 100 USD.</span><span class="sxs-lookup"><span data-stu-id="4192f-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="4192f-133">Kilka dni później opłata dodatkowa w wysokości 15,00 USD na pokrycie kosztów transportu jest rejestrowana na zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="4192f-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="4192f-134">Załącznik</span><span class="sxs-lookup"><span data-stu-id="4192f-134">Voucher</span></span> | <span data-ttu-id="4192f-135">Data</span><span class="sxs-lookup"><span data-stu-id="4192f-135">Date</span></span>       | <span data-ttu-id="4192f-136">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="4192f-136">Reference</span></span>      | <span data-ttu-id="4192f-137">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="4192f-137">Number</span></span> | <span data-ttu-id="4192f-138">Identyfikator partii</span><span class="sxs-lookup"><span data-stu-id="4192f-138">Lot ID</span></span>  | <span data-ttu-id="4192f-139">Ilość</span><span class="sxs-lookup"><span data-stu-id="4192f-139">Quantity</span></span> | <span data-ttu-id="4192f-140">Ilość</span><span class="sxs-lookup"><span data-stu-id="4192f-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="4192f-141">00001</span><span class="sxs-lookup"><span data-stu-id="4192f-141">00001</span></span>   | <span data-ttu-id="4192f-142">01-01-2015</span><span class="sxs-lookup"><span data-stu-id="4192f-142">01-01-2015</span></span> | <span data-ttu-id="4192f-143">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="4192f-143">Purchase order</span></span> | <span data-ttu-id="4192f-144">100001</span><span class="sxs-lookup"><span data-stu-id="4192f-144">100001</span></span> | <span data-ttu-id="4192f-145">0000101</span><span class="sxs-lookup"><span data-stu-id="4192f-145">0000101</span></span> | <span data-ttu-id="4192f-146">100,00</span><span class="sxs-lookup"><span data-stu-id="4192f-146">100.00</span></span>   | <span data-ttu-id="4192f-147">1000.00</span><span class="sxs-lookup"><span data-stu-id="4192f-147">1000.00</span></span> |
| <span data-ttu-id="4192f-148">00002</span><span class="sxs-lookup"><span data-stu-id="4192f-148">00002</span></span>   | <span data-ttu-id="4192f-149">20-01-2015</span><span class="sxs-lookup"><span data-stu-id="4192f-149">20-01-2015</span></span> | <span data-ttu-id="4192f-150">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="4192f-150">Purchase order</span></span> | <span data-ttu-id="4192f-151">100001</span><span class="sxs-lookup"><span data-stu-id="4192f-151">100001</span></span> | <span data-ttu-id="4192f-152">0000101</span><span class="sxs-lookup"><span data-stu-id="4192f-152">0000101</span></span> |          | <span data-ttu-id="4192f-153">100,00</span><span class="sxs-lookup"><span data-stu-id="4192f-153">100.00</span></span>  |
| <span data-ttu-id="4192f-154">00003</span><span class="sxs-lookup"><span data-stu-id="4192f-154">00003</span></span>   | <span data-ttu-id="4192f-155">31-01-2015</span><span class="sxs-lookup"><span data-stu-id="4192f-155">31-01-2015</span></span> | <span data-ttu-id="4192f-156">Korekta</span><span class="sxs-lookup"><span data-stu-id="4192f-156">Adjustment</span></span>     | <span data-ttu-id="4192f-157">100001</span><span class="sxs-lookup"><span data-stu-id="4192f-157">100001</span></span> | <span data-ttu-id="4192f-158">0000101</span><span class="sxs-lookup"><span data-stu-id="4192f-158">0000101</span></span> |          | <span data-ttu-id="4192f-159">15,00</span><span class="sxs-lookup"><span data-stu-id="4192f-159">15.00</span></span>   |

<span data-ttu-id="4192f-160">Strona **Wpisy kosztu** umożliwia filtrowanie według identyfikatora dokumentu i daty dokumentu.</span><span class="sxs-lookup"><span data-stu-id="4192f-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="4192f-161">Wpisy kosztów są dostępne tylko dla [obiektów kosztów](cost-object.md) lub zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="4192f-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="4192f-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="4192f-162">Additional resources</span></span>
--------

[<span data-ttu-id="4192f-163">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="4192f-163">Cost objects</span></span>](cost-object.md)



