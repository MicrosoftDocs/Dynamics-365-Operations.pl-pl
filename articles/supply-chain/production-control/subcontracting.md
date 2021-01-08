---
title: Podwykonawstwo
description: Ten temat pomoże stworzyć przewodnik funkcjonalności podwykonawstwa w produkcji w programie Dynamics 365 Supply Chain Management.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1cc1040393d843f39ca8c741a7c51435c7169c00
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434959"
---
# <a name="subcontracting"></a><span data-ttu-id="298fd-103">Podwykonawstwo</span><span class="sxs-lookup"><span data-stu-id="298fd-103">Subcontracting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="298fd-104">Ten temat pomoże stworzyć przewodnik funkcjonalności podwykonawstwa w produkcji w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="298fd-104">This topic will help you build a walkthrough of subcontracting in manufacturing in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="298fd-105">W pierwszej części tego tematu opisano konfigurację danych.</span><span class="sxs-lookup"><span data-stu-id="298fd-105">The first part of this topic describes the setup of the data.</span></span> <span data-ttu-id="298fd-106">Druga część prowadzi przez kolejne kroki przewodnika.</span><span class="sxs-lookup"><span data-stu-id="298fd-106">The second part takes you through the steps in the walkthrough.</span></span>

## <a name="target-audience"></a><span data-ttu-id="298fd-107">Odbiorcy docelowi</span><span class="sxs-lookup"><span data-stu-id="298fd-107">Target audience</span></span>

<span data-ttu-id="298fd-108">W tym temacie dowiesz się, jak skonfigurować podwykonawstwo w produkcji.</span><span class="sxs-lookup"><span data-stu-id="298fd-108">In this topic, you will learn how to set up subcontracting in manufacturing.</span></span> <span data-ttu-id="298fd-109">Wykorzystując istniejące dane z firmy HQUS, skonfigurujesz podstawowe ustawienia przepływu działań podwykonawczych.</span><span class="sxs-lookup"><span data-stu-id="298fd-109">You will use existing data in the HQUS legal entity to do the basic setup of a subcontracting activity flow.</span></span> <span data-ttu-id="298fd-110">Dane demonstracyjne firmy HQUS obejmują parametry konfiguracyjne, w których wstępnie ustawiono obsługę kroków przewodnika.</span><span class="sxs-lookup"><span data-stu-id="298fd-110">The demo data in the HQUS legal entity includes setup parameters that have been preset to support the steps in the walkthrough.</span></span> <span data-ttu-id="298fd-111">Co prawda przewodnik nawiązuje do głównych problemów i wyzwań występujących w różnych rolach, ale całość może wykonać administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="298fd-111">Even though the walkthrough addresses key pain points and challenges for various roles, it can be completed by the system admin.</span></span>

## <a name="demo-scenario"></a><span data-ttu-id="298fd-112">Scenariusz demonstracji</span><span class="sxs-lookup"><span data-stu-id="298fd-112">Demo scenario</span></span>

<span data-ttu-id="298fd-113">W firmie HQUS są wytwarzane głośniki wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="298fd-113">In the HQUS legal entity, high-end speakers are manufactured.</span></span> <span data-ttu-id="298fd-114">W procesie produkcji głośniki przechodzą przez następujące trzy operacje.</span><span class="sxs-lookup"><span data-stu-id="298fd-114">During the manufacturing process, speakers go through the following three operations.</span></span>

- <span data-ttu-id="298fd-115">**Wstępny montaż** — jest montowana obudowa głośnika.</span><span class="sxs-lookup"><span data-stu-id="298fd-115">**Pre-assembly** – The speaker cabinet is assembled.</span></span> <span data-ttu-id="298fd-116">Materiał na obudowę jest pobierany z magazynu materiałów przed rozpoczęciem operacji.</span><span class="sxs-lookup"><span data-stu-id="298fd-116">The material for the cabinet is picked in the material warehouse before the operation is started.</span></span>
- <span data-ttu-id="298fd-117">**Malowanie** — po zmontowaniu głośnika należy go pomalować.</span><span class="sxs-lookup"><span data-stu-id="298fd-117">**Coating** – After the speaker cabinet has been assembled, it must be coated.</span></span> <span data-ttu-id="298fd-118">Ta operacja jest wykonywana przez zewnętrznego dostawcę (podwykonawcę).</span><span class="sxs-lookup"><span data-stu-id="298fd-118">This operation is completed by a vendor (subcontractor).</span></span> <span data-ttu-id="298fd-119">Wstępnie złożona obudowa głośnika jest wysyłana do podwykonawcy świadczącego usługi lakiernicze razem z dwoma materiałami.</span><span class="sxs-lookup"><span data-stu-id="298fd-119">The pre-assembled speaker cabinet is shipped to the coating subcontractor together with two materials.</span></span>
- <span data-ttu-id="298fd-120">**Wykańczanie** — gdy podwykonawca pomaluje wstępnie złożoną obudowę głośnika, wraca ona do firmy HQUS, która dokonuje końcowego montażu głośnika.</span><span class="sxs-lookup"><span data-stu-id="298fd-120">**Finish** – After the pre-assembled speaker cabinet has been coated by the subcontractor, it's returned to the HQUS legal entity so that final assembly of the speaker can be completed.</span></span>

<span data-ttu-id="298fd-121">Poniższa ilustracja przedstawia trzy operacje oraz materiały, które są w nich wykorzystywane.</span><span class="sxs-lookup"><span data-stu-id="298fd-121">The following illustration shows the three operations and the materials that they consume.</span></span>

![Operacje Wstępny montaż, Malowanie i Wykańczanie, oraz zużywane w nich materiały](./media/subcontract01_operations-materials.png)

## <a name="setup"></a><span data-ttu-id="298fd-123">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="298fd-123">Setup</span></span>

<span data-ttu-id="298fd-124">Przed rozpoczęciem przewodnika należy skonfigurować dane.</span><span class="sxs-lookup"><span data-stu-id="298fd-124">Before you start the walkthrough, you must set up the data.</span></span>

### <a name="set-up-the-finished-product"></a><span data-ttu-id="298fd-125">Konfigurowanie wyrobu gotowego</span><span class="sxs-lookup"><span data-stu-id="298fd-125">Set up the finished product</span></span>

<span data-ttu-id="298fd-126">Ta procedura prowadzi przez konfigurowanie zwolnionego produktu D8100 „Pomalowana obudowa”.</span><span class="sxs-lookup"><span data-stu-id="298fd-126">This procedure takes you through the setup of released product D8100, "Coated Cabinet."</span></span>

1. <span data-ttu-id="298fd-127">Wybierz kolejno opcje **Zarządzanie informacjami o produktach \> Produkty \> Zwolnione produkty**, aby otworzyć stronę **Szczegóły zwolnionego produktu**.</span><span class="sxs-lookup"><span data-stu-id="298fd-127">Select **Product information management \> Products \> Released products** to open the **Released product details** page.</span></span>
2. <span data-ttu-id="298fd-128">W polu szybkiego filtru wpisz **D8100**, aby znaleźć istniejący zwolniony produkt.</span><span class="sxs-lookup"><span data-stu-id="298fd-128">In the quick filter field, enter **D8100** to find the existing released product.</span></span>

    ![Filtrowanie w celu znalezienia zwolnionego produktu D8100 na stronie Szczegóły zwolnionego produktu](./media/subcontract02_filtering-released-products.png)

3. <span data-ttu-id="298fd-130">W okienku akcji na karcie **Konstruuj** wybierz opcję **Marszruta**, aby otworzyć stronę **Marszruta**.</span><span class="sxs-lookup"><span data-stu-id="298fd-130">On the Action Pane, on the **Engineer** tab, select **Route** to open the **Route** page.</span></span>

    <span data-ttu-id="298fd-131">Strona **Marszruta** zawiera osiem wersji marszruty zwolnionego produktu D8100.</span><span class="sxs-lookup"><span data-stu-id="298fd-131">The **Route** page shows the eight route versions for released product D8100.</span></span> <span data-ttu-id="298fd-132">Osiem wersji marszruty jest rozdzielonych między cztery marszruty w oddziałach 1 i 5.</span><span class="sxs-lookup"><span data-stu-id="298fd-132">The eight route versions are divided among four routes on site 1 and site 5.</span></span> <span data-ttu-id="298fd-133">Marszruta 000400 jest używana do wyceny, marszruta 00041 jest używana w sytuacji, gdy operacja Malowanie jest wykonywana wewnętrznie, a marszruta 00042 jest stosowana dla operacji Malowanie zlecanej na zewnątrz.</span><span class="sxs-lookup"><span data-stu-id="298fd-133">Route 000400 is used for costing, route 00041 is used when the Coating operation is an internal operation, and route 00042 is used when the Coating operation is an external operation.</span></span>

    ![Osiem wersji marszruty na stronie Marszruta](./media/subcontract03_route-page.png)

4. <span data-ttu-id="298fd-135">W górnym okienku w siatce **Wersje** wybierz wersję marszruty **00042** dla oddziału **5**.</span><span class="sxs-lookup"><span data-stu-id="298fd-135">In the upper pane, in the **Versions** grid, select route version **00042** for site **5**.</span></span>
5. <span data-ttu-id="298fd-136">W dolnym okienku na karcie **Przegląd** wybierz w siatce operację **20** (**Cbnt CtSc**).</span><span class="sxs-lookup"><span data-stu-id="298fd-136">In the lower pane, on the **Overview** tab, select operation **20** (**Cbnt CtSc**) in the grid.</span></span>

    ![Wybrana operacja 20 dla wersji marszruty 00042 w oddziale 5](./media/subcontract04_route-version-operation.png)

6. <span data-ttu-id="298fd-138">Kliknij kartę **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-138">Select the **General** tab.</span></span>

    <span data-ttu-id="298fd-139">Zauważ, że pole **Typ marszruty** jest ustawione na **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="298fd-139">Notice that the field **Route type** field is set to **Vendor**.</span></span> <span data-ttu-id="298fd-140">Ta wartość wskazuje, że operacja 20 (Cbnt CtSc) jest operacją podwykonawczą.</span><span class="sxs-lookup"><span data-stu-id="298fd-140">This value indicates that operation 20 (Cbnt CtSc) is a subcontracted operation.</span></span>

    ![Pole Typ marszruty z ustawioną wartością Dostawca na karcie Ogólne](./media/subcontract05_general-tab.png)

7. <span data-ttu-id="298fd-142">Kliknij kartę **Zapotrzebowanie na zasoby**.</span><span class="sxs-lookup"><span data-stu-id="298fd-142">Select the **Resource requirements** tab.</span></span>

    <span data-ttu-id="298fd-143">Do wyszukiwania odpowiednich zasobów podczas planowania produkcji będą wykorzystywane możliwości.</span><span class="sxs-lookup"><span data-stu-id="298fd-143">Capabilities will be used to find an applicable resource during production scheduling.</span></span> <span data-ttu-id="298fd-144">Dla operacji 20 (Cbnt CtSc) zauważ, że jest wymagany zasób mający dwie możliwości — **Malowanie** i **Malowane obudowy**.</span><span class="sxs-lookup"><span data-stu-id="298fd-144">For operation 20 (Cbnt CtSc), notice that a resource that has two capabilities, **Coating** and **Coated cabinets**, is required.</span></span>

    ![Możliwości Malowanie i Malowane obudowy na karcie Zapotrzebowanie na zasoby](./media/subcontract06_resource-requirements-tab.png)

8. <span data-ttu-id="298fd-146">Wybierz opcję **Pasujące zasoby**, aby otworzyć okno dialogowe **Pasujące zasoby**.</span><span class="sxs-lookup"><span data-stu-id="298fd-146">Select **Applicable resources** to open the **Applicable resources** dialog box.</span></span>

    <span data-ttu-id="298fd-147">Zostały znalezione trzy zasoby spełniające zapotrzebowania na zasoby dla operacji.</span><span class="sxs-lookup"><span data-stu-id="298fd-147">Three resources are found that match the resource requirements for the operation.</span></span> <span data-ttu-id="298fd-148">Zauważ, że zasoby 8851 i 8852 są typu **Dostawca**.</span><span class="sxs-lookup"><span data-stu-id="298fd-148">Notice that resources 8851 and 8852 are of the **Vendor** type.</span></span>

    ![Trzy właściwe zasoby w oknie dialogowym Pasujące zasoby](./media/subcontract07_applicable-resources-dialog.png)

9. <span data-ttu-id="298fd-150">Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Pasujące zasoby** i wrócić do strony **Marszruta**.</span><span class="sxs-lookup"><span data-stu-id="298fd-150">Select **OK** to close the **Applicable resources** dialog box and return to the **Route** page.</span></span>
10. <span data-ttu-id="298fd-151">Zamknij stronę **Marszruta**, aby wrócić do strony **Szczegóły zwolnionego produktu**.</span><span class="sxs-lookup"><span data-stu-id="298fd-151">Close the **Route** page to return to the **Released product details** page.</span></span>

    ![Strona Szczegóły zwolnionego produktu](./media/subcontract08_released-product-details-page.png)

11. <span data-ttu-id="298fd-153">W okienku akcji na karcie **Konstruuj** wybierz opcję **Wersje BOM**, aby otworzyć stronę **Wersje BOM**.</span><span class="sxs-lookup"><span data-stu-id="298fd-153">On the Action Pane, on the **Engineer** tab, select **BOM versions** to open the **BOM versions** page.</span></span>

    <span data-ttu-id="298fd-154">Na stronie **Wersje BOM** znajdują się cztery wersje listy składowej (BOM) zwolnionego produktu D8100.</span><span class="sxs-lookup"><span data-stu-id="298fd-154">The **BOM versions** page shows the four bill of materials (BOM) versions for released product D8100.</span></span> <span data-ttu-id="298fd-155">BOM 000040 służy do wyceny i planowania, BOM 000041 do operacji Malowanie wykonywanej w zakładzie, a BOM 000042 i 000043 do operacji Malowanie wykonywanych przez podwykonawcę.</span><span class="sxs-lookup"><span data-stu-id="298fd-155">BOM 000040 is used for costing and planning, BOM 000041 is used if the Coating operation is done in-house, and BOMs 000042 and 000043 are used if the Coating operation is subcontracted.</span></span>

    <span data-ttu-id="298fd-156">Zauważ, że pozycja S8050 jest produktem o typie towaru **Usługa**.</span><span class="sxs-lookup"><span data-stu-id="298fd-156">Notice that item S8050 is a product of the **Service** item type.</span></span> <span data-ttu-id="298fd-157">Ta pozycja reprezentuje pracę podwykonawczą.</span><span class="sxs-lookup"><span data-stu-id="298fd-157">This item represents the subcontracted work.</span></span>

    ![Cztery wersje BOM na stronie Wersje BOM](./media/subcontract09_bom-versions-page.png)

12. <span data-ttu-id="298fd-159">Na skróconej karcie **Wiersze listy składowej (BOM)** wybierz opcję **Edytuj**, aby otworzyć okno dialogowe **Edytuj wiersz BOM**.</span><span class="sxs-lookup"><span data-stu-id="298fd-159">On the **Bill of materials lines** FastTab, select **Edit** to open the **Edit BOM line** dialog box.</span></span>

    <span data-ttu-id="298fd-160">Gdy dla zwolnionego produktu D8100 zostanie utworzone i oszacowane zlecenie produkcyjne, dla towaru S8050 zostanie automatycznie wygenerowane zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="298fd-160">When a production order is created and estimated for released product D8100, a purchase order will be automatically generated for item S8050.</span></span> <span data-ttu-id="298fd-161">To zamówienie zakupu będzie połączone ze zleceniem produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="298fd-161">This purchase order will be linked to the production order.</span></span> <span data-ttu-id="298fd-162">Aby zamówienia zakupu były generowane automatycznie, pole **Typ wiersza** musi mieć wartość **Dostawca** oraz musi być wybrane konto dostawcy dla podwykonawcy.</span><span class="sxs-lookup"><span data-stu-id="298fd-162">For purchase orders to be automatically generated, the **Line type** field must be set to **Vendor**, and the vendor account for the subcontractor must be selected.</span></span> <span data-ttu-id="298fd-163">W tym przypadku kontem dostawcy jest US-801.</span><span class="sxs-lookup"><span data-stu-id="298fd-163">In this case, the vendor account is US-801.</span></span>

    <span data-ttu-id="298fd-164">Zauważ, że wiersz BOM jest połączony z operacją Malowanie za pośrednictwem numeru operacji (w tym przypadku 20).</span><span class="sxs-lookup"><span data-stu-id="298fd-164">Notice that the BOM line is connected to the Coating operation through the operation number (in this case, 20).</span></span>

    ![Okno dialogowe Edytuj wiersz BOM](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a><span data-ttu-id="298fd-166">Tworzenie hasła dla pracowników magazynu</span><span class="sxs-lookup"><span data-stu-id="298fd-166">Create a password for warehouse workers</span></span>

<span data-ttu-id="298fd-167">Należy utworzyć hasło dla pracowników magazynu używających ręcznego urządzenia.</span><span class="sxs-lookup"><span data-stu-id="298fd-167">You must define a password for the warehouse workers who use the hand-held device.</span></span>

1. <span data-ttu-id="298fd-168">Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Pracownik**, aby otworzyć stronę **Użytkownicy pracy**.</span><span class="sxs-lookup"><span data-stu-id="298fd-168">Select **Warehouse management \> Setup \> Worker** to open the **Work users** page.</span></span>
2. <span data-ttu-id="298fd-169">Na skróconej karcie **Użytkownicy** zaznacz wiersz użytkownika **51**.</span><span class="sxs-lookup"><span data-stu-id="298fd-169">On the **Users** FastTab, select the row for user **51**.</span></span>

    ![Strona Użytkownicy pracy](./media/subcontract11_work-users-page.png)

3. <span data-ttu-id="298fd-171">Wybierz opcję **Resetuj hasło**.</span><span class="sxs-lookup"><span data-stu-id="298fd-171">Select **Reset password**.</span></span>
4. <span data-ttu-id="298fd-172">W polach **Hasło** i **Potwierdź hasło** wprowadź **1**.</span><span class="sxs-lookup"><span data-stu-id="298fd-172">In the **Password** and **Confirm password** fields, enter **1**.</span></span>
5. <span data-ttu-id="298fd-173">Wybierz opcję **Ustaw hasło**.</span><span class="sxs-lookup"><span data-stu-id="298fd-173">Select **Set password**.</span></span>

## <a name="step-by-step-walkthrough"></a><span data-ttu-id="298fd-174">Przewodnik krok po kroku</span><span class="sxs-lookup"><span data-stu-id="298fd-174">Step-by-step walkthrough</span></span>

<span data-ttu-id="298fd-175">**Scenariusz i kontekst**</span><span class="sxs-lookup"><span data-stu-id="298fd-175">**Scenario and background**</span></span>

<span data-ttu-id="298fd-176">Zlecenie produkcyjne na 10 sztuk jest tworzone dla produktu D8100 „Pomalowana obudowa”.</span><span class="sxs-lookup"><span data-stu-id="298fd-176">A production order of 10 pieces is created for product D8100, "Coated Cabinet."</span></span> <span data-ttu-id="298fd-177">Malowanie obudów jest operacją zlecaną na zewnątrz, wykonywaną u dostawcy US-801 Perfect Coating Solutions.</span><span class="sxs-lookup"><span data-stu-id="298fd-177">The coating of the cabinets is a sub-contracted operation that is done at vendor US-801, Perfect Coating Solutions.</span></span> <span data-ttu-id="298fd-178">Zlecenie produkcyjne obejmuje trzy operacje.</span><span class="sxs-lookup"><span data-stu-id="298fd-178">The production order consists of three operations.</span></span> <span data-ttu-id="298fd-179">W pierwszej operacji obudowa jest wstępnie montowana wewnętrznie w zakładzie.</span><span class="sxs-lookup"><span data-stu-id="298fd-179">In the first operation, the cabinet is pre-assembled as an in-house operation.</span></span> <span data-ttu-id="298fd-180">Materiał do wstępnego montażu jest zwalniany do pobrania w magazynie surowców.</span><span class="sxs-lookup"><span data-stu-id="298fd-180">The material for the pre-assembly is released for picking in the raw material warehouse.</span></span> <span data-ttu-id="298fd-181">Po zakończeniu wstępnego montażu wstępnie złożona obudowa jest wysyłana do Perfect Coating Solutions razem z dwoma materiałami, które są wymagane do operacji Malowanie.</span><span class="sxs-lookup"><span data-stu-id="298fd-181">After the pre-assembly is completed, the pre-assembled cabinet is sent to Perfect Coating Solutions together with two materials that are required for the Coating operation.</span></span> <span data-ttu-id="298fd-182">Po odebraniu pomalowanej obudowy od dostawcy przechodzi ona w zakładzie końcową operację montażu, po czym jest zgłaszana jako wyrób gotowy.</span><span class="sxs-lookup"><span data-stu-id="298fd-182">When the coated cabinet is received back from the vendor, it goes through a final in-house assembly operation before it's reported as finished.</span></span>

1. <span data-ttu-id="298fd-183">Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**, aby otworzyć stronę **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-183">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
2. <span data-ttu-id="298fd-184">W okienku akcji wybierz opcję **Nowe zlecenie produkcyjne**, aby otworzyć okno dialogowe **Tworzenie zlecenia produkcyjnego**.</span><span class="sxs-lookup"><span data-stu-id="298fd-184">On the Action Pane, select **New production order** to open the **Create production order** dialog box.</span></span>

    ![Okno dialogowe Tworzenie zlecenia produkcyjnego](./media/subcontract12_create-production-order-dialog.png)

3. <span data-ttu-id="298fd-186">W polu **Numer pozycji** wybierz wartość **D8100**.</span><span class="sxs-lookup"><span data-stu-id="298fd-186">In the **Item number** field, select **D8100**.</span></span>
4. <span data-ttu-id="298fd-187">Po wybraniu numeru towaru pojawią się pola wymiarów magazynowych.</span><span class="sxs-lookup"><span data-stu-id="298fd-187">After you select the item number, fields for the inventory dimensions appear.</span></span> <span data-ttu-id="298fd-188">W polu **Kolor** wybierz wartość **Chrom**.</span><span class="sxs-lookup"><span data-stu-id="298fd-188">In the **Color** field, select **Chrome**.</span></span>

    <span data-ttu-id="298fd-189">Pojawi się okno komunikatu z pytaniem, czy należy wstawić aktywne wersje BOM i marszruty.</span><span class="sxs-lookup"><span data-stu-id="298fd-189">A message box appears that asks whether the active versions for the BOM and route should be inserted.</span></span>

    ![Okno komunikatu](./media/subcontract13_message-box.png)

5. <span data-ttu-id="298fd-191">Wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="298fd-191">Select **Yes**.</span></span> 

    <span data-ttu-id="298fd-192">W oknie dialogowym **Tworzenie zlecenia produkcyjnego** aktywne wersje BOM i marszruty dla produktu D8100 są automatycznie wybierane odpowiednio w polach **Numer BOM** i **Numer marszruty**.</span><span class="sxs-lookup"><span data-stu-id="298fd-192">In the **Create production order** dialog box, the active versions of the BOM and route for product D8100 are automatically selected in the **BOM number** and **Route number** fields, respectively.</span></span> <span data-ttu-id="298fd-193">W tym przypadku są zaznaczone wartości BOM **000040** i marszruty **000040**.</span><span class="sxs-lookup"><span data-stu-id="298fd-193">In this case, BOM **000040** and route **000040** are selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="298fd-194">Zarówno dla BOM, jak i dla marszruty na potrzeby wyceny i planowania jest używana wersja 000040.</span><span class="sxs-lookup"><span data-stu-id="298fd-194">For both the BOM and the route, version 000040 is used for costing and planning.</span></span>

6. <span data-ttu-id="298fd-195">W polu **Oddział** wybierz wartość **5**.</span><span class="sxs-lookup"><span data-stu-id="298fd-195">In the **Site** field, select **5**.</span></span>
7. <span data-ttu-id="298fd-196">W polu **Magazyn** wybierz wartość **51**.</span><span class="sxs-lookup"><span data-stu-id="298fd-196">In the **Warehouse** field, select **51**.</span></span>
8. <span data-ttu-id="298fd-197">W polach **Numer BOM** i **Numer marszruty** zmień automatycznie wybraną wartość na **000042**.</span><span class="sxs-lookup"><span data-stu-id="298fd-197">In the **BOM number** and **Route number** fields, change the value that was automatically selected to **000042**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="298fd-198">Zarówno dla BOM, jak i dla marszruty wersja 000042 jest używana do zlecenia podwykonawstwa malowania obudowy do dostawcy US-801.</span><span class="sxs-lookup"><span data-stu-id="298fd-198">For both the BOM and the route, version 000042 is used to subcontract the coating of the cabinet to vendor US-801.</span></span>

    ![Wartości ustawiane w oknie dialogowym Tworzenie zlecenia produkcyjnego](./media/subcontract14_create-production-order-dialog-set.png)

9. <span data-ttu-id="298fd-200">Wybierz opcję **Utwórz**, aby utworzyć zlecenie produkcyjne i wrócić do strony **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-200">Select **Create** to create the production order and return to the **All production orders** page.</span></span>

    ![Nowe zlecenie produkcyjne na stronie Wszystkie zlecenia produkcyjne](./media/subcontract15_new-production-order.png)

10. <span data-ttu-id="298fd-202">W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Szacuj**, aby otworzyć okno dialogowe **Szacowanie**.</span><span class="sxs-lookup"><span data-stu-id="298fd-202">On the Action Pane, on the **Production order** tab, select **Estimate** to open the **Estimate** dialog box.</span></span>

    ![Okno dialogowe Szacowanie](./media/subcontract16_estimate-dialog.png)

11. <span data-ttu-id="298fd-204">Wybierz opcję **OK**, aby potwierdzić oszacowanie i wrócić do strony **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-204">Select **OK** to confirm the estimate and return to the **All production orders** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="298fd-205">Podczas szacowania zlecenia produkcyjnego jest generowane zamówienie zakupu na usługę S8050 dla dostawcy US-801.</span><span class="sxs-lookup"><span data-stu-id="298fd-205">When the production order is estimated, the purchase order for service item S8050 is generated for vendor US-801.</span></span>

12. <span data-ttu-id="298fd-206">W okienku akcji na karcie **Zlecenie produkcyjne** wybierz opcję **BOM**, aby otworzyć stronę **BOM**, gdzie można przejrzeć wiersze BOM zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="298fd-206">On the Action Pane, on the **Production order** tab, select **BOM** to open the **BOM** page, where you can view the BOM lines for the production order.</span></span>

    <span data-ttu-id="298fd-207">Dla usługi S8050 zauważ, że istnieje odwołanie do zamówienia zakupu wygenerowanego podczas szacowania zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="298fd-207">For service item S8050, notice that there is a reference to the purchase order that was generated when the production order was estimated.</span></span>

    ![Wiersze BOM zlecenia produkcyjnego na stronie BOM](./media/subcontract17_production-order-bom-lines.png)

13. <span data-ttu-id="298fd-209">Zamknij stronę **BOM**, aby wrócić do strony **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-209">Close the **BOM** page to return to the **All production orders** page.</span></span>
14. <span data-ttu-id="298fd-210">W okienku akcji na karcie **Harmonogram** kliknij opcję **Planowanie zadań**, aby otworzyć okno dialogowe **Planowanie zadań**.</span><span class="sxs-lookup"><span data-stu-id="298fd-210">On the Action Pane, on the **Schedule** tab, select **Schedule jobs** to open the **Job scheduling** dialog box.</span></span>
15. <span data-ttu-id="298fd-211">Wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="298fd-211">Specify the following values:</span></span>

    - <span data-ttu-id="298fd-212">W polu **Kierunek planowania** wybierz opcję **W przód od jutra**.</span><span class="sxs-lookup"><span data-stu-id="298fd-212">In the **Scheduling direction** field, select **Forward from tomorrow**.</span></span>
    - <span data-ttu-id="298fd-213">Ustaw opcję **Ograniczone zdolności produkcyjne** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="298fd-213">Set the **Finite capacity** option to **Yes**.</span></span>

    ![Okno dialogowe Planowanie zadań](./media/subcontract18_job-scheduling-dialog.png)

16. <span data-ttu-id="298fd-215">Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Planowanie zadań** i wrócić do strony **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-215">Select **OK** to close the **Job scheduling** dialog box and return to the **All production orders** page.</span></span>
17. <span data-ttu-id="298fd-216">W okienku akcji na karcie **Harmonogram** wybierz opcję **Wykres Gantta**, aby otworzyć stronę **Wykres Gantta — Widok zasobów**.</span><span class="sxs-lookup"><span data-stu-id="298fd-216">On the Action Pane, on the **Schedule** tab, select **Gantt** to open the **Gantt chart - Resource view** page.</span></span>

    <span data-ttu-id="298fd-217">Wykres Gantta zawiera graficzną prezentację rozplanowania zasobów w zadaniach produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="298fd-217">The Gantt chart provides a visual overview of how the production jobs are scheduled on the resources.</span></span> <span data-ttu-id="298fd-218">Zwróć uwagę, że zewnętrzna operacja malowanie składa się z trzech zadań: zadania przetwarzania, zadania transportowania i zadania czasu oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="298fd-218">Notice that the external Coating operation consists of three jobs: a process job, a transport job, and a queue time job.</span></span>

    ![Wykres Gantta na stronie Wykres Gantta — Widok zasobów](./media/subcontract19_gantt-chart.png)

18. <span data-ttu-id="298fd-220">Zamknij stronę **Wykres Gantta — Widok zasobów**, aby wrócić do strony **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-220">Close the **Gantt chart - Resource view** page to return to the **All production orders** page.</span></span>
19. <span data-ttu-id="298fd-221">W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Zwolnij**, aby otworzyć okno dialogowe **Zwolnienie**.</span><span class="sxs-lookup"><span data-stu-id="298fd-221">On the Action Pane, on the **Production order** tab, select **Release** to open the **Release** dialog box.</span></span>

    ![Okno dialogowe Zwalnianie](./media/subcontract20_release-dialog.png)

20. <span data-ttu-id="298fd-223">Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Zwalnianie**.</span><span class="sxs-lookup"><span data-stu-id="298fd-223">Select **OK** to close the **Release** dialog box.</span></span>
21. <span data-ttu-id="298fd-224">Wybierz kolejno opcje **Kontrola produkcji \> Zadania okresowe \> Zwolnij do magazynu \> Automatyczne zwalnianie wierszy BOM i formuły**, aby otworzyć okno dialogowe **Automatyczne zwalnianie wierszy BOM i formuły**.</span><span class="sxs-lookup"><span data-stu-id="298fd-224">Select **Production control \> Periodic tasks \> Release to warehouse \> Automatic release of BOM and formula lines** to open the **Automatic release of BOM and formula lines** dialog box.</span></span>

    ![Okno dialogowe Automatyczne zwalnianie wierszy BOM i formuły](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. <span data-ttu-id="298fd-226">Kliknij przycisk **OK**, aby uruchomić zadanie Automatyczne zwalnianie wierszy BOM i formuły.</span><span class="sxs-lookup"><span data-stu-id="298fd-226">Select **OK** to run the Automatic release of BOM and formula lines job.</span></span>

    <span data-ttu-id="298fd-227">To zadanie zwalnia pracę pobrania surowców do magazynu.</span><span class="sxs-lookup"><span data-stu-id="298fd-227">This job releases pick work for raw materials to the warehouse.</span></span>

23. <span data-ttu-id="298fd-228">Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**, aby otworzyć stronę **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-228">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
24. <span data-ttu-id="298fd-229">Za pomocą pola szybkiego filtru zaznacz zlecenie produkcyjne, nad którym pracujesz.</span><span class="sxs-lookup"><span data-stu-id="298fd-229">Use the quick filter field to select the production order that you've been working on.</span></span>
25. <span data-ttu-id="298fd-230">W okienku akcji na karcie **Magazyn** wybierz opcję **Szczegóły pracy**, aby otworzyć stronę **Praca**.</span><span class="sxs-lookup"><span data-stu-id="298fd-230">On the Action Pane, on the **Warehouse** tab, select **Work details** to open the **Work** page.</span></span>

    <span data-ttu-id="298fd-231">Zwróć uwagę, że na stronie są widoczne dwa zestawy pracy pobrania surowca.</span><span class="sxs-lookup"><span data-stu-id="298fd-231">Notice that the page shows two sets of work for raw material picking.</span></span> <span data-ttu-id="298fd-232">Pierwsza pracy dotyczy materiałów M8100 i M8101.</span><span class="sxs-lookup"><span data-stu-id="298fd-232">The first work is for materials M8100 and M8101.</span></span> <span data-ttu-id="298fd-233">Te materiały są zużywane przez operację 10.</span><span class="sxs-lookup"><span data-stu-id="298fd-233">These materials are consumed by operation 10.</span></span> <span data-ttu-id="298fd-234">Druga pracy dotyczy materiałów M8202 i M8250.</span><span class="sxs-lookup"><span data-stu-id="298fd-234">The second work is for materials M8202 and M8250.</span></span> <span data-ttu-id="298fd-235">Te materiały są zużywane przez operację 20, która jest operacją podwykonawczą.</span><span class="sxs-lookup"><span data-stu-id="298fd-235">These materials are consumed by operation 20, which is the subcontracted operation.</span></span>

    ![Dwa zestawy pracy pobrania surowców na stronie Praca](./media/subcontract22_work-page.png)

26. <span data-ttu-id="298fd-237">Uruchom aplikację magazynową, aby wykonać przetwarzanie pracy magazynowej dla operacji 10.</span><span class="sxs-lookup"><span data-stu-id="298fd-237">Start the warehouse app to process the warehouse work for operation 10.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. <span data-ttu-id="298fd-238">Wybierz kolejno opcje **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**, aby otworzyć stronę **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-238">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
28. <span data-ttu-id="298fd-239">Za pomocą pola szybkiego filtru zaznacz zlecenie produkcyjne, nad którym pracujesz.</span><span class="sxs-lookup"><span data-stu-id="298fd-239">Use the quick filter field to select the production order that you've been working on.</span></span>
29. <span data-ttu-id="298fd-240">W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Rozpocznij**, aby otworzyć okno dialogowe **Rozpoczęcie**.</span><span class="sxs-lookup"><span data-stu-id="298fd-240">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
30. <span data-ttu-id="298fd-241">Na karcie **Ogólne** wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="298fd-241">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="298fd-242">W polu **Od nr operacji**</span><span class="sxs-lookup"><span data-stu-id="298fd-242">In the **From Oper. No.**</span></span> <span data-ttu-id="298fd-243">wybierz wartość **10**.</span><span class="sxs-lookup"><span data-stu-id="298fd-243">field, select **10**.</span></span>
    - <span data-ttu-id="298fd-244">W polu **Do nr operacji**</span><span class="sxs-lookup"><span data-stu-id="298fd-244">In the **To Oper. No.**</span></span> <span data-ttu-id="298fd-245">wybierz wartość **10**.</span><span class="sxs-lookup"><span data-stu-id="298fd-245">field, select **10**.</span></span>

    ![Wartości ustawiane na karcie Ogólne](./media/subcontract23_start-dialog.png)

31. <span data-ttu-id="298fd-247">Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Rozpoczęcie** i wrócić do strony **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-247">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="298fd-248">Zauważ, że stan zlecenia produkcyjnego został zmieniony na **Rozpoczęte**.</span><span class="sxs-lookup"><span data-stu-id="298fd-248">Notice that the status of the production order is now **Started**.</span></span> <span data-ttu-id="298fd-249">Materiały dla operacji 10 są używane poprzez automatyczne zaksięgowanie arkusza listy pobrania.</span><span class="sxs-lookup"><span data-stu-id="298fd-249">The materials for operation 10 are consumed by an automatic posting of the picking list journal.</span></span> <span data-ttu-id="298fd-250">Zużycie czasu w operacji 10 jest uwzględniane poprzez automatyczne zaksięgowanie arkusza karty marszruty.</span><span class="sxs-lookup"><span data-stu-id="298fd-250">Time consumption for operation 10 is accounted for by an automatic posting of a route card journal.</span></span>

32. <span data-ttu-id="298fd-251">Uruchom aplikację magazynową, aby wykonać przetwarzanie pracy magazynowej dla operacji 20.</span><span class="sxs-lookup"><span data-stu-id="298fd-251">Start the warehouse app to process the warehouse work for operation 20.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. <span data-ttu-id="298fd-252">W okienku akcji na karcie **Zlecenie produkcyjne** kliknij opcję **Rozpocznij**, aby otworzyć okno dialogowe **Rozpoczęcie**.</span><span class="sxs-lookup"><span data-stu-id="298fd-252">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
34. <span data-ttu-id="298fd-253">Na karcie **Ogólne** wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="298fd-253">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="298fd-254">W polu **Od nr operacji**</span><span class="sxs-lookup"><span data-stu-id="298fd-254">In the **From Oper. No.**</span></span> <span data-ttu-id="298fd-255">wybierz wartość **20**.</span><span class="sxs-lookup"><span data-stu-id="298fd-255">field, select **20**.</span></span>
    - <span data-ttu-id="298fd-256">W polu **Do nr operacji**</span><span class="sxs-lookup"><span data-stu-id="298fd-256">In the **To Oper. No.**</span></span> <span data-ttu-id="298fd-257">wybierz wartość **20**.</span><span class="sxs-lookup"><span data-stu-id="298fd-257">field, select **20**.</span></span>
    - <span data-ttu-id="298fd-258">W polu **Ilość** wpisz wartość **10**.</span><span class="sxs-lookup"><span data-stu-id="298fd-258">In the **Quantity** field, enter **10**.</span></span>
    - <span data-ttu-id="298fd-259">W opcji **Księgowanie listy pobrania** wybierz wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="298fd-259">Set the **Post picking list now** option to **No**.</span></span>

    ![Wartości ustawiane na karcie Ogólne](./media/subcontract24_general-tab.png)

35. <span data-ttu-id="298fd-261">Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Rozpoczęcie** i wrócić do strony **Wszystkie zlecenia produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="298fd-261">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="298fd-262">Dla materiałów zużywanych w operacji Malowanie oraz dla usługi zostanie utworzona lista pobrania.</span><span class="sxs-lookup"><span data-stu-id="298fd-262">A picking list is created for the materials that are used for the Coating operation, and for the service item.</span></span> <span data-ttu-id="298fd-263">Usługa reprezentuje koszt operacji podwykonawczej.</span><span class="sxs-lookup"><span data-stu-id="298fd-263">The service item represents the cost of the subcontracted operation.</span></span>

36. <span data-ttu-id="298fd-264">W okienku akcji na karcie **Widok** wybierz opcję **Lista pobrania**, aby otworzyć stronę **Lista pobrania**.</span><span class="sxs-lookup"><span data-stu-id="298fd-264">On the Action Pane, on the **View** tab, select **Picking list** to open the **Picking list** page.</span></span>
37. <span data-ttu-id="298fd-265">Zaznacz listę pobrania, która nie jest zaksięgowana, a następnie wybierz numer arkusza, aby wyświetlić wiersze arkusza.</span><span class="sxs-lookup"><span data-stu-id="298fd-265">Select the picking list that isn't posted, and then select the journal number to view the journal lines.</span></span>

    ![Wiersze arkusza na stronie Lista pobrania](./media/subcontract25_picking-list.png)

38. <span data-ttu-id="298fd-267">W okienku akcji wybierz kolejno opcje **Drukuj** \> **Raport Lista pobrania**, aby otworzyć okno dialogowe **Raport Lista pobrania**.</span><span class="sxs-lookup"><span data-stu-id="298fd-267">On the Action Pane, select **Print** \> **Picking list report** to open the **Picking list report** dialog box.</span></span>
39. <span data-ttu-id="298fd-268">Ustaw opcję **Użyj układu dokumentu dostawy** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="298fd-268">Set the **Use delivery note layout** option to **Yes**.</span></span>

    ![Okno dialogowe Raport listy pobrania](./media/subcontract26_picking-list-report-dialog.png)

40. <span data-ttu-id="298fd-270">Kliknij przycisk **OK**, aby wygenerować raport **Lista pobrania**.</span><span class="sxs-lookup"><span data-stu-id="298fd-270">Select **OK** to generate a **Picking list** report.</span></span>

    <span data-ttu-id="298fd-271">W tym przypadku jest drukowany dokument dostawy dostawcy z poziomu arkusza listy pobrania do produkcji.</span><span class="sxs-lookup"><span data-stu-id="298fd-271">In this case, a vendor delivery note is printed from the production picking list journal.</span></span> <span data-ttu-id="298fd-272">Dokument dostawy określa materiały, które zostaną wysłane do dostawcy mającego wykonać operację Malowanie.</span><span class="sxs-lookup"><span data-stu-id="298fd-272">The delivery note specifies the materials that are shipped to the vendor who will do the Coating operation.</span></span>

    ![Raport list pobrania](./media/subcontract27_picking-list-report.png)

41. <span data-ttu-id="298fd-274">Zamknij raport **Lista pobrania**, aby wrócić do strony **Lista pobrania**.</span><span class="sxs-lookup"><span data-stu-id="298fd-274">Close the **Picking list** report to return to the **Picking list** page.</span></span>
42. <span data-ttu-id="298fd-275">W okienku akcji kliknij opcję **Księguj**, aby otworzyć okno dialogowe **Księgowanie arkusza**.</span><span class="sxs-lookup"><span data-stu-id="298fd-275">On the Action Pane, select **Post** to open the **Post journal** dialog box.</span></span>

    ![Okno dialogowe Księgowanie arkusza](./media/subcontract28_post-journal-dialog.png)

43. <span data-ttu-id="298fd-277">Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Księgowanie arkusza**.</span><span class="sxs-lookup"><span data-stu-id="298fd-277">Select **OK** to close the **Post journal** dialog box.</span></span>
44. <span data-ttu-id="298fd-278">Otwórz zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="298fd-278">Open the purchase order.</span></span>

    ![Strona Zamówienie zakupu](./media/subcontract29_purchase-order-page.png)

45. <span data-ttu-id="298fd-280">W okienku akcji na karcie **Zakup** wybierz opcję **Potwierdź**.</span><span class="sxs-lookup"><span data-stu-id="298fd-280">On the Action Pane, on the **Purchase** tab, select **Confirm**.</span></span>
46. <span data-ttu-id="298fd-281">Kliknij przycisk **Księguj**, aby otworzyć okno dialogowe **Księgowanie arkusza**.</span><span class="sxs-lookup"><span data-stu-id="298fd-281">Select **Post** to open the **Post journal** dialog box.</span></span>
47. <span data-ttu-id="298fd-282">Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Księgowanie arkusza** i wrócić do strony **Zamówienie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="298fd-282">Select **OK** to close the **Post journal** dialog box and return to the **Purchase order** page.</span></span>
48. <span data-ttu-id="298fd-283">Zmień cenę jednostkową z **33** na **40**.</span><span class="sxs-lookup"><span data-stu-id="298fd-283">Change the unit price from **33** to **40**.</span></span>

    ![Cena jednostkowa zmieniona na stronie Zamówienie zakupu](./media/subcontract30_unit-price.png)

49. <span data-ttu-id="298fd-285">Ponownie potwierdź zamówienie zakupu.</span><span class="sxs-lookup"><span data-stu-id="298fd-285">Confirm the purchase order again.</span></span>
50. <span data-ttu-id="298fd-286">Przyjęcie produktu.</span><span class="sxs-lookup"><span data-stu-id="298fd-286">Product receipt.</span></span>

    ![Okno dialogowe Księgowanie dokumentu przyjęcia produktów](./media/subcontract31_posting-product-receipt-dialog.png)

51. <span data-ttu-id="298fd-288">Faktura zakupu.</span><span class="sxs-lookup"><span data-stu-id="298fd-288">Purchase invoice.</span></span>
52. <span data-ttu-id="298fd-289">Zaktualizuj stan uzgadniania.</span><span class="sxs-lookup"><span data-stu-id="298fd-289">Update the match status.</span></span>

    ![Strona Faktura od dostawcy](./media/subcontract32_vendor-invoice-page.png)

53. <span data-ttu-id="298fd-291">Zgłoś wyroby gotowe.</span><span class="sxs-lookup"><span data-stu-id="298fd-291">Report as finished.</span></span>

    ![Okno dialogowe Zgłoszenie wyrobów gotowych](./media/subcontract33_report-as-finished-dialog.png)

54. <span data-ttu-id="298fd-293">Zakończ.</span><span class="sxs-lookup"><span data-stu-id="298fd-293">End.</span></span>

    ![Okno dialogowe Zakończenie](./media/subcontract34_end-dialog.png)

55. <span data-ttu-id="298fd-295">Porównanie kosztów.</span><span class="sxs-lookup"><span data-stu-id="298fd-295">Cost comparison.</span></span>

    ![Wykresy porównania kosztów](./media/subcontract35_cost-comparison-charts.png)

<span data-ttu-id="298fd-297">Brak danych konfiguracyjnych.</span><span class="sxs-lookup"><span data-stu-id="298fd-297">Missing setup in data.</span></span>
