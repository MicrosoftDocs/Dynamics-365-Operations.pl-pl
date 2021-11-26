---
title: Zintegrowane dane główne odbiorcy
description: W tym temacie opisano integrację danych odbiorcy między Finance and Operations i Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 48070628aafd7daac65327a484c87dc01ffb3954
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781697"
---
# <a name="integrated-customer-master"></a>Zintegrowane dane główne odbiorcy

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dane klientów mogą być przekazywane w więcej niż jednej aplikacji Dynamics 365. Na przykład wiersz odbiorcy może pochodzić z operacji sprzedaży w Dynamics 365 Sales (aplikacji angażującej klienta) lub wiersz ten może pochodzić z działania handlu detalicznego w Dynamics 365 Commerce (aplikacji Finance and Operations). Niezależnie od tego, gdzie znajdują się dane dotyczące klientów, są one integrowane w tle. Zintegrowany dane główne odbiorcy zapewniają elastyczność danych dotyczących klientów w dowolnej aplikacji Dynamics 365 i udostępniają obszerny widok klienta w ramach pakietu aplikacji Dynamics 365.

## <a name="customer-data-flow"></a>Przepływ danych klienta

*Odbiorca* jest dobrze zdefiniowaną koncepcją w aplikacjach. W związku z tym integracja danych odbiorcy polega tylko na ujednoliceniu koncepcji odbiorcy między dwoma aplikacjami. Ilustracja poniżej przedstawia przepływ danych klienta.

![Przepływ danych klienta.](media/dual-write-customer-data-flow.png)

Klienci mogą być szeroko klasyfikowani według dwóch typów: klienci komercyjni/organizacyjni oraz konsumenci/użytkownicy końcowi. Te dwa typy klientów są przechowywane i przetwarzane w różny sposób w Finance and Operations i Dataverse.

W Finance and Operations zarówno klienci komercyjni/organizacyjni, jak i konsumenci/użytkownicy końcowi są ustawieni jako dane główne w jednej tabeli o nazwie **CustTable** (CustCustomerV3Entity) i są klasyfikowani na podstawie atrybutu **Typ**. (Jeśli **Typ** jest ustawiony na **Organizacja**, klient jest klientem komercyjnym/organizacyjnym, a jeśli **Typ** jest ustawiony na **Osoba**, klient jest konsumentem/użytkownikiem końcowym). Informacje o podstawowej osobie kontaktowej są obsługiwane przez tabelę SMMContactPersonEntity.

W programie Dataverse klienci komercyjnych/organizacyjnych są zapisywani jako dane główne w tabeli Konto i są identyfikowani jako klienci, gdy atrybut **RelationshipType** jest ustawiony na **Klient**. Zarówno konsumenci/użytkownicy końcowi, jak i osoby kontaktowe są reprezentowane przez tabelę Kontakt. Aby zapewnić wyraźne oddzielenie konsumenta/użytkownika końcowego i osoby kontaktowej, tabela **kontaktów** ma flagę logiczną o nazwie **Sellable**. Gdy **Sellable** ma wartość **True**, kontakt jest konsumentem/użytkownikiem końcowym, a oferty i zamówienia mogą być tworzone dla tego kontaktu. Gdy **Sellable** ma wartość **False**, kontakt jest tylko podstawową osobą kontaktowa klienta.

Gdy kontakt non-sellable uczestniczy w ofercie lub procesie zamówienia, flaga **Sellable** ma wartość **True**, aby oznaczyć kontakt jako sellable. Kontakt, który stał się kontaktem sellable pozostaje kontaktem sellable.

## <a name="templates"></a>Szablony

Dane klienta obejmują wszystkie informacje o kliencie, takie jak grupa odbiorców, adresy, dane kontaktowe, profil płatności, profil faktury i stan lojalności. Kolekcja mapy tabeli działa razem podczas interakcji z danymi klienta, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations | Aplikacje Customer Engagement         | opis
----------------------------|---------------------------------|------------
[CDS Contacts wer. 2](mapping-reference.md#115) | kontakty | Ten szablon synchronizuje wszystkie podstawowe, pomocnicze i wyższe informacje kontaktowe dla odbiorców i dostawców.
[Grupy odbiorców](mapping-reference.md#126) | msdyn_customergroups | Ten szablon powoduje zsynchronizowanie informacji o grupie klientów.
[Metoda płatności odbiorcy](mapping-reference.md#127) | msdyn_customerpaymentmethods | Ten szablon powoduje zsynchronizowanie informacji o metodzie płatności klienta.
[Odbiorcy (wersja 3)](mapping-reference.md#101) | Konta | Ten szablon synchronizuje dane główne odbiorcy dla klientów komercyjnych i organizacji.
[Odbiorcy (wersja 3)](mapping-reference.md#116) | kontakty | Ten szablon umożliwia synchronizację danych głównych odbiorcy dla odbiorców i użytkowników końcowych.
[Afiksy nazwy](mapping-reference.md#155) | msdyn_nameaffixes | Ten szablon synchronizuje dane referencyjne afiksów nazw dla odbiorców i dostawców.
[Wiersze dni zapłaty w usłudze CDS wer. 2](mapping-reference.md#157) | msdyn_paymentdaylines | Ten szablon synchronizuje dane referencyjne wierszy dni płatności dla odbiorców i dostawców.
[Dni zapłaty w usłudze CDS](mapping-reference.md#158) | msdyn_paymentdays | Ten szablon synchronizuje dane referencyjne dni płatności dla odbiorców i dostawców.
[Wiersze harmonogramu płatności](mapping-reference.md#159) | msdyn_paymentschedulelines | Synchronizuje dane referencyjne wierszy harmonogramu płatności, zarówno dla klientów, jak i dostawców.
[Harmonogram płatności](mapping-reference.md#160) | msdyn_paymentschedules | Ten szablon synchronizuje dane referencyjne harmonogramu dla odbiorców i dostawców.
[Warunki płatności](mapping-reference.md#161) | msdyn_paymentterms | Ten szablon synchronizuje dane referencyjne warunki płatności dla odbiorców i dostawców.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
