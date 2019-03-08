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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b7077522e02f6b91d335c70adc26e23524d65aae
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371445"
---
# <a name="inventory-journal-reports"></a><span data-ttu-id="f5769-103">Raporty arkuszy magazynowych</span><span class="sxs-lookup"><span data-stu-id="f5769-103">Inventory journal reports</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5769-104">Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy.</span><span class="sxs-lookup"><span data-stu-id="f5769-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="f5769-105">Aby skonfigurować relację między określonym raportem a typem arkusza, na stronie **Nazwy arkuszy magazynowych** (**Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Nazwy arkuszy** &gt; **Zapasy**) nadaj raportowi nazwę.</span><span class="sxs-lookup"><span data-stu-id="f5769-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="f5769-106">**Uwaga:** Aby utworzyć obsługiwane konfiguracje, pobierz wymagane konfiguracje raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="f5769-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="f5769-107">Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="f5769-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="f5769-108">Przykłady raportów o zapasów z obsługiwanymi konfiguracjami w Europie są wymienione w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="f5769-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>

|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="f5769-109">**Kraj**</span><span class="sxs-lookup"><span data-stu-id="f5769-109">**Country**</span></span>        | <span data-ttu-id="f5769-110">**Opis raportu**</span><span class="sxs-lookup"><span data-stu-id="f5769-110">**Report description**</span></span>              | <span data-ttu-id="f5769-111">**Typ arkusza**</span><span class="sxs-lookup"><span data-stu-id="f5769-111">**Journal type**</span></span> | <span data-ttu-id="f5769-112">**Nazwa mapowania formatu**</span><span class="sxs-lookup"><span data-stu-id="f5769-112">**Format mapping name**</span></span>                 |
| <span data-ttu-id="f5769-113">Litwa, Węgry</span><span class="sxs-lookup"><span data-stu-id="f5769-113">Lithuania, Hungary</span></span> | <span data-ttu-id="f5769-114">Raport zestawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="f5769-114">Inventory statement report</span></span>          | <span data-ttu-id="f5769-115">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="f5769-115">Counting</span></span>         | <span data-ttu-id="f5769-116">Zestawienie zapasów (Węgry, Litwa)</span><span class="sxs-lookup"><span data-stu-id="f5769-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="f5769-117">Łotwa, Polska</span><span class="sxs-lookup"><span data-stu-id="f5769-117">Latvia, Poland</span></span>     | <span data-ttu-id="f5769-118">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="f5769-118">Inventory reclassification document</span></span> | <span data-ttu-id="f5769-119">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="f5769-119">Transfer</span></span>         | <span data-ttu-id="f5769-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="f5769-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="f5769-121">Estonia</span><span class="sxs-lookup"><span data-stu-id="f5769-121">Estonia</span></span>            | <span data-ttu-id="f5769-122">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="f5769-122">Inventory reclassification document</span></span> | <span data-ttu-id="f5769-123">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="f5769-123">Transfer</span></span>         | <span data-ttu-id="f5769-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="f5769-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="f5769-125">Polska</span><span class="sxs-lookup"><span data-stu-id="f5769-125">Poland</span></span>             | <span data-ttu-id="f5769-126">Wewnętrzne PW/RW</span><span class="sxs-lookup"><span data-stu-id="f5769-126">Internal PW/RW</span></span>                      | <span data-ttu-id="f5769-127">Transakcje</span><span class="sxs-lookup"><span data-stu-id="f5769-127">Movement</span></span>         | <span data-ttu-id="f5769-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="f5769-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="f5769-129">Łotwa</span><span class="sxs-lookup"><span data-stu-id="f5769-129">Latvia</span></span>             | <span data-ttu-id="f5769-130"> Dokument przesunięcia magazynowego</span><span class="sxs-lookup"><span data-stu-id="f5769-130">Inventory movement document</span></span>         | <span data-ttu-id="f5769-131">Transakcje</span><span class="sxs-lookup"><span data-stu-id="f5769-131">Movement</span></span>         | <span data-ttu-id="f5769-132">Movement\_LV</span><span class="sxs-lookup"><span data-stu-id="f5769-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="f5769-133">Łotwa</span><span class="sxs-lookup"><span data-stu-id="f5769-133">Latvia</span></span>             | <span data-ttu-id="f5769-134">Dokument zmniejszenia wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="f5769-134">Inventory write-down document</span></span>       | <span data-ttu-id="f5769-135">Korekta</span><span class="sxs-lookup"><span data-stu-id="f5769-135">Adjustment</span></span>       | <span data-ttu-id="f5769-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="f5769-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="f5769-137">Łotwa</span><span class="sxs-lookup"><span data-stu-id="f5769-137">Latvia</span></span>             | <span data-ttu-id="f5769-138">Przenieś dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="f5769-138">Transfer delivery note</span></span>              | <span data-ttu-id="f5769-139">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="f5769-139">Transfer</span></span>         | <span data-ttu-id="f5769-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="f5769-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="f5769-141">Łotwa</span><span class="sxs-lookup"><span data-stu-id="f5769-141">Latvia</span></span>             | <span data-ttu-id="f5769-142">Raport dokumentu inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="f5769-142">Counting document report</span></span>            | <span data-ttu-id="f5769-143">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="f5769-143">Counting</span></span>         | <span data-ttu-id="f5769-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="f5769-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="f5769-145">Łotwa</span><span class="sxs-lookup"><span data-stu-id="f5769-145">Latvia</span></span>             | <span data-ttu-id="f5769-146">Raport arkusza inwentaryzacyjnego</span><span class="sxs-lookup"><span data-stu-id="f5769-146">Counting list report</span></span>                | <span data-ttu-id="f5769-147">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="f5769-147">Counting</span></span>         | <span data-ttu-id="f5769-148">Arkusz inwentaryzacyjny</span><span class="sxs-lookup"><span data-stu-id="f5769-148">Counting list</span></span>                           |





