---
title: "Reguły inspekcji"
description: "Zasady inspekcji służą do oceniania raportów z wydatków, faktur od dostawcy i zamówień zakupu, aby się upewnić, że spełniają one utworzone przez Ciebie reguły zasad. Wszystkie reguły skojarzone z zasadą inspekcji są uruchamiane w trybie wsadowym, zgodnie z harmonogramem określonym przez użytkownika.  Każda reguła zasad jest wystąpieniem typu reguły zasad. Dla każdego typu reguły zasad w danej chwili może być aktywna tylko jedna reguła."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12991
ms.assetid: 8d787017-71dc-418f-b8c2-4ea9763d9978
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 31c3fac2117fbc580e0c40d840a037f3073d66b4
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="audit-policy-rules"></a><span data-ttu-id="7fb73-106">Reguły inspekcji</span><span class="sxs-lookup"><span data-stu-id="7fb73-106">Audit policy rules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7fb73-107">Zasady inspekcji służą do oceniania raportów z wydatków, faktur od dostawcy i zamówień zakupu, aby się upewnić, że spełniają one utworzone przez Ciebie reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="7fb73-107">You can use audit policies to evaluate expense reports, vendor invoices, and purchase orders to make sure that they comply with policy rules that you create.</span></span> <span data-ttu-id="7fb73-108">Wszystkie reguły skojarzone z zasadą inspekcji są uruchamiane w trybie wsadowym, zgodnie z harmonogramem określonym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7fb73-108">All of the rules that are associated with an audit policy are run in batch mode, according to a schedule that you specify.</span></span>  <span data-ttu-id="7fb73-109">Każda reguła zasad jest wystąpieniem typu reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="7fb73-109">Each policy rule is an instance of a policy rule type.</span></span> <span data-ttu-id="7fb73-110">Dla każdego typu reguły zasad w danej chwili może być aktywna tylko jedna reguła.</span><span class="sxs-lookup"><span data-stu-id="7fb73-110">For each policy rule type, only one policy rule can be active at a time.</span></span> 

<a name="queries-and-query-types"></a><span data-ttu-id="7fb73-111">Kwerendy i typy kwerend</span><span class="sxs-lookup"><span data-stu-id="7fb73-111">Queries and query types</span></span>
-----------------------

<span data-ttu-id="7fb73-112">Tworząc regułę zasad inspekcji, najpierw należy zaznaczyć typ reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="7fb73-112">When you create an audit policy rule, you first select a policy rule type.</span></span> <span data-ttu-id="7fb73-113">Typ reguły zasad określa drzewo obiektów aplikacji (Application Object Tree — AOT), które ma być używane jako punkt wyjścia dla tworzenia reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="7fb73-113">The policy rule type specifies the Application Object Tree (AOT) query to use as the starting point for creating the policy rule.</span></span> <span data-ttu-id="7fb73-114">Określa również typ kwerendy używany dla reguły zasad.</span><span class="sxs-lookup"><span data-stu-id="7fb73-114">It also specifies the query type to use for the policy rule.</span></span> <span data-ttu-id="7fb73-115">Kwerenda określa dokument źródłowy, który ocenia reguła zasad.</span><span class="sxs-lookup"><span data-stu-id="7fb73-115">The query determines the source document that the policy rule evaluates.</span></span> <span data-ttu-id="7fb73-116">Określa również pola w dokumencie źródłowym, które identyfikują zarówno podmiot prawny, jak i datę stosowaną po wybraniu dokumentów w celu inspekcji.</span><span class="sxs-lookup"><span data-stu-id="7fb73-116">It also specifies the fields in the source document that identify both the legal entity and the date to use when documents are selected for audit.</span></span> <span data-ttu-id="7fb73-117">Typ kwerendy kontroluje domyślne pola na stronie kwerendy i na stronie Reguła inspekcji.</span><span class="sxs-lookup"><span data-stu-id="7fb73-117">The query type controls the default fields in the query page and in the Audit policy rule page.</span></span> <span data-ttu-id="7fb73-118">Poniższa tabela zawiera typy kwerend, które są dostępne dla reguł zasad inspekcji.</span><span class="sxs-lookup"><span data-stu-id="7fb73-118">The following table shows the query types that are available for audit policy rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fb73-119">Typ kwerendy</span><span class="sxs-lookup"><span data-stu-id="7fb73-119">Query type</span></span></th>
<th><span data-ttu-id="7fb73-120">Cel</span><span class="sxs-lookup"><span data-stu-id="7fb73-120">Purpose</span></span></th>
<th><span data-ttu-id="7fb73-121">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="7fb73-121">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7fb73-122">Warunkowe</span><span class="sxs-lookup"><span data-stu-id="7fb73-122">Conditional</span></span></td>
<td><span data-ttu-id="7fb73-123">Oceń atrybuty dokumentu źródłowego pod kątem określonych wartości.</span><span class="sxs-lookup"><span data-stu-id="7fb73-123">Evaluate source document attributes against specified values.</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7fb73-124">Agregacja</span><span class="sxs-lookup"><span data-stu-id="7fb73-124">Aggregate</span></span></td>
<td><span data-ttu-id="7fb73-125">Oceń wiele dokumentów źródłowych lub wierszy dokumentu źródłowego pod kątem reguły zasad poprzez zsumowanie wartości liczbowych.</span><span class="sxs-lookup"><span data-stu-id="7fb73-125">Evaluate multiple source documents or source document lines against a policy rule by aggregating numeric values.</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7fb73-126">Próbkowanie</span><span class="sxs-lookup"><span data-stu-id="7fb73-126">Sampling</span></span></td>
<td><span data-ttu-id="7fb73-127">Losowo wybierz określony procent dokumentów źródłowych w celu oceny pod kątem naruszenia zasad.</span><span class="sxs-lookup"><span data-stu-id="7fb73-127">Randomly select a specified percentage of the source documents to evaluate for policy violations.</span></span></td>
<td><span data-ttu-id="7fb73-128">Po wybraniu tej opcji należy użyć strony Reguła inspekcji, aby określić procent dokumentów losowo wybranych do inspekcji.</span><span class="sxs-lookup"><span data-stu-id="7fb73-128">When you select this option, use the Audit policy rule page to specify the percentage of documents to randomly select for audit.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7fb73-129">Duplikat</span><span class="sxs-lookup"><span data-stu-id="7fb73-129">Duplicate</span></span></td>
<td><span data-ttu-id="7fb73-130">Oceń dokumenty źródłowe, aby określić, czy zawierają zduplikowane wpisy w określonych polach.</span><span class="sxs-lookup"><span data-stu-id="7fb73-130">Evaluate source documents to determine whether they contain duplicate entries in specified fields.</span></span></td>
<td><span data-ttu-id="7fb73-131">Po wybraniu tej opcji użyj strony Reguła inspekcji, aby określić liczbę dni dodawanych do początku zakresu dat wyboru dokumentów, jeśli dokumenty są oceniane pod kątem zduplikowanych wpisów.</span><span class="sxs-lookup"><span data-stu-id="7fb73-131">When you select this option, use the Audit policy rule page to specify the number of days to add to the start of the document selection date range when documents are evaluated for duplicate entries.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7fb73-132">Wyszukiwanie wg listy</span><span class="sxs-lookup"><span data-stu-id="7fb73-132">List search</span></span></td>
<td><span data-ttu-id="7fb73-133">Oceń dokumenty źródłowe pod kątem konkretnych obiektów.</span><span class="sxs-lookup"><span data-stu-id="7fb73-133">Evaluate source documents for specific entities.</span></span></td>
<td><span data-ttu-id="7fb73-134">Dokument główny kwerendy określa dokument podlegający inspekcji.</span><span class="sxs-lookup"><span data-stu-id="7fb73-134">The root document of the query defines the document that is being audited.</span></span> <span data-ttu-id="7fb73-135">Kwerenda musi być kwerendą listy, która zawiera odwołanie do tabeli dirpartytable.</span><span class="sxs-lookup"><span data-stu-id="7fb73-135">The query must be a list query that includes a reference to the dirpartytable table.</span></span> <span data-ttu-id="7fb73-136">Ta opcja może być używana wyłącznie z następującymi kwerendami AOT:</span><span class="sxs-lookup"><span data-stu-id="7fb73-136">This option can be used only with the following AOT queries:</span></span>
<ul>
<li><span data-ttu-id="7fb73-137"><span class="ui">AuditPolicyExpenseList</span> (Pracownicy etatowi monitorowani w raporcie z wydatków)</span><span class="sxs-lookup"><span data-stu-id="7fb73-137"><span class="ui">AuditPolicyExpenseList</span> (Expense report monitored employees)</span></span></li>
<li><span data-ttu-id="7fb73-138"><span class="ui">AuditPolicyPurchList</span> (Dostawcy monitorowani w zamówieniu zakupu)</span><span class="sxs-lookup"><span data-stu-id="7fb73-138"><span class="ui">AuditPolicyPurchList</span> (Purchase order monitored vendors)</span></span></li>
<li><span data-ttu-id="7fb73-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Dostawcy monitorowani w fakturze od dostawcy)</span><span class="sxs-lookup"><span data-stu-id="7fb73-139"><span class="ui">AuditPolicyVendInvoiceList</span> (Vendor invoice monitored vendors)</span></span></li>
</ul>
<span data-ttu-id="7fb73-140">Po wybraniu tej opcji określ monitorowane jednostki na stronie Reguła inspekcji.</span><span class="sxs-lookup"><span data-stu-id="7fb73-140">When you select this option, specify the monitored entities in the Audit policy rule page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7fb73-141">Wyszukiwanie wg słów kluczowych</span><span class="sxs-lookup"><span data-stu-id="7fb73-141">Keyword search</span></span></td>
<td><span data-ttu-id="7fb73-142">Oceń dokumenty źródłowe, aby określić, czy zawierają określone wyrazy.</span><span class="sxs-lookup"><span data-stu-id="7fb73-142">Evaluate source documents to determine whether they contain certain words.</span></span></td>
<td><span data-ttu-id="7fb73-143">Po wybraniu tej opcji określ słowa do wyszukania jednostki na stronie Reguła inspekcji.</span><span class="sxs-lookup"><span data-stu-id="7fb73-143">When you select this option, enter the words to look for in the Audit policy rule page.</span></span> <span data-ttu-id="7fb73-144">Strona Reguła inspekcji zawiera również opcje, które pozwalają wybrać tabele i pola do oceny pod kątem wprowadzonych wyrazów.</span><span class="sxs-lookup"><span data-stu-id="7fb73-144">The Audit policy rule page also includes options that let you specify the tables and fields to evaluate for the words you entered.</span></span></td>
</tr>
</tbody>
</table>

## <a name="common-parameters"></a><span data-ttu-id="7fb73-145">Wspólne parametry</span><span class="sxs-lookup"><span data-stu-id="7fb73-145">Common parameters</span></span>
<span data-ttu-id="7fb73-146">Wszystkie reguły zasad dotyczące udziału konkretnych zasad inspekcji współdzielą te same parametry przetwarzania wsadowego i ten sam zakres dat wyboru dokumentów.</span><span class="sxs-lookup"><span data-stu-id="7fb73-146">All of the policy rules for a particular audit policy share the same batch parameters and the same document selection date range.</span></span> <span data-ttu-id="7fb73-147">Te parametry są określane w zasadzie na stronie Opcje dodatkowe .</span><span class="sxs-lookup"><span data-stu-id="7fb73-147">These parameters are specified for the policy in the Additional options page.</span></span>



<a name="see-also"></a><span data-ttu-id="7fb73-148">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="7fb73-148">See also</span></span>
--------

<span data-ttu-id="7fb73-149">[Naruszenia zasad audytu i sprawy](audit-policy-violations-cases.md)
[Definiowanie zasad inspekcji dla dokumentów źródłowych](tasks/define-audit-policies-source-documents.md)</span><span class="sxs-lookup"><span data-stu-id="7fb73-149">[Audit policy violations and cases](audit-policy-violations-cases.md)
[Define audit policies for source documents](tasks/define-audit-policies-source-documents.md)</span></span>



