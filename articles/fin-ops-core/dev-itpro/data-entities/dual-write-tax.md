---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatku między programami Finance and Operations i Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
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
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 86e74086a5a74c7af5f2572d1a653a1658d729c0
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853866"
---
# <a name="integrated-tax"></a>Zintegrowany podatek

[!include [banner](../includes/banner.md)]

Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek. Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.

## <a name="templates"></a>Szablony

Dane podatku zawierają kolekcję mapy encji działa razem podczas interakcji, jak pokazano w poniższej tabeli.

Finance and Operations   | Inne aplikacje w usłudze Dynamics 365
-------------------------|---------------------------------
Kody podatków                  | msdyn\_taxcodes.md
Grupy podatków               | msdyn\_taxgroups.md
Grupy pozycji podlegających opodatkowaniu          | msdyn\_taxitemgroups.md
Zwolnienia z podatku           | msdyn\_taxexemptcodes.md
Urzędy skarbowe          | msdyn\_taxauthorities.md
Kody potrąconych zaliczek na podatek      | msdyn\_withholdingtaxcodes.md
Grupy potrąconych zaliczek na podatek   | msdyn\_withholdingtaxgroups.md
Grupa kont księgi podatku | msdyn\_taxpostinggroups  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

