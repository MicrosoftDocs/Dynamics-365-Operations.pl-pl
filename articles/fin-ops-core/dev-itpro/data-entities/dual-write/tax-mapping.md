---
title: Zintegrowany podatek
description: W tym temacie opisano integrację danych podatków między Finance and Operations i Dataverse.
author: robinarh
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
ms.openlocfilehash: a7992520b57b4c19b6dc8e13bd8e9ffc87b40f5a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750649"
---
# <a name="integrated-tax"></a><span data-ttu-id="12281-103">Zintegrowany podatek</span><span class="sxs-lookup"><span data-stu-id="12281-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="12281-104">Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="12281-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="12281-105">Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.</span><span class="sxs-lookup"><span data-stu-id="12281-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="12281-106">Szablony</span><span class="sxs-lookup"><span data-stu-id="12281-106">Templates</span></span>

<span data-ttu-id="12281-107">Dane podatku zawierają kolekcję mapowań tabel działających razem podczas interakcji z danymi, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="12281-107">Tax data includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="12281-108">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="12281-108">Finance and Operations apps</span></span> | <span data-ttu-id="12281-109">Aplikacje oparte na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="12281-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="12281-110">opis</span><span class="sxs-lookup"><span data-stu-id="12281-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="12281-111">Grupa podatków dla pozycji</span><span class="sxs-lookup"><span data-stu-id="12281-111">Item sales tax group</span></span> | <span data-ttu-id="12281-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="12281-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="12281-113">Urzędy skarbowe</span><span class="sxs-lookup"><span data-stu-id="12281-113">Sales tax authorities</span></span> | <span data-ttu-id="12281-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="12281-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="12281-115">Jednostka Kod zwolnienia z podatku w usłudze CDS</span><span class="sxs-lookup"><span data-stu-id="12281-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="12281-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="12281-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="12281-117">Grupy podatków</span><span class="sxs-lookup"><span data-stu-id="12281-117">Sales tax groups</span></span> | <span data-ttu-id="12281-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="12281-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="12281-119">Grupy V2 księgowania podatku w księdze</span><span class="sxs-lookup"><span data-stu-id="12281-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="12281-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="12281-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="12281-121">Kody potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="12281-121">Withholding tax codes</span></span> | <span data-ttu-id="12281-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="12281-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="12281-123">Grupy potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="12281-123">Withholding tax groups</span></span> | <span data-ttu-id="12281-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="12281-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]