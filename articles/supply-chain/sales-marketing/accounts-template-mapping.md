---
title: "Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations"
description: "Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont klientów między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
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
ms.openlocfilehash: 1fdbeaaba53cd439d9872be78b1cf67cbc5a57b9
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="3670e-103">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3670e-103">Synchronize accounts from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="3670e-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="3670e-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="3670e-105">Temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kont klientów między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="3670e-105">The topic discusses the templates and underlying tasks that are used to synchronize accounts from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="template-and-task"></a><span data-ttu-id="3670e-106">Szablon i zadanie</span><span class="sxs-lookup"><span data-stu-id="3670e-106">Template and task</span></span>

<span data-ttu-id="3670e-107">Następujące szablony i podstawowe zadania są używane do synchronizowania kont klientów z programu Sales do programu Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="3670e-107">The following templates and underlying tasks are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="3670e-108">**Nazwa szablonu:** Konta (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="3670e-108">**Name of the template:** Accounts (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="3670e-109">**Nazwa zadania w projekcie:** Konta - konto - odbiorcy</span><span class="sxs-lookup"><span data-stu-id="3670e-109">**Name of the task in the project:** Accounts - Account - Customers</span></span>

<span data-ttu-id="3670e-110">Zadania synchronizacji wymagane przed synchronizacją konto/odbiorca: brak</span><span class="sxs-lookup"><span data-stu-id="3670e-110">Sync tasks required prior to Account / Customer sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="3670e-111">Zestaw jednostek</span><span class="sxs-lookup"><span data-stu-id="3670e-111">Entity set</span></span>

| <span data-ttu-id="3670e-112">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="3670e-112">Sales</span></span>    | <span data-ttu-id="3670e-113">CDS</span><span class="sxs-lookup"><span data-stu-id="3670e-113">CDS</span></span>     | <span data-ttu-id="3670e-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3670e-114">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="3670e-115">Konta</span><span class="sxs-lookup"><span data-stu-id="3670e-115">Accounts</span></span> | <span data-ttu-id="3670e-116">Konto</span><span class="sxs-lookup"><span data-stu-id="3670e-116">Account</span></span> | <span data-ttu-id="3670e-117">Odbiorcy</span><span class="sxs-lookup"><span data-stu-id="3670e-117">Customers</span></span>              |

## <a name="entity-flow"></a><span data-ttu-id="3670e-118">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="3670e-118">Entity flow</span></span>

<span data-ttu-id="3670e-119">Konta klientów są zarządzane w programie Sales i synchronizowane z programem Finance and Operations jako odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="3670e-119">Accounts are managed in Sales and synchronized to Finance and Operations as Customers.</span></span> <span data-ttu-id="3670e-120">Właściwość **Obsługiwane zewnętrznie** u tych odbiorców ma ustawioną wartość **Tak**, aby śledzić odbiorców pochodzących z aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="3670e-120">The **Is Externally Maintained** property on these Customers is set to **Yes** to track Customers that originate from Sales.</span></span> <span data-ttu-id="3670e-121">Podczas fakturowania ta informacja jest używana do filtrowania faktur synchronizowanych z aplikacją Sales.</span><span class="sxs-lookup"><span data-stu-id="3670e-121">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="3670e-122">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="3670e-122">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="3670e-123">Pole **Numeru konta** jest dostępne na stronie **Konto**.</span><span class="sxs-lookup"><span data-stu-id="3670e-123">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="3670e-124">Jego wartość pełni rolę naturalnego i unikatowego klucza wspierającego integrację.</span><span class="sxs-lookup"><span data-stu-id="3670e-124">It has been made a natural and unique key to support the integration.</span></span> <span data-ttu-id="3670e-125">Funkcja klucza naturalnego w rozwiązaniu zarządzania relacjami z klientami (CRM) może mieć wpływ na klientów, którzy już korzystają z pola **Numeru konta**, ale którzy nie używają unikatowych wartości **Numer konta** dla każdego poszczególnych kont klientów.</span><span class="sxs-lookup"><span data-stu-id="3670e-125">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="3670e-126">Obecnie rozwiązanie integracji nie obsługuje takiego przypadku.</span><span class="sxs-lookup"><span data-stu-id="3670e-126">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="3670e-127">Podczas tworzenia nowego konta klienta jeśli wartość **Numer konta** jeszcze nie istnieje, jest generowana automatycznie przy użyciu numeracji.</span><span class="sxs-lookup"><span data-stu-id="3670e-127">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="3670e-128">Wartość składa się z przedrostka **ACC**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka.</span><span class="sxs-lookup"><span data-stu-id="3670e-128">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="3670e-129">Oto przykład: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="3670e-129">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="3670e-130">Gdy rozwiązanie integracji jest stosowane do aplikacji Sales, skrypt uaktualniania ustawia pole **Numer konta** dla istniejących kont klientów w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="3670e-130">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="3670e-131">Jeśli nie ma wartości **Numer konta**, jest używana numeracja opisana wcześniej.</span><span class="sxs-lookup"><span data-stu-id="3670e-131">If there are no **Account Number** values, the number sequence that was described earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="3670e-132">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="3670e-132">Preconditions and mapping setup</span></span>

- <span data-ttu-id="3670e-133">Mapowanie pola **CustomerGroupId** z **CDS &gt; Miejsce docelowe** musi zostać zaktualizowane o prawidłową wartość w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3670e-133">**CustomerGroupId** mapping from **CDS &gt; Destination** must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="3670e-134">Można określić wartość domyślną albo ustawiać wartość przy użyciu mapy wartości.</span><span class="sxs-lookup"><span data-stu-id="3670e-134">You can specify a default value, or you can set the value by using a value map.</span></span> <span data-ttu-id="3670e-135">Wartość domyślna w szablonie to **10**.</span><span class="sxs-lookup"><span data-stu-id="3670e-135">The default template value is **10**.</span></span>
- <span data-ttu-id="3670e-136">Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3670e-136">**Address country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="3670e-137">Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu z **CDS &gt; Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="3670e-137">To avoid synchronization errors, you can specify a default value in the mapping from **CDS &gt; Destination**.</span></span> <span data-ttu-id="3670e-138">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="3670e-138">That default value is then used if the field is left blank in Sales.</span></span>

    - <span data-ttu-id="3670e-139">Domyślna wartość pola **AddressCountryRegionISOCode** w szablonie to **USA**.</span><span class="sxs-lookup"><span data-stu-id="3670e-139">The default template value for **AddressCountryRegionISOCode** is **USA**.</span></span>
    - <span data-ttu-id="3670e-140">Domyślną wartością pola **DeliveryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.</span><span class="sxs-lookup"><span data-stu-id="3670e-140">The default template value for **DeliveryAddressCountryRegionISOCode** is **USA**.</span></span>

- <span data-ttu-id="3670e-141">Dodając następujące mapowania z okna **CDS &gt; Miejsce docelowe**, można ograniczyć liczbę koniecznych ręcznych aktualizacji wykonywanych w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3670e-141">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="3670e-142">Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.</span><span class="sxs-lookup"><span data-stu-id="3670e-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="3670e-143">**SiteId** — Oddział jest konieczny do generowania ofert i wierszy zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3670e-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="3670e-144">Domyślny oddział może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia.</span><span class="sxs-lookup"><span data-stu-id="3670e-144">A default site can be taken either from the product, or from the customer from the order header.</span></span> <span data-ttu-id="3670e-145">Domyślną wartością pola **SiteId** w szablonie jest **1**.</span><span class="sxs-lookup"><span data-stu-id="3670e-145">The default template value for **SiteId** is **1**.</span></span>
    - <span data-ttu-id="3670e-146">**WarehouseId** — Magazyn jest konieczny do przetwarzania ofert i wierszy zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3670e-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="3670e-147">Domyślny magazyn może być pobierany z produktu albo od odbiorcy z nagłówka zamówienia w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3670e-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span> <span data-ttu-id="3670e-148">Domyślną wartością pola **WarehouseId** w szablonie jest **13**.</span><span class="sxs-lookup"><span data-stu-id="3670e-148">The default template value for **WarehouseId** is **13**.</span></span>
    - <span data-ttu-id="3670e-149">**LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3670e-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="3670e-150">Domyślnie jest używany język z nagłówka zamówienia od odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="3670e-150">By default, the language from the order header from the customer is used.</span></span> <span data-ttu-id="3670e-151">Domyślna wartość pola **LanguageId** w szablonie to **en-us**.</span><span class="sxs-lookup"><span data-stu-id="3670e-151">The default template value for **LanguageId** is **en-us**.</span></span>

- <span data-ttu-id="3670e-152">Zaktualizuj identyfikator organizacji w usłudze CDS (**Organization_OrganizationId**) w mapowaniu **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="3670e-152">Update the CDS organization ID (**Organization_OrganizationId**) in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="3670e-153">Wartość domyślna w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="3670e-153">The default template value is **ORG001**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="3670e-154">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="3670e-154">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="3670e-155">Pola **Warunki płatności**, **Warunki frachtu**, **Warunki dostawy**, **Metoda wysyłki** i **Metoda dostawy** nie wchodzą w skład zbioru domyślnych mapowań.</span><span class="sxs-lookup"><span data-stu-id="3670e-155">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="3670e-156">Aby zamapować pola, należy skonfigurować mapowanie wartości.</span><span class="sxs-lookup"><span data-stu-id="3670e-156">To map these fields, you must set up a value mapping.</span></span> <span data-ttu-id="3670e-157">Mapowania wartości są specyficzne dla danych w organizacjach, między którymi jest synchronizowana jednostka.</span><span class="sxs-lookup"><span data-stu-id="3670e-157">Value mappings are specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="3670e-158">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="3670e-158">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapowanie szablonu w integratorze danych](./media/accounts-template-mapping-data-integrator-1.png)

![Mapowanie szablonu dla kont klientów w integratorze danych](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="3670e-161">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="3670e-161">Related topics</span></span>

[<span data-ttu-id="3670e-162">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="3670e-162">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="3670e-163">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3670e-163">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="3670e-164">Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3670e-164">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="3670e-165">Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="3670e-165">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="3670e-166">Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="3670e-166">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)




