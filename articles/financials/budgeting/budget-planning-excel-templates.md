---
title: "Szablony planowania budżetu dla programu Excel"
description: "W tym temacie opisano sposób tworzenia szablonów programu Microsoft Excel, które mogą być używane w planach budżetu."
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 079aa6bb4be020fc050b81c400050ed23d48f6ca
ms.contentlocale: pl-pl
ms.lasthandoff: 08/07/2018

---

# <a name="budget-planning-templates-for-excel"></a><span data-ttu-id="536ea-103">Szablony planowania budżetu dla programu Excel</span><span class="sxs-lookup"><span data-stu-id="536ea-103">Budget planning templates for Excel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="536ea-104">W tym temacie opisano sposób tworzenia szablonów programu Microsoft Excel, które mogą być używane w planach budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-104">This topic describes how to create Microsoft Excel templates that can be used with budget plans.</span></span>

<span data-ttu-id="536ea-105">W tym temacie pokazano, jak tworzyć szablony programu Excel przeznaczone dla planów budżetu, wykorzystując do tego standardowy zestaw danych demonstracyjnych i logowanie użytkownika będącego administratorem.</span><span class="sxs-lookup"><span data-stu-id="536ea-105">This topic shows how to create Excel templates that will be used with budget plans using the standard demo data set and the Admin user login.</span></span> <span data-ttu-id="536ea-106">Aby uzyskać więcej informacji na temat planowania budżetu, zobacz [Przegląd planowania budżetu.](budget-planning-overview-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="536ea-106">For more information about budget planning, see [Budget planning overview.](budget-planning-overview-configuration.md)</span></span> <span data-ttu-id="536ea-107">Można również przejść samouczek [Planowanie budżetu 101](budget-plan.md), który przekazuje podstawowe informacje o konfiguracjach modułu i zasadach użytkowania.</span><span class="sxs-lookup"><span data-stu-id="536ea-107">You can also follow the [Budget planning 101](budget-plan.md) tutorial to learn basic module configuration and usage principles.</span></span>

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a><span data-ttu-id="536ea-108">Generowanie arkusza przy użyciu układu dokumentu planu budżetu</span><span class="sxs-lookup"><span data-stu-id="536ea-108">Generate a worksheet using budget plan document layout</span></span>

<span data-ttu-id="536ea-109">Dokumenty planu budżetu można wyświetlać i edytować za pomocą jednego lub więcej układów.</span><span class="sxs-lookup"><span data-stu-id="536ea-109">Budget plan documents can be viewed and edited using one or more layouts.</span></span> <span data-ttu-id="536ea-110">Z każdym układem może być skojarzony szablon dokumentu planu budżetu, który umożliwia wyświetlanie i edytowanie danych planu budżetu w arkuszu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-110">Each layout can have an associated budget plan document template to view and edit the budget plan data in an Excel worksheet.</span></span> <span data-ttu-id="536ea-111">W tym temacie szablon dokumentu planu budżetu zostanie wygenerowany przy użyciu istniejącej konfiguracji układu.</span><span class="sxs-lookup"><span data-stu-id="536ea-111">In this topic, a budget plan document template will be generated using an existing layout configuration.</span></span> 

1. <span data-ttu-id="536ea-112">Otwórz **listę planów budżetu** (**Budżetowanie** &gt; **Plany budżetu**).</span><span class="sxs-lookup"><span data-stu-id="536ea-112">Open the **Budget plans list** (**Budgeting** &gt; **Budget plans**).</span></span> 
2. <span data-ttu-id="536ea-113">Kliknij przycisk **Nowy**, aby utworzyć nowy dokument planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-113">Click **New** to create a new budget plan document.</span></span> 

   <span data-ttu-id="536ea-114">[![Lista planów budżetu](./media/bpt11-1024x552.png)](./media/bpt11.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-114">[![Budget plans list](./media/bpt11-1024x552.png)](./media/bpt11.png)</span></span> 

3. <span data-ttu-id="536ea-115">Za pomocą opcji wierszy **Dodaj** dodaj wiersze.</span><span class="sxs-lookup"><span data-stu-id="536ea-115">Use the **Add** line option to add lines.</span></span> <span data-ttu-id="536ea-116">Kliknij opcję **Układy**, aby wyświetlić konfigurację układu dokumentu planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-116">Click **Layouts** to view the budget plan document layout configuration.</span></span> 

   <span data-ttu-id="536ea-117">[![Dodawanie planów budżetu](./media/bpt2-1024x274.png)](./media/bpt2.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-117">[![Budget plans add](./media/bpt2-1024x274.png)](./media/bpt2.png)</span></span> 

<span data-ttu-id="536ea-118">Możesz przejrzeć konfigurację układu i dostosować ją w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="536ea-118">You can review the layout configuration and adjust it as needed.</span></span> 
1. <span data-ttu-id="536ea-119">Wybierz kolejno opcje **Szablon** &gt; **Generuj**, aby utworzyć plik programu Excel dla tego układu.</span><span class="sxs-lookup"><span data-stu-id="536ea-119">Go to **Template** &gt; **Generate** to create an Excel file for this layout.</span></span> 
2. <span data-ttu-id="536ea-120">Po wygenerowaniu szablonu przejdź do opcji **Szablon** &gt; **Widok** i otwórz oraz przejrzyj szablon dokumentu planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-120">After the template is generated, go to **Template** &gt; **View** to open and review the budget plan document template.</span></span> <span data-ttu-id="536ea-121">Plik programu Excel można zapisać na lokalnym dysku.</span><span class="sxs-lookup"><span data-stu-id="536ea-121">You can save the Excel file to your local drive.</span></span> 

<span data-ttu-id="536ea-122">[![Zapisz jako](./media/bpt3-1024x545.png)](./media/bpt3.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-122">[![Save as](./media/bpt3-1024x545.png)](./media/bpt3.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="536ea-123">Nie można edytować układu dokumentu planu budżetu, gdy zostanie z nim skojarzony szablon program Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-123">The Budget plan document layout cannot be edited after an Excel template is associated with it.</span></span> <span data-ttu-id="536ea-124">Aby zmodyfikować układ, należy usunąć skojarzony plik szablonu programu Excel i wygenerować układ ponownie.</span><span class="sxs-lookup"><span data-stu-id="536ea-124">To modify the layout, delete the associated Excel template file and regenerate it.</span></span> <span data-ttu-id="536ea-125">Jest to niezbędne, aby zachować synchronizację pól w układzie i arkuszu.</span><span class="sxs-lookup"><span data-stu-id="536ea-125">This is required to keep the fields in the layout and the worksheet synchronized.</span></span> 

<span data-ttu-id="536ea-126">Szablon programu Excel będzie zawierał wszystkie elementy z układu dokumentu planu budżetu, gdzie kolumna **Dostępny w arkuszu** jest ustawiona na Prawda.</span><span class="sxs-lookup"><span data-stu-id="536ea-126">The Excel template will contain all of the elements from the budget plan document layout, where the **Available in Worksheet** column is set to True.</span></span> <span data-ttu-id="536ea-127">Nakładające się elementy są niedozwolone w szablonie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-127">Overlapping elements are not allowed in the Excel template.</span></span> <span data-ttu-id="536ea-128">Na przykład jeśli układ zawiera kolumny Wniosek K1, Wniosek K2, Wniosek K3 i Wniosek K4 oraz kolumnę łącznej kwoty wniosku reprezentującą sumę wszystkich 4 kolumn kwartalnych, w szablonie programu Excel do użycia będą dostępne tylko indywidualne kolumny kwartalne lub kolumna wartości łącznej.</span><span class="sxs-lookup"><span data-stu-id="536ea-128">For example, if the layout contains Request Q1, Request Q2, Request Q3, and Request Q4 columns, and a total request column that represents a sum of all 4 quarterly columns, only the quarterly columns or total column is available to be used in the Excel template.</span></span> <span data-ttu-id="536ea-129">Podczas aktualizacji nie można zaktualizować nakładających się kolumn w pliku programu Excel, ponieważ dane w tabeli mogłyby stać się nieaktualne i błędne.</span><span class="sxs-lookup"><span data-stu-id="536ea-129">The Excel file cannot update overlapping columns during the update because data in the table could become out of date and inaccurate.</span></span>

<span data-ttu-id="536ea-130">[![Przykład ](./media/bpt4-1024x615.png)](./media/bpt4.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-130">[![Example](./media/bpt4-1024x615.png)](./media/bpt4.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="536ea-131">Aby uniknąć potencjalnych problemów z wyświetlaniem i edytowaniem danych planu budżetu za pomocą programu Excel, ten sam użytkownik powinien być zalogowany w programie Microsoft Dynamics 365 for Finance and Operations oraz łączniku danych dodatku pakietu Office dla usługi Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="536ea-131">To avoid potential issues with viewing and editing budget plan data using Excel, the same user should be logged into both Microsoft Dynamics 365 for Finance and Operations and the Microsoft Dynamics Office Add-in Data Connector.</span></span>

## <a name="add-a-header-to-budget-plan-document-template"></a><span data-ttu-id="536ea-132">Dodawanie nagłówka do szablonu dokumentu planu budżetu</span><span class="sxs-lookup"><span data-stu-id="536ea-132">Add a header to budget plan document template</span></span>
<span data-ttu-id="536ea-133">Aby dodać informacje nagłówka, zaznacz górny wiersz w pliku programu Excel i wstaw puste wiersze.</span><span class="sxs-lookup"><span data-stu-id="536ea-133">To add header information, select the top row in the Excel file and insert empty rows.</span></span> <span data-ttu-id="536ea-134">W obszarze **Łącznik danych** kliknij opcję **Projekt** i dodaj pola nagłówka do pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-134">Click **Design** in the **Data Connector** to add header fields to the Excel file.</span></span>

<span data-ttu-id="536ea-135">[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-135">[![bpt5](./media/bpt5-1024x615.png)](./media/bpt5.png)</span></span> 

<span data-ttu-id="536ea-136">Na karcie **Projekt** kliknij pola **Dodaj**, a następnie wybierz pozycję **BudgetPlanHeader** jako źródło danych jednostki.</span><span class="sxs-lookup"><span data-stu-id="536ea-136">In the **Design** tab, click **Add** fields, and then select **BudgetPlanHeader** as the entity data source.</span></span>

<span data-ttu-id="536ea-137">[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-137">[![bpt6](./media/bpt6-1024x615.png)](./media/bpt6.png)</span></span>

<span data-ttu-id="536ea-138">Ustaw kursor w żądanym miejscu w pliku programu Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-138">Point the cursor to the desired location in the Excel file.</span></span> <span data-ttu-id="536ea-139">Kliknij przycisk **Dodaj etykietę**, aby dodać etykietę pola w wybranym miejscu.</span><span class="sxs-lookup"><span data-stu-id="536ea-139">Click **Add label** to add the field label to the selected location.</span></span> <span data-ttu-id="536ea-140">Kliknij przycisk **Dodaj wartość**, aby dodać pole wartości w wybranym miejscu.</span><span class="sxs-lookup"><span data-stu-id="536ea-140">Select **Add Value** to add the value field to the selected place.</span></span> <span data-ttu-id="536ea-141">Kliknij przycisk **Gotowe**, aby zamknąć projektanta.</span><span class="sxs-lookup"><span data-stu-id="536ea-141">Click **Done** to close the designer.</span></span>

## <a name="bpt7mediabpt7pngmediabpt7png"></a><span data-ttu-id="536ea-142">[![bpt7](./media/bpt7.png)](./media/bpt7.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-142">[![bpt7](./media/bpt7.png)](./media/bpt7.png)</span></span>

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a><span data-ttu-id="536ea-143">Dodawanie kolumny obliczanej do tabeli szablonu dokumentu planu budżetu</span><span class="sxs-lookup"><span data-stu-id="536ea-143">Add a calculated column to budget plan document template table</span></span>
--------------------------------------------------------------

<span data-ttu-id="536ea-144">Następnie kolumny obliczane zostaną dodane do wygenerowanego szablonu dokumentu planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-144">Next, calculated columns will be added to generated budget plan document template.</span></span> <span data-ttu-id="536ea-145">Kolumna **Wniosek razem**, która sumuje wartości kolumn od Wniosek K1 do Wniosek K4, oraz kolumna **Korekta**, która przelicza wartość w kolumnie **Wniosek razem** o ustawiony wcześniej współczynnik.</span><span class="sxs-lookup"><span data-stu-id="536ea-145">A **Total request** column, which summarizes Request Q1: Request Q4 columns, and an **Adjustment** column, which recalculates the **Total Request** column by a predefined factor.</span></span>

<span data-ttu-id="536ea-146">W obszarze **Łącznik danych** kliknij opcję **Projekt** i dodaj kolumny do tabeli.</span><span class="sxs-lookup"><span data-stu-id="536ea-146">Click **Design** in the **Data connector** to add columns to the table.</span></span> <span data-ttu-id="536ea-147">Obok źródła danych **BudgetPlanWorksheet** kliknij przycisk **Edytuj**, aby rozpocząć dodawanie kolumn.</span><span class="sxs-lookup"><span data-stu-id="536ea-147">Click **Edit** next to **BudgetPlanWorksheet** data source to start adding columns.</span></span>

<span data-ttu-id="536ea-148">[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-148">[![bpt8](./media/bpt8-1024x301.png)](./media/bpt8.png)</span></span> 

<span data-ttu-id="536ea-149">Wybrana grupa pól pokazuje kolumny dostępne w szablonie.</span><span class="sxs-lookup"><span data-stu-id="536ea-149">The selected field group displays the columns that are available in the template.</span></span> <span data-ttu-id="536ea-150">Kliknij przycisk **Formuła**, aby dodać nową kolumnę.</span><span class="sxs-lookup"><span data-stu-id="536ea-150">Click **Formula** to add a new column.</span></span> <span data-ttu-id="536ea-151">Nazwij nową kolumnę, a następnie wklej wzór do pola **Formuła**.</span><span class="sxs-lookup"><span data-stu-id="536ea-151">Name the new column and then paste the formula into the **Formula** field.</span></span> <span data-ttu-id="536ea-152">Kliknij przycisk **Aktualizuj**, aby wstawić kolumnę.</span><span class="sxs-lookup"><span data-stu-id="536ea-152">Click **Update** to insert the column.</span></span>

<span data-ttu-id="536ea-153">[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-153">[![bpt12](./media/bpt12-1024x565.png)](./media/bpt12.png)</span></span>

> [!NOTE] 
> <span data-ttu-id="536ea-154">Aby zdefiniować formułę (wzór), utwórz ją w arkuszu kalkulacyjnym, a następnie skopiuj do okna **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="536ea-154">To define the formula, create the formula in the spreadsheet, and then copy it to the **Design** window.</span></span> <span data-ttu-id="536ea-155">Tabela powiązana z programem Finance and Operations zazwyczaj nosi nazwę „AXTable1”.</span><span class="sxs-lookup"><span data-stu-id="536ea-155">A Finance and Operations bound table will typically be named "AXTable1".</span></span> <span data-ttu-id="536ea-156">Na przykład aby podsumować kolumny Wniosek K1: Wniosek K4 w arkuszu kalkulacyjnym, formuła ma postać = AxTable1\[Wniosek K1\]+AxTable1\[Wniosek K2\]+AxTable1\[Wniosek K3\]+AxTable1\[Wniosek K4\].</span><span class="sxs-lookup"><span data-stu-id="536ea-156">For example, to summarize Request Q1 : Request Q4 columns in the spreadsheet, the formula = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\].</span></span>

<span data-ttu-id="536ea-157">Powtórz te kroki, aby wstawić kolumnę **Korekta**.</span><span class="sxs-lookup"><span data-stu-id="536ea-157">Repeat these steps to insert the **Adjustment** column.</span></span> <span data-ttu-id="536ea-158">Dla tej kolumny użyj formuły = AxTable1\[Wniosek razem\]\*$I$1.</span><span class="sxs-lookup"><span data-stu-id="536ea-158">Use formula = AxTable1\[Total request\]\*$I$1 for this column.</span></span> <span data-ttu-id="536ea-159">Spowoduje to pobranie wartości z komórki I1 i pomnożenie jej przez wartości z kolumny **Wniosek razem** w celu obliczania kwot korekt.</span><span class="sxs-lookup"><span data-stu-id="536ea-159">This will take the value in cell I1 and multiply the values in the **Total request** column to calculate adjustment amounts.</span></span>

<span data-ttu-id="536ea-160">Zapisz i zamknij plik programu Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-160">Save and close the Excel file.</span></span> <span data-ttu-id="536ea-161">Wróć do programu Finance and Operations i w obszarze **Układy** kliknij kolejno opcje **Szablon &gt; Przekaż**, aby przekazać zapisany szablon programu Excel przeznaczony do używania w planie budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-161">Return to Finance and Operations, and in **Layouts**, click **Template &gt; Upload** to upload the saved Excel template to be used for the budget plan.</span></span> 

<span data-ttu-id="536ea-162">[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-162">[![bpt10](./media/bpt10-1024x352.png)](./media/bpt10.png)</span></span> 

<span data-ttu-id="536ea-163">Zamknij suwak **Układy**.</span><span class="sxs-lookup"><span data-stu-id="536ea-163">Close the **Layouts** slider.</span></span> <span data-ttu-id="536ea-164">W dokumencie **Plan budżetu** kliknij opcję **Arkusz**, aby wyświetlić i edytować dokument w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-164">In **Budget plan** document, click **Worksheet** to view and edit the document in Excel.</span></span> <span data-ttu-id="536ea-165">Należy zauważyć, że do utworzenia tego arkusza planu budżetu został użyty skorygowany szablon programu Excel, a kolumny obliczane są aktualizowane przy użyciu formuł zdefiniowanych w poprzednich krokach.</span><span class="sxs-lookup"><span data-stu-id="536ea-165">Note that the adjusted Excel template was used to create this budget plan worksheet and calculated columns are updated using the formulas that were defined in the previous steps.</span></span> 

<span data-ttu-id="536ea-166">[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-166">[![bpt11](./media/bpt111-1024x431.png)](./media/bpt111.png)</span></span>

## <a name="tips--tricks-for-creating-budget-plan-templates"></a><span data-ttu-id="536ea-167">Porady i wskazówki dotyczące tworzenia szablonów planu budżetu</span><span class="sxs-lookup"><span data-stu-id="536ea-167">Tips & tricks for creating budget plan templates</span></span>
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a><span data-ttu-id="536ea-168">Czy można dodać i używać więcej źródeł danych do szablonu planu budżetu?</span><span class="sxs-lookup"><span data-stu-id="536ea-168">Can I add and use additional data sources to a budget plan template?</span></span>

<span data-ttu-id="536ea-169">Tak, za pomocą menu **Projekt** można dodać więcej jednostek do tego samego lub innych arkuszy w szablonie programu Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-169">Yes, you can use the **Design** menu to add additional entities to the same or other sheets in the Excel template.</span></span> <span data-ttu-id="536ea-170">Na przykład można dodać źródło danych **BudgetPlanProposedProject**, aby utworzyć i prowadzić listę proponowanych projektów w tym samym czasie, kiedy pracujesz z danymi planu budżetu w programie Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-170">For example, you can add the **BudgetPlanProposedProject** data source to create and maintain a list of proposed projects at the same time when working with budget plan data in Excel.</span></span> <span data-ttu-id="536ea-171">Należy zauważyć, że dołączenie dużych źródeł danych może mieć negatywny wpływ na działanie skoroszytu programu Excel.</span><span class="sxs-lookup"><span data-stu-id="536ea-171">Note that including high-volume data sources might impact performance of the Excel workbook.</span></span> 

<span data-ttu-id="536ea-172">Można użyć opcji **Filtr** w obszarze **Łącznik danych**, aby dodać żądane filtry do dodatkowych źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="536ea-172">You can use the **Filter** option in the **Data Connector** to add desired filters to additional data sources.</span></span>

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a><span data-ttu-id="536ea-173">Czy można ukryć opcję Projekt w obszarze Łącznik danych dla innych użytkowników?</span><span class="sxs-lookup"><span data-stu-id="536ea-173">Can I hide the Design option in the Data connector for other users?</span></span>

<span data-ttu-id="536ea-174">Tak, otwórz opcje narzędzia **Łącznik danych** i tam można schować opcję **Projekt** przed innymi użytkownikami.</span><span class="sxs-lookup"><span data-stu-id="536ea-174">Yes, open the **Data Connector** options to hide the **Design** option from other users.</span></span>

<span data-ttu-id="536ea-175">[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-175">[![bpt13](./media/bpt13-1024x565.png)](./media/bpt13.png)</span></span>

<span data-ttu-id="536ea-176">Rozwiń opcje narzędzia **Łącznik danych** i wyczyść pole wyboru **Włącz projekt**.</span><span class="sxs-lookup"><span data-stu-id="536ea-176">Expand **Data connector options** and clear the **Enable design** check box.</span></span> <span data-ttu-id="536ea-177">Opcja **Projekt** przestanie być widoczna w obszarze **Łącznik danych**.</span><span class="sxs-lookup"><span data-stu-id="536ea-177">This will hide the **Design** option from the **Data connector**.</span></span>

<span data-ttu-id="536ea-178">[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-178">[![bpt14](./media/bpt14-1024x592.png)](./media/bpt14.png)</span></span>

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a><span data-ttu-id="536ea-179">Czy można uniemożliwić użytkownikom przypadkowe zamknięcie łącznika danych podczas pracy z danymi?</span><span class="sxs-lookup"><span data-stu-id="536ea-179">Can I prevent users from accidently closing the Data connector while working with data?</span></span>

<span data-ttu-id="536ea-180">Zalecamy zablokowanie szablonu, aby uniemożliwić użytkownikom jego zamknięcie.</span><span class="sxs-lookup"><span data-stu-id="536ea-180">We recommend locking the template to prevent users from closing it.</span></span> <span data-ttu-id="536ea-181">Aby włączyć blokadę, kliknij przycisk **Łącznik danych** w prawym górnym rogu. Pojawi się strzałka.</span><span class="sxs-lookup"><span data-stu-id="536ea-181">To turn on the lock, click the **Data connector**, in the top right corner an arrow appears.</span></span> 

<span data-ttu-id="536ea-182">[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-182">[![bpt15](./media/bpt15-1024x285.png)](./media/bpt15.png)</span></span> 

<span data-ttu-id="536ea-183">Kliknij strzałkę, a pojawi się dodatkowe menu.</span><span class="sxs-lookup"><span data-stu-id="536ea-183">Click the arrow for an additional menu.</span></span> <span data-ttu-id="536ea-184">Wybierz opcję **Blokowanie**.</span><span class="sxs-lookup"><span data-stu-id="536ea-184">Select **Lock**.</span></span>

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a><span data-ttu-id="536ea-185">[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-185">[![bpt16](./media/bpt16-1024x614.png)](./media/bpt16.png)</span></span>

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a><span data-ttu-id="536ea-186">Czy w moich szablonach planu budżetu mogę używać innych funkcji programu Excel, takich jak formatowanie komórek, kolory, formatowanie warunkowe i wykresy?</span><span class="sxs-lookup"><span data-stu-id="536ea-186">Can I use other Excel features, like cell formatting, colors, conditional formatting, and charts with my budget plan templates?</span></span>

<span data-ttu-id="536ea-187">Tak, większość standardowych funkcji programu Excel będzie działać w szablonach planu budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-187">Yes, most of the standard Excel capabilities will work in budget plan templates.</span></span> <span data-ttu-id="536ea-188">Zalecamy użytkownikom stosowanie kolorów do rozróżniania między kolumnami tylko do odczytu i edytowalnymi.</span><span class="sxs-lookup"><span data-stu-id="536ea-188">We recommend using color-coding for users to distinguish between read-only and editable columns.</span></span> <span data-ttu-id="536ea-189">Formatowanie warunkowe może służyć do wyróżniania problematycznych obszarów budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-189">Conditional formatting can be used to highlight problematic areas of the budget.</span></span> <span data-ttu-id="536ea-190">Sumy kolumn można łatwo przedstawiać za pomocą standardowych formuł programu Excel nad tabelą.</span><span class="sxs-lookup"><span data-stu-id="536ea-190">Column totals can easily be presented by using standard Excel formulas above the table.</span></span>

<span data-ttu-id="536ea-191">Można również tworzyć i używać tabel i wykresów przestawnych w celu dodatkowego grupowania i wizualizacji danych budżetu.</span><span class="sxs-lookup"><span data-stu-id="536ea-191">You can also create and use pivot tables and charts for additional groupings and visualizations of budget data.</span></span> <span data-ttu-id="536ea-192">Na karcie **Dane** w grupie **Połączenia** kliknij przycisk **Odśwież wszystko**, a następnie kliknij opcję **Właściwości połączenia**.</span><span class="sxs-lookup"><span data-stu-id="536ea-192">On the **Data** tab, in the **Connections** group, click **Refresh All**, and then click **Connection Properties**.</span></span> <span data-ttu-id="536ea-193">Kliknij kartę **Użycie**. W obszarze **Odśwież** zaznacz pole wyboru **Odśwież dane podczas otwierania pliku**.</span><span class="sxs-lookup"><span data-stu-id="536ea-193">Click the **Usage** tab. Under **Refresh**, select the **Refresh data when opening the file** check box.</span></span> 

<span data-ttu-id="536ea-194">[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)</span><span class="sxs-lookup"><span data-stu-id="536ea-194">[![bpt17](./media/bpt17-1024x614.png)](./media/bpt17.png)</span></span>




