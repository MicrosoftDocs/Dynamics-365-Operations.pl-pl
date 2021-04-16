---
title: Wymiary składników kosztów
description: Wymiary składników kosztów są jednym z filarów rachunku kosztów. Służą do kategoryzowania i śledzenia, dokąd płyną koszty.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 067d7035cdb9c8f4bcb2bdac9cf0a33cd4e01079
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811444"
---
# <a name="cost-element-dimensions"></a><span data-ttu-id="64025-103">Wymiary składników kosztów</span><span class="sxs-lookup"><span data-stu-id="64025-103">Cost element dimensions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64025-104">Wymiary składników kosztów są jednym z filarów rachunku kosztów. Służą do kategoryzowania i śledzenia, dokąd płyną koszty.</span><span class="sxs-lookup"><span data-stu-id="64025-104">As one of the core pillars in Cost accounting, cost element dimensions are used to categorize and track where costs flow to.</span></span> 

<span data-ttu-id="64025-105">Składnik kosztu odnosi się do elementu istotnego dla kosztów w planie kont.</span><span class="sxs-lookup"><span data-stu-id="64025-105">A cost element corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="64025-106">Zasadniczo może to być element dowolnego typu na najniższym poziomie w przedsiębiorstwie, dokąd mogą płynąć koszty.</span><span class="sxs-lookup"><span data-stu-id="64025-106">Basically, it can be any type of element at the lowest level in a business where costs can flow to.</span></span> <span data-ttu-id="64025-107">Pod względem koncepcyjnym składnikami kosztów mogą być tak różne elementy, jak konta księgowe i wszystkie zasoby związane z kosztami.</span><span class="sxs-lookup"><span data-stu-id="64025-107">Cost elements as a concept range from ledger accounts to all cost-relevant resources.</span></span> <span data-ttu-id="64025-108">Obecnie moduł Rachunek kosztów obsługuje konta księgowe.</span><span class="sxs-lookup"><span data-stu-id="64025-108">Currently, Cost accounting supports ledger accounts.</span></span>

## <a name="two-types-of-cost-elements"></a><span data-ttu-id="64025-109">Dwa rodzaje składników kosztów</span><span class="sxs-lookup"><span data-stu-id="64025-109">Two types of cost elements</span></span>
<span data-ttu-id="64025-110">Istnieją dwa typy składników kosztów: podstawowe i podrzędne.</span><span class="sxs-lookup"><span data-stu-id="64025-110">There are two types of cost elements: primary cost elements and secondary cost elements.</span></span> <span data-ttu-id="64025-111">W poniższej tabeli opisano różnice między tymi typami.</span><span class="sxs-lookup"><span data-stu-id="64025-111">The following table describes the difference between the two types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="64025-112"><strong>Podstawowe składniki kosztów</strong></span><span class="sxs-lookup"><span data-stu-id="64025-112"><strong>Primary cost elements</strong></span></span></td>
<td><span data-ttu-id="64025-113"><strong>Podrzędne składniki kosztów</strong></span><span class="sxs-lookup"><span data-stu-id="64025-113"><strong>Secondary cost elements</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="64025-114">Podstawowe składniki kosztów reprezentują przepływów kosztów z księgowości finansowej do rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="64025-114">The primary cost elements represent the flow of costs from financial accounting to cost accounting.</span></span> <span data-ttu-id="64025-115">Struktura składników kosztów odpowiada strukturze konta wynikowego w księdze głównej, gdzie składnik kosztu może odpowiadać kontu głównemu.</span><span class="sxs-lookup"><span data-stu-id="64025-115">The cost element structure corresponds to the profit and loss account structure in the general ledger, where a cost element can correspond to a main account.</span></span> <span data-ttu-id="64025-116">Nie wszystkie konta główne muszą być reprezentowane jako składniki kosztów. Zależy to od potrzeb biznesowych.</span><span class="sxs-lookup"><span data-stu-id="64025-116">Not all main accounts may necessarily be represented as cost elements depending on the business needs.</span></span> <span data-ttu-id="64025-117">Przykłady podstawowych składników kosztów:</span><span class="sxs-lookup"><span data-stu-id="64025-117">Examples of primary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="64025-118">Koszt własny sprzedaży (COG)</span><span class="sxs-lookup"><span data-stu-id="64025-118">Costs of goods sold (COGs)</span></span></li>
<li><span data-ttu-id="64025-119">Koszty pośrednie materiału</span><span class="sxs-lookup"><span data-stu-id="64025-119">Indirect material costs</span></span></li>
<li><span data-ttu-id="64025-120">Koszty pracownicze</span><span class="sxs-lookup"><span data-stu-id="64025-120">Personnel costs</span></span></li>
<li><span data-ttu-id="64025-121">Koszty energii</span><span class="sxs-lookup"><span data-stu-id="64025-121">Energy costs</span></span></li>
</ul></td>
<td><span data-ttu-id="64025-122">Podrzędne składniki kosztów reprezentują wewnętrzny przepływ kosztów, ponieważ koszty te są tworzone i wykorzystywane tylko w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="64025-122">The secondary cost elements represent the flow of costs internally because these costs are created and used only in Cost accounting.</span></span> <span data-ttu-id="64025-123">Służą one zapewnieniu możliwości śledzenia źródła kosztów.</span><span class="sxs-lookup"><span data-stu-id="64025-123">They are used to secure that the source of costs can be traced.</span></span> <span data-ttu-id="64025-124">Te składniki kosztów są używane w alokacji kosztów i obliczeniach kosztów ogólnych.</span><span class="sxs-lookup"><span data-stu-id="64025-124">These cost elements are used in cost allocations and overhead calculations.</span></span> <span data-ttu-id="64025-125">Przykłady podrzędnych składników kosztów:</span><span class="sxs-lookup"><span data-stu-id="64025-125">Examples of secondary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="64025-126">Koszty produkcji</span><span class="sxs-lookup"><span data-stu-id="64025-126">Production costs</span></span></li>
<li><span data-ttu-id="64025-127">Koszty ogólne produkcji, materiałów i marketingu</span><span class="sxs-lookup"><span data-stu-id="64025-127">Production, material, and marketing overheads</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a><span data-ttu-id="64025-128">Wymiary składników kosztów i elementy członkowskie wymiarów składników kosztów</span><span class="sxs-lookup"><span data-stu-id="64025-128">Cost element dimensions and cost element dimension members</span></span>
<span data-ttu-id="64025-129">Składniki kosztów są określane jako *wymiary składników kosztów* .</span><span class="sxs-lookup"><span data-stu-id="64025-129">Cost elements are referred to as *cost element dimensions* .</span></span> <span data-ttu-id="64025-130">Wartości poszczególnych wymiarów są nazywane *elementami członkowskimi wymiarów składników kosztów*.</span><span class="sxs-lookup"><span data-stu-id="64025-130">The individual dimension values are called *cost element dimension members*.</span></span> <span data-ttu-id="64025-131">Na przykład masz strukturę amerykańskiego planu kont (COA), która jest podstawą do sprawozdawczości ustawowej.</span><span class="sxs-lookup"><span data-stu-id="64025-131">For example, you have a US chart of accounts structure (COA) that is the base for your statutory reporting.</span></span> <span data-ttu-id="64025-132">Ten plan kont służy jako wymiar składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="64025-132">This COA is used as the cost element dimension.</span></span> <span data-ttu-id="64025-133">Konta, czyli podstawowe składniki kosztów, są przedstawiane jako elementy członkowskie wymiaru składników kosztów w rachunku kosztów.</span><span class="sxs-lookup"><span data-stu-id="64025-133">The accounts, which are primary cost elements, are represented as the cost element dimension members in Cost accounting.</span></span> <span data-ttu-id="64025-134">Poniższy zrzut ekranu przedstawia przykład kont głównych jako wymiaru składników kosztów, gdzie faktyczne konta główne są elementami członkowskimi wymiaru składników kosztów.</span><span class="sxs-lookup"><span data-stu-id="64025-134">The following screenshot shows an example of Main Accounts as the cost element dimension with its actual main accounts as the cost element dimension members.</span></span> 

<span data-ttu-id="64025-135">[![Zrzut ekranu kont głównych jako wymiar elementu kosztu](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="64025-135">[![Screenshot of Main Accounts as cost element dimension](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span></span>

## <a name="import-cost-element-dimension-members-through-data-connectors"></a><span data-ttu-id="64025-136">Importowanie elementów członkowskich wymiarów składników kosztów za pośrednictwem łączników danych</span><span class="sxs-lookup"><span data-stu-id="64025-136">Import cost element dimension members through data connectors</span></span>
<span data-ttu-id="64025-137">Aby ułatwić sobie konfigurowanie elementów członkowskich wymiarów składników kosztów w module Rachunek kosztów, można używać łączników danych wbudowanych w systemie lub utworzonych samodzielnie do podstawowych składników kosztów z jednego lub więcej systemów źródłowych.</span><span class="sxs-lookup"><span data-stu-id="64025-137">To ease the setup of cost element dimension members in Cost accounting, you can use data connectors that are either pre-built or your custom build to retrieve the primary cost elements from one or more source systems.</span></span>

## <a name="implementation-considerations"></a><span data-ttu-id="64025-138">Uwagi dotyczące implementacji</span><span class="sxs-lookup"><span data-stu-id="64025-138">Implementation considerations</span></span>
<span data-ttu-id="64025-139">Składniki kosztów reprezentują najniższy poziom szczegółów kosztów, dlatego podczas implementowania struktury składników kosztów należy się upewnić, że są uwzględnione wszystkie składniki kosztów wymagane w sprawozdawczości dla kierownictwa.</span><span class="sxs-lookup"><span data-stu-id="64025-139">As cost elements represent the lowest level of cost details, you should make sure that all the cost elements required to make the managerial reporting are included when you implement the cost elements structure.</span></span> <span data-ttu-id="64025-140">Może być trudne znalezienie odpowiedniej liczby składników kosztów na potrzeby kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="64025-140">It can be a challenge to find an appropriate number of cost elements for cost control.</span></span> <span data-ttu-id="64025-141">Posiadanie tysięcy składników kosztów może utrudnić kontrolowanie ich wszystkich.</span><span class="sxs-lookup"><span data-stu-id="64025-141">Having thousands of cost elements can make it difficult to control each cost element.</span></span> <span data-ttu-id="64025-142">Dlatego alternatywnie można grupować składniki kosztów i zarządzać kontrolą kosztów na poziomie zbiorczym.</span><span class="sxs-lookup"><span data-stu-id="64025-142">As an alternative, you can group cost elements and manage cost control at an aggregated level.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]