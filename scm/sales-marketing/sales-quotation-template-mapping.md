---
title: "Synchronizowanie nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 172a3da1b6d90a25ea9ebd14265e70e4a6f9bd70
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="e41b3-103">Synchronizowanie nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e41b3-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="e41b3-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="e41b3-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="e41b3-105">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="e41b3-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="e41b3-106">Szablon i zadania</span><span class="sxs-lookup"><span data-stu-id="e41b3-106">Template and tasks</span></span>

<span data-ttu-id="e41b3-107">Następujące szablony i podstawowe zadania są używane do synchronizowania nagłówków i wierszy ofert sprzedaży z programu Sales do programu Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e41b3-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="e41b3-108">**Nazwa szablonu:** Oferty sprzedaży (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="e41b3-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="e41b3-109">**Nazwy zadań w projekcie:**</span><span class="sxs-lookup"><span data-stu-id="e41b3-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="e41b3-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e41b3-110">QuoteHeader</span></span>
    - <span data-ttu-id="e41b3-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e41b3-111">QuoteLine</span></span>

<span data-ttu-id="e41b3-112">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze ofert sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="e41b3-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="e41b3-113">Produkty</span><span class="sxs-lookup"><span data-stu-id="e41b3-113">Products</span></span>
- <span data-ttu-id="e41b3-114">Konta (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="e41b3-114">Accounts (if used)</span></span>
- <span data-ttu-id="e41b3-115">Kontakty (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="e41b3-115">Contacts (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="e41b3-116">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="e41b3-116">Entity set</span></span>

| <span data-ttu-id="e41b3-117">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="e41b3-117">Sales</span></span>        | <span data-ttu-id="e41b3-118">CDS</span><span class="sxs-lookup"><span data-stu-id="e41b3-118">CDS</span></span>           | <span data-ttu-id="e41b3-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e41b3-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="e41b3-120">Cytaty</span><span class="sxs-lookup"><span data-stu-id="e41b3-120">Quotes</span></span>       | <span data-ttu-id="e41b3-121">Oferta</span><span class="sxs-lookup"><span data-stu-id="e41b3-121">Quotation</span></span>     | <span data-ttu-id="e41b3-122">Nagłówki ofert sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e41b3-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="e41b3-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="e41b3-123">QuoteDetails</span></span> | <span data-ttu-id="e41b3-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="e41b3-124">QuotationLine</span></span> | <span data-ttu-id="e41b3-125">Wiersze oferty sprzedaży CDS</span><span class="sxs-lookup"><span data-stu-id="e41b3-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="e41b3-126">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="e41b3-126">Entity flow</span></span>

<span data-ttu-id="e41b3-127">Oferty sprzedaży są tworzone w programie Sales i synchronizowane z programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="e41b3-128">Oferty sprzedaży z programu Sales są synchronizowane tylko wtedy, gdy są spełnione następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="e41b3-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="e41b3-129">Wszystkie produkty w wierszach oferty sprzedaży są obsługiwane zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="e41b3-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="e41b3-130">Oferta sprzedaży jest aktywna lub aktywowana.</span><span class="sxs-lookup"><span data-stu-id="e41b3-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e41b3-131">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="e41b3-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="e41b3-132">Pole **Zawiera tylko zewnętrznie obsługiwane produkty** zostało dodane do jednostki Oferta w celu umożliwienia ciągłego śledzenia, czy oferta sprzedaży zawiera wyłącznie zewnętrznie obsługiwane produkty.</span><span class="sxs-lookup"><span data-stu-id="e41b3-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="e41b3-133">Jeśli oferta sprzedaży ma tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="e41b3-134">To zachowanie pomaga zagwarantować, że nie będziesz próbować zsynchronizować wierszy oferty sprzedaży z produktami nieznanymi programowi Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="e41b3-135">Wszystkie produkty i wiersze w ofercie są aktualizowane przy użyciu informacji **Zawiera tylko zewnętrznie obsługiwane produkty** z nagłówka oferty.</span><span class="sxs-lookup"><span data-stu-id="e41b3-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="e41b3-136">Ta informacja znajduje się w polu **Oferta zawiera tylko zewnętrznie obsługiwane produkty** w jednostce Wiersz oferty.</span><span class="sxs-lookup"><span data-stu-id="e41b3-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="e41b3-137">Pola **Rabat**, **Opłaty** i **Podatek** są kontrolowane przez skomplikowaną konfigurację w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="e41b3-138">Ta konfiguracja obecnie nie obsługuje mapowanie integracji.</span><span class="sxs-lookup"><span data-stu-id="e41b3-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="e41b3-139">W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są zarządzane i obsługiwane przez program Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="e41b3-140">W programie Sales wymienione pola są tylko do odczytu, ponieważ ich wartości nie są synchronizowane z programem Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e41b3-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="e41b3-141">**Pola tylko do odczytu w nagłówku oferty sprzedaży:** % rabatu, Rabat, Kwota frachtu</span><span class="sxs-lookup"><span data-stu-id="e41b3-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="e41b3-142">**Pola tylko do odczytu w wierszach oferty sprzedaży:** Podatek</span><span class="sxs-lookup"><span data-stu-id="e41b3-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="e41b3-143">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="e41b3-143">Preconditions and mapping setup</span></span>

- <span data-ttu-id="e41b3-144">Przed rozpoczęciem synchronizacji oferty sprzedaży w programie Sales wybierz kolejno opcje **Ustawienia** &gt; **Administracja** &gt; **Ustawienia systemowe** &gt; **Sprzedaż** i upewnij się, że w polu **Metoda kalkulacji rabatów** jest ustawiona wartość **Na jednostkę**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-144">Before you synchronize sales quotations, in Sales, go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="e41b3-145">To ustawienie pomaga zagwarantować, że rabat wiersza w programie Sales jest zgodny z ustawieniem w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-145">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="e41b3-146">W przeciwnym wypadku rabat nie będzie poprawny w programie Finance and Operations, ponieważ program Finance and Operations odczyta rabat jako przyznany na jednostkę, nawet jeśli w programie Sales był on przyznany dla wiersza.</span><span class="sxs-lookup"><span data-stu-id="e41b3-146">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>
- <span data-ttu-id="e41b3-147">W programie Finance and Operations wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-147">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="e41b3-148">Na karcie **Sekwencja numerów** wybierz numerację ofert sprzedaży, a następnie kliknij przycisk **Wyświetl szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-148">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="e41b3-149">Następnie w obszarze **Konfiguracja ogólna** w polu **Ręcznie** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-149">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="e41b3-150">W programie Finance and Operations wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Ustawienia** &gt; **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-150">In Finance and Operations, go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="e41b3-151">Następnie na karcie **Wysyłki** w polu **Kontrola daty dostawy** ustaw wartość **Brak**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-151">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="e41b3-152">To ustawienie pomaga zapobiec niepowodzeniom synchronizacji ofert sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e41b3-152">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="e41b3-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e41b3-153">QuoteHeader</span></span>

- <span data-ttu-id="e41b3-154">Pole **Wymagana data dostawy** jest wymagane w programie Finance and Operations i gdy jest puste, synchronizacja nie będzie działać.</span><span class="sxs-lookup"><span data-stu-id="e41b3-154">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="e41b3-155">Aby uniknąć tego problemu, gdy to pole jest puste, domyślna data jest pobierana z ustawienia **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-155">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="e41b3-156">W miejsce tej domyślnej daty należy wpisać preferowaną przez siebie wartość.</span><span class="sxs-lookup"><span data-stu-id="e41b3-156">The date should be updated to a preferred value.</span></span> <span data-ttu-id="e41b3-157">Obecnie nie można wprowadzić wartości takiej jak **Dzisiaj** w celu reprezentowania dzisiejszej daty.</span><span class="sxs-lookup"><span data-stu-id="e41b3-157">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="e41b3-158">Należy wprowadzić konkretną datę.</span><span class="sxs-lookup"><span data-stu-id="e41b3-158">You must enter a specific date.</span></span> <span data-ttu-id="e41b3-159">Domyślną wartością pola **Wymagana data dostawy** w szablonie jest **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-159">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="e41b3-160">Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-160">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="e41b3-161">Aby uniknąć błędów synchronizacji, można określić wartość domyślną, która będzie używana, jeśli pole jest puste w programie Sales.</span><span class="sxs-lookup"><span data-stu-id="e41b3-161">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="e41b3-162">Ta wartość domyślna jest również przydatna, ponieważ nie trzeba ręcznie wprowadzać wartości w polu **Kraj/region** w lokalnych adresach.</span><span class="sxs-lookup"><span data-stu-id="e41b3-162">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="e41b3-163">Nie istnieje domyślna wartość szablonu dla ustawienia **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-163">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="e41b3-164">Zaktualizuj mapowanie dla pola **Identyfikator organizacji CDS** w ustawieniu **Źródło &gt; CDS**, tak aby pasowało do ustawienia **Organizacja CDS** w jednostce Organizacja:</span><span class="sxs-lookup"><span data-stu-id="e41b3-164">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="e41b3-165">Domyślna wartość pola **Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-165">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="e41b3-166">Domyślna wartość pola **Account_Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-166">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="e41b3-167">Domyślna wartość pola **InvoiceAccount_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-167">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

### <a name="quoteline"></a><span data-ttu-id="e41b3-168">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e41b3-168">QuoteLine</span></span>

- <span data-ttu-id="e41b3-169">Zaktualizuj mapowanie dla pola **Identyfikator organizacji CDS** w ustawieniu **Źródło &gt; CDS**, tak aby pasowało do ustawienia **Organizacja CDS** w jednostce Organizacja:</span><span class="sxs-lookup"><span data-stu-id="e41b3-169">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="e41b3-170">Domyślna wartość pola **Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-170">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="e41b3-171">Domyślna wartość pola **Product_Organization_Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-171">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="e41b3-172">Domyślna wartość pola **Quotation_Organization_Organization_OrganizationId** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-172">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="e41b3-173">Pole **Wymagana data dostawy** jest wymagane w programie Finance and Operations i gdy jest puste, synchronizacja nie będzie działać.</span><span class="sxs-lookup"><span data-stu-id="e41b3-173">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="e41b3-174">Aby uniknąć tego problemu, gdy to pole jest puste, domyślna data jest pobierana z ustawienia **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-174">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="e41b3-175">W miejsce tej domyślnej daty należy wpisać preferowaną przez siebie wartość.</span><span class="sxs-lookup"><span data-stu-id="e41b3-175">The date should be updated to a preferred value.</span></span> <span data-ttu-id="e41b3-176">Obecnie nie można wprowadzić wartości takiej jak **Dzisiaj** w celu reprezentowania dzisiejszej daty.</span><span class="sxs-lookup"><span data-stu-id="e41b3-176">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="e41b3-177">Należy wprowadzić konkretną datę.</span><span class="sxs-lookup"><span data-stu-id="e41b3-177">You must enter a specific date.</span></span> <span data-ttu-id="e41b3-178">Domyślną wartością pola **Wymagana data dostawy** w szablonie jest **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-178">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="e41b3-179">Można dodać następujące mapowanie z ustawienia **CDS &gt; Miejsce docelowe** w celu zagwarantowania, że wiersze oferty są importowane do programu Finance and Operations w razie braku domyślnych informacji o odbiorcy lub produkcie:</span><span class="sxs-lookup"><span data-stu-id="e41b3-179">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="e41b3-180">**SiteId** — Oddział jest konieczny do generowania ofert i wierszy zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-180">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="e41b3-181">Nie istnieje domyślna wartość szablonu dla pola **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-181">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="e41b3-182">**WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-182">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="e41b3-183">Nie istnieje domyślna wartość szablonu dla pola **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-183">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="e41b3-184">Upewnij się, że wymagana mapa wartości dla jednostki miary (JM) sprzedaży w programie Finance and Operations istnieje w mapowaniu **CDS &gt; Miejsce docelowe** między elementem **Quantity_UOM** a elementem **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="e41b3-184">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="e41b3-185">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="e41b3-185">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="e41b3-186">Pola **Rabat**, **Opłaty** i **Podatek** są kontrolowane przez skomplikowaną konfigurację w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-186">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="e41b3-187">Ta konfiguracja obecnie nie obsługuje mapowanie integracji.</span><span class="sxs-lookup"><span data-stu-id="e41b3-187">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="e41b3-188">W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są obsługiwane przez program Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e41b3-188">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="e41b3-189">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="e41b3-189">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="e41b3-190">Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="e41b3-190">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="e41b3-191">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="e41b3-191">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="e41b3-192">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="e41b3-192">QuoteHeader</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="e41b3-195">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="e41b3-195">QuoteLine</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="e41b3-198">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="e41b3-198">Related topics</span></span>

[<span data-ttu-id="e41b3-199">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="e41b3-199">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="e41b3-200">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e41b3-200">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="e41b3-201">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e41b3-201">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



