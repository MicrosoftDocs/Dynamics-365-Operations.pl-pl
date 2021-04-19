---
title: Modyfikacja istniejącej strony witryny
description: W tym temacie opisano sposób modyfikowania istniejącej strony witryny w Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b633965e45c16cb4e5991fab67783b867223f6ec
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803736"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="81cd9-103">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="81cd9-103">Modify an existing site page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="81cd9-104">W tym temacie opisano sposób modyfikowania istniejącej strony witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="81cd9-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="81cd9-105">W przypadku konieczności zmodyfikowania strony pierwszym krokiem jest otwarcie jej w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="81cd9-105">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="81cd9-106">Przejdź do witryny, która zawiera stronę, a następnie na liście stron znajdź żądaną stronę.</span><span class="sxs-lookup"><span data-stu-id="81cd9-106">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="81cd9-107">Jeśli nie możesz znaleźć strony, możesz skorzystać z funkcji wyszukiwania rozszerzonego narzędzia autorskiego.</span><span class="sxs-lookup"><span data-stu-id="81cd9-107">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="81cd9-108">Należy wpisać dokładną nazwę strony lub wpisać kilka pierwszych liter, a następnie gwiazdkę (\*).</span><span class="sxs-lookup"><span data-stu-id="81cd9-108">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="81cd9-109">Zostanie wyświetlona filtrowana lista stron.</span><span class="sxs-lookup"><span data-stu-id="81cd9-109">A filtered list of pages appears.</span></span> <span data-ttu-id="81cd9-110">Tej listy można użyć, aby znaleźć żądaną stronę.</span><span class="sxs-lookup"><span data-stu-id="81cd9-110">You can use this list to find the page that you want.</span></span> <span data-ttu-id="81cd9-111">Po znalezieniu poprawnej strony wybierz nazwę strony, aby otworzyć stronę w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="81cd9-111">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="81cd9-112">Jeśli strona jest widoczna w Inspektorze stron, można wybrać **Edytuj** i wyewidencjonować stroę przed otwarciem jej w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="81cd9-112">If your page is visible in the page inspector, you can select **Edit** and check the page out before you open it in the page editor.</span></span> <span data-ttu-id="81cd9-113">W ten sposób można wyewidencjonować wiele stron jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="81cd9-113">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="81cd9-114">Po otwarciu strony w edytorze stron należy upewnić się, że została ona wyewidencjonowana dla tego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="81cd9-114">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="81cd9-115">Pasek poleceń w narzędziu autorskim jest dynamiczny, kontekstowy i z uwzględnieniem stanu.</span><span class="sxs-lookup"><span data-stu-id="81cd9-115">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="81cd9-116">W związku z tym są wyświetlane tylko akcje, które można obecnie wykonać na stronie.</span><span class="sxs-lookup"><span data-stu-id="81cd9-116">Therefore, it shows only the actions that you can currently perform on the page.</span></span> <span data-ttu-id="81cd9-117">Jeśli na przykład strona nie jest wyewidencjonowana dla użytkownika, przyciski **Zapisz** i **Zakończ edycję** nie są wyświetlane na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="81cd9-117">For example, if the page isn't checked out to you, the **Save** and **Finish editing** buttons don't appear on the command bar.</span></span> <span data-ttu-id="81cd9-118">Stan strony jest również pokazany po prawej stronie okna.</span><span class="sxs-lookup"><span data-stu-id="81cd9-118">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="81cd9-119">Jeśli strona nie jest jeszcze wyewidencjonowana dla użytkownika, wybierz opcję **Edytuj** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="81cd9-119">If the page isn't already checked out to you, select **Edit** on the command bar.</span></span> <span data-ttu-id="81cd9-120">Pasek poleceń zmieni się, odzwierciedlając nowy stan strony.</span><span class="sxs-lookup"><span data-stu-id="81cd9-120">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="81cd9-121">Użytkownik otrzymuje również powiadomienie informujące o tym, że strona została wyewidencjonowana dla danego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="81cd9-121">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="81cd9-122">Następnym krokiem jest wprowadzenie rzeczywistych zmian.</span><span class="sxs-lookup"><span data-stu-id="81cd9-122">The next step is to make your actual changes.</span></span> <span data-ttu-id="81cd9-123">Często używasz drzewa konspektu strony po lewej stronie, aby znaleźć i wybrać moduł, który chcesz zmienić, a następnie wprowadzić zmiany w panelu właściwości po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="81cd9-123">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="81cd9-124">Jednak ta zmiana może czasami wymagać dodania lub usunięcia modeli lub fragmentów.</span><span class="sxs-lookup"><span data-stu-id="81cd9-124">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="81cd9-125">Aby dodać fragment lub moduł, należy użyć drzewa konspektu strony, aby znaleźć gniazdo, do którego ma zostać dodany moduł lub fragment, a następnie wybrać przycisk wielokropka (**...**) dla tego gniazda.</span><span class="sxs-lookup"><span data-stu-id="81cd9-125">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="81cd9-126">Zostanie wyświetlone menu zawierające polecenia służące do dodawania modułu lub fragmentu.</span><span class="sxs-lookup"><span data-stu-id="81cd9-126">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="81cd9-127">Aby usunąć moduł lub fragment, znajdź go i zaznacz w drzewie konspektu strony, wybierz przycisk wielokropeka, a następnie wybierz polecenie usunięcia modułu lub fragmentu.</span><span class="sxs-lookup"><span data-stu-id="81cd9-127">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="81cd9-128">Można również wyświetlać i edytować właściwości każdego modułu widocznego w wizualnym konstruktorze witryn, zaznaczając go bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="81cd9-128">You can also view and edit the properties for any module that is visible in the visual page builder preview by selecting it directly.</span></span>

<span data-ttu-id="81cd9-129">Po wprowadzeniu zmian i przejrzeniu ich efektu należy zaewidencjonować stronę, wybierając opcję **Zakończ edycję** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="81cd9-129">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Finish editing** on the command bar.</span></span> 

<span data-ttu-id="81cd9-130">Aby natychmiast opublikować zmiany, wybierz opcję **Opublikuj** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="81cd9-130">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="81cd9-131">Najnowsza zaewidencjonowana wersja zmodyfikowanej strony została opublikowana i stanie się dostępna dla użytkowników zewnętrznych, którzy przeglądają witrynę.</span><span class="sxs-lookup"><span data-stu-id="81cd9-131">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="81cd9-132">Przykład: zmiana obrazu wideo na stronie głównej</span><span class="sxs-lookup"><span data-stu-id="81cd9-132">Example: Change the video on the home page</span></span>

<span data-ttu-id="81cd9-133">Poniższy przykład ilustruje sposób modyfikowania strony głównej przez zmianę wideo wyświetlanego w module odtwarzacza wideo.</span><span class="sxs-lookup"><span data-stu-id="81cd9-133">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="81cd9-134">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="81cd9-134">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="81cd9-135">W okienku nawigacji po lewej stronie wybierz **Strony**.</span><span class="sxs-lookup"><span data-stu-id="81cd9-135">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="81cd9-136">Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="81cd9-136">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="81cd9-137">Na pasku poleceń wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="81cd9-137">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="81cd9-138">W konspekcie strony wybierz **Główne** gniazdo.</span><span class="sxs-lookup"><span data-stu-id="81cd9-138">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="81cd9-139">W obszarze **Głównym** gniazda rozwiń wszystkie moduły kontenera cieczy.</span><span class="sxs-lookup"><span data-stu-id="81cd9-139">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="81cd9-140">Znajdź i wybierz moduł odtwarzacza wideo.</span><span class="sxs-lookup"><span data-stu-id="81cd9-140">Find and select the video player module.</span></span>
1. <span data-ttu-id="81cd9-141">W panelu właściwości po prawej wybierz właściwość **wideo**.</span><span class="sxs-lookup"><span data-stu-id="81cd9-141">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="81cd9-142">Zostanie wyświetlony selektor środków trwałych.</span><span class="sxs-lookup"><span data-stu-id="81cd9-142">The asset picker appears.</span></span>
1. <span data-ttu-id="81cd9-143">W obszarze wyboru składników majątku wybierz dostępny zasób wideo lub wybierz opcję **Przekaż nowy składnik**, aby przekazać nowy składnik wideo.</span><span class="sxs-lookup"><span data-stu-id="81cd9-143">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="81cd9-144">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="81cd9-144">Select **OK**.</span></span>
1. <span data-ttu-id="81cd9-145">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="81cd9-145">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="81cd9-146">W polu **Komentarze** wprowadź **Zmieniono wideo**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="81cd9-146">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="81cd9-147">Wybierz opcję **Podgląd**, aby wyświetlić podgląd aktualizowanej strony produktu.</span><span class="sxs-lookup"><span data-stu-id="81cd9-147">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="81cd9-148">Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.</span><span class="sxs-lookup"><span data-stu-id="81cd9-148">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="81cd9-149">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="81cd9-149">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="81cd9-150">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="81cd9-150">Additional resources</span></span>

[<span data-ttu-id="81cd9-151">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="81cd9-151">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="81cd9-152">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="81cd9-152">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="81cd9-153">Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="81cd9-153">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="81cd9-154">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="81cd9-154">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="81cd9-155">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="81cd9-155">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="81cd9-156">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="81cd9-156">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="81cd9-157">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="81cd9-157">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="81cd9-158">Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL</span><span class="sxs-lookup"><span data-stu-id="81cd9-158">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
