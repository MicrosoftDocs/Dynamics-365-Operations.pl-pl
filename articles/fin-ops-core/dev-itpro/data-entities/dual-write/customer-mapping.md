---
title: Zintegrowane dane główne odbiorcy
description: W tym temacie opisano integrację danych odbiorcy między Finance and Operations i Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b7e9cd27bb918dc3a6088b45803329deb01a864e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744409"
---
# <a name="integrated-customer-master"></a>Zintegrowane dane główne odbiorcy

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


Dane klientów mogą być przekazywane w więcej niż jednej aplikacji Dynamics 365. Na przykład wiersz odbiorcy może pochodzić z operacji sprzedaży w Dynamics 365 Sales (aplikacji opartej na modelu w usłudze Dynamics 365) lub wiersz ten może pochodzić z działania handlu detalicznego w Dynamics 365 Commerce (aplikacji Finance and Operations). Niezależnie od tego, gdzie znajdują się dane dotyczące klientów, są one integrowane w tle. Zintegrowany dane główne odbiorcy zapewniają elastyczność danych dotyczących klientów w dowolnej aplikacji Dynamics 365 i udostępniają obszerny widok klienta w ramach pakietu aplikacji Dynamics 365.

## <a name="customer-data-flow"></a>Przepływ danych klienta

*Odbiorca* jest dobrze zdefiniowaną koncepcją w aplikacjach. W związku z tym integracja danych odbiorcy polega tylko na ujednoliceniu koncepcji odbiorcy między dwoma aplikacjami. Ilustracja poniżej przedstawia przepływ danych klienta.

![Przepływ danych klienta](media/dual-write-customer-data-flow.png)

Klienci mogą być szeroko klasyfikowani według dwóch typów: klienci komercyjni/organizacyjni oraz konsumenci/użytkownicy końcowi. Te dwa typy klientów są przechowywane i przetwarzane w różny sposób w Finance and Operations i Dataverse.

W Finance and Operations zarówno klienci komercyjni/organizacyjni, jak i konsumenci/użytkownicy końcowi są ustawieni jako dane główne w jednej tabeli o nazwie **CustTable** (CustCustomerV3Entity) i są klasyfikowani na podstawie atrybutu **Typ**. (Jeśli **Typ** jest ustawiony na **Organizacja**, klient jest klientem komercyjnym/organizacyjnym, a jeśli **Typ** jest ustawiony na **Osoba**, klient jest konsumentem/użytkownikiem końcowym). Informacje o podstawowej osobie kontaktowej są obsługiwane przez tabelę SMMContactPersonEntity.

W programie Dataverse klienci komercyjnych/organizacyjnych są zapisywani jako dane główne w tabeli Konto i są identyfikowani jako klienci, gdy atrybut **RelationshipType** jest ustawiony na **Klient**. Zarówno konsumenci/użytkownicy końcowi, jak i osoby kontaktowe są reprezentowane przez tabelę Kontakt. Aby zapewnić wyraźne oddzielenie konsumenta/użytkownika końcowego i osoby kontaktowej, tabela **kontaktów** ma flagę logiczną o nazwie **Sellable**. Gdy **Sellable** ma wartość **True**, kontakt jest konsumentem/użytkownikiem końcowym, a oferty i zamówienia mogą być tworzone dla tego kontaktu. Gdy **Sellable** ma wartość **False**, kontakt jest tylko podstawową osobą kontaktowa klienta.

Gdy kontakt non-sellable uczestniczy w ofercie lub procesie zamówienia, flaga **Sellable** ma wartość **True**, aby oznaczyć kontakt jako sellable. Kontakt, który stał się kontaktem sellable pozostaje kontaktem sellable.

## <a name="templates"></a>Szablony

Dane klienta obejmują wszystkie informacje o kliencie, takie jak grupa odbiorców, adresy, dane kontaktowe, profil płatności, profil faktury i stan lojalności. Kolekcja mapy tabeli działa razem podczas interakcji z danymi klienta, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365         | Opis
----------------------------|---------------------------------|------------
CDS Contacts wer. 2             | kontakty                        | Ten szablon synchronizuje wszystkie podstawowe, pomocnicze i wyższe informacje kontaktowe dla odbiorców i dostawców.
Grupy odbiorców             | msdyn_customergroups            | Ten szablon powoduje zsynchronizowanie informacji o grupie klientów.
Metoda płatności odbiorcy     | msdyn_customerpaymentmethods    | Ten szablon powoduje zsynchronizowanie informacji o metodzie płatności klienta.
Odbiorcy (wersja 3)                | Konta                        | Ten szablon synchronizuje dane główne odbiorcy dla klientów komercyjnych i organizacji.
Odbiorcy (wersja 3)                | kontakty                        | Ten szablon umożliwia synchronizację danych głównych odbiorcy dla odbiorców i użytkowników końcowych.
Afiksy nazwy                | msdyn_nameaffixes               | Ten szablon synchronizuje dane referencyjne afiksów nazw dla odbiorców i dostawców.
Wiersze dni zapłaty w usłudze CDS wer. 2    | msdyn_paymentdaylines           | Ten szablon synchronizuje dane referencyjne wierszy dni płatności dla odbiorców i dostawców.
Dni zapłaty w usłudze CDS            | msdyn_paymentdays               | Ten szablon synchronizuje dane referencyjne dni płatności dla odbiorców i dostawców.
Wiersze harmonogramu płatności      | msdyn_paymentschedulelines      | Synchronizuje dane referencyjne wierszy harmonogramu płatności, zarówno dla klientów, jak i dostawców.
Harmonogram płatności            | msdyn_paymentschedules          | Ten szablon synchronizuje dane referencyjne harmonogramu dla odbiorców i dostawców.
Warunki płatności            | msdyn_paymentterms              | Ten szablon synchronizuje dane referencyjne warunki płatności dla odbiorców i dostawców.

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
