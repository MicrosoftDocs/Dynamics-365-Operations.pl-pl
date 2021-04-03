---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatków między Finance and Operations i Dataverse.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 7501ef21492a96c81b971e1d9077beaba9be897b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560344"
---
# <a name="integrated-tax"></a><span data-ttu-id="70a5e-103">Zintegrowany podatek</span><span class="sxs-lookup"><span data-stu-id="70a5e-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="70a5e-104">Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="70a5e-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="70a5e-105">Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.</span><span class="sxs-lookup"><span data-stu-id="70a5e-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="70a5e-106">Szablony</span><span class="sxs-lookup"><span data-stu-id="70a5e-106">Templates</span></span>

<span data-ttu-id="70a5e-107">Dane podatku zawierają kolekcję mapowań tabel działających razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="70a5e-107">Tax data includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="70a5e-108">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="70a5e-108">Finance and Operations apps</span></span> | <span data-ttu-id="70a5e-109">Aplikacje oparte na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="70a5e-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="70a5e-110">opis</span><span class="sxs-lookup"><span data-stu-id="70a5e-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="70a5e-111">Grupa podatków dla pozycji</span><span class="sxs-lookup"><span data-stu-id="70a5e-111">Item sales tax group</span></span> | <span data-ttu-id="70a5e-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="70a5e-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="70a5e-113">Urzędy skarbowe</span><span class="sxs-lookup"><span data-stu-id="70a5e-113">Sales tax authorities</span></span> | <span data-ttu-id="70a5e-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="70a5e-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="70a5e-115">Jednostka Kod zwolnienia z podatku w usłudze CDS</span><span class="sxs-lookup"><span data-stu-id="70a5e-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="70a5e-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="70a5e-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="70a5e-117">Grupy podatków</span><span class="sxs-lookup"><span data-stu-id="70a5e-117">Sales tax groups</span></span> | <span data-ttu-id="70a5e-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="70a5e-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="70a5e-119">Grupy V2 księgowania podatku w księdze</span><span class="sxs-lookup"><span data-stu-id="70a5e-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="70a5e-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="70a5e-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="70a5e-121">Kody potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="70a5e-121">Withholding tax codes</span></span> | <span data-ttu-id="70a5e-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="70a5e-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="70a5e-123">Grupy potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="70a5e-123">Withholding tax groups</span></span> | <span data-ttu-id="70a5e-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="70a5e-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]