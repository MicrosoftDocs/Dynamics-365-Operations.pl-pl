---
title: Pakiet zawartości Wartości rzeczywiste a budżet dostępny dla usługi Power BI
description: W tym temacie opisano pakiet zawartość Wartości rzeczywiste a budżet dostępny dla usługi Power BI. Wyjaśniono, jak uzyskać dostęp do raportów oferowanych w pakiecie, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.
author: ryansandness
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTrackingWorkspace
audience: Application user, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c801544e9e37a528203f5a1730aa8cb526d63dbf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553745"
---
# <a name="actual-vs-budget-power-bi-content"></a><span data-ttu-id="eb737-104">Pakiet zawartości Wartości rzeczywiste a budżet dostępny dla usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="eb737-104">Actual vs budget Power BI content</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb737-105">W tym temacie opisano pakiet zawartość **Wartości rzeczywiste a budżet** dostępny dla usługi Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="eb737-105">This topic describes the **Actual vs budget** Microsoft Power BI content.</span></span> <span data-ttu-id="eb737-106">Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.</span><span class="sxs-lookup"><span data-stu-id="eb737-106">It explains how to access the Power BI reports, and provides information about the data model and entities that were used to build the content.</span></span>

## <a name="overview"></a><span data-ttu-id="eb737-107">Przegląd</span><span class="sxs-lookup"><span data-stu-id="eb737-107">Overview</span></span>

<span data-ttu-id="eb737-108">Pakiet zawartości usługi Power BI **Wartości rzeczywiste** a budżet jest przeznaczony dla osób odpowiedzialnych za monitorowanie wartości rzeczywistych w porównaniu z zabudżetowanymi w swoich organizacjach.</span><span class="sxs-lookup"><span data-stu-id="eb737-108">The **Actual vs budget** Power BI content was created for individuals who are responsible for monitoring actual versus budget performance in their organization.</span></span> <span data-ttu-id="eb737-109">Pakiet zawartość usługi Power BI **Wartości rzeczywiste a budżet** zapewnia wgląd w odchylenia budżetu.</span><span class="sxs-lookup"><span data-stu-id="eb737-109">The **Actual vs budget** Power BI content provides visibility into your budget variances.</span></span> <span data-ttu-id="eb737-110">Można analizować budżet dla bieżącego roku według kategorii kont, kodów budżetu, kont głównych, opisów konta głównego lub okresów obrachunkowych, aby lepiej zrozumieć przyczyny wszelkich odchyleń .</span><span class="sxs-lookup"><span data-stu-id="eb737-110">You can analyze budget for the current year by account category, budget code, main account, main account descriptions, or fiscal period to get a better understanding of the cause of any variances.</span></span>

## <a name="accessing-the-power-bi-content"></a><span data-ttu-id="eb737-111">Przechodzenie do pakietu zawartości usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="eb737-111">Accessing the Power BI content</span></span>
<span data-ttu-id="eb737-112">Raporty z pakietów zawartości usługi Power BI **Wartości rzeczywiste a budżet** są wyświetlane w obszarach roboczych **Budżet księgi i prognozy** i **Dyrektor finansowy**.</span><span class="sxs-lookup"><span data-stu-id="eb737-112">Reports from the **Actual vs budget** Power BI content are shown in the **Ledger budget and forecasts** and **CFO** workspaces.</span></span>

## <a name="reports-that-are-included-in-the-power-bi-content"></a><span data-ttu-id="eb737-113">Raporty dostępne w pakiecie zawartości dla usługi Power BI</span><span class="sxs-lookup"><span data-stu-id="eb737-113">Reports that are included in the Power BI content</span></span>
<span data-ttu-id="eb737-114">W poniższej tabeli przedstawiono szczegóły dotyczące mierników, które znajdują się na każdej stronie raportu w pakiecie zawartości dla usługi Power BI **Wartości rzeczywiste a budżet**.</span><span class="sxs-lookup"><span data-stu-id="eb737-114">The following table provides details about the metrics that are found on each report page in the **Actual vs budget** Power BI content.</span></span>

| <span data-ttu-id="eb737-115">Raport</span><span class="sxs-lookup"><span data-stu-id="eb737-115">Report</span></span>                      | <span data-ttu-id="eb737-116">Metryki</span><span class="sxs-lookup"><span data-stu-id="eb737-116">Metrics</span></span>                                                                             |
|-----------------------------|-------------------------------------------------------------------------------------|
| <span data-ttu-id="eb737-117">Wydatki — wartości rzeczywiste a budżet</span><span class="sxs-lookup"><span data-stu-id="eb737-117">Expenses - Actual vs budget</span></span> | <ul><li><span data-ttu-id="eb737-118">Łączne wydatki w roku</span><span class="sxs-lookup"><span data-stu-id="eb737-118">Total expenses this year</span></span></li><li><span data-ttu-id="eb737-119">Łączne zabudżetowane wydatki w roku</span><span class="sxs-lookup"><span data-stu-id="eb737-119">Budget total expenses this year</span></span></li></ul>  |
| <span data-ttu-id="eb737-120">Przychody — wartości rzeczywiste a budżet</span><span class="sxs-lookup"><span data-stu-id="eb737-120">Revenue - Actual vs budget</span></span>  | <ul><li><span data-ttu-id="eb737-121">Łączne przychody w roku</span><span class="sxs-lookup"><span data-stu-id="eb737-121">Total revenue this year</span></span></li><li><span data-ttu-id="eb737-122">Łączne zabudżetowane przychody w roku</span><span class="sxs-lookup"><span data-stu-id="eb737-122">Budget total revenue this year</span></span></li><ul>     |
| <span data-ttu-id="eb737-123">Wydatki</span><span class="sxs-lookup"><span data-stu-id="eb737-123">Expense</span></span>                     | <ul><li><span data-ttu-id="eb737-124">Łączne wydatki w roku</span><span class="sxs-lookup"><span data-stu-id="eb737-124">Total expenses this year</span></span></li><li><span data-ttu-id="eb737-125">Cel wydatków założony w budżecie</span><span class="sxs-lookup"><span data-stu-id="eb737-125">Goal for expenses based on budget</span></span></li><ul> |
| <span data-ttu-id="eb737-126">Przychód</span><span class="sxs-lookup"><span data-stu-id="eb737-126">Revenue</span></span>                     | <ul><li><span data-ttu-id="eb737-127">Łączne przychody w roku</span><span class="sxs-lookup"><span data-stu-id="eb737-127">Total revenue this year</span></span></li><li><span data-ttu-id="eb737-128">Cel przychodów założony w budżecie</span><span class="sxs-lookup"><span data-stu-id="eb737-128">Goal for revenue based on budget</span></span></li><ul>   |
| <span data-ttu-id="eb737-129">Dochód netto</span><span class="sxs-lookup"><span data-stu-id="eb737-129">Net income</span></span>                  | <ul><li><span data-ttu-id="eb737-130">Dochód netto w roku</span><span class="sxs-lookup"><span data-stu-id="eb737-130">Net income this year</span></span></li><li><span data-ttu-id="eb737-131">Cel dochodu netto założony w budżecie</span><span class="sxs-lookup"><span data-stu-id="eb737-131">Goal for net income based on budget</span></span></li><ul>   |

## <a name="understanding-the-data-model-and-entities"></a><span data-ttu-id="eb737-132">Opis modelu danych i jednostek</span><span class="sxs-lookup"><span data-stu-id="eb737-132">Understanding the data model and entities</span></span>

| <span data-ttu-id="eb737-133">Jednostka</span><span class="sxs-lookup"><span data-stu-id="eb737-133">Entity</span></span>                    | <span data-ttu-id="eb737-134">Zawartość</span><span class="sxs-lookup"><span data-stu-id="eb737-134">Contents</span></span>                                                                         |
|---------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="eb737-135">Działania na księdze głównej</span><span class="sxs-lookup"><span data-stu-id="eb737-135">General Ledger Activities</span></span> | <span data-ttu-id="eb737-136">Kwoty transakcji w księdze głównej</span><span class="sxs-lookup"><span data-stu-id="eb737-136">Transaction amounts for the general ledger</span></span>                                       |
| <span data-ttu-id="eb737-137">Działania na budżecie</span><span class="sxs-lookup"><span data-stu-id="eb737-137">Budget Activities</span></span>         | <span data-ttu-id="eb737-138">Kwoty transakcji w rejestrze budżetu</span><span class="sxs-lookup"><span data-stu-id="eb737-138">Transaction amounts for the budget register</span></span>                                      |
| <span data-ttu-id="eb737-139">Konta główne</span><span class="sxs-lookup"><span data-stu-id="eb737-139">Main Accounts</span></span>             | <span data-ttu-id="eb737-140">Konta główne, według których będą filtrowane raporty</span><span class="sxs-lookup"><span data-stu-id="eb737-140">Main accounts to filter reports by</span></span>                                               |
| <span data-ttu-id="eb737-141">Kalendarze obrachunkowe</span><span class="sxs-lookup"><span data-stu-id="eb737-141">Fiscal Calendars</span></span>          | <span data-ttu-id="eb737-142">Kalendarze obrachunkowe, według których będą filtrowane raporty</span><span class="sxs-lookup"><span data-stu-id="eb737-142">Fiscal calendars to filter reports by</span></span>                                            |
| <span data-ttu-id="eb737-143">Księgi</span><span class="sxs-lookup"><span data-stu-id="eb737-143">Ledgers</span></span>                   | <span data-ttu-id="eb737-144">Księgi, które można wyfiltrować jako bieżące księgi dla raportu</span><span class="sxs-lookup"><span data-stu-id="eb737-144">Ledgers that can be used to filter the report to the current ledger</span></span>              |
| <span data-ttu-id="eb737-145">Kody budżetu</span><span class="sxs-lookup"><span data-stu-id="eb737-145">Budget Codes</span></span>              | <span data-ttu-id="eb737-146">Kody budżetu, według których będą filtrowane raporty</span><span class="sxs-lookup"><span data-stu-id="eb737-146">Budget codes to filter reports by</span></span>                                                |
| <span data-ttu-id="eb737-147">Firmy</span><span class="sxs-lookup"><span data-stu-id="eb737-147">Legal Entities</span></span>            | <span data-ttu-id="eb737-148">Firmy, które można wyfiltrować jako bieżące firmy dla raportu</span><span class="sxs-lookup"><span data-stu-id="eb737-148">Legal entities that can be used to filter the report to the current legal entity</span></span> |
