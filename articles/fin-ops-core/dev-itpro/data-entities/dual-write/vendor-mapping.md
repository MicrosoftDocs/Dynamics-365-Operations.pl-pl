---
title: Zintegrowane dane główne dostawcy
description: W tym temacie opisano integrację danych dostawców między aplikacami Finance and Operations i Common Data Service.
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
ms.openlocfilehash: 2442a6869daac22a435c1a7504b93ea4b5c14747
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019954"
---
# <a name="integrated-vendor-master"></a>Zintegrowane dane główne dostawcy

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Termin *dostawca* odnosi się do organizacji dostawcy lub wyłącznego właściciela, będących częścią łańcucha dostaw i dostarczających towary dla firmy. Mimo że *dostawca* jest ustaloną koncepcją w aplikacji Finance and Operations, koncepcja dostawcy nie istnieje w innych aplikacjach Dynamics 365. Zamiast tego niektóre firmy przeciążają encję Konto do przechowywania informacji o kliencie i informacje o dostawcy. Inne firmy stosują koncepcję dostawcy niestandardowego. Integracja Common Data Service wspiera oba te schematy. W związku z tym można włączyć jeden z nich, w zależności od scenariusza biznesowego.

Integracja danych dostawcy między aplikacjami Finance and Operations i innymi aplikacjami Dynamics 365 umożliwia wielowątkowe tworzenie danych głównych. Niezależnie od tego, skąd pochodzą dane dostawcy, jest on integrowany w tle w graniach wszystkich aplikacji i niezależnie od różnic w infrastrukturze. 

### <a name="vendor-data-flow"></a>Przepływ danych dostawcy

Jeśli chcesz użyć innej aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz wyodrębnić informacje o dostawcy z informacji o kliencie, możesz skorzystać z nowego schematu dostawcy.

![Przepływ danych dostawcy](media/dual-write-vendor-data-flow.png)

Jeśli chcesz użyć innych aplikacji Dynamics 365 do tworzenia danych głównych dostawcy i chcesz dalej korzystać z encji Konto do przechowywania informacji o dostawcy, możesz skorzystać z nowego rozszerzonego schematu dostawcy. W tym projekcie rozszerzone informacje o dostawcy, takie jak grupa dostawców i profil księgowania dostawcy, są przechowywane w szczegółach dostawcy.

![Rozszerzony przepływ danych dostawcy](media/dual-write-vendor-detail.jpg)

Informacje kontaktowe dostawcy przypominają informacje kontaktowe klienta. W tle informacje osoby kontaktowej są przechowywane i pobierane z tych samych podmiotów.

## <a name="templates"></a>Szablony

Dane dostawcy obejmują wszystkie informacje o dostawcy, takie jak grupa dostawców, adresy, dane kontaktowe, profil płatności oraz profil faktury. Kolekcja mapy encji działa razem podczas interakcji z danymi dostawcy, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365         | Opis
----------------------------|---------------------------------|------------
Dostawca V2               | Konto | Firmy, które używają encji Konto do przechowywania informacji o dostawcy, mogą nadal używać go w taki sam sposób. Mogą również korzystać z funkcji jawnego dostawcy dostępnej w wyniku integracji z aplikacjami Finance and Operations.
Dostawca V2               | Msdyn\_vendors | Firmy, które korzystają z niestandardowego rozwiązania dla dostawców, mogą skorzystać z koncepcji dostawcy gotowego (out-of-box), która jest wprowadzana w Common Data Service wraz z integracją z aplikacjami Finance and Operations. 
Grupy dostawców | msdyn_vendorgroups | Ten szablon powoduje zsynchronizowanie informacji o grupie dostawców.
Metoda płatności dostawcy | msdyn_vendorpaymentmethods | Ten szablon powoduje zsynchronizowanie informacji o metodzie płatności.
CDS Contacts wer. 2             | kontakty                        | Szablon [kontakty](customer-mapping.md#cds-contacts-v2-to-contacts) synchronizuje wszystkie podstawowe, pomocnicze i wyższe informacje kontaktowe dla odbiorców i dostawców.
Wiersze harmonogramu płatności      | msdyn_paymentschedulelines      | Szablon [wierszy harmonogramu płatności](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) synchronizuje dane referencyjne dla odbiorców i dostawców.
Harmonogram płatności            | msdyn_paymentschedules          | Szablon [harmonogramu płatności](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) synchronizuje dane referencyjne harmonogramu płatności dla odbiorców i dostawców.
Wiersze dni zapłaty w usłudze CDS wer. 2    | msdyn_paymentdaylines           | Szablon [wiersze dni płatności](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) synchronizuje dane referencyjne wierszy dni płatności dla odbiorców i dostawców.
Dni zapłaty w usłudze CDS            | msdyn_paymentdays               | Szablon [dni płatności](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) synchronizuje dane referencyjne harmonogramu dni płatności dla odbiorców i dostawców.
Warunki płatności            | msdyn_paymentterms              | Szablon [warunki płatności](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) synchronizuje dane referencyjne warunki płatności dla odbiorców i dostawców.
Afiksy nazwy                | msdyn_nameaffixes               | Szablon [afiksów nazw](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) synchronizuje dane referencyjne afiksów nazw dla odbiorców i dostawców.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
