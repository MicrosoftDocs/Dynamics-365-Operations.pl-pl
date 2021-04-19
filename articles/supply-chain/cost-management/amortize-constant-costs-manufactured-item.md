---
title: Amortyzowanie kosztów stałych wytworzonego towaru
description: Stałe koszty wytworzonego towaru odzwierciedlają czas przezbrajania dla danej operacji oraz składniki o stałej ilości lub stałą ilość odpadków.
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 5f44c0c7a50df55206ddd08ce71772f8caac9363
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808119"
---
# <a name="amortize-constant-costs-for-a-manufactured-item"></a><span data-ttu-id="7a4d2-103">Amortyzowanie kosztów stałych wytworzonego towaru</span><span class="sxs-lookup"><span data-stu-id="7a4d2-103">Amortize constant costs for a manufactured item</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a4d2-104">Stałe koszty wytworzonego towaru odzwierciedlają czas przezbrajania dla danej operacji oraz składniki o stałej ilości lub stałą ilość odpadków.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-104">A manufactured item’s constant costs reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span> 

<span data-ttu-id="7a4d2-105">Podczas amortyzowania tych kosztów stałych w obliczonych kosztach wytworzonego towaru jest używana koncepcja wielkości partii do wyceny.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-105">The concept of a costing lot size is used to amortize these constant costs in the calculated cost of a manufactured item.</span></span> <span data-ttu-id="7a4d2-106">Nazwa tej koncepcji ma kilka synonimów, na przykład „księgowa wielkość partii”.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-106">This concept has several synonyms, one of which is accounting lot size.</span></span> <span data-ttu-id="7a4d2-107">Również koncepcja amortyzowania kosztów stałych ma kilka nazw, np. „proporcjonalne koszty stałe”.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-107">The concept of amortizing constant costs also has several synonyms, one of which is proportional constant costs.</span></span>

<span data-ttu-id="7a4d2-108">Ilość w wielkości partii do wyceny dla wyprodukowanego towaru jest używana do obliczenia listy składowej (BOM).</span><span class="sxs-lookup"><span data-stu-id="7a4d2-108">The quantity of a costing lot size for a manufactured item is used in a bill of material (BOM) calculation.</span></span> <span data-ttu-id="7a4d2-109">Wielkość ta zależy od sposobu inicjowania i wykonywania obliczeń BOM, tak jak przedstawiono poniżej:</span><span class="sxs-lookup"><span data-stu-id="7a4d2-109">The quantity depends on how you initiate and perform the BOM calculation, as illustrated by the following:</span></span>

-   <span data-ttu-id="7a4d2-110">Domyślna ilość obliczania w obliczeniach BOM towaru — Standardowa ilość zamówienia towaru z zapasów pełni rolę wielkości partii do wyceny, ale wartość domyślna może być większą ilością w celu odzwierciedlenia wielokrotności ilości zamówienia towaru.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-110">Default calculation quantity in an item’s BOM calculation − The item’s standard order quantity for inventory acts as the costing lot size, but the default value might be a greater quantity to reflect the item’s order quantity multiple.</span></span> <span data-ttu-id="7a4d2-111">Standardową ilość zamówienia towaru oraz wielokrotność można zdefiniować w ramach domyślnych ustawień zamówień lub ustawień zamówień właściwych dla oddziału.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-111">The item’s standard order quantity and multiple can be defined within its default order settings or site-specific order settings.</span></span>
-   <span data-ttu-id="7a4d2-112">Określona ilość obliczania w obliczeniach BOM towaru — określona ilość obliczania służy jako wycena rozmiaru partii danego towaru.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-112">Specified calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item.</span></span> <span data-ttu-id="7a4d2-113">Na początku ilość obliczania jest równa standardowej ilości zamówienia towaru, ale wartość domyślną można ręcznie zastąpić.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-113">The calculation quantity initially uses the item’s standard order quantity, but the default value can be manually overridden.</span></span> <span data-ttu-id="7a4d2-114">Podana ilość obliczania reprezentuje wielkość partii do wyceny dla określonego towaru i dla wytworzonych składników, których typem wiersza BOM jest Produkcja.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-114">The specified calculation quantity represents the costing lot size for the specified item, and for manufactured components that have a BOM line type of production.</span></span> <span data-ttu-id="7a4d2-115">Jest to spowodowane założeniem, że składnik zostanie wyprodukowany w ściśle określonej ilości.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-115">This is because it is assumed that the component will be produced to the exact quantity.</span></span> <span data-ttu-id="7a4d2-116">Rozmiar partii do wyceny innych wytwarzanych składników mających typ wiersza BOM Towar będzie odzwierciedlać standardową ilość zamówienia.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-116">The costing lot size for other manufactured components that have a BOM line type of item will reflect their standard order quantity.</span></span>
-   <span data-ttu-id="7a4d2-117">Określona ilość obliczania produkcji na zamówienie w obliczeniach BOM towaru — określona ilość obliczania służy jako wycena rozmiaru partii towaru i jego wyprodukowanych składników, gdy w obliczeniach BOM jest używany tryb rozłożenia produkcji na zamówienie.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-117">Specified make-to-order calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item and its manufactured components when BOM calculations use a make-to-order explosion mode.</span></span> <span data-ttu-id="7a4d2-118">Zakłada się, że wytwarzane składniki będą produkowane aż do osiągnięcia określonej ilości, tak jak w przypadku wytwarzanych składników o typie wiersza BOM Produkcja.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-118">It is assumed that the manufactured components will be produced to the exact quantity, just like a manufactured component that has a BOM line type of production.</span></span>
-   <span data-ttu-id="7a4d2-119">Określona ilość obliczania w obliczeniach BOM zależnych od zamówienia — obliczenia BOM zależne od zamówienia mogą być wykonywane w wypadku elementu wiersza w zamówieniu sprzedaży, ofercie sprzedaży lub zleceniu serwisowym.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-119">Specified calculation quantity in an order-specific BOM calculation − An order-specific BOM calculation can be performed for a line item on a sales order, sales quotation, or service order.</span></span> <span data-ttu-id="7a4d2-120">Podana ilość obliczania jest równa ilości pierwotnej pozycji w wierszu, ale ilość domyślną można zastąpić.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-120">The specified calculation quantity uses the quantity on the originating line item, but the default quantity can be overridden.</span></span> <span data-ttu-id="7a4d2-121">Można wybrać, czy w obliczeniach BOM zależnych od zamówienia jest używany tryb rozłożenia produkcji na zamówienie, czy wielopoziomowy tryb rozłożenia.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-121">You can select whether the order-specific BOM calculation uses a make-to-order or multilevel explosion mode.</span></span>

<span data-ttu-id="7a4d2-122">Obliczona kwota zamortyzowanych stałych kosztów wytworzonego towaru jest określana jako opłaty.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-122">The calculated amount of a manufactured item’s amortized constant costs is termed charges.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]