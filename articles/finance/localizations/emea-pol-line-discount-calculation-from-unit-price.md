---
title: Obliczanie rabatu wiersza od ceny jednostkowej dla Polski
description: Dla firm w Polsce rabat wiersza może być obliczany na podstawie ceny jednostkowej z wiersza faktury, a nie z kwoty wiersza. Ten temat zawiera informacje o metodzie obliczania rabatu wiersza względem ceny jednostkowej i wyjaśnienia, jak skonfigurować tę funkcję.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 263424
ms.search.region: Poland
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: aa60d4602604838ddb5296362627fcf82af06440
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3984668"
---
# <a name="line-discount-calculation-from-the-unit-price-for-poland"></a><span data-ttu-id="ab87e-104">Obliczanie rabatu wiersza od ceny jednostkowej dla Polski</span><span class="sxs-lookup"><span data-stu-id="ab87e-104">Line discount calculation from the unit price for Poland</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab87e-105">Dla firm w Polsce rabat wiersza może być obliczany na podstawie ceny jednostkowej z wiersza faktury, a nie z kwoty wiersza.</span><span class="sxs-lookup"><span data-stu-id="ab87e-105">For legal entities in Poland, the line discount can be calculated from the unit price of an invoice line instead of from a line amount.</span></span> <span data-ttu-id="ab87e-106">Ten temat zawiera informacje o metodzie obliczania rabatu wiersza względem ceny jednostkowej i wyjaśnienia, jak skonfigurować tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="ab87e-106">This topic provides information about the Line discount calculation from unit price method and explains how to set it up.</span></span>

<span data-ttu-id="ab87e-107">W firmach w Polsce rabat wiersza nie ma być obliczany na podstawie kwoty wiersza.</span><span class="sxs-lookup"><span data-stu-id="ab87e-107">For legal entities in Poland, the line discount doesn't have to be calculated from a line amount.</span></span> <span data-ttu-id="ab87e-108">Zamiast tego można go obliczać na podstawie ceny jednostkowej wiersza faktury.</span><span class="sxs-lookup"><span data-stu-id="ab87e-108">Instead, it can be calculated from the unit price of an invoice line.</span></span> <span data-ttu-id="ab87e-109">Gdy jest używana metoda obliczania rabatu wiersza na podstawie ceny jednostkowej, przed obliczeniem kwoty wiersza następuje zaokrąglenie ceny jednostkowej z rabatem.</span><span class="sxs-lookup"><span data-stu-id="ab87e-109">When the Line discount calculation from unit price method is used, the discounted unit price is rounded before the line amount is calculated.</span></span> <span data-ttu-id="ab87e-110">W poniższej tabeli przedstawiono, jak rabat wiersza jest obliczany metodą standardową i metodą od ceny jednostkowej.</span><span class="sxs-lookup"><span data-stu-id="ab87e-110">The following table shows how the line discount is calculated by both the standard method and the Line discount calculation from unit price method.</span></span>

|<span data-ttu-id="ab87e-111">Ilość</span><span class="sxs-lookup"><span data-stu-id="ab87e-111">Quantity</span></span>|<span data-ttu-id="ab87e-112">Cena</span><span class="sxs-lookup"><span data-stu-id="ab87e-112">Price</span></span>|<span data-ttu-id="ab87e-113">Procent rabatu</span><span class="sxs-lookup"><span data-stu-id="ab87e-113">Discount percentage</span></span>|<span data-ttu-id="ab87e-114">Kwota netto (metoda standardowa)</span><span class="sxs-lookup"><span data-stu-id="ab87e-114">Net amount (Standard method)</span></span>|<span data-ttu-id="ab87e-115">Kwota netto (metoda obliczania rabatu wiersza od ceny jednostkowej)</span><span class="sxs-lookup"><span data-stu-id="ab87e-115">Net amount (Line discount calculation from unit price method)</span></span>|
|--------|-----|-------------------|---------------|------------------------------------------------|
|<span data-ttu-id="ab87e-116">100</span><span class="sxs-lookup"><span data-stu-id="ab87e-116">100</span></span>     |<span data-ttu-id="ab87e-117">6.75</span><span class="sxs-lookup"><span data-stu-id="ab87e-117">6.75</span></span> |<span data-ttu-id="ab87e-118">5</span><span class="sxs-lookup"><span data-stu-id="ab87e-118">5</span></span>                  |<span data-ttu-id="ab87e-119">641,25 (6,75 × 100 = 675.00; 675 × 0,95 = 641,25)</span><span class="sxs-lookup"><span data-stu-id="ab87e-119">641.25 (6.75 × 100 = 675.00; 675 × 0.95 = 641.25)</span></span>|<span data-ttu-id="ab87e-120">641,00 (6,75 × 0,95 = 6,4125; 6,41 × 100 = 641,00)</span><span class="sxs-lookup"><span data-stu-id="ab87e-120">641.00 (6.75 × 0.95 = 6.4125; 6.41 × 100 = 641.00)</span></span>|

> [!NOTE]
> <span data-ttu-id="ab87e-121">Wartość 0,95 użyta w obliczeniach to wynik działania 1,00 – 0,05, gdzie 0,05 jest kwotą rabatu, jeśli cena jednostkowa wynosi 1,00.</span><span class="sxs-lookup"><span data-stu-id="ab87e-121">The 0.95 that is used in the calculations equals 1.00 – 0.05, where 0.05 is the discount amount if the unit price is 1.00.</span></span>

## <a name="set-up-the-calculation-of-line-discount-parameter"></a><span data-ttu-id="ab87e-122">Konfigurowanie parametru obliczania rabatu wiersza</span><span class="sxs-lookup"><span data-stu-id="ab87e-122">Set up the Calculation of line discount parameter</span></span>
<span data-ttu-id="ab87e-123">Metoda obliczania rabatu wiersza względem ceny jednostkowej może być stosowana do rozrachunków z odbiorcami i rozrachunków z dostawcami, a konfiguruje się ją na stronach **Parametry modułu rozrachunków z odbiorcami** i **Parametry modułu Zaopatrzenie i sourcing**.</span><span class="sxs-lookup"><span data-stu-id="ab87e-123">The Line discount calculation from unit price method affects both Accounts receivable and Accounts payable, and is set up on the **Accounts receivable parameters** page and the **Procurement and sourcing parameters** page.</span></span> <span data-ttu-id="ab87e-124">Parametr **Obliczanie rabatu liniowego** ma następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="ab87e-124">The **Calculation of line discount** parameter has the following options:</span></span>

-   <span data-ttu-id="ab87e-125">**Od wartości wiersza** — rabat wiersza jest obliczany metodą standardową.</span><span class="sxs-lookup"><span data-stu-id="ab87e-125">**From line value** – Use the standard method to calculate the line discount.</span></span>
-   <span data-ttu-id="ab87e-126">**Od ceny jednostkowej** — rabat wiersza jest obliczany względem ceny jednostkowej.</span><span class="sxs-lookup"><span data-stu-id="ab87e-126">**From unit price** – Use the Line discount calculation from unit price method to calculate the line discount.</span></span>

<span data-ttu-id="ab87e-127">Parametr **Obliczanie rabatu liniowego** wpływa na następujące dokumenty:</span><span class="sxs-lookup"><span data-stu-id="ab87e-127">The **Calculation of line discount** parameter affects the following documents:</span></span>

-   <span data-ttu-id="ab87e-128">Zamówienia sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ab87e-128">Sales orders</span></span>
-   <span data-ttu-id="ab87e-129">Zamówienia zakupu</span><span class="sxs-lookup"><span data-stu-id="ab87e-129">Purchase orders</span></span>
-   <span data-ttu-id="ab87e-130">Faktury dostawcy</span><span class="sxs-lookup"><span data-stu-id="ab87e-130">Vendor invoices</span></span>




