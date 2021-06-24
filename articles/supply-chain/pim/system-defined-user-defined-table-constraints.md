---
title: Ograniczenia tabeli zdefiniowane przez użytkownika lub przez system
description: Ten artykuł wyjaśnia dwa rodzaje ograniczeń tabel dla składników w modelu konfiguracji produktu — zdefiniowane przez użytkownika i zdefiniowane przez system. Ograniczenia tabel reprezentują macierze dozwolonych kombinacji atrybutów, gdzie każdy wiersz definiuje jeden zestaw możliwych wartości atrybutów.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35ea5b97708272edf50f09d892088bcd3e07402d
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187974"
---
# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="c6055-104">Ograniczenia tabeli zdefiniowane przez użytkownika lub przez system</span><span class="sxs-lookup"><span data-stu-id="c6055-104">System-defined and user-defined table constraints</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c6055-105">Ten artykuł wyjaśnia dwa rodzaje ograniczeń tabel dla składników w modelu konfiguracji produktu — zdefiniowane przez użytkownika i zdefiniowane przez system.</span><span class="sxs-lookup"><span data-stu-id="c6055-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="c6055-106">Ograniczenia tabel reprezentują macierze dozwolonych kombinacji atrybutów, gdzie każdy wiersz definiuje jeden zestaw możliwych wartości atrybutów.</span><span class="sxs-lookup"><span data-stu-id="c6055-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="c6055-107">Powiązane tabele przedstawiają macierze kombinacji atrybutów, które są dozwolone dla składników w modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c6055-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="c6055-108">Każdy wiersz w tabeli definiuje jeden zestaw atrybutów możliwych wartości.</span><span class="sxs-lookup"><span data-stu-id="c6055-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="c6055-109">Można zadeklarować dwa typy ograniczeń w modelu konfiguracji produktu:</span><span class="sxs-lookup"><span data-stu-id="c6055-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="c6055-110">**Ograniczenia wyrażenia** — można utworzyć wyrażenie, które określa relacje między atrybutami, aby zagwarantować, że podczas konfigurowania produktu mogą być wybrane tylko zgodne wartości.</span><span class="sxs-lookup"><span data-stu-id="c6055-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="c6055-111">**Powiązane tabele** — można utworzyć tabelę, która określa wszystkie kombinacje, które są dozwolone dla określonego zestawu atrybutów.</span><span class="sxs-lookup"><span data-stu-id="c6055-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="c6055-112">Dostępne są dwa typy powiązanych tabel: zdefiniowane przez użytkownika i zdefiniowane przez system.</span><span class="sxs-lookup"><span data-stu-id="c6055-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="c6055-113">Ten artykuł opisuje powiązane tabeli zdefiniowane przez użytkownika i przez system dla składników w modeli konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c6055-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="c6055-114">Powiązane tabele zdefiniowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="c6055-114">User-defined table constraints</span></span>
<span data-ttu-id="c6055-115">Powiązane tabele zdefiniowane przez użytkownika to typ macierzy używany do opisywania kombinacji dla wartości atrybutów, które są zdefiniowane przez typy atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c6055-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="c6055-116">Na przykład jeśli produkujesz głośniki, możesz w powiązanych tabelach zdefiniowanych przez użytkownika możesz umieścić kolumny dla wykończenia i maskownicy.</span><span class="sxs-lookup"><span data-stu-id="c6055-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="c6055-117">Typ atrybutu dla wykończenia ma cztery wartości a typ atrybutu dla maskownicy ma trzy możliwe wartości.</span><span class="sxs-lookup"><span data-stu-id="c6055-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="c6055-118">Z tego powodu, jeśli ograniczenia nie są używane, jest 4 x 3 = 12 możliwych kombinacji.</span><span class="sxs-lookup"><span data-stu-id="c6055-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="c6055-119">Jednak w tym przykładzie tylko sześć kombinacji jest dozwolonych, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c6055-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="c6055-120">Te informacje są wyświetlane na karcie **Dozwolone kombinacje** na stronie **Edycja powiązanych tabel**.</span><span class="sxs-lookup"><span data-stu-id="c6055-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="c6055-121">Wykończenie</span><span class="sxs-lookup"><span data-stu-id="c6055-121">Cabinet finish</span></span> | <span data-ttu-id="c6055-122">Maskownica</span><span class="sxs-lookup"><span data-stu-id="c6055-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="c6055-123">Czarny</span><span class="sxs-lookup"><span data-stu-id="c6055-123">Black</span></span>          | <span data-ttu-id="c6055-124">Czarny</span><span class="sxs-lookup"><span data-stu-id="c6055-124">Black</span></span>       |
| <span data-ttu-id="c6055-125">Czarny</span><span class="sxs-lookup"><span data-stu-id="c6055-125">Black</span></span>          | <span data-ttu-id="c6055-126">Metal</span><span class="sxs-lookup"><span data-stu-id="c6055-126">Metal</span></span>       |
| <span data-ttu-id="c6055-127">Dąb</span><span class="sxs-lookup"><span data-stu-id="c6055-127">Oak</span></span>            | <span data-ttu-id="c6055-128">Czarny</span><span class="sxs-lookup"><span data-stu-id="c6055-128">Black</span></span>       |
| <span data-ttu-id="c6055-129">Rosewood</span><span class="sxs-lookup"><span data-stu-id="c6055-129">Rosewood</span></span>       | <span data-ttu-id="c6055-130">Biały</span><span class="sxs-lookup"><span data-stu-id="c6055-130">White</span></span>       |
| <span data-ttu-id="c6055-131">Biały</span><span class="sxs-lookup"><span data-stu-id="c6055-131">White</span></span>          | <span data-ttu-id="c6055-132">Czarny</span><span class="sxs-lookup"><span data-stu-id="c6055-132">Black</span></span>       |
| <span data-ttu-id="c6055-133">Biały</span><span class="sxs-lookup"><span data-stu-id="c6055-133">White</span></span>          | <span data-ttu-id="c6055-134">Biały</span><span class="sxs-lookup"><span data-stu-id="c6055-134">White</span></span>       |

<span data-ttu-id="c6055-135">Powiązane tabele zdefiniowane przez użytkownika są definiowane przez statyczne danych wejściowych tabeli, co działa tak samo jak w przypadku ograniczenia wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="c6055-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="c6055-136">Jeśli używasz powiązanej tabeli zdefiniowanej przez użytkownika, ma to tę zaletę, że tabele są często tworzenie, analiza i obsługa tabel jest często łatwiejsza niż długich ograniczenia wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="c6055-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="c6055-137">Powiązane tabele zdefiniowanych przez system</span><span class="sxs-lookup"><span data-stu-id="c6055-137">System-defined table constraints</span></span>
<span data-ttu-id="c6055-138">Powiązane tabele zdefiniowane przez system tworzą dynamiczne mapowanie między typem atrybutem i polem w tabeli.</span><span class="sxs-lookup"><span data-stu-id="c6055-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="c6055-139">Gdy powiązana tabela zdefiniowana przez system jest uwzględniana w modelu konfiguracji produktu, mapowanie gwarantuje, że dane w tabeli są wyświetlane zamiast wartości typu atrybutu.</span><span class="sxs-lookup"><span data-stu-id="c6055-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="c6055-140">Wynikiem jest ograniczenie dynamiczne, ponieważ powiązane tabele mogą być modyfikowane (np. przez inne moduły).</span><span class="sxs-lookup"><span data-stu-id="c6055-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="c6055-141">Podczas tworzenia powiązanych tabel zdefiniowanych przez system wybiera się tabelę, opcjonalnie definiuje się kwerendę do użycia, a następnie kojarzy się typy atrybutów z polami w wybranej tabeli.</span><span class="sxs-lookup"><span data-stu-id="c6055-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="c6055-142">Typy pól muszą pasować do typów atrybutów.</span><span class="sxs-lookup"><span data-stu-id="c6055-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="c6055-143">Zanim ograniczenie tabeli będzie mogło zacząć obowiązywać w modelu konfiguracji produktu, należy je dodać do ograniczenia jednego ze składników modelu.</span><span class="sxs-lookup"><span data-stu-id="c6055-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="c6055-144">Procedura obejmuje utworzenie nowego ograniczenia, wybranie typu ograniczenia tabeli, a następnie wybranie definicji ograniczenia tabeli, która ma być używana.</span><span class="sxs-lookup"><span data-stu-id="c6055-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="c6055-145">Ponadto wszystkie pola w powiązanych tabelach muszą być mapowane do atrybutów w modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="c6055-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c6055-146">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c6055-146">Additional resources</span></span>

[<span data-ttu-id="c6055-147">Omówienie modeli konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="c6055-147">Product configuration models overview</span></span>](product-configuration-models.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]