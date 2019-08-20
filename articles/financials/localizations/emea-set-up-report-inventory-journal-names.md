---
title: Raporty arkuszy magazynowych
description: Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d051c8ab7f15f69dd06db0986c3151b61d595b6d
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852414"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="710d4-103">Raporty arkuszy magazynowych</span><span class="sxs-lookup"><span data-stu-id="710d4-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="710d4-104">Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy.</span><span class="sxs-lookup"><span data-stu-id="710d4-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="710d4-105">Aby skonfigurować relację między określonym raportem a typem arkusza, na stronie **Nazwy arkuszy magazynowych** (**Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Nazwy arkuszy** &gt; **Zapasy**) nadaj raportowi nazwę.</span><span class="sxs-lookup"><span data-stu-id="710d4-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="710d4-106">**Uwaga:** Aby utworzyć obsługiwane konfiguracje, pobierz wymagane konfiguracje raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="710d4-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="710d4-107">Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="710d4-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="710d4-108">Przykłady raportów o zapasów z obsługiwanymi konfiguracjami w Europie są wymienione w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="710d4-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="710d4-109">**Kraj**</span><span class="sxs-lookup"><span data-stu-id="710d4-109">**Country**</span></span>        | <span data-ttu-id="710d4-110">**Opis raportu**</span><span class="sxs-lookup"><span data-stu-id="710d4-110">**Report description**</span></span>              | <span data-ttu-id="710d4-111">**Typ arkusza**</span><span class="sxs-lookup"><span data-stu-id="710d4-111">**Journal type**</span></span> | <span data-ttu-id="710d4-112">**Nazwa mapowania formatu**</span><span class="sxs-lookup"><span data-stu-id="710d4-112">**Format mapping name**</span></span>                 |
| <span data-ttu-id="710d4-113">Litwa, Węgry</span><span class="sxs-lookup"><span data-stu-id="710d4-113">Lithuania, Hungary</span></span> | <span data-ttu-id="710d4-114">Raport zestawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="710d4-114">Inventory statement report</span></span>          | <span data-ttu-id="710d4-115">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="710d4-115">Counting</span></span>         | <span data-ttu-id="710d4-116">Zestawienie zapasów (Węgry, Litwa)</span><span class="sxs-lookup"><span data-stu-id="710d4-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="710d4-117">Łotwa, Polska</span><span class="sxs-lookup"><span data-stu-id="710d4-117">Latvia, Poland</span></span>     | <span data-ttu-id="710d4-118">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="710d4-118">Inventory reclassification document</span></span> | <span data-ttu-id="710d4-119">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="710d4-119">Transfer</span></span>         | <span data-ttu-id="710d4-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="710d4-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="710d4-121">Estonia</span><span class="sxs-lookup"><span data-stu-id="710d4-121">Estonia</span></span>            | <span data-ttu-id="710d4-122">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="710d4-122">Inventory reclassification document</span></span> | <span data-ttu-id="710d4-123">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="710d4-123">Transfer</span></span>         | <span data-ttu-id="710d4-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="710d4-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="710d4-125">Polska</span><span class="sxs-lookup"><span data-stu-id="710d4-125">Poland</span></span>             | <span data-ttu-id="710d4-126">Wewnętrzne PW/RW</span><span class="sxs-lookup"><span data-stu-id="710d4-126">Internal PW/RW</span></span>                      | <span data-ttu-id="710d4-127">Transakcje</span><span class="sxs-lookup"><span data-stu-id="710d4-127">Movement</span></span>         | <span data-ttu-id="710d4-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="710d4-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="710d4-129">Łotwa</span><span class="sxs-lookup"><span data-stu-id="710d4-129">Latvia</span></span>             | <span data-ttu-id="710d4-130"> Dokument przesunięcia magazynowego</span><span class="sxs-lookup"><span data-stu-id="710d4-130">Inventory movement document</span></span>         | <span data-ttu-id="710d4-131">Transakcje</span><span class="sxs-lookup"><span data-stu-id="710d4-131">Movement</span></span>         | <span data-ttu-id="710d4-132">Movement\_LV</span><span class="sxs-lookup"><span data-stu-id="710d4-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="710d4-133">Łotwa</span><span class="sxs-lookup"><span data-stu-id="710d4-133">Latvia</span></span>             | <span data-ttu-id="710d4-134">Dokument zmniejszenia wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="710d4-134">Inventory write-down document</span></span>       | <span data-ttu-id="710d4-135">Korekta</span><span class="sxs-lookup"><span data-stu-id="710d4-135">Adjustment</span></span>       | <span data-ttu-id="710d4-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="710d4-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="710d4-137">Łotwa</span><span class="sxs-lookup"><span data-stu-id="710d4-137">Latvia</span></span>             | <span data-ttu-id="710d4-138">Przenieś dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="710d4-138">Transfer delivery note</span></span>              | <span data-ttu-id="710d4-139">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="710d4-139">Transfer</span></span>         | <span data-ttu-id="710d4-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="710d4-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="710d4-141">Łotwa</span><span class="sxs-lookup"><span data-stu-id="710d4-141">Latvia</span></span>             | <span data-ttu-id="710d4-142">Raport dokumentu inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="710d4-142">Counting document report</span></span>            | <span data-ttu-id="710d4-143">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="710d4-143">Counting</span></span>         | <span data-ttu-id="710d4-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="710d4-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="710d4-145">Łotwa</span><span class="sxs-lookup"><span data-stu-id="710d4-145">Latvia</span></span>             | <span data-ttu-id="710d4-146">Raport arkusza inwentaryzacyjnego</span><span class="sxs-lookup"><span data-stu-id="710d4-146">Counting list report</span></span>                | <span data-ttu-id="710d4-147">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="710d4-147">Counting</span></span>         | <span data-ttu-id="710d4-148">Arkusz inwentaryzacyjny</span><span class="sxs-lookup"><span data-stu-id="710d4-148">Counting list</span></span>                           |





