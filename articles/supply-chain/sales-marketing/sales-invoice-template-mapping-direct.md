---
title: Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales
description: Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: e12b2ca0fd5df3b2acf6b84d7ff51967e1acc93e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231775"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="9e94e-103">Synchronizowanie nagłówków i wierszy faktur bezpośrednio z rozwiązania Finance and Operations do rozwiązania Sales</span><span class="sxs-lookup"><span data-stu-id="9e94e-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e94e-104">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy faktur sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="9e94e-105">Przepływ danych w rozwiązaniu Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="9e94e-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="9e94e-106">Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="9e94e-107">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="9e94e-108">Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-108">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="9e94e-109">[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="9e94e-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="9e94e-110">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="9e94e-110">Templates and tasks</span></span>

<span data-ttu-id="9e94e-111">Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="9e94e-111">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="9e94e-112">Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="9e94e-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="9e94e-113">Następujący szablon i podstawowe zadania są używane do synchronizowania nagłówków i wierszy faktur sprzedaży bezpośrednio z Supply Chain Management do Sales:</span><span class="sxs-lookup"><span data-stu-id="9e94e-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Supply Chain Management to Sales:</span></span>

- <span data-ttu-id="9e94e-114">**Nazwa szablonu w integracji danych:** Faktury sprzedaży (Fin and Ops do Sales) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="9e94e-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="9e94e-115">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="9e94e-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="9e94e-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="9e94e-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="9e94e-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="9e94e-117">SalesInvoiceLine</span></span>

<span data-ttu-id="9e94e-118">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze faktur sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="9e94e-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="9e94e-119">Produkty (Supply Chain Management do Sales) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="9e94e-119">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="9e94e-120">Konta (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)</span><span class="sxs-lookup"><span data-stu-id="9e94e-120">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="9e94e-121">Kontakty (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)</span><span class="sxs-lookup"><span data-stu-id="9e94e-121">Contacts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="9e94e-122">Nagłówek zamówienia sprzedaży i wiersze (Supply Chain Management do Sales) - bezpośrednio</span><span class="sxs-lookup"><span data-stu-id="9e94e-122">Sales order header and lines (Supply Chain Management to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="9e94e-123">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="9e94e-123">Entity set</span></span>

| <span data-ttu-id="9e94e-124">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="9e94e-124">Supply Chain Management</span></span>                              | <span data-ttu-id="9e94e-125">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="9e94e-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="9e94e-126">Nagłówki faktur sprzedaży odbiorcy obsługiwanego zewnętrznie</span><span class="sxs-lookup"><span data-stu-id="9e94e-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="9e94e-127">Faktury</span><span class="sxs-lookup"><span data-stu-id="9e94e-127">Invoices</span></span>       |
| <span data-ttu-id="9e94e-128">Wiersze faktur sprzedaży odbiorcy obsługiwanego zewnętrznie</span><span class="sxs-lookup"><span data-stu-id="9e94e-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="9e94e-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="9e94e-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="9e94e-130">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="9e94e-130">Entity flow</span></span>

<span data-ttu-id="9e94e-131">Faktury sprzedaży są tworzone w Supply Chain Management i synchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-131">Sales invoices are created in Supply Chain Management and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="9e94e-132">Aktualnie podatek dotyczący opłat w nagłówku faktury sprzedaży nie jest uwzględniony w synchronizacji między rozwiązaniem Supply Chain Managements a programem Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Supply Chain Managements to Sales.</span></span> <span data-ttu-id="9e94e-133">Program Sales nie obsługuje informacji podatkowych na poziomie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="9e94e-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="9e94e-134">Jednakże podatek dotyczący opłat na poziomie wiersza jest uwzględniony w synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="9e94e-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="9e94e-135">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="9e94e-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="9e94e-136">Pole **Numer faktury** zostało dodane do jednostki **Faktura** i jest wyświetlane na stronie.</span><span class="sxs-lookup"><span data-stu-id="9e94e-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="9e94e-137">Przycisk **Utwórz fakturę** na stronie **Zamówienie sprzedaży** jest ukryty, ponieważ faktury zostaną utworzone w rozwiązaniu Supply Chain Management i zsynchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="9e94e-138">Strony **Faktura** nie można edytować, ponieważ faktury zostaną zsynchronizowane z rozwiązania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9e94e-138">The **Invoice** page can't be edited, because invoices will be synchronized from Supply Chain Management.</span></span>
- <span data-ttu-id="9e94e-139">Wartość **Stan zamówienia sprzedaży** automatycznie zmienia się na **Zafakturowano** po zsynchronizowaniu powiązanej faktury z rozwiązania Supply Chain Management do programu Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Supply Chain Management has been synchronized to Sales.</span></span> <span data-ttu-id="9e94e-140">Ponadto właściciel zamówienia sprzedaży, u którego utworzono fakturę jest przypisywany jako właściciel faktury.</span><span class="sxs-lookup"><span data-stu-id="9e94e-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="9e94e-141">Dlatego właściciel zamówienia sprzedaży może wyświetlić fakturę.</span><span class="sxs-lookup"><span data-stu-id="9e94e-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="9e94e-142">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="9e94e-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="9e94e-143">Przed zsynchronizowaniem faktur sprzedaży należy zaktualizować poniższe ustawienia w systemach.</span><span class="sxs-lookup"><span data-stu-id="9e94e-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="9e94e-144">Konfiguracja w programie Sales</span><span class="sxs-lookup"><span data-stu-id="9e94e-144">Setup in Sales</span></span>

<span data-ttu-id="9e94e-145">Przejdź do okna **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="9e94e-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="9e94e-146">Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="9e94e-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="9e94e-147">Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.</span><span class="sxs-lookup"><span data-stu-id="9e94e-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="9e94e-148">Konfiguracja w projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="9e94e-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="9e94e-149">Zadanie SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="9e94e-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="9e94e-150">Sprawdź, czy istnieje wymagane mapowanie dla **InvoiceCountryRegionId** na **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="9e94e-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="9e94e-151">Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów.</span><span class="sxs-lookup"><span data-stu-id="9e94e-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="9e94e-152">Cennik jest wymagany do utworzenia faktur w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="9e94e-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="9e94e-153">Zaktualizuj mapę wartości dla parametru **pricelevelid.name \[Nazwa cennika\]** na cennik używany w programie Sales według waluty.</span><span class="sxs-lookup"><span data-stu-id="9e94e-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="9e94e-154">Dla jednej waluty można użyć cennika domyślnego.</span><span class="sxs-lookup"><span data-stu-id="9e94e-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="9e94e-155">Ponadto, jeżeli masz cenniki w kilku walutach, możesz użyć mapy wartości.</span><span class="sxs-lookup"><span data-stu-id="9e94e-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="9e94e-156">Wartość szablonu pola **pricelevelid.name \[Nazwa cennika\]** to mapa wartości oparta na walucie z USD = CRM Service USA (przykład).</span><span class="sxs-lookup"><span data-stu-id="9e94e-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="9e94e-157">Zadanie SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="9e94e-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="9e94e-158">Sprawdź, czy istnieje wymagane mapowanie dla opcji **Jednostka miary**.</span><span class="sxs-lookup"><span data-stu-id="9e94e-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="9e94e-159">Upewnij się, że w rozwiązaniu Supply Chain Management istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="9e94e-159">Make sure that the required value map for **SalesUnitSymbol** in Supply Chain Management exists.</span></span>

    <span data-ttu-id="9e94e-160">Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **SalesUnitSymbol** na **Ilość\_Jednostka miary**.</span><span class="sxs-lookup"><span data-stu-id="9e94e-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="9e94e-161">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="9e94e-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="9e94e-162">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="9e94e-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="9e94e-163">Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="9e94e-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="9e94e-164">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="9e94e-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="9e94e-165">Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9e94e-165">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="9e94e-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="9e94e-166">SalesInvoiceHeader</span></span>

![Mapowanie szablonu w integracji danych](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="9e94e-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="9e94e-168">SalesInvoiceLine</span></span>

![Mapowanie szablonu w integracji danych](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="9e94e-170">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="9e94e-170">Related topics</span></span>

[<span data-ttu-id="9e94e-171">Od prospekta do gotówki</span><span class="sxs-lookup"><span data-stu-id="9e94e-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="9e94e-172">Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9e94e-172">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="9e94e-173">Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="9e94e-173">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="9e94e-174">Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9e94e-174">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="9e94e-175">Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9e94e-175">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]