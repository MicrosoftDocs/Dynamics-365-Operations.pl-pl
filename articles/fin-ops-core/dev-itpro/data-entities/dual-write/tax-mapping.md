---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatków między Finance and Operations i Dataverse.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: rhaertle
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: c7e76294944196670ed4b02ebf785c1bed7b5106f73d4b66a15a19c9a4235cbf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738559"
---
# <a name="integrated-tax"></a>Zintegrowany podatek

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek. Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.

## <a name="templates"></a>Szablony

Dane podatku zawierają kolekcję mapowań tabel działających razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.

| Aplikacje Finance and Operations | Aplikacje Customer Engagement | opis |
|-----------------------------|-----------------------------------|-------------|
[Grupa podatków dla pozycji](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Urzędy skarbowe](mapping-reference.md#193) | msdyn_taxauthorities | |
[Jednostka Kod zwolnienia z podatku w usłudze CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Grupy podatków](mapping-reference.md#195) | msdyn_taxgroups | |
[Grupy V2 księgowania podatku w księdze](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Kody potrąconych zaliczek na podatek](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Grupy potrąconych zaliczek na podatek](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
