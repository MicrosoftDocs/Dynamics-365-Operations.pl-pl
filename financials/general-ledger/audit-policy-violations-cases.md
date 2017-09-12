---
title: Naruszenia zasad inspekcji i sprawy
description: "W tym artykule wyjaśniono, jak są generowane sprawy inspekcji na podstawie naruszeń reguł inspekcji. Znajdują się tu także informacje o różnych sposobach, w jakie zasady inspekcji wykorzystują funkcje zakresu dat wyboru dokumentów."
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 24ee0dbf01208f8decc167e11e84191eaae03edf
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="audit-policy-violations-and-cases"></a><span data-ttu-id="258e8-104">Naruszenia zasad inspekcji i sprawy</span><span class="sxs-lookup"><span data-stu-id="258e8-104">Audit policy violations and cases</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="258e8-105">W tym artykule wyjaśniono, jak są generowane sprawy inspekcji na podstawie naruszeń reguł inspekcji.</span><span class="sxs-lookup"><span data-stu-id="258e8-105">The article explains how audit cases are generated from violations of audit policy rules.</span></span> <span data-ttu-id="258e8-106">Znajdują się tu także informacje o różnych sposobach, w jakie zasady inspekcji wykorzystują funkcje zakresu dat wyboru dokumentów.</span><span class="sxs-lookup"><span data-stu-id="258e8-106">It also includes information about the various ways that audit policies use the document selection date range.</span></span>

<a name="how-audit-cases-are-generated"></a><span data-ttu-id="258e8-107">Jak są generowane sprawy inspekcji</span><span class="sxs-lookup"><span data-stu-id="258e8-107">How audit cases are generated</span></span>
-----------------------------

<span data-ttu-id="258e8-108">Zasady inspekcji są używane do identyfikowania raportów z wydatków, zamówień zakupu i faktur od dostawcy, które nie są zgodne z regułami firmy zdefiniowanymi i skonfigurowanymi jako reguły inspekcji.</span><span class="sxs-lookup"><span data-stu-id="258e8-108">Audit policies are used to identify expense reports, purchase orders, and vendor invoices that don't comply with business rules that you define and configure as audit policy rules.</span></span> 

<span data-ttu-id="258e8-109">Zasady inspekcji są uruchamiane w trybie wsadowym.</span><span class="sxs-lookup"><span data-stu-id="258e8-109">Audit policies are run in batch mode.</span></span> <span data-ttu-id="258e8-110">Po uruchomieniu zasad inspekcji wszystkie reguły należące do tej zasady są uruchamiane w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="258e8-110">When you run an audit policy, all the policy rules that are part of that policy are run at the same time.</span></span>

<span data-ttu-id="258e8-111">Każda reguła ocenia zestaw dokumentów.</span><span class="sxs-lookup"><span data-stu-id="258e8-111">Each policy rule evaluates a set of documents.</span></span> <span data-ttu-id="258e8-112">Reguła wybiera dokumenty z wybranego zakresu dat spełniające określone kryteria.</span><span class="sxs-lookup"><span data-stu-id="258e8-112">The policy rule selects documents that are in the document selection date range and that match the specified criteria.</span></span> <span data-ttu-id="258e8-113">Na przykład jedna reguła może wybrać raporty z wydatków, w których uwzględniono posiłki o wartości przekraczającej 50.00.</span><span class="sxs-lookup"><span data-stu-id="258e8-113">For example, one policy rule might select expense reports that have meals that exceed 50.00.</span></span> <span data-ttu-id="258e8-114">Inna reguła może wybrać faktury od dostawcy, które są płatne na rzecz określonego dostawcy.</span><span class="sxs-lookup"><span data-stu-id="258e8-114">Another policy rule might select vendor invoices that are payable to a specific vendor.</span></span> <span data-ttu-id="258e8-115">Dla każdego dokumentu wskazanego w zestawie jest generowane naruszenie.</span><span class="sxs-lookup"><span data-stu-id="258e8-115">For each document that is selected in the set, a violation is generated.</span></span> <span data-ttu-id="258e8-116">Naruszenie to jest zapisem, że określony dokument, np. faktura nr 12345, jest niezgodny z regułą.</span><span class="sxs-lookup"><span data-stu-id="258e8-116">That violation is a record that a particular document, such as invoice 12345, doesn't comply with the policy rule.</span></span> 

<span data-ttu-id="258e8-117">System grupuje razem wiele rekordów naruszenia zasad inspekcji i kojarzy ze sprawami inspekcji.</span><span class="sxs-lookup"><span data-stu-id="258e8-117">Multiple audit violation records are grouped together and associated with audit cases.</span></span> <span data-ttu-id="258e8-118">Domyślnie sprawy dla każdej zasady inspekcji są pogrupowane według reguły inspekcji.</span><span class="sxs-lookup"><span data-stu-id="258e8-118">By default, cases for each audit policy are grouped by audit policy rule.</span></span> <span data-ttu-id="258e8-119">Można jednak wybrać inne kryteria grupowania na stronie **Kryteria grupowania przypadków**.</span><span class="sxs-lookup"><span data-stu-id="258e8-119">If you prefer, you can select other grouping criteria by using the **Case grouping criteria** page.</span></span> <span data-ttu-id="258e8-120">Na przykład można pogrupować nagłówki wydatków według identyfikatora projektu i faktury od dostawcy według konta dostawcy.</span><span class="sxs-lookup"><span data-stu-id="258e8-120">For example, you can group expense headers by project ID and vendor invoices by vendor account.</span></span> <span data-ttu-id="258e8-121">W takim przypadku wszystkie naruszenia nagłówka wydatków, które mają ten sam identyfikator projektu, zostaną pogrupowane w tej samej sprawie, oraz wszystkie faktury od dostawcy, które mają to samo konto dostawcy, zostaną pogrupowane w tej samej sprawie.</span><span class="sxs-lookup"><span data-stu-id="258e8-121">In this case, all expense header violations that have the same project ID will be grouped in the same case, and all vendor invoices that have the same vendor account will be grouped in the same case.</span></span> 

> [!NOTE]
> <span data-ttu-id="258e8-122">W przypadku reguł inspekcji opartych na typie zapytania **Duplikat** naruszenia nie są pogrupowane według reguły ani według kryteriów określonych na stronie **Kryteria grupowania przypadków**.</span><span class="sxs-lookup"><span data-stu-id="258e8-122">For audit policy rules that are based on a **Duplicate** query type, violations aren't grouped by policy rule or by the criteria that are specified on the **Case grouping criteria** page.</span></span> <span data-ttu-id="258e8-123">Zamiast tego są one pogrupowane według kryteriów, które są wbudowane w regułę inspekcji.</span><span class="sxs-lookup"><span data-stu-id="258e8-123">Instead, they are grouped by the criteria that are built into the audit policy rule.</span></span> <span data-ttu-id="258e8-124">Na przykład, jeśli reguła ocenia raporty z wydatków pod kątem zduplikowanych wydatków z tą samą kwotą, numerem handlowca i datą, wszystkie wydatki posiadające te same wartości w tych polach zostaną umieszczone w jednej sprawie.</span><span class="sxs-lookup"><span data-stu-id="258e8-124">For example, if a policy rule evaluates expense reports for duplicate expenses of the same amount, merchant ID, and date, all expenses that have the same values in those fields will be one case.</span></span> <span data-ttu-id="258e8-125">Wszelkie wydatki, które mają różne wartości będą osobnymi sprawami.</span><span class="sxs-lookup"><span data-stu-id="258e8-125">Any expenses that have different values will be a separate case.</span></span>

<span data-ttu-id="258e8-126">Po wygenerowaniu sprawy inspekcji są obsługiwane przy użyciu typowych procesów zarządzania sprawami.</span><span class="sxs-lookup"><span data-stu-id="258e8-126">After the audit cases have been generated, they are handled by using the typical processes for case management.</span></span>

## <a name="document-selection-date-ranges"></a><span data-ttu-id="258e8-127">Wybór zakresu dat dokumentu</span><span class="sxs-lookup"><span data-stu-id="258e8-127">Document selection date ranges</span></span>
<span data-ttu-id="258e8-128">Po uruchomieniu zasad inspekcji, każda reguła wybiera dokumenty określonego typu z datą należącą do wskazanego zakresu.</span><span class="sxs-lookup"><span data-stu-id="258e8-128">When an audit policy is run, each policy rule selects documents of the specified type that have a date that is in the document selection date range.</span></span> <span data-ttu-id="258e8-129">Zakres wyboru dat dokumentów określa się na stronie **Dodatkowe opcje**.</span><span class="sxs-lookup"><span data-stu-id="258e8-129">The document selection date range is specified on the **Additional options** page.</span></span> <span data-ttu-id="258e8-130">Wiele dokumentów ma więcej niż jedną skojarzoną datę.</span><span class="sxs-lookup"><span data-stu-id="258e8-130">Many documents have more than one date associated with them.</span></span> <span data-ttu-id="258e8-131">Pole daty, które jest używane przez regułę inspekcji określa się na stronie **Typ reguły**.</span><span class="sxs-lookup"><span data-stu-id="258e8-131">The date field that the audit policy rule uses is specified on the **Policy rule type** page.</span></span>

<span data-ttu-id="258e8-132">Oto inne sposoby wykorzystania wyboru zakresu dat dokumentu przez regułę inspekcji:</span><span class="sxs-lookup"><span data-stu-id="258e8-132">Here are some other ways that an audit policy uses the document selection date range:</span></span>

-   <span data-ttu-id="258e8-133">Zasada używa wersji każdej reguły inspekcji ważnej w ostatnim dniu wyboru zakresu dat dokumentu.</span><span class="sxs-lookup"><span data-stu-id="258e8-133">The policy uses the version of each policy rule that is effective on the last day of the document selection date range.</span></span> <span data-ttu-id="258e8-134">Ważność wszystkich reguł można sprawdzić na stronie **Zasady inspekcji**.</span><span class="sxs-lookup"><span data-stu-id="258e8-134">You can view the effective dates for each policy rule on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="258e8-135">Zasady używają węzłów organizacyjnych skojarzonych z zasadą w ostatnim dniu wyboru zakresu dat dokumentu.</span><span class="sxs-lookup"><span data-stu-id="258e8-135">The policy uses the organization nodes that are associated with the policy on the last day of the document selection date range.</span></span> <span data-ttu-id="258e8-136">Na stronie listy **Zasady inspekcji** widoczne są tylko węzły organizacji, które są już powiązane z zasadami.</span><span class="sxs-lookup"><span data-stu-id="258e8-136">Only the organization nodes that are currently associated with the policy appear on the **Audit policies** list page.</span></span>
-   <span data-ttu-id="258e8-137">W przypadku reguł opartych na typie zapytania **Wyszukiwanie wg listy** zasada ocenia dokumenty pod kątem monitorowanych jednostek, które są aktywne w ostatnim dniu wyboru zakresu dat dokumentu.</span><span class="sxs-lookup"><span data-stu-id="258e8-137">For policy rules that are based on a **List search** query type, the policy evaluates documents for monitored entities that are effective on the last day of the document selection date range.</span></span>


<span data-ttu-id="258e8-138">Aby uzyskać więcej informacji, zobacz [Reguły inspekcji](audit-policy-rules.md).</span><span class="sxs-lookup"><span data-stu-id="258e8-138">For more information, see [Audit policy rules](audit-policy-rules.md)</span></span>




