---
title: "Omówienie zarządzanie jakością"
description: "W tym temacie opisano, jak za pomocą funkcji zarządzania jakością w programie Microsoft Dynamics 365 for Finance and Operations poprawiać jakość produktów w łańcuchu dostaw."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 79b3127f726a08cc24c20145b5ad9969157a899c
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="quality-management-overview"></a><span data-ttu-id="05c19-103">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="05c19-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05c19-104">W tym temacie opisano, jak za pomocą funkcji zarządzania jakością w programie Microsoft Dynamics 365 for Finance and Operations poprawiać jakość produktów w łańcuchu dostaw.</span><span class="sxs-lookup"><span data-stu-id="05c19-104">This topic describes how you can use quality management in Microsoft Dynamics 365 for Finance and Operations to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="05c19-105">Zarządzanie jakością pomaga przy zarządzaniu czasem przetwarzania, kiedy masz do czynienia z produktami niespełniającymi norm, bez względu na pochodzenie tych produktów.</span><span class="sxs-lookup"><span data-stu-id="05c19-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="05c19-106">Ze względu na to, że typy diagnostyki są powiązane z raportowaniem korekt, program Microsoft Dynamics 365 for Finance and Operations może zaplanować zadania usuwania problemów i zapobiegania ich ponownemu występowaniu.</span><span class="sxs-lookup"><span data-stu-id="05c19-106">Because diagnostic types are linked to correction reporting, Microsoft Dynamics 365 for Finance and Operations can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="05c19-107">Oprócz funkcji związanych z zarządzaniem brakiem zgodności zarządzanie jakością zawiera funkcje monitorowania błędów według typu problemu (łącznie z błędami wewnętrznymi) i identyfikowania rozwiązań krótko- i długoterminowych.</span><span class="sxs-lookup"><span data-stu-id="05c19-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="05c19-108">Statystyki kluczowych wskaźników wydajności (KPI) pokazują historię wcześniejszych problemów z brakiem zgodności i rozwiązania, które zostały zastosowane do ich korekty.</span><span class="sxs-lookup"><span data-stu-id="05c19-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="05c19-109">Korzystając z danych historycznych można sprawdzić skuteczność pomiarów jakości, które zostały wcześniej przeprowadzone, i określić odpowiednie rozwiązania na przyszłość.</span><span class="sxs-lookup"><span data-stu-id="05c19-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="05c19-110">Po skonfigurowaniu powiązania jakości system Finance and Operations może generować zlecania kontroli jakości dla różnych procesów biznesowych, zdarzenia i warunki.</span><span class="sxs-lookup"><span data-stu-id="05c19-110">When you set up a quality association, Finance and Operations can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="05c19-111">Skojarzenia jakości mogą obejmować określone pozycje, grupy towarów lub wszystkie pozycje.</span><span class="sxs-lookup"><span data-stu-id="05c19-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="05c19-112">Przykłady korzystania z funkcji zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="05c19-112">Examples of the use of quality management</span></span>
<span data-ttu-id="05c19-113">Zarządzanie jakością jest elastyczne i może być implementowane na różne sposoby, aby spełnić wymagania określonych poziomów operacji łańcucha dostaw.</span><span class="sxs-lookup"><span data-stu-id="05c19-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="05c19-114">Poniższe przykłady ilustrują możliwe wykorzystanie tych funkcji:</span><span class="sxs-lookup"><span data-stu-id="05c19-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="05c19-115">Automatyczne uruchamianie procesu kontroli jakości, na podstawie wstępnie zdefiniowanych kryteriów (przy rejestracji magazynu zamówienia zakupu od określonego dostawcy).</span><span class="sxs-lookup"><span data-stu-id="05c19-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="05c19-116">Blokowanie zapasów podczas inspekcji, aby zapobiec używaniu niezatwierdzonych zapasów (całkowite blokowanie ilości zamówienia zakupu).</span><span class="sxs-lookup"><span data-stu-id="05c19-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="05c19-117">Używanie kontroli wyrywkowej pozycji w ramach powiązania jakości do określenia kwoty bieżących zapasów fizycznych, które muszą być poddane inspekcji.</span><span class="sxs-lookup"><span data-stu-id="05c19-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="05c19-118">Kontrola wyrywkowa może dotyczyć stałej ilości lub części określonej procentowo.</span><span class="sxs-lookup"><span data-stu-id="05c19-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="05c19-119">Tworzenie zleceń kontroli jakości dla przyjęć częściowych.</span><span class="sxs-lookup"><span data-stu-id="05c19-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="05c19-120">Aby utworzyć zlecenie kontroli jakości oparte na ilości fizycznie przyjętej względem zamówienia, należy zaznaczyć pole wyboru **Dla zaktualizowanej ilości** w formularzu **Kontrola wyrywkowa towarów**.</span><span class="sxs-lookup"><span data-stu-id="05c19-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="05c19-121">Tworzenie typów testów zawierających minimalne, maksymalne i docelowe wartości testu, i testowanie jakościowe vs ilościowe ze wstępnie zdefiniowanymi wynikami weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="05c19-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="05c19-122">Określanie akceptowanego poziomu jakości (AQL) do kontrolowania tolerancji pomiaru jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="05c19-123">Określanie zasobów wymaganych do operacji inspekcji, takich jak obszar testowy i przyrządy testowe.</span><span class="sxs-lookup"><span data-stu-id="05c19-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="05c19-124">Korzystanie ze skojarzeń jakości</span><span class="sxs-lookup"><span data-stu-id="05c19-124">Working with quality associations</span></span>
<span data-ttu-id="05c19-125">Proces biznesowy, który używa skojarzeń jakości może być powiązany z różnymi dokumentami źródłowymi, takimi jak zamówienia zakupu, zamówienia sprzedaży lub zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="05c19-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="05c19-126">Poszczególne rekordy skojarzenia jakości określają serie testów, akceptowany poziom jakości i plan próbkowania dotyczące generowanych zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="05c19-127">Należy określić rekord skojarzenia jakości dla każdego odchylenia w procesie biznesowym.</span><span class="sxs-lookup"><span data-stu-id="05c19-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="05c19-128">Na przykład można skonfigurować skojarzenia jakości, które generuje zlecenia kontroli jakości podczas aktualizowania dokumentu przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="05c19-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="05c19-129">W zależności od ustawień planu wykonania, można zablokować sam proces uruchomienia, gdy jest otwarte zlecenie kontroli jakości, lub następne procesy, takie jak fakturowanie zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="05c19-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="05c19-130">**Uwaga:** jeśli są otwarte zlecenia kontroli jakości, ilości zapasów są automatycznie blokowane przed wydaniem.</span><span class="sxs-lookup"><span data-stu-id="05c19-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="05c19-131">W zależności od ustawienia **pełnego blokowanie** na stronie **Kontrola wyrywkowa pozycji** ilość jest ilością w zleceniu kontroli jakości lub ilością w wierszu dokumentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="05c19-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="05c19-132">W danym procesie biznesowym rekord skojarzenia jakości identyfikuje zdarzenie i warunki, dla których wygenerowano zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="05c19-133">Warunki mogą być właściwe dla oddziału lub firmy.</span><span class="sxs-lookup"><span data-stu-id="05c19-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="05c19-134">Zlecenia kontroli jakości, uwzględniające testy destrukcyjne mogą być generowane tylko wtedy, gdy istnieją dostępne zapasy dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="05c19-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="05c19-135">Poniższe przykłady przedstawiają możliwe sposoby określania rekordu skojarzenia jakości dla odchyleń w poszczególnych procesach biznesowych.</span><span class="sxs-lookup"><span data-stu-id="05c19-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="05c19-136">Dla każdego przykładu poniższa tabela podsumowuje zdarzenia i warunki zdefiniowane przez rekord skojarzenia jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="05c19-137">Typ odwołania</span><span class="sxs-lookup"><span data-stu-id="05c19-137">Reference type</span></span></th>
<th><span data-ttu-id="05c19-138">Typ zdarzenia</span><span class="sxs-lookup"><span data-stu-id="05c19-138">Event type</span></span></th>
<th><span data-ttu-id="05c19-139">Wykonanie</span><span class="sxs-lookup"><span data-stu-id="05c19-139">Execution</span></span></th>
<th><span data-ttu-id="05c19-140">Blokowanie zdarzeń</span><span class="sxs-lookup"><span data-stu-id="05c19-140">Event blocking</span></span></th>
<th><span data-ttu-id="05c19-141">Odwołanie do dokumentu</span><span class="sxs-lookup"><span data-stu-id="05c19-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="05c19-142">Zapasy</span><span class="sxs-lookup"><span data-stu-id="05c19-142">Inventory</span></span></td>
<td><span data-ttu-id="05c19-143">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="05c19-143">Not applicable</span></span></td>
<td><span data-ttu-id="05c19-144">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="05c19-144">Not applicable</span></span></td>
<td><span data-ttu-id="05c19-145">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-145">None</span></span></td>
<td><span data-ttu-id="05c19-146">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="05c19-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="05c19-147">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="05c19-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="05c19-148">Proces pobierania został zaplanowany</span><span class="sxs-lookup"><span data-stu-id="05c19-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="05c19-149">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-149">Before</span></span></td>
<td><span data-ttu-id="05c19-150">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="05c19-151">Określony identyfikator, Grupa lub Tylko wszystkie</span><span class="sxs-lookup"><span data-stu-id="05c19-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-152">Proces pobierania</span><span class="sxs-lookup"><span data-stu-id="05c19-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-153">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="05c19-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-154">Faktura</span><span class="sxs-lookup"><span data-stu-id="05c19-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="05c19-155">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="05c19-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-156">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-156">Before</span></span></td>
<td><span data-ttu-id="05c19-157">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-158">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="05c19-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-159">Faktura</span><span class="sxs-lookup"><span data-stu-id="05c19-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="05c19-160">Zakup</span><span class="sxs-lookup"><span data-stu-id="05c19-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="05c19-161">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="05c19-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="05c19-162">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-162">Before</span></span></td>
<td><span data-ttu-id="05c19-163">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-164">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="05c19-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-165">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="05c19-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-166">Faktura</span><span class="sxs-lookup"><span data-stu-id="05c19-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="05c19-167">Po</span><span class="sxs-lookup"><span data-stu-id="05c19-167">After</span></span></td>
<td><span data-ttu-id="05c19-168">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-169">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="05c19-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-170">Faktura</span><span class="sxs-lookup"><span data-stu-id="05c19-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="05c19-171">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="05c19-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-172">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="05c19-172">Not applicable</span></span></td>
<td><span data-ttu-id="05c19-173">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-174">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="05c19-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-175">Faktura</span><span class="sxs-lookup"><span data-stu-id="05c19-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="05c19-176">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="05c19-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-177">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-177">Before</span></span></td>
<td><span data-ttu-id="05c19-178">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-179">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="05c19-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-180">Faktura</span><span class="sxs-lookup"><span data-stu-id="05c19-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="05c19-181">Po</span><span class="sxs-lookup"><span data-stu-id="05c19-181">After</span></span></td>
<td><span data-ttu-id="05c19-182">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-183">Faktura</span><span class="sxs-lookup"><span data-stu-id="05c19-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="05c19-184">Produkcja</span><span class="sxs-lookup"><span data-stu-id="05c19-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-185">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="05c19-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-186">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="05c19-186">Not applicable</span></span></td>
<td><span data-ttu-id="05c19-187">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="05c19-188">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="05c19-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-189">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-190">Zamknij</span><span class="sxs-lookup"><span data-stu-id="05c19-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="05c19-191">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-192">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-192">Before</span></span></td>
<td><span data-ttu-id="05c19-193">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-194">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-195">Zamknij</span><span class="sxs-lookup"><span data-stu-id="05c19-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="05c19-196">Po</span><span class="sxs-lookup"><span data-stu-id="05c19-196">After</span></span></td>
<td><span data-ttu-id="05c19-197">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-198">Zamknij</span><span class="sxs-lookup"><span data-stu-id="05c19-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="05c19-199">Kwarantanna</span><span class="sxs-lookup"><span data-stu-id="05c19-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-200">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="05c19-201">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-201">Before</span></span></td>
<td><span data-ttu-id="05c19-202">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-203">Zamknij</span><span class="sxs-lookup"><span data-stu-id="05c19-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-204">Po</span><span class="sxs-lookup"><span data-stu-id="05c19-204">After</span></span></td>
<td><span data-ttu-id="05c19-205">Zamknij</span><span class="sxs-lookup"><span data-stu-id="05c19-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-206">Zamknij</span><span class="sxs-lookup"><span data-stu-id="05c19-206">End</span></span></td>
<td><span data-ttu-id="05c19-207">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-207">Before</span></span></td>
<td><span data-ttu-id="05c19-208">Zamknij</span><span class="sxs-lookup"><span data-stu-id="05c19-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="05c19-209">Operacja marszruty</span><span class="sxs-lookup"><span data-stu-id="05c19-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-210">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="05c19-211">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-211">Before</span></span></td>
<td><span data-ttu-id="05c19-212">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-213">Określony identyfikator, Grupa lub Wszystkie, oraz Specyficzne dla zasobu, Grupa lub Wszystkie</span><span class="sxs-lookup"><span data-stu-id="05c19-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-214">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-215">Po</span><span class="sxs-lookup"><span data-stu-id="05c19-215">After</span></span></td>
<td><span data-ttu-id="05c19-216">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="05c19-217">Wytwarzanie produktu towarzyszącego</span><span class="sxs-lookup"><span data-stu-id="05c19-217">Co-product production</span></span></td>
<td><span data-ttu-id="05c19-218">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="05c19-218">Registration</span></span></td>
<td><span data-ttu-id="05c19-219">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="05c19-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-220">Brak</span><span class="sxs-lookup"><span data-stu-id="05c19-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="05c19-221">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="05c19-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="05c19-222">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="05c19-222">Report as finished</span></span></td>
<td><span data-ttu-id="05c19-223">Przed</span><span class="sxs-lookup"><span data-stu-id="05c19-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-224">Po</span><span class="sxs-lookup"><span data-stu-id="05c19-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="05c19-225">Poniższa tabela zawiera więcej informacji na temat sposobu generowania zleceń kontroli jakości dla określonych typów procesów.</span><span class="sxs-lookup"><span data-stu-id="05c19-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="05c19-226">Typ procesu</span><span class="sxs-lookup"><span data-stu-id="05c19-226">Type of process</span></span></th>
<th><span data-ttu-id="05c19-227">Kiedy zlecenia kontroli jakości mogą być generowane automatycznie</span><span class="sxs-lookup"><span data-stu-id="05c19-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="05c19-228">Kiedy zlecenia kontroli jakości mogą być generowane, jeśli wymagane są testy destrukcyjne</span><span class="sxs-lookup"><span data-stu-id="05c19-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="05c19-229">Informacje o warunku</span><span class="sxs-lookup"><span data-stu-id="05c19-229">Condition information</span></span></th>
<th><span data-ttu-id="05c19-230">Informacje generowane ręcznie</span><span class="sxs-lookup"><span data-stu-id="05c19-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="05c19-231">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="05c19-231">Purchase order</span></span></td>
<td><span data-ttu-id="05c19-232">Przed zaksięgowaniem lub po zaksięgowaniu listy przychodu lub dokumentu przyjęcia produktu dla odebranego materiału</span><span class="sxs-lookup"><span data-stu-id="05c19-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="05c19-233">Po odebraniu i zaksięgowaniu dokumentu przyjęcia produktów dla materiału, ponieważ materiał musi być dostępny do testów destrukcyjnych</span><span class="sxs-lookup"><span data-stu-id="05c19-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="05c19-234">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="05c19-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="05c19-235">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia zakupu, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="05c19-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-236">Zlecenie kwarantanny</span><span class="sxs-lookup"><span data-stu-id="05c19-236">Quarantine order</span></span></td>
<td><span data-ttu-id="05c19-237">Przed lub po zgłoszeniu zlecenia kwarantanny jako zakończonego lub gotowego</span><span class="sxs-lookup"><span data-stu-id="05c19-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="05c19-238">Nie można generować zleceń kontroli jakości wymagających testów destrukcyjnych.</span><span class="sxs-lookup"><span data-stu-id="05c19-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="05c19-239">Zakłada się, że funkcja zlecenia kwarantanny obsługuje dyspozycje niszczonego materiału.</span><span class="sxs-lookup"><span data-stu-id="05c19-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="05c19-240">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="05c19-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="05c19-241">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia kwarantanny, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="05c19-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-242">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="05c19-242">Sales order</span></span></td>
<td><span data-ttu-id="05c19-243">Przed zaplanowanym procesem pobrania lub aktualizacją dokumentu dostawy dla wysłanych pozycji</span><span class="sxs-lookup"><span data-stu-id="05c19-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="05c19-244">Na dowolnym z etapów</span><span class="sxs-lookup"><span data-stu-id="05c19-244">At any step</span></span></td>
<td><span data-ttu-id="05c19-245">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub odbiorcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="05c19-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="05c19-246">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia sprzedaży, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="05c19-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-247">Zlecenie produkcyjne</span><span class="sxs-lookup"><span data-stu-id="05c19-247">Production order</span></span></td>
<td><span data-ttu-id="05c19-248">Przed zgłoszeniem lub po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="05c19-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="05c19-249">Po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="05c19-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="05c19-250">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="05c19-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="05c19-251">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia produkcyjnego, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="05c19-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-252">Zlecenie produkcyjne, które ma operację marszruty</span><span class="sxs-lookup"><span data-stu-id="05c19-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="05c19-253">Przed zakończeniem lub po zakończeniu raportu dla operacji</span><span class="sxs-lookup"><span data-stu-id="05c19-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="05c19-254">Po zakończeniu zgłaszania produkcji dla ostatniej operacji</span><span class="sxs-lookup"><span data-stu-id="05c19-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="05c19-255">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub zasobem operacyjnym, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="05c19-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="05c19-256">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy operacji marszruty, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="05c19-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="05c19-257">Zapasy</span><span class="sxs-lookup"><span data-stu-id="05c19-257">Inventory</span></span></td>
<td><span data-ttu-id="05c19-258">Zlecenie kontroli jakości nie może być generowane automatycznie dla transakcji w arkuszu magazynowym lub dla transakcji zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="05c19-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="05c19-259">Zlecenie kontroli jakości musi być tworzone ręcznie dla ilości zapasów towaru.</span><span class="sxs-lookup"><span data-stu-id="05c19-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="05c19-260">Fizyczne dostępne zapasy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="05c19-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="05c19-261">Strony zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="05c19-261">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05c19-262">Strona</span><span class="sxs-lookup"><span data-stu-id="05c19-262">Page</span></span></th>
<th><span data-ttu-id="05c19-263">Opis</span><span class="sxs-lookup"><span data-stu-id="05c19-263">Description</span></span></th>
<th><span data-ttu-id="05c19-264">Przykład</span><span class="sxs-lookup"><span data-stu-id="05c19-264">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="05c19-265">Powiązania jakości</span><span class="sxs-lookup"><span data-stu-id="05c19-265">Quality associations</span></span></td>
<td><span data-ttu-id="05c19-266">Zobacz poprzednie części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="05c19-266">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="05c19-267">Powiązanie jakości określa wszystkie poniższe informacje dla generowanego zlecenia kontroli jakości:</span><span class="sxs-lookup"><span data-stu-id="05c19-267">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="05c19-268">Zdarzenie transakcji</span><span class="sxs-lookup"><span data-stu-id="05c19-268">The transaction event</span></span></li>
<li><span data-ttu-id="05c19-269">Zestaw testów, które należy wykonać na towarach</span><span class="sxs-lookup"><span data-stu-id="05c19-269">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="05c19-270">AQL</span><span class="sxs-lookup"><span data-stu-id="05c19-270">The AQL</span></span></li>
<li><span data-ttu-id="05c19-271">Plan pobierania próbek</span><span class="sxs-lookup"><span data-stu-id="05c19-271">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="05c19-272">Należy określić skojarzenie jakości dla każdego odchylenia w procesie biznesowym, które wymaga automatycznego generowania zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-272">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="05c19-273">Na przykład: zlecenie kontroli jakości może być generowane w procesie biznesowym związanym z zamówieniami zakupu, zleceniami kwarantanny, zamówieniami sprzedaży i zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="05c19-273">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="05c19-274">Testy</span><span class="sxs-lookup"><span data-stu-id="05c19-274">Tests</span></span></td>
<td><span data-ttu-id="05c19-275">Ta strona służy do definiowania i wyświetlania poszczególnych testów decydujących, czy produkty są zgodne ze specyfikacjami jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-275">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="05c19-276">Do grupy testowej można przypisać jeden lub więcej testów.</span><span class="sxs-lookup"><span data-stu-id="05c19-276">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="05c19-277">W takim przypadku określa się również informacje właściwe dla danego testu, takie jak akceptowalne wartości pomiaru.</span><span class="sxs-lookup"><span data-stu-id="05c19-277">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="05c19-278">Wartości pomiaru są używane w testach ilościowych, a zmienne testowe są używane w testach jakościowych.</span><span class="sxs-lookup"><span data-stu-id="05c19-278">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="05c19-279">Testy ilościowe mogą być typu <strong>Całkowity</strong> lub <strong>Ułamek</strong> i mają przypisaną jednostkę miary.</span><span class="sxs-lookup"><span data-stu-id="05c19-279">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="05c19-280">Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="05c19-280">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="05c19-281">Test jakościowy ma przypisany typ <strong>Opcja</strong>.</span><span class="sxs-lookup"><span data-stu-id="05c19-281">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="05c19-282">Testy jakości wymagają dodatkowych informacji konfiguracyjnych dotyczących zmiennej testowej i jej wyliczonych opcji.</span><span class="sxs-lookup"><span data-stu-id="05c19-282">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="05c19-283">Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="05c19-283">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="05c19-284">Firma produkcyjna wykonuje dwa testy na zakupionym materiale, w tym test ilości dotyczący jakości materiału i test jakości dotyczący uszkodzenia opakowania.</span><span class="sxs-lookup"><span data-stu-id="05c19-284">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="05c19-285">Firma definiuje dodatkowe informacje na temat testu jakości w celu określenia zmiennej testowej (uszkodzone opakowanie) i jej wartości wynikowe.</span><span class="sxs-lookup"><span data-stu-id="05c19-285">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="05c19-286">Firma używa strony <strong>Grupy testowe</strong> do przypisania dwóch testów do grupy testowej i do określenia informacji specyficznych dla testu.</span><span class="sxs-lookup"><span data-stu-id="05c19-286">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="05c19-287">Grupa testów jest przypisywana do zlecenia kontroli jakości, dzięki czemu firma może raportować wyniki testu dla dwóch testów.</span><span class="sxs-lookup"><span data-stu-id="05c19-287">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="05c19-288">Grupy testowe</span><span class="sxs-lookup"><span data-stu-id="05c19-288">Test groups</span></span></td>
<td><span data-ttu-id="05c19-289">Strona ta służy do konfigurowania, edytowania i wyświetlania grup testowych oraz testów indywidualnych przypisanych do danej grupy testowej.</span><span class="sxs-lookup"><span data-stu-id="05c19-289">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="05c19-290">W górnym okienku wyświetlane są grupy testowe, a w dolnym — testy przypisane do wybranej grupy testowej.</span><span class="sxs-lookup"><span data-stu-id="05c19-290">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="05c19-291">Do grupy testowej można przypisać różne zasady, w tym plan próbkowania, akceptowany poziom jakości i wymaganie dotyczące testowania destrukcyjnego.</span><span class="sxs-lookup"><span data-stu-id="05c19-291">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="05c19-292">Po przypisaniu każdego z tych testów do grupy testowej, można zdefiniować dodatkowe informacje, takie jak sekwencje, dokumenty i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="05c19-292">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="05c19-293">W przypadku testu ilościowego zdefiniowane informacje zawierają również akceptowalne wartości pomiaru.</span><span class="sxs-lookup"><span data-stu-id="05c19-293">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="05c19-294">W przypadku testu jakościowego informacje zmienną testową i domyślny rezultat.</span><span class="sxs-lookup"><span data-stu-id="05c19-294">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="05c19-295">Za pomocą grupy testów przypisanej do zlecenia kontroli jakości określa się domyślny zestaw testów, które muszą zostać przeprowadzone odnośnie do określonego towaru.</span><span class="sxs-lookup"><span data-stu-id="05c19-295">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="05c19-296">Ale mnożna dodawać, usuwać lub zmieniać testy w zleceniu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-296">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="05c19-297">Wyniki testu są raportowane dla każdego testu w zleceniu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-297">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="05c19-298">W przedsiębiorstwie produkcyjnym zdefiniowano grupę testową dla każdego odchylenia dotyczącego zasad kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-298">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="05c19-299">Poszczególne grupy testowe odpowiadają różnym planom próbkowania, seriom testów, które muszą być wykonywane razem, akceptowanemu poziomowi jakości i innym czynnikom.</span><span class="sxs-lookup"><span data-stu-id="05c19-299">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="05c19-300">W testach ilościowych są również różnice we właściwych wartościach pomiaru.</span><span class="sxs-lookup"><span data-stu-id="05c19-300">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="05c19-301">Aby wymusić wytyczne co do jakości, firma przypisuje grupę testową do każdej reguły w celu automatycznego generowania zleceń kontroli jakości na stronie <strong>powiązań jakości</strong> i przypisuje grupę testową do ręcznie tworzonych zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-301">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="05c19-302">Grupy jakości pozycji</span><span class="sxs-lookup"><span data-stu-id="05c19-302">Item quality groups</span></span></td>
<td><span data-ttu-id="05c19-303">Ta strona umożliwia konfigurowanie, edycję i wyświetlanie towarów przypisanych do grupy jakości lub grup jakości przypisanych do towaru.</span><span class="sxs-lookup"><span data-stu-id="05c19-303">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="05c19-304">Grupa jakości reprezentuje wspólne wymagania dotyczące testowania towarów.</span><span class="sxs-lookup"><span data-stu-id="05c19-304">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="05c19-305">Po zdefiniowaniu wymogów testu na stronie <strong>Grupy testowe</strong> można zdefiniować reguły automatycznego generowania zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-305">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="05c19-306">Aby uprościć proces, nie definiuje się reguł dla poszczególnych towarów.</span><span class="sxs-lookup"><span data-stu-id="05c19-306">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="05c19-307">Zamiast tego definiuje się reguły dla grupy jakości na stronie <strong>powiązań jakości</strong>.</span><span class="sxs-lookup"><span data-stu-id="05c19-307">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="05c19-308">Można również użyć strony <strong>Grupy jakości towarów</strong> dla wybranej grupy jakości w celu przypisania odpowiednich towarów do tej grupy.</span><span class="sxs-lookup"><span data-stu-id="05c19-308">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="05c19-309">Można również użyć strony <strong>Grupy jakości towarów</strong> dla wybranego towaru w celu przypisania odpowiednich grup jakości do danego towaru.</span><span class="sxs-lookup"><span data-stu-id="05c19-309">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="05c19-310">Firma produkcyjna nabywa kilka surowców mających te same wymagania dotyczące testowania przed zbliżającą się inspekcją.</span><span class="sxs-lookup"><span data-stu-id="05c19-310">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="05c19-311">Firma definiuje grupę jakości, a następnie przypisuje do tej grupy kody towarów, które są skojarzone z surowcami.</span><span class="sxs-lookup"><span data-stu-id="05c19-311">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="05c19-312">Później firma nabywa nowy typ surowca, który ma te same wymagania dotyczące testowania.</span><span class="sxs-lookup"><span data-stu-id="05c19-312">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="05c19-313">Zamiast konfigurować nowe wymagania dotyczące nowego materiału, firma dodaje kod towaru dla nowego materiału do istniejącej grupy jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-313">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="05c19-314">Ta sama firma produkuje również towary mające te same wymagania dotyczące testowania produkcji i wysyła towary mające te same wymagania dotyczące przeprowadzania testów przed wysyłką.</span><span class="sxs-lookup"><span data-stu-id="05c19-314">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="05c19-315">Firma definiuje dwie dodatkowe grupy jakości i przypisuje do każdej z nich odpowiednie kody towarów.</span><span class="sxs-lookup"><span data-stu-id="05c19-315">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="05c19-316">Zmienne testowe</span><span class="sxs-lookup"><span data-stu-id="05c19-316">Test variables</span></span></td>
<td><span data-ttu-id="05c19-317">Ta strona umożliwia definiowanie i wyświetlanie zmiennych skojarzonych z testem jakościowym.</span><span class="sxs-lookup"><span data-stu-id="05c19-317">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="05c19-318">Dla każdej zmiennej można zdefiniować wyliczenie wyników reprezentujące możliwe opcje.</span><span class="sxs-lookup"><span data-stu-id="05c19-318">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="05c19-319">Testy definiuje się na stronie <strong>Testy</strong>.</span><span class="sxs-lookup"><span data-stu-id="05c19-319">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="05c19-320">W przypadku testów jakościowych trzeba ustawić typ testu jako <strong>Opcja</strong>.</span><span class="sxs-lookup"><span data-stu-id="05c19-320">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="05c19-321">Strona <strong>Grupy testowe</strong> służy do przypisywania zmiennej testowej do konkretnego testu.</span><span class="sxs-lookup"><span data-stu-id="05c19-321">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="05c19-322">Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie.</span><span class="sxs-lookup"><span data-stu-id="05c19-322">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="05c19-323">Ten test inspekcji zawiera kilka zmiennych.</span><span class="sxs-lookup"><span data-stu-id="05c19-323">This inspection test has several variables.</span></span> <span data-ttu-id="05c19-324">Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły.</span><span class="sxs-lookup"><span data-stu-id="05c19-324">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="05c19-325">Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="05c19-325">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="05c19-326">Wyniki zmiennych testowych.</span><span class="sxs-lookup"><span data-stu-id="05c19-326">Test variable outcomes</span></span></td>
<td><span data-ttu-id="05c19-327">Ta strona służy do konfigurowania, edytowania i wyświetlania możliwych wartości zmiennej testowej skojarzonej z testem jakości.</span><span class="sxs-lookup"><span data-stu-id="05c19-327">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="05c19-328">Dla każdego wyniku należy przypisać stan <strong>powodzenie</strong> lub <strong>niepowodzenie</strong>.</span><span class="sxs-lookup"><span data-stu-id="05c19-328">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="05c19-329">Należy zdefiniować zmienną i jej wyniki dla każdego testu jakości zdefiniowanego na stronie <strong>Testy</strong>.</span><span class="sxs-lookup"><span data-stu-id="05c19-329">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="05c19-330">(Dla testów jakościowych ustawiono typ testu <strong>Opcja</strong> na stronie <strong>Testy</strong>). Strona <strong>Grupy testów</strong> służy do przypisywania zmiennej testowej i domyślnego wyniku do konkretnego testu.</span><span class="sxs-lookup"><span data-stu-id="05c19-330">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="05c19-331">Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie.</span><span class="sxs-lookup"><span data-stu-id="05c19-331">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="05c19-332">Ten test inspekcji zawiera kilka zmiennych.</span><span class="sxs-lookup"><span data-stu-id="05c19-332">This inspection test has of several variables.</span></span> <span data-ttu-id="05c19-333">Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły.</span><span class="sxs-lookup"><span data-stu-id="05c19-333">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="05c19-334">Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="05c19-334">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="05c19-335">Każdy wynik ma przypisany stan <strong>powodzenie</strong> lub <strong>niepowodzenie</strong>.</span><span class="sxs-lookup"><span data-stu-id="05c19-335">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="05c19-336">Podczas sprawdzania poszczególnych zmiennych, kontroler raportuje wyniki testów, zaznaczając jeden z wyników.</span><span class="sxs-lookup"><span data-stu-id="05c19-336">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="05c19-337">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="05c19-337">Additional resources</span></span>
--------

[<span data-ttu-id="05c19-338">Procesy zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="05c19-338">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="05c19-339">Włączanie zarządzania niezgodnościami</span><span class="sxs-lookup"><span data-stu-id="05c19-339">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)

