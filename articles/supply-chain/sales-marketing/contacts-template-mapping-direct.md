---
title: Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management
description: W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania pozycji Kontakt (Kontakty) i Kontakt (Klienci) kont z Dynamics 365 Sales do rozwiązań Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 7bc4b48260907788eb90a19c5dc0b5c8f1d9d3b5
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908115"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a><span data-ttu-id="2d67a-103">Synchronizowanie kontaktów w rozwiązaniu Sales bezpośrednio z kontaktami lub odbiorcami w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2d67a-103">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="2d67a-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integrowanie danych na platformie Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="2d67a-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="2d67a-105">W tym temacie omówiono szablony i podstawowe zadania, które są używane do synchronizowania tabel Kontakt (Kontakty) i Kontakt (Klienci) kont bezpośrednio z Dynamics 365 Sales do rozwiązań Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) tables directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="2d67a-106">Przepływ danych w rozwiązaniu Prospekt na gotówkę</span><span class="sxs-lookup"><span data-stu-id="2d67a-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="2d67a-107">Rozwiązanie Prospekt na gotówkę korzysta z funkcji Integracji danych do synchronizacji danych między wystąpieniami Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="2d67a-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="2d67a-108">Szablony Prospekt na gotówkę, które są dostępne w funkcji integracji danych umożliwiają przepływ danych o kontach, kontaktach, produktach, ofertach sprzedaży, zamówieniach sprzedaży i fakturach sprzedaży między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="2d67a-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="2d67a-109">Poniższa ilustracja przedstawia sposób synchronizacji danych między usługą Supply Chain Management a Sales.</span><span class="sxs-lookup"><span data-stu-id="2d67a-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="2d67a-110">[![Przepływ danych w rozwiązaniu Prospekt na gotówkę](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="2d67a-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2d67a-111">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="2d67a-111">Templates and tasks</span></span>

<span data-ttu-id="2d67a-112">Aby wyświetlić dostępne szablony, otwórz [Centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="2d67a-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="2d67a-113">Wybierz opcję **Projekty**, a następnie w prawym górnym rogu wybierz opcję **Nowy projekt**, aby wybrać szablony publiczne.</span><span class="sxs-lookup"><span data-stu-id="2d67a-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="2d67a-114">Następujące szablony i podstawowe zadania są używane do synchronizowania tabel kontaktów (osób kontaktowych) w programie Sales z tabelami kontaktów (odbiorcami) w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) tables in Sales to Contact (Customers) tables in Supply Chain Management.</span></span>

- <span data-ttu-id="2d67a-115">**Nazwy szablonów w integracji danych**</span><span class="sxs-lookup"><span data-stu-id="2d67a-115">**Names of the templates in Data integration**</span></span>

    - <span data-ttu-id="2d67a-116">Kontakty (Sales to Supply Chain Management) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="2d67a-116">Contacts (Sales to Supply Chain Management) - Direct</span></span>
    - <span data-ttu-id="2d67a-117">Kontakty do Klienta (Sales to Supply Chain Management) — bezpośrednie</span><span class="sxs-lookup"><span data-stu-id="2d67a-117">Contacts to Customer (Sales to Supply Chain Management) - Direct</span></span>

- <span data-ttu-id="2d67a-118">**Nazwy zadań w projekcie integracji danych**</span><span class="sxs-lookup"><span data-stu-id="2d67a-118">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="2d67a-119">Kontakty</span><span class="sxs-lookup"><span data-stu-id="2d67a-119">Contacts</span></span>
    - <span data-ttu-id="2d67a-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="2d67a-120">ContactToCustomer</span></span>

<span data-ttu-id="2d67a-121">Przed rozpoczęciem synchronizowania kontaktów należy wykonać następujące zadanie synchronizacji: Konta (Z Sales do Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="2d67a-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Supply Chain Management)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="2d67a-122">Zestawy jednostek</span><span class="sxs-lookup"><span data-stu-id="2d67a-122">Entity sets</span></span>

| <span data-ttu-id="2d67a-123">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="2d67a-123">Sales</span></span>    | <span data-ttu-id="2d67a-124">Zarządzanie łańcuchem dostaw</span><span class="sxs-lookup"><span data-stu-id="2d67a-124">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="2d67a-125">Kontakty</span><span class="sxs-lookup"><span data-stu-id="2d67a-125">Contacts</span></span> | <span data-ttu-id="2d67a-126">Kontakty w usłudze Dataverse</span><span class="sxs-lookup"><span data-stu-id="2d67a-126">Dataverse Contacts</span></span>           |
| <span data-ttu-id="2d67a-127">Kontakty</span><span class="sxs-lookup"><span data-stu-id="2d67a-127">Contacts</span></span> | <span data-ttu-id="2d67a-128">Odbiorcy V2</span><span class="sxs-lookup"><span data-stu-id="2d67a-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="2d67a-129">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="2d67a-129">Entity flow</span></span>

<span data-ttu-id="2d67a-130">Kontakty są zarządzane w usłudze Sales i synchronizowane z usługą Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-130">Contacts are managed in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="2d67a-131">Kontakt w programie Sales może stać się kontaktem lub odbiorcą w rozwiązaniu Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-131">A contact in Sales can become either a contact or a customer in Supply Chain Management.</span></span> <span data-ttu-id="2d67a-132">Aby określić, czy kontakt w programie Sales ma być synchronizowany z programem Supply Chain Management jako kontakt lub odbiorca, system sprawdza następujące właściwości kontaktu w programie Sales:</span><span class="sxs-lookup"><span data-stu-id="2d67a-132">To determine whether a contact in Sales should be synchronized to Supply Chain Management as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="2d67a-133">**Synchronizacja z klientem w programie Supply Chain Management:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają zaznaczoną wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="2d67a-133">**Synchronization to a customer in Supply Chain Management:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="2d67a-134">**Synchronizacja z kontaktem w programie Supply Chain Management:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają wartość **Nie**, a ustawienie **Firma** (konto nadrzędne/kontakt) wskazuje na konto (nie kontakt)</span><span class="sxs-lookup"><span data-stu-id="2d67a-134">**Synchronization to a contact in Supply Chain Management:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="2d67a-135">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="2d67a-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="2d67a-136">Do kontaktu dodano nową kolumnę **Aktywny odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-136">A new **Is Active Customer** column has been added to the contact.</span></span> <span data-ttu-id="2d67a-137">Ta kolumna służy do rozróżniania między kontaktami, które mają działania sprzedaży, a kontaktami, które nie mają takich działań.</span><span class="sxs-lookup"><span data-stu-id="2d67a-137">This column is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="2d67a-138">Ustawienie **Aktywny odbiorca** ma wartość **Tak** tylko dla kontaktów, które mają powiązane oferty, zamówienia lub faktury.</span><span class="sxs-lookup"><span data-stu-id="2d67a-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="2d67a-139">Tylko te kontakty są synchronizowane z programem Supply Chain Management jako odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="2d67a-139">Only those contacts are synchronized to Supply Chain Management as customers.</span></span>

<span data-ttu-id="2d67a-140">Do kolumny dodano nowe pole **IsCompanyAnAccount**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-140">A new **IsCompanyAnAccount** column has been added to the contact.</span></span> <span data-ttu-id="2d67a-141">Ta kolumna wskazuje, czy kontakt jest połączony z firmą (kontem nadrzędnym/kontaktem) o typie **Konto**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-141">This column indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="2d67a-142">Ta informacja jest używana do identyfikowania kontaktów, które powinny być synchronizowane z programem Supply Chain Management jako kontakty.</span><span class="sxs-lookup"><span data-stu-id="2d67a-142">This information is used to identify contacts that should be synchronized to Supply Chain Management as contacts.</span></span>

<span data-ttu-id="2d67a-143">Do kontaktu dodano nową kolumnę **Numer osoby kontaktowej** w celu zagwarantowania naturalnego i unikatowego klucza integracji.</span><span class="sxs-lookup"><span data-stu-id="2d67a-143">A new **Contact Number** column has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="2d67a-144">Podczas tworzenia nowego kontaktu wartość w polu **Numer kontaktowy** jest generowany automatycznie przy użyciu ustalonej numeracji.</span><span class="sxs-lookup"><span data-stu-id="2d67a-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="2d67a-145">Wartość składa się z przedrostka **CON**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka.</span><span class="sxs-lookup"><span data-stu-id="2d67a-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="2d67a-146">Oto przykład: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="2d67a-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="2d67a-147">Gdy rozwiązanie integracji dla programu Sales zostanie zastosowane, skrypt uaktualniania ustawia kolumnę **Numer kontaktowy** dla istniejących kontaktów przy użyciu omówionej wcześniej numeracji.</span><span class="sxs-lookup"><span data-stu-id="2d67a-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** column for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="2d67a-148">Skrypt uaktualniania ustawia również w kolumnie **Aktywny odbiorca** wartość **Tak** dla wszystkich kontaktów mających działania sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2d67a-148">The upgrade script also sets the **Is Active Customer** column to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-supply-chain-management"></a><span data-ttu-id="2d67a-149">W Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2d67a-149">In Supply Chain Management</span></span>

<span data-ttu-id="2d67a-150">Kontakty są oznakowane za pomocą właściwości **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="2d67a-151">Ta właściwość wskazuje, że dany kontakt jest obsługiwany zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="2d67a-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="2d67a-152">W takim przypadku zewnętrznie obsługiwane kontakty są prowadzone w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="2d67a-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="2d67a-153">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="2d67a-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="2d67a-154">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="2d67a-154">Contact to customer</span></span>

- <span data-ttu-id="2d67a-155">**CustomerGroup** jest wymagane w Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-155">**CustomerGroup** is required in Supply Chain Management.</span></span> <span data-ttu-id="2d67a-156">Aby ułatwić uniknięcie błędów synchronizacji, można określić wartość domyślną w mapowaniu.</span><span class="sxs-lookup"><span data-stu-id="2d67a-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="2d67a-157">Ta wartość domyślna będzie następnie używana, jeśli ta kolumna pozostanie pusta w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="2d67a-157">That default value is then used if the column is left blank in Sales.</span></span>

    <span data-ttu-id="2d67a-158">Wartość domyślna w szablonie to **10**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-158">The default template value is **10**.</span></span>

- <span data-ttu-id="2d67a-159">Dodając następujące mapowania, można ograniczyć liczbę koniecznych ręcznych aktualizacji wymaganych w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="2d67a-160">Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="2d67a-161">**SiteId** — W programie Supply Chain Management można również określić domyślny oddział.</span><span class="sxs-lookup"><span data-stu-id="2d67a-161">**SiteId** – A default site can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="2d67a-162">Witryna jest konieczna do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-162">A site is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="2d67a-163">Szablon nie ma zdefiniowanej domyślnej wartości pola **SiteID**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="2d67a-164">**WarehouseId** — W programie Supply Chain Management można również określić domyślny magazyn.</span><span class="sxs-lookup"><span data-stu-id="2d67a-164">**WarehouseId** – A default warehouse can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="2d67a-165">Magazyn jest konieczny do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-165">A warehouse is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="2d67a-166">Szablon nie ma zdefiniowanej domyślnej wartości pola **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="2d67a-167">**LanguageId** — Język jest konieczny do generowania ofert i wierszy zamówień sprzedaży w usłudze Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>
    
        <span data-ttu-id="2d67a-168">Domyślna wartość pola w szablonie to **en-us**.</span><span class="sxs-lookup"><span data-stu-id="2d67a-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2d67a-169">Mapowanie szablonu w integracji danych</span><span class="sxs-lookup"><span data-stu-id="2d67a-169">Template mapping in Data integration</span></span>

<span data-ttu-id="2d67a-170">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="2d67a-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="2d67a-171">Mapowanie pokazuje, które informacje z kolumn zostaną zsynchronizowane z rozwiązania Sales do rozwiązania Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2d67a-171">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="2d67a-172">Kontakt > kontakt</span><span class="sxs-lookup"><span data-stu-id="2d67a-172">Contact to contact</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="2d67a-174">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="2d67a-174">Contact to customer</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="2d67a-176">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="2d67a-176">Related topics</span></span>

[<span data-ttu-id="2d67a-177">Od prospekta do gotówki</span><span class="sxs-lookup"><span data-stu-id="2d67a-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="2d67a-178">Synchronizowanie kont klientów bezpośrednio z rozwiązania Sales do odbiorców w Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2d67a-178">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="2d67a-179">Synchronizowanie produktów bezpośrednio z rozwiązania Supply Chain Management do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="2d67a-179">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="2d67a-180">Synchronizowanie zamówień sprzedaży w rozwiązaniu Sales bezpośrednio z elementami w rozwiązaniu Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2d67a-180">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="2d67a-181">Synchronizowanie nagłówków faktur i wierszy zamówień sprzedaży w rozwiązaniu Supply Chain Management bezpośrednio z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="2d67a-181">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]