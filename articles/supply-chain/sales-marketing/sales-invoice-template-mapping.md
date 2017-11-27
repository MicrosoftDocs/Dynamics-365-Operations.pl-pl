---
title: "Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
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
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="82ea5-103">Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="82ea5-103">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="82ea5-104">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="82ea5-104">The topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="82ea5-105">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="82ea5-105">Templates and tasks</span></span>

<span data-ttu-id="82ea5-106">Następujące szablony i podstawowe zadania są używane do synchronizowania nagłówków i wierszy faktur sprzedaży z programu Finance i Operations do programu Sales:</span><span class="sxs-lookup"><span data-stu-id="82ea5-106">The following templates and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="82ea5-107">**Nazwa szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="82ea5-107">**Name of the template in Data integration**</span></span> 

     - <span data-ttu-id="82ea5-108">Faktury sprzedaży (z Fin and Ops do Sales)</span><span class="sxs-lookup"><span data-stu-id="82ea5-108">Sales Invoices (Fin and Ops to Sales)</span></span>

- <span data-ttu-id="82ea5-109">**Nazwy zadań w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="82ea5-109">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="82ea5-110">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="82ea5-110">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="82ea5-111">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="82ea5-111">SalesInvoiceLine</span></span>

<span data-ttu-id="82ea5-112">Zadania synchronizacji wymagane przed synchronizacją nagłówka faktury sprzedaży i wierszy:</span><span class="sxs-lookup"><span data-stu-id="82ea5-112">Sync tasks required prior to Sales invoice header and lines synchronization:</span></span>
-   <span data-ttu-id="82ea5-113">Produkty (z Fin and Ops do Sales)</span><span class="sxs-lookup"><span data-stu-id="82ea5-113">Products (Fin and Ops to Sales)</span></span>
-   <span data-ttu-id="82ea5-114">Konta (Sales do Fin and Ops) (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="82ea5-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="82ea5-115">Kontakty (Sales do Fin and Ops) (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="82ea5-115">Contacts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="82ea5-116">Nagłówek i wiersze zamówienia sprzedaży (Fin and Ops do Sales)</span><span class="sxs-lookup"><span data-stu-id="82ea5-116">Sales order header and lines (Fin and Ops to Sales)</span></span>

## <a name="entity-set"></a><span data-ttu-id="82ea5-117">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="82ea5-117">Entity set</span></span>

| <span data-ttu-id="82ea5-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="82ea5-118">Finance and Operations</span></span>                               | <span data-ttu-id="82ea5-119">Usługa Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="82ea5-119">Common Data Service (CDS)</span></span>              | <span data-ttu-id="82ea5-120">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="82ea5-120">Sales</span></span>          |
|------------------------------------------------------|------------------|----------------|
| <span data-ttu-id="82ea5-121">Nagłówki faktur sprzedaży odbiorcy obsługiwanego zewnętrznie</span><span class="sxs-lookup"><span data-stu-id="82ea5-121">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="82ea5-122">SalesInvoice</span><span class="sxs-lookup"><span data-stu-id="82ea5-122">SalesInvoice</span></span>     | <span data-ttu-id="82ea5-123">Faktury</span><span class="sxs-lookup"><span data-stu-id="82ea5-123">Invoices</span></span>       |
| <span data-ttu-id="82ea5-124">Wiersze faktur sprzedaży odbiorcy obsługiwanego zewnętrznie</span><span class="sxs-lookup"><span data-stu-id="82ea5-124">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="82ea5-125">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="82ea5-125">SalesInvoiceLine</span></span> | <span data-ttu-id="82ea5-126">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="82ea5-126">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="82ea5-127">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="82ea5-127">Entity flow</span></span>

<span data-ttu-id="82ea5-128">Faktury sprzedaży są tworzone w programie Finance and Operations i synchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="82ea5-128">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="82ea5-129">Podatek dotyczący opłat w **nagłówku faktury sprzedaży** nie jest aktualnie uwzględniony w synchronizacji między rozwiązaniem Finance and Operations a programem Sales.</span><span class="sxs-lookup"><span data-stu-id="82ea5-129">Tax related to charges on the **Sales invoice header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="82ea5-130">Jest to spowodowane tym, że program Sales nie obsługuje informacji podatkowych na poziomie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="82ea5-130">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="82ea5-131">Uwzględniony jest podatek dotyczący opłat na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="82ea5-131">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="82ea5-132">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="82ea5-132">Prospect to cash solution for Sales</span></span>

-  <span data-ttu-id="82ea5-133">**Pole numeru faktury** jest dodawane do jednostki **Faktura** i wyświetlane na stronie.</span><span class="sxs-lookup"><span data-stu-id="82ea5-133">An **Invoice number field** is added to the **Invoice** entity and displayed on the page.</span></span>
 
-  <span data-ttu-id="82ea5-134">Przycisk **Utwórz fakturę** na stronie **Zamówienie sprzedaży** jest ukryty, ponieważ faktury zostaną utworzone w rozwiązaniu Finance and Operations i zsynchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="82ea5-134">The **Create invoice** button on the **Sales order** page is hidden because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="82ea5-135">Strony **Faktura** nie można edytować, ponieważ faktury zostaną zsynchronizowane z rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="82ea5-135">The **Invoice** page is non-editable because invoices will be synced from Finance and Operations.</span></span>
 
-  <span data-ttu-id="82ea5-136">**Stan zamówienia sprzedaży** automatycznie zmienia się na **Zafakturowano**, po zsynchronizowaniu powiązanej faktury z rozwiązania Finance and Operations do programu Sales.</span><span class="sxs-lookup"><span data-stu-id="82ea5-136">The **Sales order status** changes automatically to **Invoiced** when the related invoice from Finance and Operations has been  synchronized to Sales.</span></span> <span data-ttu-id="82ea5-137">Ponadto właściciel zamówienia sprzedaży, u którego utworzono fakturę jest przypisywany jako właściciel faktury.</span><span class="sxs-lookup"><span data-stu-id="82ea5-137">Also, the owner of the sales order from which the invoice was created is assigned as the owner of the invoice.</span></span> <span data-ttu-id="82ea5-138">Umożliwia to właścicielowi zamówienia sprzedaży wyświetlenie faktury.</span><span class="sxs-lookup"><span data-stu-id="82ea5-138">This gives the owner of the sales order the ability to view the invoice.</span></span>
 
## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="82ea5-139">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="82ea5-139">Preconditions and mapping setup</span></span>

<span data-ttu-id="82ea5-140">Przed zsynchronizowaniem faktur sprzedaży należy zaktualizować w systemach następujące ustawienie:</span><span class="sxs-lookup"><span data-stu-id="82ea5-140">Before synchronizing sales invoices, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="82ea5-141">Konfiguracja w programie Sales</span><span class="sxs-lookup"><span data-stu-id="82ea5-141">Setup in Sales</span></span>

- <span data-ttu-id="82ea5-142">W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Użyj systemowego obliczania cen###** jest ustawiona na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-142">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="82ea5-143">W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Metoda kalkulacji rabatów** jest ustawiona na **Pozycja w wierszu**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-143">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="82ea5-144">Konfiguracja w projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="82ea5-144">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="82ea5-145">Zadanie SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="82ea5-145">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="82ea5-146">Zaktualizuj mapowanie dla **Identyfikator organizacji CDS** w **Źródło** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-146">Update the mapping for **CDS Organization ID** in **Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="82ea5-147">Domyślna wartość szablonu dla **SalesOrder_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="82ea5-147">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="82ea5-148">Domyślna wartość szablonu **Account_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="82ea5-148">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="82ea5-149">Domyślna wartość szablonu **Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="82ea5-149">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="82ea5-150">Upewnij się, że wymagane mapowanie istnieje w **Źródło** > **CDS dla InvoiceCountryRegionId** na **BillingAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-150">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId** to **BillingAddress_Country**.</span></span>

    -  <span data-ttu-id="82ea5-151">Wartość szablonu to **ValueMap** ze zmapowaną liczbą kraju.</span><span class="sxs-lookup"><span data-stu-id="82ea5-151">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="82ea5-152">**Cennik** jest wymagany do utworzenia faktur w programie Sales.</span><span class="sxs-lookup"><span data-stu-id="82ea5-152">**Price list** is required to create invoices in Sales.</span></span> <span data-ttu-id="82ea5-153">Zaktualizuj parametr **ValueMap** w **CDS** > **Przeznaczenie dla pricelevelid.name [nazwa cennika]** na **Cennik** używany w programie Sales według waluty.</span><span class="sxs-lookup"><span data-stu-id="82ea5-153">Update the **ValueMap** in **CDS** > **Destination for pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="82ea5-154">Można użyć domyślnego **cennika** dla pojedynczej waluty lub użyć parametru **ValueMap**, jeżeli **cenniki** są dostępne w kilku walutach.</span><span class="sxs-lookup"><span data-stu-id="82ea5-154">You can either use the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>

    -  <span data-ttu-id="82ea5-155">Wartość szablonu dla **pricelevelid.name [nazwa cennika]** to **ValueMap** na podstawie opcji **Waluta**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-155">Template value for **pricelevelid.name [Price List Name]** is **ValueMap** based on **Currency**.</span></span>
    -  <span data-ttu-id="82ea5-156">usd: CRM Service USA (przykład).</span><span class="sxs-lookup"><span data-stu-id="82ea5-156">usd: CRM Service USA (sample).</span></span> 

#### <a name="salesinvoiceline-task"></a><span data-ttu-id="82ea5-157">Zadanie SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="82ea5-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="82ea5-158">Upewnij się, że wymagane mapowanie istnieje w **Źródło** > **CDS dla jednostki miary**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-158">Ensure that the needed mapping exists in **Source** > **CDS for Unit of measure**.</span></span>

- <span data-ttu-id="82ea5-159">Sprawdź, czy wymagany parametr **ValueMap** dla **SalesUnitSymbol** w rozwiązaniu Finance and Operations istnieje w **Źródło** > **Mapowanie CDS**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-159">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span> 
    
    - <span data-ttu-id="82ea5-160">Wartość szablonu z **ValueMap**jest zdefiniowana dla **SalesUnitSymbol do Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-160">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>
    
-  <span data-ttu-id="82ea5-161">Zaktualizuj mapowanie dla **Identyfikator organizacji CDS w Źródło** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="82ea5-161">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="82ea5-162">Domyślna wartość szablonu dla **SalesInvoicer_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="82ea5-162">Default template value for **SalesInvoicer_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="82ea5-163">Domyślna wartość szablonu **Product_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="82ea5-163">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>
 
## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="82ea5-164">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="82ea5-164">Template mapping in Data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="82ea5-165">Opcje **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="82ea5-165">**Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** are not part of the default mappings.</span></span> <span data-ttu-id="82ea5-166">Mapowanie tych pól wymaga skonfigurowania mapowania wartości, które jest specyficzne dla danych w organizacjach, między którymi synchronizowana jest jednostka.</span><span class="sxs-lookup"><span data-stu-id="82ea5-166">Mapping of these fields requires value mapping to be set up, which is specific to the data in the organizations between which the entity is synchronized.</span></span>

<span data-ttu-id="82ea5-167">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="82ea5-167">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mapowanie szablonu w integratorze danych](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="82ea5-172">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="82ea5-172">Related topics</span></span>

[<span data-ttu-id="82ea5-173">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="82ea5-173">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="82ea5-174">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="82ea5-174">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="82ea5-175">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="82ea5-175">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="82ea5-176">Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="82ea5-176">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="82ea5-177">Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="82ea5-177">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)


