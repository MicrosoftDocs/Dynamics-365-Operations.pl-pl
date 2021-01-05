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
ms.openlocfilehash: f8b52043f9c09dfe7e80f9fec7b495acd3ccb590
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4408400"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="5421a-103">Raporty arkuszy magazynowych</span><span class="sxs-lookup"><span data-stu-id="5421a-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5421a-104">Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy.</span><span class="sxs-lookup"><span data-stu-id="5421a-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="5421a-105">Aby skonfigurować relację między określonym raportem a typem arkusza, na stronie **Nazwy arkuszy magazynowych** (**Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Nazwy arkuszy** &gt; **Zapasy**) nadaj raportowi nazwę.</span><span class="sxs-lookup"><span data-stu-id="5421a-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="5421a-106">**Uwaga:** Aby utworzyć obsługiwane konfiguracje, pobierz wymagane konfiguracje raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="5421a-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="5421a-107">Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="5421a-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="5421a-108">Przykłady raportów o zapasów z obsługiwanymi konfiguracjami w Europie są wymienione w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="5421a-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

| <span data-ttu-id="5421a-109">Kraj</span><span class="sxs-lookup"><span data-stu-id="5421a-109">Country</span></span>            |    <span data-ttu-id="5421a-110">Opis raportu</span><span class="sxs-lookup"><span data-stu-id="5421a-110">Report description</span></span>               | <span data-ttu-id="5421a-111">Typ arkusza</span><span class="sxs-lookup"><span data-stu-id="5421a-111">Journal type</span></span>     |    <span data-ttu-id="5421a-112">Nazwa mapowania formatu</span><span class="sxs-lookup"><span data-stu-id="5421a-112">Format mapping name</span></span>                  |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="5421a-113">Litwa, Węgry</span><span class="sxs-lookup"><span data-stu-id="5421a-113">Lithuania, Hungary</span></span> | <span data-ttu-id="5421a-114">Raport zestawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="5421a-114">Inventory statement report</span></span>          | <span data-ttu-id="5421a-115">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="5421a-115">Counting</span></span>         | <span data-ttu-id="5421a-116">Zestawienie zapasów (Węgry, Litwa)</span><span class="sxs-lookup"><span data-stu-id="5421a-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="5421a-117">Łotwa, Polska</span><span class="sxs-lookup"><span data-stu-id="5421a-117">Latvia, Poland</span></span>     | <span data-ttu-id="5421a-118">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="5421a-118">Inventory reclassification document</span></span> | <span data-ttu-id="5421a-119">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="5421a-119">Transfer</span></span>         | <span data-ttu-id="5421a-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="5421a-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="5421a-121">Estonia</span><span class="sxs-lookup"><span data-stu-id="5421a-121">Estonia</span></span>            | <span data-ttu-id="5421a-122">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="5421a-122">Inventory reclassification document</span></span> | <span data-ttu-id="5421a-123">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="5421a-123">Transfer</span></span>         | <span data-ttu-id="5421a-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="5421a-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="5421a-125">Polska</span><span class="sxs-lookup"><span data-stu-id="5421a-125">Poland</span></span>             | <span data-ttu-id="5421a-126">Wewnętrzne PW/RW</span><span class="sxs-lookup"><span data-stu-id="5421a-126">Internal PW/RW</span></span>                      | <span data-ttu-id="5421a-127">Transakcje</span><span class="sxs-lookup"><span data-stu-id="5421a-127">Movement</span></span>         | <span data-ttu-id="5421a-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="5421a-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="5421a-129">Łotwa</span><span class="sxs-lookup"><span data-stu-id="5421a-129">Latvia</span></span>             | <span data-ttu-id="5421a-130"> Dokument przesunięcia magazynowego</span><span class="sxs-lookup"><span data-stu-id="5421a-130">Inventory movement document</span></span>         | <span data-ttu-id="5421a-131">Transakcje</span><span class="sxs-lookup"><span data-stu-id="5421a-131">Movement</span></span>         | <span data-ttu-id="5421a-132">Movement\_LV</span><span class="sxs-lookup"><span data-stu-id="5421a-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="5421a-133">Łotwa</span><span class="sxs-lookup"><span data-stu-id="5421a-133">Latvia</span></span>             | <span data-ttu-id="5421a-134">Dokument zmniejszenia wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="5421a-134">Inventory write-down document</span></span>       | <span data-ttu-id="5421a-135">Korekta</span><span class="sxs-lookup"><span data-stu-id="5421a-135">Adjustment</span></span>       | <span data-ttu-id="5421a-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="5421a-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="5421a-137">Łotwa</span><span class="sxs-lookup"><span data-stu-id="5421a-137">Latvia</span></span>             | <span data-ttu-id="5421a-138">Przenieś dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="5421a-138">Transfer delivery note</span></span>              | <span data-ttu-id="5421a-139">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="5421a-139">Transfer</span></span>         | <span data-ttu-id="5421a-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="5421a-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="5421a-141">Łotwa</span><span class="sxs-lookup"><span data-stu-id="5421a-141">Latvia</span></span>             | <span data-ttu-id="5421a-142">Raport dokumentu inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="5421a-142">Counting document report</span></span>            | <span data-ttu-id="5421a-143">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="5421a-143">Counting</span></span>         | <span data-ttu-id="5421a-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="5421a-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="5421a-145">Łotwa</span><span class="sxs-lookup"><span data-stu-id="5421a-145">Latvia</span></span>             | <span data-ttu-id="5421a-146">Raport arkusza inwentaryzacyjnego</span><span class="sxs-lookup"><span data-stu-id="5421a-146">Counting list report</span></span>                | <span data-ttu-id="5421a-147">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="5421a-147">Counting</span></span>         | <span data-ttu-id="5421a-148">Arkusz inwentaryzacyjny</span><span class="sxs-lookup"><span data-stu-id="5421a-148">Counting list</span></span>                           |





