---
title: Poziom obliczania kosztu
description: W tym temacie opisano poziom BOM o nazwie poziom obliczania kosztu. Ten poziom BOM wyklucza produkcję i zamówienia partii z obliczeń.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 52b77e794ee38add556ac01d62c973b38c48a548
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435134"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="fd6a6-104">Poziom obliczania kosztu</span><span class="sxs-lookup"><span data-stu-id="fd6a6-104">Cost calculation level</span></span>

<span data-ttu-id="fd6a6-105">Poziom BOM o nazwie **Poziom obliczania kosztu** wyklucza zlecenia produkcyjne i zamówienia partii z jego obliczeń.</span><span class="sxs-lookup"><span data-stu-id="fd6a6-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="fd6a6-106">Ten poziom jest używany w systemie podczas uruchamiania obliczeń kosztów w wersjach ceny.</span><span class="sxs-lookup"><span data-stu-id="fd6a6-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="fd6a6-107">W procesach takich jak ponowne obliczanie i zamykanie zapasów system używa zamiast tego **Poziom wyceny** poziom BOM.</span><span class="sxs-lookup"><span data-stu-id="fd6a6-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="fd6a6-108">Poniższy prosty scenariusz pokazuje różnice między poziomem BOM **Poziom obliczania kosztu** a poziomem BOM **Poziom wyceny**.</span><span class="sxs-lookup"><span data-stu-id="fd6a6-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="fd6a6-109">Istnieją trzy produkty: A, B i C. Produkt C jest składnikiem produktu B, a produkt B jest składnikiem produktu A.</span><span class="sxs-lookup"><span data-stu-id="fd6a6-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="fd6a6-110">**Poziom wyceny** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="fd6a6-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="fd6a6-111">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="fd6a6-111">**Product A:** 0</span></span>
    - <span data-ttu-id="fd6a6-112">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="fd6a6-112">**Product B:** 1</span></span>
    - <span data-ttu-id="fd6a6-113">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="fd6a6-113">**Product C:** 2</span></span>

- <span data-ttu-id="fd6a6-114">**Poziom obliczania kosztu** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="fd6a6-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="fd6a6-115">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="fd6a6-115">**Product A:** 0</span></span>
    - <span data-ttu-id="fd6a6-116">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="fd6a6-116">**Product B:** 1</span></span>
    - <span data-ttu-id="fd6a6-117">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="fd6a6-117">**Product C:** 2</span></span>

<span data-ttu-id="fd6a6-118">Tworzone jest zlecenie produkcyjne dla produktu C, a produkt A jest dodawany do BOM zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="fd6a6-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="fd6a6-119">Po oszacowaniu zamówienia poziomy BOM są aktualizowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="fd6a6-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="fd6a6-120">**Poziom wyceny** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="fd6a6-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="fd6a6-121">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="fd6a6-121">**Product B:** 1</span></span>
    - <span data-ttu-id="fd6a6-122">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="fd6a6-122">**Product C:** 2</span></span>
    - <span data-ttu-id="fd6a6-123">**Produkt A:** 3</span><span class="sxs-lookup"><span data-stu-id="fd6a6-123">**Product A:** 3</span></span>

- <span data-ttu-id="fd6a6-124">**Poziom obliczania kosztu** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="fd6a6-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="fd6a6-125">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="fd6a6-125">**Product A:** 0</span></span>
    - <span data-ttu-id="fd6a6-126">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="fd6a6-126">**Product B:** 1</span></span>
    - <span data-ttu-id="fd6a6-127">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="fd6a6-127">**Product C:** 2</span></span>

<span data-ttu-id="fd6a6-128">To zachowanie gwarantuje, że zmiany BOM zlecenia produkcyjnego nie wpływają na kolejne obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="fd6a6-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
