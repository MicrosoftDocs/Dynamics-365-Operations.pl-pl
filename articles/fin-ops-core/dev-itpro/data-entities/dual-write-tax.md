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
ms.openlocfilehash: b6be53e9a2065373ca37c2791568a8161823803f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772417"
---
## <a name="integrated-tax"></a><span data-ttu-id="2b764-103">Zintegrowany podatek</span><span class="sxs-lookup"><span data-stu-id="2b764-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2b764-104">Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="2b764-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="2b764-105">Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.</span><span class="sxs-lookup"><span data-stu-id="2b764-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="2b764-106">Szablony</span><span class="sxs-lookup"><span data-stu-id="2b764-106">Templates</span></span>

<span data-ttu-id="2b764-107">Dane podatku zawierają kolekcję mapy encji działa razem podczas interakcji, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="2b764-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="2b764-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2b764-108">Finance and Operations</span></span>   | <span data-ttu-id="2b764-109">Aplikacja Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="2b764-109">Customer Engagement application</span></span>
-------------------------|---------------------------------
<span data-ttu-id="2b764-110">Kody podatków</span><span class="sxs-lookup"><span data-stu-id="2b764-110">Tax codes</span></span>                  | <span data-ttu-id="2b764-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="2b764-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="2b764-112">Grupy podatków</span><span class="sxs-lookup"><span data-stu-id="2b764-112">Tax groups</span></span>               | <span data-ttu-id="2b764-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="2b764-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="2b764-114">Grupy pozycji podlegających opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="2b764-114">Tax item groups</span></span>          | <span data-ttu-id="2b764-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="2b764-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="2b764-116">Zwolnienia z podatku</span><span class="sxs-lookup"><span data-stu-id="2b764-116">Tax Exemptions</span></span>           | <span data-ttu-id="2b764-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="2b764-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="2b764-118">Urzędy skarbowe</span><span class="sxs-lookup"><span data-stu-id="2b764-118">Tax Authorities</span></span>          | <span data-ttu-id="2b764-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="2b764-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="2b764-120">Kody potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="2b764-120">Withholding tax codes</span></span>      | <span data-ttu-id="2b764-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="2b764-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="2b764-122">Grupy potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="2b764-122">Withholding tax groups</span></span>   | <span data-ttu-id="2b764-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="2b764-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="2b764-124">Grupa kont księgi podatku</span><span class="sxs-lookup"><span data-stu-id="2b764-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="2b764-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="2b764-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

