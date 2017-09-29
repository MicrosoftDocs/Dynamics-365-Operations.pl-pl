---
title: Raporty arkuszy magazynowych
description: "Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalName
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 265144
ms.search.region: Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: f4bc900e2279abcbaea84e0d4ef7bf2b01f9f039
ms.contentlocale: pl-pl
ms.lasthandoff: 06/29/2017


---

# <a name="inventory-journal-reports"></a><span data-ttu-id="bf478-103">Raporty arkuszy magazynowych</span><span class="sxs-lookup"><span data-stu-id="bf478-103">Inventory journal reports</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bf478-104">Jeśli używasz konfigurowalnych raportów o zapasach opartych na raportowaniu elektronicznym, należy zdefiniować relacje między określonymi raportami a typami arkuszy.</span><span class="sxs-lookup"><span data-stu-id="bf478-104">When you use configurable inventory reports based on electronic reporting, you need to set up a relationship between a specific report and a journal type.</span></span>

<span data-ttu-id="bf478-105">Aby skonfigurować relację między określonym raportem a typem arkusza, na stronie **Nazwy arkuszy magazynowych** (**Zarządzanie zapasami** &gt; **Ustawienia** &gt; **Nazwy arkuszy** &gt; **Zapasy**) nadaj raportowi nazwę.</span><span class="sxs-lookup"><span data-stu-id="bf478-105">To set up a relationship between a specific report and a journal type, on the **Inventory journal names** page (**Inventory management** &gt; **Setup** &gt; **Journal names** &gt; **Inventory**), enter a name for the report.</span></span> <span data-ttu-id="bf478-106">**Uwaga:** Aby utworzyć obsługiwane konfiguracje, pobierz wymagane konfiguracje raportowania elektronicznego.</span><span class="sxs-lookup"><span data-stu-id="bf478-106">**Note:** To set up supported configurations, download the required electronic reporting configurations.</span></span> <span data-ttu-id="bf478-107">Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span><span class="sxs-lookup"><span data-stu-id="bf478-107">For more information, see [Download Electronic reporting configurations from Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).</span></span> <span data-ttu-id="bf478-108">Przykłady raportów o zapasów z obsługiwanymi konfiguracjami w Europie są wymienione w tabeli poniżej.</span><span class="sxs-lookup"><span data-stu-id="bf478-108">Examples of inventory reports with supported configurations in Europe are listed in the following table.</span></span>
|                    |                                     |                  |                                         |
|--------------------|-------------------------------------|------------------|-----------------------------------------|
| <span data-ttu-id="bf478-109">**Kraj**</span><span class="sxs-lookup"><span data-stu-id="bf478-109">**Country**</span></span>        | <span data-ttu-id="bf478-110">**Opis raportu**</span><span class="sxs-lookup"><span data-stu-id="bf478-110">**Report description**</span></span>              | <span data-ttu-id="bf478-111">**Typ arkusza**</span><span class="sxs-lookup"><span data-stu-id="bf478-111">**Journal type**</span></span> | <span data-ttu-id="bf478-112">**Nazwa mapowania formatu**</span><span class="sxs-lookup"><span data-stu-id="bf478-112">**Format mapping name**</span></span>                 |
| <span data-ttu-id="bf478-113">Litwa, Węgry</span><span class="sxs-lookup"><span data-stu-id="bf478-113">Lithuania, Hungary</span></span> | <span data-ttu-id="bf478-114">Raport zestawienia zapasów</span><span class="sxs-lookup"><span data-stu-id="bf478-114">Inventory statement report</span></span>          | <span data-ttu-id="bf478-115">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="bf478-115">Counting</span></span>         | <span data-ttu-id="bf478-116">Zestawienie zapasów (Węgry, Litwa)</span><span class="sxs-lookup"><span data-stu-id="bf478-116">Inventory statement (HU, LT)</span></span>            |
| <span data-ttu-id="bf478-117">Łotwa, Polska</span><span class="sxs-lookup"><span data-stu-id="bf478-117">Latvia, Poland</span></span>     | <span data-ttu-id="bf478-118">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="bf478-118">Inventory reclassification document</span></span> | <span data-ttu-id="bf478-119">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="bf478-119">Transfer</span></span>         | <span data-ttu-id="bf478-120">InventoryReclassificationDocument\_PLLV</span><span class="sxs-lookup"><span data-stu-id="bf478-120">InventoryReclassificationDocument\_PLLV</span></span> |
| <span data-ttu-id="bf478-121">Estonia</span><span class="sxs-lookup"><span data-stu-id="bf478-121">Estonia</span></span>            | <span data-ttu-id="bf478-122">Dokument przeklasyfikowania zapasów</span><span class="sxs-lookup"><span data-stu-id="bf478-122">Inventory reclassification document</span></span> | <span data-ttu-id="bf478-123">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="bf478-123">Transfer</span></span>         | <span data-ttu-id="bf478-124">InventoryReclassificationDocument\_EE</span><span class="sxs-lookup"><span data-stu-id="bf478-124">InventoryReclassificationDocument\_EE</span></span>   |
| <span data-ttu-id="bf478-125">Polska</span><span class="sxs-lookup"><span data-stu-id="bf478-125">Poland</span></span>             | <span data-ttu-id="bf478-126">Wewnętrzne PW/RW</span><span class="sxs-lookup"><span data-stu-id="bf478-126">Internal PW/RW</span></span>                      | <span data-ttu-id="bf478-127">Transakcje</span><span class="sxs-lookup"><span data-stu-id="bf478-127">Movement</span></span>         | <span data-ttu-id="bf478-128">InventJournalLinesDocPL</span><span class="sxs-lookup"><span data-stu-id="bf478-128">InventJournalLinesDocPL</span></span>                 |
| <span data-ttu-id="bf478-129">Łotwa</span><span class="sxs-lookup"><span data-stu-id="bf478-129">Latvia</span></span>             | <span data-ttu-id="bf478-130"> Dokument przesunięcia magazynowego</span><span class="sxs-lookup"><span data-stu-id="bf478-130">Inventory movement document</span></span>         | <span data-ttu-id="bf478-131">Transakcje</span><span class="sxs-lookup"><span data-stu-id="bf478-131">Movement</span></span>         | <span data-ttu-id="bf478-132">Movement\_LV</span><span class="sxs-lookup"><span data-stu-id="bf478-132">Movement\_LV</span></span>                            |
| <span data-ttu-id="bf478-133">Łotwa</span><span class="sxs-lookup"><span data-stu-id="bf478-133">Latvia</span></span>             | <span data-ttu-id="bf478-134">Dokument zmniejszenia wartości zapasów</span><span class="sxs-lookup"><span data-stu-id="bf478-134">Inventory write-down document</span></span>       | <span data-ttu-id="bf478-135">Korekta</span><span class="sxs-lookup"><span data-stu-id="bf478-135">Adjustment</span></span>       | <span data-ttu-id="bf478-136">InventJournalLines\_LV</span><span class="sxs-lookup"><span data-stu-id="bf478-136">InventJournalLines\_LV</span></span>                  |
| <span data-ttu-id="bf478-137">Łotwa</span><span class="sxs-lookup"><span data-stu-id="bf478-137">Latvia</span></span>             | <span data-ttu-id="bf478-138">Przenieś dokument dostawy</span><span class="sxs-lookup"><span data-stu-id="bf478-138">Transfer delivery note</span></span>              | <span data-ttu-id="bf478-139">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="bf478-139">Transfer</span></span>         | <span data-ttu-id="bf478-140">InternalTransferDeliveryNote\_LV</span><span class="sxs-lookup"><span data-stu-id="bf478-140">InternalTransferDeliveryNote\_LV</span></span>        |
| <span data-ttu-id="bf478-141">Łotwa</span><span class="sxs-lookup"><span data-stu-id="bf478-141">Latvia</span></span>             | <span data-ttu-id="bf478-142">Raport dokumentu inwentaryzacji</span><span class="sxs-lookup"><span data-stu-id="bf478-142">Counting document report</span></span>            | <span data-ttu-id="bf478-143">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="bf478-143">Counting</span></span>         | <span data-ttu-id="bf478-144">CountedDocument\_LV</span><span class="sxs-lookup"><span data-stu-id="bf478-144">CountedDocument\_LV</span></span>                     |
| <span data-ttu-id="bf478-145">Łotwa</span><span class="sxs-lookup"><span data-stu-id="bf478-145">Latvia</span></span>             | <span data-ttu-id="bf478-146">Raport arkusza inwentaryzacyjnego</span><span class="sxs-lookup"><span data-stu-id="bf478-146">Counting list report</span></span>                | <span data-ttu-id="bf478-147">Zliczanie</span><span class="sxs-lookup"><span data-stu-id="bf478-147">Counting</span></span>         | <span data-ttu-id="bf478-148">Arkusz inwentaryzacyjny</span><span class="sxs-lookup"><span data-stu-id="bf478-148">Counting list</span></span>                           |






