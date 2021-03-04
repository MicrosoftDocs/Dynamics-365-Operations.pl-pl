---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatków między Finance and Operations i Dataverse.
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
ms.openlocfilehash: 14c22dd6602b5fbf866c8dc6b057f6c8acb1f48f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679303"
---
# <a name="integrated-tax"></a>Zintegrowany podatek

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek. Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.

## <a name="templates"></a>Szablony

Dane podatku zawierają kolekcję mapowań tabel działających razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]