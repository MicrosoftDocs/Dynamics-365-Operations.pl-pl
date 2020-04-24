---
title: Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management
description: Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont z Dynamics 365 Sales do Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 1146fce7cf620a002231a5bc9246c706b97d478d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210141"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a><span data-ttu-id="af1dc-103">Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="af1dc-103">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="af1dc-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="af1dc-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="af1dc-105">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont bezpośrednio z Dynamics 365 Sales do Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="af1dc-106">Przepływ danych w rozwiązaniu Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="af1dc-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="af1dc-107">Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="af1dc-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span>  <span data-ttu-id="af1dc-108">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="af1dc-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="af1dc-109">Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="af1dc-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="af1dc-110">[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="af1dc-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="af1dc-111">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="af1dc-111">Templates and tasks</span></span>

<span data-ttu-id="af1dc-112">Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="af1dc-112">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="af1dc-113">Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="af1dc-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="af1dc-114">Następujący szablon i podstawowe zadanie są używane do synchronizowania kont klientów z usługi Sales do Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="af1dc-114">The following template and underlying task are used to synchronize accounts from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="af1dc-115">**Nazwa szablonu w integracji danych:** Konta (Sales do Fin and Ops) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="af1dc-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="af1dc-116">**Nazwa zadania w projekcie:** Konta - odbiorcy</span><span class="sxs-lookup"><span data-stu-id="af1dc-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="af1dc-117">Przed zsynchronizowaniem konta/odbiorcy nie jest wymagane wykonanie zadań synchronizacji.</span><span class="sxs-lookup"><span data-stu-id="af1dc-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="af1dc-118">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="af1dc-118">Entity set</span></span>

| <span data-ttu-id="af1dc-119">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="af1dc-119">Sales</span></span>    | <span data-ttu-id="af1dc-120">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="af1dc-120">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="af1dc-121">Konta</span><span class="sxs-lookup"><span data-stu-id="af1dc-121">Accounts</span></span> | <span data-ttu-id="af1dc-122">Odbiorcy V2</span><span class="sxs-lookup"><span data-stu-id="af1dc-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="af1dc-123">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="af1dc-123">Entity flow</span></span>

<span data-ttu-id="af1dc-124">Konta klientów są zarządzane w usłudze Sales i synchronizowane z usługą Supply Chain Management jako odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="af1dc-124">Accounts are managed in Sales and synchronized to Supply Chain Management as customers.</span></span> <span data-ttu-id="af1dc-125">Właściwość **Obsługiwane zewnętrznie** u tych odbiorców ma ustawioną wartość **Tak**, aby śledzić odbiorców pochodzących z aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="af1dc-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="af1dc-126">Podczas fakturowania ta informacja jest używana do filtrowania faktur synchronizowanych z aplikacją Sales.</span><span class="sxs-lookup"><span data-stu-id="af1dc-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="af1dc-127">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="af1dc-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="af1dc-128">Pole **Numeru konta** jest dostępne na stronie **Konto**.</span><span class="sxs-lookup"><span data-stu-id="af1dc-128">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="af1dc-129">Jego wartość pełni rolę naturalnego i unikatowego klucza wspierającego integrację.</span><span class="sxs-lookup"><span data-stu-id="af1dc-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="af1dc-130">Funkcja klucza naturalnego w rozwiązaniu zarządzania relacjami z klientami (CRM) może mieć wpływ na klientów, którzy już korzystają z pola **Numeru konta**, ale którzy nie używają unikatowych wartości **Numer konta** dla każdego poszczególnych kont klientów.</span><span class="sxs-lookup"><span data-stu-id="af1dc-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="af1dc-131">Obecnie rozwiązanie integracji nie obsługuje takiego przypadku.</span><span class="sxs-lookup"><span data-stu-id="af1dc-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="af1dc-132">Podczas tworzenia nowego konta klienta jeśli wartość **Numer konta** jeszcze nie istnieje, jest generowana automatycznie przy użyciu numeracji.</span><span class="sxs-lookup"><span data-stu-id="af1dc-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="af1dc-133">Wartość składa się z przedrostka **ACC**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka.</span><span class="sxs-lookup"><span data-stu-id="af1dc-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="af1dc-134">Oto przykład: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="af1dc-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="af1dc-135">Gdy rozwiązanie integracji jest stosowane do aplikacji Sales, skrypt uaktualniania ustawia pole **Numer konta** dla istniejących kont klientów w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="af1dc-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="af1dc-136">Jeśli nie ma wartości **Numer konta**, jest używana numeracja podana wcześniej.</span><span class="sxs-lookup"><span data-stu-id="af1dc-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="af1dc-137">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="af1dc-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="af1dc-138">Mapowanie pola **CustomerGroupId** musi zostać zaktualizowane o prawidłową wartość w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-138">The **CustomerGroupId** mapping must be updated to a valid value in Supply Chain Management.</span></span> <span data-ttu-id="af1dc-139">Można określić wartość domyślną albo ustawiać wartość przy użyciu mapy wartości.</span><span class="sxs-lookup"><span data-stu-id="af1dc-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="af1dc-140">Wartość domyślna w szablonie to **10**.</span><span class="sxs-lookup"><span data-stu-id="af1dc-140">The default template value is **10**.</span></span>

- <span data-ttu-id="af1dc-141">Dodając następujące mapowania, można ograniczyć liczbę koniecznych ręcznych aktualizacji wymaganych w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="af1dc-142">Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.</span><span class="sxs-lookup"><span data-stu-id="af1dc-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="af1dc-143">**SiteId** — Witryna jest konieczna do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="af1dc-144">Domyślny oddział może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia.</span><span class="sxs-lookup"><span data-stu-id="af1dc-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="af1dc-145">Wartość domyślna w szablonie to **1**.</span><span class="sxs-lookup"><span data-stu-id="af1dc-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="af1dc-146">**WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="af1dc-147">Domyślny magazyn może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-147">A default warehouse can be taken either from the product, or from the customer from the order header in Supply Chain Management.</span></span>

        <span data-ttu-id="af1dc-148">Wartość domyślna w szablonie to **13**.</span><span class="sxs-lookup"><span data-stu-id="af1dc-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="af1dc-149">**LanguageId** — Język jest konieczny do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span> <span data-ttu-id="af1dc-150">Domyślnie jest używany język z nagłówka zamówienia od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="af1dc-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="af1dc-151">Domyślna wartość pola w szablonie to **en-us**.</span><span class="sxs-lookup"><span data-stu-id="af1dc-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="af1dc-152">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="af1dc-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="af1dc-153">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="af1dc-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="af1dc-154">Aby zamapować te pola, należy skonfigurować mapowanie wartości specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="af1dc-154">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="af1dc-155">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="af1dc-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="af1dc-156">Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="af1dc-156">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mapowanie szablonu w integracji danych](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="af1dc-158">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="af1dc-158">Related topics</span></span>


[<span data-ttu-id="af1dc-159">Od prospekta do gotówki</span><span class="sxs-lookup"><span data-stu-id="af1dc-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="af1dc-160">Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="af1dc-160">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="af1dc-161">Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="af1dc-161">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="af1dc-162">Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="af1dc-162">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="af1dc-163">Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="af1dc-163">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)

