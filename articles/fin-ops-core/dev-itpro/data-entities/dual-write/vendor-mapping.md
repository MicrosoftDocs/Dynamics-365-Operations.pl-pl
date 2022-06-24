---
title: Zintegrowane dane główne dostawcy
description: W tym artykule opisano integrację danych dostawcy między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 394bb19000076eace6377e07bb3a939c8345da8a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905323"
---
# <a name="integrated-vendor-master"></a>Zintegrowane dane główne dostawcy

[!include [banner](../../includes/banner.md)]



Termin *dostawca* odnosi się do organizacji dostawcy lub jedynego właściciela, który dostarcza towary lub usługi firmie. Mimo że *dostawca* jest ustaloną koncepcją w Microsoft  Dynamics 365 Supply Chain Management, koncepcja dostawcy nie istnieje w aplikacjach angażujących klientów nie ma koncepcji dostawcy. Można jednak przeciążyć tabelę **Konta/kontaktu**, aby przechowywać informacje o dostawcach. Zintegrowany wzorzec dostawcy wprowadza wyraźną koncepcję dostawcy w aplikacjach angażujących klienta. Można skorzystać z nowego projektu dostawcy lub danych dostawcy sklepu w tabeli **Konto/kontakt**. Podwójne zapisywanie obsługuje obie metody.

W obu przypadkach dane dostawcy są zintegrowane między Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service i portalami Power Apps. W Supply Chain Management dane są dostępne dla przepływów pracy, takich jak zapotrzebowania zakupu i zamówienia zakupu.

## <a name="vendor-data-flow"></a>Przepływ danych dostawcy

Jeśli nie chcesz przechowywać danych dostawcy w tabeli **Konto/kontakt** w Dataverse, możesz użyć nowego projektu dostawcy.

![Przepływ danych dostawcy.](media/dual-write-vendor-data-flow.png)

Jeśli chcesz dalej przechowywać dane dostawcy w tabeli **Konto/kontakt**, możesz użyć rozszerzonego projektu dostawcy. Aby skorzystać z rozszerzonego projektu dostawcy, należy skonfigurować przepływy pracy dostawcy w pakiecie rozwiązania podwójnego zapisywania. Aby uzyskać więcej informacji, zajrzyj do [Przełączanie się między projektami dostawcy](vendor-switch.md).

![Rozszerzony przepływ danych dostawcy.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Jeśli korzystasz z portali Power Apps dla dostawców samoobsługowych, informacje o dostawcy mogą przepływać bezpośrednio do aplikacji Finanse i Działania.

## <a name="templates"></a>Szablony

Dane dostawcy obejmują wszystkie informacje o dostawcy, takie jak grupa dostawców, adresy, dane kontaktowe, profil płatności oraz profil faktury. Kolekcja mapowań tabel działa razem podczas interakcji z danymi dostawcy, jak pokazano w poniższej tabeli.

Aplikacje Finanse i Działania | Aplikacje Customer Engagement     | opis
----------------------------|-----------------------------|------------
[CDS Contacts wer. 2](mapping-reference.md#115) | kontakty | Ten szablon synchronizuje wszystkie podstawowe, pomocnicze i wyższe informacje kontaktowe dla odbiorców i dostawców.
[Afiksy nazwy](mapping-reference.md#155) | msdyn_nameaffixes | Ten szablon synchronizuje dane referencyjne afiksów nazw dla odbiorców i dostawców.
[Wiersze dni zapłaty w usłudze CDS wer. 2](mapping-reference.md#157) | msdyn_paymentdaylines | Ten szablon synchronizuje dane referencyjne wierszy dni płatności dla odbiorców i dostawców.
[Dni zapłaty w usłudze CDS](mapping-reference.md#158) | msdyn_paymentdays | Ten szablon synchronizuje dane referencyjne dni płatności dla odbiorców i dostawców.
[Wiersze harmonogramu płatności](mapping-reference.md#159) | msdyn_paymentschedulelines | Synchronizuje dane referencyjne wierszy harmonogramu płatności, zarówno dla klientów, jak i dostawców.
[Harmonogram płatności](mapping-reference.md#160) | msdyn_paymentschedules | Ten szablon synchronizuje dane referencyjne harmonogramu dla odbiorców i dostawców.
[Warunki płatności](mapping-reference.md#161) | msdyn_paymentterms | Ten szablon synchronizuje dane referencyjne warunki płatności dla odbiorców i dostawców.
[Dostawcy wersja 2](mapping-reference.md#202) | msdyn_vendors | Firmy, które korzystają z niestandardowego rozwiązania dla dostawców, mogą skorzystać z koncepcji dostawcy gotowego (out-of-box), która jest wprowadzana w Dataverse wraz z integracją z aplikacjami Finanse i Działania.
[Grupy dostawców](mapping-reference.md#200) | msdyn_vendorgroups | Ten szablon powoduje zsynchronizowanie informacji o grupie dostawców.
[Metoda płatności dostawcy](mapping-reference.md#201) | msdyn_vendorpaymentmethods | Ten szablon powoduje zsynchronizowanie informacji o metodzie płatności.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
