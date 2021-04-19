---
title: Obliczenia na potrzeby modelu konfiguracji produktu
description: W tym temacie opisano sposób tworzenia obliczeń dla atrybutów w modelu konfiguracji produktu
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829625"
---
# <a name="product-configuration-model-calculations"></a><span data-ttu-id="419f6-103">Obliczenia na potrzeby modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="419f6-103">Product configuration model calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="419f6-104">W tym temacie opisano sposób tworzenia obliczeń dla atrybutów w modelu konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="419f6-104">This topic describes how to create calculations for attributes in a product configuration model.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="419f6-105">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="419f6-105">Prerequisites</span></span>

<span data-ttu-id="419f6-106">Obliczeń są używane w modelu konfiguracji produktu do obliczania wartości konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="419f6-106">Calculations are used in a product configuration model to calculate the configuration values for a product.</span></span> <span data-ttu-id="419f6-107">Aby można było rozpocząć konfigurowanie obliczeń, musi istnieć powiązany model konfiguracji produktu.</span><span class="sxs-lookup"><span data-stu-id="419f6-107">Before you can start to set up calculations, the related product configuration model must exist.</span></span> <span data-ttu-id="419f6-108">Aby uzyskać przegląd procesu konfiguracji dla modeli konfiguracji i powiązanych zadań, zobacz temat [Konfigurowanie modelu konfiguracji produktu](set-up-maintain-product-configuration-model.md).</span><span class="sxs-lookup"><span data-stu-id="419f6-108">For an overview of the setup process for configuration models and the related tasks, see [Set up a product configuration model](set-up-maintain-product-configuration-model.md).</span></span>

## <a name="create-a-calculation"></a><span data-ttu-id="419f6-109">Tworzenie obliczenia</span><span class="sxs-lookup"><span data-stu-id="419f6-109">Create a calculation</span></span>

<span data-ttu-id="419f6-110">Obliczenie składa się z wyrażenia i atrybutu docelowego.</span><span class="sxs-lookup"><span data-stu-id="419f6-110">A calculation consists of an expression and a target attribute.</span></span> <span data-ttu-id="419f6-111">Aby uzyskać więcej informacji, zobacz [Obliczenia dla modeli produktu w konfiguracji — często zadawane pytania](calculate-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="419f6-111">For more information, see [Calculations for product configuration models FAQ](calculate-product-configuration-models.md).</span></span>

<span data-ttu-id="419f6-112">Aby utworzyć obliczenie dla istniejącego modelu produktu, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="419f6-112">To create a calculation for an existing product model, follow these steps.</span></span>

1. <span data-ttu-id="419f6-113">Kliknij kolejno opcje **Zarządzanie informacjami o produktach \> Wspólne \> Modele konfiguracji produktu**.</span><span class="sxs-lookup"><span data-stu-id="419f6-113">Go to **Product information management \> Common \> Product configuration models**.</span></span>
1. <span data-ttu-id="419f6-114">Otwórz model konfiguracji produktu, a następnie kliknij przycisk **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="419f6-114">Open a product configuration model, and then select **Edit**.</span></span>
1. <span data-ttu-id="419f6-115">Na skróconej karcie **Obliczenia** wybierz opcję **Dodaj**, aby dodać obliczenia, a następnie określ dla niego następujące pola:</span><span class="sxs-lookup"><span data-stu-id="419f6-115">On the **Calculations** FastTab, select **Add** to add a calculation, and then set the following fields:</span></span>

    - <span data-ttu-id="419f6-116">**Nazwa** – wprowadź nazwę dla obliczeń.</span><span class="sxs-lookup"><span data-stu-id="419f6-116">**Name** – Enter a name for the calculation.</span></span>
    - <span data-ttu-id="419f6-117">**Opis** – wprowadź opis obliczeń.</span><span class="sxs-lookup"><span data-stu-id="419f6-117">**Description** – Enter a description of the calculation.</span></span>
    - <span data-ttu-id="419f6-118">**Atrybut docelowy** – wybierz atrybut, dla których są wykonywane obliczenia.</span><span class="sxs-lookup"><span data-stu-id="419f6-118">**Target attribute** – Select the attribute that you're making the calculation for.</span></span>

1. <span data-ttu-id="419f6-119">Wybierz polecenie **Edytuj wyrażenie**.</span><span class="sxs-lookup"><span data-stu-id="419f6-119">Select **Edit expression**.</span></span>
1. <span data-ttu-id="419f6-120">W oknie dialogowym **Wprowadzanie obliczenia** dodaj do wyrażenia wymagane atrybuty, operatory i wartości.</span><span class="sxs-lookup"><span data-stu-id="419f6-120">In the **Enter a calculation** dialog box, add the required attributes, operators, and values to the expression.</span></span> <span data-ttu-id="419f6-121">Aby uzyskać więcej informacji o tym, jak pracować z tymi elementami, zobacz temat [Ograniczenia wyrażenia i ograniczenia tabeli w modelach konfiguracji produktu](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="419f6-121">For more information about how to work with these elements, see [Expression constraints and table constraints in product configuration models](expression-constraints-table-constraints-product-configuration-models.md).</span></span>
1. <span data-ttu-id="419f6-122">Gdy wyrażenie jest gotowe, wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="419f6-122">When your expression is ready, select **OK**.</span></span>

## <a name="calculation-examples"></a><span data-ttu-id="419f6-123">Przykłady obliczeń</span><span class="sxs-lookup"><span data-stu-id="419f6-123">Calculation examples</span></span>

<span data-ttu-id="419f6-124">Ta sekcja zawiera kilka przykładów, które pokazują pracę obliczeń.</span><span class="sxs-lookup"><span data-stu-id="419f6-124">This section provides a few examples that show how calculations work.</span></span>

### <a name="example-1"></a><span data-ttu-id="419f6-125">Przykład 1</span><span class="sxs-lookup"><span data-stu-id="419f6-125">Example 1</span></span>

<span data-ttu-id="419f6-126">Atrybutem docelowym jest wartość logiczna, a obliczenia wykorzystują następujące wyrażenie warunkowe:</span><span class="sxs-lookup"><span data-stu-id="419f6-126">The target attribute is Boolean, and the calculation uses the following conditional expression:</span></span>

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

<span data-ttu-id="419f6-127">To wyrażenie zwróci wartość *Prawda* (True) do atrybutu docelowego, jeśli dziesiętny atrybut `decimalAttribute2` jest większy niż lub równy dziesiętnemu atrybutowi `decimalAttribute1`.</span><span class="sxs-lookup"><span data-stu-id="419f6-127">This expression returns a value of *True* to the target attribute if `decimalAttribute2` is greater than or equal to `decimalAttribute1`.</span></span> <span data-ttu-id="419f6-128">W przeciwnym wypadku zwraca ona wartość logiczną *Fałsz* (False).</span><span class="sxs-lookup"><span data-stu-id="419f6-128">Otherwise, it returns a value of *False*.</span></span>

### <a name="example-2"></a><span data-ttu-id="419f6-129">Przykład 2</span><span class="sxs-lookup"><span data-stu-id="419f6-129">Example 2</span></span>

<span data-ttu-id="419f6-130">W tym przykładzie jako atrybut docelowy jest używany atrybut tekstowy `textFixedList`.</span><span class="sxs-lookup"><span data-stu-id="419f6-130">This example uses the text attribute `textFixedList` as the target attribute.</span></span> <span data-ttu-id="419f6-131">Ten atrybut zawiera następującą stałą listę.</span><span class="sxs-lookup"><span data-stu-id="419f6-131">This attribute contains the following fixed list.</span></span>

| <span data-ttu-id="419f6-132">Wartość</span><span class="sxs-lookup"><span data-stu-id="419f6-132">Value</span></span> | <span data-ttu-id="419f6-133">Wartość zmiennej</span><span class="sxs-lookup"><span data-stu-id="419f6-133">Solver value</span></span> |
|---|---|
| <span data-ttu-id="419f6-134">A</span><span class="sxs-lookup"><span data-stu-id="419f6-134">A</span></span> | <span data-ttu-id="419f6-135">1a</span><span class="sxs-lookup"><span data-stu-id="419f6-135">1a</span></span> |
| <span data-ttu-id="419f6-136">mld</span><span class="sxs-lookup"><span data-stu-id="419f6-136">B</span></span> | <span data-ttu-id="419f6-137">2b</span><span class="sxs-lookup"><span data-stu-id="419f6-137">2b</span></span> |
| <span data-ttu-id="419f6-138">C</span><span class="sxs-lookup"><span data-stu-id="419f6-138">C</span></span> | <span data-ttu-id="419f6-139">2c</span><span class="sxs-lookup"><span data-stu-id="419f6-139">2c</span></span> |

<span data-ttu-id="419f6-140">Poniższy zrzut ekranu pokazuje, jak ustawienia tego atrybutu mogą wyglądać w systemie.</span><span class="sxs-lookup"><span data-stu-id="419f6-140">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="419f6-141">![Ustawienia typu atrybutu dla przykładu 2](media/model-calculations-example2.png "Ustawienia typu atrybutu dla przykładu 2")</span><span class="sxs-lookup"><span data-stu-id="419f6-141">![Attribute type settings for example 2](media/model-calculations-example2.png "Attribute type settings for example 2")</span></span>

<span data-ttu-id="419f6-142">Atrybut jest używany w następującym oświadczeniu warunkowym:</span><span class="sxs-lookup"><span data-stu-id="419f6-142">The attribute is used in the following conditional statement:</span></span>

`If[integerAttribute < 150, 0, 2]`

<span data-ttu-id="419f6-143">Jeśli `integerAttribute` jest mniejszy niż 150, instrukcja zwraca wartość tekstową pierwszego rekordu na stałej liście, *A*. W przeciwnym razie zwraca wartość tekstową trzeciego rekordu na stałej liście, *C*.</span><span class="sxs-lookup"><span data-stu-id="419f6-143">If `integerAttribute` is less than 150, this statement returns the text value of the first record in the fixed list, *A*. Otherwise, it returns the text value of the third record in the fixed list, *C*.</span></span>

> [!NOTE]
> <span data-ttu-id="419f6-144">Ustalona lista jest równoważna wyliczeniu od zera (wyliczeniu), a dostęp do jej wartości uzyskuje się za pomocą odpowiedniej liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="419f6-144">The fixed list is equivalent to a zero-based enumeration (enum), and its values are accessed by the appropriate integer value.</span></span> <span data-ttu-id="419f6-145">W związku z tym pierwsza stała wartość listy (*A*) zostanie dopasowana do wartości *0*, druga wartość (*B*) zostanie dopasowana do *1*, a trzecia wartość (*C*) zostanie dopasowana do *2*.</span><span class="sxs-lookup"><span data-stu-id="419f6-145">Therefore, the first fixed list value (*A*) is matched to *0*, the second value (*B*) is matched to *1*, and the third value (*C*) is matched to *2*.</span></span>

### <a name="example-3"></a><span data-ttu-id="419f6-146">Przykład 3</span><span class="sxs-lookup"><span data-stu-id="419f6-146">Example 3</span></span>

<span data-ttu-id="419f6-147">W tym przykładzie zastosowano atrybut docelowy `textFixedList` z poprzedniego przykładu.</span><span class="sxs-lookup"><span data-stu-id="419f6-147">This example uses the `textFixedList` target attribute from the previous example.</span></span> <span data-ttu-id="419f6-148">Używa również innego atrybutu tekstowego `textAttribute`, który zawiera następującą stałą listę.</span><span class="sxs-lookup"><span data-stu-id="419f6-148">It also uses another text attribute, `textAttribute`, that contains the following fixed list.</span></span>

| <span data-ttu-id="419f6-149">Wartość</span><span class="sxs-lookup"><span data-stu-id="419f6-149">Value</span></span> | <span data-ttu-id="419f6-150">Wartość zmiennej</span><span class="sxs-lookup"><span data-stu-id="419f6-150">Solver value</span></span> |
|---|---|
| <span data-ttu-id="419f6-151">AA</span><span class="sxs-lookup"><span data-stu-id="419f6-151">AA</span></span> | <span data-ttu-id="419f6-152">1aa</span><span class="sxs-lookup"><span data-stu-id="419f6-152">1aa</span></span> |
| <span data-ttu-id="419f6-153">BB</span><span class="sxs-lookup"><span data-stu-id="419f6-153">BB</span></span> | <span data-ttu-id="419f6-154">2bb</span><span class="sxs-lookup"><span data-stu-id="419f6-154">2bb</span></span> |

<span data-ttu-id="419f6-155">Poniższy zrzut ekranu pokazuje, jak ustawienia tego atrybutu mogą wyglądać w systemie.</span><span class="sxs-lookup"><span data-stu-id="419f6-155">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="419f6-156">![Ustawienia typu atrybutu dla przykładu 3](media/model-calculations-example3.png "Ustawienia typu atrybutu dla przykładu 3")</span><span class="sxs-lookup"><span data-stu-id="419f6-156">![Attribute type settings for example 3](media/model-calculations-example3.png "Attribute type settings for example 3")</span></span>

<span data-ttu-id="419f6-157">Wartość atrybutu `textFixedList` jest obliczana przy użyciu następującego zestawienia warunkowego:</span><span class="sxs-lookup"><span data-stu-id="419f6-157">The value for the `textFixedList` attribute is calculated by using the following conditional statement:</span></span>

`If[textAttribute == "1aa", 0, 2]`

<span data-ttu-id="419f6-158">Jeśli wartość `textAttribute` ma wartość zmiennej równą *1aa*,, to wyrażenie zwraca wartość tekstową pierwszego rekordu na stałej liście `textFixedList`, *A*. W przeciwnym razie zwraca wartość tekstową trzeciego rekordu na stałej liście `textFixedList`, *C*.</span><span class="sxs-lookup"><span data-stu-id="419f6-158">If the `textAttribute` value has a solver value that equals *1aa*, this expression returns the text value of the first record in the `textFixedList` fixed list, *A*. Otherwise, it returns the text value of the third record in the `textFixedList` fixed list, *C*.</span></span>

> [!NOTE]
> - <span data-ttu-id="419f6-159">Instrukcja warunkowa musi korzystać z wartości zmiennej atrybutu.</span><span class="sxs-lookup"><span data-stu-id="419f6-159">The conditional statement must use the solver value of the attribute.</span></span>
> - <span data-ttu-id="419f6-160">W obliczeniach mogą być używane tylko atrybuty tekstu stałej listy.</span><span class="sxs-lookup"><span data-stu-id="419f6-160">Only fixed-list text attributes can be used in calculations.</span></span>

## <a name="see-also"></a><span data-ttu-id="419f6-161">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="419f6-161">See also</span></span>

- [<span data-ttu-id="419f6-162">Obliczenia dla modeli produktu w konfiguracji — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="419f6-162">Calculations for product configuration models FAQ</span></span>](calculate-product-configuration-models.md)
- [<span data-ttu-id="419f6-163">Dodawanie ograniczenia wyrażenia do modelu konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="419f6-163">Add an expression constraint to a product configuration model</span></span>](tasks/add-expression-constraint-product-configuration-model.md)
- [<span data-ttu-id="419f6-164">Omówienie modeli konfiguracji produktu</span><span class="sxs-lookup"><span data-stu-id="419f6-164">Product configuration models overview</span></span>](product-configuration-models.md)
