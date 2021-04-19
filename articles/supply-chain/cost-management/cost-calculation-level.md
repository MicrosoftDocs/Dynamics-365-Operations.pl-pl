---
title: Poziom obliczania kosztu
description: W tym temacie opisano poziom BOM o nazwie poziom obliczania kosztu. Ten poziom BOM wyklucza produkcję i zamówienia partii z obliczeń.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f7cde239107528a6bc2aeb0e424d024d4f3fb2a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839494"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="9d8ea-104">Poziom obliczania kosztu</span><span class="sxs-lookup"><span data-stu-id="9d8ea-104">Cost calculation level</span></span>

<span data-ttu-id="9d8ea-105">Poziom BOM o nazwie **Poziom obliczania kosztu** wyklucza zlecenia produkcyjne i zamówienia partii z jego obliczeń.</span><span class="sxs-lookup"><span data-stu-id="9d8ea-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="9d8ea-106">Ten poziom jest używany w systemie podczas uruchamiania obliczeń kosztów w wersjach ceny.</span><span class="sxs-lookup"><span data-stu-id="9d8ea-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="9d8ea-107">W procesach takich jak ponowne obliczanie i zamykanie zapasów system używa zamiast tego **Poziom wyceny** poziom BOM.</span><span class="sxs-lookup"><span data-stu-id="9d8ea-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="9d8ea-108">Poniższy prosty scenariusz pokazuje różnice między poziomem BOM **Poziom obliczania kosztu** a poziomem BOM **Poziom wyceny**.</span><span class="sxs-lookup"><span data-stu-id="9d8ea-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="9d8ea-109">Istnieją trzy produkty: A, B i C. Produkt C jest składnikiem produktu B, a produkt B jest składnikiem produktu A.</span><span class="sxs-lookup"><span data-stu-id="9d8ea-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="9d8ea-110">**Poziom wyceny** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="9d8ea-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="9d8ea-111">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="9d8ea-111">**Product A:** 0</span></span>
    - <span data-ttu-id="9d8ea-112">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="9d8ea-112">**Product B:** 1</span></span>
    - <span data-ttu-id="9d8ea-113">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="9d8ea-113">**Product C:** 2</span></span>

- <span data-ttu-id="9d8ea-114">**Poziom obliczania kosztu** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="9d8ea-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="9d8ea-115">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="9d8ea-115">**Product A:** 0</span></span>
    - <span data-ttu-id="9d8ea-116">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="9d8ea-116">**Product B:** 1</span></span>
    - <span data-ttu-id="9d8ea-117">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="9d8ea-117">**Product C:** 2</span></span>

<span data-ttu-id="9d8ea-118">Tworzone jest zlecenie produkcyjne dla produktu C, a produkt A jest dodawany do BOM zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="9d8ea-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="9d8ea-119">Po oszacowaniu zamówienia poziomy BOM są aktualizowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9d8ea-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="9d8ea-120">**Poziom wyceny** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="9d8ea-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="9d8ea-121">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="9d8ea-121">**Product B:** 1</span></span>
    - <span data-ttu-id="9d8ea-122">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="9d8ea-122">**Product C:** 2</span></span>
    - <span data-ttu-id="9d8ea-123">**Produkt A:** 3</span><span class="sxs-lookup"><span data-stu-id="9d8ea-123">**Product A:** 3</span></span>

- <span data-ttu-id="9d8ea-124">**Poziom obliczania kosztu** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="9d8ea-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="9d8ea-125">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="9d8ea-125">**Product A:** 0</span></span>
    - <span data-ttu-id="9d8ea-126">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="9d8ea-126">**Product B:** 1</span></span>
    - <span data-ttu-id="9d8ea-127">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="9d8ea-127">**Product C:** 2</span></span>

<span data-ttu-id="9d8ea-128">To zachowanie gwarantuje, że zmiany BOM zlecenia produkcyjnego nie wpływają na kolejne obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="9d8ea-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]