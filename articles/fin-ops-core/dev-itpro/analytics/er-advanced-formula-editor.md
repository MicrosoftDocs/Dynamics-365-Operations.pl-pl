---
title: Zaawansowany edytor formuł raportów elektronicznych
description: W tym temacie opisano sposób, w jaki można użyć Zaawansowanego edytora formuł w celu skonfigurowania wyrażeń w mapowaniu modelu raportowania elektronicznego (ER) i formatu składników.
author: NickSelin
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: d18aeedb2f21176ffe964b926168d4bf088a093b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751215"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="2d1bb-103">Zaawansowany edytor formuł raportów elektronicznych</span><span class="sxs-lookup"><span data-stu-id="2d1bb-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d1bb-104">Poza [elektronicznym raportowaniem](general-electronic-reporting.md) [edytor formuł](general-electronic-reporting-formula-designer.md), można stosować zaawansowane edytory formuł elektronicznego raportowania, aby usprawnić proces konfigurowania wyrażeń modułu raportowanie elektroniczne (er).</span><span class="sxs-lookup"><span data-stu-id="2d1bb-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="2d1bb-105">Edytor zaawansowany jest oparty na przeglądarce i obsługiwany przez [Edytor Monaco](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="2d1bb-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="2d1bb-106">W tym temacie opisano najczęściej używane funkcje edytora zaawansowanego:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="2d1bb-107">Autoformatowanie kodu</span><span class="sxs-lookup"><span data-stu-id="2d1bb-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="2d1bb-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="2d1bb-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="2d1bb-109">Zakończenie kodu</span><span class="sxs-lookup"><span data-stu-id="2d1bb-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="2d1bb-110">Nawigacja kodu</span><span class="sxs-lookup"><span data-stu-id="2d1bb-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="2d1bb-111">Tworzenie struktury kodu</span><span class="sxs-lookup"><span data-stu-id="2d1bb-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="2d1bb-112">Znajdź i zastąp</span><span class="sxs-lookup"><span data-stu-id="2d1bb-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="2d1bb-113">Wklejanie danych</span><span class="sxs-lookup"><span data-stu-id="2d1bb-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="2d1bb-114">Kolorowanie składni</span><span class="sxs-lookup"><span data-stu-id="2d1bb-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="2d1bb-115"><a name="ActivateAdvEditor">Uaktywnianie zaawansowanego edytora formuł</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="2d1bb-116">Wykonaj poniższe kroki, aby rozpocząć korzystanie z Zaawansowanego edytora formuł w wystąpieniu rozwiązania Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="2d1bb-117">Otwórz **Administracja organizacji** \> **Elektroniczne raportowanie** \> **Konfiguracje**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="2d1bb-118">Na stronie **Konfiguracje** w okienku akcji na karcie **Konfiguracje** w grupie **Ustawienia zaawansowane** wybierz opcję **Parametry użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="2d1bb-119">W oknie dialogowym **Parametry użytkownika** w sekcji **Śledzenie wykonywania** określ parametr **Włącz zaawansowany edytor formuł** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="2d1bb-120">[![Strona konfiguracji raportowania elektronicznego](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-120">[![ER configurations page](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="2d1bb-121">Należy pamiętać, że ten parametr jest właściwy dla użytkownika i właściwy dla firmy.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-121">Be aware that this parameter is user specific and company specific.</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-122"><a name="Autoformatting">Autoformatowanie kodu</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-122"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="2d1bb-123">Po zapisaniu złożonego wyrażenia składającego się z wielu wierszy kodu, wcięcie nowego wprowadzonego wiersza będzie automatycznie oparte na wcięciach poprzedniego wiersza.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-123">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="2d1bb-124">Można wybrać wiersze i zmienić wcięcia, wpisując **Tab** lub **kombinację SHIFT+TAB**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-124">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="2d1bb-125">[![Edytor formuł ER](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-125">[![ER formula editor](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="2d1bb-126">Autoformatowanie pozwala na zachowanie całego wyformatowanego wyrażenia, ułatwiając dalszą konserwację i upraszcza zrozumienie skonfigurowanej logiki.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-126">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-127"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-127"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="2d1bb-128">Edytor zapewnia uzupełnianie wyrazów ułatwiających pisanie wyrażeń i unikanie literówek.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-128">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="2d1bb-129">Po rozpoczęciu dodawania nowego tekstu edytor automatycznie udostępnia listę funkcji obsługiwanych w funkcjach ER, które zawierają wprowadzone znaki.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-129">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="2d1bb-130">Narzędzie IntelliSense można również uruchamiać w dowolnym miejscu skonfigurowanego wyrażenia, naciskając kombinację klawiszy **CTRL+ Spacja**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-130">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="2d1bb-131">[![Edytor formuł ER](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-131">[![ER formula editor](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-132"><a name="CodeCompletion">Zakończenie kodu</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-132"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="2d1bb-133">Edytor automatycznie umożliwia wykonanie kodu przez:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-133">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="2d1bb-134">Wstawianie nawiasu zamykającego przy wprowadzaniu nawiasu otwierającego, pozostawiając kursor w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-134">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="2d1bb-135">Wstawienie symbolu drugiej oferty, gdy zostanie wprowadzony pierwszy z nich, utrzymując kursor w ofertach.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-135">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="2d1bb-136">Wstawienie drugiego symbolu drugiej oferty, gdy zostanie wprowadzony pierwszy z nich, utrzymując kursor w ofertach.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-136">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="2d1bb-137">[![Edytor formuł ER](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-137">[![ER formula editor](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="2d1bb-138">Po wskazaniu wprowadzonego nawiasu, drugi nawias tej pary jest automatycznie wyróżniany w celu przedstawienia obsługiwanej konstrukcji.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-138">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-139"><a name="CodeNavigation">Nawigacja kodu</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-139"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="2d1bb-140">Wymagane symbole lub wiersze w wyrażeniu można zlokalizować, wpisując polecenie **Przejdź do** za pomocą palety poleceń lub menu kontekstowego.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-140">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="2d1bb-141">Aby na przykład przeskoczyć do wiersza **8**, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-141">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="2d1bb-142">Naciśnij **klawisze CTRL+G**, wprowadź wartość **8**, a następnie naciśnij klawisz **ENTER**</span><span class="sxs-lookup"><span data-stu-id="2d1bb-142">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="2d1bb-143">— lub —</span><span class="sxs-lookup"><span data-stu-id="2d1bb-143">-or-</span></span>

- <span data-ttu-id="2d1bb-144">Naciśnij klawisz **F1**, wpisz **G**, wybierz opcję **Przejdź do wiersza**, wprowadź wartość **8**, a następnie naciśnij klawisz **ENTER**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-144">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="2d1bb-145">[![Edytor formuł ER](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-145">[![ER formula editor](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-146"><a name="CodeStructuring">Tworzenie struktury kodu</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-146"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="2d1bb-147">Kod niektórych funkcji, takich [IF](er-functions-logical-if.md) lub [CASE](er-functions-logical-case.md), jest automatycznie uporządkowany.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-147">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="2d1bb-148">Można rozwijać i zwijać dowolne lub wszystkie regiony składane w tym kodzie w celu zmniejszenia możliwej do edycji części wyrażenia w celu skoncentrowania się na thepiece kodu, który wymaga uwagi użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-148">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="2d1bb-149">W tym celu można użyć polecenia przełącz złóż/rozłóż.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-149">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="2d1bb-150">Aby na przykład złożyć wszystkie regiony, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-150">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="2d1bb-151">Naciśnij klawisze **CTRL+K**</span><span class="sxs-lookup"><span data-stu-id="2d1bb-151">Press **Ctrl+K**</span></span>

  <span data-ttu-id="2d1bb-152">— lub —</span><span class="sxs-lookup"><span data-stu-id="2d1bb-152">-or-</span></span>

- <span data-ttu-id="2d1bb-153">Naciśnij klawisz **F1**, naciśnij **FO**, wybierz opcję **Złóż wszystko**, a następnie naciśnij klawisz **ENTER**</span><span class="sxs-lookup"><span data-stu-id="2d1bb-153">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="2d1bb-154">Aby na przykład rozłożyć wszystkie regiony, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-154">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="2d1bb-155">Naciśnij klawisze **CTRL+J**</span><span class="sxs-lookup"><span data-stu-id="2d1bb-155">Press **Ctrl+J**</span></span>

  <span data-ttu-id="2d1bb-156">— lub —</span><span class="sxs-lookup"><span data-stu-id="2d1bb-156">-or-</span></span>
  
- <span data-ttu-id="2d1bb-157">Naciśnij klawisz **F1**, naciśnij **UN**, wybierz opcję **Rozłóż wszystko**, a następnie naciśnij klawisz **ENTER**</span><span class="sxs-lookup"><span data-stu-id="2d1bb-157">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="2d1bb-158">[![Edytor formuł ER](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-158">[![ER formula editor](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-159"><a name="FindAndReplace">Znajdź i zastąp</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-159"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="2d1bb-160">Aby wyszukać wystąpienia określonego tekstu, zaznacz tekst w wyrażeniu i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-160">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="2d1bb-161">Naciśnij klawisze **CTRL+F**, a następnie naciśnij klawisz **F3**, aby znaleźć następne wystąpienie zaznaczonego tekstu, lub naciśnij klawisze **Shift+F3**, aby znaleźć poprzednie wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-161">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="2d1bb-162">— lub —</span><span class="sxs-lookup"><span data-stu-id="2d1bb-162">-or-</span></span>
  
- <span data-ttu-id="2d1bb-163">Naciśnij klawisz **F1**, wpisz **F**, a następnie wybierz żądaną opcję, aby odnaleźć zaznaczony tekst.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-163">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="2d1bb-164">Aby zamienić wystąpienia określonego tekstu, zaznacz tekst w wyrażeniu i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-164">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="2d1bb-165">Naciśnij klawisze **CTRL+H**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-165">Press **Ctrl+H**.</span></span> <span data-ttu-id="2d1bb-166">Wprowadź tekst alternatywny i zaznacz opcję zamiana, aby zastąpić zaznaczony tekst lub wszystkie wystąpienia tego tekstu w bieżącym wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-166">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="2d1bb-167">— lub —</span><span class="sxs-lookup"><span data-stu-id="2d1bb-167">-or-</span></span>
  
- <span data-ttu-id="2d1bb-168">Naciśnij klawisz **F1**, wpisz **R**, a następnie wybierz żądaną opcję, aby podmienić zaznaczony tekst.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-168">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="2d1bb-169">Wprowadź tekst alternatywny i zaznacz opcję zamiana, aby zastąpić zaznaczony tekst lub wszystkie wystąpienia tego tekstu w bieżącym wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-169">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="2d1bb-170">Aby zmienić wszystkie wystąpienia określonego tekstu, zaznacz tekst w wyrażeniu i wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-170">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="2d1bb-171">Naciśnij klawisze **CTRL+F2**, a następnie wprowadź tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-171">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="2d1bb-172">— lub —</span><span class="sxs-lookup"><span data-stu-id="2d1bb-172">-or-</span></span>
  
- <span data-ttu-id="2d1bb-173">Naciśnij klawisz **F1**, wpisz **R**, a następnie wybierz żądaną opcję, aby zmienić zaznaczony tekst.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-173">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="2d1bb-174">Wpisz tekst alternatywny.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-174">Enter the alternative text.</span></span>

<span data-ttu-id="2d1bb-175">[![Edytor formuł ER](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-175">[![ER formula editor](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-176"><a name="DataPasting">Wklejanie źródeł danych i funkcji</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-176"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="2d1bb-177">Możesz wybrać opcję **Dodaj źródło danych**, która wkleja do bieżącego wyrażenia źródło danych, które jest aktualnie zaznaczone w lewym panelu  **Źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-177">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="2d1bb-178">Możesz wybrać opcję **Dodaj funkcję**, która wkleja do bieżącego wyrażeniafunkcję, która jest aktualnie zaznaczona w prawym panelu **Funkcje**.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-178">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="2d1bb-179">Jeśli zostanie użyty Edytor formuł ER, wybrana funkcja lub wybrane źródło danych będzie zawsze wklejane na końcu skonfigurowanego wyrażenia.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-179">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="2d1bb-180">Jeśli zostanie użyty Zaawansowany edytor formuł ER, wybrana funkcja lub wybrane źródło danych może być wklejone gdziekolwiek w skonfigurowanym wyrażeniu.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-180">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="2d1bb-181">W celu określenia miejsca, w którym mają być wklejone dane, należy użyć kursora.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-181">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="2d1bb-182">[![Edytor formuł ER](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-182">[![ER formula editor](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="2d1bb-183"><a name="SyntaxColorization">Kolorowanie składni</a></span><span class="sxs-lookup"><span data-stu-id="2d1bb-183"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="2d1bb-184">Obecnie różne kolory są używane do podświetlania następujących części wyrażeń:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-184">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="2d1bb-185">Tekst w podwójnych nawiasach, który może reprezentować identyfikator etykiety stałej tekstowej.</span><span class="sxs-lookup"><span data-stu-id="2d1bb-185">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="2d1bb-186">[![Edytor formuł ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-186">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="2d1bb-187">Ograniczenia</span><span class="sxs-lookup"><span data-stu-id="2d1bb-187">Limitations</span></span>

<span data-ttu-id="2d1bb-188">Edytor jest obecnie obsługiwany w następujących przeglądarkach sieci Web:</span><span class="sxs-lookup"><span data-stu-id="2d1bb-188">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="2d1bb-189">Chrome</span><span class="sxs-lookup"><span data-stu-id="2d1bb-189">Chrome</span></span>
- <span data-ttu-id="2d1bb-190">Edge</span><span class="sxs-lookup"><span data-stu-id="2d1bb-190">Edge</span></span>
- <span data-ttu-id="2d1bb-191">Firefox</span><span class="sxs-lookup"><span data-stu-id="2d1bb-191">Firefox</span></span>
- <span data-ttu-id="2d1bb-192">Opera</span><span class="sxs-lookup"><span data-stu-id="2d1bb-192">Opera</span></span>
- <span data-ttu-id="2d1bb-193">Safari</span><span class="sxs-lookup"><span data-stu-id="2d1bb-193">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d1bb-194">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2d1bb-194">Additional resources</span></span>

- [<span data-ttu-id="2d1bb-195">Omówienie raportowania elektronicznego (ER)</span><span class="sxs-lookup"><span data-stu-id="2d1bb-195">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="2d1bb-196">Projektant formuł w module Raportowanie elektroniczne</span><span class="sxs-lookup"><span data-stu-id="2d1bb-196">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="2d1bb-197">Edytor Monaco</span><span class="sxs-lookup"><span data-stu-id="2d1bb-197">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]