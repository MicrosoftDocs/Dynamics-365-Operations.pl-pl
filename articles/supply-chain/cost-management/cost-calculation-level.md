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
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 42088d8c005cf3fc04e768f1b8e8c8ca0b8c6993
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967739"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="50110-104">Poziom obliczania kosztu</span><span class="sxs-lookup"><span data-stu-id="50110-104">Cost calculation level</span></span>

<span data-ttu-id="50110-105">Poziom BOM o nazwie **Poziom obliczania kosztu** wyklucza zlecenia produkcyjne i zamówienia partii z jego obliczeń.</span><span class="sxs-lookup"><span data-stu-id="50110-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="50110-106">Ten poziom jest używany w systemie podczas uruchamiania obliczeń kosztów w wersjach ceny.</span><span class="sxs-lookup"><span data-stu-id="50110-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="50110-107">W procesach takich jak ponowne obliczanie i zamykanie zapasów system używa zamiast tego **Poziom wyceny** poziom BOM.</span><span class="sxs-lookup"><span data-stu-id="50110-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="50110-108">Poniższy prosty scenariusz pokazuje różnice między poziomem BOM **Poziom obliczania kosztu** a poziomem BOM **Poziom wyceny**.</span><span class="sxs-lookup"><span data-stu-id="50110-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="50110-109">Istnieją trzy produkty: A, B i C. Produkt C jest składnikiem produktu B, a produkt B jest składnikiem produktu A.</span><span class="sxs-lookup"><span data-stu-id="50110-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="50110-110">**Poziom wyceny** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="50110-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="50110-111">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="50110-111">**Product A:** 0</span></span>
    - <span data-ttu-id="50110-112">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="50110-112">**Product B:** 1</span></span>
    - <span data-ttu-id="50110-113">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="50110-113">**Product C:** 2</span></span>

- <span data-ttu-id="50110-114">**Poziom obliczania kosztu** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="50110-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="50110-115">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="50110-115">**Product A:** 0</span></span>
    - <span data-ttu-id="50110-116">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="50110-116">**Product B:** 1</span></span>
    - <span data-ttu-id="50110-117">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="50110-117">**Product C:** 2</span></span>

<span data-ttu-id="50110-118">Tworzone jest zlecenie produkcyjne dla produktu C, a produkt A jest dodawany do BOM zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="50110-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="50110-119">Po oszacowaniu zamówienia poziomy BOM są aktualizowane w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="50110-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="50110-120">**Poziom wyceny** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="50110-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="50110-121">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="50110-121">**Product B:** 1</span></span>
    - <span data-ttu-id="50110-122">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="50110-122">**Product C:** 2</span></span>
    - <span data-ttu-id="50110-123">**Produkt A:** 3</span><span class="sxs-lookup"><span data-stu-id="50110-123">**Product A:** 3</span></span>

- <span data-ttu-id="50110-124">**Poziom obliczania kosztu** przypisuje następujące poziomy BOM:</span><span class="sxs-lookup"><span data-stu-id="50110-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="50110-125">**Produkt A:** 0</span><span class="sxs-lookup"><span data-stu-id="50110-125">**Product A:** 0</span></span>
    - <span data-ttu-id="50110-126">**Produkt B:** 1</span><span class="sxs-lookup"><span data-stu-id="50110-126">**Product B:** 1</span></span>
    - <span data-ttu-id="50110-127">**Produkt C:** 2</span><span class="sxs-lookup"><span data-stu-id="50110-127">**Product C:** 2</span></span>

<span data-ttu-id="50110-128">To zachowanie gwarantuje, że zmiany BOM zlecenia produkcyjnego nie wpływają na kolejne obliczenia kosztów.</span><span class="sxs-lookup"><span data-stu-id="50110-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
