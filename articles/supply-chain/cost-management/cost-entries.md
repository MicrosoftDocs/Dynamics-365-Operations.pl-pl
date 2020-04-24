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
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8dc87ed64c888078f606a2b4d2e35c7c81e78b0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201877"
---
# <a name="cost-entries"></a><span data-ttu-id="a5691-104">Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="a5691-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5691-105">Ten artykuł zawiera informacje o wpisach kosztów i sytuacjach, kiedy są tworzone.</span><span class="sxs-lookup"><span data-stu-id="a5691-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="a5691-106">Wpis kosztu to rekord, w którym są rejestrowane ilość i koszt danego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="a5691-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="a5691-107">Wpisy kosztów są agregacjami dla transakcji magazynowych, które są rejestrowane w aktywnych wymiarach magazynu finansowego.</span><span class="sxs-lookup"><span data-stu-id="a5691-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="a5691-108">Przykłady</span><span class="sxs-lookup"><span data-stu-id="a5691-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="a5691-109">Przykład 1: Nie są tworzone żadne wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="a5691-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="a5691-110">Rejestrowane jest zdarzenie arkusza przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="a5691-110">A transfer journal event is registered.</span></span> <span data-ttu-id="a5691-111">Zdarzenie przenosi jedną sztukę towaru A z lokalizacji A do lokalizacji B. Wymiar magazynowy Lokalizacja nie jest traktowany jako część obiektu kosztu.</span><span class="sxs-lookup"><span data-stu-id="a5691-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="a5691-112">Z tego względu zdarzenie tworzy dwie transakcje magazynowe i żadnych wpisów kosztów.</span><span class="sxs-lookup"><span data-stu-id="a5691-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="a5691-113">Przykład 2: Wpisy kosztów są tworzone</span><span class="sxs-lookup"><span data-stu-id="a5691-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="a5691-114">Rejestrowane jest zdarzenie arkusza przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="a5691-114">A transfer journal event is registered.</span></span> <span data-ttu-id="a5691-115">Zdarzenie przenosi jedną sztukę towaru A z oddziału 1 do oddziału 2.</span><span class="sxs-lookup"><span data-stu-id="a5691-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="a5691-116">Wymiar magazynowy Oddział jest traktowany jako część obiektu kosztu.</span><span class="sxs-lookup"><span data-stu-id="a5691-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="a5691-117">Z tego względu zdarzenie tworzy dwie transakcje magazynowe i dwa wpisy kosztów.</span><span class="sxs-lookup"><span data-stu-id="a5691-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="a5691-118">Przykład 3: Tworzony jest jeden wpis kosztów</span><span class="sxs-lookup"><span data-stu-id="a5691-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="a5691-119">Zdarzenie przyjęcia produktów jest rejestrowane w zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="a5691-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="a5691-120">Zdarzenia rejestruje 100 sztuk towaru A z kosztem jednostkowym 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="a5691-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="a5691-121">Ponieważ towar A używa numeru seryjnego do śledzenia celu zarządzania magazynem, tworzony jest unikatowy numer seryjny dla każdego przyjętego towaru.</span><span class="sxs-lookup"><span data-stu-id="a5691-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="a5691-122">Z tego względu zdarzenie tworzy 100 transakcji magazynowych i jeden wpisz kosztu.</span><span class="sxs-lookup"><span data-stu-id="a5691-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="a5691-123">Strona Wpisy kosztów</span><span class="sxs-lookup"><span data-stu-id="a5691-123">Cost entries page</span></span>
<span data-ttu-id="a5691-124">Nowa strona **Wpisy kosztów** umożliwia przeglądanie i kontrolowanie rejestracji kosztów i ilości.</span><span class="sxs-lookup"><span data-stu-id="a5691-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="a5691-125">Ta strona stanowi uzupełnienie stron **Transakcje magazynowe** i **Rozliczenia zapasów**.</span><span class="sxs-lookup"><span data-stu-id="a5691-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="a5691-126">Rekordy są rejestrowane w porządku chronologicznym dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="a5691-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="a5691-127">W związku z tym można szybko znajdować i kontrolować zakumulowane koszty określonego zdarzenia lub wszystkie zdarzenia, które są powiązane z dokumentem.</span><span class="sxs-lookup"><span data-stu-id="a5691-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="a5691-128">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="a5691-128">Here is an example:</span></span>

-   <span data-ttu-id="a5691-129">Zdarzenie przyjęcia produktów jest rejestrowane dla towaru A. Przyjmowanych jest 100 sztuk z kosztem jednostkowym 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="a5691-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="a5691-130">Kilka dni po zarejestrowaniu zdarzenia faktury, koszt wzrasta do 11,00 USD.</span><span class="sxs-lookup"><span data-stu-id="a5691-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="a5691-131">Dlatego łączna suma wynosi 1100 USD.</span><span class="sxs-lookup"><span data-stu-id="a5691-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="a5691-132">Tworzony jest drugi załącznik, aby uwzględnić różnicę 100 USD.</span><span class="sxs-lookup"><span data-stu-id="a5691-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="a5691-133">Kilka dni później opłata dodatkowa w wysokości 15,00 USD na pokrycie kosztów transportu jest rejestrowana na zamówieniu zakupu.</span><span class="sxs-lookup"><span data-stu-id="a5691-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="a5691-134">Załącznik</span><span class="sxs-lookup"><span data-stu-id="a5691-134">Voucher</span></span> | <span data-ttu-id="a5691-135">Data</span><span class="sxs-lookup"><span data-stu-id="a5691-135">Date</span></span>       | <span data-ttu-id="a5691-136">Odwołanie</span><span class="sxs-lookup"><span data-stu-id="a5691-136">Reference</span></span>      | <span data-ttu-id="a5691-137">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="a5691-137">Number</span></span> | <span data-ttu-id="a5691-138">Identyfikator partii</span><span class="sxs-lookup"><span data-stu-id="a5691-138">Lot ID</span></span>  | <span data-ttu-id="a5691-139">Ilość</span><span class="sxs-lookup"><span data-stu-id="a5691-139">Quantity</span></span> | <span data-ttu-id="a5691-140">Ilość</span><span class="sxs-lookup"><span data-stu-id="a5691-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="a5691-141">00001</span><span class="sxs-lookup"><span data-stu-id="a5691-141">00001</span></span>   | <span data-ttu-id="a5691-142">01-01-2015</span><span class="sxs-lookup"><span data-stu-id="a5691-142">01-01-2015</span></span> | <span data-ttu-id="a5691-143">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="a5691-143">Purchase order</span></span> | <span data-ttu-id="a5691-144">100001</span><span class="sxs-lookup"><span data-stu-id="a5691-144">100001</span></span> | <span data-ttu-id="a5691-145">0000101</span><span class="sxs-lookup"><span data-stu-id="a5691-145">0000101</span></span> | <span data-ttu-id="a5691-146">100,00</span><span class="sxs-lookup"><span data-stu-id="a5691-146">100.00</span></span>   | <span data-ttu-id="a5691-147">1000.00</span><span class="sxs-lookup"><span data-stu-id="a5691-147">1000.00</span></span> |
| <span data-ttu-id="a5691-148">00002</span><span class="sxs-lookup"><span data-stu-id="a5691-148">00002</span></span>   | <span data-ttu-id="a5691-149">20-01-2015</span><span class="sxs-lookup"><span data-stu-id="a5691-149">20-01-2015</span></span> | <span data-ttu-id="a5691-150">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="a5691-150">Purchase order</span></span> | <span data-ttu-id="a5691-151">100001</span><span class="sxs-lookup"><span data-stu-id="a5691-151">100001</span></span> | <span data-ttu-id="a5691-152">0000101</span><span class="sxs-lookup"><span data-stu-id="a5691-152">0000101</span></span> |          | <span data-ttu-id="a5691-153">100,00</span><span class="sxs-lookup"><span data-stu-id="a5691-153">100.00</span></span>  |
| <span data-ttu-id="a5691-154">00003</span><span class="sxs-lookup"><span data-stu-id="a5691-154">00003</span></span>   | <span data-ttu-id="a5691-155">31-01-2015</span><span class="sxs-lookup"><span data-stu-id="a5691-155">31-01-2015</span></span> | <span data-ttu-id="a5691-156">Korekta</span><span class="sxs-lookup"><span data-stu-id="a5691-156">Adjustment</span></span>     | <span data-ttu-id="a5691-157">100001</span><span class="sxs-lookup"><span data-stu-id="a5691-157">100001</span></span> | <span data-ttu-id="a5691-158">0000101</span><span class="sxs-lookup"><span data-stu-id="a5691-158">0000101</span></span> |          | <span data-ttu-id="a5691-159">15,00</span><span class="sxs-lookup"><span data-stu-id="a5691-159">15.00</span></span>   |

<span data-ttu-id="a5691-160">Strona **Wpisy kosztu** umożliwia filtrowanie według identyfikatora dokumentu i daty dokumentu.</span><span class="sxs-lookup"><span data-stu-id="a5691-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="a5691-161">Wpisy kosztów są dostępne tylko dla [obiektów kosztów](cost-object.md) lub zwolnionych produktów.</span><span class="sxs-lookup"><span data-stu-id="a5691-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="a5691-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a5691-162">Additional resources</span></span>
--------

[<span data-ttu-id="a5691-163">Obiekty kosztów</span><span class="sxs-lookup"><span data-stu-id="a5691-163">Cost objects</span></span>](cost-object.md)



