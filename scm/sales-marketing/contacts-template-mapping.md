---
title: "Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations"
description: "Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania kontaktów (kontaktów) i kontaktów (odbiorców) między programem Microsoft Dynamics 365 for Sales a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
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
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 7a856a9460d092925a34a0733f37f89354c2ddf1
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="ec9cb-103">Synchronizowanie kontaktów w rozwiązaniu Sales do kontaktów lub odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec9cb-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ec9cb-104">Zanim zaczniesz używać rozwiązania Prospekt na gotówkę, zapoznaj się z tematem [Integracja danych w usłudze 365 Dynamics](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="ec9cb-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="ec9cb-105">Ten temat zawiera omówienie szablonów i podstawowych zadań, które są używane do synchronizowania jednostek Kontakt (kontaktów) i kontaktów (odbiorców) między programem Microsoft Dynamics 365 for Sales (Sales) a programem Microsoft Dynamics 365 for Finance and Operations Enterprise Edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="ec9cb-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ec9cb-106">Szablony i zadania</span><span class="sxs-lookup"><span data-stu-id="ec9cb-106">Templates and tasks</span></span>

<span data-ttu-id="ec9cb-107">Następujące szablony i podstawowe zadania są używane do synchronizowania kontaktów (kontaktów) w programie Sales z kontaktami (odbiorcami) w programie Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="ec9cb-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="ec9cb-108">**Nazwy szablonów:**</span><span class="sxs-lookup"><span data-stu-id="ec9cb-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="ec9cb-109">Kontakty z kontaktami (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ec9cb-109">Contacts to Contact (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="ec9cb-110">Kontakty z odbiorcami (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ec9cb-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="ec9cb-111">**Nazwy zadań w projekcie:**</span><span class="sxs-lookup"><span data-stu-id="ec9cb-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="ec9cb-112">Kontakty</span><span class="sxs-lookup"><span data-stu-id="ec9cb-112">Contacts</span></span>
    - <span data-ttu-id="ec9cb-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="ec9cb-113">ContactToCustomer</span></span>

<span data-ttu-id="ec9cb-114">Przed rozpoczęciem synchronizowania kontaktów należy wykonać następujące zadanie synchronizacji: Konta (z Sales do Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="ec9cb-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="ec9cb-115">Zestawy jednostek</span><span class="sxs-lookup"><span data-stu-id="ec9cb-115">Entity sets</span></span>

| <span data-ttu-id="ec9cb-116">Sprzedaż</span><span class="sxs-lookup"><span data-stu-id="ec9cb-116">Sales</span></span>    | <span data-ttu-id="ec9cb-117">CDS</span><span class="sxs-lookup"><span data-stu-id="ec9cb-117">CDS</span></span>     | <span data-ttu-id="ec9cb-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec9cb-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="ec9cb-119">Kontakty</span><span class="sxs-lookup"><span data-stu-id="ec9cb-119">Contacts</span></span> | <span data-ttu-id="ec9cb-120">Kontakt</span><span class="sxs-lookup"><span data-stu-id="ec9cb-120">Contact</span></span> | <span data-ttu-id="ec9cb-121">Kontakty w usłudze CDS</span><span class="sxs-lookup"><span data-stu-id="ec9cb-121">CDS Contacts</span></span>           |
| <span data-ttu-id="ec9cb-122">Kontakty</span><span class="sxs-lookup"><span data-stu-id="ec9cb-122">Contacts</span></span> | <span data-ttu-id="ec9cb-123">Konto</span><span class="sxs-lookup"><span data-stu-id="ec9cb-123">Account</span></span> | <span data-ttu-id="ec9cb-124">Odbiorcy V2</span><span class="sxs-lookup"><span data-stu-id="ec9cb-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="ec9cb-125">Przepływ jednostek</span><span class="sxs-lookup"><span data-stu-id="ec9cb-125">Entity flow</span></span>

<span data-ttu-id="ec9cb-126">Kontakty są zarządzane w programie Sales oraz synchronizowane z usługą Common Data Service (CDS) i programem Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="ec9cb-127">Kontakt w programie Sales może stać się kontaktem w usłudze CDS i programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="ec9cb-128">Alternatywnie może się stać kontem klienta w usłudze CDS i programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-129">Aby ustalić, czy kontakt powinien zostać pobrany w programie Sales w celu synchronizacji z usługą CDS i programem Finance and Operations (na przykład kontakty z okna Sprzedaż &gt; Kontakt do okna CDS &gt; Kontakty i do programu Finance and Operations), system analizuje następujące właściwości kontaktu w programie Sales:</span><span class="sxs-lookup"><span data-stu-id="ec9cb-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="ec9cb-130">**Synchronizacja z kontem klienta w usłudze CDS i odbiorcą w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają zaznaczoną wartość **Tak**</span><span class="sxs-lookup"><span data-stu-id="ec9cb-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="ec9cb-131">**Synchronizacji z kontaktami w usłudze CDS i kontaktami w programie Finance and Operations:** Kontakty, które w ustawieniu **Aktywny odbiorca** mają wartość **Nie**, a ustawienie **Firma** (konto nadrzędne/kontakt) wskazuje konto klienta (nie kontakt)</span><span class="sxs-lookup"><span data-stu-id="ec9cb-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ec9cb-132">Rozwiązanie Prospekt na gotówkę dla aplikacji Sales</span><span class="sxs-lookup"><span data-stu-id="ec9cb-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="ec9cb-133">Do kontaktu dodano nowe pole **Aktywny odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="ec9cb-134">To pole służy do rozróżniania między kontaktami, które mają działania sprzedaży, a kontaktami, które nie mają takich działań.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="ec9cb-135">Ustawienie **Aktywny odbiorca** ma wartość **Tak** tylko dla kontaktów, które mają powiązane oferty, zamówienia lub faktury.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="ec9cb-136">Tylko te kontakty są synchronizowane z programem Finance and Operations jako odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="ec9cb-137">Do kontaktu dodano nowe pole **IsCompanyAnAccount**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="ec9cb-138">To pole wskazuje, czy kontakt jest połączony z firmą (kontem nadrzędnym/kontaktem) o typie **Konto**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="ec9cb-139">Ta informacja jest używana do identyfikowania kontaktów, które powinny być synchronizowane z programem Finance and Operations jako kontakty.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="ec9cb-140">Do kontaktu dodano nowe pole **Numer osoby kontaktowej** w celu zagwarantowania naturalnego i unikatowego klucza integracji.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="ec9cb-141">Podczas tworzenia nowego kontaktu wartość w polu **Numer kontaktowy** jest generowany automatycznie przy użyciu ustalonej numeracji.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="ec9cb-142">Wartość składa się z przedrostka **CON**, następnie rosnącej liczby kolejnej, a na końcu sześcioznakowego przyrostka.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="ec9cb-143">Oto przykład: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="ec9cb-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="ec9cb-144">Gdy rozwiązanie integracji dla programu Sales zostanie dodane do programu Sprzedaż, skrypt uaktualniania ustawia pole **Numer kontaktowy** dla istniejących kontaktów przy użyciu omówionej wcześniej numeracji.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="ec9cb-145">Skrypt uaktualniania ustawia również w polu **Aktywny odbiorca** wartość **Tak** dla wszystkich kontaktów mających działania sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="ec9cb-146">W programie Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec9cb-146">In Finance and Operations</span></span> 

<span data-ttu-id="ec9cb-147">Kontakty są oznakowane za pomocą właściwości **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="ec9cb-148">Ta właściwość wskazuje, że dany kontakt jest obsługiwany zewnętrznie.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="ec9cb-149">W takim przypadku zewnętrznie obsługiwane kontakty są prowadzone w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ec9cb-150">Warunki wstępne i ustawienia mapowania</span><span class="sxs-lookup"><span data-stu-id="ec9cb-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="ec9cb-151">Kontakt > kontakt</span><span class="sxs-lookup"><span data-stu-id="ec9cb-151">Contact to Contact</span></span>

- <span data-ttu-id="ec9cb-152">Zaktualizuj pole **Identyfikator organizacji CDS** w mapowaniu **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="ec9cb-153">Domyślna wartość pola **Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="ec9cb-154">Domyślna wartość pola **PrimaryAccount_Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="ec9cb-155">Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-156">Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Operacje**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="ec9cb-157">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="ec9cb-158">Domyślną wartością pola **PrimaryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="ec9cb-159">Upewnij się, że w programie Finance and Operations istnieje wartość następującego pola.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-160">Jeśli informacja nie jest wymagana w programie Finance and Operations, można usunąć mapowanie z mapowania **CDS &gt; Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="ec9cb-161">**Nazwa pola w programie Finance and Operations:** Decyzja</span><span class="sxs-lookup"><span data-stu-id="ec9cb-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="ec9cb-162">**Mapowanie:** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="ec9cb-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="ec9cb-163">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="ec9cb-163">Contact to Customer</span></span>

- <span data-ttu-id="ec9cb-164">Zaktualizuj pole **Identyfikator organizacji CDS** w mapowaniu **Źródło &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="ec9cb-165">Domyślna wartość pola **Organization_OrganizationId [Identyfikator organizacji]** w szablonie to **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="ec9cb-166">Pole **Kod kraju/regionu w adresie** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-167">Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="ec9cb-168">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="ec9cb-169">Domyślną wartością pola **PrimaryAddressCountryRegionISOCode** w szablonie jest **Stany Zjednoczone**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="ec9cb-170">Pole **CustomerGroup** jest wymagane w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-171">Aby uniknąć błędów synchronizacji, można określić wartość domyślną w mapowaniu **CDS &gt; Miejsce docelowe**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="ec9cb-172">Ta wartość domyślna będzie następnie używana, jeśli to pole jest pozostawione puste w aplikacji Sales.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="ec9cb-173">Domyślną wartością pola **CustomerGroupId** w szablonie jest **10**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="ec9cb-174">Dodając następujące mapowania z okna **CDS &gt; Miejsce docelowe**, można ograniczyć liczbę ręcznych aktualizacji wykonywanych w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-175">Można używać wartości domyślnej lub mapy wartości na przykład z ustawienia **Kraj/region** lub **Miejscowość**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="ec9cb-176">**SiteId** — W programie Finance and Operations można również określić domyślny oddział.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-177">Oddział jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-178">Szablon nie ma zdefiniowanej domyślnej wartości pola **SiteID**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="ec9cb-179">**WarehouseId** — W programie Finance and Operations można również określić domyślny magazyn.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-180">Magazyn jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-181">Szablon nie ma zdefiniowanej domyślnej wartości pola **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="ec9cb-182">**LanguageId** — Język jest konieczny do generowania ofert i zamówień sprzedaży w programie Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="ec9cb-183">Domyślna wartość pola **LanguageId** w szablonie to **en-us**.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="ec9cb-184">Mapowanie szablonu w integratorze danych</span><span class="sxs-lookup"><span data-stu-id="ec9cb-184">Template mapping in data integrator</span></span>

<span data-ttu-id="ec9cb-185">Na poniższych ilustracjach pokazano przykładowe mapowanie szablonu w integratorze danych.</span><span class="sxs-lookup"><span data-stu-id="ec9cb-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="ec9cb-186">Kontakt > kontakt</span><span class="sxs-lookup"><span data-stu-id="ec9cb-186">Contact to Contact</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-template-mapping-data-integrator-1.png)

![Mapowanie szablonu dla kontaktów w integratorze danych](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="ec9cb-189">Kontakt > odbiorca</span><span class="sxs-lookup"><span data-stu-id="ec9cb-189">Contact to Customer</span></span>

![Mapowanie szablonu w integratorze danych](./media/contacts-template-mapping-data-integrator-3.png)

![Mapowanie szablonu dla kontaktów w integratorze danych](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="ec9cb-192">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="ec9cb-192">Related topics</span></span>

[<span data-ttu-id="ec9cb-193">Synchronizowanie produktów w rozwiązaniu Finance and Operations do produktów w rozwiązaniu Sales</span><span class="sxs-lookup"><span data-stu-id="ec9cb-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="ec9cb-194">Synchronizowanie kont w rozwiązaniu Sales do odbiorców w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec9cb-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="ec9cb-195">Synchronizowanie nagłówków i wierszy ofert sprzedaży w rozwiązaniu Sales do elementów w rozwiązaniu Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec9cb-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

