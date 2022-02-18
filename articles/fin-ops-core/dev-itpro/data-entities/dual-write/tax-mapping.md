---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatku między programami Finanse i Działania i Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 532e6603b74ad0293d65684d2d6858ef31fbc496
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063194"
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
