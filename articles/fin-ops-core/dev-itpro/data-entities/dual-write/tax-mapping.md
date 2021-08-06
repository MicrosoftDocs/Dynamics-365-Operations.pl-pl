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
ms.openlocfilehash: e1b5d62e56dd1f87dbfedc6a8ca7379587481ff4
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542326"
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
