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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173092"
---
# <a name="integrated-tax"></a><span data-ttu-id="91253-103">Zintegrowany podatek</span><span class="sxs-lookup"><span data-stu-id="91253-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="91253-104">Dane ustawień podatku określają ustawienia zarówno podatków pośrednich (VAT, GST, podatków), jak i potrąconej zaliczki na podatek.</span><span class="sxs-lookup"><span data-stu-id="91253-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="91253-105">Zawiera opis reguły obliczania podatku, stawki podatkowej, księgowania podatku, rozliczania i innych koncepcji.</span><span class="sxs-lookup"><span data-stu-id="91253-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="91253-106">Szablony</span><span class="sxs-lookup"><span data-stu-id="91253-106">Templates</span></span>

<span data-ttu-id="91253-107">Dane podatku zawierają kolekcję mapy encji działa razem podczas interakcji, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="91253-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="91253-108">Aplikacje Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="91253-108">Finance and Operations apps</span></span> | <span data-ttu-id="91253-109">Aplikacje oparte na modelu w systemie Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="91253-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="91253-110">opis</span><span class="sxs-lookup"><span data-stu-id="91253-110">Description</span></span> |
-------------------------|---------------------------------
<span data-ttu-id="91253-111">Kody podatków</span><span class="sxs-lookup"><span data-stu-id="91253-111">Tax codes</span></span>                   | <span data-ttu-id="91253-112">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="91253-112">msdyn\_taxcodes.md</span></span> | 
<span data-ttu-id="91253-113">Grupy podatków</span><span class="sxs-lookup"><span data-stu-id="91253-113">Tax groups</span></span>                 | <span data-ttu-id="91253-114">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="91253-114">msdyn\_taxgroups.md</span></span> | 
<span data-ttu-id="91253-115">Grupy pozycji podlegających opodatkowaniu</span><span class="sxs-lookup"><span data-stu-id="91253-115">Tax item groups</span></span>             | <span data-ttu-id="91253-116">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="91253-116">msdyn\_taxitemgroups.md</span></span> | 
<span data-ttu-id="91253-117">Zwolnienia z podatku</span><span class="sxs-lookup"><span data-stu-id="91253-117">Tax Exemptions</span></span>             | <span data-ttu-id="91253-118">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="91253-118">msdyn\_taxexemptcodes.md</span></span> | 
<span data-ttu-id="91253-119">Urzędy skarbowe</span><span class="sxs-lookup"><span data-stu-id="91253-119">Tax Authorities</span></span>             | <span data-ttu-id="91253-120">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="91253-120">msdyn\_taxauthorities.md</span></span> | 
<span data-ttu-id="91253-121">Kody potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="91253-121">Withholding tax codes</span></span>       | <span data-ttu-id="91253-122">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="91253-122">msdyn\_withholdingtaxcodes.md</span></span> | 
<span data-ttu-id="91253-123">Grupy potrąconych zaliczek na podatek</span><span class="sxs-lookup"><span data-stu-id="91253-123">Withholding tax groups</span></span>     | <span data-ttu-id="91253-124">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="91253-124">msdyn\_withholdingtaxgroups.md</span></span> | 
<span data-ttu-id="91253-125">Grupa kont księgi podatku</span><span class="sxs-lookup"><span data-stu-id="91253-125">Tax Ledger Account Group</span></span> | <span data-ttu-id="91253-126">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="91253-126">msdyn\_taxpostinggroups</span></span>     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

