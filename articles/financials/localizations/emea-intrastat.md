---
title: Intrastat
description: "Ten artykuł zawiera informacje o sprawozdawczości Intrastat o handlu towarami i — w niektórych przypadkach — usługami między krajami/regionami Unii Europejskiej (UE). Omówiono proces sprawozdawczości oraz opisano wymagane ustawienia i warunki wstępne."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Intrastat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 50526d278df0a09948a5810f00f4fe2834917742
ms.openlocfilehash: e5445d850e2e5afc201662d8c5343d27bc4ecb05
ms.contentlocale: pl-pl
ms.lasthandoff: 10/03/2017

---

# <a name="intrastat"></a><span data-ttu-id="eb76f-104">Intrastat</span><span class="sxs-lookup"><span data-stu-id="eb76f-104">Intrastat</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="eb76f-105">Ten artykuł zawiera informacje o sprawozdawczości Intrastat o handlu towarami i — w niektórych przypadkach — usługami między krajami/regionami Unii Europejskiej (UE).</span><span class="sxs-lookup"><span data-stu-id="eb76f-105">This article provides information about Intrastat reporting for the trade of goods and, in some cases, services among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="eb76f-106">Omówiono proces sprawozdawczości oraz opisano wymagane ustawienia i warunki wstępne.</span><span class="sxs-lookup"><span data-stu-id="eb76f-106">It provides an overview of the reporting process, and describes the required settings and prerequisites.</span></span>

<span data-ttu-id="eb76f-107">Intrastat to system gromadzenia i generowania danych statystycznych na temat handlu towarami między krajami/regionami Unii Europejskiej (UE).</span><span class="sxs-lookup"><span data-stu-id="eb76f-107">Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="eb76f-108">Raport Intrastat jest wymagany w przypadku każdego produktu przekraczającego granicę innego kraju/regionu UE.</span><span class="sxs-lookup"><span data-stu-id="eb76f-108">Intrastat reporting is required whenever a product crosses the border of another EU country/region.</span></span> <span data-ttu-id="eb76f-109">W niektórych krajach/regionach obowiązek tworzenia raportów Intrastat dotyczy również usług.</span><span class="sxs-lookup"><span data-stu-id="eb76f-109">In several countries/regions, Intrastat reporting also applies to services.</span></span> <span data-ttu-id="eb76f-110">Na potrzeby raportów Intrastat mogą być gromadzone obowiązkowe i opcjonalne elementy.</span><span class="sxs-lookup"><span data-stu-id="eb76f-110">Mandatory and optional elements can be collected in Intrastat reporting.</span></span> <span data-ttu-id="eb76f-111">Wymagane są następujące elementy: identyfikator VAT podmiotu odpowiedzialnego za dostarczenie informacji, okres referencyjny, przepływ (przyjęcie lub wysyłka), ośmiocyfrowy kod towaru, kraj członkowski (kraj wysyłki i kraj docelowy), wartość towaru, ilość towaru (waga netto i jednostka dodatkowa) oraz charakter transakcji.</span><span class="sxs-lookup"><span data-stu-id="eb76f-111">The following elements are mandatory: the value-added tax (VAT) number of the party that is responsible for providing information, the reference period, the flow (arrival or dispatch), the eight-digit commodity code, the partner member state (member state of consignment on arrivals and member state of destination on dispatches), the value of the goods, the quantity of the goods (net mass and supplementary unit), and the nature of the transaction.</span></span> <span data-ttu-id="eb76f-112">Kraje/regiony mogą również gromadzić opcjonalne informacje w różnych warunkach.</span><span class="sxs-lookup"><span data-stu-id="eb76f-112">Countries/regions can also collect optional elements under various conditions.</span></span> <span data-ttu-id="eb76f-113">Do informacji opcjonalnych należą: kraj/region pochodzenia towaru, warunki dostawy, środek transportu, bardziej szczegółowy kod towaru niż 8-cyfrowy, kraj pochodzenia dla wysyłki i kraj pochodzenia dla odbioru, procedura statystyczna, wartość statystyczna, opis towaru oraz port/lotnisko załadunku/rozładunku.</span><span class="sxs-lookup"><span data-stu-id="eb76f-113">Some optional elements are the country/region of origin, the delivery terms, the mode of transport, a more detailed commodity code than CN8, the region of origin on dispatches and the region of destination on arrivals, the statistical procedure, the statistical value, a description of the goods, and the port/airport of loading/unloading.</span></span>

## <a name="overview-of-the-intrastat-reporting-process"></a><span data-ttu-id="eb76f-114">Omówienie procedury raportowania Intrastat</span><span class="sxs-lookup"><span data-stu-id="eb76f-114">Overview of the Intrastat reporting process</span></span>
<span data-ttu-id="eb76f-115">W poniższych sekcjach opisano cały przebieg informacji używanych na potrzeby raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-115">The following sections describe the overall flow of information that is used for Intrastat reporting.</span></span>

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a><span data-ttu-id="eb76f-116">1. Podanie transakcji przekraczającej granicę innego kraju/regionu UE</span><span class="sxs-lookup"><span data-stu-id="eb76f-116">1. Enter a transaction that crosses the border of another EU country/region</span></span>

<span data-ttu-id="eb76f-117">Faktura dla odbiorcy, faktura niezależna, faktura zakupu, faktura projektu, dokument dostawy dla odbiorcy, dokument przyjęcia produktów od dostawcy lub zamówienie przeniesienia są przenoszone do arkusza Intrastat tyko wtedy, gdy kraj/region wysyłki lub dostawy znajduje się w **UE**.</span><span class="sxs-lookup"><span data-stu-id="eb76f-117">A customer invoice, free text invoice, purchase invoice, project invoice, customer packing slip, vendor product receipt, or transfer order is transferred to the Intrastat journal only if the country/region type of the destination (on dispatches) or consignment (on arrivals) is **EU**.</span></span> <span data-ttu-id="eb76f-118">Ta funkcja została rozszerzona w programie Microsoft Dynamics 365 for Operations (wydanie 1611) i teraz pozwala określać adresy załadunku dla transakcji wewnątrzwspólnotowych.</span><span class="sxs-lookup"><span data-stu-id="eb76f-118">This feature was extended for Microsoft Dynamics 365 for Operations (1611) and allows you to specify lading addresses for an intra-community transaction.</span></span> <span data-ttu-id="eb76f-119">Jeżeli adres załadunku różni się od adresu służbowego dostawcy (lub adres służbowego odbiorcy w zamówieniu zwrotu), funkcja raportowania Intrastat użyje tych informacji.</span><span class="sxs-lookup"><span data-stu-id="eb76f-119">If a lading address differs with a vendor business address (or customer business address for return order) the Intrastat reporting will operate with this information.</span></span> <span data-ttu-id="eb76f-120">Podczas tworzenia zamówienia sprzedaży, faktury niezależnej, zamówienia zakupu, faktury od dostawcy, faktury projektu lub zamówienia przeniesienia, niektóre pola, które są powiązane z handlem zagranicznym, mają wartości domyślne w nagłówku dokumentu lub w wierszu.</span><span class="sxs-lookup"><span data-stu-id="eb76f-120">When you create a sales order, free text invoice, purchase order, vendor invoice, project invoice, or transfer order, some fields that are related to foreign trade have default values in the document header or on the line.</span></span> <span data-ttu-id="eb76f-121">Domyślny kod transakcji jest pobierany z odpowiedniego pola na stronie **Parametry handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="eb76f-121">The default transaction code is taken from the corresponding field on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="eb76f-122">Domyślny kod towaru, kraj/region pochodzenia i województwo pochodzenia są pobierane z pozycji.</span><span class="sxs-lookup"><span data-stu-id="eb76f-122">The default commodity code, country/region of origin, and state/province of origin are taken from the item.</span></span> <span data-ttu-id="eb76f-123">Można zmienić domyślne wartości i wprowadzić inne dane związane z handlem zagranicznym, takie jak procedura statystyczna, środek transportu i port.</span><span class="sxs-lookup"><span data-stu-id="eb76f-123">You can change the default values and can also fill in other foreign trade–related information: the statistics procedure, transport method, and port.</span></span>

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="eb76f-124">2. Używanie arkusza Intrastat do generowania i raportowania informacji dotyczących handlu między krajami/regionami Unii Europejskiej (UE)</span><span class="sxs-lookup"><span data-stu-id="eb76f-124">2. Use the Intrastat journal to generate information about trade among EU countries/regions</span></span>

<span data-ttu-id="eb76f-125">Na potrzeby statystyczne co miesiąc generuje się dane dotyczące handlu między krajami/regionami Unii Europejskiej.</span><span class="sxs-lookup"><span data-stu-id="eb76f-125">For statistical purposes, you generate information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="eb76f-126">Można przenieść transakcje z faktury niezależnej, faktury dla odbiorcy, dokumentu dostawy, faktury od dostawcy, dokumentu dostawy dostawcy, faktury projektu lub zamówienia przeniesienia na podstawie kryteriów transferu ustawionych na stronie **Parametry handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="eb76f-126">You can transfer transactions from a free text invoice, customer invoice, customer packing slip, vendor invoice, vendor packing slip, project invoice, or transfer order, according to the transfer criteria that are set up on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="eb76f-127">Można również ręcznie wprowadzić transakcje.</span><span class="sxs-lookup"><span data-stu-id="eb76f-127">Alternatively, you can enter transactions manually.</span></span> <span data-ttu-id="eb76f-128">W razie potrzeby można ręcznie zaktualizować przeniesione transakcje w arkuszu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-128">You can manually update transferred transactions in the Intrastat journal, if any updates are required.</span></span> <span data-ttu-id="eb76f-129">W określonych warunkach, które są ustawione na stronie **Kompresja Intrastat**, można kompresować transakcje w arkuszu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-129">Under specific conditions that are set up on the **Compression of Intrastat** page, you can compress the transactions in the Intrastat journal.</span></span> <span data-ttu-id="eb76f-130">W niektórych krajach/regionach można stosować niewielki próg wartości transakcji.</span><span class="sxs-lookup"><span data-stu-id="eb76f-130">Some countries/regions let you apply a small transaction threshold.</span></span> <span data-ttu-id="eb76f-131">Następnie transakcje poniżej tego progu można zgłaszać pod określonym kodem towaru.</span><span class="sxs-lookup"><span data-stu-id="eb76f-131">You can then report transactions that are below that threshold under the specified commodity code.</span></span> <span data-ttu-id="eb76f-132">Kod towaru można zaktualizować w odpowiednich wierszach arkusza Intrastat, na podstawie ustawienia **dolnego limitu** na stronie **Parametry handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="eb76f-132">You can update the commodity code on the corresponding Intrastat journal lines, based on the **Minimum limit** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="eb76f-133">Można także skompresować te transakcje na podstawie ustawienia **kompresji Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="eb76f-133">You can also compress those transactions, based on the **Compression of Intrastat** setting.</span></span> <span data-ttu-id="eb76f-134">Można sprawdzić poprawność transakcji w arkuszu Intrastat na podstawie ustawienia **Sprawdzenie ustawień** na stronie **Parametry handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="eb76f-134">You can validate the completeness of the transactions in the Intrastat journal, based on the **Check setup** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="eb76f-135">Można sprawdzić kompletność informacji w następujących polach: kraj/region, województwo, waga, kod towaru, kod transakcji, dodatkowe jednostki, port, pochodzenie, warunki dostawy, metody transportu i numer identyfikacji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="eb76f-135">The data in corresponding fields might be validated for completeness: country/region, state or province, weight, commodity code, transaction code, additional unit, port, origin, terms of delivery, transport method, and tax exempt number.</span></span> <span data-ttu-id="eb76f-136">Transakcje niekompletne zostaną oznaczone jako nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="eb76f-136">Transactions that aren't completed will be marked as not valid.</span></span>

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="eb76f-137">3. Używanie arkusza Intrastat do zgłaszanie informacji dotyczących handlu między krajami/regionami Unii Europejskiej (UE)</span><span class="sxs-lookup"><span data-stu-id="eb76f-137">3. Use the Intrastat journal to report information about trade among EU countries/regions</span></span>

<span data-ttu-id="eb76f-138">Na potrzeby statystyczne co miesiąc generuje się dane dotyczące handlu między krajami/regionami Unii Europejskiej.</span><span class="sxs-lookup"><span data-stu-id="eb76f-138">For statistical purposes, you report information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="eb76f-139">Na podstawie ustawienia **Mapowanie formatu raportów** na stronie **Parametry handlu zagranicznego** można wydrukować raport Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-139">You can print the Intrastat report, based on the **Report format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="eb76f-140">Można również wygenerować plik elektroniczny na podstawie ustawienia **Mapowanie formatu plików** na stronie **Parametry handlu zagranicznego**.</span><span class="sxs-lookup"><span data-stu-id="eb76f-140">You can also generate an electronic file, based on the **File format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="eb76f-141">Aby dowiedzieć się więcej o raportowaniu Intrastat, w tym o warunkach wstępnych, obejrzyj nagrania zadań dotyczące raportowania Intrastat:</span><span class="sxs-lookup"><span data-stu-id="eb76f-141">For more information about Intrastat reporting, including required prerequisites, see the Intrastat reporting task recordings:</span></span>

-   <span data-ttu-id="eb76f-142">Generowanie unijnej deklaracji Intrastat</span><span class="sxs-lookup"><span data-stu-id="eb76f-142">Generate an EU Intrastat declaration,</span></span>
-   <span data-ttu-id="eb76f-143">Przesyłanie transakcji do systemu Intrastat</span><span class="sxs-lookup"><span data-stu-id="eb76f-143">Transfer transactions to the Intrastat,</span></span>
-   <span data-ttu-id="eb76f-144">Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej</span><span class="sxs-lookup"><span data-stu-id="eb76f-144">Specifying lading address for an intra-community transaction.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eb76f-145">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="eb76f-145">Prerequisites</span></span>
<span data-ttu-id="eb76f-146">W następującej tabeli są podane wymagania wstępne dla raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-146">The following table lists the prerequisites for Intrastat reporting.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb76f-147">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="eb76f-147">Prerequisite</span></span></th>
<th><span data-ttu-id="eb76f-148">Opis</span><span class="sxs-lookup"><span data-stu-id="eb76f-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="eb76f-149">Ustawienia adresu</span><span class="sxs-lookup"><span data-stu-id="eb76f-149">Address setup</span></span></td>
<td><span data-ttu-id="eb76f-150">Konfigurowanie kodu ISO (International Organization for Standardization) dla krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="eb76f-150">Set up International Organization for Standardization (ISO) codes for countries/regions.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-151">Firma</span><span class="sxs-lookup"><span data-stu-id="eb76f-151">Legal entity</span></span></td>
<td><span data-ttu-id="eb76f-152">Konfigurowanie numerów identyfikacji podatkowej do celów importu/eksportu, wewnętrznego numeru oddziału dla importu/eksportu i kodu Intrastat przypisanego do firmy.</span><span class="sxs-lookup"><span data-stu-id="eb76f-152">Set up tax exempt numbers for import/export, the branch number extension for import/export, and the Intrastat code that is assigned to the legal entity.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb76f-153">Hierarchia kategorii produktów (hierarchia sprzedaży, hierarchia zaopatrzenia)</span><span class="sxs-lookup"><span data-stu-id="eb76f-153">Product category hierarchy (sales hierarchy, procurement hierarchy)</span></span></td>
<td><span data-ttu-id="eb76f-154">Przypisz kody asortymentu Intrastat do węzła kategorii na karcie <strong>Kody asortymentu</strong> na stronie <strong>Hierarchia kategorii</strong>.</span><span class="sxs-lookup"><span data-stu-id="eb76f-154">Assign the Intrastat commodity codes to the category nodes on the <strong>Commodity codes</strong> tab of the <strong>Category hierarchy</strong> page.</span></span> <span data-ttu-id="eb76f-155">Po przypisaniu kodu asortymentu do węzła nadrzędnego kategorii, ten kod jest stosowany do wszystkich podrzędnych węzłów kategorii.</span><span class="sxs-lookup"><span data-stu-id="eb76f-155">When you assign a commodity code to a parent category node, that code is applicable to all child category nodes.</span></span> <span data-ttu-id="eb76f-156">Wybrane kody asortymentu będą dostępne w widoku <strong>Wybrane</strong> po wybraniu kodu asortymentu w szczegółach zwolnionego produktu i na zamówieniu sprzedaży, zamówienia zakupu oraz w wierszach zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="eb76f-156">The selected commodity codes will be available in the <strong>Selected</strong> view when you select a commodity code in the released product details, and on sales order, purchase order, and transfer order lines.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-157">Szczegóły zwolnionego produktu</span><span class="sxs-lookup"><span data-stu-id="eb76f-157">Released product details</span></span></td>
<td><span data-ttu-id="eb76f-158">Konfigurowanie następujących danych handlu zagranicznego dla zwolnionych produktów:</span><span class="sxs-lookup"><span data-stu-id="eb76f-158">Set up the following foreign trade data for released products:</span></span>
<ul>
<li><span data-ttu-id="eb76f-159"><strong>Kod asortymentu</strong> — pozwala wybrać dowolną listę wybranych towarów pobraną z przypisanej kategorii produktów lub pełną listę kodów asortymentu Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-159"><strong>Commodity code</strong> – Select from either the list of selected commodities that is retrieved from assigned product categories or the full list of Intrastat commodity codes.</span></span></li>
<li><span data-ttu-id="eb76f-160"><strong>Statystyczny procent sumy</strong></span><span class="sxs-lookup"><span data-stu-id="eb76f-160"><strong>Statistical charges percentage</strong></span></span></li>
<li><span data-ttu-id="eb76f-161"><strong>Kraj/region pochodzenia</strong> — umożliwia wybór domyślnego kraju/regionu, w którym towary zostały w całości pozyskane lub wyprodukowane.</span><span class="sxs-lookup"><span data-stu-id="eb76f-161"><strong>Country/region of origin</strong> – Select the default country/region where the goods were completely obtained or produced.</span></span></li>
<li><span data-ttu-id="eb76f-162"><strong>Województwo pochodzenia/docelowe</strong> — pozwala wybrać domyślne województwo docelowe dla przyjęć i województwo pochodzenia dla wysyłki.</span><span class="sxs-lookup"><span data-stu-id="eb76f-162"><strong>State/province of origin/destination</strong> – Select the default state/province of destination for arrivals and the state/province of origin for dispatches.</span></span></li>
<li><span data-ttu-id="eb76f-163"><strong>Waga netto w kg</strong></span><span class="sxs-lookup"><span data-stu-id="eb76f-163"><strong>Net weight in kg</strong></span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb76f-164">Odbiorcy</span><span class="sxs-lookup"><span data-stu-id="eb76f-164">Customers</span></span></td>
<td><span data-ttu-id="eb76f-165">Konfigurowanie adresu dostawy w kraju/regionie UE dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="eb76f-165">Set up the customer delivery address in the EU country/region.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-166">Dostawcy</span><span class="sxs-lookup"><span data-stu-id="eb76f-166">Vendors</span></span></td>
<td><span data-ttu-id="eb76f-167">Konfigurowanie adresu dostawcy w kraju/regionie UE.</span><span class="sxs-lookup"><span data-stu-id="eb76f-167">Set up the vendor address in the EU country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb76f-168">Opłaty dodatkowe</span><span class="sxs-lookup"><span data-stu-id="eb76f-168">Miscellaneous charges</span></span></td>
<td><span data-ttu-id="eb76f-169">Konfigurowanie kodu opłat dodatkowych w celu uwzględnienia kwoty faktury, kwoty statystycznej lub obu.</span><span class="sxs-lookup"><span data-stu-id="eb76f-169">Set up the miscellaneous charges code to include in the invoice amount, the statistical amount, or both.</span></span> <span data-ttu-id="eb76f-170">Na stronie <strong>Kody opłat</strong> na karcie <strong>Handel zagraniczny</strong> włącz <strong>wartość faktury Intrastat</strong>, aby uwzględnić kwotę opłat w wartości faktury i włączyć <strong>Wartość statystyczna Intrastat</strong> w celu objęcia wartości statystycznej kwoty opłat dodatkowych.</span><span class="sxs-lookup"><span data-stu-id="eb76f-170">On the <strong>Charges codes</strong> page, on the <strong>Foreign trade</strong> tab, enable <strong>Intrastat invoice value</strong> to include the charges amount in the invoice value, and enable <strong>Intrastat statistical value</strong> to include the charges amount in the statistical value.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-171">Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="eb76f-171">Electronic reporting</span></span></td>
<td><span data-ttu-id="eb76f-172">Ustawienie konfiguracji raportu elektronicznego do eksportowania danych Intrastat do pliku w formacie żądanym przez odpowiednie organy i podglądu danych Intrastat w formacie przyjaznym dla użytkownika, który daje się odczytać (np. plik programu Microsoft Excel).</span><span class="sxs-lookup"><span data-stu-id="eb76f-172">Set up electronic reporting configurations to export Intrastat data in an electronic file that has the format that is requested by the relevant authorities, and to preview Intrastat data in a user-friendly, readable format (for example, in Microsoft Excel).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-173">Magazynowanie</span><span class="sxs-lookup"><span data-stu-id="eb76f-173">Warehousing</span></span></td>
<td><span data-ttu-id="eb76f-174">Skojarz konta dostawców z kodami magazynu w celu uzupełnienia numeru identyfikacji podatkowej przy przesyłaniu zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="eb76f-174">Associate vendor accounts with warehouse codes for filling tax exempt number when transferring Transfer order.</span></span></td>
</tr>
</tbody>
</table>

## <a name="setup"></a><span data-ttu-id="eb76f-175">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="eb76f-175">Setup</span></span>
<span data-ttu-id="eb76f-176">W poniższych sekcjach opisano ustawienia, które są wymagane na potrzeby raportowania Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-176">The following sections describe the settings that are required for Intrastat reporting.</span></span>

### <a name="set-up-all-required-intrastat-related-lists"></a><span data-ttu-id="eb76f-177">Ustaw wszystkie wymagane listy związane z deklaracją Intrastat</span><span class="sxs-lookup"><span data-stu-id="eb76f-177">Set up all required Intrastat-related lists</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb76f-178">Lista</span><span class="sxs-lookup"><span data-stu-id="eb76f-178">List</span></span></th>
<th><span data-ttu-id="eb76f-179">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="eb76f-179">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="eb76f-180">Kody asortymentu</span><span class="sxs-lookup"><span data-stu-id="eb76f-180">Commodity codes</span></span></td>
<td><span data-ttu-id="eb76f-181">Skonfiguruj hierarchię kategorii typu <strong>kod asortymentu</strong>i wprowadź wszystkie kody asortymentu zgodnie z listą.</span><span class="sxs-lookup"><span data-stu-id="eb76f-181">Set up a category hierarchy of type <strong>Commodity code</strong>, and enter all commodity codes according to the combined nomenclature list.</span></span> <span data-ttu-id="eb76f-182">Dla każdego towaru należy zdefiniować następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="eb76f-182">For each commodity, you set up the following information:</span></span>
<ul>
<li><span data-ttu-id="eb76f-183">Nazwa i kod towaru</span><span class="sxs-lookup"><span data-stu-id="eb76f-183">The name of the commodity and the commodity code</span></span></li>
<li><span data-ttu-id="eb76f-184">Przyjazna nazwa lub przetłumaczona nazwa</span><span class="sxs-lookup"><span data-stu-id="eb76f-184">The friendly name and/or translated name</span></span></li>
<li><span data-ttu-id="eb76f-185">Ustawienia raportowania dodatkowych (uzupełniających) jednostek na karcie <strong>Handel zagraniczny</strong>. Można wybrać dodatkowe jednostki z listy.</span><span class="sxs-lookup"><span data-stu-id="eb76f-185">Settings for reporting additional (supplementary) units on the <strong>Foreign trade</strong> tab. You can select the additional unit in the unit list.</span></span> <span data-ttu-id="eb76f-186">Można również określić, czy oprócz wybranej jednostki dodatkowej należy podać wagę towarów.</span><span class="sxs-lookup"><span data-stu-id="eb76f-186">You can also specify whether the weight of commodities must be reported in addition to the selected additional unit.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-187">Kody transakcji</span><span class="sxs-lookup"><span data-stu-id="eb76f-187">Transaction codes</span></span></td>
<td><span data-ttu-id="eb76f-188">Ustaw charakter transakcji zgodnie z wymaganiami danego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="eb76f-188">Set up the nature of the transaction according to your country's/region's requirements.</span></span> <span data-ttu-id="eb76f-189">Dla każdego ustawionego kodu transakcji należy skonfigurować reguły obliczania kwot faktur i kwot statystycznych dla zamówień sprzedaży/zakupu i zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="eb76f-189">For each transaction code that you set up, you must set up the rules for calculating invoice amounts and statistical amounts for transfer orders and sales/purchase orders.</span></span>
<ul>
<li><span data-ttu-id="eb76f-190">Dla zamówień przeniesienia należy zdefiniować jedną z następujących reguł obliczania kwot faktur i kwot statystycznych:</span><span class="sxs-lookup"><span data-stu-id="eb76f-190">For transfer orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="eb76f-191"><strong>Puste</strong> – kwota będzie równa 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="eb76f-191"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="eb76f-192"><strong>Wartość finansowa</strong> – kwota będzie równa kosztowi finansowemu.</span><span class="sxs-lookup"><span data-stu-id="eb76f-192"><strong>Financial cost amount</strong> – The amount will be equal to the financial cost.</span></span></li>
<li><span data-ttu-id="eb76f-193"><strong>Łączny koszt</strong> – kwota będzie równa łącznemu kosztowi transakcji.</span><span class="sxs-lookup"><span data-stu-id="eb76f-193"><strong>Total cost</strong> – The amount will be equal to the total cost of the transaction.</span></span></li>
<li><span data-ttu-id="eb76f-194"><strong>Ręcznie</strong> – kwota będzie równa kwocie ręcznie określonej w wierszu zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="eb76f-194"><strong>Manual</strong> – The amount will be equal to the amount that is manually specified on the transfer order line.</span></span></li>
</ul></li>
<li><span data-ttu-id="eb76f-195">Dla zamówień sprzedaży i zakupu należy zdefiniować jedną z następujących reguł obliczania kwot faktur i kwot statystycznych:</span><span class="sxs-lookup"><span data-stu-id="eb76f-195">For sales orders and purchase orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="eb76f-196"><strong>Puste</strong> – kwota będzie równa 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="eb76f-196"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="eb76f-197"><strong>Kwota faktury</strong> – kwota będzie równa kwocie fakturowana dla towaru.</span><span class="sxs-lookup"><span data-stu-id="eb76f-197"><strong>Invoice amount</strong> – The amount will be equal to the amount that is invoiced for the commodity.</span></span></li>
<li><span data-ttu-id="eb76f-198"><strong>Kwota podstawy</strong> – kwota będzie równa kwocie, która zostałaby zafakturowana przed zastosowaniem rabatów.</span><span class="sxs-lookup"><span data-stu-id="eb76f-198"><strong>Base amount</strong> – The amount will be equal to the amount that would be invoiced before any discount is applied.</span></span></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb76f-199">Metody transportu</span><span class="sxs-lookup"><span data-stu-id="eb76f-199">Transport methods</span></span></td>
<td><span data-ttu-id="eb76f-200">Ustaw tryb transportu zgodnie z wymaganiami danego kraju/regionu.</span><span class="sxs-lookup"><span data-stu-id="eb76f-200">Set up the transport mode according to your country's/region's requirements.</span></span> <span data-ttu-id="eb76f-201">Dla każdej metody dostawy można skonfigurować domyślną metodę transportu na karcie <strong>Handel zagraniczny</strong>.</span><span class="sxs-lookup"><span data-stu-id="eb76f-201">For each delivery mode, you can set up a default transport method on the <strong>Foreign trade</strong> tab.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-202">Porty</span><span class="sxs-lookup"><span data-stu-id="eb76f-202">Ports</span></span></td>
<td><span data-ttu-id="eb76f-203">Skonfiguruj port/lotnisko załadunku/rozładunku, jeśli te informacje są gromadzone w danym kraju/regionie.</span><span class="sxs-lookup"><span data-stu-id="eb76f-203">Set up the port/airport of loading/unloading if this information is collected by your country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb76f-204">Procedury statystyczne</span><span class="sxs-lookup"><span data-stu-id="eb76f-204">Statistics procedures</span></span></td>
<td><span data-ttu-id="eb76f-205">Ustaw procedury statystyczne, jeśli te informacje są gromadzone w danym kraju/regionie.</span><span class="sxs-lookup"><span data-stu-id="eb76f-205">Set up the statistical procedure if this information is collected by your country/region.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a><span data-ttu-id="eb76f-206">Konfigurowanie reguł kompresowania transakcji Intrastat</span><span class="sxs-lookup"><span data-stu-id="eb76f-206">Set up rules for compressing Intrastat transactions</span></span>

<span data-ttu-id="eb76f-207">Na stronie **Kompresja Intrastat** można wybrać pola, które mają być używane dla kompresji.</span><span class="sxs-lookup"><span data-stu-id="eb76f-207">On the **Compression of Intrastat** page, you can select the fields to use for compression.</span></span> <span data-ttu-id="eb76f-208">Wszystkie transakcje zawierające tą samą kombinację wartości dla wybranych pól w dzienniku Intrastat zostaną skompresowane w jedną transakcję podczas wykonywania funkcji kompresowania w dzienniku Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-208">All transactions that have the same combination of values for the selected fields in the Intrastat journal will be compressed into a single transaction when you run the Compress function in the Intrastat journal.</span></span>

### <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="eb76f-209">Konfigurowanie parametrów handlu zagranicznego</span><span class="sxs-lookup"><span data-stu-id="eb76f-209">Set up foreign trade parameters</span></span>

<span data-ttu-id="eb76f-210">Użyj strony **Parametry handlu zagranicznego**, aby skonfigurować parametry w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="eb76f-210">Use the **Foreign trade parameters** page to set up the parameters in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb76f-211">Tabulator</span><span class="sxs-lookup"><span data-stu-id="eb76f-211">Tab</span></span></th>
<th><span data-ttu-id="eb76f-212">Parametry</span><span class="sxs-lookup"><span data-stu-id="eb76f-212">Parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="eb76f-213">Ogólne</span><span class="sxs-lookup"><span data-stu-id="eb76f-213">General</span></span></td>
<td><ul>
<li><span data-ttu-id="eb76f-214"><strong>Ogólne</strong> — pozwala określić następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="eb76f-214"><strong>General</strong> – Specify the following information:</span></span>
<ul>
<li><span data-ttu-id="eb76f-215">Domyślne kody transakcji dla zamówień sprzedaży, zamówień zakupu, faktur korygujących i zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="eb76f-215">The default transaction codes for sales orders, purchase orders, credit notes, and transfer orders.</span></span> <span data-ttu-id="eb76f-216">Kod transakcji ustawiony dla faktur korygujących jest również używany jako kod zwrotu towarów fizycznych i jest używany do obsługi odchyleń zwrotów towarów fizycznych względem faktur korygujących.</span><span class="sxs-lookup"><span data-stu-id="eb76f-216">The transaction code that is set up for credit notes is also used as the code for physical goods return and is used for deviating physical returns versus correction credit notes.</span></span></li>
<li><span data-ttu-id="eb76f-217">Pracownik odpowiedzialny za przygotowywanie raportów Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-217">The employee who is responsible for preparing Intrastat reports.</span></span></li>
</ul></li>
<li><span data-ttu-id="eb76f-218"><strong>Minimalny limit</strong> — pozwala określić ustawienia aktualizacji transakcji, które są poniżej progu:</span><span class="sxs-lookup"><span data-stu-id="eb76f-218"><strong>Minimum limit</strong> – Specify the settings for updating transactions that are below the threshold:</span></span>
<ul>
<li><span data-ttu-id="eb76f-219">Kwota i waga progu</span><span class="sxs-lookup"><span data-stu-id="eb76f-219">The threshold amount and weight</span></span></li>
<li><span data-ttu-id="eb76f-220">Kod asortymentu do zastosowania do transakcji będących pod progiem</span><span class="sxs-lookup"><span data-stu-id="eb76f-220">The commodity code to apply to transactions that are under the threshold</span></span></li>
</ul></li>
<li><span data-ttu-id="eb76f-221"><strong>Przenieś</strong> — pozwala określić kryteria przenoszenia transakcji do dziennika Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-221"><strong>Transfer</strong> – Specify the criteria for transferring transactions to the Intrastat journal.</span></span> <span data-ttu-id="eb76f-222">Można określić, że transakcje są przenoszone tylko wtedy, gdy towary spełniają co najmniej następujące kryteria:</span><span class="sxs-lookup"><span data-stu-id="eb76f-222">You can specify that transactions are transferred only when the items meet one or all of the following criteria:</span></span>
<ul>
<li><span data-ttu-id="eb76f-223">Towary nie są usługą.</span><span class="sxs-lookup"><span data-stu-id="eb76f-223">The items aren't service items.</span></span></li>
<li><span data-ttu-id="eb76f-224">Towary mają kod asortymentu.</span><span class="sxs-lookup"><span data-stu-id="eb76f-224">The items have a commodity code.</span></span></li>
<li><span data-ttu-id="eb76f-225">Towary mają wagę.</span><span class="sxs-lookup"><span data-stu-id="eb76f-225">The items have a weight.</span></span></li>
<li><span data-ttu-id="eb76f-226">Towary mają dodatkowe jednostki.</span><span class="sxs-lookup"><span data-stu-id="eb76f-226">The items have additional units.</span></span></li>
</ul></li>
<li><span data-ttu-id="eb76f-227"><strong>Sprawdź ustawienia</strong> — pozwala określić reguły sprawdzania kompletności danych Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-227"><strong>Check setup</strong> – Specify the rules for validating the completeness of Intrastat data.</span></span> <span data-ttu-id="eb76f-228">Można wybrać, które dane mają być sprawdzane.</span><span class="sxs-lookup"><span data-stu-id="eb76f-228">You can select which data is validated.</span></span></li>
<li><span data-ttu-id="eb76f-229"><strong>Reguły zaokrąglania</strong> — pozwala określić następujące ustawienia do zaokrąglania kwot i wagi w raportach Intrastat:</span><span class="sxs-lookup"><span data-stu-id="eb76f-229"><strong>Rounding rules</strong> – Specify the following settings for rounding amounts and weights in Intrastat reporting:</span></span>
<ul>
<li><span data-ttu-id="eb76f-230">Typ reguły zaokrąglania (precyzyjna)</span><span class="sxs-lookup"><span data-stu-id="eb76f-230">The rounding rule (precision)</span></span></li>
<li><span data-ttu-id="eb76f-231">Reguła zaokrąglania: w górę, w dół lub normalnie.</span><span class="sxs-lookup"><span data-stu-id="eb76f-231">The rounding method: up, down, or normal</span></span></li>
<li><span data-ttu-id="eb76f-232">Liczba miejsc dziesiętnych dla kwot i wag</span><span class="sxs-lookup"><span data-stu-id="eb76f-232">The number of decimal places for amounts and weights</span></span></li>
<li><span data-ttu-id="eb76f-233">Instrukcje dotyczące zaokrąglania wag poniżej 1 kilograma (kg): w górę do 1 kg, normalnie lub bez zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="eb76f-233">Instructions for rounding weights that are less than 1 kilogram (kg): up to 1 kg, normal, or no rounding</span></span></li>
</ul></li>
<li><span data-ttu-id="eb76f-234"><strong>Raportowanie elektroniczne</strong> — umożliwia określenie odwołania do konfiguracji raportowania elektronicznego, tak aby można było wygenerować plik elektroniczny i raport.</span><span class="sxs-lookup"><span data-stu-id="eb76f-234"><strong>Electronic reporting</strong> – Specify references to electronic reporting configurations, so that you can generate an electronic file and report.</span></span></li>
<li><span data-ttu-id="eb76f-235"><strong>Hierarchia kodów asortymentu</strong> — pozwala określić hierarchię kategorii typu <strong>Kod asortymentu</strong>, która reprezentuje kod asortymentu Intrastat CN8.</span><span class="sxs-lookup"><span data-stu-id="eb76f-235"><strong>Commodity code hierarchy</strong> – Specify the category hierarchy of the <strong>Commodity code</strong> type that represents Intrastat commodity code CN8.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-236">Dane kontaktowe agenta</span><span class="sxs-lookup"><span data-stu-id="eb76f-236">Agent contact information</span></span></td>
<td><span data-ttu-id="eb76f-237">Wpisywanie imienia i nazwiska, adresu numeru identyfikacji podatkowej, numeru telefonu i numeru faksu agenta.</span><span class="sxs-lookup"><span data-stu-id="eb76f-237">Specify the agent's name, address, tax exempt number, telephone number, and fax number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="eb76f-238">Właściwości kraju/regionu</span><span class="sxs-lookup"><span data-stu-id="eb76f-238">Country/region properties</span></span></td>
<td><span data-ttu-id="eb76f-239">Ustawianie kraju/regionu aktualnie zaznaczonej firmy jako <strong>Krajowa</strong>.</span><span class="sxs-lookup"><span data-stu-id="eb76f-239">Set the country/region of the current legal entity to <strong>Domestic</strong>.</span></span> <span data-ttu-id="eb76f-240">Ustawianie kraju/regionu w UE, dla kraju/regionu UE który uczestniczy w handlu wewnątrz UE z aktualną firmą, jako <strong>UE</strong>.</span><span class="sxs-lookup"><span data-stu-id="eb76f-240">Set the country/region of EU countries/regions that participate in EU trade with the current legal entity to <strong>EU</strong>.</span></span> <span data-ttu-id="eb76f-241">Dla każdego kraju/regionu możesz też określić kod kraju/regionu dla handlu zagranicznego.</span><span class="sxs-lookup"><span data-stu-id="eb76f-241">For each country/region, you also identify country/region code for foreign trade purposes.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="eb76f-242">Sekwencja numerów</span><span class="sxs-lookup"><span data-stu-id="eb76f-242">Number sequence</span></span></td>
<td><span data-ttu-id="eb76f-243">Określanie kodu identyfikacyjnego dla dziennika Intrastat.</span><span class="sxs-lookup"><span data-stu-id="eb76f-243">Specify the number sequence for the Intrastat journal.</span></span></td>
</tr>
</tbody>
</table>

 




