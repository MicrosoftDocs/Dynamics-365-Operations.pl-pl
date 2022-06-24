---
title: Zintegrowany podatek
description: W tym artykule opisano integrację danych podatku między aplikacjami finansowymi i operacyjnymi oraz usługą Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 8864a9567d57739aa72fa1859f5cfce6df33e8f7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864551"
---
# <a name="integrated-tax"></a>Zintegrowany podatek

[!include [banner](../../includes/banner.md)]



Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek. Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.

## <a name="templates"></a>Szablony

Dane podatku zawierają kolekcję mapowań tabel działających razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.

| Aplikacje Finanse i Działania | Aplikacje Customer Engagement | Opis |
|-----------------------------|-----------------------------------|-------------|
[Grupa podatków dla pozycji](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Urzędy skarbowe](mapping-reference.md#193) | msdyn_taxauthorities | |
[Jednostka Kod zwolnienia z podatku w usłudze CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Grupy podatków](mapping-reference.md#195) | msdyn_taxgroups | |
[Grupy V2 księgowania podatku w księdze](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Kody potrąconych zaliczek na podatek](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Grupy potrąconych zaliczek na podatek](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
