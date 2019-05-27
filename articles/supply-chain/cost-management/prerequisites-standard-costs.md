---
title: Wymagania wstępne dla kosztów standardowych
description: W tym temacie opisano podstawowe czynności związane z używaniem kosztów standardowych.
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5a4a4e49ef1cee923011ddab24497c65f85c1e3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547820"
---
# <a name="prerequisites-for-standard-costs"></a><span data-ttu-id="f2c2e-103">Wymagania wstępne dla kosztów standardowych</span><span class="sxs-lookup"><span data-stu-id="f2c2e-103">Prerequisites for standard costs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2c2e-104">W tym temacie opisano podstawowe czynności związane z używaniem kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-104">This topic describes the basic steps for using standard costs.</span></span> <span data-ttu-id="f2c2e-105">Kolejne czynności zależą od specyfiki działalności firmy.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-105">Subsequent steps depend on the company's operations.</span></span> <span data-ttu-id="f2c2e-106">Na przykład są inne dla środowiska nieprodukcyjnego, środowiska produkcyjnego bez marszrut oraz środowiska produkcyjnego wykorzystującego marszruty.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-106">For example, the steps differ for a nonmanufacturing environment, a manufacturing environment that doesn't use routings, and a manufacturing environment that uses routings.</span></span> 

<span data-ttu-id="f2c2e-107">Aby skonfigurować koszty standardowe, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-107">To set up standard costs, follow these steps.</span></span>

<span data-ttu-id="f2c2e-108">**1. Utwórz grupę modeli pozycji opartą na kosztach standardowych.**</span><span class="sxs-lookup"><span data-stu-id="f2c2e-108">**1. Create an item model group for standard costs.**</span></span>

<span data-ttu-id="f2c2e-109">Na stronie **Grupy modeli pozycji** utwórz nową grupę dla kosztów standardowych oraz przypisz jej model zapasów **Koszt standardowy**.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-109">Use the **Item model groups** page to create a new group for standard costs, and assign an inventory model of **Standard cost**.</span></span> <span data-ttu-id="f2c2e-110">Identyfikator grupy modeli pozycji powinien być jednoznaczny, np. **Koszt standardowy**.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-110">The identifier for the item model group should be meaningful, such as **Std Cost**.</span></span> <span data-ttu-id="f2c2e-111">Zaznacz odpowiednie pola wyboru, aby grupa zezwalała na ujemne wartości zapasów finansowych oraz wymuszała księgowanie zapasów fizycznych i finansowych.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-111">Select the check boxes to indicate that the group should allow financial negative inventory, and that it should post physical inventory and financial inventory.</span></span> <span data-ttu-id="f2c2e-112">Ta grupa kosztów standardowych zostanie przypisana do towarów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-112">This standard cost group will be assigned to items.</span></span>

<span data-ttu-id="f2c2e-113">**2. Zdefiniuj konta księgowe skojarzone z odchyleniami kosztu standardowego.**</span><span class="sxs-lookup"><span data-stu-id="f2c2e-113">**2. Define ledger accounts that are related to standard cost variances.**</span></span> 

<span data-ttu-id="f2c2e-114">Strona **Plan kont** służy do definiowania kont księgowych skojarzonych z odchyleniami kosztu standardowego.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-114">Use the **Chart of accounts** page to define ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="f2c2e-115">Te konta księgowe należy zdefiniować przed ich przypisaniem na stronie **Księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-115">These ledger accounts must be defined before they can be assigned on the **Posting** page.</span></span> <span data-ttu-id="f2c2e-116">Konta księgowe mogą uwzględniać grupy towarów i grupy kosztów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-116">The ledger accounts can reflect item groups and cost groups.</span></span>

<span data-ttu-id="f2c2e-117">**3. Przypisz konta księgowe do księgowań pozycji (towarów) skojarzonych z odchyleniami kosztu standardowego.**</span><span class="sxs-lookup"><span data-stu-id="f2c2e-117">**3. Assign ledger accounts to item postings that are related to standard cost variances.**</span></span> 

<span data-ttu-id="f2c2e-118">Strona **Księgowanie** służy do przypisywania kont księgowych skojarzonych z odchyleniami kosztu standardowego.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-118">Use the **Posting** page to assign the ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="f2c2e-119">Można zdefiniować konto księgowe odchyleń według towaru (lub grupy towarów) i według grupy kosztów (lub typu grupy kosztów) albo określić, że konto księgowe dotyczy wszystkich towarów oraz wszystkich grup kosztów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-119">You can specify a variance's ledger account by item (or item group) and by cost group (or cost group type), or you can specify that the ledger account applies to all items and all cost groups.</span></span> <span data-ttu-id="f2c2e-120">Te opcje odpowiadają relacjom kosztów dla tabel, grup i wszystkich elementów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-120">These options correspond to cost relations for tables, groups, and all.</span></span> 

<span data-ttu-id="f2c2e-121">Zanim zdefiniujesz zasady księgowania pozycji, na stronie **Kombinacje transakcji** włącz funkcję relacji kosztowych (dla tabel, grup i wszystkich elementów).</span><span class="sxs-lookup"><span data-stu-id="f2c2e-121">Before you define the item posting rules, use the **Transaction combinations** page to enable cost relations (for tables, groups, and all).</span></span>

<span data-ttu-id="f2c2e-122">**4. Zdefiniuj parametry zapasów skojarzone z kosztami standardowymi.**</span><span class="sxs-lookup"><span data-stu-id="f2c2e-122">**4. Define inventory parameters that are related to standard costs.**</span></span> 

-  <span data-ttu-id="f2c2e-123">Na karcie **Księgowanie zapasów** dostępnej na stronie **Ustawienia zasad księgowania zapasów > Parametry** zdefiniuj dwa parametry kontroli kosztów powiązane z kosztami standardowymi.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-123">Use the **Inventory accounting** tab on the **Inventory accounting policies setup > Parameters** page to define two cost control parameters that are related to standard costs.</span></span>

    -  <span data-ttu-id="f2c2e-124">W polu **Podział kosztów** wybierz opcję **Brak** lub **Księga podrzędna**.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-124">In the **Cost breakdown** field, select **None** or **Sub ledger**.</span></span> <span data-ttu-id="f2c2e-125">W przypadku wybrania opcji **Księga podrzędna** podziałem kosztów jest *aktywny* podziału kosztów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-125">If you select **Sub ledger**, the cost breakdown is an *active* cost breakdown.</span></span> <span data-ttu-id="f2c2e-126">Aktywne rozbicie kosztów ma kluczowe znaczenie w obliczaniu, zachowywaniu i wyświetlaniu podziału grupy kosztów w wielopoziomowej strukturze produktów dla towarów, którym przypisano koszt standardowy.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-126">An active cost breakdown is critical for calculating, retaining, and viewing cost group segmentation across a multilevel product structure for standard cost items.</span></span> <span data-ttu-id="f2c2e-127">Jeśli podział kosztów jest aktywny, można raportować oraz analizować zapasy, pracę w toku i koszt własny sprzedaży przypadający na grupę kosztów na jednym poziomie, na wielu poziomach lub w formacie sumarycznym.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-127">When the cost breakdown is active, you can report and analyze inventory, work in process (WIP), and cost of goods sold (COGS) per cost group in a single-level, multilevel, or total format.</span></span> <span data-ttu-id="f2c2e-128">Jeśli podział kosztów jest aktywny, aktywowanie kosztu wytworzonego towaru spowoduje zapisanie segmentacji grupy kosztów w rekordzie kosztu towaru.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-128">When the cost breakdown is active, if you activate a manufactured item's cost, the cost group segmentation will be stored in the item's cost record.</span></span> 

    -  <span data-ttu-id="f2c2e-129">W przypadku wybrania wartości **Brak** segmentacja grupy kosztów nie będzie przechowywana dla towarów opartych na kosztach standardowych.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-129">If you select **None**, cost group segmentation won't be maintained for standard cost items.</span></span> <span data-ttu-id="f2c2e-130">Innymi słowy koszt standardowy wytworzonego towaru będzie obliczany i zachowywany jako jedna kwota, bez segmentacji grup kosztów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-130">In other words, a manufactured item's standard cost will be calculated and maintained as a single amount, without cost group segmentation.</span></span> <span data-ttu-id="f2c2e-131">Udział kosztów wytworzonych składników będzie obliczany jako jedna kwota.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-131">The cost contributions of manufactured components will be aggregated into the single amount.</span></span>

-  <span data-ttu-id="f2c2e-132">W polu **Odchylenia od standardu** wybierz opcję **Podsumowane** lub **Na grupę kosztów**.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-132">In the **Variances to standard** field, select **Summarized** or **Per cost group**.</span></span> <span data-ttu-id="f2c2e-133">Wybór opcji **Na grupę kosztów** umożliwi identyfikowanie odchyleń cen zakupu i odchyleń produkcji według grup kosztów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-133">If you select **Per cost group**, you can identify purchase price variances and production variances by cost group.</span></span> <span data-ttu-id="f2c2e-134">Można także zidentyfikować cztery typy odchyleń produkcji: wielkości partii, ilości, ceny i podstawiania.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-134">You can also identify the four types of production variances: the lot size, quantity, price, and substitution variances.</span></span> <span data-ttu-id="f2c2e-135">Wybór opcji **Podsumowane** spowoduje, że nie będzie można identyfikować odchyleń według grup kosztów ani czterech typów odchyleń produkcji.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-135">If you select **Summarized**, you can't identify variances by cost group, and you can't identify the four types of production variances.</span></span> <span data-ttu-id="f2c2e-136">Można tylko wyświetlać podsumowanie odchylenia produkcji.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-136">You can just view a summarized production variance.</span></span>

-  <span data-ttu-id="f2c2e-137">Zasady zamiany odchyleń wartości standardowych działają niezależnie od zasad podziału kosztów, tj.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-137">The policy about variance to standard works independently of the cost breakdown policy.</span></span> <span data-ttu-id="f2c2e-138">Innymi słowy można wybrać zasadę podziału kosztów **Brak** i następnie wybrać odchylenia według grup kosztów, aby nadal były rejestrowane odchylenia produkcyjne z podziałem na grupy kosztów.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-138">In other words, you can select a cost breakdown policy of **None** and select variances per cost group, so that production variances by cost group will still be captured.</span></span>

<span data-ttu-id="f2c2e-139">**5. Utwórz wersje wyceny oparte na kosztach standardowych.**</span><span class="sxs-lookup"><span data-stu-id="f2c2e-139">**5. Create costing versions for standard costs.**</span></span> 

<span data-ttu-id="f2c2e-140">Na stronie **Konfiguracja wersji wyceny** można utworzyć jedną lub więcej wersji wyceny opartych na kosztach standardowych.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-140">Use the **Costing version setup** page to create one or more costing versions for standard costs.</span></span> <span data-ttu-id="f2c2e-141">Każda wersja wyceny musi mieć ustawiony typ wyceny **Kosz standardowy** i zezwalać na obecność danych kosztów w zawartości.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-141">Each costing version must be designated by a costing type of **Standard cost** and must allow content to include cost data.</span></span>

<span data-ttu-id="f2c2e-142">**6. Przygotuj istniejącego odbiorcę do używania kosztów standardowych.**</span><span class="sxs-lookup"><span data-stu-id="f2c2e-142">**6. Prepare an existing customer to use standard costs.**</span></span> 

<span data-ttu-id="f2c2e-143">Odbiorcy, którzy chcą przestawić istniejące towary na model zapasów z kosztem standardowym, muszą w tym celu użyć strony **Konwersje na koszt standardowy**.</span><span class="sxs-lookup"><span data-stu-id="f2c2e-143">Customers who want to change their existing items to a standard cost inventory model must use the **Standard cost conversions** page.</span></span>


<a name="related-topics"></a><span data-ttu-id="f2c2e-144">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="f2c2e-144">Related topics</span></span>
--------

[<span data-ttu-id="f2c2e-145">Omówienie konwersji na koszt standardowy</span><span class="sxs-lookup"><span data-stu-id="f2c2e-145">Standard cost conversion overview</span></span>](standard-cost-conversion-overview.md)

### <a name="blogs"></a><span data-ttu-id="f2c2e-146">Blogi</span><span class="sxs-lookup"><span data-stu-id="f2c2e-146">Blogs</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="f2c2e-147">Blogi społeczności</span><span class="sxs-lookup"><span data-stu-id="f2c2e-147">Community blogs</span></span>

- [<span data-ttu-id="f2c2e-148">Jak ustawić standardowe koszty w materiałów bezpośrednich w Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f2c2e-148">How to set up standard costs for direct materials in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [<span data-ttu-id="f2c2e-149">Koszty standardowe bezpośredniej robocizny w Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f2c2e-149">Standard direct labor costs in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)
