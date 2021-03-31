---
title: Typowe przyczyny odchyleń produkcji
description: Ten artykuł wyjaśnia różne typowe przyczyny poszczególnych typów odchyleń produkcji.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f36e482595cad49d1149873f8bcdd6a05a3287d5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229286"
---
# <a name="common-sources-of-production-variances"></a><span data-ttu-id="2f80c-103">Typowe przyczyny odchyleń produkcji</span><span class="sxs-lookup"><span data-stu-id="2f80c-103">Common sources of production variances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f80c-104">Ten artykuł wyjaśnia różne typowe przyczyny poszczególnych typów odchyleń produkcji.</span><span class="sxs-lookup"><span data-stu-id="2f80c-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="2f80c-105">Poniżej przedstawiono niektóre typowe źródła odchyleń w **rozmiarze partii**:</span><span class="sxs-lookup"><span data-stu-id="2f80c-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="2f80c-106">Właściwa ilość w zleceniu produkcyjnym różni się od ilości obliczania stosowanej w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="2f80c-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="2f80c-107">Ilość stanowi podstawę do amortyzowania kosztów stałych.</span><span class="sxs-lookup"><span data-stu-id="2f80c-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="2f80c-108">Wartość kosztów stałych w zleceniu produkcyjnym różni się od kosztów stałych stosowanych w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="2f80c-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="2f80c-109">Rozbieżność ta może mieć różne przyczyny.</span><span class="sxs-lookup"><span data-stu-id="2f80c-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="2f80c-110">Na przykład koszty stałe mogą odzwierciedlać następujące zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="2f80c-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="2f80c-111">Ręcznie zmiany w liście składowej (BOM) lub marszrucie</span><span class="sxs-lookup"><span data-stu-id="2f80c-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="2f80c-112">Wybór innej wersji BOM lub marszruty podczas tworzenia zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="2f80c-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="2f80c-113">Zaplanowane zmiany inżynieryjne w wersji BOM lub marszruty przypisanej do towaru</span><span class="sxs-lookup"><span data-stu-id="2f80c-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="2f80c-114">Poniżej przedstawiono niektóre typowe źródła odchyleń w **cenie produkcji**:</span><span class="sxs-lookup"><span data-stu-id="2f80c-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="2f80c-115">Kategoria kosztów (i cena w kategorii kosztów) zgłoszonego zużycia w operacji marszruty różni się od kategorii kosztów stosowanej w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="2f80c-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="2f80c-116">Aktywny koszt dla kategorii kosztów własnych różni się od kategorii kosztów własnych stosowanej w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="2f80c-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="2f80c-117">Poniżej przedstawiono niektóre typowe źródła odchyleń w **ilości produkcji**:</span><span class="sxs-lookup"><span data-stu-id="2f80c-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="2f80c-118">Nadmierne lub niewystarczające wydanie składnika materiałowego.</span><span class="sxs-lookup"><span data-stu-id="2f80c-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="2f80c-119">Zawyżony lub zaniżony zgłoszony czas operacji marszruty.</span><span class="sxs-lookup"><span data-stu-id="2f80c-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="2f80c-120">Przyjęcie za dużej lub za małej ilości dobrego towaru nadrzędnego względem ilości zamówienia.</span><span class="sxs-lookup"><span data-stu-id="2f80c-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="2f80c-121">Jednak wydanie składników i zgłoszenie operacji wykonano kompletnie na podstawie ilości zamówienia dla zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="2f80c-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="2f80c-122">Poniżej przedstawiono niektóre typowe źródła odchyleń w **podstawiania produkcji**:</span><span class="sxs-lookup"><span data-stu-id="2f80c-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="2f80c-123">Wydanie składnika materiałowego nienależącego do BOM produkcji.</span><span class="sxs-lookup"><span data-stu-id="2f80c-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="2f80c-124">Ręczne dodanie składnika do BOM produkcji i zgłoszenie go jako zużytego.</span><span class="sxs-lookup"><span data-stu-id="2f80c-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="2f80c-125">Zgłoszenie towaru jako zużytego bez ręcznego dodania go do BOM produkcji.</span><span class="sxs-lookup"><span data-stu-id="2f80c-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="2f80c-126">Ręczne dodanie operacji do marszruty produkcji i zgłoszenie tej operacji jako zużytej.</span><span class="sxs-lookup"><span data-stu-id="2f80c-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="2f80c-127">Podczas tworzenia zlecenia produkcyjnego wybrano wersję BOM inną niż wersja BOM używana w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="2f80c-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="2f80c-128">Podczas tworzenia zlecenia produkcyjnego wybrano wersję marszruty inną niż wersja marszruty używana w obliczeniach kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="2f80c-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]