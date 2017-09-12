---
title: "Organizowanie składników raportu w projektancie raportów"
description: "Po zaprojektowaniu bloków konstrukcyjnych i wygenerowaniu raportów przydatne jest zorganizowania tych obiektów, tak aby użytkownicy mogli je łatwiej znaleźć. W tym artykule wyjaśniono, jak organizować istniejące raporty, bloki konstrukcyjne i obiekty w projektancie raportów."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: fade9e2acdb94daa6a908d949c578fd7ed439882
ms.contentlocale: pl-pl
ms.lasthandoff: 07/18/2017

---

# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="1ae9f-104">Organizowanie składników raportu w projektancie raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-104">Organize report components in report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1ae9f-105">Po zaprojektowaniu bloków konstrukcyjnych i wygenerowaniu raportów przydatne jest zorganizowania tych obiektów, tak aby użytkownicy mogli je łatwiej znaleźć.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="1ae9f-106">W tym artykule wyjaśniono, jak organizować istniejące raporty, bloki konstrukcyjne i obiekty w projektancie raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="1ae9f-107">Można zmieniać nazwy folderów, raportów, bloków konstrukcyjnych i innych obiektów w projektancie raportów, aby ułatwić organizowanie plików.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="1ae9f-108">W zależności od typu obiektu, którego nazwa jest zmieniana, może być konieczna aktualizacja skojarzeń z tym obiektem.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="1ae9f-109">Zmienianie nazwy folderu lub bloku konstrukcyjnego w Projektancie raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="1ae9f-110">W Projektancie raportów można zmieniać nazwy folderów, definicje raportów, definicje wierszy, definicje kolumn i definicje drzewa raportowania.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span> <span data-ttu-id="1ae9f-111">**Uwaga:** Po zmianie nazwy bloku konstrukcyjnego należy zaktualizować wszelkie definicje raportowania, które używają tego bloku.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-111">**Note:** When you rename a building block, you must update any reporting definitions that use the building block.</span></span> <span data-ttu-id="1ae9f-112">W przeciwnym razie nie można wygenerować nowego raportu.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-112">Otherwise, a new report can't be generated.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="1ae9f-113">Zmienianie nazwy folderu lub bloku konstrukcyjnego w Projektancie raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-113">Rename a folder or building block in Report Designer</span></span>

1.  <span data-ttu-id="1ae9f-114">W Konstruktorze raportów użyj okienka nawigacji, by znaleźć folder lub obiekt, którego nazwę chcesz zmienić.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-114">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2.  <span data-ttu-id="1ae9f-115">Kliknij prawym przyciskiem myszy folder lub obiekt, a następnie kliknij przycisk **Zmień nazwę**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-115">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="1ae9f-116">Pole **Nazwa** w okienku nawigacji staje się dostępne.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-116">The **Name** field in the navigation pane becomes available.</span></span>
3.  <span data-ttu-id="1ae9f-117">Wpisz nową nazwę, a następnie naciśnij klawisz Enter.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-117">Type a new name, and then press Enter.</span></span>
4.  <span data-ttu-id="1ae9f-118">Jeśli blok konstrukcyjny jest definicją wiersza, kolumny lub drzewa raportowania, należy zaktualizować pozostałe skojarzone z nim bloki konstrukcyjne.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-118">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="1ae9f-119">Kliknij prawym przyciskiem myszy blok konstrukcyjny, którego nazwa została zmieniona w kroku 3, wybierz opcję **Skojarzenia**, a następnie wybierz pozycję na liście, aby ją zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-119">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5.  <span data-ttu-id="1ae9f-120">Powtórz krok 4, dopóki nie zostaną zaktualizowane wszystkie powiązane elementy.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-120">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="1ae9f-121">Umożliwia tworzenie grup raportów i zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-121">Create and manage report groups</span></span>
<span data-ttu-id="1ae9f-122">Można grupować definicje raportów, by generować wiele raportów w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-122">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="1ae9f-123">Do tworzenia, modyfikowania, usuwania i generowania grup raportów wymagana jest rola projektanta lub administratora.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-123">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="1ae9f-124">Użytkownicy z rolą generatora mogą tworzyć grupy raportów, a także modyfikować ustawienie dotyczące definicji raportów użytkownika dla grup raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-124">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="1ae9f-125">Tworzenie grupy raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-125">Create a report group</span></span>

1.  <span data-ttu-id="1ae9f-126">W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-126">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="1ae9f-127">W menu **Plik** kliknij kolejno opcje **Nowy** &gt; **Definicja grupy raportów**, aby otworzyć nową grupę raportów w oknie podglądu.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-127">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="1ae9f-128">Alternatywnie kliknij przycisk **Grupa raportów** ![Grupa raportów](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Grupa raportów") na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-128">Alternatively, click the **Report Group** button ![Report Group](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Report Group") on the toolbar.</span></span>
3.  <span data-ttu-id="1ae9f-129">Kliknij kartę **Grupa raportów**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-129">Click the **Report Group** tab.</span></span> <span data-ttu-id="1ae9f-130">Aby zastąpić informacje o definicjach poszczególnych raportów do generowania tego raportu, zaznacz pole wyboru **Zastąp ustawienia firmy, szczegółów i daty z poszczególnych definicji raportów**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-130">To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="1ae9f-131">Nazwa firmy, poziom szczegółowości, ustawienie tymczasowości i informacje o datach są wypełniane automatycznie, ale można je aktualizować.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-131">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4.  <span data-ttu-id="1ae9f-132">Aby wygenerować wiele raportów z walutami raportowania, zaznacz pole wyboru **Uwzględnij wszystkie waluty raportowania**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-132">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="1ae9f-133">Następnie podczas oglądania raportów w przeglądarce sieci web można kliknąć przycisk **Waluta**, a będzie dostępnych wiele widoków.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-133">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5.  <span data-ttu-id="1ae9f-134">W polu **Raporty w grupie** kliknij opcję **Dodaj**, aby wybrać raporty w celu ich dodania do grupy raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-134">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="1ae9f-135">Aby wybrać wiele raportów w oknie dialogowym **Dodaj**, przytrzymaj klawisz Ctrl podczas wybierania raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-135">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="1ae9f-136">Po zakończeniu wybierania raportów kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-136">When you've finished selecting reports, click **OK**.</span></span>
6.  <span data-ttu-id="1ae9f-137">Kliknij kolejno opcje **Plik** &gt; **Zapisz**, aby zapisać nową grupę raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-137">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="1ae9f-138">Modyfikowanie grupy raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-138">Modify a report group</span></span>

1.  <span data-ttu-id="1ae9f-139">W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-139">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="1ae9f-140">Kliknij dwukrotnie grupę raportów, którą chcesz zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-140">Double-click the report group to modify.</span></span>
3.  <span data-ttu-id="1ae9f-141">Na karcie **Grupa raportów** wprowadź żądane zmiany.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-141">On the **Report Group** tab, make the changes that you want.</span></span>
4.  <span data-ttu-id="1ae9f-142">W menu **Plik** kliknij polecenie **Zapisz**, aby zapisać zmodyfikowaną grupę raportów. Alternatywnie kliknij przycisk **Zapisz** ![Zapisz](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Zapisz") na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-142">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Save") on the toolbar.</span></span>

<span data-ttu-id="1ae9f-143">**Uwaga:** Jeśli masz zaplanowane raporty do generowania w ustalonych odstępach czasu, można zastąpić te ustawienia i natychmiast wygenerować raport.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-143">**Note:** If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="1ae9f-144">Generowanie raportu grupy raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-144">Generate a report group report</span></span>

1.  <span data-ttu-id="1ae9f-145">W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="1ae9f-146">Otwórz grupę raportów do wygenerowania.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-146">Open the report group to generate.</span></span>
3.  <span data-ttu-id="1ae9f-147">Kliknij przycisk **Generuj raport** ![Generuj raport](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generuj raport"), aby wygenerować raport.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-147">Click the **Generate Report** button ![Generate Report](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="1ae9f-148">Usuwanie grupy raportu</span><span class="sxs-lookup"><span data-stu-id="1ae9f-148">Delete a report group</span></span>

1.  <span data-ttu-id="1ae9f-149">W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-149">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="1ae9f-150">Kliknij prawym przyciskiem myszy grupę raportów, którą chcesz usunąć, i wybierz polecenie **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-150">Right-click the report group to delete, and then select **Delete**.</span></span>
3.  <span data-ttu-id="1ae9f-151">Gdy pojawi się komunikat potwierdzający, kliknij przycisk **Tak**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-151">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="1ae9f-152">Formanty karty Grupa raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-152">Report Group tab controls</span></span>
<span data-ttu-id="1ae9f-153">W poniższej tabeli opisano formanty istniejące na karcie **Grupa raportów**.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-153">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ae9f-154">Kontrola</span><span class="sxs-lookup"><span data-stu-id="1ae9f-154">Control</span></span></th>
<th><span data-ttu-id="1ae9f-155">Opis</span><span class="sxs-lookup"><span data-stu-id="1ae9f-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1ae9f-156">Zastępowanie firmy, szczegółów i ustawień danych z indywidualnych definicji raportów</span><span class="sxs-lookup"><span data-stu-id="1ae9f-156">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="1ae9f-157">Zaznaczenie tego pola wyboru umożliwia zastąpienie indywidualnych definicji raportów w danej grupie raportów tylko pod kątem generowania tych raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-157">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1ae9f-158">Nazwa firmy</span><span class="sxs-lookup"><span data-stu-id="1ae9f-158">Company name</span></span></td>
<td><span data-ttu-id="1ae9f-159">Wybierz firmę do użytku w tych raportach.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-159">Select the company to use for the reports.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1ae9f-160">Poziom podsumowania</span><span class="sxs-lookup"><span data-stu-id="1ae9f-160">Detail level</span></span></td>
<td><span data-ttu-id="1ae9f-161">Określ poziom szczegółowości raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-161">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="1ae9f-162"><strong>Finanse</strong> — raport wysokiego poziomu.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-162"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="1ae9f-163">Nie można wyświetlić szczegółów kont i wymiarów, z wyjątkiem tych, które zostały dodane przy użyciu drzewa raportowania.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-163">You can't drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="1ae9f-164"><strong>Finanse i konto</strong> — raport zawierający ogólne podsumowanie i szczegóły konta.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-164"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="1ae9f-165"><strong>Finanse, konto i transakcja</strong> — raport zawierający ogólne podsumowanie i szczegóły transakcji.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-165"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1ae9f-166">Tymczasowe</span><span class="sxs-lookup"><span data-stu-id="1ae9f-166">Provisional</span></span></td>
<td><span data-ttu-id="1ae9f-167">Określ typy działań objętych raportami.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-167">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="1ae9f-168"><strong>Tylko zaksięgowane działania</strong> — obejmują tylko transakcje i salda, które są zaksięgowane w danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-168"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="1ae9f-169"><strong>Działania zaksięgowane i niezaksięgowane</strong> — obejmują wszystkie transakcje i salda, które zostały wprowadzone i zaksięgowane w danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-169"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="1ae9f-170"><strong>Tylko niezaksięgowane działania</strong> — obejmują tylko transakcje i salda, które zostały wprowadzone, ale nie są jeszcze zaksięgowane w danych finansowych.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-170"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1ae9f-171">Uwzględnij wszystkie waluty raportowania</span><span class="sxs-lookup"><span data-stu-id="1ae9f-171">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="1ae9f-172">W tym miejscu są wyświetlone wszelkie dodatkowe waluty raportowania skonfigurowane w systemie Microsoft Dynamics ERP.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-172">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="1ae9f-173">Zaznacz to pole wyboru, aby generować dodatkowe raporty we wskazanych walutach.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-173">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="1ae9f-174">Aby wyświetlić te raporty w przeglądarce sieci web, kliknij przycisk <strong>Waluta</strong> i wybierając walutę.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-174">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1ae9f-175">Informacje o dacie niezapisane w definicji raportu</span><span class="sxs-lookup"><span data-stu-id="1ae9f-175">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="1ae9f-176">Okres podstawowy</span><span class="sxs-lookup"><span data-stu-id="1ae9f-176">Base period</span></span></li>
<li><span data-ttu-id="1ae9f-177">Rok podstawowy</span><span class="sxs-lookup"><span data-stu-id="1ae9f-177">Base year</span></span></li>
<li><span data-ttu-id="1ae9f-178">Objęty okres</span><span class="sxs-lookup"><span data-stu-id="1ae9f-178">Period covered</span></span></li>
</ul>
<span data-ttu-id="1ae9f-179">W definicji raportu są zapisywane tylko ustawienia domyślnego okresu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-179">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1ae9f-180">Informacje o dacie nie są zapisane w definicji raportu</span><span class="sxs-lookup"><span data-stu-id="1ae9f-180">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="1ae9f-181">Data raportu</span><span class="sxs-lookup"><span data-stu-id="1ae9f-181">Report date</span></span></li>
<li><span data-ttu-id="1ae9f-182">Domyślny okres podstawowy</span><span class="sxs-lookup"><span data-stu-id="1ae9f-182">Default base period</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1ae9f-183">Raporty w grupie</span><span class="sxs-lookup"><span data-stu-id="1ae9f-183">Reports in group</span></span></td>
<td><span data-ttu-id="1ae9f-184">Dodawanie, usuwanie i zmienianie kolejności raportów w grupie raportów.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-184">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="1ae9f-185">Aby dodać definicje raportów do grupy raportów, kliknij dwukrotnie grupę raportów, aby ją otworzyć, a następnie kliknij <strong>Dodaj</strong>.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-185">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="1ae9f-186">Wybierz raporty, które mają znaleźć się w grupie raportów, a następnie kliknij <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-186">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="1ae9f-187">Aby usunąć raport z grupy raportów, wybierz go, a następnie kliknij <strong>Usuń</strong>.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-187">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="1ae9f-188">Aby zmodyfikować kolejność, w jakiej raporty są generowane, wybierz raport na liście, a następnie kliknij przycisk <strong>Przenieś w górę</strong> lub <strong>Przenieś w dół</strong>.</span><span class="sxs-lookup"><span data-stu-id="1ae9f-188">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="1ae9f-189">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1ae9f-189">See also</span></span>
--------

[<span data-ttu-id="1ae9f-190">Raporty finansowe</span><span class="sxs-lookup"><span data-stu-id="1ae9f-190">Financial reporting</span></span>](financial-reporting-intro.md)




