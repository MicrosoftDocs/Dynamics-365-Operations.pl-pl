---
title: Zintegrowane dane główne odbiorcy
description: W tym temacie opisano integrację danych odbiorcy między Finance and Operations i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 977b74b10b4549d09a8816264f9ff603fa86e91c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172838"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="a90a0-103">Zintegrowane dane główne odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a90a0-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="a90a0-104">Dane klientów mogą być przekazywane w więcej niż jednej aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a90a0-104">Customer data can be mastered in more than one Dynamics 365 application.</span></span> <span data-ttu-id="a90a0-105">Na przykład rekord odbiorcy może pochodzić z operacji sprzedaży w Dynamics 365 Sales (aplikacji opartej na modelu w usłudze Dynamics 365) lub rekord ten może pochodzić z działania handlu detalicznego w Dynamics 365 Commerce ( aplikacji Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="a90a0-105">For example, a customer record can originate though sales activity in Dynamics 365 Sales (a model-driven app in Dynamics 365), or a record can originate through retail activity in Dynamics 365 Commerce (a Finance and Operations app).</span></span> <span data-ttu-id="a90a0-106">Niezależnie od tego, gdzie znajdują się dane dotyczące klientów, są one integrowane w tle.</span><span class="sxs-lookup"><span data-stu-id="a90a0-106">No matter where where the customer data originates, it is integrated behind the scenes.</span></span> <span data-ttu-id="a90a0-107">Zintegrowany dane główne odbiorcy zapewniają elastyczność danych dotyczących klientów w dowolnej aplikacji Dynamics 365 i udostępniają obszerny widok klienta w ramach pakietu aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a90a0-107">Integrated customer master gives you the flexibility to master customer data in any Dynamics 365 application and provides a comprehensive view of the customer across the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="a90a0-108">Przepływ danych klienta</span><span class="sxs-lookup"><span data-stu-id="a90a0-108">Customer data flow</span></span>

<span data-ttu-id="a90a0-109">*Odbiorca* jest dobrze zdefiniowaną koncepcją w aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="a90a0-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="a90a0-110">W związku z tym integracja danych odbiorcy polega tylko na ujednoliceniu koncepcji odbiorcy między dwoma aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="a90a0-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="a90a0-111">Ilustracja poniżej przedstawia przepływ danych klienta.</span><span class="sxs-lookup"><span data-stu-id="a90a0-111">The following illustration shows the customer data flow.</span></span>

![Przepływ danych klienta](media/dual-write-customer-data-flow.png)

<span data-ttu-id="a90a0-113">Klienci mogą być szeroko klasyfikowani według dwóch typów: klienci komercyjni/organizacyjni oraz konsumenci/użytkownicy końcowi.</span><span class="sxs-lookup"><span data-stu-id="a90a0-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="a90a0-114">Te dwa typy klientów są przechowywane i przetwarzane w różny sposób w Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a90a0-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="a90a0-115">W Finance and Operations zarówno klienci komercyjni/organizacyjni, jak i konsumenci/użytkownicy końcowi są ustawieni jako dane główne w jednej tabeli o nazwie **CustTable** (CustomerCustomerV3Entity) i są klasyfikowani na podstawie atrybutu **Typ**.</span><span class="sxs-lookup"><span data-stu-id="a90a0-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="a90a0-116">(Jeśli **Typ** jest ustawiony na **Organizacja**, klient jest klientem komercyjnym/organizacyjnym, a jeśli **Typ** jest ustawiony na **Osoba**, klient jest konsumentem/użytkownikiem końcowym). Informacje o podstawowej osobie kontaktowej są obsługiwana przez obiekt SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="a90a0-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="a90a0-117">W programie Common Data Service klienci komercyjnych/organizacyjnych są zapisywani jako dane główne w obiekcie Konto i są identyfikowani jako klienci, gdy atrybut **RelationshipType** jest ustawiony na **Klient**.</span><span class="sxs-lookup"><span data-stu-id="a90a0-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="a90a0-118">Zarówno konsumenci/użytkownicy końcowi, jak i osoby kontaktowe są reprezentowane przez obiekt Contact.</span><span class="sxs-lookup"><span data-stu-id="a90a0-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="a90a0-119">Aby zapewnić wyraźne oddzielenie konsumenta/użytkownika końcowego i osoby kontaktowej, obiekt **Contact** ma flagę logiczną o nazwie **Sellable**.</span><span class="sxs-lookup"><span data-stu-id="a90a0-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="a90a0-120">Gdy **Sellable** ma wartość **True**, kontakt jest konsumentem/użytkownikiem końcowym, a oferty i zamówienia mogą być tworzone dla tego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="a90a0-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="a90a0-121">Gdy **Sellable** ma wartość **False**, kontakt jest tylko podstawową osobą kontaktowa klienta.</span><span class="sxs-lookup"><span data-stu-id="a90a0-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="a90a0-122">Gdy kontakt non-sellable uczestniczy w ofercie lub procesie zamówienia, flaga **Sellable** ma wartość **True**, aby oznaczyć kontakt jako sellable.</span><span class="sxs-lookup"><span data-stu-id="a90a0-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="a90a0-123">Kontakt, który stał się kontaktem sellable pozostaje kontaktem sellable.</span><span class="sxs-lookup"><span data-stu-id="a90a0-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="a90a0-124">Szablony</span><span class="sxs-lookup"><span data-stu-id="a90a0-124">Templates</span></span>

<span data-ttu-id="a90a0-125">Dane klienta obejmują wszystkie informacje o kliencie, takie jak grupa odbiorców, adresy, dane kontaktowe, profil płatności, profil faktury i stan lojalności.</span><span class="sxs-lookup"><span data-stu-id="a90a0-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="a90a0-126">Kolekcja mapy jednostki działa razem podczas interakcji z danymi klienta, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="a90a0-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="a90a0-127">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a90a0-127">Finance and Operations apps</span></span> | <span data-ttu-id="a90a0-128">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a90a0-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="a90a0-129">Opis</span><span class="sxs-lookup"><span data-stu-id="a90a0-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="a90a0-130">CDS Contacts wer. 2</span><span class="sxs-lookup"><span data-stu-id="a90a0-130">CDS Contacts V2</span></span>             | <span data-ttu-id="a90a0-131">kontakty</span><span class="sxs-lookup"><span data-stu-id="a90a0-131">contacts</span></span>                        | <span data-ttu-id="a90a0-132">Ten szablon synchronizuje wszystkie podstawowe, pomocnicze i wyższe informacje kontaktowe dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="a90a0-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="a90a0-133">Grupy odbiorców</span><span class="sxs-lookup"><span data-stu-id="a90a0-133">Customer groups</span></span>             | <span data-ttu-id="a90a0-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="a90a0-134">msdyn_customergroups</span></span>            | <span data-ttu-id="a90a0-135">Ten szablon powoduje zsynchronizowanie informacji o grupie klientów.</span><span class="sxs-lookup"><span data-stu-id="a90a0-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="a90a0-136">Metoda płatności odbiorcy</span><span class="sxs-lookup"><span data-stu-id="a90a0-136">Customer payment method</span></span>     | <span data-ttu-id="a90a0-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="a90a0-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="a90a0-138">Ten szablon powoduje zsynchronizowanie informacji o metodzie płatności klienta.</span><span class="sxs-lookup"><span data-stu-id="a90a0-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="a90a0-139">Odbiorcy (wersja 3)</span><span class="sxs-lookup"><span data-stu-id="a90a0-139">Customers V3</span></span>                | <span data-ttu-id="a90a0-140">Konta</span><span class="sxs-lookup"><span data-stu-id="a90a0-140">accounts</span></span>                        | <span data-ttu-id="a90a0-141">Ten szablon synchronizuje dane główne odbiorcy dla klientów komercyjnych i organizacji.</span><span class="sxs-lookup"><span data-stu-id="a90a0-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="a90a0-142">Odbiorcy (wersja 3)</span><span class="sxs-lookup"><span data-stu-id="a90a0-142">Customers V3</span></span>                | <span data-ttu-id="a90a0-143">kontakty</span><span class="sxs-lookup"><span data-stu-id="a90a0-143">contacts</span></span>                        | <span data-ttu-id="a90a0-144">Ten szablon umożliwia synchronizację danych głównych odbiorcy dla odbiorców i użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="a90a0-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="a90a0-145">Afiksy nazwy</span><span class="sxs-lookup"><span data-stu-id="a90a0-145">Name affixes</span></span>                | <span data-ttu-id="a90a0-146">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="a90a0-146">msdyn_nameaffixes</span></span>               | <span data-ttu-id="a90a0-147">Ten szablon synchronizuje dane referencyjne afiksów nazw dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="a90a0-147">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a90a0-148">Wiersze dni zapłaty w usłudze CDS wer. 2</span><span class="sxs-lookup"><span data-stu-id="a90a0-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="a90a0-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="a90a0-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="a90a0-150">Ten szablon synchronizuje dane referencyjne wierszy dni płatności dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="a90a0-150">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a90a0-151">Dni zapłaty w usłudze CDS</span><span class="sxs-lookup"><span data-stu-id="a90a0-151">Payment days CDS</span></span>            | <span data-ttu-id="a90a0-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="a90a0-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="a90a0-153">Ten szablon synchronizuje dane referencyjne dni płatności dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="a90a0-153">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a90a0-154">Wiersze harmonogramu płatności</span><span class="sxs-lookup"><span data-stu-id="a90a0-154">Payment schedule lines</span></span>      | <span data-ttu-id="a90a0-155">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="a90a0-155">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="a90a0-156">Synchronizuje dane referencyjne wierszy harmonogramu płatności, zarówno dla klientów, jak i dostawców.</span><span class="sxs-lookup"><span data-stu-id="a90a0-156">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a90a0-157">Harmonogram płatności</span><span class="sxs-lookup"><span data-stu-id="a90a0-157">Payment schedule</span></span>            | <span data-ttu-id="a90a0-158">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="a90a0-158">msdyn_paymentschedules</span></span>          | <span data-ttu-id="a90a0-159">Ten szablon synchronizuje dane referencyjne harmonogramu dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="a90a0-159">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="a90a0-160">Warunki płatności</span><span class="sxs-lookup"><span data-stu-id="a90a0-160">Terms of payment</span></span>            | <span data-ttu-id="a90a0-161">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="a90a0-161">msdyn_paymentterms</span></span>              | <span data-ttu-id="a90a0-162">Ten szablon synchronizuje dane referencyjne warunki płatności dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="a90a0-162">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
