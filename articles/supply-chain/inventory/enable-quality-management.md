---
title: Omówienie zarządzanie jakością
description: W tym temacie opisano, jak za pomocą funkcji zarządzania jakością w Dynamics 365 Supply Chain Management poprawiać jakość produktów w łańcuchu dostaw.
author: perlynne
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65858838b0fbb245a9330fab4e3b65b36a9eb944
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219372"
---
# <a name="quality-management-overview"></a><span data-ttu-id="37ef3-103">Omówienie zarządzanie jakością</span><span class="sxs-lookup"><span data-stu-id="37ef3-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37ef3-104">W tym temacie opisano, jak za pomocą funkcji zarządzania jakością w Dynamics 365 Supply Chain Management poprawiać jakość produktów w łańcuchu dostaw.</span><span class="sxs-lookup"><span data-stu-id="37ef3-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="37ef3-105">Zarządzanie jakością pomaga przy zarządzaniu czasem przetwarzania, kiedy masz do czynienia z produktami niespełniającymi norm, bez względu na pochodzenie tych produktów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="37ef3-106">Ze względu na to, że typy diagnostyki są powiązane z raportowaniem korekt, rozwiązanie Supply Chain Management może zaplanować zadania naprawiania problemów i zapobiegania ich ponownemu występowaniu.</span><span class="sxs-lookup"><span data-stu-id="37ef3-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="37ef3-107">Oprócz funkcji związanych z zarządzaniem brakiem zgodności zarządzanie jakością zawiera funkcje monitorowania błędów według typu problemu (łącznie z błędami wewnętrznymi) i identyfikowania rozwiązań krótko- i długoterminowych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="37ef3-108">Statystyki kluczowych wskaźników wydajności (KPI) pokazują historię wcześniejszych problemów z brakiem zgodności i rozwiązania, które zostały zastosowane do ich korekty.</span><span class="sxs-lookup"><span data-stu-id="37ef3-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="37ef3-109">Korzystając z danych historycznych można sprawdzić skuteczność pomiarów jakości, które zostały wcześniej przeprowadzone, i określić odpowiednie rozwiązania na przyszłość.</span><span class="sxs-lookup"><span data-stu-id="37ef3-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="37ef3-110">Po skonfigurowaniu powiązania jakości rozwiązanie Supply Chain Management może generować zlecania kontroli jakości dla różnych procesów biznesowych, zdarzenia i warunki.</span><span class="sxs-lookup"><span data-stu-id="37ef3-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="37ef3-111">Skojarzenia jakości mogą obejmować określone pozycje, grupy towarów lub wszystkie pozycje.</span><span class="sxs-lookup"><span data-stu-id="37ef3-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="37ef3-112">Przykłady korzystania z funkcji zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="37ef3-112">Examples of the use of quality management</span></span>
<span data-ttu-id="37ef3-113">Zarządzanie jakością jest elastyczne i może być implementowane na różne sposoby, aby spełnić wymagania określonych poziomów operacji łańcucha dostaw.</span><span class="sxs-lookup"><span data-stu-id="37ef3-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="37ef3-114">Poniższe przykłady ilustrują możliwe wykorzystanie tych funkcji:</span><span class="sxs-lookup"><span data-stu-id="37ef3-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="37ef3-115">Automatyczne uruchamianie procesu kontroli jakości, na podstawie wstępnie zdefiniowanych kryteriów (przy rejestracji magazynu zamówienia zakupu od określonego dostawcy).</span><span class="sxs-lookup"><span data-stu-id="37ef3-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="37ef3-116">Blokowanie zapasów podczas inspekcji, aby zapobiec używaniu niezatwierdzonych zapasów (całkowite blokowanie ilości zamówienia zakupu).</span><span class="sxs-lookup"><span data-stu-id="37ef3-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="37ef3-117">Używanie kontroli wyrywkowej pozycji w ramach powiązania jakości do określenia kwoty bieżących zapasów fizycznych, które muszą być poddane inspekcji.</span><span class="sxs-lookup"><span data-stu-id="37ef3-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="37ef3-118">Kontrola wyrywkowa może dotyczyć stałej ilości lub części określonej procentowo lub pełnego numeru identyfikacyjnego.</span><span class="sxs-lookup"><span data-stu-id="37ef3-118">Sampling can be based on fixed quantities, a percentage, or full license plate.</span></span>

> [!NOTE]
> <span data-ttu-id="37ef3-119">Funkcja _Zarządzanie jakością dla procesów magazynowych_ rozszerza możliwości zarządzania jakością.</span><span class="sxs-lookup"><span data-stu-id="37ef3-119">The _Quality management for warehouse processes_ feature extends the capabilities of quality management.</span></span> <span data-ttu-id="37ef3-120">Jeśli ta funkcja jest używana, zobacz [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md), aby przejrzeć przykłady sposobu działania funkcji zarządzania jakością, gdy jest ona włączona.</span><span class="sxs-lookup"><span data-stu-id="37ef3-120">If you are using this feature, then see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md) for examples of how quality management works when it's enabled.</span></span>

-   <span data-ttu-id="37ef3-121">Tworzenie zleceń kontroli jakości dla przyjęć częściowych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-121">Create quality orders for partial receipts.</span></span> <span data-ttu-id="37ef3-122">Aby utworzyć zlecenie kontroli jakości oparte na ilości fizycznie przyjętej względem zamówienia, należy zaznaczyć pole wyboru **Dla zaktualizowanej ilości** w formularzu **Kontrola wyrywkowa towarów**.</span><span class="sxs-lookup"><span data-stu-id="37ef3-122">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="37ef3-123">Tworzenie typów testów zawierających minimalne, maksymalne i docelowe wartości testu, i testowanie jakościowe vs ilościowe ze wstępnie zdefiniowanymi wynikami weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="37ef3-123">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="37ef3-124">Określanie akceptowanego poziomu jakości (AQL) do kontrolowania tolerancji pomiaru jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-124">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="37ef3-125">Określanie zasobów wymaganych do operacji inspekcji, takich jak obszar testowy i przyrządy testowe.</span><span class="sxs-lookup"><span data-stu-id="37ef3-125">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="37ef3-126">Korzystanie ze skojarzeń jakości</span><span class="sxs-lookup"><span data-stu-id="37ef3-126">Working with quality associations</span></span>
<span data-ttu-id="37ef3-127">Proces biznesowy, który używa skojarzeń jakości może być powiązany z różnymi dokumentami źródłowymi, takimi jak zamówienia zakupu, zamówienia sprzedaży lub zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="37ef3-127">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="37ef3-128">Poszczególne rekordy skojarzenia jakości określają serie testów, akceptowany poziom jakości i plan próbkowania dotyczące generowanych zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-128">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="37ef3-129">Należy określić rekord skojarzenia jakości dla każdego odchylenia w procesie biznesowym.</span><span class="sxs-lookup"><span data-stu-id="37ef3-129">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="37ef3-130">Na przykład można skonfigurować skojarzenia jakości, które generuje zlecenia kontroli jakości podczas aktualizowania dokumentu przyjęcia produktów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-130">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="37ef3-131">W zależności od ustawień planu wykonania, można zablokować sam proces uruchomienia, gdy jest otwarte zlecenie kontroli jakości, lub następne procesy, takie jak fakturowanie zamówień zakupu.</span><span class="sxs-lookup"><span data-stu-id="37ef3-131">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="37ef3-132">**Uwaga:** jeśli są otwarte zlecenia kontroli jakości, ilości zapasów są automatycznie blokowane przed wydaniem.</span><span class="sxs-lookup"><span data-stu-id="37ef3-132">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="37ef3-133">W zależności od ustawienia **pełnego blokowanie** na stronie **Kontrola wyrywkowa pozycji** ilość jest ilością w zleceniu kontroli jakości lub ilością w wierszu dokumentu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="37ef3-133">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="37ef3-134">W danym procesie biznesowym rekord skojarzenia jakości identyfikuje zdarzenie i warunki, dla których wygenerowano zlecenie kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-134">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="37ef3-135">Warunki mogą być właściwe dla oddziału lub firmy.</span><span class="sxs-lookup"><span data-stu-id="37ef3-135">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="37ef3-136">Zlecenia kontroli jakości, uwzględniające testy destrukcyjne mogą być generowane tylko wtedy, gdy istnieją dostępne zapasy dla zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="37ef3-136">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="37ef3-137">Poniższe przykłady przedstawiają możliwe sposoby określania rekordu skojarzenia jakości dla odchyleń w poszczególnych procesach biznesowych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-137">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="37ef3-138">Dla każdego przykładu poniższa tabela podsumowuje zdarzenia i warunki zdefiniowane przez rekord skojarzenia jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-138">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="37ef3-139">Typ odwołania</span><span class="sxs-lookup"><span data-stu-id="37ef3-139">Reference type</span></span></th>
<th><span data-ttu-id="37ef3-140">Typ zdarzenia</span><span class="sxs-lookup"><span data-stu-id="37ef3-140">Event type</span></span></th>
<th><span data-ttu-id="37ef3-141">Wykonanie</span><span class="sxs-lookup"><span data-stu-id="37ef3-141">Execution</span></span></th>
<th><span data-ttu-id="37ef3-142">Blokowanie zdarzeń</span><span class="sxs-lookup"><span data-stu-id="37ef3-142">Event blocking</span></span></th>
<th><span data-ttu-id="37ef3-143">Odwołanie do dokumentu</span><span class="sxs-lookup"><span data-stu-id="37ef3-143">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="37ef3-144">Zapasy</span><span class="sxs-lookup"><span data-stu-id="37ef3-144">Inventory</span></span></td>
<td><span data-ttu-id="37ef3-145">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="37ef3-145">Not applicable</span></span></td>
<td><span data-ttu-id="37ef3-146">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="37ef3-146">Not applicable</span></span></td>
<td><span data-ttu-id="37ef3-147">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-147">None</span></span></td>
<td><span data-ttu-id="37ef3-148">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="37ef3-148">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="37ef3-149">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="37ef3-149">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="37ef3-150">Proces pobierania został zaplanowany</span><span class="sxs-lookup"><span data-stu-id="37ef3-150">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="37ef3-151">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-151">Before</span></span></td>
<td><span data-ttu-id="37ef3-152">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-152">None</span></span></td>
<td rowspan="22"><span data-ttu-id="37ef3-153">Określony identyfikator, Grupa lub Tylko wszystkie</span><span class="sxs-lookup"><span data-stu-id="37ef3-153">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-154">Proces pobierania</span><span class="sxs-lookup"><span data-stu-id="37ef3-154">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-155">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="37ef3-155">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-156">Faktura</span><span class="sxs-lookup"><span data-stu-id="37ef3-156">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="37ef3-157">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="37ef3-157">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-158">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-158">Before</span></span></td>
<td><span data-ttu-id="37ef3-159">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-160">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="37ef3-160">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-161">Faktura</span><span class="sxs-lookup"><span data-stu-id="37ef3-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="37ef3-162">Zakup</span><span class="sxs-lookup"><span data-stu-id="37ef3-162">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="37ef3-163">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="37ef3-163">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="37ef3-164">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-164">Before</span></span></td>
<td><span data-ttu-id="37ef3-165">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-165">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-166">Lista przychodu</span><span class="sxs-lookup"><span data-stu-id="37ef3-166">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-167">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="37ef3-167">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-168">Faktura</span><span class="sxs-lookup"><span data-stu-id="37ef3-168">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="37ef3-169">Po</span><span class="sxs-lookup"><span data-stu-id="37ef3-169">After</span></span></td>
<td><span data-ttu-id="37ef3-170">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-170">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-171">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="37ef3-171">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-172">Faktura</span><span class="sxs-lookup"><span data-stu-id="37ef3-172">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="37ef3-173">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="37ef3-173">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-174">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="37ef3-174">Not applicable</span></span></td>
<td><span data-ttu-id="37ef3-175">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-175">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-176">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="37ef3-176">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-177">Faktura</span><span class="sxs-lookup"><span data-stu-id="37ef3-177">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="37ef3-178">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="37ef3-178">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-179">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-179">Before</span></span></td>
<td><span data-ttu-id="37ef3-180">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-180">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-181">Dokument przyjęcia produktów</span><span class="sxs-lookup"><span data-stu-id="37ef3-181">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-182">Faktura</span><span class="sxs-lookup"><span data-stu-id="37ef3-182">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="37ef3-183">Po</span><span class="sxs-lookup"><span data-stu-id="37ef3-183">After</span></span></td>
<td><span data-ttu-id="37ef3-184">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-185">Faktura</span><span class="sxs-lookup"><span data-stu-id="37ef3-185">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="37ef3-186">Produkcja</span><span class="sxs-lookup"><span data-stu-id="37ef3-186">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-187">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="37ef3-187">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-188">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="37ef3-188">Not applicable</span></span></td>
<td><span data-ttu-id="37ef3-189">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-189">None</span></span></td>
<td rowspan="12"><span data-ttu-id="37ef3-190">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="37ef3-190">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-191">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-191">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-192">Zamknij</span><span class="sxs-lookup"><span data-stu-id="37ef3-192">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="37ef3-193">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-193">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-194">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-194">Before</span></span></td>
<td><span data-ttu-id="37ef3-195">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-195">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-196">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-196">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-197">Zamknij</span><span class="sxs-lookup"><span data-stu-id="37ef3-197">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="37ef3-198">Po</span><span class="sxs-lookup"><span data-stu-id="37ef3-198">After</span></span></td>
<td><span data-ttu-id="37ef3-199">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-199">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-200">Zamknij</span><span class="sxs-lookup"><span data-stu-id="37ef3-200">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="37ef3-201">Kwarantanna</span><span class="sxs-lookup"><span data-stu-id="37ef3-201">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-202">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-202">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="37ef3-203">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-203">Before</span></span></td>
<td><span data-ttu-id="37ef3-204">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-204">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-205">Zamknij</span><span class="sxs-lookup"><span data-stu-id="37ef3-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-206">Po</span><span class="sxs-lookup"><span data-stu-id="37ef3-206">After</span></span></td>
<td><span data-ttu-id="37ef3-207">Zamknij</span><span class="sxs-lookup"><span data-stu-id="37ef3-207">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-208">Zamknij</span><span class="sxs-lookup"><span data-stu-id="37ef3-208">End</span></span></td>
<td><span data-ttu-id="37ef3-209">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-209">Before</span></span></td>
<td><span data-ttu-id="37ef3-210">Zamknij</span><span class="sxs-lookup"><span data-stu-id="37ef3-210">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="37ef3-211">Operacja marszruty</span><span class="sxs-lookup"><span data-stu-id="37ef3-211">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-212">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-212">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="37ef3-213">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-213">Before</span></span></td>
<td><span data-ttu-id="37ef3-214">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-214">None</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-215">Określony identyfikator, Grupa lub Wszystkie, oraz Specyficzne dla zasobu, Grupa lub Wszystkie</span><span class="sxs-lookup"><span data-stu-id="37ef3-215">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-216">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-216">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-217">Po</span><span class="sxs-lookup"><span data-stu-id="37ef3-217">After</span></span></td>
<td><span data-ttu-id="37ef3-218">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-218">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="37ef3-219">Wytwarzanie produktu towarzyszącego</span><span class="sxs-lookup"><span data-stu-id="37ef3-219">Co-product production</span></span></td>
<td><span data-ttu-id="37ef3-220">Rejestracja</span><span class="sxs-lookup"><span data-stu-id="37ef3-220">Registration</span></span></td>
<td><span data-ttu-id="37ef3-221">Nie dotyczy</span><span class="sxs-lookup"><span data-stu-id="37ef3-221">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-222">Brak</span><span class="sxs-lookup"><span data-stu-id="37ef3-222">None</span></span></td>
<td rowspan="3"><span data-ttu-id="37ef3-223">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="37ef3-223">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="37ef3-224">Zgłoszenie wyrobów gotowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-224">Report as finished</span></span></td>
<td><span data-ttu-id="37ef3-225">Przed</span><span class="sxs-lookup"><span data-stu-id="37ef3-225">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-226">Po</span><span class="sxs-lookup"><span data-stu-id="37ef3-226">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="37ef3-227">Poniższa tabela zawiera więcej informacji na temat sposobu generowania zleceń kontroli jakości dla określonych typów procesów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-227">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="37ef3-228">Typ procesu</span><span class="sxs-lookup"><span data-stu-id="37ef3-228">Type of process</span></span></th>
<th><span data-ttu-id="37ef3-229">Kiedy zlecenia kontroli jakości mogą być generowane automatycznie</span><span class="sxs-lookup"><span data-stu-id="37ef3-229">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="37ef3-230">Kiedy zlecenia kontroli jakości mogą być generowane, jeśli wymagane są testy destrukcyjne</span><span class="sxs-lookup"><span data-stu-id="37ef3-230">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="37ef3-231">Informacje o warunku</span><span class="sxs-lookup"><span data-stu-id="37ef3-231">Condition information</span></span></th>
<th><span data-ttu-id="37ef3-232">Informacje generowane ręcznie</span><span class="sxs-lookup"><span data-stu-id="37ef3-232">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="37ef3-233">Zamówienie zakupu</span><span class="sxs-lookup"><span data-stu-id="37ef3-233">Purchase order</span></span></td>
<td><span data-ttu-id="37ef3-234">Przed zaksięgowaniem lub po zaksięgowaniu listy przychodu lub dokumentu przyjęcia produktu dla odebranego materiału</span><span class="sxs-lookup"><span data-stu-id="37ef3-234">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="37ef3-235">Po odebraniu i zaksięgowaniu dokumentu przyjęcia produktów dla materiału, ponieważ materiał musi być dostępny do testów destrukcyjnych</span><span class="sxs-lookup"><span data-stu-id="37ef3-235">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="37ef3-236">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="37ef3-236">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="37ef3-237">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia zakupu, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="37ef3-237">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-238">Zlecenie kwarantanny</span><span class="sxs-lookup"><span data-stu-id="37ef3-238">Quarantine order</span></span></td>
<td><span data-ttu-id="37ef3-239">Przed lub po zgłoszeniu zlecenia kwarantanny jako zakończonego lub gotowego</span><span class="sxs-lookup"><span data-stu-id="37ef3-239">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="37ef3-240">Nie można generować zleceń kontroli jakości wymagających testów destrukcyjnych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-240">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="37ef3-241">Zakłada się, że funkcja zlecenia kwarantanny obsługuje dyspozycje niszczonego materiału.</span><span class="sxs-lookup"><span data-stu-id="37ef3-241">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="37ef3-242">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub dostawcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="37ef3-242">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="37ef3-243">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia kwarantanny, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="37ef3-243">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-244">Zamówienie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="37ef3-244">Sales order</span></span></td>
<td><span data-ttu-id="37ef3-245">Przed zaplanowanym procesem pobrania lub aktualizacją dokumentu dostawy dla wysłanych pozycji</span><span class="sxs-lookup"><span data-stu-id="37ef3-245">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="37ef3-246">Na dowolnym z etapów</span><span class="sxs-lookup"><span data-stu-id="37ef3-246">At any step</span></span></td>
<td><span data-ttu-id="37ef3-247">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub odbiorcą, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="37ef3-247">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="37ef3-248">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zamówienia sprzedaży, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="37ef3-248">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-249">Zlecenie produkcyjne</span><span class="sxs-lookup"><span data-stu-id="37ef3-249">Production order</span></span></td>
<td><span data-ttu-id="37ef3-250">Przed zgłoszeniem lub po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="37ef3-250">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="37ef3-251">Po zgłoszeniu ilości wyrobów gotowych dla zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="37ef3-251">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="37ef3-252">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="37ef3-252">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="37ef3-253">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy zlecenia produkcyjnego, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="37ef3-253">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-254">Zlecenie produkcyjne, które ma operację marszruty</span><span class="sxs-lookup"><span data-stu-id="37ef3-254">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="37ef3-255">Przed zakończeniem lub po zakończeniu raportu dla operacji</span><span class="sxs-lookup"><span data-stu-id="37ef3-255">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="37ef3-256">Po zakończeniu zgłaszania produkcji dla ostatniej operacji</span><span class="sxs-lookup"><span data-stu-id="37ef3-256">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="37ef3-257">Wymaganie zlecenia kontroli jakości może być związane z określonym oddziałem, towarem lub zasobem operacyjnym, lub kombinacją tych warunków.</span><span class="sxs-lookup"><span data-stu-id="37ef3-257">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="37ef3-258">Ręcznie wygenerowane zlecenie kontroli jakości, które dotyczy operacji marszruty, może używać informacji z rekordu skojarzenia jakości, takich plan próbkowania.</span><span class="sxs-lookup"><span data-stu-id="37ef3-258">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-259">Zapasy</span><span class="sxs-lookup"><span data-stu-id="37ef3-259">Inventory</span></span></td>
<td><span data-ttu-id="37ef3-260">Zlecenie kontroli jakości nie może być generowane automatycznie dla transakcji w arkuszu magazynowym lub dla transakcji zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="37ef3-260">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="37ef3-261">Zlecenie kontroli jakości musi być tworzone ręcznie dla ilości zapasów towaru.</span><span class="sxs-lookup"><span data-stu-id="37ef3-261">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="37ef3-262">Fizyczne dostępne zapasy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="37ef3-262">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="37ef3-263">Przykłady automatycznego generowania zlecenia kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="37ef3-263">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="37ef3-264">Zakupy</span><span class="sxs-lookup"><span data-stu-id="37ef3-264">Purchasing</span></span>

<span data-ttu-id="37ef3-265">Jeśli w obszarze zakupów w polu **Typ zdarzenia** zostanie ustawiona wartość **Przyjęcie produktów**, a w polu **Wykonanie** wartość **Po** na stronie **Powiązania jakości**, otrzymasz następujące wyniki :</span><span class="sxs-lookup"><span data-stu-id="37ef3-265">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="37ef3-266">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Tak**, zlecenie kontroli jakości jest generowane dla każdego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości i ustawień w ramach kontroli wyrywkowej pozycji.</span><span class="sxs-lookup"><span data-stu-id="37ef3-266">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="37ef3-267">Za każdym razem, gdy ilość jest przyjmowana względem zamówienia zakupu, nowe zlecenia kontroli jakości są generowane na podstawie nowo przyjętej ilości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-267">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="37ef3-268">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Nie**, zlecenie kontroli jakości jest generowane dla pierwszego przyjęcia względem zamówienia zakupu na podstawie przyjętej ilości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-268">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="37ef3-269">Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="37ef3-269">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="37ef3-270">Zlecenia kontroli jakości nie są generowane dla kolejnych przyjęć względem zamówienia zakupu.</span><span class="sxs-lookup"><span data-stu-id="37ef3-270">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="37ef3-271">Produkcyjne</span><span class="sxs-lookup"><span data-stu-id="37ef3-271">Production</span></span>

<span data-ttu-id="37ef3-272">Jeśli w obszarze produkcji w polu **Typ zdarzenia** zostanie ustawiona wartość **Zgłoszenie wyrobów gotowych**, a w polu **Wykonanie** wartość **Po** na stronie **Powiązania jakości**, otrzymasz następujące wyniki :</span><span class="sxs-lookup"><span data-stu-id="37ef3-272">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="37ef3-273">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Tak**, zlecenie kontroli jakości jest generowane dla każdej ilości wyrobów gotowych i ustawień w ramach kontroli wyrywkowej pozycji.</span><span class="sxs-lookup"><span data-stu-id="37ef3-273">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="37ef3-274">Za każdym razem, gdy ilość jest zgłaszana jako gotowa względem zlecenia produkcyjnego, nowe zlecenia kontroli jakości są generowane na podstawie nowej ilości zgłoszonej jako gotowa.</span><span class="sxs-lookup"><span data-stu-id="37ef3-274">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="37ef3-275">Ta logika generowania jest spójna z procesem zakupów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-275">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="37ef3-276">Jeśli opcja **Dla zaktualizowanej ilości** została ustawiona na **Nie**, zlecenie kontroli jakości jest generowane po pierwszym zgłoszeniu ilości jako gotowej na podstawie gotowej ilości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-276">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="37ef3-277">Ponadto co najmniej jedno zlecenie kontroli jakości jest tworzone na podstawie pozostałej ilości, w zależności od wymiarów śledzenia kontroli wyrywkowej pozycji.</span><span class="sxs-lookup"><span data-stu-id="37ef3-277">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="37ef3-278">Zlecenia kontroli jakości nie są generowane dla kolejnych gotowych ilości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-278">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="37ef3-279">Specyfikacja jakości</span><span class="sxs-lookup"><span data-stu-id="37ef3-279">Quality specification</span></span></th>
<th><span data-ttu-id="37ef3-280">Dla zaktualizowanej ilości</span><span class="sxs-lookup"><span data-stu-id="37ef3-280">Per updated quantity</span></span></th>
<th><span data-ttu-id="37ef3-281">Dla wymiaru śledzenia</span><span class="sxs-lookup"><span data-stu-id="37ef3-281">Per tracking dimension</span></span></th>
<th><span data-ttu-id="37ef3-282">Wynik</span><span class="sxs-lookup"><span data-stu-id="37ef3-282">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="37ef3-283">Wartość procentowa: 10%</span><span class="sxs-lookup"><span data-stu-id="37ef3-283">Percentage: 10%</span></span></td>
<td><span data-ttu-id="37ef3-284">Tak</span><span class="sxs-lookup"><span data-stu-id="37ef3-284">Yes</span></span></td>
<td>
<p><span data-ttu-id="37ef3-285">Numer partii: Nie</span><span class="sxs-lookup"><span data-stu-id="37ef3-285">Batch number: No</span></span></p>
<p><span data-ttu-id="37ef3-286">Numer seryjny: Nie</span><span class="sxs-lookup"><span data-stu-id="37ef3-286">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="37ef3-287">Ilość w zamówieniu: 100</span><span class="sxs-lookup"><span data-stu-id="37ef3-287">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="37ef3-288">Zgłaszanie wyrobów gotowych dla 30</span><span class="sxs-lookup"><span data-stu-id="37ef3-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="37ef3-289">Zlecenie kontroli jakości nr 1 dla 3 (10% z 30)</span><span class="sxs-lookup"><span data-stu-id="37ef3-289">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="37ef3-290">Zgłaszanie wyrobów gotowych dla 70</span><span class="sxs-lookup"><span data-stu-id="37ef3-290">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="37ef3-291">Zlecenie kontroli jakości nr 2 dla 7 (10% pozostałej ilości zamówienia, w tym przypadku 70)</span><span class="sxs-lookup"><span data-stu-id="37ef3-291">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-292">Stała ilość: 1</span><span class="sxs-lookup"><span data-stu-id="37ef3-292">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="37ef3-293">Nie</span><span class="sxs-lookup"><span data-stu-id="37ef3-293">No</span></span></td>
<td>
<p><span data-ttu-id="37ef3-294">Numer partii: Nie</span><span class="sxs-lookup"><span data-stu-id="37ef3-294">Batch number: No</span></span></p>
<p><span data-ttu-id="37ef3-295">Numer seryjny: Nie</span><span class="sxs-lookup"><span data-stu-id="37ef3-295">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="37ef3-296">Ilość w zamówieniu: 100</span><span class="sxs-lookup"><span data-stu-id="37ef3-296">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="37ef3-297">Zgłaszanie wyrobów gotowych dla 30</span><span class="sxs-lookup"><span data-stu-id="37ef3-297">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="37ef3-298">Zlecenie kontroli jakości nr 1 dla 1 (dla pierwszej ilości zgłoszonej jako gotowa, która ma stałą wartość równą 1)</span><span class="sxs-lookup"><span data-stu-id="37ef3-298">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="37ef3-299">Zlecenie kontroli jakości nr 2 dla 1 (dla pozostałej ilości, która nadal ma stałą wartość równą 1)</span><span class="sxs-lookup"><span data-stu-id="37ef3-299">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="37ef3-300">Zgłaszanie wyrobów gotowych dla 10</span><span class="sxs-lookup"><span data-stu-id="37ef3-300">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="37ef3-301">Zlecenia kontroli jakości nie są tworzone.</span><span class="sxs-lookup"><span data-stu-id="37ef3-301">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="37ef3-302">Zgłaszanie wyrobów gotowych dla 60</span><span class="sxs-lookup"><span data-stu-id="37ef3-302">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="37ef3-303">Zlecenia kontroli jakości nie są tworzone.</span><span class="sxs-lookup"><span data-stu-id="37ef3-303">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-304">Stała ilość: 1</span><span class="sxs-lookup"><span data-stu-id="37ef3-304">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="37ef3-305">Tak</span><span class="sxs-lookup"><span data-stu-id="37ef3-305">Yes</span></span></td>
<td>
<p><span data-ttu-id="37ef3-306">Numer partii: Tak</span><span class="sxs-lookup"><span data-stu-id="37ef3-306">Batch number: Yes</span></span></p>
<p><span data-ttu-id="37ef3-307">Numer seryjny: Tak</span><span class="sxs-lookup"><span data-stu-id="37ef3-307">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="37ef3-308">Ilość w zamówieniu: 10</span><span class="sxs-lookup"><span data-stu-id="37ef3-308">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="37ef3-309">Zgłaszanie wyrobów gotowych dla 3: 1 dla b1, s1; 1 dla b2, s2; i 1 dla b3, s3</span><span class="sxs-lookup"><span data-stu-id="37ef3-309">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="37ef3-310">Zlecenie kontroli jakości nr 1 dla 1 — partia b1, numer seryjny s1</span><span class="sxs-lookup"><span data-stu-id="37ef3-310">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="37ef3-311">Zlecenie kontroli jakości nr 2 dla 1 — partia b2, numer seryjny s2</span><span class="sxs-lookup"><span data-stu-id="37ef3-311">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="37ef3-312">Zlecenie kontroli jakości nr 3 dla 1 — partia b3, numer seryjny s3</span><span class="sxs-lookup"><span data-stu-id="37ef3-312">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="37ef3-313">Zgłaszanie wyrobów gotowych dla 2: 1 dla b4, s4 i 1 dla b5, s5</span><span class="sxs-lookup"><span data-stu-id="37ef3-313">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="37ef3-314">Zlecenie kontroli jakości nr 4 dla 1 — partia b4, numer seryjny s4</span><span class="sxs-lookup"><span data-stu-id="37ef3-314">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="37ef3-315">Zlecenie kontroli jakości nr 5 dla 1 — partia b5, numer seryjny s5</span><span class="sxs-lookup"><span data-stu-id="37ef3-315">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="37ef3-316"><strong>Uwaga:</strong> partii można użyć ponownie.</span><span class="sxs-lookup"><span data-stu-id="37ef3-316"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="37ef3-317">Stała ilość: 2</span><span class="sxs-lookup"><span data-stu-id="37ef3-317">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="37ef3-318">Nie</span><span class="sxs-lookup"><span data-stu-id="37ef3-318">No</span></span></td>
<td>
<p><span data-ttu-id="37ef3-319">Numer partii: Tak</span><span class="sxs-lookup"><span data-stu-id="37ef3-319">Batch number: Yes</span></span></p>
<p><span data-ttu-id="37ef3-320">Numer seryjny: Tak</span><span class="sxs-lookup"><span data-stu-id="37ef3-320">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="37ef3-321">Ilość w zamówieniu: 10</span><span class="sxs-lookup"><span data-stu-id="37ef3-321">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="37ef3-322">Zgłaszanie wyrobów gotowych dla 4: 1 dla b1, s1; 1 dla b2, s2; 1 dla b3, s3 i 1 dla b4, s4</span><span class="sxs-lookup"><span data-stu-id="37ef3-322">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="37ef3-323">Zlecenie kontroli jakości nr 1 dla 1 — partia b1, numer seryjny s1</span><span class="sxs-lookup"><span data-stu-id="37ef3-323">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="37ef3-324">Zlecenie kontroli jakości nr 2 dla 1 — partia b2, numer seryjny s2</span><span class="sxs-lookup"><span data-stu-id="37ef3-324">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="37ef3-325">Zlecenie kontroli jakości nr 3 dla 1 — partia b3, numer seryjny s3</span><span class="sxs-lookup"><span data-stu-id="37ef3-325">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="37ef3-326">Zlecenie kontroli jakości nr 4 dla 1 — partia b4, numer seryjny s4</span><span class="sxs-lookup"><span data-stu-id="37ef3-326">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="37ef3-327">Zlecenie kontroli jakości nr 5 dla 2 bez odwołania do partii i numeru seryjnego</span><span class="sxs-lookup"><span data-stu-id="37ef3-327">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="37ef3-328">Zgłaszanie wyrobów gotowych dla 6: 1 dla b5, s5; 1 dla b6, s6; 1 dla b7, s7; 1 dla b8, s8; 1 dla b9, s9; i 1 dla b10, s10</span><span class="sxs-lookup"><span data-stu-id="37ef3-328">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="37ef3-329">Zlecenia kontroli jakości nie są tworzone.</span><span class="sxs-lookup"><span data-stu-id="37ef3-329">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="37ef3-330">Funkcja *Zarządzanie jakością dla procesów magazynowych* dodaje możliwości przetwarzania zlecenia kontroli jakości dla produkcji z ustawionym typem **Typ zdarzenia** jako *Zgłoś jako gotowe*, a  **Wykonanie** ma ustawienie *Po* i dla zakupów z typem **Typ zdarzenia** ustawionym jako *Rejestracja*.</span><span class="sxs-lookup"><span data-stu-id="37ef3-330">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production with **Event type** set to *Report as finished* and **Execution** set to *After*, and for purchases with **Event type** set to *Registration*.</span></span> <span data-ttu-id="37ef3-331">Aby zapoznać sie ze szczegółami, zobacz [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="37ef3-331">For details, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

## <a name="quality-management-pages"></a><span data-ttu-id="37ef3-332">Strony zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="37ef3-332">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37ef3-333">Strona</span><span class="sxs-lookup"><span data-stu-id="37ef3-333">Page</span></span></th>
<th><span data-ttu-id="37ef3-334">opis</span><span class="sxs-lookup"><span data-stu-id="37ef3-334">Description</span></span></th>
<th><span data-ttu-id="37ef3-335">Przykład</span><span class="sxs-lookup"><span data-stu-id="37ef3-335">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="37ef3-336">Powiązania jakości</span><span class="sxs-lookup"><span data-stu-id="37ef3-336">Quality associations</span></span></td>
<td><span data-ttu-id="37ef3-337">Zobacz poprzednie części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="37ef3-337">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="37ef3-338">Powiązanie jakości określa wszystkie poniższe informacje dla generowanego zlecenia kontroli jakości:</span><span class="sxs-lookup"><span data-stu-id="37ef3-338">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="37ef3-339">Zdarzenie transakcji</span><span class="sxs-lookup"><span data-stu-id="37ef3-339">The transaction event</span></span></li>
<li><span data-ttu-id="37ef3-340">Zestaw testów, które należy wykonać na towarach</span><span class="sxs-lookup"><span data-stu-id="37ef3-340">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="37ef3-341">AQL</span><span class="sxs-lookup"><span data-stu-id="37ef3-341">The AQL</span></span></li>
<li><span data-ttu-id="37ef3-342">Plan pobierania próbek</span><span class="sxs-lookup"><span data-stu-id="37ef3-342">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="37ef3-343">Należy określić skojarzenie jakości dla każdego odchylenia w procesie biznesowym, które wymaga automatycznego generowania zlecenia kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-343">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="37ef3-344">Na przykład: zlecenie kontroli jakości może być generowane w procesie biznesowym związanym z zamówieniami zakupu, zleceniami kwarantanny, zamówieniami sprzedaży i zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="37ef3-344">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37ef3-345">Testy</span><span class="sxs-lookup"><span data-stu-id="37ef3-345">Tests</span></span></td>
<td><span data-ttu-id="37ef3-346">Ta strona służy do definiowania i wyświetlania poszczególnych testów decydujących, czy produkty są zgodne ze specyfikacjami jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-346">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="37ef3-347">Do grupy testowej można przypisać jeden lub więcej testów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-347">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="37ef3-348">W takim przypadku określa się również informacje właściwe dla danego testu, takie jak akceptowalne wartości pomiaru.</span><span class="sxs-lookup"><span data-stu-id="37ef3-348">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="37ef3-349">Wartości pomiaru są używane w testach ilościowych, a zmienne testowe są używane w testach jakościowych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-349">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="37ef3-350">Testy ilościowe mogą być typu <strong>Całkowity</strong> lub <strong>Ułamek</strong> i mają przypisaną jednostkę miary.</span><span class="sxs-lookup"><span data-stu-id="37ef3-350">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="37ef3-351">Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="37ef3-351">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="37ef3-352">Test jakościowy ma przypisany typ <strong>Opcja</strong>.</span><span class="sxs-lookup"><span data-stu-id="37ef3-352">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="37ef3-353">Testy jakości wymagają dodatkowych informacji konfiguracyjnych dotyczących zmiennej testowej i jej wyliczonych opcji.</span><span class="sxs-lookup"><span data-stu-id="37ef3-353">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="37ef3-354">Specyfikacje jakości i wyniki testu są wyrażane jako liczby.</span><span class="sxs-lookup"><span data-stu-id="37ef3-354">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="37ef3-355">Firma produkcyjna wykonuje dwa testy na zakupionym materiale, w tym test ilości dotyczący jakości materiału i test jakości dotyczący uszkodzenia opakowania.</span><span class="sxs-lookup"><span data-stu-id="37ef3-355">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="37ef3-356">Firma definiuje dodatkowe informacje na temat testu jakości w celu określenia zmiennej testowej (uszkodzone opakowanie) i jej wartości wynikowe.</span><span class="sxs-lookup"><span data-stu-id="37ef3-356">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="37ef3-357">Firma używa strony <strong>Grupy testowe</strong> do przypisania dwóch testów do grupy testowej i do określenia informacji specyficznych dla testu.</span><span class="sxs-lookup"><span data-stu-id="37ef3-357">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="37ef3-358">Grupa testów jest przypisywana do zlecenia kontroli jakości, dzięki czemu firma może raportować wyniki testu dla dwóch testów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-358">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37ef3-359">Grupy testowe</span><span class="sxs-lookup"><span data-stu-id="37ef3-359">Test groups</span></span></td>
<td><span data-ttu-id="37ef3-360">Strona ta służy do konfigurowania, edytowania i wyświetlania grup testowych oraz testów indywidualnych przypisanych do danej grupy testowej.</span><span class="sxs-lookup"><span data-stu-id="37ef3-360">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="37ef3-361">W górnym okienku wyświetlane są grupy testowe, a w dolnym — testy przypisane do wybranej grupy testowej.</span><span class="sxs-lookup"><span data-stu-id="37ef3-361">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="37ef3-362">Do grupy testowej można przypisać różne zasady, w tym plan próbkowania, akceptowany poziom jakości i wymaganie dotyczące testowania destrukcyjnego.</span><span class="sxs-lookup"><span data-stu-id="37ef3-362">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="37ef3-363">Po przypisaniu każdego z tych testów do grupy testowej, można zdefiniować dodatkowe informacje, takie jak sekwencje, dokumenty i daty ważności.</span><span class="sxs-lookup"><span data-stu-id="37ef3-363">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="37ef3-364">W przypadku testu ilościowego zdefiniowane informacje zawierają również akceptowalne wartości pomiaru.</span><span class="sxs-lookup"><span data-stu-id="37ef3-364">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="37ef3-365">W przypadku testu jakościowego informacje zmienną testową i domyślny rezultat.</span><span class="sxs-lookup"><span data-stu-id="37ef3-365">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="37ef3-366">Za pomocą grupy testów przypisanej do zlecenia kontroli jakości określa się domyślny zestaw testów, które muszą zostać przeprowadzone odnośnie do określonego towaru.</span><span class="sxs-lookup"><span data-stu-id="37ef3-366">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="37ef3-367">Ale mnożna dodawać, usuwać lub zmieniać testy w zleceniu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-367">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="37ef3-368">Wyniki testu są raportowane dla każdego testu w zleceniu kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-368">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="37ef3-369">W przedsiębiorstwie produkcyjnym zdefiniowano grupę testową dla każdego odchylenia dotyczącego zasad kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-369">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="37ef3-370">Poszczególne grupy testowe odpowiadają różnym planom próbkowania, seriom testów, które muszą być wykonywane razem, akceptowanemu poziomowi jakości i innym czynnikom.</span><span class="sxs-lookup"><span data-stu-id="37ef3-370">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="37ef3-371">W testach ilościowych są również różnice we właściwych wartościach pomiaru.</span><span class="sxs-lookup"><span data-stu-id="37ef3-371">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="37ef3-372">Aby wymusić wytyczne co do jakości, firma przypisuje grupę testową do każdej reguły w celu automatycznego generowania zleceń kontroli jakości na stronie <strong>powiązań jakości</strong> i przypisuje grupę testową do ręcznie tworzonych zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-372">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37ef3-373">Grupy jakości pozycji</span><span class="sxs-lookup"><span data-stu-id="37ef3-373">Item quality groups</span></span></td>
<td><span data-ttu-id="37ef3-374">Ta strona umożliwia konfigurowanie, edycję i wyświetlanie towarów przypisanych do grupy jakości lub grup jakości przypisanych do towaru.</span><span class="sxs-lookup"><span data-stu-id="37ef3-374">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="37ef3-375">Grupa jakości reprezentuje wspólne wymagania dotyczące testowania towarów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-375">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="37ef3-376">Po zdefiniowaniu wymogów testu na stronie <strong>Grupy testowe</strong> można zdefiniować reguły automatycznego generowania zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-376">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="37ef3-377">Aby uprościć proces, nie definiuje się reguł dla poszczególnych towarów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-377">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="37ef3-378">Zamiast tego definiuje się reguły dla grupy jakości na stronie <strong>powiązań jakości</strong>.</span><span class="sxs-lookup"><span data-stu-id="37ef3-378">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="37ef3-379">Można również użyć strony <strong>Grupy jakości towarów</strong> dla wybranej grupy jakości w celu przypisania odpowiednich towarów do tej grupy.</span><span class="sxs-lookup"><span data-stu-id="37ef3-379">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="37ef3-380">Można również użyć strony <strong>Grupy jakości towarów</strong> dla wybranego towaru w celu przypisania odpowiednich grup jakości do danego towaru.</span><span class="sxs-lookup"><span data-stu-id="37ef3-380">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="37ef3-381">Firma produkcyjna nabywa kilka surowców mających te same wymagania dotyczące testowania przed zbliżającą się inspekcją.</span><span class="sxs-lookup"><span data-stu-id="37ef3-381">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="37ef3-382">Firma definiuje grupę jakości, a następnie przypisuje do tej grupy kody towarów, które są skojarzone z surowcami.</span><span class="sxs-lookup"><span data-stu-id="37ef3-382">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="37ef3-383">Później firma nabywa nowy typ surowca, który ma te same wymagania dotyczące testowania.</span><span class="sxs-lookup"><span data-stu-id="37ef3-383">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="37ef3-384">Zamiast konfigurować nowe wymagania dotyczące nowego materiału, firma dodaje kod towaru dla nowego materiału do istniejącej grupy jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-384">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="37ef3-385">Ta sama firma produkuje również towary mające te same wymagania dotyczące testowania produkcji i wysyła towary mające te same wymagania dotyczące przeprowadzania testów przed wysyłką.</span><span class="sxs-lookup"><span data-stu-id="37ef3-385">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="37ef3-386">Firma definiuje dwie dodatkowe grupy jakości i przypisuje do każdej z nich odpowiednie kody towarów.</span><span class="sxs-lookup"><span data-stu-id="37ef3-386">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="37ef3-387">Zmienne testowe</span><span class="sxs-lookup"><span data-stu-id="37ef3-387">Test variables</span></span></td>
<td><span data-ttu-id="37ef3-388">Ta strona umożliwia definiowanie i wyświetlanie zmiennych skojarzonych z testem jakościowym.</span><span class="sxs-lookup"><span data-stu-id="37ef3-388">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="37ef3-389">Dla każdej zmiennej można zdefiniować wyliczenie wyników reprezentujące możliwe opcje.</span><span class="sxs-lookup"><span data-stu-id="37ef3-389">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="37ef3-390">Testy definiuje się na stronie <strong>Testy</strong>.</span><span class="sxs-lookup"><span data-stu-id="37ef3-390">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="37ef3-391">W przypadku testów jakościowych trzeba ustawić typ testu jako <strong>Opcja</strong>.</span><span class="sxs-lookup"><span data-stu-id="37ef3-391">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="37ef3-392">Strona <strong>Grupy testowe</strong> służy do przypisywania zmiennej testowej do konkretnego testu.</span><span class="sxs-lookup"><span data-stu-id="37ef3-392">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="37ef3-393">Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie.</span><span class="sxs-lookup"><span data-stu-id="37ef3-393">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="37ef3-394">Ten test inspekcji zawiera kilka zmiennych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-394">This inspection test has several variables.</span></span> <span data-ttu-id="37ef3-395">Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły.</span><span class="sxs-lookup"><span data-stu-id="37ef3-395">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="37ef3-396">Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="37ef3-396">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="37ef3-397">Wyniki zmiennych testowych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-397">Test variable outcomes</span></span></td>
<td><span data-ttu-id="37ef3-398">Ta strona służy do konfigurowania, edytowania i wyświetlania możliwych wartości zmiennej testowej skojarzonej z testem jakości.</span><span class="sxs-lookup"><span data-stu-id="37ef3-398">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="37ef3-399">Dla każdego wyniku należy przypisać stan <strong>powodzenie</strong> lub <strong>niepowodzenie</strong>.</span><span class="sxs-lookup"><span data-stu-id="37ef3-399">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="37ef3-400">Należy zdefiniować zmienną i jej wyniki dla każdego testu jakości zdefiniowanego na stronie <strong>Testy</strong>.</span><span class="sxs-lookup"><span data-stu-id="37ef3-400">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="37ef3-401">(Dla testów jakościowych ustawiono typ testu <strong>Opcja</strong> na stronie <strong>Testy</strong>). Strona <strong>Grupy testów</strong> służy do przypisywania zmiennej testowej i domyślnego wyniku do konkretnego testu.</span><span class="sxs-lookup"><span data-stu-id="37ef3-401">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="37ef3-402">Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie.</span><span class="sxs-lookup"><span data-stu-id="37ef3-402">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="37ef3-403">Ten test inspekcji zawiera kilka zmiennych.</span><span class="sxs-lookup"><span data-stu-id="37ef3-403">This inspection test has of several variables.</span></span> <span data-ttu-id="37ef3-404">Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły.</span><span class="sxs-lookup"><span data-stu-id="37ef3-404">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="37ef3-405">Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy.</span><span class="sxs-lookup"><span data-stu-id="37ef3-405">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="37ef3-406">Każdy wynik ma przypisany stan <strong>powodzenie</strong> lub <strong>niepowodzenie</strong>.</span><span class="sxs-lookup"><span data-stu-id="37ef3-406">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="37ef3-407">Podczas sprawdzania poszczególnych zmiennych, kontroler raportuje wyniki testów, zaznaczając jeden z wyników.</span><span class="sxs-lookup"><span data-stu-id="37ef3-407">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="37ef3-408">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="37ef3-408">Additional resources</span></span>
--------

[<span data-ttu-id="37ef3-409">Procesy zarządzania jakością</span><span class="sxs-lookup"><span data-stu-id="37ef3-409">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="37ef3-410">Zarządzanie brakiem zgodności</span><span class="sxs-lookup"><span data-stu-id="37ef3-410">Nonconformance management</span></span>](enable-nonconformance-management.md)

[<span data-ttu-id="37ef3-411">Zarządzanie jakością dla procesów magazynowych</span><span class="sxs-lookup"><span data-stu-id="37ef3-411">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]