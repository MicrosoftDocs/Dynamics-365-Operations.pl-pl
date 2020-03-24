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
ms.openlocfilehash: 269346d38eeb3812c352d16f9d50fbcd09307c12
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124596"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="36ef8-103">Zintegrowane dane główne odbiorcy</span><span class="sxs-lookup"><span data-stu-id="36ef8-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="36ef8-104">Jest to typowe dla rekordów klientów, które mają być danymi głównymi w więcej niż jednej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="36ef8-104">It's typical for customer records to be mastered in more than one application.</span></span> <span data-ttu-id="36ef8-105">Na przykład sprzedaż może przekazywać rekordy klientów komercyjnych za pośrednictwem aplikacji Sales, a handel elektroniczny lub sprzedaż detaliczna mogą przekazywać rekordy klienta za pośrednictwem aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36ef8-105">For example, sales activity can bring in commercial customer records through a Sales application, and e-Commerce or retail sales can bring in customer records through a Finance and Operations application.</span></span> <span data-ttu-id="36ef8-106">Niezależnie od tego, skąd pochodzi rekord klienta, jest on integrowany w tle w graniach wszystkich aplikacji i niezależnie od różnic w infrastrukturze.</span><span class="sxs-lookup"><span data-stu-id="36ef8-106">Regardless of where the customer record originates, it's integrated behind the scenes across application boundaries and infrastructure differences.</span></span> <span data-ttu-id="36ef8-107">Zintegrowane tworzenie danych głównych klienta pomaga obsługiwać scenariusze wielowątkowego tworzenia danych głównych i zapewnia kompleksowy widok klienta w pakiecie aplikacji Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="36ef8-107">Integrated customer mastering helps handle multi-mastering scenarios and provides a comprehensive view of the customer to the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="36ef8-108">Przepływ danych klienta</span><span class="sxs-lookup"><span data-stu-id="36ef8-108">Customer data flow</span></span>

<span data-ttu-id="36ef8-109">*Odbiorca* jest dobrze zdefiniowaną koncepcją w aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="36ef8-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="36ef8-110">W związku z tym integracja danych odbiorcy polega tylko na ujednoliceniu koncepcji odbiorcy między dwoma aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="36ef8-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="36ef8-111">Ilustracja poniżej przedstawia przepływ danych klienta.</span><span class="sxs-lookup"><span data-stu-id="36ef8-111">The following illustration shows the customer data flow.</span></span>

![Przepływ danych klienta](media/dual-write-customer-data-flow.png)

<span data-ttu-id="36ef8-113">Klienci mogą być szeroko klasyfikowani według dwóch typów: klienci komercyjni/organizacyjni oraz konsumenci/użytkownicy końcowi.</span><span class="sxs-lookup"><span data-stu-id="36ef8-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="36ef8-114">Te dwa typy klientów są przechowywane i przetwarzane w różny sposób w Finance and Operations i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="36ef8-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="36ef8-115">W Finance and Operations zarówno klienci komercyjni/organizacyjni, jak i konsumenci/użytkownicy końcowi są ustawieni jako dane główne w jednej tabeli o nazwie **CustTable** (CustomerCustomerV3Entity) i są klasyfikowani na podstawie atrybutu **Typ**.</span><span class="sxs-lookup"><span data-stu-id="36ef8-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="36ef8-116">(Jeśli **Typ** jest ustawiony na **Organizacja**, klient jest klientem komercyjnym/organizacyjnym, a jeśli **Typ** jest ustawiony na **Osoba**, klient jest konsumentem/użytkownikiem końcowym). Informacje o podstawowej osobie kontaktowej są obsługiwana przez obiekt SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="36ef8-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="36ef8-117">W programie Common Data Service klienci komercyjnych/organizacyjnych są zapisywani jako dane główne w obiekcie Konto i są identyfikowani jako klienci, gdy atrybut **RelationshipType** jest ustawiony na **Klient**.</span><span class="sxs-lookup"><span data-stu-id="36ef8-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="36ef8-118">Zarówno konsumenci/użytkownicy końcowi, jak i osoby kontaktowe są reprezentowane przez obiekt Contact.</span><span class="sxs-lookup"><span data-stu-id="36ef8-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="36ef8-119">Aby zapewnić wyraźne oddzielenie konsumenta/użytkownika końcowego i osoby kontaktowej, obiekt **Contact** ma flagę logiczną o nazwie **Sellable**.</span><span class="sxs-lookup"><span data-stu-id="36ef8-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="36ef8-120">Gdy **Sellable** ma wartość **True**, kontakt jest konsumentem/użytkownikiem końcowym, a oferty i zamówienia mogą być tworzone dla tego kontaktu.</span><span class="sxs-lookup"><span data-stu-id="36ef8-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="36ef8-121">Gdy **Sellable** ma wartość **False**, kontakt jest tylko podstawową osobą kontaktowa klienta.</span><span class="sxs-lookup"><span data-stu-id="36ef8-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="36ef8-122">Gdy kontakt non-sellable uczestniczy w ofercie lub procesie zamówienia, flaga **Sellable** ma wartość **True**, aby oznaczyć kontakt jako sellable.</span><span class="sxs-lookup"><span data-stu-id="36ef8-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="36ef8-123">Kontakt, który stał się kontaktem sellable pozostaje kontaktem sellable.</span><span class="sxs-lookup"><span data-stu-id="36ef8-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="36ef8-124">Szablony</span><span class="sxs-lookup"><span data-stu-id="36ef8-124">Templates</span></span>

<span data-ttu-id="36ef8-125">Dane klienta obejmują wszystkie informacje o kliencie, takie jak grupa odbiorców, adresy, dane kontaktowe, profil płatności, profil faktury i stan lojalności.</span><span class="sxs-lookup"><span data-stu-id="36ef8-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="36ef8-126">Kolekcja mapy jednostki działa razem podczas interakcji z danymi klienta, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="36ef8-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="36ef8-127">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="36ef8-127">Finance and Operations apps</span></span> | <span data-ttu-id="36ef8-128">Inne aplikacje w usłudze Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="36ef8-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="36ef8-129">Opis</span><span class="sxs-lookup"><span data-stu-id="36ef8-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="36ef8-130">CDS Contacts wer. 2</span><span class="sxs-lookup"><span data-stu-id="36ef8-130">CDS Contacts V2</span></span>             | <span data-ttu-id="36ef8-131">kontakty</span><span class="sxs-lookup"><span data-stu-id="36ef8-131">contacts</span></span>                        | <span data-ttu-id="36ef8-132">Ten szablon synchronizuje wszystkie podstawowe, pomocnicze i wyższe informacje kontaktowe dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="36ef8-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="36ef8-133">Grupy odbiorców</span><span class="sxs-lookup"><span data-stu-id="36ef8-133">Customer groups</span></span>             | <span data-ttu-id="36ef8-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="36ef8-134">msdyn_customergroups</span></span>            | <span data-ttu-id="36ef8-135">Ten szablon powoduje zsynchronizowanie informacji o grupie klientów.</span><span class="sxs-lookup"><span data-stu-id="36ef8-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="36ef8-136">Metoda płatności odbiorcy</span><span class="sxs-lookup"><span data-stu-id="36ef8-136">Customer payment method</span></span>     | <span data-ttu-id="36ef8-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="36ef8-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="36ef8-138">Ten szablon powoduje zsynchronizowanie informacji o metodzie płatności klienta.</span><span class="sxs-lookup"><span data-stu-id="36ef8-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="36ef8-139">Odbiorcy (wersja 3)</span><span class="sxs-lookup"><span data-stu-id="36ef8-139">Customers V3</span></span>                | <span data-ttu-id="36ef8-140">Konta</span><span class="sxs-lookup"><span data-stu-id="36ef8-140">accounts</span></span>                        | <span data-ttu-id="36ef8-141">Ten szablon synchronizuje dane główne odbiorcy dla klientów komercyjnych i organizacji.</span><span class="sxs-lookup"><span data-stu-id="36ef8-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="36ef8-142">Odbiorcy (wersja 3)</span><span class="sxs-lookup"><span data-stu-id="36ef8-142">Customers V3</span></span>                | <span data-ttu-id="36ef8-143">kontakty</span><span class="sxs-lookup"><span data-stu-id="36ef8-143">contacts</span></span>                        | <span data-ttu-id="36ef8-144">Ten szablon umożliwia synchronizację danych głównych odbiorcy dla odbiorców i użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="36ef8-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="36ef8-145">Karta lojalnościowa</span><span class="sxs-lookup"><span data-stu-id="36ef8-145">Loyalty card</span></span>                | <span data-ttu-id="36ef8-146">msdyn_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="36ef8-146">msdyn_loyaltycards</span></span>              | <span data-ttu-id="36ef8-147">Ten szablon powoduje zsynchronizowanie informacji o karcie klienta.</span><span class="sxs-lookup"><span data-stu-id="36ef8-147">This template synchronizes customer loyalty card information.</span></span>
<span data-ttu-id="36ef8-148">Afiksy nazwy</span><span class="sxs-lookup"><span data-stu-id="36ef8-148">Name affixes</span></span>                | <span data-ttu-id="36ef8-149">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="36ef8-149">msdyn_nameaffixes</span></span>               | <span data-ttu-id="36ef8-150">Ten szablon synchronizuje dane referencyjne afiksów nazw dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="36ef8-150">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="36ef8-151">Wiersze dni zapłaty w usłudze CDS wer. 2</span><span class="sxs-lookup"><span data-stu-id="36ef8-151">Payment day lines CDS V2</span></span>    | <span data-ttu-id="36ef8-152">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="36ef8-152">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="36ef8-153">Ten szablon synchronizuje dane referencyjne wierszy dni płatności dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="36ef8-153">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="36ef8-154">Dni zapłaty w usłudze CDS</span><span class="sxs-lookup"><span data-stu-id="36ef8-154">Payment days CDS</span></span>            | <span data-ttu-id="36ef8-155">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="36ef8-155">msdyn_paymentdays</span></span>               | <span data-ttu-id="36ef8-156">Ten szablon synchronizuje dane referencyjne dni płatności dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="36ef8-156">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="36ef8-157">Wiersze harmonogramu płatności</span><span class="sxs-lookup"><span data-stu-id="36ef8-157">Payment schedule lines</span></span>      | <span data-ttu-id="36ef8-158">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="36ef8-158">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="36ef8-159">Synchronizuje dane referencyjne wierszy harmonogramu płatności, zarówno dla klientów, jak i dostawców.</span><span class="sxs-lookup"><span data-stu-id="36ef8-159">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="36ef8-160">Harmonogram płatności</span><span class="sxs-lookup"><span data-stu-id="36ef8-160">Payment schedule</span></span>            | <span data-ttu-id="36ef8-161">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="36ef8-161">msdyn_paymentschedules</span></span>          | <span data-ttu-id="36ef8-162">Ten szablon synchronizuje dane referencyjne harmonogramu dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="36ef8-162">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="36ef8-163">Warunki płatności</span><span class="sxs-lookup"><span data-stu-id="36ef8-163">Terms of payment</span></span>            | <span data-ttu-id="36ef8-164">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="36ef8-164">msdyn_paymentterms</span></span>              | <span data-ttu-id="36ef8-165">Ten szablon synchronizuje dane referencyjne warunki płatności dla odbiorców i dostawców.</span><span class="sxs-lookup"><span data-stu-id="36ef8-165">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
