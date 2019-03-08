---
title: Typowe przyczyny odchyleń produkcji
description: Ten artykuł wyjaśnia różne typowe przyczyny poszczególnych typów odchyleń produkcji.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50f8cd7904e1d32175edd321fbd6533e985fb324
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "308697"
---
# <a name="common-sources-of-production-variances"></a><span data-ttu-id="a0260-103">Typowe przyczyny odchyleń produkcji</span><span class="sxs-lookup"><span data-stu-id="a0260-103">Common sources of production variances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0260-104">Ten artykuł wyjaśnia różne typowe przyczyny poszczególnych typów odchyleń produkcji.</span><span class="sxs-lookup"><span data-stu-id="a0260-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="a0260-105">Poniżej przedstawiono niektóre typowe źródła odchyleń w **rozmiarze partii**:</span><span class="sxs-lookup"><span data-stu-id="a0260-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="a0260-106">Właściwa ilość w zleceniu produkcyjnym różni się od ilości obliczania stosowanej w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="a0260-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="a0260-107">Ilość stanowi podstawę do amortyzowania kosztów stałych.</span><span class="sxs-lookup"><span data-stu-id="a0260-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="a0260-108">Wartość kosztów stałych w zleceniu produkcyjnym różni się od kosztów stałych stosowanych w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="a0260-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="a0260-109">Rozbieżność ta może mieć różne przyczyny.</span><span class="sxs-lookup"><span data-stu-id="a0260-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="a0260-110">Na przykład koszty stałe mogą odzwierciedlać następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="a0260-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="a0260-111">Ręcznie zmiany w liście składowej (BOM) lub marszrucie</span><span class="sxs-lookup"><span data-stu-id="a0260-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="a0260-112">Wybór innej wersji BOM lub marszruty podczas tworzenia zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="a0260-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="a0260-113">Zaplanowane zmiany inżynieryjne w wersji BOM lub marszruty przypisanej do towaru</span><span class="sxs-lookup"><span data-stu-id="a0260-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="a0260-114">Poniżej przedstawiono niektóre typowe źródła odchyleń w **cenie produkcji**:</span><span class="sxs-lookup"><span data-stu-id="a0260-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="a0260-115">Kategoria kosztów (i cena w kategorii kosztów) zgłoszonego zużycia w operacji marszruty różni się od kategorii kosztów stosowanej w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="a0260-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="a0260-116">Aktywny koszt dla kategorii kosztów własnych różni się od kategorii kosztów własnych stosowanej w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="a0260-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="a0260-117">Poniżej przedstawiono niektóre typowe źródła odchyleń w **ilości produkcji**:</span><span class="sxs-lookup"><span data-stu-id="a0260-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="a0260-118">Nadmierne lub niewystarczające wydanie składnika materiałowego.</span><span class="sxs-lookup"><span data-stu-id="a0260-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="a0260-119">Zawyżony lub zaniżony zgłoszony czas operacji marszruty.</span><span class="sxs-lookup"><span data-stu-id="a0260-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="a0260-120">Przyjęcie za dużej lub za małej ilości dobrego towaru nadrzędnego względem ilości zamówienia.</span><span class="sxs-lookup"><span data-stu-id="a0260-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="a0260-121">Jednak wydanie składników i zgłoszenie operacji wykonano kompletnie na podstawie ilości zamówienia dla zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="a0260-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="a0260-122">Poniżej przedstawiono niektóre typowe źródła odchyleń w **podstawiania produkcji**:</span><span class="sxs-lookup"><span data-stu-id="a0260-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="a0260-123">Wydanie składnika materiałowego nienależącego do BOM produkcji.</span><span class="sxs-lookup"><span data-stu-id="a0260-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="a0260-124">Ręczne dodanie składnika do BOM produkcji i zgłoszenie go jako zużytego.</span><span class="sxs-lookup"><span data-stu-id="a0260-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="a0260-125">Zgłoszenie towaru jako zużytego bez ręcznego dodania go do BOM produkcji.</span><span class="sxs-lookup"><span data-stu-id="a0260-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="a0260-126">Ręczne dodanie operacji do marszruty produkcji i zgłoszenie tej operacji jako zużytej.</span><span class="sxs-lookup"><span data-stu-id="a0260-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="a0260-127">Podczas tworzenia zlecenia produkcyjnego wybrano wersję BOM inną niż wersja BOM używana w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="a0260-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="a0260-128">Podczas tworzenia zlecenia produkcyjnego wybrano wersję marszruty inną niż wersja marszruty używana w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="a0260-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>




