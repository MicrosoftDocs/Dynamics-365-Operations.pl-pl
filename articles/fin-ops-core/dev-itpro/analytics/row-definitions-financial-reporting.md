---
title: Definicje wierszy w Projektancie raportów finansowych
description: Definicja wiersza to składnik (blok konstrukcyjny) raportu, który określa zawartość każdego wiersza w raporcie finansowym. Definicję wiersza można łączyć z definicjami kolumn, drzewa raportowania i raportów, by tworzyć grupy elementów konstrukcyjnych dostępne dla wielu firm.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 214a36a1284756e47aa1d28af99234657f1861c0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688290"
---
# <a name="row-definitions-in-financial-report-designer"></a><span data-ttu-id="cbf5f-104">Definicje wierszy w Projektancie raportów finansowych</span><span class="sxs-lookup"><span data-stu-id="cbf5f-104">Row definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbf5f-105">Definicja wiersza to składnik (blok konstrukcyjny) raportu, który określa zawartość każdego wiersza w raporcie finansowym.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-105">A row definition is a report component, or building block, that specifies the contents of each row on a financial report.</span></span> <span data-ttu-id="cbf5f-106">Definicję wiersza można łączyć z definicjami kolumn, drzewa raportowania i raportów, by tworzyć grupy elementów konstrukcyjnych dostępne dla wielu firm.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-106">A row definition can be combined with column definitions, reporting tree definitions, and report definitions to create a building block group that can be used by multiple companies.</span></span>

## <a name="create-a-row-definition"></a><span data-ttu-id="cbf5f-107">Tworzenie definicji wierszy</span><span class="sxs-lookup"><span data-stu-id="cbf5f-107">Create a row definition</span></span>

1. <span data-ttu-id="cbf5f-108">W Projektancie raportów w okienku nawigacji kliknij **Definicje wierszy**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-108">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="cbf5f-109">W menu **Plik** kliknij **Nowy**, a następnie kliknij polecenie **Definicja wiersza**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-109">On the **File** menu, click **New**, and then click **Row Definition**.</span></span> <span data-ttu-id="cbf5f-110">Aby uzyskać więcej informacji dotyczących zawartości każdej komórki, zobacz [Modyfikowanie komórek definicji wiersza](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="cbf5f-110">For more information about the content of each cell, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="open-a-row-definition"></a><span data-ttu-id="cbf5f-111">Otwieranie definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="cbf5f-111">Open a row definition</span></span>
1. <span data-ttu-id="cbf5f-112">W Projektancie raportów w okienku nawigacji kliknij **Definicje wierszy**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-112">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="cbf5f-113">Kliknij dwukrotnie nazwę definicji wiersza, którą chcesz otworzyć.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-113">Double-click the name of the row definition to open.</span></span>
3. <span data-ttu-id="cbf5f-114">Aby wyświetlić podstawowe elementy skojarzone z definicja wiersza, kliknij definicję wiersz prawym przyciskiem myszy, a następnie wybierz **Skojarzenia**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-114">To view any building blocks that are associated with the row definition, right-click the row definition, and then select **Associations**.</span></span>

## <a name="contents-of-a-row-definition"></a><span data-ttu-id="cbf5f-115"> Zawartość definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="cbf5f-115">Contents of a row definition</span></span>
<span data-ttu-id="cbf5f-116">Definicja wiersza może zawierać maksymalnie 20 000 wierszy wymiarów finansowych i uwzględniać następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="cbf5f-116">A row definition can contain up to 20,000 financial dimension rows and can include the following information:</span></span>

- <span data-ttu-id="cbf5f-117">Opisowy tekst, który dodaje znaczenie do raportu przez utworzenie nagłówków, wierszy i obszarów sekcji, np. **Gotówka** lub **Całkowity przychód**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-117">Descriptive text that adds meaning to the report by creating section headings, lines, and spaces, such as **Cash** or **Total Revenue**</span></span>
- <span data-ttu-id="cbf5f-118">Łącza do danych finansowych, co może obejmować wartości wymiarów z programu Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="cbf5f-118">Links to financial data, which can include dimension values in the Microsoft Dynamics 365 Finance</span></span>

    > [!NOTE]
    > <span data-ttu-id="cbf5f-119">Definicję wierszy można skonfigurować w taki sposób, że podczas każdego generowania raportu będzie pobierać dane z systemu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-119">You can set up a row definition to pull data from the financial dimensions system every time that the report is generated.</span></span>

- <span data-ttu-id="cbf5f-120">Sumy wierszy i formuły oparte na połączonych danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-120">Row totals and formulas that are based on the linked financial data</span></span>

<span data-ttu-id="cbf5f-121">Zazwyczaj każdy wiersz w definicji wiersza zawiera jeden z następujących typów informacji:</span><span class="sxs-lookup"><span data-stu-id="cbf5f-121">Usually, each row in a row definition contains one of the following types of information:</span></span>

- <span data-ttu-id="cbf5f-122">Odwołania do systemu wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-122">References to the financial dimensions system</span></span>
- <span data-ttu-id="cbf5f-123">Sumy lub obliczenia oparte na danych.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-123">Totals or calculations that are based on the data</span></span>
- <span data-ttu-id="cbf5f-124">Formatowanie</span><span class="sxs-lookup"><span data-stu-id="cbf5f-124">Formatting</span></span>

<span data-ttu-id="cbf5f-125">Istnieją dwie metody wprowadzania danych w definicji wiersza:</span><span class="sxs-lookup"><span data-stu-id="cbf5f-125">There are two methods for entering information in a row definition:</span></span>

- <span data-ttu-id="cbf5f-126">Ręczne wprowadzanie danych wiersza w nowej definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-126">Manually enter row information in a new row definition.</span></span> <span data-ttu-id="cbf5f-127">Aby uzyskać więcej informacji, zobacz [Modyfikowanie komórek definicji wiersza](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="cbf5f-127">For more information, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>
- <span data-ttu-id="cbf5f-128">Używanie Projektanta raportów do pobierania danych wiersza bezpośrednio z wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-128">Use report designer to pull row information directly from the financial dimensions.</span></span> <span data-ttu-id="cbf5f-129">Aby uzyskać więcej informacji, zobacz sekcję „Powiązane formuły/wiersze/jednostki” w artykule [Modyfikowanie komórek definicji wiersza](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="cbf5f-129">For more information, see the "Related formulas/rows/units" section in [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="add-dimensions-in-a-row-definition"></a><span data-ttu-id="cbf5f-130"> Dodawanie wymiarów w definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="cbf5f-130">Add dimensions in a row definition</span></span>
<span data-ttu-id="cbf5f-131">Wymiar jest częścią wspólną danych i wartości.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-131">A dimension is an intersection of data and values.</span></span> <span data-ttu-id="cbf5f-132">W projektancie raportów można grupować dane i wartości.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-132">You can group data and values in report designer.</span></span> <span data-ttu-id="cbf5f-133">Następnie można klasyfikować i analizować transakcje bardziej szczegółowo.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-133">You can then classify and analyze transactions in more detail.</span></span> <span data-ttu-id="cbf5f-134">Można użyć okna dialogowego **Wstaw wiersze z wymiarów**, aby dodawać wiersze do definicji wiersza w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-134">You can use the **Insert Rows from Dimensions** dialog box to add multiple rows to a row definition at the same time.</span></span> <span data-ttu-id="cbf5f-135">To okno dialogowe wyświetla jedną kolumnę dla każdego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-135">The dialog box displays one column for each dimension.</span></span> <span data-ttu-id="cbf5f-136">W poniższej tabeli opisano informacje, które można podać dla każdego wymiaru.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-136">The following table describes the information that you can specify for each dimension.</span></span>

| <span data-ttu-id="cbf5f-137">Opcja</span><span class="sxs-lookup"><span data-stu-id="cbf5f-137">Option</span></span>                | <span data-ttu-id="cbf5f-138">Opis</span><span class="sxs-lookup"><span data-stu-id="cbf5f-138">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="cbf5f-139">Wymiar</span><span class="sxs-lookup"><span data-stu-id="cbf5f-139">Dimension</span></span>             | <span data-ttu-id="cbf5f-140">Wzorzec określający wymiar, który ma zostać dodany do definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-140">The pattern that identifies the dimension to add to the row definition.</span></span> <span data-ttu-id="cbf5f-141">Ten wzorzec zawiera jeden znak & lub znak \# dla każde pozycji w wymiarach.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-141">This pattern contains one ampersand (&) or number sign (\#) for each position in the dimensions.</span></span> <span data-ttu-id="cbf5f-142">Ogólnie rzecz biorąc używaj wyłącznie znaków & dla wymiaru Konto główne i wyłącznie znaków # dla innych wymiarów.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-142">Generally, use all ampersands for the Main Account dimension and all number signs for other dimensions.</span></span> |
| <span data-ttu-id="cbf5f-143">Początek zakresu wymiarów</span><span class="sxs-lookup"><span data-stu-id="cbf5f-143">Dimension Range Start</span></span> | <span data-ttu-id="cbf5f-144">Pierwsza wartość dla tego wymiaru, która ma zostać dodana do definicji wierszy.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-144">The first value for this dimension to add to the row definition.</span></span> |
| <span data-ttu-id="cbf5f-145">Koniec zakresu wymiarów</span><span class="sxs-lookup"><span data-stu-id="cbf5f-145">Dimension Range End</span></span>   | <span data-ttu-id="cbf5f-146">Ostatnia wartość tego wymiaru, która ma zostać dodana do definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-146">The last value for this dimension to add to the row definition.</span></span> |

<span data-ttu-id="cbf5f-147">Aby dodać wymiary do definicji wiersza, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="cbf5f-147">To add dimensions to a row definition, follow these steps.</span></span>

1. <span data-ttu-id="cbf5f-148">W Projektancie raportów kliknij **Definicje wierszy**, a następnie otwórz definicję wiersza, którą chcesz zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-148">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="cbf5f-149">W menu **Edycja** kliknij **Wstaw wiersze z wymiarów**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-149">On the **Edit** menu, click **Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="cbf5f-150">W oknie dialogowym **Wstaw wiersze z wymiarów** w wierszu **Wymiary** wybierz komórki dla wymiaru, który ma zostać przeniesiony do definicji wiersza, a następnie kliknij przycisk **Wszystkie &&&**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-150">In the **Insert Rows from Dimensions** dialog box, in the **Dimensions** row, select the cell for the dimension to transfer to the row definition, and then click **All &&&**.</span></span>
4. <span data-ttu-id="cbf5f-151">Aby ograniczyć definicję wiersza do określonego zakresu wartości wymiarów, wprowadź początkową wartość wymiaru w komórce **Początek zakresu wymiaru**, a następnie wprowadź końcową wartość wymiaru w komórce **Koniec zakresu wymiaru**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-151">To limit the row definition to a specific range of dimension values, enter the starting dimension value in the **Dimension Range Start** cell, and then enter the ending dimension value in the **Dimension Range End** cell.</span></span> <span data-ttu-id="cbf5f-152">Aby uwzględnić wszystkie wartości dla wybranego wymiaru, pozostaw te komórki puste.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-152">To include all values for the selected dimension, leave these cells empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cbf5f-153">Użycie symboli wieloznacznych (\* lub ?) w zakresach wymiarów może spowodować, że nie zostaną zwrócone wszystkie oczekiwane wyniki. Jest to zależne od sposobu gromadzenia danych w bazie danych systemu ERP.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-153">Wildcard characters (\* or ?) in dimension ranges might not return all the results that you want, depending on how the ERP database collates data.</span></span>

5. <span data-ttu-id="cbf5f-154">W polu **Początkowy kod wiersza** określ kod wiersza dla pierwszej wartości wymiaru, która ma zostać dodana do definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-154">In the **Starting row code** field, specify the row code for the first dimension value to add to the row definition.</span></span>
6. <span data-ttu-id="cbf5f-155">W polu **Przyrost każdego wiersza** określ odstęp między kolejnymi kodami wierszy.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-155">In the **Increment each row by** field, specify the gap between consecutive row codes.</span></span> <span data-ttu-id="cbf5f-156">Na przykład jeśli kod pierwszego wiersza wynosi 100, a wartość przyrostu wynosi 30, pierwsze nowe wiersze mają kody 100, 130, 160, 190 i 220.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-156">For example, if the first row code is 100, and the increment value is 30, the first new rows have the codes 100, 130, 160, 190, and 220.</span></span> <span data-ttu-id="cbf5f-157">Użyj wartość przyrostu, która zapewnia wystarczający odstęp na wstawienie nowych wierszy formatu i formuły.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-157">Use an increment value that provides enough space to insert new format and formula rows.</span></span>
7. <span data-ttu-id="cbf5f-158">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="cbf5f-158">Click **OK**.</span></span> <span data-ttu-id="cbf5f-159">Dla każdej wybranej wartości wymiaru jest dodawany jeden wiersz do definicji wiersza.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-159">For each of the selected dimension values, one line is added to the row definition.</span></span>

## <a name="adjust-rounding-in-a-row-definition"></a><span data-ttu-id="cbf5f-160"> Korekta zaokrąglenia w definicji wiersza</span><span class="sxs-lookup"><span data-stu-id="cbf5f-160">Adjust rounding in a row definition</span></span>
<span data-ttu-id="cbf5f-161">W przypadku bilansu, w którym kwoty są zaokrąglane, sumy mogą się nie bilansować.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-161">If you have a balance sheet where the amounts are rounded, the totals might not balance.</span></span> <span data-ttu-id="cbf5f-162">Ten problem może wystąpić, jeśli na przykład używasz opcji zaokrąglania w raporcie o bilansie, a definicja raportu również określa zaokrąglanie.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-162">This issue can occur if, for example, you use the rounding option on a balance sheet report and the report definition also specifies rounding.</span></span> <span data-ttu-id="cbf5f-163">Aby bilansować kwoty w bilansach, można w definicji wiersza użyć opcji **Korygowanie zaokrągleń**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-163">You can use the **Rounding adjustment** option in the row definition to balance the amounts in the balance sheets.</span></span> <span data-ttu-id="cbf5f-164">W definicji raportu na karcie **Ustawienia** można wyłączyć zaokrąglanie lub je zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-164">You can turn rounding off or modify it on the **Settings** tab of the report definition.</span></span> <span data-ttu-id="cbf5f-165">W poniższej tabeli przedstawiono sposób zaokrąglania kwot:</span><span class="sxs-lookup"><span data-stu-id="cbf5f-165">The following table shows how amounts are rounded.</span></span> <span data-ttu-id="cbf5f-166">W tej tabeli sumy wierszy 100 i 200 różnią się, gdy zaokrąglanie jest włączone.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-166">In this table, the totals of rows 100 and 200 differ when rounding is turned on.</span></span>

| <span data-ttu-id="cbf5f-167">Kod wiersza</span><span class="sxs-lookup"><span data-stu-id="cbf5f-167">Row code</span></span> | <span data-ttu-id="cbf5f-168">Kwoty bez zaokrąglania</span><span class="sxs-lookup"><span data-stu-id="cbf5f-168">Amounts without rounding</span></span> | <span data-ttu-id="cbf5f-169">Kwota z zaokrąglaniem do całych tysięcy</span><span class="sxs-lookup"><span data-stu-id="cbf5f-169">Amount with rounding to whole thousands</span></span> |
|----------|--------------------------|-----------------------------------------|
| <span data-ttu-id="cbf5f-170">100</span><span class="sxs-lookup"><span data-stu-id="cbf5f-170">100</span></span>      | <span data-ttu-id="cbf5f-171">3600</span><span class="sxs-lookup"><span data-stu-id="cbf5f-171">3,600</span></span>                    | <span data-ttu-id="cbf5f-172">4</span><span class="sxs-lookup"><span data-stu-id="cbf5f-172">4</span></span>                                       |
| <span data-ttu-id="cbf5f-173">200</span><span class="sxs-lookup"><span data-stu-id="cbf5f-173">200</span></span>      | <span data-ttu-id="cbf5f-174">3700</span><span class="sxs-lookup"><span data-stu-id="cbf5f-174">3,700</span></span>                    | <span data-ttu-id="cbf5f-175">4</span><span class="sxs-lookup"><span data-stu-id="cbf5f-175">4</span></span>                                       |
| <span data-ttu-id="cbf5f-176">Suma</span><span class="sxs-lookup"><span data-stu-id="cbf5f-176">Total</span></span>    | <span data-ttu-id="cbf5f-177">7300</span><span class="sxs-lookup"><span data-stu-id="cbf5f-177">7,300</span></span>                    | <span data-ttu-id="cbf5f-178">8</span><span class="sxs-lookup"><span data-stu-id="cbf5f-178">8</span></span>                                       |

<span data-ttu-id="cbf5f-179">Aby dostosować zaokrąglenie w bilansie, należy wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="cbf5f-179">To adjust rounding in a balance sheet, follow these steps.</span></span>

1. <span data-ttu-id="cbf5f-180">W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-180">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="cbf5f-181">W menu **Edycja** kliknij polecenie **Doksięgowanie zaokrągleń**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-181">On the **Edit** menu, click **Rounding Adjustment**.</span></span>
3. <span data-ttu-id="cbf5f-182">W oknie dialogowym **Korygowanie zaokrągleń** wpisz następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="cbf5f-182">In the **Rounding Adjustments** dialog box, enter the following values:</span></span>

    - <span data-ttu-id="cbf5f-183">**Wiersz korekty zaokrąglania** — kod wiersza, który powinien być korygowany w celu zbilansowania bilansu.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-183">**Rounding adjustment row** – The row code for the row that should be adjusted to balance the balance sheet.</span></span>
    - <span data-ttu-id="cbf5f-184">**Wiersz sumy aktywów** — kod wiersza dla wierszy w bilansie, który zawiera sumy aktywów.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-184">**Total assets row** – The row code for the row in the balance sheet that contains the total assets.</span></span>
    - <span data-ttu-id="cbf5f-185">**Wiersz sumy zobowiązań i kapitału własnego** — kod wiersza dla wierszy w bilansie, który zawiera sumy zobowiązań i kapitału własnego.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-185">**Total liabilities and equity row** – The row code for the row in the balance sheet that contains the total liabilities and equity.</span></span>
    - <span data-ttu-id="cbf5f-186">**Limit kwoty korekty** — dodatnia liczba całkowita określająca limit dla automatycznych korekt.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-186">**Adjustment amount limit** – A positive whole number that specifies the limit on automatic adjustments.</span></span> <span data-ttu-id="cbf5f-187">Ta kwota jest porównywana z bezwzględną wartością rzeczywistej różnicy zaokrągleń.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-187">This amount is compared with the absolute value of the actual rounding difference.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cbf5f-188">Te kody wierszy muszą być połączone z danymi finansowymi.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-188">These row codes must be linked to your financial data.</span></span> <span data-ttu-id="cbf5f-189">Innymi słowy, wiersz musi mieć wartość wymiaru w komórce **Łącze do Wymiary finansowe**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-189">In other words, the row must have a dimension value in its **Link to Financial Dimensions** cell.</span></span> <span data-ttu-id="cbf5f-190">**Nie** należy używać odwołania do wiersza opisu (**DESC**), obliczenia (**CALC**) ani sumy (**TOT**).</span><span class="sxs-lookup"><span data-stu-id="cbf5f-190">Do **not** reference a description (**DESC**), calculated (**CALC**), or totaled (**TOT**) row.</span></span>

<span data-ttu-id="cbf5f-191">Kwoty w bilansie będą teraz bilansowane równomiernie, gdy jest włączone zaokrąglanie.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-191">The amounts in your balance sheet will now balance evenly when rounding is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="cbf5f-192">Limit doksięgowania jest stosowany na podstawie opcji **Dokładność zaokrąglania** określonej w definicji raportu.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-192">The adjustment limit is applied based on the **Rounding precision** option that is specified for the report definition.</span></span> <span data-ttu-id="cbf5f-193">Na przykład zaokrąglanie raportu do tysięcy i wprowadzenie wartości **2** w polu **Limit kwoty korekty** spowoduje wyświetlanie komunikatu ostrzegawczego, gdy wartość określona w polu **Wiersz korekty zaokrąglania** zwiększy się lub zmniejszy o ponad 2000.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-193">For example, if you round your report to thousands and enter **2** in the **Adjustment amount limit** field, you receive a warning message when the value in the **Rounding adjustment row** field increases or decreases by more than 2,000.</span></span>

## <a name="format-row-and-column-text"></a><span data-ttu-id="cbf5f-194">Formatowanie tekstu wiersza i kolumny</span><span class="sxs-lookup"><span data-stu-id="cbf5f-194">Format row and column text</span></span>
<span data-ttu-id="cbf5f-195">Można dostosować wygląd raportów, zmieniając czcionki i formatując tekst.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-195">You can customize the appearance of your reports by changing fonts and formatting text.</span></span> <span data-ttu-id="cbf5f-196">Poniższe sekcje zawierają wyjaśnienia dotyczące formatowania wyglądu wierszy i kolumn w raportach.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-196">The following sections explain how to format the appearance of rows and columns on reports.</span></span>

### <a name="manage-font-styles"></a><span data-ttu-id="cbf5f-197">Zarządzanie stylami czcionek</span><span class="sxs-lookup"><span data-stu-id="cbf5f-197">Manage font styles</span></span>

<span data-ttu-id="cbf5f-198">Można tworzyć i modyfikować style czcionek dla raportu.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-198">You can create and modify font styles for your report.</span></span> <span data-ttu-id="cbf5f-199">Następnie można zastosować te style do dokumentu albo do określonego wiersza lub kolumny w raporcie.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-199">You can then apply those styles to the document, or to a specific row or column on a report.</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="cbf5f-200"><strong>Tworzenie stylu czcionki</strong></span><span class="sxs-lookup"><span data-stu-id="cbf5f-200"><strong>Create a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="cbf5f-201">W Projektancie raportów w menu <strong>Format</strong> kliknij <strong>Style i formatowanie</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-201">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="cbf5f-202">W oknie dialogowym <strong>Style i formatowanie</strong> kliknij przycisk <strong>Nowy</strong>, po czym nadaj nowemu stylowi unikatową nazwę.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-202">In the <strong>Styles and Formatting</strong> dialog box, click <strong>New</strong>, and then enter a unique name for the new style.</span></span></li>
<li><span data-ttu-id="cbf5f-203">Zaznacz parametry czcionki i kliknij przycisk <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-203">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="cbf5f-204"><strong>Modyfikowanie stylu czcionki</strong></span><span class="sxs-lookup"><span data-stu-id="cbf5f-204"><strong>Modify a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="cbf5f-205">W Projektancie raportów w menu <strong>Format</strong> kliknij <strong>Style i formatowanie</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-205">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="cbf5f-206">W oknie dialogowym <strong>Style i formatowanie</strong> zaznacz styl, który chcesz zmodyfikować, i kliknij przycisk <strong>Modyfikuj</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-206">In the <strong>Styles and Formatting</strong> dialog box, select a style to modify, and then click <strong>Modify</strong>.</span></span></li>
<li><span data-ttu-id="cbf5f-207">Zaznacz parametry czcionki i kliknij przycisk <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-207">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="cbf5f-208"><strong>Stosowanie stylu czcionki</strong></span><span class="sxs-lookup"><span data-stu-id="cbf5f-208"><strong>Apply a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="cbf5f-209">W Projektancie raportów, w definicji lub definicji kolumny albo w nagłówkach i stopkach, wybierz jedną lub więcej komórek.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-209">In Report Designer, in a definition or column definition, or in headers and footers, select one or more cells.</span></span></li>
<li><span data-ttu-id="cbf5f-210">Na pasku narzędzi na liście <strong>Styl</strong> zaznacz styl czcionki.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-210">In the <strong>Style</strong> list on the toolbar, select a font style.</span></span></li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a><span data-ttu-id="cbf5f-211">Formatowanie tekstu wiersza</span><span class="sxs-lookup"><span data-stu-id="cbf5f-211">Format row text</span></span>

<span data-ttu-id="cbf5f-212">Formatowanie określone w definicji wiersza zastępuje wszelkie formatowanie określone w definicji kolumny oraz w definicji raportu.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-212">The formatting that is specified in the row definition overrides any formatting that is specified in the column definition and the report definition.</span></span> <span data-ttu-id="cbf5f-213">Format tekstu można zmodyfikować za pomocą formantów na pasku narzędzi formatowania.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-213">You can modify the text format by using the controls on the formatting toolbar.</span></span> <span data-ttu-id="cbf5f-214">Są to standardowe formanty systemu Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-214">These controls are standard Microsoft Windows controls.</span></span>

1. <span data-ttu-id="cbf5f-215">W Projektancie raportów otwórz definicję wierszy, którą chcesz zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-215">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="cbf5f-216">Zaznacz komórki do formatowania.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-216">Select the cells to format.</span></span> <span data-ttu-id="cbf5f-217">Aby wybrać wiele komórek, przytrzymaj klawisz Ctrl i zaznaczaj kolejne komórki.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-217">To select multiple cells, hold down the Ctrl key while you select the cell.</span></span>
3. <span data-ttu-id="cbf5f-218">Kliknij przycisk na pasku narzędzi dla formatu, który chcesz zastosować.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-218">Click the toolbar button of the format to apply.</span></span> <span data-ttu-id="cbf5f-219">Na przykład aby zwiększyć wcięcie wiersza, zaznacz wiersz, a następnie kliknij **Zwiększ wcięcie** ![Zwiększ wcięcie](media/indent.gif "Zwiększ wcięcie") na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-219">For example, to indent a row, select the row, and then click **Increase Indent** ![Increase Indent](media/indent.gif "Increase Indent") on the toolbar.</span></span>

### <a name="adjust-columns-while-you-design-reports"></a><span data-ttu-id="cbf5f-220">Dostosowywanie kolumn podczas projektowania raportów</span><span class="sxs-lookup"><span data-stu-id="cbf5f-220">Adjust columns while you design reports</span></span>

<span data-ttu-id="cbf5f-221">Aby ułatwić wyświetlanie kolumn, nad którymi pracujesz w definicji wiersza, można dopasować szerokość kolumny oraz ukryć (zminimalizować) lub pokazać kolumny w okienku widoku.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-221">To make it easier to view the columns that you're working on in the row definition, you can adjust the width of a column, and can also hide (minimize) or show columns in the view pane.</span></span> <span data-ttu-id="cbf5f-222">Wprowadzane modyfikacje wpływają tylko na wygląd kolumn na ekranie.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-222">The modifications that you make affect only the on-screen appearance of the columns.</span></span> <span data-ttu-id="cbf5f-223">Nie wpływają na formatowanie kolumn w raportach.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-223">They don't affect the column formatting on reports.</span></span>

### <a name="change-the-width-of-a-column-in-the-view-pane"></a><span data-ttu-id="cbf5f-224">Zmienianie szerokości kolumny w okienku widoku</span><span class="sxs-lookup"><span data-stu-id="cbf5f-224">Change the width of a column in the view pane</span></span>

1. <span data-ttu-id="cbf5f-225">W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-225">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="cbf5f-226">W menu **Format** wybierz **Szerokość kolumny**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-226">On the **Format** menu, select **Column Width**.</span></span>
3. <span data-ttu-id="cbf5f-227">W oknie dialogowym **Szerokość kolumny** wprowadź wartość, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-227">In the **Column Width** dialog box, enter a value, and then click **OK**.</span></span> <span data-ttu-id="cbf5f-228">Alternatywnie można przeciągać prawą granicę komórki nagłówka kolumny, aby zmienić szerokość kolumny.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-228">Alternatively, you can drag the right boundary of a column heading cell to change the width of the column.</span></span>

### <a name="hide-columns-in-the-view-pane"></a><span data-ttu-id="cbf5f-229">Ukrywanie kolumn w okienku widoku</span><span class="sxs-lookup"><span data-stu-id="cbf5f-229">Hide columns in the view pane</span></span>

1. <span data-ttu-id="cbf5f-230">W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-230">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="cbf5f-231">Zaznacz kolumnę lub kolumny, które chcesz zminimalizować.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-231">Select the column or columns to minimize.</span></span>
3. <span data-ttu-id="cbf5f-232">Kliknij prawym przyciskiem myszy, a następnie kliknij **Ukryj**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-232">Right-click, and then click **Hide**.</span></span>

### <a name="show-all-hidden-columns-in-the-view-pane"></a><span data-ttu-id="cbf5f-233">Pokazywanie wszystkich ukrytych kolumn w okienku widoku</span><span class="sxs-lookup"><span data-stu-id="cbf5f-233">Show all hidden columns in the view pane</span></span>

1. <span data-ttu-id="cbf5f-234">W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-234">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="cbf5f-235">Kliknij prawym przyciskiem myszy zminimalizowaną kolumnę, którą chcesz wyświetlać, a następnie kliknij **Odkryj**.</span><span class="sxs-lookup"><span data-stu-id="cbf5f-235">Right-click the minimized column to display, and then click **Unhide**.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="cbf5f-236">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cbf5f-236">Additional resources</span></span>

[<span data-ttu-id="cbf5f-237">Raportowanie finansowe</span><span class="sxs-lookup"><span data-stu-id="cbf5f-237">Financial reporting</span></span>](financial-reporting-intro.md)
