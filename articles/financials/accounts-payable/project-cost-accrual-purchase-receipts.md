---
title: "Naliczanie kosztów projektu w przyjęciach zakupów"
description: "W tym temacie opisano, jak koszty projektu naliczone z przyjęć zakupów można śledzić w programie Microsoft Dynamics 365 for Finance and Operations."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a0aaa5941807199a64e6541960dbcdf83fedb47e
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="44144-103">Naliczanie kosztów projektu w przyjęciach zakupów</span><span class="sxs-lookup"><span data-stu-id="44144-103">Project cost accrual on purchase receipts</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="44144-104">W tym temacie opisano, jak koszty projektu naliczone z przyjęć zakupów można śledzić w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="44144-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="44144-105">Faktury za projekt często przychodzą później niż są dostarczane towary i usługi, co może mieć znaczący wpływ na kluczowe wskaźniki wydajności (KPI) projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="44144-106">Ważna jest możliwość śledzenia tych transakcji w sprawozdaniach finansowych i raportach z projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="44144-107">Ilustruje to przykładowy scenariusz opisany poniżej.</span><span class="sxs-lookup"><span data-stu-id="44144-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="44144-108">Firma Contoso Consulting rozpoczęła nowy projekt wdrożenia chmury.</span><span class="sxs-lookup"><span data-stu-id="44144-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="44144-109">Utworzono zamówienie zakupu na zakup komputera do projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="44144-110">Komputer będzie kosztować 1500 USD, a usługi instalacyjne dodatkowe 150 USD.</span><span class="sxs-lookup"><span data-stu-id="44144-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="44144-111">Dostawca dostarczył i zainstalował komputer, ale faktura jeszcze nie dotarła do Contoso Consulting.</span><span class="sxs-lookup"><span data-stu-id="44144-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="44144-112">Kierownik projektu chciałby widzieć naliczenie kosztów projektu w kwocie 1650 USD, zanim faktura zostanie dostarczona.</span><span class="sxs-lookup"><span data-stu-id="44144-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="44144-113">Ponadto koszt powinien znaleźć odzwierciedlenie w sprawozdaniu finansowym firmy na koniec miesiąca.</span><span class="sxs-lookup"><span data-stu-id="44144-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="44144-114">Dla celów sprawozdawczości naliczony koszt musi być zarejestrowany na poziomach finansowym i projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="44144-115">W programie Finance and Operations finansową aktualizację przyjęcia produktu można śledzić w kategoriach towaru i zaopatrzenia.</span><span class="sxs-lookup"><span data-stu-id="44144-115">In Finance and Operations, the financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="44144-116">W przypadku towarów na stronie **Parametry modułu rozrachunków z dostawcami** zaznacz opcję **Księguj przyjęcia produktów w księdze**.</span><span class="sxs-lookup"><span data-stu-id="44144-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="44144-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="44144-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="44144-118">Dla kategorii zaopatrzenia na stronie **Reguła kategorii** zaznacz zasady **Zakupy**, a następnie dla każdej kategorii zaopatrzenia zaznacz opcję **Naliczanie wydatku na zakup w momencie przyjęcia**.</span><span class="sxs-lookup"><span data-stu-id="44144-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="44144-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="44144-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="44144-120">Konta **Koszty zakupu niezafakturowane** i **Naliczenie zakupu** w oknie **Ustawienia księgowania** będą używane podczas księgowana załączników związanych z przyjęciem produktu.</span><span class="sxs-lookup"><span data-stu-id="44144-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>
<span data-ttu-id="44144-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span><span class="sxs-lookup"><span data-stu-id="44144-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span></span> 

<span data-ttu-id="44144-122">W tym samym scenariuszu zobaczmy, jak księgowanie przyjęcia produktu wpłynie na księgę główną i informacji o projekcie.</span><span class="sxs-lookup"><span data-stu-id="44144-122">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="44144-123">**Krok 1:** Utwórz i potwierdź nowe zamówienie zakupu dla projektu, aby zarejestrować zakup komputera za 1500 USD i usług instalacyjnych za 150 USD.</span><span class="sxs-lookup"><span data-stu-id="44144-123">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="44144-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="44144-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="44144-125">Po potwierdzeniu zamówienia zakupu zostaną dla projektu utworzone transakcje na ustalony koszt.</span><span class="sxs-lookup"><span data-stu-id="44144-125">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="44144-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="44144-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="44144-127">Transakcje na ustalony koszt będą miały w polu **Źródło transakcji** ustawioną wartość **Zamówienie zakupu**.</span><span class="sxs-lookup"><span data-stu-id="44144-127">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="44144-128">Utworzenie i potwierdzenie zamówienia zakupu nie tworzy transakcji dla projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-128">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="44144-129">**Krok 2:** Towary i usługi zostają dostarczone i następuje zarejestrowanie przyjęcia produktu.</span><span class="sxs-lookup"><span data-stu-id="44144-129">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="44144-130">Zaksięgowanie przyjęcia produktu spowoduje wygenerowanie załącznika i jego zaksięgowanie w księdze.</span><span class="sxs-lookup"><span data-stu-id="44144-130">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="44144-131">Załącznik zostanie zapisany po stronie debetowej na koncie niezafakturowanych kosztów zakupu, a po stronie uznaniowej na koncie naliczeń zakupu.</span><span class="sxs-lookup"><span data-stu-id="44144-131">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="44144-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="44144-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="44144-133">W celu zaksięgowania przyjęcia produktu będzie używana konfiguracja księgowania kategorii zaopatrzenia i produktów, a nie konfiguracja księgowania kategorii projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-133">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="44144-134">W celu właściwego wykazania finansowego wpływu naliczeń zakupu należy odpowiednio dopasować tę konfigurację.</span><span class="sxs-lookup"><span data-stu-id="44144-134">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="44144-135">Na stronie **Kategoria zaopatrzenia** można zamapować kategorie zaopatrzenia na kategorie projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-135">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="44144-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="44144-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="44144-137">**Krok 3:** Utwórz wersję roboczą faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="44144-137">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="44144-138">W programie Finance and Operations zaksięgowanie przyjęcia produktu nie wpływa na informacje o projekcie.</span><span class="sxs-lookup"><span data-stu-id="44144-138">In Finance and Operations, posting a product receipt does not impact project information.</span></span> <span data-ttu-id="44144-139">Aby obejść to zachowanie, można wygenerować wersję roboczą faktury od dostawcy natychmiast po zaksięgowaniu przyjęcia zakupu.</span><span class="sxs-lookup"><span data-stu-id="44144-139">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="44144-140">Przejdź do strony **Zamówienie zakupu** &gt; karta **Faktura** &gt; **Generuj** &gt; **fakturę**.</span><span class="sxs-lookup"><span data-stu-id="44144-140">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="44144-141">Zostanie utworzony dokument oczekującej faktury, który aktualizuje dane projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-141">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="44144-142">Utworzenie wersji roboczej faktury od dostawcy spowoduje generowanie oczekujących transakcji projektu.</span><span class="sxs-lookup"><span data-stu-id="44144-142">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="44144-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="44144-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="44144-144">Na stronie **Ustalony koszt** rekordy utworzone w kroku 1 zostaną zamknięte, a program utworzy nowe rekordy odzwierciedlające potwierdzenie kosztów pochodzące z oczekującej faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="44144-144">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="44144-145">Pole **Źródło transakcji** dotyczące ustalonego kosztu zostanie ustawione na wartość **Faktura od dostawcy**.</span><span class="sxs-lookup"><span data-stu-id="44144-145">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="44144-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="44144-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="44144-147">Faktura od dostawcy pozostanie w stanie oczekiwania do momentu nadejścia rzeczywistej faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="44144-147">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>




