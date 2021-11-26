---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatków między Finance and Operations i Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d1e74bbbeba019ca48dd823b58251643e96edd0c
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782217"
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
