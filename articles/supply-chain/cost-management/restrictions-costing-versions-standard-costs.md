---
title: Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych.
description: W tym temacie opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych.
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdbe74f2f71d0fbd3c237cceb6b184747636e9a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821496"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a><span data-ttu-id="da809-103">Ograniczenia dotyczące wersji wyceny opartej na kosztach standardowych.</span><span class="sxs-lookup"><span data-stu-id="da809-103">Restrictions on costing versions for standard costs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da809-104">W tym temacie opisano ograniczenia mające zastosowanie do wersji wyceny kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="da809-104">This topic describes the restrictions that apply to a costing version for standard costs.</span></span> 

<span data-ttu-id="da809-105">Poniższe ograniczenia zapewniają zgodność ze standardowymi zasadami wyceny:</span><span class="sxs-lookup"><span data-stu-id="da809-105">The following restrictions help guarantee adherence to standard costing principles:</span></span>

-  <span data-ttu-id="da809-106">Opłaty muszą być uwzględnione w koszcie towaru.</span><span class="sxs-lookup"><span data-stu-id="da809-106">Charges must be included in an item's cost.</span></span> <span data-ttu-id="da809-107">Opłaty dotyczące wytworzonego towaru odzwierciedlają zamortyzowane koszty stałe w informacjach listy składowej (BOM) i marszruty,</span><span class="sxs-lookup"><span data-stu-id="da809-107">The charges for a manufactured item represent the amortized constant costs in the bill of materials (BOM) and route information.</span></span> <span data-ttu-id="da809-108">zatem muszą być uwzględnione w koszcie jednostkowym.</span><span class="sxs-lookup"><span data-stu-id="da809-108">Therefore, the charges must be included in the unit cost.</span></span> <span data-ttu-id="da809-109">W koszcie jednostkowym towaru muszą być również uwzględnione opłaty dotyczące zakupionego towaru.</span><span class="sxs-lookup"><span data-stu-id="da809-109">The charges for a purchased item are also included in the item's unit cost.</span></span>

-  <span data-ttu-id="da809-110">Obliczanie standardowych kosztów wyprodukowanych towarów musi być oparte na rekordach kosztów w wersji wyceny kosztów standardowych.</span><span class="sxs-lookup"><span data-stu-id="da809-110">Calculation of standard costs for manufactured items must be based on the cost records in a costing version for standard costs.</span></span> <span data-ttu-id="da809-111">Alternatywne źródła danych kosztów mogą być używane jedynie do wersji wyceny kosztów planowanych, np. w umowach handlowych z ceną zakupu na kupowane towary.</span><span class="sxs-lookup"><span data-stu-id="da809-111">Alternative sources of cost data can be used only with a costing version for planned costs, such as purchase price trade agreements for purchased items.</span></span> <span data-ttu-id="da809-112">Alternatywne źródła danych kosztów są definiowane przez grupę obliczania BOM.</span><span class="sxs-lookup"><span data-stu-id="da809-112">Alternative sources of cost data are defined by the BOM calculation group.</span></span>

-  <span data-ttu-id="da809-113">Obliczenia BOM muszą być wykonywane w trybie jednopoziomowego rozłożenia.</span><span class="sxs-lookup"><span data-stu-id="da809-113">BOM calculations must be performed in a single-level explosion mode.</span></span>

<span data-ttu-id="da809-114">Dane o kosztach standardowych towaru mogą być kopiowane do rekordów innej wersji wyceny, która obejmuje koszty standardowe i planowane.</span><span class="sxs-lookup"><span data-stu-id="da809-114">The item cost data for standard costs can be copied to another costing version that contains standard costs or planned costs.</span></span> <span data-ttu-id="da809-115">Dane kosztów planowanych towaru nie mogą być jednak kopiowane do wersji wyceny zawierającej koszty standardowe, ponieważ wymienione powyżej ograniczenia nie mają zastosowania do kosztów planowanych.</span><span class="sxs-lookup"><span data-stu-id="da809-115">However, the item cost data for planned costs can't be copied to a cost version that contains standard costs, because the restrictions that are listed earlier in this topic don't apply to planned costs.</span></span>

<a name="related-topics"></a><span data-ttu-id="da809-116">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="da809-116">Related topics</span></span>
--------

[<span data-ttu-id="da809-117">Omówienie wersji wyceny</span><span class="sxs-lookup"><span data-stu-id="da809-117">Costing versions overview</span></span>](costing-versions.md)

[<span data-ttu-id="da809-118">Aktualizowanie kosztów standardowych w środowisku nieobejmującym wytwarzania</span><span class="sxs-lookup"><span data-stu-id="da809-118">Update standard costs in a non-manufacturing environment</span></span>](update-standard-costs-non-manufacturing-environment.md)

[<span data-ttu-id="da809-119">Przygotowanie do zarządzania kosztami standardowymi wyprodukowanych towarów</span><span class="sxs-lookup"><span data-stu-id="da809-119">Prepare to maintain standard costs for manufactured items</span></span>](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]