---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatków między Finance and Operations i Common Data Service.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 26818ceace7d2b7e7c3ed4d0bb0bd9ab2e884aba
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997607"
---
# <a name="integrated-tax"></a>Zintegrowany podatek

[!include [banner](../../includes/banner.md)]



Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek. Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.

## <a name="templates"></a>Szablony

Dane podatku zawierają kolekcję mapy encji działa razem podczas interakcji, jak pokazano w poniższej tabeli.

Aplikacje Finance and Operations | Aplikacje oparte na modelu w systemie Dynamics 365 | opis |
-------------------------|---------------------------------|----|
Grupa podatków dla pozycji | msdyn_taxitemgroups |
Urzędy skarbowe | msdyn_taxauthorities |
Jednostka Kod zwolnienia z podatku w usłudze CDS | msdyn_taxexemptcodes |
Grupy podatków | msdyn_taxgroups |
Grupy V2 księgowania podatku w księdze | msdyn_taxpostinggroups |
Kody potrąconych zaliczek na podatek | msdyn_withholdingtaxcodes |
Grupy potrąconych zaliczek na podatek | msdyn_withholdingtaxgroups | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

