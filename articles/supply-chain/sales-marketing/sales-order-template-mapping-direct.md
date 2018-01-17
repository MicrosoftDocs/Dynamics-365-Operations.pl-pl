---
title: "Synchronizowanie nagłówków i wierszy zamówień sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: e311b0becbb243cebdc265eccf3059eb46217dee
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="5be01-103">Synchronizowanie nagłówków i wierszy zamówień sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="5be01-103">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="5be01-104">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży bezpośrednio między programem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition a programem Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-104">This topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="5be01-105">Przepływ danych w rozwiązaniu Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="5be01-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="5be01-106">Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracja danych do synchronizacji danych między wystąpieniami programu Finance and Operations a programem Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="5be01-107">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="5be01-108">Poniższa ilustracja przedstawia sposób synchronizacji danych między programami Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="5be01-109">[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="5be01-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="5be01-110">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="5be01-110">Templates and tasks</span></span>

<span data-ttu-id="5be01-111">Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="5be01-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="5be01-112">Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="5be01-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="5be01-113">Następujący szablon i podstawowe zadania są używane do synchronizowania nagłówków i wierszy zamówień sprzedaży z programu Finance and Operations do programu Sales:</span><span class="sxs-lookup"><span data-stu-id="5be01-113">The following template and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="5be01-114">**Nazwa szablonu w integracji danych:** Zamówienia sprzedaży (Fin and Ops do Sales) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="5be01-114">**Name of the template in Data integration:** Sales Orders (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="5be01-115">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="5be01-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="5be01-116">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="5be01-116">OrderHeader</span></span>
    - <span data-ttu-id="5be01-117">OrderLine</span><span class="sxs-lookup"><span data-stu-id="5be01-117">OrderLine</span></span>

<span data-ttu-id="5be01-118">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze faktur sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="5be01-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="5be01-119">Produkty (z Fin and Ops do Sales) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="5be01-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="5be01-120">Konta (Sales do Fin and Ops) — bezpośrednie (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="5be01-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="5be01-121">Kontakty z odbiorcami (z Sales do Fin and Ops) — bezpośrednie (jeśli używane)</span><span class="sxs-lookup"><span data-stu-id="5be01-121">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="5be01-122">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="5be01-122">Entity set</span></span>

| <span data-ttu-id="5be01-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5be01-123">Finance and Operations</span></span>  | <span data-ttu-id="5be01-124">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="5be01-124">Sales</span></span>             |
|-------------------------|-------------------|
| <span data-ttu-id="5be01-125">Nagłówki zamówień sprzedaży CDS</span><span class="sxs-lookup"><span data-stu-id="5be01-125">CDS sales order headers</span></span> | <span data-ttu-id="5be01-126">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="5be01-126">SalesOrders</span></span>       |
| <span data-ttu-id="5be01-127">Wiersze zamówienia sprzedaży CDS</span><span class="sxs-lookup"><span data-stu-id="5be01-127">CDS sales order lines</span></span>   | <span data-ttu-id="5be01-128">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="5be01-128">SalesOrderDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="5be01-129">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="5be01-129">Entity flow</span></span>

<span data-ttu-id="5be01-130">Zamówienia sprzedaży są tworzone w programie Finance and Operations i synchronizowane z programem Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-130">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="5be01-131">Filtry w szablonie pomagają zagwarantować, że w synchronizacji uwzględniane są tylko odpowiednie zamówienia sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="5be01-131">Filters in the template help guarantee that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="5be01-132">W zamówieniu sprzedaży klient zamawiający i fakturujący pochodzący z rozwiązania Sales zostaną uwzględnieni w synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="5be01-132">On the sales order, both the ordering customer and the invoicing customer that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="5be01-133">W rozwiązaniu Finance and Operations pola **OrderingCustomerIsExternallyMaintained** i **InvoiceCustomerIsExternallyMaintained** służą do śledzenia synchronizacji w jednostkach danych.</span><span class="sxs-lookup"><span data-stu-id="5be01-133">In Finance and Operations, the **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** fields are used to track the synchronization in the data entities.</span></span>
- <span data-ttu-id="5be01-134">Zamówienie sprzedaży w rozwiązaniu Finance and Operations musi zostać potwierdzone.</span><span class="sxs-lookup"><span data-stu-id="5be01-134">The sales order in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="5be01-135">Z rozwiązaniem Sales są synchronizowane tylko potwierdzone zamówienia sprzedaży lub zamówienia sprzedaży o wyższym statusie przetwarzania, takim jak **Wysłano** lub **Zafakturowano**.</span><span class="sxs-lookup"><span data-stu-id="5be01-135">Only confirmed sales orders or sales orders that have a higher processing status, such as **Shipped** or **Invoiced**, are synchronized to Sales.</span></span>
- <span data-ttu-id="5be01-136">Po utworzeniu lub zmodyfikowaniu zamówienia sprzedaży należy wykonać zadanie wsadowe **Obliczanie sum sprzedaży** w rozwiązaniu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5be01-136">After a sales order is created or modified, the **Calculate sales totals** batch job in Finance and Operations must be run.</span></span> <span data-ttu-id="5be01-137">Z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="5be01-137">Only sales orders where sales totals are calculated will be synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="5be01-138">Aktualnie podatek dotyczący opłat w nagłówku zamówienia sprzedaży nie jest uwzględniony w synchronizacji między rozwiązaniem Finance and Operations a programem Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-138">Currently, tax that is related to charges on the sales order header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="5be01-139">Program Sales nie obsługuje informacji podatkowych na poziomie nagłówka.</span><span class="sxs-lookup"><span data-stu-id="5be01-139">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="5be01-140">Jednakże podatek dotyczący opłat na poziomie wiersza jest uwzględniony w synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="5be01-140">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="5be01-141">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="5be01-141">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="5be01-142">Nowe pola zostały dodane do jednostki **Zamówienie** i są wyświetlane na stronie:</span><span class="sxs-lookup"><span data-stu-id="5be01-142">New fields have been added to the **Order** entity and appear on the page:</span></span>

- <span data-ttu-id="5be01-143">**Jest obsługiwane zewnętrznie**— ustaw tę opcję na **Tak**, gdy zamówienie pochodzi z programu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5be01-143">**Is Maintained Externally** – Set this option to **Yes** when the order is coming from Finance and Operations.</span></span>
- <span data-ttu-id="5be01-144">**Stan przetwarzania** — to pole służy do wyświetlania stanu przetwarzania zamówienia w rozwiązaniu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5be01-144">**Processing status** – This field shows the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="5be01-145">Dostępne są następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="5be01-145">The following values are available:</span></span>

    - <span data-ttu-id="5be01-146">Aktywne</span><span class="sxs-lookup"><span data-stu-id="5be01-146">Active</span></span>
    - <span data-ttu-id="5be01-147">Potwierdzone</span><span class="sxs-lookup"><span data-stu-id="5be01-147">Confirmed</span></span>
    - <span data-ttu-id="5be01-148">Dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="5be01-148">Packing Slip</span></span>
    - <span data-ttu-id="5be01-149">Zafakturowano</span><span class="sxs-lookup"><span data-stu-id="5be01-149">Invoiced</span></span>
    - <span data-ttu-id="5be01-150">Pobrane</span><span class="sxs-lookup"><span data-stu-id="5be01-150">Picked</span></span>
    - <span data-ttu-id="5be01-151">Częściowo pobrane</span><span class="sxs-lookup"><span data-stu-id="5be01-151">Partially Picked</span></span>
    - <span data-ttu-id="5be01-152">Częściowo zapakowano</span><span class="sxs-lookup"><span data-stu-id="5be01-152">Partially Packed</span></span>
    - <span data-ttu-id="5be01-153">Wysłano</span><span class="sxs-lookup"><span data-stu-id="5be01-153">Shipped</span></span>
    - <span data-ttu-id="5be01-154">Częściowo wysłane</span><span class="sxs-lookup"><span data-stu-id="5be01-154">Partially Shipped</span></span>
    - <span data-ttu-id="5be01-155">Częściowo zafakturowane</span><span class="sxs-lookup"><span data-stu-id="5be01-155">Partially Invoiced</span></span>
    - <span data-ttu-id="5be01-156">Anulowane</span><span class="sxs-lookup"><span data-stu-id="5be01-156">Cancelled</span></span>

<span data-ttu-id="5be01-157">Ustawienie **Zawiera tylko zewnętrznie obsługiwane produkty** jest używane w innych scenariuszach dotyczących zamówienia sprzedaży (na przykład synchronizacji z rozwiązania Sales do Finance and Operation) do spójnego śledzenia, czy zamówienie sprzedaży składa się całkowicie z produktów obsługiwanych zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="5be01-157">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (for example, synchronization from Sales to Finance and Operation) to consistently track whether a sales order consists entirely of externally maintained products.</span></span> <span data-ttu-id="5be01-158">Jeśli zamówienie sprzedaży zawiera tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5be01-158">If a sales order consists entirely of externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="5be01-159">To ustawienie pomaga zagwarantować, że nie będziesz próbować zsynchronizować wierszy zamówienia sprzedaży z produktami nieznanymi rozwiązaniu Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5be01-159">This setting helps guarantee that you don't try to synchronize sales order lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="5be01-160">W przypadku zamówień obsługiwanych zewnętrznie przyciski **Utwórz fakturę**, **Anuluj zamówienie**, **Oblicz ponownie**, **Pobierz produkty** i **Wyszukaj adres** na stronie **Zamówienie sprzedaży** są ukryte, ponieważ faktury zostaną utworzone w rozwiązaniu Finance and Operations i zsynchronizowane z rozwiązaniem Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-160">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products**, and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="5be01-161">Strony zamówienia nie można edytować, ponieważ informacje o zamówieniu sprzedaży zostaną zsynchronizowane z rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5be01-161">The order page can't be edited, because sales order information will be synchronized from Finance and Operations.</span></span>

<span data-ttu-id="5be01-162">Stan zamówienia sprzedaży pozostanie **Aktywny**, aby zapewnić przepływ zmian z rozwiązania Finance and Operations do zamówienia sprzedaży w programie Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-162">The status of a sales order will remain **Active** to help guarantee that changes from Finance and Operations can flow to the sales order in Sales.</span></span> <span data-ttu-id="5be01-163">Aby kontrolować to zachowanie, ustaw wartość domyślną pola **Kod stanu \[Stan\]** na **Aktywne** w projekcie integracji danych.</span><span class="sxs-lookup"><span data-stu-id="5be01-163">To control this behavior, set the default **Statecode \[Status\]** value to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="5be01-164">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="5be01-164">Preconditions and mapping setup</span></span>

<span data-ttu-id="5be01-165">Przed zsynchronizowaniem zamówień sprzedaży należy zaktualizować poniższe ustawienia w systemach.</span><span class="sxs-lookup"><span data-stu-id="5be01-165">Before you synchronize sales orders, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="5be01-166">Konfiguracja w programie Sales</span><span class="sxs-lookup"><span data-stu-id="5be01-166">Setup in Sales</span></span>

- <span data-ttu-id="5be01-167">Upewnij się, że skonfigurowano uprawienia dla zespołu, do którego przypisany jest użytkownik z połączenia rozwiązania Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-167">Make sure that permissions are set up for the team that the user from your Sales connection set is assigned to.</span></span> <span data-ttu-id="5be01-168">Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora.</span><span class="sxs-lookup"><span data-stu-id="5be01-168">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="5be01-169">Jeżeli zespół nie ma także dostępu w trybie administratora po uruchomieniu projektu z integracji danych, zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego.</span><span class="sxs-lookup"><span data-stu-id="5be01-169">If the team doesn't also have admin access, when you run the project from Data integration, you will receive an error message that states that Principal team is missing.</span></span>

    <span data-ttu-id="5be01-170">Przejdź do okna **Ustawienia** > **Zabezpieczenia** > **Zespoły**, wybierz odpowiedni zespół, wybierz opcję **Zarządzaj rolami** i wybierz rolę o odpowiednich uprawnieniach, na przykład **Administrator systemu**.</span><span class="sxs-lookup"><span data-stu-id="5be01-170">Go to **Settings** > **Security** > **Teams**, select the relevant team, select **Manage Roles**, and select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="5be01-171">Przejdź do okna **Ustawienia** > **Administracja** > **Ustawienia systemu** > **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="5be01-171">Go to **Settings** > **Administration** > **System settings** > **Sales**, and makes sure that the following settings are used:</span></span>

    - <span data-ttu-id="5be01-172">Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5be01-172">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="5be01-173">Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.</span><span class="sxs-lookup"><span data-stu-id="5be01-173">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="5be01-174">Konfiguracja w programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5be01-174">Setup in Finance and Operations</span></span>

<span data-ttu-id="5be01-175">Przejdź do okna **Sprzedaż i marketing** > **Zadania okresowe** > **Obliczanie sum sprzedaży** i skonfiguruj zadanie tak, aby było uruchamiane jako zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="5be01-175">Go to **Sales and marketing** > **Periodic tasks** > **Calculate sales totals**, and set the job to run as a batch job.</span></span> <span data-ttu-id="5be01-176">Ustaw opcję **Oblicz sumy dla zamówień sprzedaży** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5be01-176">Set the **Calculate totals for sales orders** option to **Yes**.</span></span> <span data-ttu-id="5be01-177">Ten krok jest ważny, ponieważ z rozwiązaniem Sales zostaną synchronizowane tylko zamówienia sprzedaży, dla których obliczono sumy sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="5be01-177">This step is important, because only sales orders where sales totals are calculated will be synchronized to Sales.</span></span> <span data-ttu-id="5be01-178">Częstotliwość zadania wsadowego powinna być zgodna z częstotliwością synchronizacji zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="5be01-178">The frequency of the batch job should be aligned with the frequency of sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="5be01-179">Konfiguracja w projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="5be01-179">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="5be01-180">Zadanie SalesHeader</span><span class="sxs-lookup"><span data-stu-id="5be01-180">SalesHeader task</span></span>

- <span data-ttu-id="5be01-181">Upewnij się, że wymagane mapowanie istnieje w parametru **InvoiceCountryRegionId** na **BillingAddress\_Country** i dla parametru **DeliveryCountryRegionId** na **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="5be01-181">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country** and for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="5be01-182">Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów.</span><span class="sxs-lookup"><span data-stu-id="5be01-182">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="5be01-183">Cennik jest wymagany do utworzenia zamówień w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="5be01-183">A price list is required in order to create orders in Sales.</span></span> <span data-ttu-id="5be01-184">Zaktualizuj mapę wartości dla parametru **pricelevelid.name \[Nazwa cennika\]** na cennik używany w programie Sales według waluty.</span><span class="sxs-lookup"><span data-stu-id="5be01-184">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="5be01-185">Dla jednej waluty można użyć cennika domyślnego.</span><span class="sxs-lookup"><span data-stu-id="5be01-185">You can use the default price list for a single currency.</span></span> <span data-ttu-id="5be01-186">Ponadto, jeżeli masz cenniki w kilku walutach, możesz użyć mapy wartości.</span><span class="sxs-lookup"><span data-stu-id="5be01-186">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="5be01-187">Wartość szablonu domyślnego dla parametru **pricelevelid.name \[Nazwa cennika\]** to **CRM Service USA (przykład)**.</span><span class="sxs-lookup"><span data-stu-id="5be01-187">The default template value for **pricelevelid.name \[Price list name\]** is **CRM Service USA (sample)**.</span></span>

#### <a name="salesline-task"></a><span data-ttu-id="5be01-188">Zadanie SalesLine</span><span class="sxs-lookup"><span data-stu-id="5be01-188">SalesLine task</span></span>

- <span data-ttu-id="5be01-189">Sprawdź, czy istnieje wymagane mapowanie dla **DeliveryCountryRegionId** na **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="5be01-189">Make sure that the required mapping exists for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="5be01-190">Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów.</span><span class="sxs-lookup"><span data-stu-id="5be01-190">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="5be01-191">Upewnij się, że w rozwiązaniu Finance and Operations istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="5be01-191">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="5be01-192">Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **SalesUnitSymbol** na **Ilość\_Jednostka miary**.</span><span class="sxs-lookup"><span data-stu-id="5be01-192">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="5be01-193">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="5be01-193">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="5be01-194">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="5be01-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="5be01-195">Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="5be01-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="5be01-196">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="5be01-196">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="5be01-197">Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5be01-197">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="orderheader"></a><span data-ttu-id="5be01-198">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="5be01-198">OrderHeader</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a><span data-ttu-id="5be01-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="5be01-200">OrderLine</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="5be01-202">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="5be01-202">Related topics</span></span>

[<span data-ttu-id="5be01-203">Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="5be01-203">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="5be01-204">Synchronizowanie kont bezpośrednio w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5be01-204">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="5be01-205">Synchronizowanie produktów bezpośrednio w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="5be01-205">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="5be01-206">Synchronizowanie kontaktów bezpośrednio w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5be01-206">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="5be01-207">Synchronizowanie nagłówków i wierszy faktur sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="5be01-207">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




