---
title: "Synchronizowanie kontaktów bezpośrednio w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania jednostek Kontakty (kontakty) i Kontakty (odbiorcy) między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 95b7d5be86676a1442df1c71308cb978b854d2c8
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="7b084-103">Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7b084-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="7b084-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="7b084-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="7b084-105">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania jednostek Kontakty (kontakty) i Kontakty (odbiorcy) bezpośrednio między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="7b084-106">Przepływ danych w rozwiązaniu Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="7b084-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="7b084-107">Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracja danych do synchronizacji danych między wystąpieniami programu Finance and Operations a programem Sales.</span><span class="sxs-lookup"><span data-stu-id="7b084-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="7b084-108">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między programami Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="7b084-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="7b084-109">Poniższa ilustracja przedstawia sposób synchronizacji danych między programami Finance and Operations a Sales.</span><span class="sxs-lookup"><span data-stu-id="7b084-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="7b084-110">[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="7b084-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="7b084-111">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="7b084-111">Templates and tasks</span></span>

<span data-ttu-id="7b084-112">Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="7b084-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="7b084-113">Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="7b084-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="7b084-114">Następujące szablony i podstawowe zadania są używane do synchronizowania jednostek kontaktów (kontaktów) w programie Sales z jednostkami kontaktów (odbiorcami) w programie Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="7b084-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="7b084-115">**Nazwy szablonów w integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="7b084-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="7b084-116">Kontakty (z Sales do Fin and Ops) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="7b084-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="7b084-117">Kontakty z odbiorcami (z Sales do Fin and Ops) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="7b084-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="7b084-118">**Nazwy zadań w projekcie integracji danych:**</span><span class="sxs-lookup"><span data-stu-id="7b084-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="7b084-119">Kontakty</span><span class="sxs-lookup"><span data-stu-id="7b084-119">Contacts</span></span>
    - <span data-ttu-id="7b084-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="7b084-120">ContactToCustomer</span></span>

<span data-ttu-id="7b084-121">Przed rozpoczęciem synchronizowania kontaktów należy wykonać następujące zadanie synchronizacji: Konta (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7b084-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="7b084-122">Zestawy jednostek</span><span class="sxs-lookup"><span data-stu-id="7b084-122">Entity sets</span></span>

| <span data-ttu-id="7b084-123">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="7b084-123">Sales</span></span>    | <span data-ttu-id="7b084-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7b084-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="7b084-125">Kontakty</span><span class="sxs-lookup"><span data-stu-id="7b084-125">Contacts</span></span> | <span data-ttu-id="7b084-126">Kontakty w usłudze CDS</span><span class="sxs-lookup"><span data-stu-id="7b084-126">CDS Contacts</span></span>           |
| <span data-ttu-id="7b084-127">Kontakty</span><span class="sxs-lookup"><span data-stu-id="7b084-127">Contacts</span></span> | <span data-ttu-id="7b084-128">Odbiorcy V2</span><span class="sxs-lookup"><span data-stu-id="7b084-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="7b084-129">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="7b084-129">Entity flow</span></span>

<span data-ttu-id="7b084-130">Produkty są zarządzane w programie Sales i synchronizowane z programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="7b084-131">Kontakt w programie Sales może stać się kontaktem lub odbiorcą w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="7b084-132">Aby określić, czy kontakt w programie Sales ma być synchronizowany z programem Finance and Operations jako kontakt lub odbiorca, system sprawdza następujące właściwości kontaktu w programie Sales:</span><span class="sxs-lookup"><span data-stu-id="7b084-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="7b084-133">**Synchronizacja z klientem w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają zaznaczoną wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="7b084-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="7b084-134">**Synchronizacja z kontaktem w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają wartość **Nie**, a ustawienie **Firma** (konto nadrzędne/kontakt) wskazuje na konto (nie kontakt)</span><span class="sxs-lookup"><span data-stu-id="7b084-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="7b084-135">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="7b084-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="7b084-136">Do kontaktu dodano nowe pole **Aktywny odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="7b084-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="7b084-137">To pole służy do rozróżniania między kontaktami, które mają działania sprzedaży, a kontaktami, które nie mają takich działań.</span><span class="sxs-lookup"><span data-stu-id="7b084-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="7b084-138">Ustawienie **Aktywny odbiorca** ma wartość **Tak** tylko dla kontaktów, które mają powiązane oferty, zamówienia lub faktury.</span><span class="sxs-lookup"><span data-stu-id="7b084-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="7b084-139">Tylko te kontakty są synchronizowane z programem Finance and Operations jako odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="7b084-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="7b084-140">Do kontaktu dodano nowe pole **IsCompanyAnAccount**.</span><span class="sxs-lookup"><span data-stu-id="7b084-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="7b084-141">To pole wskazuje, czy kontakt jest połączony z firmą (kontem nadrzędnym/kontaktem) o typie **Konto**.</span><span class="sxs-lookup"><span data-stu-id="7b084-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="7b084-142">Ta informacja jest używana do identyfikowania kontaktów, które powinny być synchronizowane z programem Finance and Operations jako kontakty.</span><span class="sxs-lookup"><span data-stu-id="7b084-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="7b084-143">Do kontaktu dodano nowe pole **Numer osoby kontaktowej** w celu zagwarantowania naturalnego i unikatowego klucza integracji.</span><span class="sxs-lookup"><span data-stu-id="7b084-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="7b084-144">Podczas tworzenia nowego kontaktu wartość w polu **Numer kontaktowy** jest generowany automatycznie przy użyciu ustalonej numeracji.</span><span class="sxs-lookup"><span data-stu-id="7b084-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="7b084-145">Wartość składa się z przedrostka **CON**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka.</span><span class="sxs-lookup"><span data-stu-id="7b084-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="7b084-146">Oto przykład: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="7b084-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="7b084-147">Gdy rozwiązanie integracji dla programu Sales zostanie zastosowane, skrypt uaktualniania ustawia pole **Numer kontaktowy** dla istniejących kontaktów przy użyciu omówionej wcześniej numeracji.</span><span class="sxs-lookup"><span data-stu-id="7b084-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="7b084-148">Skrypt uaktualniania ustawia również w polu **Aktywny odbiorca** wartość **Tak** dla wszystkich kontaktów mających działania sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="7b084-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="7b084-149">W programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7b084-149">In Finance and Operations</span></span>

<span data-ttu-id="7b084-150">Kontakty są oznakowane za pomocą właściwości **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="7b084-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="7b084-151">Ta właściwość wskazuje, że dany kontakt jest obsługiwany zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="7b084-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="7b084-152">W takim przypadku zewnętrznie obsługiwane kontakty są prowadzone w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="7b084-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="7b084-153">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="7b084-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="7b084-154">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="7b084-154">Contact to customer</span></span>

- <span data-ttu-id="7b084-155">Pole **CustomerGroup** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="7b084-156">Aby ułatwić uniknięcie błędów synchronizacji, można określić wartość domyślną w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="7b084-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="7b084-157">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="7b084-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="7b084-158">Wartość domyślna w szablonie to **10**.</span><span class="sxs-lookup"><span data-stu-id="7b084-158">The default template value is **10**.</span></span>

- <span data-ttu-id="7b084-159">Dodając następujące mapowania, można ograniczyć liczbę koniecznych ręcznych aktualizacji wykonywanych w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="7b084-160">Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.</span><span class="sxs-lookup"><span data-stu-id="7b084-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="7b084-161">**SiteId** — W programie Finance and Operations można również określić domyślny oddział.</span><span class="sxs-lookup"><span data-stu-id="7b084-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="7b084-162">Oddział jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="7b084-163">Szablon nie ma zdefiniowanej domyślnej wartości pola **SiteID**.</span><span class="sxs-lookup"><span data-stu-id="7b084-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="7b084-164">**WarehouseId** — W programie Finance and Operations można również określić domyślny magazyn.</span><span class="sxs-lookup"><span data-stu-id="7b084-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="7b084-165">Magazyn jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="7b084-166">Szablon nie ma zdefiniowanej domyślnej wartości pola **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="7b084-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="7b084-167">**LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="7b084-168">Domyślna wartość pola w szablonie to **en-us**.</span><span class="sxs-lookup"><span data-stu-id="7b084-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7b084-169">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="7b084-169">Template mapping in Data integration</span></span>

<span data-ttu-id="7b084-170">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="7b084-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="7b084-171">Mapowanie pokazuje, które informacje z pól zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7b084-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="7b084-172">Kontakt > kontakt</span><span class="sxs-lookup"><span data-stu-id="7b084-172">Contact to contact</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="7b084-174">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="7b084-174">Contact to customer</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="7b084-176">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="7b084-176">Related topics</span></span>

[<span data-ttu-id="7b084-177">Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="7b084-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="7b084-178">Synchronizowanie kont bezpośrednio w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7b084-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="7b084-179">Synchronizowanie produktów bezpośrednio w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="7b084-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="7b084-180">Synchronizowanie nagłówków i wierszy zamówień sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="7b084-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="7b084-181">Synchronizowanie nagłówków i wierszy faktur sprzedaży bezpośrednio w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="7b084-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



