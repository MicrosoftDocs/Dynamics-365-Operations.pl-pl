---
title: "Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kontaktów (kontaktów) i kontaktów (odbiorców) między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
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
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 41e27776b94df059ada13efb9a3dbf6a29d67f36
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="627f1-103">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="627f1-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="627f1-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="627f1-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="627f1-105">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania jednostek Kontakt (kontaktów) i kontaktów (odbiorców) między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="627f1-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="627f1-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="627f1-106">Templates and tasks</span></span>

<span data-ttu-id="627f1-107">Następujące szablony i podstawowe zadania są używane do synchronizowania kontaktów (kontaktów) w programie Sales z kontaktami (odbiorcami) w programie Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="627f1-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="627f1-108">**Nazwy szablonów:**</span><span class="sxs-lookup"><span data-stu-id="627f1-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="627f1-109">Kontakty (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="627f1-109">Contacts (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="627f1-110">Kontakty z odbiorcami (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="627f1-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="627f1-111">**Nazwy zadań w projekcie:**</span><span class="sxs-lookup"><span data-stu-id="627f1-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="627f1-112">Kontakty</span><span class="sxs-lookup"><span data-stu-id="627f1-112">Contacts</span></span>
    - <span data-ttu-id="627f1-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="627f1-113">ContactToCustomer</span></span>

<span data-ttu-id="627f1-114">Przed rozpoczęciem synchronizowania kontaktów należy wykonać następujące zadanie synchronizacji: Konta (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="627f1-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="627f1-115">Zestawy jednostek</span><span class="sxs-lookup"><span data-stu-id="627f1-115">Entity sets</span></span>

| <span data-ttu-id="627f1-116">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="627f1-116">Sales</span></span>    | <span data-ttu-id="627f1-117">CDS</span><span class="sxs-lookup"><span data-stu-id="627f1-117">CDS</span></span>     | <span data-ttu-id="627f1-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="627f1-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="627f1-119">Kontakty</span><span class="sxs-lookup"><span data-stu-id="627f1-119">Contacts</span></span> | <span data-ttu-id="627f1-120">Kontakt</span><span class="sxs-lookup"><span data-stu-id="627f1-120">Contact</span></span> | <span data-ttu-id="627f1-121">Kontakty w usłudze CDS</span><span class="sxs-lookup"><span data-stu-id="627f1-121">CDS Contacts</span></span>           |
| <span data-ttu-id="627f1-122">Kontakty</span><span class="sxs-lookup"><span data-stu-id="627f1-122">Contacts</span></span> | <span data-ttu-id="627f1-123">Konto</span><span class="sxs-lookup"><span data-stu-id="627f1-123">Account</span></span> | <span data-ttu-id="627f1-124">Odbiorcy V2</span><span class="sxs-lookup"><span data-stu-id="627f1-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="627f1-125">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="627f1-125">Entity flow</span></span>

<span data-ttu-id="627f1-126">Kontakty są zarządzane w programie Sales oraz synchronizowane z usługą Common Data Service (CDS) i programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="627f1-127">Kontakt w programie Sales może stać się kontaktem w usłudze CDS i programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="627f1-128">Alternatywnie może się stać kontem klienta w usłudze CDS i programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="627f1-129">Aby ustalić, czy kontakt powinien zostać pobrany w programie Sales w celu synchronizacji z usługą CDS i programem Finance and Operations (na przykład kontakty z okna Sprzedaż &gt; Kontakt do okna CDS &gt; Kontakty i do programu Finance and Operations), system analizuje następujące właściwości kontaktu w programie Sales:</span><span class="sxs-lookup"><span data-stu-id="627f1-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="627f1-130">**Synchronizacja z kontem klienta w usłudze CDS i odbiorcą w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają zaznaczoną wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="627f1-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="627f1-131">**Synchronizacji z kontaktami w usłudze CDS i kontaktami w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają wartość **Nie**, a ustawienie **Firma** (konto nadrzędne/kontakt) wskazuje konto klienta (nie kontakt)</span><span class="sxs-lookup"><span data-stu-id="627f1-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="627f1-132">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="627f1-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="627f1-133">Do kontaktu dodano nowe pole **Aktywny odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="627f1-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="627f1-134">To pole służy do rozróżniania między kontaktami, które mają działania sprzedaży, a kontaktami, które nie mają takich działań.</span><span class="sxs-lookup"><span data-stu-id="627f1-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="627f1-135">Ustawienie **Aktywny odbiorca** ma wartość **Tak** tylko dla kontaktów, które mają powiązane oferty, zamówienia lub faktury.</span><span class="sxs-lookup"><span data-stu-id="627f1-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="627f1-136">Tylko te kontakty są synchronizowane z programem Finance and Operations jako odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="627f1-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="627f1-137">Do kontaktu dodano nowe pole **IsCompanyAnAccount**.</span><span class="sxs-lookup"><span data-stu-id="627f1-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="627f1-138">To pole wskazuje, czy kontakt jest połączony z firmą (kontem nadrzędnym/kontaktem) o typie **Konto**.</span><span class="sxs-lookup"><span data-stu-id="627f1-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="627f1-139">Ta informacja jest używana do identyfikowania kontaktów, które powinny być synchronizowane z programem Finance and Operations jako kontakty.</span><span class="sxs-lookup"><span data-stu-id="627f1-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="627f1-140">Do kontaktu dodano nowe pole **Numer osoby kontaktowej** w celu zagwarantowania naturalnego i unikatowego klucza integracji.</span><span class="sxs-lookup"><span data-stu-id="627f1-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="627f1-141">Podczas tworzenia nowego kontaktu wartość w polu **Numer kontaktowy** jest generowany automatycznie przy użyciu ustalonej numeracji.</span><span class="sxs-lookup"><span data-stu-id="627f1-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="627f1-142">Wartość składa się z przedrostka **CON**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka.</span><span class="sxs-lookup"><span data-stu-id="627f1-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="627f1-143">Oto przykład: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="627f1-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="627f1-144">Gdy rozwiązanie integracji dla programu Sales zostanie dodane do programu Sprzedaż, skrypt uaktualniania ustawia pole **Numer kontaktowy** dla istniejących kontaktów przy użyciu omówionej wcześniej numeracji.</span><span class="sxs-lookup"><span data-stu-id="627f1-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="627f1-145">Skrypt uaktualniania ustawia również w polu **Aktywny odbiorca** wartość **Tak** dla wszystkich kontaktów mających działania sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="627f1-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="627f1-146">W programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="627f1-146">In Finance and Operations</span></span> 

<span data-ttu-id="627f1-147">Kontakty są oznakowane za pomocą właściwości **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="627f1-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="627f1-148">Ta właściwość wskazuje, że dany kontakt jest obsługiwany zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="627f1-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="627f1-149">W takim przypadku zewnętrznie obsługiwane kontakty są prowadzone w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="627f1-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="627f1-150">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="627f1-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="627f1-151">Kontakt > kontakt</span><span class="sxs-lookup"><span data-stu-id="627f1-151">Contact to Contact</span></span>

- <span data-ttu-id="627f1-152">Zaktualizuj pole **Identyfikator organizacji CDS** w mapowaniu **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="627f1-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="627f1-153">Domyślna wartość pola **Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="627f1-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="627f1-154">Domyślna wartość pola **PrimaryAccount_Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="627f1-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="627f1-155">Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="627f1-156">Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Operacje**.</span><span class="sxs-lookup"><span data-stu-id="627f1-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="627f1-157">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="627f1-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="627f1-158">Domyślną wartością pola **PrimaryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.</span><span class="sxs-lookup"><span data-stu-id="627f1-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="627f1-159">Upewnij się, że w programie Finance and Operations istnieje wartość następującego pola.</span><span class="sxs-lookup"><span data-stu-id="627f1-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="627f1-160">Jeśli informacja nie jest wymagana w programie Finance and Operations, można usunąć mapowanie z mapowania **CDS &gt; Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="627f1-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="627f1-161">**Nazwa pola w programie Finance and Operations:** Decyzja</span><span class="sxs-lookup"><span data-stu-id="627f1-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="627f1-162">**Mapowanie:** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="627f1-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="627f1-163">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="627f1-163">Contact to Customer</span></span>

- <span data-ttu-id="627f1-164">Zaktualizuj pole **Identyfikator organizacji CDS** w mapowaniu **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="627f1-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="627f1-165">Domyślna wartość pola **Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="627f1-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="627f1-166">Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="627f1-167">Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="627f1-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="627f1-168">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="627f1-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="627f1-169">Domyślną wartością pola **PrimaryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.</span><span class="sxs-lookup"><span data-stu-id="627f1-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="627f1-170">Pole **CustomerGroup** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="627f1-171">Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="627f1-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="627f1-172">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="627f1-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="627f1-173">Domyślną wartością pola **CustomerGroupId** w szablonie jest **10**.</span><span class="sxs-lookup"><span data-stu-id="627f1-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="627f1-174">Dodając następujące mapowania z okna **CDS &gt; Miejsce docelowe**, można ograniczyć liczbę ręcznych aktualizacji wykonywanych w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="627f1-175">Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.</span><span class="sxs-lookup"><span data-stu-id="627f1-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="627f1-176">**SiteId** — W programie Finance and Operations można również określić domyślny oddział.</span><span class="sxs-lookup"><span data-stu-id="627f1-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="627f1-177">Oddział jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="627f1-178">Szablon nie ma zdefiniowanej domyślnej wartości pola **SiteID**.</span><span class="sxs-lookup"><span data-stu-id="627f1-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="627f1-179">**WarehouseId** — W programie Finance and Operations można również określić domyślny magazyn.</span><span class="sxs-lookup"><span data-stu-id="627f1-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="627f1-180">Magazyn jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="627f1-181">Szablon nie ma zdefiniowanej domyślnej wartości pola **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="627f1-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="627f1-182">**LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="627f1-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="627f1-183">Domyślna wartość pola **LanguageId** w szablonie to **en-us**.</span><span class="sxs-lookup"><span data-stu-id="627f1-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="627f1-184">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="627f1-184">Template mapping in data integrator</span></span>

<span data-ttu-id="627f1-185">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="627f1-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="627f1-186">Kontakt > kontakt</span><span class="sxs-lookup"><span data-stu-id="627f1-186">Contact to Contact</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-template-mapping-data-integrator-1.png)

![Mapowanie szablonu dla kontaktów w integratorze danych](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="627f1-189">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="627f1-189">Contact to Customer</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-template-mapping-data-integrator-3.png)

![Mapowanie szablonu dla kontaktów w integratorze danych](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="627f1-192">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="627f1-192">Related topics</span></span>

[<span data-ttu-id="627f1-193">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="627f1-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="627f1-194">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="627f1-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="627f1-195">Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="627f1-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="627f1-196">Synchronizowanie nagłówków i wierszy zamówień sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="627f1-196">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="627f1-197">Synchronizowanie nagłówków i wierszy faktur sprzedaży w rozwiązaniu Finance and Operations z elementami w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="627f1-197">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)

