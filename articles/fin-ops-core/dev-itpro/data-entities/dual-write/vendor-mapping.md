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
ms.openlocfilehash: 8d531ed4e46d8ee5d2b0937b6efc480e051fe708
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173115"
---
# <a name="integrated-vendor-master"></a>Zintegrowane dane główne dostawcy

[!include [banner](../../includes/banner.md)]



Termin *dostawca* odnosi się do organizacji dostawcy lub jedynego właściciela, który dostarcza towary lub usługi firmie. Mimo że *dostawca* jest ustaloną koncepcją w Microsoft  Dynamics 365 Supply Chain Management, koncepcja dostawcy nie istnieje w aplikacjach opartych na modelach w Dynamics 365. Można jednak przeciążyć jednostkę **Konta/kontaktu**, aby przechowywać informacje o dostawcach. Zintegrowany wzorzec dostawcy wprowadza jawną koncepcję dostawcy w aplikacjach opartych na modelach w Dynamics 365. Można skorzystać z nowego projektu dostawcy lub danych dostawcy sklepu w jednostce **Konto/kontakt**. Podwójne zapisywanie obsługuje obie metody.

W obu przypadkach dane dostawcy są zintegrowane między Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service i portalami Power Apps. W Supply Chain Management dane są dostępne dla przepływów pracy, takich jak zapotrzebowania zakupu i zamówienia zakupu.

## <a name="vendor-data-flow"></a>Przepływ danych dostawcy

Jeśli nie chcesz przechowywać danych dostawcy w jednostce **Konto/kontakt** w Common Data Service, możesz użyć nowego projektu dostawcy.

![Przepływ danych dostawcy](media/dual-write-vendor-data-flow.png)

Jeśli chcesz dalej przechowywać dane dostawcy w jednostce **Konto/kontakt**, możesz użyć rozszerzonego projektu dostawcy. Aby skorzystać z rozszerzonego projektu dostawcy, należy skonfigurować przepływy pracy dostawcy w pakiecie rozwiązania podwójnego zapisywania. Aby uzyskać więcej informacji, zajrzyj do [Przełączanie się między projektami dostawcy](vendor-switch.md).

![Rozszerzony przepływ danych dostawcy](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Jeśli korzystasz z portali Power Apps dla dostawców samoobsługowych, informacje o dostawcy mogą przepływać bezpośrednio do aplikacji Finance and Operations.

## <a name="templates"></a>Szablony

Dane dostawcy obejmują wszystkie informacje o dostawcy, takie jak grupa dostawców, adresy, dane kontaktowe, profil płatności oraz profil faktury. Kolekcja mapy encji działa razem podczas interakcji z danymi dostawcy, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations | Inne aplikacje w usłudze Dynamics 365     | Opis
----------------------------|-----------------------------|------------
Dostawca V2                   | Konto                     | Firmy, które używają encji Konto do przechowywania informacji o dostawcy, mogą nadal używać go w taki sam sposób. Mogą również korzystać z funkcji jawnego dostawcy dostępnej w wyniku integracji z aplikacjami Finance and Operations.
Dostawca V2                   | Msdyn\_vendors              | Firmy, które korzystają z niestandardowego rozwiązania dla dostawców, mogą skorzystać z koncepcji dostawcy gotowego (out-of-box), która jest wprowadzana w Common Data Service wraz z integracją z aplikacjami Finance and Operations. 
Grupy dostawców               | msdyn\_vendorgroups         | Ten szablon powoduje zsynchronizowanie informacji o grupie dostawców.
Metoda płatności dostawcy       | msdyn\_vendorpaymentmethods | Ten szablon powoduje zsynchronizowanie informacji o metodzie płatności.
CDS Contacts wer. 2             | kontakty                    | Szablon [kontakty](customer-mapping.md#cds-contacts-v2-to-contacts) synchronizuje wszystkie podstawowe, pomocnicze i wyższe informacje kontaktowe dla odbiorców i dostawców.
Wiersze harmonogramu płatności      | msdyn\_paymentschedulelines | Szablon [wierszy harmonogramu płatności](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) synchronizuje dane referencyjne dla odbiorców i dostawców.
Harmonogram płatności            | msdyn\_paymentschedules     | Szablon [harmonogramu płatności](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) synchronizuje dane referencyjne harmonogramu płatności dla odbiorców i dostawców.
Wiersze dni zapłaty w usłudze CDS wer. 2    | msdyn\_paymentdaylines      | Szablon [wiersze dni płatności](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) synchronizuje dane referencyjne wierszy dni płatności dla odbiorców i dostawców.
Dni zapłaty w usłudze CDS            | msdyn\_paymentdays          | Szablon [dni płatności](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) synchronizuje dane referencyjne harmonogramu dni płatności dla odbiorców i dostawców.
Warunki płatności            | msdyn\_paymentterms         | Szablon [warunki płatności](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) synchronizuje dane referencyjne warunki płatności dla odbiorców i dostawców.
Afiksy nazwy                | msdyn\_nameaffixes          | Szablon [afiksów nazw](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) synchronizuje dane referencyjne afiksów nazw dla odbiorców i dostawców.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
