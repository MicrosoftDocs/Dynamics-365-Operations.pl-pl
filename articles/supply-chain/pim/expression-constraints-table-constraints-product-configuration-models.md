---
title: Ograniczenia wyrażenia i ograniczenia tabeli w modelach konfiguracji produktu.
description: W tym temacie opisano zastosowanie ograniczeń wyrażenia i ograniczeń tabeli. Ograniczenia służą do kontroli wartości atrybutów, które można wybrać podczas konfigurowania produktów dla zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego. Można użyć ograniczeń wyrażenia lub ograniczeń tabeli, w zależności od preferencji dotyczących tworzenia ograniczeń.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57b0a11fbadd7e39140085eebcaa96b961196f32
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189875"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="c1421-105">Ograniczenia wyrażenia i ograniczenia tabeli w modelach konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c1421-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1421-106">W tym temacie opisano zastosowanie ograniczeń wyrażenia i ograniczeń tabeli.</span><span class="sxs-lookup"><span data-stu-id="c1421-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="c1421-107">Ograniczenia służą do kontroli wartości atrybutów, które można wybrać podczas konfigurowania produktów dla zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="c1421-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="c1421-108">Można użyć ograniczeń wyrażenia lub ograniczeń tabeli, w zależności od preferencji dotyczących tworzenia ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="c1421-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="c1421-109">Ograniczenia służą do kontroli wartości atrybutów, które można wybrać podczas konfigurowania produktów dla zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="c1421-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="c1421-110">Można użyć ograniczeń wyrażenia lub ograniczeń tabeli, w zależności od preferencji dotyczących tworzenia ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="c1421-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="c1421-111">Czym są ograniczenia wyrażenia?</span><span class="sxs-lookup"><span data-stu-id="c1421-111">What are expression constraints?</span></span>
<span data-ttu-id="c1421-112">Ograniczenia wyrażenia charakteryzują się wyrażeniem zawierającym operatory logiczne i arytmetycznego oraz funkcje.</span><span class="sxs-lookup"><span data-stu-id="c1421-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="c1421-113">Ograniczenie wyrażenia jest przeznaczone dla określonego składnika w modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c1421-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="c1421-114">Nie można ponownie zastosować lub współużytkować go z innym składnikiem.</span><span class="sxs-lookup"><span data-stu-id="c1421-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="c1421-115">Jednakże, ograniczenia wyrażenia dla składnika mogą odwoływać się do atrybutów składników podrzędnych dla składników.</span><span class="sxs-lookup"><span data-stu-id="c1421-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="c1421-116">Czym są ograniczenia tabeli?</span><span class="sxs-lookup"><span data-stu-id="c1421-116">What are table constraints?</span></span>
<span data-ttu-id="c1421-117">Ograniczenia tabeli to listy kombinacji wartości, które są dozwolone dla atrybutów podczas konfigurowania produktu.</span><span class="sxs-lookup"><span data-stu-id="c1421-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="c1421-118">Definicje ograniczeń tabeli mogą być używane ogólnie.</span><span class="sxs-lookup"><span data-stu-id="c1421-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="c1421-119">Podczas tworzenia ograniczenia tabeli dla składnika w modelu konfiguracji produktu, należy wybrać definicję ograniczenia tabeli.</span><span class="sxs-lookup"><span data-stu-id="c1421-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="c1421-120">Aby utworzyć kombinacje, które są dozwolone, należy dodać atrybuty określonych typów do składników.</span><span class="sxs-lookup"><span data-stu-id="c1421-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="c1421-121">Każdy typ atrybutu ma określoną wartość.</span><span class="sxs-lookup"><span data-stu-id="c1421-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="c1421-122">Przykład ograniczenia tabeli</span><span class="sxs-lookup"><span data-stu-id="c1421-122">Example of a table constraint</span></span>

<span data-ttu-id="c1421-123">Ten przykład pokazuje, jak można ograniczyć konfigurację głośnika do określonych wykończeń i maskownic.</span><span class="sxs-lookup"><span data-stu-id="c1421-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="c1421-124">Pierwsza tabela pokazuje wykończenia i maskownice powszechnie dostępnych dla konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="c1421-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="c1421-125">Wartości są zdefiniowane dla atrybutów typu **Wykończenia** i **Maskownica**.</span><span class="sxs-lookup"><span data-stu-id="c1421-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="c1421-126">Typ atrybutu</span><span class="sxs-lookup"><span data-stu-id="c1421-126">Attribute type</span></span> | <span data-ttu-id="c1421-127">Wartości</span><span class="sxs-lookup"><span data-stu-id="c1421-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="c1421-128">Wykończenie</span><span class="sxs-lookup"><span data-stu-id="c1421-128">Cabinet finish</span></span> | <span data-ttu-id="c1421-129">Czarny, Dąb, Rosewood, Biały</span><span class="sxs-lookup"><span data-stu-id="c1421-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="c1421-130">Maskownica</span><span class="sxs-lookup"><span data-stu-id="c1421-130">Front grill</span></span>    | <span data-ttu-id="c1421-131">Czarny, Metal, Biały</span><span class="sxs-lookup"><span data-stu-id="c1421-131">Black, Metal, White</span></span>         |

<span data-ttu-id="c1421-132">Następna tabela przedstawia kombinacje, które są definiowane przez ograniczenie tabeli **Kolor i wykończenie**.</span><span class="sxs-lookup"><span data-stu-id="c1421-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="c1421-133">Za pomocą tego ograniczenia tabeli można skonfigurować głośnik w dębowym wykończeniem i czarną maskownicą, wykończeniem Rodewood i białą maskownicą itd.</span><span class="sxs-lookup"><span data-stu-id="c1421-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="c1421-134">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="c1421-134">Finish</span></span>         | <span data-ttu-id="c1421-135">Maskownica</span><span class="sxs-lookup"><span data-stu-id="c1421-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="c1421-136">Dąb</span><span class="sxs-lookup"><span data-stu-id="c1421-136">Oak</span></span>            | <span data-ttu-id="c1421-137">Czarny</span><span class="sxs-lookup"><span data-stu-id="c1421-137">Black</span></span>                       |
| <span data-ttu-id="c1421-138">Rosewood</span><span class="sxs-lookup"><span data-stu-id="c1421-138">Rosewood</span></span>       | <span data-ttu-id="c1421-139">Biały</span><span class="sxs-lookup"><span data-stu-id="c1421-139">White</span></span>                       |
| <span data-ttu-id="c1421-140">Biały</span><span class="sxs-lookup"><span data-stu-id="c1421-140">White</span></span>          | <span data-ttu-id="c1421-141">Czarny</span><span class="sxs-lookup"><span data-stu-id="c1421-141">Black</span></span>                       |
| <span data-ttu-id="c1421-142">Biały</span><span class="sxs-lookup"><span data-stu-id="c1421-142">White</span></span>          | <span data-ttu-id="c1421-143">Biały</span><span class="sxs-lookup"><span data-stu-id="c1421-143">White</span></span>                       |
| <span data-ttu-id="c1421-144">Czarny</span><span class="sxs-lookup"><span data-stu-id="c1421-144">Black</span></span>          | <span data-ttu-id="c1421-145">Czarny</span><span class="sxs-lookup"><span data-stu-id="c1421-145">Black</span></span>                       |
| <span data-ttu-id="c1421-146">Czarny</span><span class="sxs-lookup"><span data-stu-id="c1421-146">Black</span></span>          | <span data-ttu-id="c1421-147">Metal</span><span class="sxs-lookup"><span data-stu-id="c1421-147">Metal</span></span>                       | 

<span data-ttu-id="c1421-148">Można tworzyć ograniczenia tabeli zdefiniowane przez użytkownika lub przez system.</span><span class="sxs-lookup"><span data-stu-id="c1421-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="c1421-149">Aby uzyskać więcej informacji, zobacz [Ograniczenia tabeli zdefiniowane przez użytkownika lub przez system](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="c1421-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="c1421-150">Jakiej składni należy używać w celu zapisywania ograniczeń?</span><span class="sxs-lookup"><span data-stu-id="c1421-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="c1421-151">Trzeba zapisać ograniczenia za pomocą składni Optimization Modeling Language (OML).</span><span class="sxs-lookup"><span data-stu-id="c1421-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="c1421-152">System używa narzędzia Microsoft Solver Foundation do rozwiązywania ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="c1421-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="c1421-153">Z których ograniczeń należy korzystać: ograniczeń wyrażenia czy ograniczeń tabeli?</span><span class="sxs-lookup"><span data-stu-id="c1421-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="c1421-154">Można użyć albo ograniczeń wyrażenia, albo ograniczeń tabeli, w zależności od preferencji dotyczących ograniczeń.</span><span class="sxs-lookup"><span data-stu-id="c1421-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="c1421-155">Ograniczenie tabeli jest tworzone jako macierz, podczas gdy ograniczenie wyrażenia to indywidualna instrukcja.</span><span class="sxs-lookup"><span data-stu-id="c1421-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="c1421-156">Podczas konfigurowania produktu, nie ma znaczenia, jaki rodzaj ograniczenia jest używany.</span><span class="sxs-lookup"><span data-stu-id="c1421-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="c1421-157">W poniższym przykładzie pokazano, jak te dwie metody się od siebie różnią.</span><span class="sxs-lookup"><span data-stu-id="c1421-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="c1421-158">Jeśli konfigurujesz produkt za pomocą następujących ustawień ograniczenia, dozwolone są następujące kombinacje:</span><span class="sxs-lookup"><span data-stu-id="c1421-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="c1421-159">Produkt w kolorze Czarny i rozmiarze 30 lub 50</span><span class="sxs-lookup"><span data-stu-id="c1421-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="c1421-160">Produkt w kolorze Czerwony i rozmiarze 20</span><span class="sxs-lookup"><span data-stu-id="c1421-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="c1421-161">Konfiguracja ograniczenia tabeli</span><span class="sxs-lookup"><span data-stu-id="c1421-161">Table constraint setup</span></span>

| <span data-ttu-id="c1421-162">Kolor</span><span class="sxs-lookup"><span data-stu-id="c1421-162">Color</span></span> | <span data-ttu-id="c1421-163">Rozmiar</span><span class="sxs-lookup"><span data-stu-id="c1421-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="c1421-164">Czarny</span><span class="sxs-lookup"><span data-stu-id="c1421-164">Black</span></span> | <span data-ttu-id="c1421-165">30</span><span class="sxs-lookup"><span data-stu-id="c1421-165">30</span></span>   |
| <span data-ttu-id="c1421-166">Czarny</span><span class="sxs-lookup"><span data-stu-id="c1421-166">Black</span></span> | <span data-ttu-id="c1421-167">50</span><span class="sxs-lookup"><span data-stu-id="c1421-167">50</span></span>   |
| <span data-ttu-id="c1421-168">Czerwony</span><span class="sxs-lookup"><span data-stu-id="c1421-168">Red</span></span>   | <span data-ttu-id="c1421-169">20</span><span class="sxs-lookup"><span data-stu-id="c1421-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="c1421-170">Ustawienia ograniczenia wyrażenia</span><span class="sxs-lookup"><span data-stu-id="c1421-170">Expression constraint setup</span></span>

<span data-ttu-id="c1421-171">(Kolor == "Czarny" & (rozmiar == "30" | rozmiar == "50")) | (kolor == "Czerwony" & rozmiar = "20")</span><span class="sxs-lookup"><span data-stu-id="c1421-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="c1421-172">Czy używać operatorów czy notacji infix podczas zapisywania ograniczeń wyrażenia?</span><span class="sxs-lookup"><span data-stu-id="c1421-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="c1421-173">Możesz zapisać ograniczeń wyrażenia przy użyciu dostępnych operatorów prefiksu lub przy użyciu notacji infix.</span><span class="sxs-lookup"><span data-stu-id="c1421-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="c1421-174">Dla operatorów **Min**, **Max** i **Abs** nie można użyć notacji infix.</span><span class="sxs-lookup"><span data-stu-id="c1421-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="c1421-175">Operatory te są dołączane jako operacje standardowe w większości języków programowania.</span><span class="sxs-lookup"><span data-stu-id="c1421-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="c1421-176">Jakich operatorów i notacji infix należy używać podczas zapisywania ograniczeń wyrażenia?</span><span class="sxs-lookup"><span data-stu-id="c1421-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="c1421-177">W poniższych tabelach znajdują się listy operatorów i notacji infix, których można używać podczas zapisywania ograniczenia wyrażenia dla składnika w modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c1421-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="c1421-178">W przykładach w tym pierwszej tabeli zobacz jak zapisać wyrażenie przy użyciu notacji infix lub operatorów.</span><span class="sxs-lookup"><span data-stu-id="c1421-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1421-179">Operator</span><span class="sxs-lookup"><span data-stu-id="c1421-179">Operator</span></span></th>
<th><span data-ttu-id="c1421-180">Opis</span><span class="sxs-lookup"><span data-stu-id="c1421-180">Description</span></span></th>
<th><span data-ttu-id="c1421-181">Składnia</span><span class="sxs-lookup"><span data-stu-id="c1421-181">Syntax</span></span></th>
<th><span data-ttu-id="c1421-182">Przykłady</span><span class="sxs-lookup"><span data-stu-id="c1421-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c1421-183">Implies</span><span class="sxs-lookup"><span data-stu-id="c1421-183">Implies</span></span></td>
<td><span data-ttu-id="c1421-184">Jest to wartość true, jeśli pierwszy warunek nie jest spełniony, drugi warunek jest prawdziwy, lub oba są.</span><span class="sxs-lookup"><span data-stu-id="c1421-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="c1421-185">Implies[a, b], infix: a -: b</span><span class="sxs-lookup"><span data-stu-id="c1421-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="c1421-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="c1421-187"><strong>Notacja Infix:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="c1421-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c1421-188">i</span><span class="sxs-lookup"><span data-stu-id="c1421-188">And</span></span></td>
<td><span data-ttu-id="c1421-189">Jest to możliwe tylko wtedy, gdy są spełnione wszystkie warunki.</span><span class="sxs-lookup"><span data-stu-id="c1421-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="c1421-190">Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>True</strong>.</span><span class="sxs-lookup"><span data-stu-id="c1421-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="c1421-191">And[args], infix: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="c1421-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="c1421-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="c1421-193"><strong>Notacja Infix:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="c1421-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c1421-194">lub</span><span class="sxs-lookup"><span data-stu-id="c1421-194">Or</span></span></td>
<td><span data-ttu-id="c1421-195">Wartość jest True, jeśli jest spełniony dowolny z warunków.</span><span class="sxs-lookup"><span data-stu-id="c1421-195">This is true if any condition is true.</span></span> <span data-ttu-id="c1421-196">Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>False</strong>.</span><span class="sxs-lookup"><span data-stu-id="c1421-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="c1421-197">Or[args], infix: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="c1421-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="c1421-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="c1421-199"><strong>Notacja Infix:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="c1421-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c1421-200">Plus</span><span class="sxs-lookup"><span data-stu-id="c1421-200">Plus</span></span></td>
<td><span data-ttu-id="c1421-201">Sumuje warunki.</span><span class="sxs-lookup"><span data-stu-id="c1421-201">This sums its conditions.</span></span> <span data-ttu-id="c1421-202">Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="c1421-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="c1421-203">Plus[args], infix: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="c1421-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="c1421-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="c1421-205"><strong>Notacja infix:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="c1421-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c1421-206">Minus</span><span class="sxs-lookup"><span data-stu-id="c1421-206">Minus</span></span></td>
<td><span data-ttu-id="c1421-207">Zmienia to znak argumentu.</span><span class="sxs-lookup"><span data-stu-id="c1421-207">This negates its argument.</span></span> <span data-ttu-id="c1421-208">To musi mieć dokładnie jeden warunek.</span><span class="sxs-lookup"><span data-stu-id="c1421-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="c1421-209">Minus[expr], infix: -expr</span><span class="sxs-lookup"><span data-stu-id="c1421-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-210"><strong>Operator:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="c1421-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="c1421-211"><strong>Notacja infix:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="c1421-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c1421-212">Abs</span><span class="sxs-lookup"><span data-stu-id="c1421-212">Abs</span></span></td>
<td><span data-ttu-id="c1421-213">Wartość bezwzględna dla warunku.</span><span class="sxs-lookup"><span data-stu-id="c1421-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="c1421-214">To musi mieć dokładnie jeden warunek.</span><span class="sxs-lookup"><span data-stu-id="c1421-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="c1421-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="c1421-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="c1421-216"><strong>Operator:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="c1421-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c1421-217">Czasy</span><span class="sxs-lookup"><span data-stu-id="c1421-217">Times</span></span></td>
<td><span data-ttu-id="c1421-218">Produkt jego warunków.</span><span class="sxs-lookup"><span data-stu-id="c1421-218">This takes the product of its conditions.</span></span> <span data-ttu-id="c1421-219">Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="c1421-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="c1421-220">Times[args], infix: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="c1421-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-221"><strong>Operator:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="c1421-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="c1421-222"><strong>Notacja infix:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="c1421-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c1421-223">Potęga</span><span class="sxs-lookup"><span data-stu-id="c1421-223">Power</span></span></td>
<td><span data-ttu-id="c1421-224">Wartość wykładnicza.</span><span class="sxs-lookup"><span data-stu-id="c1421-224">This takes an exponential.</span></span> <span data-ttu-id="c1421-225">Potęgowanie od prawej do lewej.</span><span class="sxs-lookup"><span data-stu-id="c1421-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="c1421-226">(Innymi słowy jest łączna z prawej). Dlatego <strong>Power[a, b, c]</strong> jest równoznaczne z <strong>Power[a, Power[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="c1421-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="c1421-227">Operatora <strong>Power</strong> można użyć tylko pod warunkiem, że wykładnik jest dodatnią wartością stałą.</span><span class="sxs-lookup"><span data-stu-id="c1421-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="c1421-228">Power[args], infix: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="c1421-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-229"><strong>Operator:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="c1421-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="c1421-230"><strong>Notacja infix:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="c1421-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c1421-231">Maks.</span><span class="sxs-lookup"><span data-stu-id="c1421-231">Max</span></span></td>
<td><span data-ttu-id="c1421-232">Opcja zapewnia największy warunek.</span><span class="sxs-lookup"><span data-stu-id="c1421-232">This produces the largest condition.</span></span> <span data-ttu-id="c1421-233">Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="c1421-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="c1421-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="c1421-234">Max[args]</span></span></td>
<td><span data-ttu-id="c1421-235"><strong>Operator:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="c1421-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c1421-236">Min.</span><span class="sxs-lookup"><span data-stu-id="c1421-236">Min</span></span></td>
<td><span data-ttu-id="c1421-237">Opcja zapewnia najmniejszy warunek.</span><span class="sxs-lookup"><span data-stu-id="c1421-237">This produces the smallest condition.</span></span> <span data-ttu-id="c1421-238">Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>Infinity</strong>.</span><span class="sxs-lookup"><span data-stu-id="c1421-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="c1421-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="c1421-239">Min[args]</span></span></td>
<td><span data-ttu-id="c1421-240"><strong>Operator:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="c1421-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c1421-241">Nie</span><span class="sxs-lookup"><span data-stu-id="c1421-241">Not</span></span></td>
<td><span data-ttu-id="c1421-242">Daje logiczną odwrotność danego warunku.</span><span class="sxs-lookup"><span data-stu-id="c1421-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="c1421-243">To musi mieć dokładnie jeden warunek.</span><span class="sxs-lookup"><span data-stu-id="c1421-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="c1421-244">Not[expr], infix: !expr</span><span class="sxs-lookup"><span data-stu-id="c1421-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="c1421-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="c1421-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="c1421-246"><strong>Notacja infix:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="c1421-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c1421-247">W następnej tabeli przedstawiono przykłady jak zapisać notację infix.</span><span class="sxs-lookup"><span data-stu-id="c1421-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="c1421-248">Notacja infix:</span><span class="sxs-lookup"><span data-stu-id="c1421-248">Infix notation</span></span>   |                                          <span data-ttu-id="c1421-249">opis</span><span class="sxs-lookup"><span data-stu-id="c1421-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="c1421-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="c1421-250">x + y + z</span></span>     |                                           <span data-ttu-id="c1421-251">Dodanie</span><span class="sxs-lookup"><span data-stu-id="c1421-251">Addition</span></span>                                            |
|    <span data-ttu-id="c1421-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="c1421-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="c1421-253">Mnożenie</span><span class="sxs-lookup"><span data-stu-id="c1421-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="c1421-254">x - y</span><span class="sxs-lookup"><span data-stu-id="c1421-254">x - y</span></span>       | <span data-ttu-id="c1421-255">Odejmowanie binarne jest tłumaczona tak samo, jak binarnego dodawanie z zanegowaniem drugiego.</span><span class="sxs-lookup"><span data-stu-id="c1421-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="c1421-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="c1421-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="c1421-257">Potęgowanie z łącznością do prawej</span><span class="sxs-lookup"><span data-stu-id="c1421-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="c1421-258">!x</span><span class="sxs-lookup"><span data-stu-id="c1421-258">!x</span></span>         |                                          <span data-ttu-id="c1421-259">Wartość logiczna not</span><span class="sxs-lookup"><span data-stu-id="c1421-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="c1421-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="c1421-260">x -: y</span></span>       |                                      <span data-ttu-id="c1421-261">Logiczna implikacja</span><span class="sxs-lookup"><span data-stu-id="c1421-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="c1421-262">x</span><span class="sxs-lookup"><span data-stu-id="c1421-262">x</span></span>         |                                               <span data-ttu-id="c1421-263">y</span><span class="sxs-lookup"><span data-stu-id="c1421-263">y</span></span>                                               |
|     <span data-ttu-id="c1421-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="c1421-264">x & y & z</span></span>     |                                          <span data-ttu-id="c1421-265">Wartość logiczna and</span><span class="sxs-lookup"><span data-stu-id="c1421-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="c1421-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="c1421-266">x == y == z</span></span>    |                                           <span data-ttu-id="c1421-267">Równość</span><span class="sxs-lookup"><span data-stu-id="c1421-267">Equality</span></span>                                            |
|    <span data-ttu-id="c1421-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="c1421-268">x != y != z</span></span>    |                                           <span data-ttu-id="c1421-269">Określone</span><span class="sxs-lookup"><span data-stu-id="c1421-269">Distinct</span></span>                                            |
|  <span data-ttu-id="c1421-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="c1421-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="c1421-271">Mniejsze niż</span><span class="sxs-lookup"><span data-stu-id="c1421-271">Less than</span></span>                                           |
|  <span data-ttu-id="c1421-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="c1421-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="c1421-273">Większe niż</span><span class="sxs-lookup"><span data-stu-id="c1421-273">Greater than</span></span>                                          |
| <span data-ttu-id="c1421-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="c1421-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="c1421-275">Mniejsze lub równe</span><span class="sxs-lookup"><span data-stu-id="c1421-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="c1421-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="c1421-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="c1421-277">Większe lub równe</span><span class="sxs-lookup"><span data-stu-id="c1421-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="c1421-278">(x)</span><span class="sxs-lookup"><span data-stu-id="c1421-278">(x)</span></span>        |                           <span data-ttu-id="c1421-279">Nawiasy zastępują domyślny priorytet.</span><span class="sxs-lookup"><span data-stu-id="c1421-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="c1421-280">Dlaczego moje ograniczenia wyrażeń nie przechodzą pomyślnie sprawdzania poprawności?</span><span class="sxs-lookup"><span data-stu-id="c1421-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="c1421-281">Nie można używać zarezerwowanych słów kluczowych jako nazwy zamiennej dla atrybutów, komponentów czy podskładniki w modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c1421-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span> <span data-ttu-id="c1421-282">Oto lista zastrzeżonych słów kluczowych, których nie można używać:</span><span class="sxs-lookup"><span data-stu-id="c1421-282">Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="c1421-283">Pułap</span><span class="sxs-lookup"><span data-stu-id="c1421-283">Ceiling</span></span>
-   <span data-ttu-id="c1421-284">Element</span><span class="sxs-lookup"><span data-stu-id="c1421-284">Element</span></span>
-   <span data-ttu-id="c1421-285">Taka sama</span><span class="sxs-lookup"><span data-stu-id="c1421-285">Equal</span></span>
-   <span data-ttu-id="c1421-286">Podłoga</span><span class="sxs-lookup"><span data-stu-id="c1421-286">Floor</span></span>
-   <span data-ttu-id="c1421-287">Jeśli</span><span class="sxs-lookup"><span data-stu-id="c1421-287">If</span></span>
-   <span data-ttu-id="c1421-288">Mniejsze</span><span class="sxs-lookup"><span data-stu-id="c1421-288">Less</span></span>
-   <span data-ttu-id="c1421-289">Większe</span><span class="sxs-lookup"><span data-stu-id="c1421-289">Greater</span></span>
-   <span data-ttu-id="c1421-290">Implies</span><span class="sxs-lookup"><span data-stu-id="c1421-290">Implies</span></span>
-   <span data-ttu-id="c1421-291">Dziennik</span><span class="sxs-lookup"><span data-stu-id="c1421-291">Log</span></span>
-   <span data-ttu-id="c1421-292">Maksimum</span><span class="sxs-lookup"><span data-stu-id="c1421-292">Max</span></span>
-   <span data-ttu-id="c1421-293">Minimum</span><span class="sxs-lookup"><span data-stu-id="c1421-293">Min</span></span>
-   <span data-ttu-id="c1421-294">Minus</span><span class="sxs-lookup"><span data-stu-id="c1421-294">Minus</span></span>
-   <span data-ttu-id="c1421-295">Plus</span><span class="sxs-lookup"><span data-stu-id="c1421-295">Plus</span></span>
-   <span data-ttu-id="c1421-296">Moc</span><span class="sxs-lookup"><span data-stu-id="c1421-296">Power</span></span>
-   <span data-ttu-id="c1421-297">Czasy</span><span class="sxs-lookup"><span data-stu-id="c1421-297">Times</span></span>
-   <span data-ttu-id="c1421-298">Przedział</span><span class="sxs-lookup"><span data-stu-id="c1421-298">Slot</span></span>
-   <span data-ttu-id="c1421-299">Model</span><span class="sxs-lookup"><span data-stu-id="c1421-299">Model</span></span>
-   <span data-ttu-id="c1421-300">Decyzja</span><span class="sxs-lookup"><span data-stu-id="c1421-300">Decision</span></span>
-   <span data-ttu-id="c1421-301">Cel</span><span class="sxs-lookup"><span data-stu-id="c1421-301">Goal</span></span>


## <a name="additional-resources"></a><span data-ttu-id="c1421-302">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c1421-302">Additional resources</span></span>

[<span data-ttu-id="c1421-303">Tworzenie ograniczenia wyrażenia</span><span class="sxs-lookup"><span data-stu-id="c1421-303">Create an expression constraint</span></span>](tasks/add-expression-constraint-product-configuration-model.md)

[<span data-ttu-id="c1421-304">Dodawanie obliczenia do modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="c1421-304">Add a calculation to a product configuration model</span></span>](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]