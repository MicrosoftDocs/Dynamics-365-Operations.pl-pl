---
title: Powiązania jakości
description: W tym temacie opisano sposób używania skojarzeń jakości w systemie Microsoft Dynamics 365 Supply Chain Management do automatycznego generowania zleceń kontroli jakości związanych z procesami sprzedaży, zakupu i produkcji.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f46f09dc9b67cfb04d0320a071c2c739266af58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956786"
---
# <a name="quality-associations"></a><span data-ttu-id="b13a1-103">Powiązania jakości</span><span class="sxs-lookup"><span data-stu-id="b13a1-103">Quality associations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b13a1-104">W tym temacie opisano sposób używania skojarzeń jakości w systemie Microsoft Dynamics 365 Supply Chain Management do automatycznego generowania zleceń kontroli jakości związanych z procesami sprzedaży, zakupu i produkcji.</span><span class="sxs-lookup"><span data-stu-id="b13a1-104">This topic describes how you can use quality associations in Microsoft Dynamics 365 Supply Chain Management to automatically generate quality orders that are related to your sales, purchase, and production processes.</span></span>

<span data-ttu-id="b13a1-105">Powiązanie jakości określa wszystkie poniższe informacje dla generowanego zlecenia kontroli jakości:</span><span class="sxs-lookup"><span data-stu-id="b13a1-105">A quality association defines all the following information for a quality order that is generated:</span></span>

- <span data-ttu-id="b13a1-106">Zdarzenie transakcji</span><span class="sxs-lookup"><span data-stu-id="b13a1-106">The transaction event</span></span>
- <span data-ttu-id="b13a1-107">Zestaw testów, które należy wykonać na towarach</span><span class="sxs-lookup"><span data-stu-id="b13a1-107">The set of tests that must be performed on the items</span></span>
- <span data-ttu-id="b13a1-108">Akceptowalny poziom jakości (AQL)</span><span class="sxs-lookup"><span data-stu-id="b13a1-108">The acceptable quality level (AQL)</span></span>
- <span data-ttu-id="b13a1-109">Plan pobierania próbek</span><span class="sxs-lookup"><span data-stu-id="b13a1-109">The sampling plan</span></span>

<span data-ttu-id="b13a1-110">Należy określić skojarzenie jakości dla każdego odchylenia w procesie biznesowym, które wymaga automatycznego generowania zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-110">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="b13a1-111">Na przykład: zlecenie kontroli jakości może być generowane w procesie biznesowym związanym z zamówieniami zakupu, zleceniami kwarantanny, zamówieniami sprzedaży i zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="b13a1-111">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="b13a1-112">Korzystanie ze skojarzeń jakości</span><span class="sxs-lookup"><span data-stu-id="b13a1-112">Working with quality associations</span></span>

<span data-ttu-id="b13a1-113">Proces biznesowy, który używa skojarzeń jakości może być powiązany z różnymi dokumentami źródłowymi, takimi jak zamówienia zakupu, zamówienia sprzedaży lub zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="b13a1-113">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="b13a1-114">Poszczególne rekordy skojarzenia jakości określają serie testów, akceptowany poziom jakości i plan próbkowania dotyczące generowanych zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-114">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="b13a1-115">Należy określić rekord skojarzenia jakości dla każdego odchylenia w procesie biznesowym.</span><span class="sxs-lookup"><span data-stu-id="b13a1-115">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="b13a1-116">Na przykład można skonfigurować skojarzenia jakości, które generuje zlecenia kontroli jakości podczas aktualizowania dokumentu przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="b13a1-116">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="b13a1-117">W zależności od konfiguracji planu wykonania, w przypadku otwartego zlecenia kontroli jakości może zostać zablokowany sam proces wyzwalający.</span><span class="sxs-lookup"><span data-stu-id="b13a1-117">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order.</span></span> <span data-ttu-id="b13a1-118">Mogą również zostać zablokowane kolejne procesy, takie jak fakturowanie zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="b13a1-118">Alternatively, subsequent processes, such as purchase order invoicing, can be blocked.</span></span>

> [!NOTE]
> <span data-ttu-id="b13a1-119">Jeśli są otwarte zlecenia kontroli jakości, ilości zapasów są automatycznie blokowane przed wydaniem.</span><span class="sxs-lookup"><span data-stu-id="b13a1-119">While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="b13a1-120">W zależności od ustawienia pola **Pełne blokowanie** na stronie **Kontrola wyrywkowa towarów** ilość jest ilością w zleceniu kontroli jakości lub ilością w wierszu dokumentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="b13a1-120">Depending on the setting of the **Full blocking** field on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span> <span data-ttu-id="b13a1-121">Aby uzyskać więcej informacji, zobacz temat [Kontrola wyrywkowa towaru zarządzania jakością](quality-item-sampling.md).</span><span class="sxs-lookup"><span data-stu-id="b13a1-121">For more information, see [Quality management item sampling](quality-item-sampling.md).</span></span>

<span data-ttu-id="b13a1-122">W danym procesie biznesowym rekord skojarzenia jakości identyfikuje zdarzenie i warunki, dla których wygenerowano zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-122">For a given business process, the quality association record identifies the event and conditions that a quality order is generated for.</span></span> <span data-ttu-id="b13a1-123">Warunki mogą być właściwe dla oddziału lub firmy.</span><span class="sxs-lookup"><span data-stu-id="b13a1-123">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="b13a1-124">Zlecenia kontroli jakości, uwzględniające testy destrukcyjne mogą być generowane tylko wtedy, gdy istnieją dostępne zapasy dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="b13a1-124">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="b13a1-125">Aby pracować ze skojarzeniami jakości, przejdź do menu **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Skojarzenia jakości**.</span><span class="sxs-lookup"><span data-stu-id="b13a1-125">To work with quality associations, go to **Inventory management \> Setup \> Quality control \> Quality associations**.</span></span> <span data-ttu-id="b13a1-126">Poniższe przykłady pokazują możliwe sposoby określania rekordu skojarzenia jakości dla odchyleń w poszczególnych procesach biznesowych.</span><span class="sxs-lookup"><span data-stu-id="b13a1-126">The following examples show how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="b13a1-127">Dla każdego przykładu poniższa tabela podsumowuje zdarzenia i warunki zdefiniowane przez rekord skojarzenia jakości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-127">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13a1-128">Typ odwołania</span><span class="sxs-lookup"><span data-stu-id="b13a1-128">Reference type</span></span></th>
<th><span data-ttu-id="b13a1-129">Typ zdarzenia</span><span class="sxs-lookup"><span data-stu-id="b13a1-129">Event type</span></span></th>
<th><span data-ttu-id="b13a1-130">Wykonanie</span><span class="sxs-lookup"><span data-stu-id="b13a1-130">Execution</span></span></th>
<th><span data-ttu-id="b13a1-131">Blokowanie zdarzeń</span><span class="sxs-lookup"><span data-stu-id="b13a1-131">Event blocking</span></span></th>
<th><span data-ttu-id="b13a1-132">Odwołanie do dokumentu</span><span class="sxs-lookup"><span data-stu-id="b13a1-132">Document reference</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13a1-133">Zapasy</span><span class="sxs-lookup"><span data-stu-id="b13a1-133">Inventory</span></span></td>
<td><span data-ttu-id="b13a1-134">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="b13a1-134">Not applicable</span></span></td>
<td><span data-ttu-id="b13a1-135">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="b13a1-135">Not applicable</span></span></td>
<td><span data-ttu-id="b13a1-136">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-136">None</span></span></td>
<td><span data-ttu-id="b13a1-137">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="b13a1-137">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="b13a1-138">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="b13a1-138">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="b13a1-139">Proces pobierania został zaplanowany</span><span class="sxs-lookup"><span data-stu-id="b13a1-139">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="b13a1-140">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-140">Before</span></span></td>
<td><span data-ttu-id="b13a1-141">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-141">None</span></span></td>
<td rowspan="22"><span data-ttu-id="b13a1-142">Określony identyfikator, Grupa lub Tylko wszystkie</span><span class="sxs-lookup"><span data-stu-id="b13a1-142">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-143">Proces pobierania</span><span class="sxs-lookup"><span data-stu-id="b13a1-143">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-144">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="b13a1-144">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-145">Faktura</span><span class="sxs-lookup"><span data-stu-id="b13a1-145">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="b13a1-146">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="b13a1-146">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-147">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-147">Before</span></span></td>
<td><span data-ttu-id="b13a1-148">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-148">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-149">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="b13a1-149">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-150">Faktura</span><span class="sxs-lookup"><span data-stu-id="b13a1-150">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="b13a1-151">Zakup</span><span class="sxs-lookup"><span data-stu-id="b13a1-151">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="b13a1-152">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="b13a1-152">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="b13a1-153">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-153">Before</span></span></td>
<td><span data-ttu-id="b13a1-154">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-154">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-155">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="b13a1-155">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-156">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="b13a1-156">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-157">Faktura</span><span class="sxs-lookup"><span data-stu-id="b13a1-157">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="b13a1-158">Po</span><span class="sxs-lookup"><span data-stu-id="b13a1-158">After</span></span></td>
<td><span data-ttu-id="b13a1-159">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-160">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="b13a1-160">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-161">Faktura</span><span class="sxs-lookup"><span data-stu-id="b13a1-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="b13a1-162">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="b13a1-162">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-163">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="b13a1-163">Not applicable</span></span></td>
<td><span data-ttu-id="b13a1-164">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-164">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-165">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="b13a1-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-166">Faktura</span><span class="sxs-lookup"><span data-stu-id="b13a1-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="b13a1-167">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="b13a1-167">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-168">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-168">Before</span></span></td>
<td><span data-ttu-id="b13a1-169">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-169">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-170">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="b13a1-170">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-171">Faktura</span><span class="sxs-lookup"><span data-stu-id="b13a1-171">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="b13a1-172">Po</span><span class="sxs-lookup"><span data-stu-id="b13a1-172">After</span></span></td>
<td><span data-ttu-id="b13a1-173">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-174">Faktura</span><span class="sxs-lookup"><span data-stu-id="b13a1-174">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="b13a1-175">Produkcja</span><span class="sxs-lookup"><span data-stu-id="b13a1-175">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-176">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="b13a1-176">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-177">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="b13a1-177">Not applicable</span></span></td>
<td><span data-ttu-id="b13a1-178">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-178">None</span></span></td>
<td rowspan="12"><span data-ttu-id="b13a1-179">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="b13a1-179">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-180">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-180">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-181">Zamknij</span><span class="sxs-lookup"><span data-stu-id="b13a1-181">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="b13a1-182">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-182">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-183">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-183">Before</span></span></td>
<td><span data-ttu-id="b13a1-184">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-185">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-185">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-186">Zamknij</span><span class="sxs-lookup"><span data-stu-id="b13a1-186">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="b13a1-187">Po</span><span class="sxs-lookup"><span data-stu-id="b13a1-187">After</span></span></td>
<td><span data-ttu-id="b13a1-188">Brak</span><span class="sxs-lookup"><span data-stu-id="b13a1-188">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-189">Zamknij</span><span class="sxs-lookup"><span data-stu-id="b13a1-189">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="b13a1-190">Kwarantanna</span><span class="sxs-lookup"><span data-stu-id="b13a1-190">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-191">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-191">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="b13a1-192">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-192">Before</span></span></td>
<td><span data-ttu-id="b13a1-193">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-193">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-194">Zamknij</span><span class="sxs-lookup"><span data-stu-id="b13a1-194">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-195">Po</span><span class="sxs-lookup"><span data-stu-id="b13a1-195">After</span></span></td>
<td><span data-ttu-id="b13a1-196">Zamknij</span><span class="sxs-lookup"><span data-stu-id="b13a1-196">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-197">Zamknij</span><span class="sxs-lookup"><span data-stu-id="b13a1-197">End</span></span></td>
<td><span data-ttu-id="b13a1-198">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-198">Before</span></span></td>
<td><span data-ttu-id="b13a1-199">Zamknij</span><span class="sxs-lookup"><span data-stu-id="b13a1-199">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="b13a1-200">Operacja marszruty</span><span class="sxs-lookup"><span data-stu-id="b13a1-200">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-201">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-201">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="b13a1-202">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-202">Before</span></span></td>
<td><span data-ttu-id="b13a1-203">None</span><span class="sxs-lookup"><span data-stu-id="b13a1-203">None</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-204">Określony identyfikator, Grupa lub Wszystkie, oraz określony Zasób, Grupa lub Wszystkie</span><span class="sxs-lookup"><span data-stu-id="b13a1-204">Specific ID, Group, or All, and specific Resource, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-205">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-205">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-206">Po</span><span class="sxs-lookup"><span data-stu-id="b13a1-206">After</span></span></td>
<td><span data-ttu-id="b13a1-207">None</span><span class="sxs-lookup"><span data-stu-id="b13a1-207">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="b13a1-208">Wytwarzanie produktu towarzyszącego</span><span class="sxs-lookup"><span data-stu-id="b13a1-208">Co-product production</span></span></td>
<td><span data-ttu-id="b13a1-209">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="b13a1-209">Registration</span></span></td>
<td><span data-ttu-id="b13a1-210">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="b13a1-210">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-211">None</span><span class="sxs-lookup"><span data-stu-id="b13a1-211">None</span></span></td>
<td rowspan="3"><span data-ttu-id="b13a1-212">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="b13a1-212">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="b13a1-213">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-213">Report as finished</span></span></td>
<td><span data-ttu-id="b13a1-214">Przed</span><span class="sxs-lookup"><span data-stu-id="b13a1-214">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-215">Po</span><span class="sxs-lookup"><span data-stu-id="b13a1-215">After</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="b13a1-216">Funkcja *Zarządzanie jakością dla procesów magazynowych* dodaje możliwości przetwarzania zlecenia kontroli jakości dla produkcji z polem **Typ zdarzenia** ustawionym jako *Zgłoś jako gotowe*, a polem **Wykonanie** jako *Po* i dla zakupów z polem **Typ zdarzenia** ustawionym jako *Rejestracja*.</span><span class="sxs-lookup"><span data-stu-id="b13a1-216">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production where the **Event type** field is set to *Report as finished* and the **Execution** field is set to *After*, and for purchases where the **Event type** field is set to *Registration*.</span></span> <span data-ttu-id="b13a1-217">Aby zapoznać sie ze szczegółami, zobacz [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="b13a1-217">For more information, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

<span data-ttu-id="b13a1-218">Poniższa tabela zawiera więcej informacji na temat sposobu generowania zleceń kontroli jakości dla określonych typów procesów.</span><span class="sxs-lookup"><span data-stu-id="b13a1-218">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>

<div class="tableSection">
<table>
<thead>
<tr>
<th><span data-ttu-id="b13a1-219">Typ procesu</span><span class="sxs-lookup"><span data-stu-id="b13a1-219">Type of process</span></span></th>
<th><span data-ttu-id="b13a1-220">Kiedy zlecenia kontroli jakości mogą być generowane automatycznie</span><span class="sxs-lookup"><span data-stu-id="b13a1-220">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="b13a1-221">Kiedy zlecenia kontroli jakości mogą być generowane, jeśli wymagane są testy destrukcyjne</span><span class="sxs-lookup"><span data-stu-id="b13a1-221">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="b13a1-222">Informacje o warunku</span><span class="sxs-lookup"><span data-stu-id="b13a1-222">Condition information</span></span></th>
<th><span data-ttu-id="b13a1-223">Informacje generowane ręcznie</span><span class="sxs-lookup"><span data-stu-id="b13a1-223">Manual generation information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13a1-224">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="b13a1-224">Purchase order</span></span></td>
<td><span data-ttu-id="b13a1-225">Przed zaksięgowaniem lub po zaksięgowaniu listy przychodu lub dokumentu przyjęcia produktu dla odebranego materiału</span><span class="sxs-lookup"><span data-stu-id="b13a1-225">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="b13a1-226">Po odebraniu i zaksięgowaniu dokumentu przyjęcia produktów dla materiału, ponieważ materiał musi być dostępny do testów destrukcyjnych</span><span class="sxs-lookup"><span data-stu-id="b13a1-226">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="b13a1-227">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="b13a1-227">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="b13a1-228">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia zakupu, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="b13a1-228">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-229">Zlecenie kwarantanny</span><span class="sxs-lookup"><span data-stu-id="b13a1-229">Quarantine order</span></span></td>
<td><span data-ttu-id="b13a1-230">Przed lub po zgłoszeniu zlecenia kwarantanny jako zakończonego lub gotowego</span><span class="sxs-lookup"><span data-stu-id="b13a1-230">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="b13a1-231">Nie można generować zleceń kontroli jakości wymagających testów destrukcyjnych.</span><span class="sxs-lookup"><span data-stu-id="b13a1-231">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="b13a1-232">Zakłada się, że funkcja zlecenia kwarantanny obsługuje dyspozycje niszczonego materiału.</span><span class="sxs-lookup"><span data-stu-id="b13a1-232">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="b13a1-233">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="b13a1-233">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="b13a1-234">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia kwarantanny, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="b13a1-234">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-235">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="b13a1-235">Sales order</span></span></td>
<td><span data-ttu-id="b13a1-236">Przed zaplanowanym procesem pobrania lub aktualizacją dokumentu dostawy dla wysłanych pozycji</span><span class="sxs-lookup"><span data-stu-id="b13a1-236">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="b13a1-237">Na dowolnym z etapów</span><span class="sxs-lookup"><span data-stu-id="b13a1-237">At any step</span></span></td>
<td><span data-ttu-id="b13a1-238">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub odbiorcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="b13a1-238">The requirement for a quality order can reflect a specific site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="b13a1-239">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia sprzedaży, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="b13a1-239">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-240">Zlecenie produkcyjne</span><span class="sxs-lookup"><span data-stu-id="b13a1-240">Production order</span></span></td>
<td><span data-ttu-id="b13a1-241">Przed zgłoszeniem lub po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="b13a1-241">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="b13a1-242">Po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="b13a1-242">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="b13a1-243">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem lub towarem albo kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="b13a1-243">The requirement for a quality order can reflect a specific site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="b13a1-244">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia produkcyjnego, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="b13a1-244">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-245">Zlecenie produkcyjne, które ma operację marszruty</span><span class="sxs-lookup"><span data-stu-id="b13a1-245">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="b13a1-246">Przed zakończeniem lub po zakończeniu raportu dla operacji</span><span class="sxs-lookup"><span data-stu-id="b13a1-246">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="b13a1-247">Po zakończeniu zgłaszania produkcji dla ostatniej operacji</span><span class="sxs-lookup"><span data-stu-id="b13a1-247">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="b13a1-248">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub zasobem operacyjnym, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="b13a1-248">The requirement for a quality order can reflect a specific site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="b13a1-249">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy operacji marszruty, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="b13a1-249">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-250">Zapasy</span><span class="sxs-lookup"><span data-stu-id="b13a1-250">Inventory</span></span></td>
<td><span data-ttu-id="b13a1-251">Zlecenie kontroli jakości nie może być generowane automatycznie dla transakcji w arkuszu magazynowym lub dla transakcji zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="b13a1-251">A quality order can't be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="b13a1-252">Zlecenie kontroli jakości musi być tworzone ręcznie dla ilości zapasów towaru.</span><span class="sxs-lookup"><span data-stu-id="b13a1-252">A quality order must be manually created for an item's inventory quantity.</span></span> <span data-ttu-id="b13a1-253">Fizyczne dostępne zapasy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="b13a1-253">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a><span data-ttu-id="b13a1-254">Przykłady automatycznego generowania zleceń kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="b13a1-254">Examples of automatic generation of quality orders</span></span>

### <a name="purchasing"></a><span data-ttu-id="b13a1-255">Zakup</span><span class="sxs-lookup"><span data-stu-id="b13a1-255">Purchasing</span></span>

<span data-ttu-id="b13a1-256">Jeśli w obszarze zakupów w polu **Typ zdarzenia** zostanie ustawiona wartość *Przyjęcie produktów*, a w polu **Wykonanie** wartość *Po* na stronie **Powiązania jakości**, otrzymasz następujące wyniki :</span><span class="sxs-lookup"><span data-stu-id="b13a1-256">In purchasing, if you set the **Event type** field to *Product receipt* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="b13a1-257">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Tak*, zlecenie kontroli jakości jest generowane dla każdego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości i ustawień w ramach kontroli wyrywkowej pozycji.</span><span class="sxs-lookup"><span data-stu-id="b13a1-257">If the **Per updated quantity** option is set to *Yes*, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="b13a1-258">Za każdym razem, gdy ilość jest przyjmowana względem zamówienia zakupu, nowe zlecenia kontroli jakości są generowane na podstawie nowo przyjętej ilości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-258">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="b13a1-259">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Nie*, zlecenie kontroli jakości jest generowane dla pierwszego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-259">If the **Per updated quantity** option is set to *No*, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="b13a1-260">Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="b13a1-260">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="b13a1-261">Zlecenia kontroli jakości nie są generowane dla kolejnych przyjęć względem zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="b13a1-261">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="b13a1-262">Produkcyjne</span><span class="sxs-lookup"><span data-stu-id="b13a1-262">Production</span></span>

<span data-ttu-id="b13a1-263">Jeśli w obszarze produkcji w polu **Typ zdarzenia** zostanie ustawiona wartość *Zgłoszenie wyrobów gotowych*, a w polu **Wykonanie** wartość *Po* na stronie **Powiązania jakości**, otrzymasz następujące wyniki :</span><span class="sxs-lookup"><span data-stu-id="b13a1-263">In production, if you set the **Event type** field to *Report as finished* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="b13a1-264">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Tak*, zlecenie kontroli jakości jest generowane dla każdej ilości wyrobów gotowych i ustawień w ramach kontroli wyrywkowej pozycji.</span><span class="sxs-lookup"><span data-stu-id="b13a1-264">If the **Per updated quantity** option is set to *Yes*, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="b13a1-265">Za każdym razem, gdy ilość jest zgłaszana jako gotowa względem zlecenia produkcyjnego, nowe zlecenia kontroli jakości są generowane na podstawie nowej ilości zgłoszonej jako gotowa.</span><span class="sxs-lookup"><span data-stu-id="b13a1-265">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on the newly finished quantity.</span></span> <span data-ttu-id="b13a1-266">Ta logika generowania jest spójna z procesem zakupów.</span><span class="sxs-lookup"><span data-stu-id="b13a1-266">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="b13a1-267">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na *Nie*, zlecenie kontroli jakości jest generowane po pierwszym zgłoszeniu ilości jako gotowej na podstawie gotowej ilości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-267">If the **Per updated quantity** option is set to *No*, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="b13a1-268">Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia kontroli wyrywkowej pozycji.</span><span class="sxs-lookup"><span data-stu-id="b13a1-268">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="b13a1-269">Zlecenia kontroli jakości nie są generowane dla kolejnych gotowych ilości.</span><span class="sxs-lookup"><span data-stu-id="b13a1-269">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="b13a1-270">Specyfikacja jakości</span><span class="sxs-lookup"><span data-stu-id="b13a1-270">Quality specification</span></span></th>
<th><span data-ttu-id="b13a1-271">Dla zaktualizowanej ilości</span><span class="sxs-lookup"><span data-stu-id="b13a1-271">Per updated quantity</span></span></th>
<th><span data-ttu-id="b13a1-272">Dla wymiaru śledzenia</span><span class="sxs-lookup"><span data-stu-id="b13a1-272">Per tracking dimension</span></span></th>
<th><span data-ttu-id="b13a1-273">Wynik</span><span class="sxs-lookup"><span data-stu-id="b13a1-273">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="b13a1-274">Wartość procentowa: 10%</span><span class="sxs-lookup"><span data-stu-id="b13a1-274">Percentage: 10%</span></span></td>
<td><span data-ttu-id="b13a1-275">Tak</span><span class="sxs-lookup"><span data-stu-id="b13a1-275">Yes</span></span></td>
<td>
<p><span data-ttu-id="b13a1-276">Numer partii: Nie</span><span class="sxs-lookup"><span data-stu-id="b13a1-276">Batch number: No</span></span></p>
<p><span data-ttu-id="b13a1-277">Numer seryjny: Nie</span><span class="sxs-lookup"><span data-stu-id="b13a1-277">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="b13a1-278">Ilość w zamówieniu: 100</span><span class="sxs-lookup"><span data-stu-id="b13a1-278">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="b13a1-279">Zgłaszanie wyrobów gotowych dla 30</span><span class="sxs-lookup"><span data-stu-id="b13a1-279">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="b13a1-280">Zlecenie kontroli jakości 1 dla 3 (10% z 30)</span><span class="sxs-lookup"><span data-stu-id="b13a1-280">Quality order 1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="b13a1-281">Zgłaszanie wyrobów gotowych dla 70</span><span class="sxs-lookup"><span data-stu-id="b13a1-281">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="b13a1-282">Zlecenie kontroli jakości 2 dla 7 (10% pozostałej ilości zamówienia, w tym przypadku 70)</span><span class="sxs-lookup"><span data-stu-id="b13a1-282">Quality order 2 for 7 (10% of the remaining order quantity, which is 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-283">Stała ilość: 1</span><span class="sxs-lookup"><span data-stu-id="b13a1-283">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="b13a1-284">Nr</span><span class="sxs-lookup"><span data-stu-id="b13a1-284">No</span></span></td>
<td>
<p><span data-ttu-id="b13a1-285">Numer partii: Nie</span><span class="sxs-lookup"><span data-stu-id="b13a1-285">Batch number: No</span></span></p>
<p><span data-ttu-id="b13a1-286">Numer seryjny: Nie</span><span class="sxs-lookup"><span data-stu-id="b13a1-286">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="b13a1-287">Ilość w zamówieniu: 100</span><span class="sxs-lookup"><span data-stu-id="b13a1-287">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="b13a1-288">Zgłaszanie wyrobów gotowych dla 30</span><span class="sxs-lookup"><span data-stu-id="b13a1-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="b13a1-289">Zlecenie kontroli jakości 1 dla 1 (dla pierwszej ilości zgłoszonej jako gotowa, która ma stałą wartość równą 1)</span><span class="sxs-lookup"><span data-stu-id="b13a1-289">Quality order 1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="b13a1-290">Zlecenie kontroli jakości 2 dla 1 (dla pozostałej ilości, która nadal ma stałą wartość równą 1)</span><span class="sxs-lookup"><span data-stu-id="b13a1-290">Quality order 2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="b13a1-291">Zgłaszanie wyrobów gotowych dla 10</span><span class="sxs-lookup"><span data-stu-id="b13a1-291">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="b13a1-292">Zlecenia kontroli jakości nie są tworzone.</span><span class="sxs-lookup"><span data-stu-id="b13a1-292">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="b13a1-293">Zgłaszanie wyrobów gotowych dla 60</span><span class="sxs-lookup"><span data-stu-id="b13a1-293">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="b13a1-294">Zlecenia kontroli jakości nie są tworzone.</span><span class="sxs-lookup"><span data-stu-id="b13a1-294">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-295">Stała ilość: 1</span><span class="sxs-lookup"><span data-stu-id="b13a1-295">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="b13a1-296">Tak</span><span class="sxs-lookup"><span data-stu-id="b13a1-296">Yes</span></span></td>
<td>
<p><span data-ttu-id="b13a1-297">Numer partii: Tak</span><span class="sxs-lookup"><span data-stu-id="b13a1-297">Batch number: Yes</span></span></p>
<p><span data-ttu-id="b13a1-298">Numer seryjny: Tak</span><span class="sxs-lookup"><span data-stu-id="b13a1-298">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="b13a1-299">Ilość w zamówieniu: 10</span><span class="sxs-lookup"><span data-stu-id="b13a1-299">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="b13a1-300">Zgłoś jako gotowe dla 3: 1 dla numeru partii b1, numeru seryjnego s1; 1 dla numeru partii b2, numeru seryjnego s2; i 1 dla numeru partii b3, numeru seryjnego s3</span><span class="sxs-lookup"><span data-stu-id="b13a1-300">Report as finished for 3: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; and 1 for batch number b3, serial number s3</span></span>
<ul>
<li><span data-ttu-id="b13a1-301">Zlecenie kontroli jakości 1 dla 1 z numeru partii b1, numeru seryjnego s1</span><span class="sxs-lookup"><span data-stu-id="b13a1-301">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="b13a1-302">Zlecenie kontroli jakości 2 dla 1 z numeru partii b2, numeru seryjnego s2</span><span class="sxs-lookup"><span data-stu-id="b13a1-302">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="b13a1-303">Zlecenie kontroli jakości 3 dla 1 z numeru partii b3, numeru seryjnego s3</span><span class="sxs-lookup"><span data-stu-id="b13a1-303">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="b13a1-304">Zgłoś jako gotowe dla 2: 1 dla numeru partii b4, numeru seryjnego s4; i 1 dla numeru partii b5, numeru seryjnego s5</span><span class="sxs-lookup"><span data-stu-id="b13a1-304">Report as finished for 2: 1 for batch number b4, serial number s4; and 1 for batch number b5, serial number s5</span></span>
<ul>
<li><span data-ttu-id="b13a1-305">Zlecenie kontroli jakości 4 dla 1 z numeru partii b4, numeru seryjnego s4</span><span class="sxs-lookup"><span data-stu-id="b13a1-305">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
<li><span data-ttu-id="b13a1-306">Zlecenie kontroli jakości 5 dla 1 z numeru partii b5, numeru seryjnego s5</span><span class="sxs-lookup"><span data-stu-id="b13a1-306">Quality order 5 for 1 of batch number b5, serial number s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="b13a1-307"><strong>Uwaga:</strong> partii można użyć ponownie.</span><span class="sxs-lookup"><span data-stu-id="b13a1-307"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="b13a1-308">Stała ilość: 2</span><span class="sxs-lookup"><span data-stu-id="b13a1-308">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="b13a1-309">Nr</span><span class="sxs-lookup"><span data-stu-id="b13a1-309">No</span></span></td>
<td>
<p><span data-ttu-id="b13a1-310">Numer partii: Tak</span><span class="sxs-lookup"><span data-stu-id="b13a1-310">Batch number: Yes</span></span></p>
<p><span data-ttu-id="b13a1-311">Numer seryjny: Tak</span><span class="sxs-lookup"><span data-stu-id="b13a1-311">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="b13a1-312">Ilość w zamówieniu: 10</span><span class="sxs-lookup"><span data-stu-id="b13a1-312">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="b13a1-313">Zgłoś jako gotowe dla 4: 1 dla numeru partii b1, numeru seryjnego s1; 1 dla numeru partii b2, numeru seryjnego s2; 1 dla numeru partii b3, numeru seryjnego s3 i 1 dla numeru partii b4, numery seryjnego s4</span><span class="sxs-lookup"><span data-stu-id="b13a1-313">Report as finished for 4: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; 1 for batch number b3, serial number s3; and 1 for batch number b4, serial number s4</span></span>
<ul>
<li><span data-ttu-id="b13a1-314">Zlecenie kontroli jakości 1 dla 1 z numeru partii b1, numeru seryjnego s1</span><span class="sxs-lookup"><span data-stu-id="b13a1-314">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="b13a1-315">Zlecenie kontroli jakości 2 dla 1 z numeru partii b2, numeru seryjnego s2</span><span class="sxs-lookup"><span data-stu-id="b13a1-315">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="b13a1-316">Zlecenie kontroli jakości 3 dla 1 z numeru partii b3, numeru seryjnego s3</span><span class="sxs-lookup"><span data-stu-id="b13a1-316">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
<li><span data-ttu-id="b13a1-317">Zlecenie kontroli jakości 4 dla 1 z numeru partii b4, numeru seryjnego s4</span><span class="sxs-lookup"><span data-stu-id="b13a1-317">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="b13a1-318">Zlecenie kontroli jakości 5 dla 2 bez odwołania do numeru partii i numeru seryjnego</span><span class="sxs-lookup"><span data-stu-id="b13a1-318">Quality order 5 for 2, without a reference to a batch number and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="b13a1-319">Zgłoś jako gotowe dla 6: 1 dla numeru partii b5, numeru seryjnego s5; 1 dla numeru partii b6, numeru seryjnego s6; 1 dla numeru partii b7, numeru seryjnego s7; 1 dla numeru partii b8, numeru seryjnego s8; 1 dla numeru partii b9, numeru seryjnego s9; i 1 dla numeru partii b10, numeru seryjnego s10</span><span class="sxs-lookup"><span data-stu-id="b13a1-319">Report as finished for 6: 1 for batch number b5, serial number s5; 1 for batch number b6, serial number s6; 1 for batch number b7, serial number s7; 1 for batch number b8, serial number s8; 1 for batch number b9, serial number s9; and 1 for batch number b10, serial number s10</span></span>
<ul>
<li><span data-ttu-id="b13a1-320">Zlecenia kontroli jakości nie są tworzone.</span><span class="sxs-lookup"><span data-stu-id="b13a1-320">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="b13a1-321">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b13a1-321">Additional resources</span></span>

- [<span data-ttu-id="b13a1-322">Procesy zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="b13a1-322">Quality management processes</span></span>](quality-management-processes.md)
- [<span data-ttu-id="b13a1-323">Włączanie zarządzania kontrolą jakości i niezgodnością</span><span class="sxs-lookup"><span data-stu-id="b13a1-323">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="b13a1-324">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="b13a1-324">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
