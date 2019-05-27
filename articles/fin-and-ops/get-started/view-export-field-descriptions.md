---
title: Wyświetlanie i eksportowanie opisów pól
description: W tym artykule opisano, jak wyświetlać opisy pól i jak używać strony Opisy pól do eksportowania opisów.
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be1495fc42b5f19884a7d9df747f6bec9b64680
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561698"
---
# <a name="view-and-export-field-descriptions"></a><span data-ttu-id="e4132-103">Wyświetlanie i eksportowanie opisów pól</span><span class="sxs-lookup"><span data-stu-id="e4132-103">View and export field descriptions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4132-104">W tym artykule opisano, jak wyświetlać opisy pól i jak używać strony Opisy pól do eksportowania opisów.</span><span class="sxs-lookup"><span data-stu-id="e4132-104">This article describes how to view field descriptions and how to use the Field descriptions page to export descriptions.</span></span>

<span data-ttu-id="e4132-105">Program Microsoft Dynamics 365 for Finance and Operations zawiera opisy niektórych bardziej skomplikowanych pól.</span><span class="sxs-lookup"><span data-stu-id="e4132-105">Microsoft Dynamics 365 for Finance and Operations has descriptions for some of the more complex fields.</span></span> <span data-ttu-id="e4132-106">Opisy te są wyświetlane po umieszczeniu wskaźnika myszy na danym polu.</span><span class="sxs-lookup"><span data-stu-id="e4132-106">These descriptions appear when you hover over a field.</span></span> <span data-ttu-id="e4132-107">Strona **Opisy pól** umożliwia także przeglądanie i eksportowanie opisów.</span><span class="sxs-lookup"><span data-stu-id="e4132-107">You can also view and export descriptions on the **Field descriptions** page.</span></span>

<span data-ttu-id="e4132-108">Nie wszystkie strony mają opisy pól.</span><span class="sxs-lookup"><span data-stu-id="e4132-108">Not all pages have field descriptions.</span></span> <span data-ttu-id="e4132-109">Chcemy podać opisy jedynie dla bardziej złożonych pól, a nie tych, których funkcja jest oczywista.</span><span class="sxs-lookup"><span data-stu-id="e4132-109">We want to provide descriptions only for the more complex fields, not where the use of the field is obvious.</span></span> <span data-ttu-id="e4132-110">Dlatego niektóre strony nie mają żadnych opisów pól, niektóre mają kilka opisów, za to te bardziej złożone strony, np. wiele stron parametrów, zawierają wiele opisów.</span><span class="sxs-lookup"><span data-stu-id="e4132-110">Therefore, some pages don't have any field descriptions, some pages have a few descriptions, and some of the more complex pages, such as many of the parameters pages, have many descriptions.</span></span>

<span data-ttu-id="e4132-111">Jeśli masz dostęp do środowiska programistycznego programu Finance and Operations, istnieje możliwość dodawania nowych opisów pól i modyfikowania istniejących opisów.</span><span class="sxs-lookup"><span data-stu-id="e4132-111">If you have access to the Finance and Operations development environment, you can add new field descriptions and customize existing descriptions.</span></span> <span data-ttu-id="e4132-112">Na przykład do opisu pola można dodać informacje specyficzne dla firmy.</span><span class="sxs-lookup"><span data-stu-id="e4132-112">For example, you can add company-specific information to a field description.</span></span> <span data-ttu-id="e4132-113">Aby uzyskać więcej informacji, zobacz [Dostosowywanie pomocy pól](../../dev-itpro/user-interface/customize-field-help.md).</span><span class="sxs-lookup"><span data-stu-id="e4132-113">For more information, see [Customize field help](../../dev-itpro/user-interface/customize-field-help.md).</span></span>

## <a name="see-field-descriptions-in-the-user-interface"></a><span data-ttu-id="e4132-114">Wyświetlanie opisów pól w interfejsie użytkownika</span><span class="sxs-lookup"><span data-stu-id="e4132-114">See field descriptions in the user interface</span></span>

<span data-ttu-id="e4132-115">Opisy pól można wyświetlić, umieszczając kursor myszy nad polem.</span><span class="sxs-lookup"><span data-stu-id="e4132-115">You can view field descriptions by hovering over a field.</span></span> <span data-ttu-id="e4132-116">Jeśli opis nie jest dostępny, po umieszczeniu wskaźnika myszy na polu zobaczysz nazwę pola.</span><span class="sxs-lookup"><span data-stu-id="e4132-116">If no description is available, you see the field name when you hover over the field.</span></span>

> [!NOTE]
> <span data-ttu-id="e4132-117">W systemie Dynamics AX 7.0.0 (luty 2016) opisy pól można oglądać tylko na stronie **Opisy pól**.</span><span class="sxs-lookup"><span data-stu-id="e4132-117">In Dynamics AX 7.0 (February 2016), field descriptions can be viewed only on the **Field descriptions** page.</span></span>

<span data-ttu-id="e4132-118">Na poniższej ilustracji przedstawiono opis pola, który pojawia się po umieszczeniu wskaźnika myszy nad polem **Zablokuj pozycje podczas inwentaryzacji**.</span><span class="sxs-lookup"><span data-stu-id="e4132-118">The following illustration shows the field description that appears when you hover over the **Lock items during count** field.</span></span>

<span data-ttu-id="e4132-119">[![Przykład opisu pola](./media/field-description.png)](./media/field-description.png)</span><span class="sxs-lookup"><span data-stu-id="e4132-119">[![Example of a field description](./media/field-description.png)](./media/field-description.png)</span></span>

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a><span data-ttu-id="e4132-120">Używanie strony Opisy pól do wyświetlania i eksportowania pomocy dla pól</span><span class="sxs-lookup"><span data-stu-id="e4132-120">Use the Field descriptions page to view and export field help</span></span>

<span data-ttu-id="e4132-121">Strona **Opisy pól** umożliwia przeglądanie i eksportowanie opisów pól.</span><span class="sxs-lookup"><span data-stu-id="e4132-121">The **Field descriptions** page lets you view and export field descriptions.</span></span> <span data-ttu-id="e4132-122">Dostępne opisy można wyświetlić opisy dla jednej strony naraz.</span><span class="sxs-lookup"><span data-stu-id="e4132-122">You can see the descriptions that are available for one page at a time.</span></span>

### <a name="view-the-descriptions-for-a-page"></a><span data-ttu-id="e4132-123">Zobacz opisy dla strony</span><span class="sxs-lookup"><span data-stu-id="e4132-123">View the descriptions for a page</span></span>

<span data-ttu-id="e4132-124">Aby wyświetlić opisy dla strony, wykonaj następującą czynność:</span><span class="sxs-lookup"><span data-stu-id="e4132-124">To view the descriptions for a page, follow this step.</span></span>

- <span data-ttu-id="e4132-125">W polu **Wybór strony** wpisz nazwę strony.</span><span class="sxs-lookup"><span data-stu-id="e4132-125">In the **Select a page** field, type the name of the page.</span></span> <span data-ttu-id="e4132-126">Alternatywnie kliknij strzałkę, aby otworzyć listę wszystkich stron, a następnie przejrzyj lub wyfiltruj listę.</span><span class="sxs-lookup"><span data-stu-id="e4132-126">Alternatively, click the arrow to open a list of all the pages, and then browse or filter the list.</span></span>

<span data-ttu-id="e4132-127">Można użyć nazwy strony wyświetlanej w interfejsie użytkownika (na przykład **Odbiorcy**) lub nazwy kodowej (nazwy w drzewie obiektów aplikacji) dostępnej po kliknięciu strony prawym przyciskiem myszy (na przykład **CustTable**).</span><span class="sxs-lookup"><span data-stu-id="e4132-127">You can use either the name of the page that is shown in the user interface (UI) (for example, **Customers**) or the code name (AOT name) that's available when you right-click a page (for example, **CustTable**).</span></span>

<span data-ttu-id="e4132-128">Aby uzyskać informacje o różnych sposobach filtrowania listy stron, zobacz sekcję „Wyszukiwanie strony” w dalszej części tego artykułu.</span><span class="sxs-lookup"><span data-stu-id="e4132-128">For information about the various ways to filter the list of pages, see the "Searching for a page" section later in this article.</span></span>

<span data-ttu-id="e4132-129">Jeśli w opcji **Uwzględnij pola bez opisu** zaznaczysz wartość **Tak**, będą wyświetlane wszystkie pola istniejące na stronie, nawet jeśli nie mają opisów pól.</span><span class="sxs-lookup"><span data-stu-id="e4132-129">If you set the **Include fields without a description** option to **Yes**, all the fields on the page are shown, even if they don't have a field description.</span></span>

### <a name="export-the-descriptions-for-a-page"></a><span data-ttu-id="e4132-130">Eksportuj opisy dla strony</span><span class="sxs-lookup"><span data-stu-id="e4132-130">Export the descriptions for a page</span></span>

<span data-ttu-id="e4132-131">Aby wyeksportować opisy dla strony, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e4132-131">To export the descriptions for a page, follow these steps.</span></span>

1. <span data-ttu-id="e4132-132">W polu **Wybór strony** zaznacz stronę.</span><span class="sxs-lookup"><span data-stu-id="e4132-132">In the **Select a page** field, select a page.</span></span>
2. <span data-ttu-id="e4132-133">W prawym górnym rogu kliknij przycisk **Otwórz w Microsoft Office**, a następnie wybierz opcję **FieldDescriptionTmp**.</span><span class="sxs-lookup"><span data-stu-id="e4132-133">Click the **Open in Microsoft Office** button in the upper-right corner, and then click **FieldDescriptionTmp**.</span></span>

### <a name="searching-for-a-page"></a><span data-ttu-id="e4132-134">Wyszukiwanie strony</span><span class="sxs-lookup"><span data-stu-id="e4132-134">Searching for a page</span></span>

<span data-ttu-id="e4132-135">Istnieje kilka sposobów, aby wyszukać stronę w polu **Wybór strony**.</span><span class="sxs-lookup"><span data-stu-id="e4132-135">There are several ways to search for a page in the **Select a page** field.</span></span> <span data-ttu-id="e4132-136">W wielu przypadkach trzeba kliknąć strzałkę w polu pola **Wybór strony**, aby otworzyć listę rozwijaną, a następnie wybrać stronę z wyfiltrowanej listy.</span><span class="sxs-lookup"><span data-stu-id="e4132-136">In many cases, you must click the arrow in the **Select a page** field to open the drop-down list, and then select from a filtered list of pages.</span></span>

- <span data-ttu-id="e4132-137">Wpisz część nazwy, a następnie otwórz listę rozwijaną i wybierz stronę w wyfiltrowanej listy.</span><span class="sxs-lookup"><span data-stu-id="e4132-137">Type part of the name, and then open the drop-down list to select from a filtered list of pages.</span></span>
- <span data-ttu-id="e4132-138">Otwórz listę rozwijaną, a następnie kliknij nagłówek **Nazwa strony** u góry listy lub nagłówek **Nazwa drzewa obiektów aplikacji (AOT) strony**.</span><span class="sxs-lookup"><span data-stu-id="e4132-138">Open the drop-down list, and then click either the **Page name** heading at the top of the list or the **Page AOT name** heading.</span></span> <span data-ttu-id="e4132-139">Zostanie otwarte okno dialogowe, w którym można użyć zaawansowanych opcji filtrowania, np. **Nazwa strony zaczyna się od**.</span><span class="sxs-lookup"><span data-stu-id="e4132-139">A dialog box appears, where you can use advanced filtering options, such as **Page name begins with**.</span></span>
- <span data-ttu-id="e4132-140">Wpisz pełną nazwę strony.</span><span class="sxs-lookup"><span data-stu-id="e4132-140">Type the full name of the page.</span></span> <span data-ttu-id="e4132-141">Po wybraniu tej opcji najlepiej otworzyć listę rozwijaną i sprawdzić, co jeszcze jest na niej, nawet gdy są wyświetlane opisy pól.</span><span class="sxs-lookup"><span data-stu-id="e4132-141">When you use this option, it's best to open the drop-down list and see what else is in the list, even if field descriptions are shown.</span></span>

    - <span data-ttu-id="e4132-142">W przypadku istnienia jednego dokładnego dopasowania do nazwy zostaną wyświetlone opisy pól dla tej strony.</span><span class="sxs-lookup"><span data-stu-id="e4132-142">If there is a single exact match to the name, the field descriptions for that page are shown.</span></span>
    - <span data-ttu-id="e4132-143">Jeśli istnieje więcej niż jedno dokładne dopasowanie, opisy nie są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="e4132-143">If there is more than one exact match, no descriptions are shown.</span></span> <span data-ttu-id="e4132-144">Należy otworzyć listę rozwijaną i wybrać żądaną stronę.</span><span class="sxs-lookup"><span data-stu-id="e4132-144">You must open the drop-down list and select the page that you want.</span></span>
    - <span data-ttu-id="e4132-145">Jeśli wpisywana nazwa jest częścią nazwy innej strony, zobaczysz opisy dla swojej strony.</span><span class="sxs-lookup"><span data-stu-id="e4132-145">If the name that you typed is part of the name of another page, you see the descriptions for your page.</span></span> <span data-ttu-id="e4132-146">Jednak po otwarciu listy rozwijanej zobaczysz dodatkowe strony, których tytuły zawierają w sobie tę nazwę.</span><span class="sxs-lookup"><span data-stu-id="e4132-146">However, if you open the drop-down list, you see additional pages that contain that name.</span></span>

<span data-ttu-id="e4132-147">Na przykład nie są wyświetlane żadne opisy po wpisaniu **Inwentaryzacja** w polu **Wybór strony**.</span><span class="sxs-lookup"><span data-stu-id="e4132-147">For example, no descriptions are shown when you type **Counting** in the **Select a page** field.</span></span> <span data-ttu-id="e4132-148">Otwierasz listę rozwijaną i widzisz, że istnieją dwie strony o nazwie **Inwentaryzacja**, a także kilka stron, w których wyraz „Inwentaryzacja” jest częścią nazwy.</span><span class="sxs-lookup"><span data-stu-id="e4132-148">You open the drop-down list, and see that there are two pages that have the name **Counting** and several pages that contain the word "Counting" in the name.</span></span> <span data-ttu-id="e4132-149">Jeśli wybierzesz stronę o nazwie **InventJournalCount** w drzewie obiektów aplikacji, opisy pól są wyświetlane dla tej strony.</span><span class="sxs-lookup"><span data-stu-id="e4132-149">If you select the page that has the AOT name **InventJournalCount**, the field descriptions are shown for that page.</span></span> <span data-ttu-id="e4132-150">Jednakże jeśli lista rozwijana zostanie otwarta ponownie, będzie zawierać wszystkie strony, które w nazwie strony w drzewie obiektów aplikacji mają tekst „InventJournalCount”.</span><span class="sxs-lookup"><span data-stu-id="e4132-150">However, if you open the drop-down list again, you will see that the list now contains all pages that have "InventJournalCount" as part of their AOT name.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e4132-151">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="e4132-151">Troubleshooting</span></span>

<span data-ttu-id="e4132-152">Ta sekcja zawiera informacje pomocne w rozwiązywaniu problemów, które mogą wystąpić podczas używania opisów pól.</span><span class="sxs-lookup"><span data-stu-id="e4132-152">This section provides information to help you troubleshoot issues that you might encounter when you use field descriptions.</span></span>

### <a name="i-cant-find-a-field-description"></a><span data-ttu-id="e4132-153">Nie można odnaleźć opisu pola</span><span class="sxs-lookup"><span data-stu-id="e4132-153">I can't find a field description</span></span>

<span data-ttu-id="e4132-154">Pracujemy nad dodaniem opisów bardziej skomplikowanych pól.</span><span class="sxs-lookup"><span data-stu-id="e4132-154">We're in the process of adding descriptions for the more complex fields.</span></span> <span data-ttu-id="e4132-155">Jeśli potrzebujesz pomocy dla określonego pola, daj nam znać przez dodanie komentarza do tego tematu.</span><span class="sxs-lookup"><span data-stu-id="e4132-155">If you require help for a particular field, let us know by adding a comment for this topic.</span></span>

### <a name="the-field-description-isnt-helpful"></a><span data-ttu-id="e4132-156">Opis pola nie jest pomocny.</span><span class="sxs-lookup"><span data-stu-id="e4132-156">The field description isn't helpful</span></span>

<span data-ttu-id="e4132-157">Daj nam znać przez dodanie komentarza do tego tematu.</span><span class="sxs-lookup"><span data-stu-id="e4132-157">Let us know by adding a comment for this topic.</span></span> <span data-ttu-id="e4132-158">Jeśli to możliwe, opisz dodatkowe informacje, których potrzebujesz.</span><span class="sxs-lookup"><span data-stu-id="e4132-158">If you can, describe the additional information that you require.</span></span>

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a><span data-ttu-id="e4132-159">Nie mogę znaleźć pola na stronie Opisy pól</span><span class="sxs-lookup"><span data-stu-id="e4132-159">I can't find a field on the Field descriptions page</span></span>

<span data-ttu-id="e4132-160">Aby wyświetlić wszystkie pola na stronie, ustaw opcję **Uwzględnij pola bez opisu** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e4132-160">To show all the fields on a page, set the **Include fields without a description** option to **Yes**.</span></span> <span data-ttu-id="e4132-161">Kliknij pole **Wybór strony**, aby sprawdzić, czy została wybrana poprawna strona.</span><span class="sxs-lookup"><span data-stu-id="e4132-161">Click the **Select a page** field to verify that you've selected the correct page.</span></span> <span data-ttu-id="e4132-162">Jeśli wpisana nazwa jest częścią nazwy innego pola, być może wybrano stronę, która ma dłuższą nazwę.</span><span class="sxs-lookup"><span data-stu-id="e4132-162">If the name that you typed is part of another field name, you might have selected the page that has the longer name.</span></span>

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a><span data-ttu-id="e4132-163">Nie mogę znaleźć strony na stronie Opisy pól</span><span class="sxs-lookup"><span data-stu-id="e4132-163">I can't find a page on the Field descriptions page</span></span>

<span data-ttu-id="e4132-164">Aby uzyskać informacje o różnych sposobach znajdowania stron, zobacz sekcję „Wyszukiwanie stron” wcześniej w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="e4132-164">For information about the various way to find pages, see the "Searching for pages" section earlier in this article.</span></span> <span data-ttu-id="e4132-165">Jeśli została wpisana dokładna nazwa strony, opisy pól mogą nie być pokazywane, gdy więcej niż jedna strona ma tę samą nazwę.</span><span class="sxs-lookup"><span data-stu-id="e4132-165">If you've typed the exact name of the page, the field descriptions might not be shown if more than one page has the same name.</span></span> <span data-ttu-id="e4132-166">Kliknij strzałkę w polu **Wybór strony**, aby otworzyć wyfiltrowaną listę dostępnych stron.</span><span class="sxs-lookup"><span data-stu-id="e4132-166">Click the arrow in the **Select a page** field to open a filtered list of the pages that are available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4132-167">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e4132-167">Additional resources</span></span>

[<span data-ttu-id="e4132-168">Dostosowywanie pomocy pól</span><span class="sxs-lookup"><span data-stu-id="e4132-168">Customize field help</span></span>](../../dev-itpro/user-interface/customize-field-help.md)
