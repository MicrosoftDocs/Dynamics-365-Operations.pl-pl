---
title: "Pakiet zawartości usługi Power BI Wartości rzeczywiste a budżet"
description: "W tym temacie opisano pakiet zawartość Wartości rzeczywiste a budżet dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: ryansandness
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 2a0ad5af4e4d7da09690331dc9d1a51d2e97a664
ms.contentlocale: pl-pl
ms.lasthandoff: 12/01/2017

---

# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="57d56-104">Pakiet zawartości usługi Power BI Wartości rzeczywiste a budżet</span><span class="sxs-lookup"><span data-stu-id="57d56-104">Actual vs budget Power BI content</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="57d56-105">W tym temacie opisano pakiet zawartość **Wartości rzeczywiste a budżet** dostępny dla usługi Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="57d56-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="57d56-106">Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.</span><span class="sxs-lookup"><span data-stu-id="57d56-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span> 

# <a name="overview"></a><span data-ttu-id="57d56-107">Przegląd</span><span class="sxs-lookup"><span data-stu-id="57d56-107">Overview</span></span>

<span data-ttu-id="57d56-108">Pakiet zawartości usługi Power BI **Wartości rzeczywiste a budżet** jest przeznaczony dla osób odpowiedzialnych za monitorowanie wartości rzeczywistych w porównaniu z zabudżetowanymi w swoich organizacjach.</span><span class="sxs-lookup"><span data-stu-id="57d56-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="57d56-109">Pakiet zawartość usługi Power BI **Wartości rzeczywiste a budżet** zapewnia wgląd w odchylenia budżetu.</span><span class="sxs-lookup"><span data-stu-id="57d56-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="57d56-110">Można analizować budżet dla bieżącego roku według kategorii kont, kodów budżetu, kont głównych, opisów konta głównego lub okresów obrachunkowych, aby lepiej zrozumieć przyczyny wszelkich odchyleń .</span><span class="sxs-lookup"><span data-stu-id="57d56-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span> 

# <a name="accessing-the-power-bi-content"></a><span data-ttu-id="57d56-111">Przechodzenie do pakietu zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="57d56-111">Accessing the Power BI content</span></span>
<span data-ttu-id="57d56-112">Raporty z pakietów zawartości usługi Power BI **Wartości rzeczywiste a budżet** są wyświetlane w obszarach roboczych **Budżet księgi i prognozy** i **Dyrektor finansowy**.</span><span class="sxs-lookup"><span data-stu-id="57d56-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

# <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="57d56-113">Raporty umieszczone w pakiecie zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="57d56-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="57d56-114">W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości dla usługi Power BI **Wartości rzeczywiste a budżet** .</span><span class="sxs-lookup"><span data-stu-id="57d56-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="57d56-115">Raport</span><span class="sxs-lookup"><span data-stu-id="57d56-115">Report</span></span>                      | <span data-ttu-id="57d56-116">Metryki</span><span class="sxs-lookup"><span data-stu-id="57d56-116">Metrics</span></span> |
|-----------------------------|---------|
| <span data-ttu-id="57d56-117">Wydatki — wartości rzeczywiste a budżet</span><span class="sxs-lookup"><span data-stu-id="57d56-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="57d56-118">Łączne wydatki w roku</span><span class="sxs-lookup"><span data-stu-id="57d56-118">Total expenses this year</span></span></li><li><span data-ttu-id="57d56-119">Łączne zabudżetowane wydatki w roku</span><span class="sxs-lookup"><span data-stu-id="57d56-119">Budget total expenses this year</span></span></li></ul> |
| <span data-ttu-id="57d56-120">Przychody — wartości rzeczywiste a budżet</span><span class="sxs-lookup"><span data-stu-id="57d56-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="57d56-121">Łączne przychody w roku</span><span class="sxs-lookup"><span data-stu-id="57d56-121">Total revenue this year</span></span></li><li><span data-ttu-id="57d56-122">Łączne zabudżetowane przychody w roku</span><span class="sxs-lookup"><span data-stu-id="57d56-122">Budget total revenue this year</span></span></li><ul> |
| <span data-ttu-id="57d56-123">Wydatki</span><span class="sxs-lookup"><span data-stu-id="57d56-123">Expense</span></span>                     | <ul><li><span data-ttu-id="57d56-124">Łączne wydatki w roku</span><span class="sxs-lookup"><span data-stu-id="57d56-124">Total expenses this year</span></span></li><li><span data-ttu-id="57d56-125">Cel wydatków założony w budżecie</span><span class="sxs-lookup"><span data-stu-id="57d56-125">Goal for expenses based on budget</span></span> </li><ul> |
| <span data-ttu-id="57d56-126">Przychód</span><span class="sxs-lookup"><span data-stu-id="57d56-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="57d56-127">Łączne przychody w roku</span><span class="sxs-lookup"><span data-stu-id="57d56-127">Total revenue this year</span></span></li><li><span data-ttu-id="57d56-128">Cel przychodów założony w budżecie</span><span class="sxs-lookup"><span data-stu-id="57d56-128">Goal for revenue based on budget</span></span> </li><ul> |
| <span data-ttu-id="57d56-129">Dochód netto</span><span class="sxs-lookup"><span data-stu-id="57d56-129">Net income</span></span>                  | <ul><li><span data-ttu-id="57d56-130">Dochód netto w roku</span><span class="sxs-lookup"><span data-stu-id="57d56-130">Net income this year</span></span></li><li><span data-ttu-id="57d56-131">Cel dochodu netto założony w budżecie</span><span class="sxs-lookup"><span data-stu-id="57d56-131">Goal for net income based on budget</span></span> </li><ul> |

## <a name="extending-the-power-bi-content"></a><span data-ttu-id="57d56-132">Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="57d56-132">Extending the Power BI content</span></span>
<span data-ttu-id="57d56-133">Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="57d56-133">By using the content packs that are available in Microsoft Dynamics Lifecycle Services (LCS), you can provide great analytics to people who don't sign in to Microsoft Dynamics 365.</span></span> <span data-ttu-id="57d56-134">Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz.</span><span class="sxs-lookup"><span data-stu-id="57d56-134">You can modify these content packs so that they include other reports or visuals, and then publish the content packs to your Power BI.com tenant for analysis.</span></span> 

<span data-ttu-id="57d56-135">Pakiet zawartości usługi Power BI **Wartości rzeczywiste a budżet** znajduje się w bibliotece zasobów wspólnych w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="57d56-135">You can find the **Actual vs budget** Power BI content in the Shared assets library in LCS.</span></span> <span data-ttu-id="57d56-136">Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](power-bi-content-microsoft-partners.md).</span><span class="sxs-lookup"><span data-stu-id="57d56-136">For more information about how to download the content and implement it in your organization, see [Power BI content in LCS from Microsoft and your partners](power-bi-content-microsoft-partners.md).</span></span> <span data-ttu-id="57d56-137">Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).</span><span class="sxs-lookup"><span data-stu-id="57d56-137">To watch a demo that shows how to implement the Power BI content, see the [Power BI content from Microsoft and your partners in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.</span></span>

# <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="57d56-138">Opis modelu danych i jednostek</span><span class="sxs-lookup"><span data-stu-id="57d56-138">Understanding the data model and entities</span></span>

| <span data-ttu-id="57d56-139">Jednostka</span><span class="sxs-lookup"><span data-stu-id="57d56-139">Entity</span></span>                    | <span data-ttu-id="57d56-140">Zawartość</span><span class="sxs-lookup"><span data-stu-id="57d56-140">Contents</span></span> |
|---------------------------|----------|
| <span data-ttu-id="57d56-141">Działania na księdze głównej</span><span class="sxs-lookup"><span data-stu-id="57d56-141">General Ledger Activities</span></span> | <span data-ttu-id="57d56-142">Kwoty transakcji w księdze głównej</span><span class="sxs-lookup"><span data-stu-id="57d56-142">Transaction amounts for the general ledger</span></span> |
| <span data-ttu-id="57d56-143">Działania na budżecie</span><span class="sxs-lookup"><span data-stu-id="57d56-143">Budget Activities</span></span>         | <span data-ttu-id="57d56-144">Kwoty transakcji w rejestrze budżetu</span><span class="sxs-lookup"><span data-stu-id="57d56-144">Transaction amounts for the budget register</span></span> |
| <span data-ttu-id="57d56-145">Konta główne</span><span class="sxs-lookup"><span data-stu-id="57d56-145">Main Accounts</span></span>             | <span data-ttu-id="57d56-146">Konta główne, według których będą filtrowane raporty</span><span class="sxs-lookup"><span data-stu-id="57d56-146">Main accounts to filter reports by</span></span> |
| <span data-ttu-id="57d56-147">Kalendarze obrachunkowe</span><span class="sxs-lookup"><span data-stu-id="57d56-147">Fiscal Calendars</span></span>          | <span data-ttu-id="57d56-148">Kalendarze obrachunkowe, według których będą filtrowane raporty</span><span class="sxs-lookup"><span data-stu-id="57d56-148">Fiscal calendars to filter reports by</span></span> |
| <span data-ttu-id="57d56-149">Księgi</span><span class="sxs-lookup"><span data-stu-id="57d56-149">Ledgers</span></span>                   | <span data-ttu-id="57d56-150">Księgi, które można wyfiltrować jako bieżące księgi dla raportu</span><span class="sxs-lookup"><span data-stu-id="57d56-150">Ledgers that can be used to filter the report to the current ledger</span></span> |
| <span data-ttu-id="57d56-151">Kody budżetu</span><span class="sxs-lookup"><span data-stu-id="57d56-151">Budget Codes</span></span>              | <span data-ttu-id="57d56-152">Kody budżetu, według których będą filtrowane raporty</span><span class="sxs-lookup"><span data-stu-id="57d56-152">Budget codes to filter reports by</span></span> |
| <span data-ttu-id="57d56-153">Firmy</span><span class="sxs-lookup"><span data-stu-id="57d56-153">Legal Entities</span></span>            | <span data-ttu-id="57d56-154">Firmy, które można wyfiltrować jako bieżące firmy dla raportu</span><span class="sxs-lookup"><span data-stu-id="57d56-154">Legal entities that can be used to filter the report to the current legal entity</span></span> |

