---
title: Zapisywanie, pogląd i publikowanie strony
description: W tym temacie opisano, jak zapisać, wyświetlić podgląd i opublikować stronę w Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db4866b22060b764fdde3e4a44e99e969133c0a0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415033"
---
# <a name="save-preview-and-publish-a-page"></a><span data-ttu-id="b19f8-103">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="b19f8-103">Save, preview, and publish a page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b19f8-104">W tym temacie opisano, jak zapisać, wyświetlić podgląd i opublikować stronę w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b19f8-104">This topic describes how to save, preview, and publish a page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="save-a-page"></a><span data-ttu-id="b19f8-105">Zapisywanie strony</span><span class="sxs-lookup"><span data-stu-id="b19f8-105">Save a page</span></span>

<span data-ttu-id="b19f8-106">Aby zapisać stronę, należy ją wyewidencjonować i otworzyć w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="b19f8-106">To save a page, you must have it checked out to yourself and open in the page editor.</span></span> <span data-ttu-id="b19f8-107">Aby wyewidencjonować stronę, na pasku poleceń wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-107">To check out a page, select **Edit** on the command bar.</span></span> <span data-ttu-id="b19f8-108">Po zakończeniu edycji stronę należy zapisać, aby zagwarantować przechowywanie wprowadzonych zmian.</span><span class="sxs-lookup"><span data-stu-id="b19f8-108">After you've finished editing a page, you should immediately save it to ensure that your changes are stored.</span></span>

<span data-ttu-id="b19f8-109">Po zapisaniu strony zmiany są widoczne tylko dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="b19f8-109">When you save a page, the changes are visible only to you.</span></span> <span data-ttu-id="b19f8-110">Operacja zapisywania jest przeznaczona głównie do przechowywania zmian, gdy strona nie jest jeszcze gotowa do zaewidencjonowania.</span><span class="sxs-lookup"><span data-stu-id="b19f8-110">The save operation is intended primarily to store changes while the page isn't yet ready to be checked in.</span></span> <span data-ttu-id="b19f8-111">Po zakończeniu modyfikowania strony zaleca się zaewidencjonowanie jej w systemie, aby zmiany stały się widoczne dla innych osób.</span><span class="sxs-lookup"><span data-stu-id="b19f8-111">When you've finished modifying the page, we recommend that you check it in, so that the changes become visible to others.</span></span> <span data-ttu-id="b19f8-112">Na tym etapie strona może być również wyewidencjonowana przez innych użytkowników, którzy muszą ją zmodyfikować.</span><span class="sxs-lookup"><span data-stu-id="b19f8-112">At that point, the page can also be checked out by other users who must modify it.</span></span>

## <a name="preview-a-page"></a><span data-ttu-id="b19f8-113">Podgląd strony</span><span class="sxs-lookup"><span data-stu-id="b19f8-113">Preview a page</span></span>

<span data-ttu-id="b19f8-114">Narzędzie autorskie oferuje dwa rodzaje funkcji wersji podglądu: wizualny konstruktor stron, czyli okienko podglądu „widoczne dla użytkownika” (WYSIWYG) w edytorze stron i osobnym oknie podglądu.</span><span class="sxs-lookup"><span data-stu-id="b19f8-114">The authoring tool offers two kinds of preview features: visual page builder, which is a "what you see is what you get" (WYSIWYG) preview pane in the page editor, and a separate preview window.</span></span>

<span data-ttu-id="b19f8-115">Gdy jest używany edytor stron, w środkowym okienku jest wyświetlany komunikat „widoczny dla użytkownika” (WYSIWYG).</span><span class="sxs-lookup"><span data-stu-id="b19f8-115">While you're using the page editor, a "what you see is what you get" (WYSIWYG) preview appears in the center pane.</span></span> <span data-ttu-id="b19f8-116">Podgląd ten jest automatycznie aktualizowany przy każdym zapisywaniu strony.</span><span class="sxs-lookup"><span data-stu-id="b19f8-116">This preview is automatically updated whenever you save the page.</span></span> <span data-ttu-id="b19f8-117">Można je również zaktualizować ręcznie, klikając przycisk **Odśwież** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="b19f8-117">You can also manually update it by selecting **Refresh** on the command bar.</span></span> <span data-ttu-id="b19f8-118">Podgląd w trybie WYSIWYG renderuje stronę w taki sposób, jak będzie widoczna dla użytkowników witryny.</span><span class="sxs-lookup"><span data-stu-id="b19f8-118">The preview renders the page just as the site's users will see it, but authoring helpers are rendered on top of it.</span></span>

<span data-ttu-id="b19f8-119">Po zakończeniu modyfikowania strony można wyświetlić jej podgląd, aby zobaczyć, co będą widoczne dla klientów.</span><span class="sxs-lookup"><span data-stu-id="b19f8-119">When you've finished modifying the page, you might want to preview it to see what customers will see.</span></span> <span data-ttu-id="b19f8-120">Aby wyświetlić podgląd strony, należy wybrać opcję **Podgląd** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="b19f8-120">To preview a page, select **Preview** on the command bar.</span></span> <span data-ttu-id="b19f8-121">Podgląd zostanie wyświetlony w osobnym oknie przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="b19f8-121">The preview will appear in a separate browser window.</span></span> <span data-ttu-id="b19f8-122">Strona w oknie podglądu jest renderowana w taki sposób, jak będzie widoczna dla użytkownika witryny.</span><span class="sxs-lookup"><span data-stu-id="b19f8-122">The page in the preview window is rendered just as the site's user will see it.</span></span> <span data-ttu-id="b19f8-123">Można zmienić rozmiar okna, aby upewnić się, że moduły odpowiadające są poprawnie renderowane we wszystkich portach widoków.</span><span class="sxs-lookup"><span data-stu-id="b19f8-123">You can resize the window to make sure that responsive modules are correctly rendered in all view ports.</span></span>

> [!NOTE]
> <span data-ttu-id="b19f8-124">Do wyświetlenia podglądu nieopublikowanej zawartości jest wymagane uwierzytelnianie i poprawne uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="b19f8-124">Authentication and correct permissions are required to preview unpublished content.</span></span> <span data-ttu-id="b19f8-125">Dlatego jeśli adres URL podglądu zostanie udostępniony innej osobie, musi mieć odpowiednie uprawnienia, aby uzyskać dostęp do tej zawartości.</span><span class="sxs-lookup"><span data-stu-id="b19f8-125">Therefore, if you share the URL of the preview with someone, that person must have the correct permissions to access the content.</span></span>

## <a name="publish-a-page"></a><span data-ttu-id="b19f8-126">Opublikuj stronę</span><span class="sxs-lookup"><span data-stu-id="b19f8-126">Publish a page</span></span>

<span data-ttu-id="b19f8-127">Gdy strona jest gotowa, następnym krokiem jest jej opublikowanie, dzięki czemu użytkownicy zewnętrzni będą mogli wyświetlić zawartość.</span><span class="sxs-lookup"><span data-stu-id="b19f8-127">When your page is ready, the next step is to publish it, so that external users can view the content.</span></span> <span data-ttu-id="b19f8-128">Zanim będzie możliwe opublikowanie strony, należy ją wyewidencjować, wybierając opcję **Zakończ edycję** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="b19f8-128">Before you can publish a page, you must check it in by selecting **Finish editing** on the command bar.</span></span>

<span data-ttu-id="b19f8-129">Strony można publikować i cofać ich publikowanie za pomocą Inspektora stron lub edytora stron.</span><span class="sxs-lookup"><span data-stu-id="b19f8-129">You can publish and unpublish pages from either the page inspector or the page editor.</span></span> <span data-ttu-id="b19f8-130">W Inspektorze stron jest wyświetlana lista stron umożliwiająca wykonywanie operacji zbiorczych.</span><span class="sxs-lookup"><span data-stu-id="b19f8-130">The page inspector shows a list of pages and allows for bulk operations.</span></span> <span data-ttu-id="b19f8-131">Edytora stron można używać do publikowania lub cofania publikowania tylko jednej strony otwartej w tym edytorze.</span><span class="sxs-lookup"><span data-stu-id="b19f8-131">The page editor can be used to publish or unpublish only the single page that is open in it.</span></span>

<span data-ttu-id="b19f8-132">Aby opublikować co najmniej jedną stronę za pomocą Inspektora stron, zaznacz strony, upewnij się, że są one zaewidencjonowane, a następnie wybierz opcję **Opublikuj** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="b19f8-132">To publish one or more pages from the page inspector, select the pages, make sure that they are checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="b19f8-133">Strony zostaną opublikowane, a użytkownik otrzymuje powiadomienie o operacji w narzędziu autorskim.</span><span class="sxs-lookup"><span data-stu-id="b19f8-133">The pages are published, and you receive a notification about the operation in the authoring tool.</span></span>

<span data-ttu-id="b19f8-134">Aby opublikować pojedynczą stronę z edytora stron, procedura jest podobna.</span><span class="sxs-lookup"><span data-stu-id="b19f8-134">To publish a single page from the page editor, the procedure is similar.</span></span> <span data-ttu-id="b19f8-135">Gdy strona jest otwarta w edytorze stron, upewnij się, że została zaewidencjonowana w systemie, a następnie wybierz opcję **Opublikuj** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="b19f8-135">While the page is open in the page editor, make sure that it has been checked in, and then select **Publish** on the command bar.</span></span> <span data-ttu-id="b19f8-136">Strona zostanie opublikowana, a użytkownik otrzymuje powiadomienie o operacji.</span><span class="sxs-lookup"><span data-stu-id="b19f8-136">The page is published, and you receive a notification about the operation.</span></span>

<span data-ttu-id="b19f8-137">Po opublikowaniu strony publikowana jest tylko zawartość strony.</span><span class="sxs-lookup"><span data-stu-id="b19f8-137">When you publish a page, just the page content is published.</span></span> <span data-ttu-id="b19f8-138">Użytkownik i inni użytkownicy mogą przejść do tej strony i wyświetlić ją tylko po powiązaniu z nim adresu URL.</span><span class="sxs-lookup"><span data-stu-id="b19f8-138">You and other users can go to the page and view it only after a URL is associated with it.</span></span> <span data-ttu-id="b19f8-139">Adres URL musi być publikowany oddzielnie.</span><span class="sxs-lookup"><span data-stu-id="b19f8-139">The URL must be published separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b19f8-140">Zanim będzie możliwe opublikowanie strony, wszelkie obrazy lub fragmenty, do których odwołuje się Strona, muszą być już opublikowane.</span><span class="sxs-lookup"><span data-stu-id="b19f8-140">Before you can publish a page, any images or fragments that the page references must already be published.</span></span>

## <a name="save-preview-and-publish-a-home-page"></a><span data-ttu-id="b19f8-141">Zapisywanie, pogląd i publikowanie strony głównej</span><span class="sxs-lookup"><span data-stu-id="b19f8-141">Save, preview, and publish a home page</span></span>

<span data-ttu-id="b19f8-142">Aby zapisać, przejrzeć i opublikować stronę główną, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b19f8-142">To save, preview, and publish a home page, follow these steps.</span></span>

1. <span data-ttu-id="b19f8-143">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="b19f8-143">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="b19f8-144">W okienku nawigacji po lewej stronie wybierz **Strony**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-144">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="b19f8-145">Znajdź i wybierz stronę główną, aby otworzyć ją w edytorze stron.</span><span class="sxs-lookup"><span data-stu-id="b19f8-145">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="b19f8-146">Wybierz opcję **Edycja**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-146">Select **Edit**.</span></span>
1. <span data-ttu-id="b19f8-147">Zmodyfikuj stronę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="b19f8-147">Modify the page as you require.</span></span>
1. <span data-ttu-id="b19f8-148">Wybierz **Zapisz** i następnie wybierz **Zakończ edycję**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-148">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="b19f8-149">W polu **Komentarze** wprowadź notatkę dotyczącą wprowadzonych zmian, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-149">In the **Comments** field, enter a note about the changes that you made, and then select **OK**.</span></span>
1. <span data-ttu-id="b19f8-150">Wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="b19f8-150">Select **Preview** to preview your page.</span></span> <span data-ttu-id="b19f8-151">Po zakończeniu Zamknij kartę podglądu, aby powrócić do narzędzia autorskiego.</span><span class="sxs-lookup"><span data-stu-id="b19f8-151">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="b19f8-152">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-152">Select **Publish**.</span></span>

## <a name="publish-a-url"></a><span data-ttu-id="b19f8-153">Publikuj adres URL</span><span class="sxs-lookup"><span data-stu-id="b19f8-153">Publish a URL</span></span>

<span data-ttu-id="b19f8-154">Aby opublikować adres URL, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="b19f8-154">To publish a URL, follow these steps.</span></span>

1. <span data-ttu-id="b19f8-155">W obszarze **Witryny** wybierz **Fabrikam** (lub nazwę witryny).</span><span class="sxs-lookup"><span data-stu-id="b19f8-155">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="b19f8-156">W okienku nawigacji po lewej stronie zaznacz **adresy URL**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-156">In the navigation pane on the left, select **URLs**.</span></span>
1. <span data-ttu-id="b19f8-157">Znajdź i zaznacz adres URL, który chcesz opublikować.</span><span class="sxs-lookup"><span data-stu-id="b19f8-157">Find and select the URL to publish.</span></span>
1. <span data-ttu-id="b19f8-158">Na pasku poleceń wybierz opcję **Opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="b19f8-158">On the command bar, select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b19f8-159">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="b19f8-159">Additional resources</span></span>

[<span data-ttu-id="b19f8-160">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="b19f8-160">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="b19f8-161">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="b19f8-161">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="b19f8-162">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="b19f8-162">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="b19f8-163">Zarządzanie metadanymi funkcji optymalizacji aparatu wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="b19f8-163">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="b19f8-164">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="b19f8-164">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="b19f8-165">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="b19f8-165">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="b19f8-166">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="b19f8-166">Verify page content accessibility</span></span>](verify-accessibility.md)
