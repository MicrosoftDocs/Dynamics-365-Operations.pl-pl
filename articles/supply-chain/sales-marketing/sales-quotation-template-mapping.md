---
title: "Synchronizowanie nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c8cfc484eed02423dbf0c7caaf8ac2337b6ac38d
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="c36e8-103">Synchronizowanie nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c36e8-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="c36e8-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="c36e8-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="c36e8-105">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="c36e8-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="c36e8-106">Szablon i zadania</span><span class="sxs-lookup"><span data-stu-id="c36e8-106">Template and tasks</span></span>

<span data-ttu-id="c36e8-107">Następujące szablony i podstawowe zadania są używane do synchronizowania nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="c36e8-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="c36e8-108">**Nazwa szablonu:** Oferty sprzedaży (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="c36e8-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="c36e8-109">**Nazwy zadań w projekcie:**</span><span class="sxs-lookup"><span data-stu-id="c36e8-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="c36e8-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="c36e8-110">QuoteHeader</span></span>
    - <span data-ttu-id="c36e8-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="c36e8-111">QuoteLine</span></span>

<span data-ttu-id="c36e8-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze ofert sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="c36e8-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="c36e8-113">Produkty (z Fin and Ops do Sales)</span><span class="sxs-lookup"><span data-stu-id="c36e8-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="c36e8-114">Konta (Sales do Fin and Ops) (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="c36e8-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="c36e8-115">Kontakty z odbiorcami (z Sales do Fin and Ops) (jeśli używane)</span><span class="sxs-lookup"><span data-stu-id="c36e8-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="c36e8-116">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="c36e8-116">Entity set</span></span>

| <span data-ttu-id="c36e8-117">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="c36e8-117">Sales</span></span>        | <span data-ttu-id="c36e8-118">CDS</span><span class="sxs-lookup"><span data-stu-id="c36e8-118">CDS</span></span>           | <span data-ttu-id="c36e8-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c36e8-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="c36e8-120">Cytaty</span><span class="sxs-lookup"><span data-stu-id="c36e8-120">Quotes</span></span>       | <span data-ttu-id="c36e8-121">Oferta</span><span class="sxs-lookup"><span data-stu-id="c36e8-121">Quotation</span></span>     | <span data-ttu-id="c36e8-122">Nagłówki ofert sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c36e8-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="c36e8-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="c36e8-123">QuoteDetails</span></span> | <span data-ttu-id="c36e8-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="c36e8-124">QuotationLine</span></span> | <span data-ttu-id="c36e8-125">Wiersze oferty sprzedaży CDS</span><span class="sxs-lookup"><span data-stu-id="c36e8-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="c36e8-126">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="c36e8-126">Entity flow</span></span>

<span data-ttu-id="c36e8-127">Oferty sprzedaży są tworzone w programie Sales i synchronizowane z programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="c36e8-128">Oferty sprzedaży z programu Sales są synchronizowane tylko wtedy, gdy są spełnione następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="c36e8-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="c36e8-129">Wszystkie produkty w wierszach oferty sprzedaży są obsługiwane zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="c36e8-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="c36e8-130">Oferta sprzedaży jest aktywna lub aktywowana.</span><span class="sxs-lookup"><span data-stu-id="c36e8-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="c36e8-131">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="c36e8-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="c36e8-132">Pole **Zawiera tylko zewnętrznie obsługiwane produkty** zostało dodane do jednostki Oferta w celu umożliwienia ciągłego śledzenia, czy oferta sprzedaży zawiera wyłącznie zewnętrznie obsługiwane produkty.</span><span class="sxs-lookup"><span data-stu-id="c36e8-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="c36e8-133">Jeśli oferta sprzedaży ma tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="c36e8-134">To zachowanie pomaga zagwarantować, że nie będziesz próbować zsynchronizować wierszy oferty sprzedaży z produktami nieznanymi programowi Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="c36e8-135">Wszystkie produkty i wiersze w ofercie są aktualizowane przy użyciu informacji **Zawiera tylko zewnętrznie obsługiwane produkty** z nagłówka oferty.</span><span class="sxs-lookup"><span data-stu-id="c36e8-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="c36e8-136">Ta informacja znajduje się w polu **Oferta zawiera tylko zewnętrznie obsługiwane produkty** w jednostce Wiersz oferty.</span><span class="sxs-lookup"><span data-stu-id="c36e8-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="c36e8-137">Pola **Rabat**, **Opłaty** i **Podatek** są kontrolowane przez skomplikowaną konfigurację w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="c36e8-138">Ta konfiguracja obecnie nie obsługuje mapowanie integracji.</span><span class="sxs-lookup"><span data-stu-id="c36e8-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="c36e8-139">W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są zarządzane i obsługiwane przez program Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="c36e8-140">W programie Sales wymienione pola są tylko do odczytu, ponieważ ich wartości nie są synchronizowane z programem Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="c36e8-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="c36e8-141">**Pola tylko do odczytu w nagłówku oferty sprzedaży:** % rabatu, Rabat, Kwota frachtu</span><span class="sxs-lookup"><span data-stu-id="c36e8-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="c36e8-142">**Pola tylko do odczytu w wierszach oferty sprzedaży:** Podatek</span><span class="sxs-lookup"><span data-stu-id="c36e8-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="c36e8-143">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="c36e8-143">Preconditions and mapping setup</span></span>

<span data-ttu-id="c36e8-144">Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować w systemach następujące ustawienie:</span><span class="sxs-lookup"><span data-stu-id="c36e8-144">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="c36e8-145">Konfiguracja w programie Sales</span><span class="sxs-lookup"><span data-stu-id="c36e8-145">Setup in Sales</span></span>

- <span data-ttu-id="c36e8-146">Wybierz kolejno opcje **Ustawienia** &gt; **Administracja** &gt; **Ustawienia systemowe** &gt; **Sprzedaż** i upewnij się, że w polu **Metoda kalkulacji rabatów** jest ustawiona wartość **Na jednostkę**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-146">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="c36e8-147">To ustawienie pomaga zagwarantować, że rabat wiersza w programie Sales jest zgodny z ustawieniem w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-147">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="c36e8-148">W przeciwnym wypadku rabat nie będzie poprawny w programie Finance and Operations, ponieważ program Finance and Operations odczyta rabat jako przyznany na jednostkę, nawet jeśli w programie Sales był on przyznany dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="c36e8-148">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="c36e8-149">Konfiguracja w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c36e8-149">Setup in Finance and Operations</span></span>

- <span data-ttu-id="c36e8-150">Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-150">Go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="c36e8-151">Na karcie **Sekwencja numerów** wybierz numerację ofert sprzedaży, a następnie kliknij przycisk **Wyświetl szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-151">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="c36e8-152">Następnie w obszarze **Konfiguracja ogólna** w polu **Ręcznie** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-152">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="c36e8-153">Wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-153">Go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="c36e8-154">Następnie na karcie **Wysyłki** w polu **Kontrola daty dostawy** ustaw wartość **Brak**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-154">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="c36e8-155">To ustawienie pomaga zapobiec niepowodzeniom synchronizacji ofert sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c36e8-155">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="c36e8-156">Konfiguracja w projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="c36e8-156">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="c36e8-157">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="c36e8-157">QuoteHeader</span></span>

- <span data-ttu-id="c36e8-158">Pole **Wymagana data dostawy** jest wymagane w programie Finance and Operations i gdy jest puste, synchronizacja nie będzie działać.</span><span class="sxs-lookup"><span data-stu-id="c36e8-158">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="c36e8-159">Aby uniknąć tego problemu, gdy to pole jest puste, domyślna data jest pobierana z ustawienia **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-159">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="c36e8-160">W miejsce tej domyślnej daty należy wpisać preferowaną przez siebie wartość.</span><span class="sxs-lookup"><span data-stu-id="c36e8-160">The date should be updated to a preferred value.</span></span> <span data-ttu-id="c36e8-161">Obecnie nie można wprowadzić wartości takiej jak **Dzisiaj** w celu reprezentowania dzisiejszej daty.</span><span class="sxs-lookup"><span data-stu-id="c36e8-161">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="c36e8-162">Należy wprowadzić konkretną datę.</span><span class="sxs-lookup"><span data-stu-id="c36e8-162">You must enter a specific date.</span></span> <span data-ttu-id="c36e8-163">Domyślną wartością pola **Wymagana data dostawy** w szablonie jest **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-163">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="c36e8-164">Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-164">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="c36e8-165">Aby uniknąć błędów synchronizacji, można określić wartość domyślną, która będzie używana, jeśli pole jest puste w programie Sales.</span><span class="sxs-lookup"><span data-stu-id="c36e8-165">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="c36e8-166">Ta wartość domyślna jest również przydatna, ponieważ nie trzeba ręcznie wprowadzać wartości w polu **Kraj/region** w lokalnych adresach.</span><span class="sxs-lookup"><span data-stu-id="c36e8-166">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="c36e8-167">Nie istnieje domyślna wartość szablonu dla ustawienia **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-167">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="c36e8-168">Zaktualizuj mapowanie dla pola **Identyfikator organizacji CDS** w ustawieniu **Źródło &gt; CDS**, tak aby pasowało do ustawienia **Organizacja CDS** w jednostce Organizacja:</span><span class="sxs-lookup"><span data-stu-id="c36e8-168">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="c36e8-169">Domyślna wartość pola **Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-169">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="c36e8-170">Domyślna wartość pola **Account_Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-170">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="c36e8-171">Domyślna wartość pola **InvoiceAccount_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-171">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="c36e8-172">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="c36e8-172">QuoteLine</span></span>

- <span data-ttu-id="c36e8-173">Zaktualizuj mapowanie dla pola **Identyfikator organizacji CDS** w ustawieniu **Źródło &gt; CDS**, tak aby pasowało do ustawienia **Organizacja CDS** w jednostce Organizacja:</span><span class="sxs-lookup"><span data-stu-id="c36e8-173">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="c36e8-174">Domyślna wartość pola **Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-174">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="c36e8-175">Domyślna wartość pola **Product_Organization_Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-175">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="c36e8-176">Domyślna wartość pola **Quotation_Organization_Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-176">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="c36e8-177">Pole **Wymagana data dostawy** jest wymagane w programie Finance and Operations i gdy jest puste, synchronizacja nie będzie działać.</span><span class="sxs-lookup"><span data-stu-id="c36e8-177">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="c36e8-178">Aby uniknąć tego problemu, gdy to pole jest puste, domyślna data jest pobierana z ustawienia **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-178">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="c36e8-179">W miejsce tej domyślnej daty należy wpisać preferowaną przez siebie wartość.</span><span class="sxs-lookup"><span data-stu-id="c36e8-179">The date should be updated to a preferred value.</span></span> <span data-ttu-id="c36e8-180">Obecnie nie można wprowadzić wartości takiej jak **Dzisiaj** w celu reprezentowania dzisiejszej daty.</span><span class="sxs-lookup"><span data-stu-id="c36e8-180">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="c36e8-181">Należy wprowadzić konkretną datę.</span><span class="sxs-lookup"><span data-stu-id="c36e8-181">You must enter a specific date.</span></span> <span data-ttu-id="c36e8-182">Domyślną wartością pola **Wymagana data dostawy** w szablonie jest **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-182">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="c36e8-183">Można dodać następujące mapowanie z ustawienia **CDS &gt; Miejsce docelowe** w celu zagwarantowania, że wiersze oferty są importowane do programu Finance and Operations w razie braku domyślnych informacji o odbiorcy lub produkcie:</span><span class="sxs-lookup"><span data-stu-id="c36e8-183">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="c36e8-184">**SiteId** — Oddział jest konieczny do generowania ofert i wierszy zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-184">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="c36e8-185">Nie istnieje domyślna wartość szablonu dla pola **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-185">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="c36e8-186">**WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-186">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="c36e8-187">Nie istnieje domyślna wartość szablonu dla pola **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-187">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="c36e8-188">Upewnij się, że wymagana mapa wartości dla jednostki miary (JM) sprzedaży w programie Finance and Operations istnieje w mapowaniu **CDS &gt; Miejsce docelowe** między elementem **Quantity_UOM** a elementem **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="c36e8-188">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="c36e8-189">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="c36e8-189">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="c36e8-190">Pola **Rabat**, **Opłaty** i **Podatek** są kontrolowane przez skomplikowaną konfigurację w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-190">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="c36e8-191">Ta konfiguracja obecnie nie obsługuje mapowanie integracji.</span><span class="sxs-lookup"><span data-stu-id="c36e8-191">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="c36e8-192">W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są obsługiwane przez program Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c36e8-192">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="c36e8-193">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="c36e8-193">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="c36e8-194">Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="c36e8-194">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="c36e8-195">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="c36e8-195">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="c36e8-196">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="c36e8-196">QuoteHeader</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="c36e8-199">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="c36e8-199">QuoteLine</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="c36e8-202">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="c36e8-202">Related topics</span></span>

[<span data-ttu-id="c36e8-203">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="c36e8-203">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="c36e8-204">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c36e8-204">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="c36e8-205">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c36e8-205">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



