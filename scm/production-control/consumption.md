---
title: "Obliczanie zużycia materiału"
description: "Ten artykuł zawiera informacje o różnych opcjach związanych z obliczaniem zużycia materiałów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 88fb31fc425c9fbd2ef96e4497f120da4440af04
ms.contentlocale: pl-pl
ms.lasthandoff: 06/29/2017


---

# <a name="calculate-material-consumption"></a><span data-ttu-id="56eac-103">Obliczanie zużycia materiału</span><span class="sxs-lookup"><span data-stu-id="56eac-103">Calculate material consumption</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="56eac-104">Ten artykuł zawiera informacje o różnych opcjach związanych z obliczaniem zużycia materiałów.</span><span class="sxs-lookup"><span data-stu-id="56eac-104">This article provides information about various options that are related to the calculation of material consumption.</span></span> 

<span data-ttu-id="56eac-105">Następujące opcje, które odnoszą się do obliczania zużycia materiałów są dostępne na kartach **ustawienia** i **zużycie etapowe** na skróconej karcie **szczegóły wiersza** strony **BOM**.</span><span class="sxs-lookup"><span data-stu-id="56eac-105">The following options that are related to the calculation of material consumption are available on the **Setup** and **Step consumption** tabs on the **Line details** FastTab of the **Bill of materials** page.</span></span>

## <a name="variable-and-constant-consumption"></a><span data-ttu-id="56eac-106">Zużycie stałe i zmienne</span><span class="sxs-lookup"><span data-stu-id="56eac-106">Variable and constant consumption</span></span>
<span data-ttu-id="56eac-107">W polu **Zużycie jest** można określić, czy zużycie powinno być obliczane jako wartości stałe, czy zmienne.</span><span class="sxs-lookup"><span data-stu-id="56eac-107">In the **Consumption is** field, you can select whether consumption should be calculated as a constant quantity or a variable quantity.</span></span> <span data-ttu-id="56eac-108">Wybierz opcję **Stała**, jeśli stała ilość lub objętość towaru jest potrzebna do produkcji, bez względu na ilość produkowanych pozycji.</span><span class="sxs-lookup"><span data-stu-id="56eac-108">Select **Constant** if a fixed quantity or volume is required for the production, regardless of the quantity that is produced.</span></span> <span data-ttu-id="56eac-109">Wybierz **zmienne** (ustawienie domyślne), gdy wymagana ilość materiału do towarów gotowych jest proporcjonalna do liczby gotowych towarów, które są produkowane.</span><span class="sxs-lookup"><span data-stu-id="56eac-109">Select **Variable**, which is the default setting, if the required amount of material in the finished goods is proportional to the number of finished goods that are produced.</span></span>

## <a name="calculating-consumption-from-a-formula"></a><span data-ttu-id="56eac-110">Wzór do obliczania zużycia</span><span class="sxs-lookup"><span data-stu-id="56eac-110">Calculating consumption from a formula</span></span>
<span data-ttu-id="56eac-111">W polu **formuła** można skonfigurować różne formuły do obliczania zużycia materiału.</span><span class="sxs-lookup"><span data-stu-id="56eac-111">In the **Formula** field, you can set up various formulas for calculating material consumption.</span></span> <span data-ttu-id="56eac-112">W przypadku korzystania z wartości domyślnej **Standardowa**, zużycie nie jest obliczana na podstawie formuły.</span><span class="sxs-lookup"><span data-stu-id="56eac-112">If you use the default value, **Standard**, the consumption isn't calculated from a formula.</span></span> <span data-ttu-id="56eac-113">Poniższe formuły współpracują z polami **wysokość**, **szerokość**, **głębokość**, **gęstość**, i **stała**:</span><span class="sxs-lookup"><span data-stu-id="56eac-113">The following formulas work together with the **Height**, **Width**, **Depth**, **Density**, and **Constant** fields:</span></span>

-   <span data-ttu-id="56eac-114">Wysokość \* Stała</span><span class="sxs-lookup"><span data-stu-id="56eac-114">Height \* Constant</span></span>
-   <span data-ttu-id="56eac-115">Wysokość \* Szerokość \* Stała</span><span class="sxs-lookup"><span data-stu-id="56eac-115">Height \* Width \* Constant</span></span>
-   <span data-ttu-id="56eac-116">Wysokość \* Szerokość \* Długość \* Stała</span><span class="sxs-lookup"><span data-stu-id="56eac-116">Height \* Width \* Depth \* Constant</span></span>
-   <span data-ttu-id="56eac-117">(Wysokość \* Szerokość \* Długość/Gęstość) \* Stała</span><span class="sxs-lookup"><span data-stu-id="56eac-117">(Height \* Width \* Depth / Density) \* Constant</span></span>

## <a name="rounding-up-and-multiples"></a><span data-ttu-id="56eac-118">Zaokrąglenie i wielokrotności</span><span class="sxs-lookup"><span data-stu-id="56eac-118">Rounding up and multiples</span></span>
<span data-ttu-id="56eac-119">Razem pola **zaokrąglanie w górę** i **wielokrotności** umożliwiają zaokrąglanie w górę do wartości zużycia materiału.</span><span class="sxs-lookup"><span data-stu-id="56eac-119">Together, the **Rounding up** and **Multiples** fields let you round up the material consumption value.</span></span> <span data-ttu-id="56eac-120">Można na przykład zaokrąglać wartości na podstawie jednostki załadunkowej, w której surowiec jest pobierany dla produkcji.</span><span class="sxs-lookup"><span data-stu-id="56eac-120">For example, you can round up the value according to the handling unit in which the raw material is picked for production.</span></span> <span data-ttu-id="56eac-121">Dostępne są następujące opcje w polu **zaokrąglanie w górę**: **ilość**, **miara** i **zużycie**.</span><span class="sxs-lookup"><span data-stu-id="56eac-121">The following options are available in the **Rounding up** field: **Quantity**, **Measurement**, and **Consumption**.</span></span>

### <a name="quantity"></a><span data-ttu-id="56eac-122">Ilość</span><span class="sxs-lookup"><span data-stu-id="56eac-122">Quantity</span></span>

<span data-ttu-id="56eac-123">W przypadku wybrania opcji **ilość** jako mechanizmu zaokrąglenia w górę, ilość musi być wielokrotnością określonej ilości.</span><span class="sxs-lookup"><span data-stu-id="56eac-123">If you select **Quantity** as the rounding-up mechanism, the quantity must be a multiple of the specified quantity.</span></span> <span data-ttu-id="56eac-124">Jeśli na przykład są wymagane liczby całkowite, wybierz **1** polu **Wielokrotność**.</span><span class="sxs-lookup"><span data-stu-id="56eac-124">For example, if whole numbers are required, select **1** in the **Multiples** field.</span></span> <span data-ttu-id="56eac-125">Liczby są następnie zaokrąglane w górę do ilości, która dzieli się przez 1.</span><span class="sxs-lookup"><span data-stu-id="56eac-125">Numbers are then rounded up to a quantity that is divisible by 1.</span></span>

### <a name="measurement"></a><span data-ttu-id="56eac-126">Miara</span><span class="sxs-lookup"><span data-stu-id="56eac-126">Measurement</span></span>

<span data-ttu-id="56eac-127">Zazwyczaj, zaznacza się **miarę** jako mechanizm zaokrąglania w górę, gdy surowce są dostarczane w określonych wymiarach.</span><span class="sxs-lookup"><span data-stu-id="56eac-127">Typically, you select **Measurement** as the rounding-up mechanism when the raw material comes in specific dimensions.</span></span> <span data-ttu-id="56eac-128">Na przykład: do wyprodukowania gotowego towaru potrzeba 2-metrowej metalowej rury, ale rury są fabrycznie cięte na kawałki o długości 4,5 m.</span><span class="sxs-lookup"><span data-stu-id="56eac-128">For example, a piece of 2-meter metal tube is required for a finished good, and the metal tube is stored in 4.5-meter lengths.</span></span> <span data-ttu-id="56eac-129">W takim przypadku **miary** mechanizm zaokrąglania w górę może być używany do obliczenia, ile metalowych rur potrzeba do wyprodukowania określonej liczby gotowego produktu.</span><span class="sxs-lookup"><span data-stu-id="56eac-129">In this case, the **Measurement** rounding-up mechanism can be used to calculate how many metal tubes are required to produce a specific number of pieces of the finished good.</span></span> <span data-ttu-id="56eac-130">W tym przykładzie pole **Formuła** jest ustawione jako **Wysokość \* Stała**.</span><span class="sxs-lookup"><span data-stu-id="56eac-130">For this example, the **Formula** field is set to **Height \* Constant**.</span></span> <span data-ttu-id="56eac-131">Pole **Wysokość** jest ustawione jako **2**, co wskazuje długość rury wymaganą dla towaru gotowego.</span><span class="sxs-lookup"><span data-stu-id="56eac-131">The **Height** field is set to **2** to indicate the length of the tube that is required for the finished good.</span></span> <span data-ttu-id="56eac-132">W polu **Wielokrotność** ustawiono opcję **4,5**, co wskazuje, że rura jest dostarczana w kawałkach o długości 4,5 m.</span><span class="sxs-lookup"><span data-stu-id="56eac-132">The **Multiple** field is set to **4.5** to indicate that the tube is picked in lengths of 4.5 meters.</span></span> <span data-ttu-id="56eac-133">Obliczenie ma następującą postać:</span><span class="sxs-lookup"><span data-stu-id="56eac-133">Here is the calculation:</span></span>

1.  <span data-ttu-id="56eac-134">Liczba wielokrotności, które są wymagane w przypadku 10 sztuk towaru gotowego: 10 / 2 = 5 sztuk</span><span class="sxs-lookup"><span data-stu-id="56eac-134">Number of multiples that are required for 10 pieces of the finished good: 10 ÷ 2 = 5 pieces</span></span>
2.  <span data-ttu-id="56eac-135">Suma zużycia: 4.5 x 5 = 22,5 m rury metalowej</span><span class="sxs-lookup"><span data-stu-id="56eac-135">Total consumption:  4.5 × 5 = 22.5 meters of metal tube</span></span>

<span data-ttu-id="56eac-136">Oznacza to, że z każdych pięciu sztuk zużytej rury zostaje odpadek o długości 0,5 m.</span><span class="sxs-lookup"><span data-stu-id="56eac-136">It's assumed that 0.5 meter of tube is scrapped for every five pieces of tube that are consumed.</span></span>

### <a name="consumption"></a><span data-ttu-id="56eac-137">Zużycie</span><span class="sxs-lookup"><span data-stu-id="56eac-137">Consumption</span></span>

<span data-ttu-id="56eac-138">Zazwyczaj wybiera się **Zużycie** jako mechanizm zaokrąglania, gdy surowiec musi być pobrany w określonej jednostce załadunkowej.</span><span class="sxs-lookup"><span data-stu-id="56eac-138">Typically, you select **Consumption** as the rounding-up mechanism when raw material must be picked in whole quantities of a specific handling unit of the product.</span></span> <span data-ttu-id="56eac-139">Na przykład do wyprodukowania jednej sztuki towaru gotowego potrzeba 2 litrów farby, a jedna puszka farby zawiera 25 litrów.</span><span class="sxs-lookup"><span data-stu-id="56eac-139">For example, 2 quarts of paint are used to produce one piece of a finished good, and the paint is picked in 25-quart cans.</span></span> <span data-ttu-id="56eac-140">W takim przypadku mechanizm zaokrąglania w górę **Zużycia** pozwala na zaokrąglanie w górę do liczby całkowitej 25-litrowych puszek.</span><span class="sxs-lookup"><span data-stu-id="56eac-140">In this case, the **Consumption** rounding-up mechanism can be used to round up consumption to whole numbers of 25-quart cans.</span></span> <span data-ttu-id="56eac-141">Poniżej znajduje się obliczenie ilości farby wymaganej do wyprodukowania 180 sztuk towaru gotowego:</span><span class="sxs-lookup"><span data-stu-id="56eac-141">Here is the calculation for the amount of paint that is required if 180 pieces of the finished good must be produced:</span></span>

1.  <span data-ttu-id="56eac-142">Wymagana farba bez odpadków: 180 x 2 = 360 litrów</span><span class="sxs-lookup"><span data-stu-id="56eac-142">Paint that is required, excluding scrap: 180 × 2 = 360 quarts</span></span>
2.  <span data-ttu-id="56eac-143">Liczba puszek: 360 / 25 = 14,4, która jest zaokrąglana do 15</span><span class="sxs-lookup"><span data-stu-id="56eac-143">Number of cans: 360 ÷ 25 = 14.4, which is rounded up to 15</span></span>
3.  <span data-ttu-id="56eac-144">Wymagana farba z uwzględnieniem odpadków: 15 x 25 = 375 litrów</span><span class="sxs-lookup"><span data-stu-id="56eac-144">Paint that is required, including scrap: 15 × 25 = 375 quarts</span></span>

## <a name="step-consumption"></a><span data-ttu-id="56eac-145">Zużycie etapowe</span><span class="sxs-lookup"><span data-stu-id="56eac-145">Step consumption</span></span>
<span data-ttu-id="56eac-146">Zużycie etapowe jest używane do obliczania zużycia stałego w interwałach ilości.</span><span class="sxs-lookup"><span data-stu-id="56eac-146">Step consumption is used to calculate constant consumption in quantity intervals.</span></span> <span data-ttu-id="56eac-147">Wybranie opcji **Zużycie etapowe** w polu **formuły** na karcie **ustawienia** umożliwia dodanie informacji o krokach na karcie **Zużycie etapowe**.</span><span class="sxs-lookup"><span data-stu-id="56eac-147">If you select **Step consumption** in the **Formula** field on the **Setup** tab, you can add information about the steps on the **Step consumption** tab.</span></span> <span data-ttu-id="56eac-148">Stała ilość zużytej ilości może być ustawiona w interwałach wyprodukowanej ilości.</span><span class="sxs-lookup"><span data-stu-id="56eac-148">The fixed consumed quantity can be set up in intervals of the produced quantity.</span></span> <span data-ttu-id="56eac-149">Na przykład Zużycie etapowe skonfigurowano jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="56eac-149">For example, step consumption is set up as shown in the following table.</span></span>

| <span data-ttu-id="56eac-150">Od serii</span><span class="sxs-lookup"><span data-stu-id="56eac-150">From series</span></span> | <span data-ttu-id="56eac-151">Ilość</span><span class="sxs-lookup"><span data-stu-id="56eac-151">Quantity</span></span> |
|-------------|----------|
| <span data-ttu-id="56eac-152">0,00</span><span class="sxs-lookup"><span data-stu-id="56eac-152">0.00</span></span>        | <span data-ttu-id="56eac-153">10 0000</span><span class="sxs-lookup"><span data-stu-id="56eac-153">10.0000</span></span>  |
| <span data-ttu-id="56eac-154">100,00</span><span class="sxs-lookup"><span data-stu-id="56eac-154">100.00</span></span>      | <span data-ttu-id="56eac-155">20 0000</span><span class="sxs-lookup"><span data-stu-id="56eac-155">20.0000</span></span>  |
| <span data-ttu-id="56eac-156">200,00</span><span class="sxs-lookup"><span data-stu-id="56eac-156">200.00</span></span>      | <span data-ttu-id="56eac-157">40 0000</span><span class="sxs-lookup"><span data-stu-id="56eac-157">40.0000</span></span>  |

<span data-ttu-id="56eac-158">Ilość BOM wynosi 1, a ilość produkcji — 110.</span><span class="sxs-lookup"><span data-stu-id="56eac-158">The bill of materials (BOM) quantity is 1, and the production quantity is 110.</span></span> <span data-ttu-id="56eac-159">Formuła zużycia: Od serii (ilość) = zużycie.</span><span class="sxs-lookup"><span data-stu-id="56eac-159">The formula for the consumption is From series (Quantity) = Consumption.</span></span> <span data-ttu-id="56eac-160">Ponieważ wielkość produkcji wynosi 110, należy do zakresu Od serii 100.</span><span class="sxs-lookup"><span data-stu-id="56eac-160">Because the production quantity is 110, it falls into the "From 100 series."</span></span> <span data-ttu-id="56eac-161">Zatem ilość wynosi 20.</span><span class="sxs-lookup"><span data-stu-id="56eac-161">Therefore, the quantity is 20.</span></span>




