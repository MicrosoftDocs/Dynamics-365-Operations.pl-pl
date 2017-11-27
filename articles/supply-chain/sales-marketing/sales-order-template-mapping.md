---
title: "Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
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
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="dd59b-103">Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="dd59b-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="dd59b-104">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="dd59b-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="dd59b-105">Szablon i zadania</span><span class="sxs-lookup"><span data-stu-id="dd59b-105">Template and tasks</span></span>

<span data-ttu-id="dd59b-106">Następujące szablony i podstawowe zadania są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży z programu Finance i Operations do programu Sales:</span><span class="sxs-lookup"><span data-stu-id="dd59b-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="dd59b-107">**Nazwa szablonu w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="dd59b-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="dd59b-108">Zamówienia sprzedaży (z Fin and Ops do Sales)</span><span class="sxs-lookup"><span data-stu-id="dd59b-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="dd59b-109">**Nazwy zadań w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="dd59b-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="dd59b-110">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="dd59b-110">OrderHeader</span></span>
    - <span data-ttu-id="dd59b-111">OrderLine</span><span class="sxs-lookup"><span data-stu-id="dd59b-111">OrderLine</span></span>

<span data-ttu-id="dd59b-112">Zadania synchronizacji wymagane przed synchronizacją nagłówka faktury sprzedaży i wierszy:</span><span class="sxs-lookup"><span data-stu-id="dd59b-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="dd59b-113">Produkty (z Fin and Ops do Sales)</span><span class="sxs-lookup"><span data-stu-id="dd59b-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="dd59b-114">Konta (Sales do Fin and Ops) (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="dd59b-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="dd59b-115">Kontakty z odbiorcami (z Sales do Fin and Ops) (jeśli używane)</span><span class="sxs-lookup"><span data-stu-id="dd59b-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="dd59b-116">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="dd59b-116">Entity set</span></span>

| <span data-ttu-id="dd59b-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dd59b-117">Finance and Operations</span></span> |    <span data-ttu-id="dd59b-118">Usługa Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="dd59b-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="dd59b-119">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="dd59b-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="dd59b-120">Nagłówki zamówień sprzedaży CDS</span><span class="sxs-lookup"><span data-stu-id="dd59b-120">CDS sales order headers</span></span>| <span data-ttu-id="dd59b-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="dd59b-121">SalesOrder</span></span>     | <span data-ttu-id="dd59b-122">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="dd59b-122">SalesOrders</span></span> |
| <span data-ttu-id="dd59b-123">Wiersze zamówienia sprzedaży CDS</span><span class="sxs-lookup"><span data-stu-id="dd59b-123">CDS sales order lines</span></span>  | <span data-ttu-id="dd59b-124">SalesOrderLine</span><span class="sxs-lookup"><span data-stu-id="dd59b-124">SalesOrderLine</span></span> | <span data-ttu-id="dd59b-125">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="dd59b-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="dd59b-126">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="dd59b-126">Entity flow</span></span>

<span data-ttu-id="dd59b-127">Zamówienia sprzedaży są tworzone w programie Finance and Operations i synchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="dd59b-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="dd59b-128">Filtry w szablonie zapewniają, że w synchronizacji uwzględniane są tylko odpowiednie zamówienia sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="dd59b-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="dd59b-129">W synchronizacji zostanie uwzględniony klient zamawiający i fakturujący z programu Sales.</span><span class="sxs-lookup"><span data-stu-id="dd59b-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="dd59b-130">W rozwiązaniu Finance and Operations pola **OrderingCustomerIsExternallyMaintained** i **InvoiceCustomerIsExternallyMaintained** służą do śledzenia synchronizacji w jednostkach danych.</span><span class="sxs-lookup"><span data-stu-id="dd59b-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="dd59b-131">**Zamówienie sprzedaży** w rozwiązaniu Finance and Operations musi zostać potwierdzone.</span><span class="sxs-lookup"><span data-stu-id="dd59b-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="dd59b-132">Z programem Sales są synchronizowane tylko potwierdzone zamówienia sprzedaży lub zamówienia sprzedaży o wyższym statusie przetwarzania, na przykład, Wysłano lub Zafakturowano.</span><span class="sxs-lookup"><span data-stu-id="dd59b-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="dd59b-133">Po utworzeniu lub zmodyfikowaniu zamówienia sprzedaży należy wykonać zadanie wsadowe **Obliczanie sum sprzedaży** w rozwiązaniu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dd59b-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="dd59b-134">Z usługą CDS i programem Sales zostaną zsynchronizowane tylko zamówienia sprzedaży z obliczonymi sumami sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="dd59b-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="dd59b-135">Podatek dotyczący opłat w **nagłówku zamówienia sprzedaży** nie jest aktualnie uwzględniony w synchronizacji między rozwiązaniem Finance and Operations a programem Sales.</span><span class="sxs-lookup"><span data-stu-id="dd59b-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="dd59b-136">Jest to spowodowane tym, że program Sales nie obsługuje informacji podatkowych na poziomie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="dd59b-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="dd59b-137">Uwzględniony jest podatek dotyczący opłat na poziomie wiersza.</span><span class="sxs-lookup"><span data-stu-id="dd59b-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="dd59b-138">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="dd59b-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="dd59b-139">Nowe pola dodane do jednostki **Zamówienie** i wyświetlane na stronie:</span><span class="sxs-lookup"><span data-stu-id="dd59b-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="dd59b-140">**Jest obsługiwane zewnętrznie**— ustaw na **Tak**, gdy zamówienie pochodzi z programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dd59b-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="dd59b-141">**Stan przetwarzania** — służy do wyświetlania stanu przetwarzania zamówienia w rozwiązaniu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dd59b-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="dd59b-142">Dostępne wartości:</span><span class="sxs-lookup"><span data-stu-id="dd59b-142">Values are:</span></span>

    - <span data-ttu-id="dd59b-143">Aktywne</span><span class="sxs-lookup"><span data-stu-id="dd59b-143">Active</span></span>
    - <span data-ttu-id="dd59b-144">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="dd59b-144">Confirmed</span></span>
    - <span data-ttu-id="dd59b-145">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="dd59b-145">Packing Slip</span></span>
    - <span data-ttu-id="dd59b-146">Zafakturowano</span><span class="sxs-lookup"><span data-stu-id="dd59b-146">Invoiced</span></span>
    - <span data-ttu-id="dd59b-147">Pobrane</span><span class="sxs-lookup"><span data-stu-id="dd59b-147">Picked</span></span>
    - <span data-ttu-id="dd59b-148">Częściowo pobrane</span><span class="sxs-lookup"><span data-stu-id="dd59b-148">Partially Picked</span></span>
    - <span data-ttu-id="dd59b-149">Częściowo zapakowano</span><span class="sxs-lookup"><span data-stu-id="dd59b-149">Partially Packed</span></span>
    - <span data-ttu-id="dd59b-150">Wysłano</span><span class="sxs-lookup"><span data-stu-id="dd59b-150">Shipped</span></span>
    - <span data-ttu-id="dd59b-151">Częściowo wysłane</span><span class="sxs-lookup"><span data-stu-id="dd59b-151">Partially Shipped</span></span>
    - <span data-ttu-id="dd59b-152">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="dd59b-152">Partially Invoiced</span></span>
    - <span data-ttu-id="dd59b-153">Anulowane</span><span class="sxs-lookup"><span data-stu-id="dd59b-153">Cancelled</span></span>

<span data-ttu-id="dd59b-154">Ustawienie **Zawiera tylko zewnętrznie obsługiwane produkty** jest używane w innych scenariuszach dotyczących zamówienia sprzedaży (od synchronizacji rozwiązania Sales to Finance z programem Operation) do spójnego śledzenia, czy zamówienie sprzedaży składa się całkowicie z **produktów obsługiwanych zewnętrznie**; w takim przypadku produkty są obsługiwane w rozwiązaniu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dd59b-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="dd59b-155">Zapewnia to brak możliwości synchronizacji wierszy zamówienia sprzedaży z produktami nieznanymi w rozwiązaniu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dd59b-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="dd59b-156">Przyciski **Utwórz fakturę**, **Anuluj zamówienie**, **Oblicz ponownie**, **Pobierz produkty** i **Wyszukaj adres** na stronie **Zamówienie sprzedaży** są ukryte dla zamówień obsługiwanych zewnętrznie, ponieważ faktury zostaną utworzone w rozwiązaniu Finance and Operations i zsynchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="dd59b-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="dd59b-157">Strony zamówienia nie można edytować, ponieważ informacje o zamówieniu sprzedaży zostaną zsynchronizowane z rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="dd59b-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="dd59b-158">Opcja **Stan zamówienia sprzedaży** pozostanie aktywna, aby zapewnić przepływ zmian z rozwiązania Finance and Operations do **zamówienia sprzedaży** w programie Sales.</span><span class="sxs-lookup"><span data-stu-id="dd59b-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="dd59b-159">Można to kontrolować, ustawiając domyślny **Kod stanu [Stan]** na **Aktywny** w projekcie integracji danych.</span><span class="sxs-lookup"><span data-stu-id="dd59b-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="dd59b-160">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="dd59b-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="dd59b-161">Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować w systemach następujące ustawienie:</span><span class="sxs-lookup"><span data-stu-id="dd59b-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="dd59b-162">Konfiguracja w programie Sales</span><span class="sxs-lookup"><span data-stu-id="dd59b-162">Setup in Sales</span></span>

- <span data-ttu-id="dd59b-163">Zapewnij uprawienia dla zespołu (za pomocą opcji **Ustawione połączenie** programu Sales ), do którego przypisany jest użytkownik.</span><span class="sxs-lookup"><span data-stu-id="dd59b-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="dd59b-164">Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora.</span><span class="sxs-lookup"><span data-stu-id="dd59b-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="dd59b-165">W przeciwnym wypadku zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego przy uruchomieniu projektu z integratora danych.</span><span class="sxs-lookup"><span data-stu-id="dd59b-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="dd59b-166">W obszarze **Ustawienia** > **Zabezpieczenia** > **Zespoły** wybierz odpowiedni zespół, kliknij opcję **Zarządzaj rolami** i wybierz rolę o odpowiednich uprawnieniach, np. Administrator systemu.</span><span class="sxs-lookup"><span data-stu-id="dd59b-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="dd59b-167">W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Użyj systemowego obliczania cen###** jest ustawiona na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="dd59b-168">W obszarze **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** sprawdź, czy opcja **Metoda kalkulacji rabatów** jest ustawiona na **Pozycja w wierszu**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="dd59b-169">Konfiguracja w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dd59b-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="dd59b-170">Ustaw opcje **Sprzedaż i marketing** > **Zadania okresowe** > **Obliczanie sum sprzedaży**, aby uruchomić jako zadanie wsadowe z opcją **Oblicz sumy dla zamówień sprzedaży** ustawioną na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="dd59b-171">Jest to ważne, ponieważ z usługą CDS i programem Sales zostaną zsynchronizowane tylko zamówienia sprzedaży z obliczonymi sumami sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="dd59b-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="dd59b-172">Częstotliwość zadania wsadowego powinna być zgodna z częstotliwością synchronizacji zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="dd59b-172">The frequency of the batch job should be alligned with the frequency of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="dd59b-173">Konfiguracja w projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="dd59b-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="dd59b-174">Zadanie SalesHeader</span><span class="sxs-lookup"><span data-stu-id="dd59b-174">SalesHeader task</span></span>

- <span data-ttu-id="dd59b-175">Zaktualizuj mapowanie dla **Identyfikator organizacji CDS w Źródło** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="dd59b-176">Domyślna wartość szablonu **Account_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="dd59b-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="dd59b-177">Szablon domyślny dla **InvoiceAccount_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="dd59b-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="dd59b-178">Domyślna wartość szablonu **Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="dd59b-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="dd59b-179">Upewnij się, że wymagane mapowanie istnieje w opcji **Źródło** > **CDS dla parametru InvoiceCountryRegionId na BillingAddress_Country** i dla **DeliveryCountryRegionId na DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="dd59b-180">Wartość szablonu to **ValueMap** ze zmapowaną liczbą kraju.</span><span class="sxs-lookup"><span data-stu-id="dd59b-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="dd59b-181">**Cennik** jest wymagany do utworzenia zamówień w programie Sales.</span><span class="sxs-lookup"><span data-stu-id="dd59b-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="dd59b-182">Zaktualizuj parametr **ValueMap** w **CDS** > **Przeznaczenie** dla **pricelevelid.name [nazwa cennika]** na **cennik** używany w programie Sales według waluty.</span><span class="sxs-lookup"><span data-stu-id="dd59b-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="dd59b-183">Można użyć domyślnego **cennika** dla pojedynczej waluty lub użyć parametru **ValueMap**, jeżeli **cenniki** są dostępne w kilku walutach.</span><span class="sxs-lookup"><span data-stu-id="dd59b-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="dd59b-184">Wartość szablonu domyślnego dla parametru **pricelevelid.name [nazwa cennika]** to CRM Service USA (przykład).</span><span class="sxs-lookup"><span data-stu-id="dd59b-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="dd59b-185">Zadanie SalesLine</span><span class="sxs-lookup"><span data-stu-id="dd59b-185">SalesLine task</span></span>

- <span data-ttu-id="dd59b-186">Zaktualizuj mapowanie dla **Identyfikator organizacji CDS w Źródło** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="dd59b-187">Domyślna wartość szablonu dla **SalesOrder_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="dd59b-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="dd59b-188">Domyślna wartość szablonu **Product_Organization_OrganizationId** to ORG001.</span><span class="sxs-lookup"><span data-stu-id="dd59b-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="dd59b-189">Upewnij się, że wymagane mapowanie istnieje w **Źródło** > **CDS** dla parametru **DeliveryCountryRegionId** na **DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="dd59b-190">Wartość szablonu to **ValueMap** ze zmapowaną liczbą kraju.</span><span class="sxs-lookup"><span data-stu-id="dd59b-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="dd59b-191">Sprawdź, czy wymagany parametr **ValueMap** dla **SalesUnitSymbol** w rozwiązaniu Finance and Operations istnieje w **Źródło** > **Mapowanie CDS**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="dd59b-192">Wartość szablonu z **ValueMap**jest zdefiniowana dla **SalesUnitSymbol do Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="dd59b-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="dd59b-193">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="dd59b-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="dd59b-194">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="dd59b-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="dd59b-195">Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="dd59b-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="dd59b-196">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="dd59b-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="dd59b-197">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="dd59b-197">OrderHeader</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-1.png)

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="dd59b-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="dd59b-200">OrderLine</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-3.png)

![Mapowanie szablonu w integratorze danych](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="dd59b-203">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="dd59b-203">Related topics</span></span>

[<span data-ttu-id="dd59b-204">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="dd59b-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="dd59b-205">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dd59b-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="dd59b-206">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dd59b-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="dd59b-207">Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="dd59b-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="dd59b-208">Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="dd59b-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


