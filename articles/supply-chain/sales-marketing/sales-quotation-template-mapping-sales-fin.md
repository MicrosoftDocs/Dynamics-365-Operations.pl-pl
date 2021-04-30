---
title: Synchronizowanie nagłówków ofert i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales
description: Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: bdca4d63fbe04a01cf1bbf2ccd7b095d4718a115
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910312"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a><span data-ttu-id="33857-103">Synchronizowanie nagłówków ofert i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="33857-103">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="33857-104">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania nagłówków i wierszy ofert sprzedaży bezpośrednio między Dynamics 365 Supply Chain Management a Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="33857-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

> [!NOTE]
> <span data-ttu-id="33857-105">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="33857-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="33857-106">Przepływ danych w rozwiązaniu Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="33857-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="33857-107">Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="33857-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="33857-108">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="33857-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="33857-109">Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="33857-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="33857-110">[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="33857-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="33857-111">Szablon i zadania</span><span class="sxs-lookup"><span data-stu-id="33857-111">Template and tasks</span></span>

<span data-ttu-id="33857-112">Następujący szablon i podstawowe zadania są używane do synchronizowania nagłówków i wierszy ofert sprzedaży bezpośrednio z programu Sales do programu Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="33857-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="33857-113">**Nazwa szablonu w integracji danych:** Oferty sprzedaży (Sales do Supply Chain Management) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="33857-113">**Name of the template in Data integration:** Sales Quotes (Sales to Supply Chain Management) - Direct</span></span>
- <span data-ttu-id="33857-114">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="33857-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="33857-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="33857-115">QuoteHeader</span></span>
    - <span data-ttu-id="33857-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="33857-116">QuoteLine</span></span>

<span data-ttu-id="33857-117">Następujące zadania synchronizacji są wymagane, zanim będzie można zsynchronizować nagłówki i wiersze ofert sprzedaży:</span><span class="sxs-lookup"><span data-stu-id="33857-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="33857-118">Produkty (Supply Chain Management do Sales) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="33857-118">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="33857-119">Konta (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)</span><span class="sxs-lookup"><span data-stu-id="33857-119">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="33857-120">Kontakty do Odbiorcy (Sales do Supply Chain Management) — bezpośrednie (jeśli używane)</span><span class="sxs-lookup"><span data-stu-id="33857-120">Contacts to Customers (Sales to Supply Chain Management) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="33857-121">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="33857-121">Entity set</span></span>

| <span data-ttu-id="33857-122">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="33857-122">Sales</span></span>        | <span data-ttu-id="33857-123">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="33857-123">Supply Chain Management</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="33857-124">Cytaty</span><span class="sxs-lookup"><span data-stu-id="33857-124">Quotes</span></span>       | <span data-ttu-id="33857-125">Nagłówek oferty sprzedaży w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="33857-125">Dataverse sales quotation header</span></span> |
| <span data-ttu-id="33857-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="33857-126">QuoteDetails</span></span> | <span data-ttu-id="33857-127">Wiersze oferty sprzedaży w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="33857-127">Dataverse sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="33857-128">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="33857-128">Entity flow</span></span>

<span data-ttu-id="33857-129">Oferty sprzedaży są tworzone w Sales i synchronizowane z programem Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-129">Sales quotations are created in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="33857-130">Oferty sprzedaży z programu Sales są synchronizowane tylko wtedy, gdy są spełnione następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="33857-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="33857-131">Wszystkie oferty produktów w ofercie sprzedaży są obsługiwane zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="33857-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="33857-132">Po kliknięciu opcji **Aktywuj ofertę** oferta sprzedaży jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="33857-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="33857-133">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="33857-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="33857-134">Pole **Zawiera tylko zewnętrznie obsługiwane produkty** zostało dodane do jednostki **Oferta** w celu umożliwienia ciągłego śledzenia, czy oferta sprzedaży zawiera wyłącznie zewnętrznie obsługiwane produkty.</span><span class="sxs-lookup"><span data-stu-id="33857-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="33857-135">Jeśli oferta sprzedaży ma tylko zewnętrznie obsługiwane produkty, są one obsługiwane w programie Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-135">If a sales quotation has only externally maintained products, the products are maintained in Supply Chain Management.</span></span> <span data-ttu-id="33857-136">To zachowanie pomaga zagwarantować, że nie będziesz próbować zsynchronizować wierszy oferty sprzedaży zawierających produkty nieznane programowi Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Supply Chain Management.</span></span>

<span data-ttu-id="33857-137">Wszystkie produkty z oferty w ofercie sprzedaży są aktualizowane przy użyciu informacji **Zawiera tylko zewnętrznie obsługiwane produkty** z nagłówka oferty sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="33857-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="33857-138">Ta informacja znajduje się w polu **Oferta zawiera tylko zewnętrznie obsługiwane produkty** w jednostce **Szczegóły oferty**.</span><span class="sxs-lookup"><span data-stu-id="33857-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="33857-139">Rabat można dodać do produktu z oferty i zostanie on zsynchronizowany z programem Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-139">A discount can be added to the quote product and will be synchronized to Supply Chain Management.</span></span> <span data-ttu-id="33857-140">Pola **Rabat**, **Opłaty** i **Podatek** w nagłówku są kontrolowane przez konfigurację w programie Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Supply Chain Management.</span></span> <span data-ttu-id="33857-141">Obecnie ta konfiguracja nie obsługuje mapowanie integracji.</span><span class="sxs-lookup"><span data-stu-id="33857-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="33857-142">W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są obsługiwane w programie Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in FSupply Chain Management.</span></span>

<span data-ttu-id="33857-143">W programie Sales wymienione pola są tylko do odczytu, ponieważ ich wartości nie są synchronizowane z programem Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="33857-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Supply Chain Management:</span></span>

- <span data-ttu-id="33857-144">Pola tylko do odczytu w nagłówku oferty sprzedaży: **% rabatu**, **Rabat** i **Kwota frachtu**</span><span class="sxs-lookup"><span data-stu-id="33857-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="33857-145">Pola tylko do odczytu w produktach w ofercie: **Podatek**</span><span class="sxs-lookup"><span data-stu-id="33857-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="33857-146">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="33857-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="33857-147">Przed zsynchronizowaniem ofert sprzedaży należy zaktualizować poniższe ustawienia.</span><span class="sxs-lookup"><span data-stu-id="33857-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="33857-148">Konfiguracja w programie Sales</span><span class="sxs-lookup"><span data-stu-id="33857-148">Setup in Sales</span></span>

- <span data-ttu-id="33857-149">Upewnij się, że skonfigurowano uprawienia dla zespołu, do którego przypisany jest użytkownik z połączenia ustawionego w rozwiązaniu Sales.</span><span class="sxs-lookup"><span data-stu-id="33857-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="33857-150">Jeżeli korzystasz z danych demonstracyjnych, zwykle użytkownik, ale nie zespół ma dostęp w trybie administratora.</span><span class="sxs-lookup"><span data-stu-id="33857-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="33857-151">Jeżeli zespół nie ma dostępu w trybie administratora po uruchomieniu projektu z integracji danych, zostanie wyświetlony komunikat o błędzie z informacją o braku zespołu sprzedającego.</span><span class="sxs-lookup"><span data-stu-id="33857-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="33857-152">Aby ustawić uprawnienia dla zespołu, przejdź do okna **Ustawienia** &gt; **Zabezpieczenia** &gt; **Zespoły** i wybierz odpowiedni zespół.</span><span class="sxs-lookup"><span data-stu-id="33857-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="33857-153">Wybierz opcję **Zarządzaj rolami**, a następnie wybierz rolę o odpowiednich uprawnieniach, na przykład **Administrator systemu**.</span><span class="sxs-lookup"><span data-stu-id="33857-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="33857-154">Przejdź do okna **Ustawienia** &gt; **Administracja** &gt; **Ustawienia systemu** &gt; **Sprzedaż** i sprawdź, czy używane są następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="33857-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="33857-155">Opcja **Użyj systemowego obliczania cen** jest ustawiona na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="33857-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="33857-156">Pole **Metoda kalkulacji rabatów** jest ustawione na **Pozycja w wierszu**.</span><span class="sxs-lookup"><span data-stu-id="33857-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="33857-157">Konfiguracja w projekcie integracji danych</span><span class="sxs-lookup"><span data-stu-id="33857-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="33857-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="33857-158">QuoteHeader</span></span>

- <span data-ttu-id="33857-159">Sprawdź, czy istnieje wymagane mapowanie dla **Shipto\_country** na **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="33857-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="33857-160">Na mapie wartości można zdefiniować wartość domyślną, która jest używana, jeżeli wartość zostanie pozostawiona pusta.</span><span class="sxs-lookup"><span data-stu-id="33857-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="33857-161">Pozostaw lewą stronę pustą i ustaw odpowiedni kraj lub region z prawej strony.</span><span class="sxs-lookup"><span data-stu-id="33857-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="33857-162">Dzięki temu nie trzeba wpisywać kraju ani regionu dla zamówień krajowych.</span><span class="sxs-lookup"><span data-stu-id="33857-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="33857-163">Wartość szablonu to mapa wartości, w które zmapowanych jest kilka krajów lub regionów, a pusta wartość jest równa wartości **US**.</span><span class="sxs-lookup"><span data-stu-id="33857-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="33857-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="33857-164">QuoteLine</span></span>

- <span data-ttu-id="33857-165">Upewnij się, że w rozwiązaniu Supply Chain Management istnieje wymagana mapa wartości dla pola **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="33857-165">Make sure that the required value map exists for **SalesUnitSymbol** in Supply Chain Management.</span></span>
- <span data-ttu-id="33857-166">Upewnij się, że w rozwiązaniu Sales skonfigurowano wymagane jednostki.</span><span class="sxs-lookup"><span data-stu-id="33857-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="33857-167">Wartość szablonu zawierająca mapę wartości jest zdefiniowana dla parametru **oumid.name** na **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="33857-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="33857-168">Opcjonalnie: Można dodać następujące mapowanie w celu zagwarantowania, że wiersze oferty sprzedaży są importowane do programu Supply Chain Management w razie braku domyślnych informacji o odbiorcy lub produkcie:</span><span class="sxs-lookup"><span data-stu-id="33857-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Supply Chain Management if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="33857-169">**SiteId** — Witryna jest konieczna do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="33857-170">Nie istnieje domyślna wartość szablonu dla pola **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="33857-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="33857-171">**WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="33857-172">Nie istnieje domyślna wartość szablonu dla pola **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="33857-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="33857-173">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="33857-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="33857-174">Pola **Rabat**, **Opłaty** i **Podatek** w nagłówku są kontrolowane przez skomplkowaną konfigurację w programie Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Supply Chain Management.</span></span> <span data-ttu-id="33857-175">Obecnie ta konfiguracja nie obsługuje mapowanie integracji.</span><span class="sxs-lookup"><span data-stu-id="33857-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="33857-176">W obecnym kształcie systemu pola **Cena**, **Rabat**, **Opłata** i **Podatek** są obsługiwane przez program Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="33857-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Supply Chain Management.</span></span>
> - <span data-ttu-id="33857-177">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="33857-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="33857-178">Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="33857-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="33857-179">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="33857-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="33857-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="33857-180">QuoteHeader</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="33857-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="33857-182">QuoteLine</span></span>

![Mapowanie szablonu w integratorze danych](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="33857-184">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="33857-184">Related topics</span></span>

[<span data-ttu-id="33857-185">Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="33857-185">Prospect to cash</span></span>](prospect-to-cash.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]