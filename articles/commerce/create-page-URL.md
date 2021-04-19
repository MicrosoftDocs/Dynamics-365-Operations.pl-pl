---
title: Tworzenie adresu URL strony
description: W tym temacie przedstawiono podstawowe pojęcia i procedury dotyczące tworzenia adresu URL strony w witrynie.
author: bicyclingfool
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 98743d8948669f32d3c74e1915c7ed53db81141c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795698"
---
# <a name="create-a-page-url"></a><span data-ttu-id="2d366-103">Tworzenie adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="2d366-103">Create a page URL</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2d366-104">W tym temacie przedstawiono podstawowe pojęcia i procedury dotyczące tworzenia adresu URL strony w witrynie.</span><span class="sxs-lookup"><span data-stu-id="2d366-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

<span data-ttu-id="2d366-105">Pełny lub bezwzględny adres URL wskazujący stronę w witrynie składa się z różnych części.</span><span class="sxs-lookup"><span data-stu-id="2d366-105">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="2d366-106">Adres URL `https://www.contoso.com/en-us/contactus` zawiera na przykład następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="2d366-106">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="2d366-107">`https://www.contoso.com` — Protokół HTTP i domenę witryny.</span><span class="sxs-lookup"><span data-stu-id="2d366-107">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="2d366-108">`/en-us` — Ścieżka języka witryny.</span><span class="sxs-lookup"><span data-stu-id="2d366-108">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="2d366-109">`/contactus`— Względny adres URL strony **Skontaktuj się z nami**.</span><span class="sxs-lookup"><span data-stu-id="2d366-109">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="2d366-110">Względny adres URL jest również znany jako *URL*.</span><span class="sxs-lookup"><span data-stu-id="2d366-110">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="2d366-111">Podczas konfigurowania witryny użytkownik określa domenę serwisu i opcjonalną ścieżkę języka.</span><span class="sxs-lookup"><span data-stu-id="2d366-111">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="2d366-112">Za pośrednictwem strony sklepy internetowe w ustawieniach witryny można dodawać kolejne domeny i ścieżki językowe do witryny.</span><span class="sxs-lookup"><span data-stu-id="2d366-112">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="2d366-113">URL strony istnieje jako jednostka samodzielna w środowisku tworzenia witryn.</span><span class="sxs-lookup"><span data-stu-id="2d366-113">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="2d366-114">URL strony składa się z dwóch części: nazwy reprezentującej adres URL, a także wskaźnika do strony w witrynie lub zewnętrznej witrynie</span><span class="sxs-lookup"><span data-stu-id="2d366-114">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="2d366-115">URL strony można również skonfigurować w taki sposób, aby pełnił rolę przekierowania do innej strony w oddziale lub witrynie zewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="2d366-115">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="2d366-116">Tworzenie adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="2d366-116">Create a page URL</span></span>

<span data-ttu-id="2d366-117">Adresy URL stron można tworzyć na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="2d366-117">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="2d366-118">Automatycznie podczas tworzenia strony</span><span class="sxs-lookup"><span data-stu-id="2d366-118">Automatically, when you create a page</span></span>
- <span data-ttu-id="2d366-119">Ręcznie, ze strony adresy **URL**</span><span class="sxs-lookup"><span data-stu-id="2d366-119">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="2d366-120">Utwórz adres URL strony podczas tworzenia strony</span><span class="sxs-lookup"><span data-stu-id="2d366-120">Create a page URL when you create a page</span></span>

<span data-ttu-id="2d366-121">Jeśli podczas tworzenia nowej strony w polu adresu **URL** zostanie wprowadzona nazwa, adres URL strony wskazujący na tę stronę zostanie automatycznie utworzony na stronie adresy **URL**.</span><span class="sxs-lookup"><span data-stu-id="2d366-121">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="2d366-122">Po opublikowaniu adresu URL i strony wskazywanej przez użytkownika, użytkownicy witryny (odbiorcy) mogą uzyskać dostęp do strony skojarzonej z adresem URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-122">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="2d366-123">Jeśli publikujesz adres URL bez publikowania strony, do której on wskazuje, użytkownicy witryny otrzymają komunikat o błędzie 404 przy próbie uzyskania dostępu do strony.</span><span class="sxs-lookup"><span data-stu-id="2d366-123">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="2d366-124">Jeśli strona zostanie opublikowana bez publikowania adresu URL, który wskazuje na Tę stronę, nie można uzyskać dostępu do tej strony przy użyciu adresu URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-124">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="2d366-125">Ręczne tworzenie adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="2d366-125">Manually create a page URL</span></span>

<span data-ttu-id="2d366-126">Podczas tworzenia nowych stron nie jest wymagane określanie adresu URL strony.</span><span class="sxs-lookup"><span data-stu-id="2d366-126">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="2d366-127">Jeśli pole adresu URL pozostanie puste, Strona zostanie utworzona w stanie niepołączonym.</span><span class="sxs-lookup"><span data-stu-id="2d366-127">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="2d366-128">W takim przypadku klienci nie będą mogli uzyskać dostępu do strony, nawet jeśli jest ona opublikowana.</span><span class="sxs-lookup"><span data-stu-id="2d366-128">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="2d366-129">Aby udostępnić stronę, musisz ręcznie utworzyć adres URL i połączyć go z tą stroną.</span><span class="sxs-lookup"><span data-stu-id="2d366-129">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="2d366-130">Aby ręcznie utworzyć adres URL strony, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2d366-130">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="2d366-131">Na stronie **adresy URL** wybierz opcję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="2d366-131">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="2d366-132">Wybierz stronę witryny, aby powiązać ją z adresem URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-132">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="2d366-133">Wprowadź URL, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d366-133">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="2d366-134">W tym momencie adres URL jest w stanie wersji roboczej.</span><span class="sxs-lookup"><span data-stu-id="2d366-134">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="2d366-135">Aby użytkownicy witryny mogli uzyskać dostęp do skojarzonej strony, musi zostać opublikowana.</span><span class="sxs-lookup"><span data-stu-id="2d366-135">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="2d366-136">Aktualizacja adresu URL strony</span><span class="sxs-lookup"><span data-stu-id="2d366-136">Update a page URL</span></span>

<span data-ttu-id="2d366-137">Aby zaktualizować stronę docelową adresu URL strony, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2d366-137">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="2d366-138">Na stronie adresy **URL** wybierz adres URL, który ma zostać zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="2d366-138">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="2d366-139">W okienku właściwości po prawej stronie wybierz przycisk wielokropka (**...**) obok pola strony docelowej.</span><span class="sxs-lookup"><span data-stu-id="2d366-139">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="2d366-140">W oknie dialogowym wybierz inną stroną i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d366-140">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="2d366-141">Zapisz i opublikuj URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-141">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="2d366-142">Przekieruj stronę URL</span><span class="sxs-lookup"><span data-stu-id="2d366-142">Redirect a page URL</span></span>

<span data-ttu-id="2d366-143">Czasami klienci mogą wyświetlać inną stronę, gdy żądają określonego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-143">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="2d366-144">W takich przypadkach najlepszym i najprostszym sposobem jest często zmiana strony, na którą wskazuje adres URL strony.</span><span class="sxs-lookup"><span data-stu-id="2d366-144">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="2d366-145">Mogą jednak istnieć uzasadnione przyczyny użycia protokołu HTTP 301 lub 3023 przekierowywania do przekierowywania żądań o adres URL do innego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-145">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="2d366-146">Aby przekierować adres URL do innego adresu URL, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2d366-146">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="2d366-147">Na stronie adresy **URL** wybierz adres URL, który ma zostać zaktualizowany.</span><span class="sxs-lookup"><span data-stu-id="2d366-147">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="2d366-148">W okienku właściwości po prawej stronie wybierz opcję **Przekieruj**.</span><span class="sxs-lookup"><span data-stu-id="2d366-148">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="2d366-149">Wybierz cel dla przekierowania.</span><span class="sxs-lookup"><span data-stu-id="2d366-149">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="2d366-150">Aby wskazać inną stronę w witrynie, wybierz opcję **wewnętrzny adres URL**, a następnie wybierz przycisk wielokropka (**...**), a następnie wybierz adres URL do przekierowania.</span><span class="sxs-lookup"><span data-stu-id="2d366-150">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="2d366-151">Aby wskazać stronę w witrynie zewnętrznej, wybierz **zewnętrzny adres URL**, a następnie wprowadź pełny adres URL tej strony.</span><span class="sxs-lookup"><span data-stu-id="2d366-151">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="2d366-152">Pamiętaj, aby uwzględnić protokół.</span><span class="sxs-lookup"><span data-stu-id="2d366-152">Be sure to include the protocol.</span></span> <span data-ttu-id="2d366-153">Na przykład wpisz `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="2d366-153">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="2d366-154">Jeśli adres URL już przekierowuje do wewnętrznego adresu URL, należy zaznaczyć pole wyboru **Wyczyść zaznaczenie**, aby można było wprowadzić zewnętrzny adres URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-154">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="2d366-155">Wybór typu przekierowania:</span><span class="sxs-lookup"><span data-stu-id="2d366-155">Select a redirect type:</span></span>

    - <span data-ttu-id="2d366-156">**Stałe przekierowanie (301)** — tę opcję należy wybrać, jeśli wiadomo, że zawartość jest trwale przenoszona i nie zostanie przywrócona do poprzedniego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-156">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="2d366-157">Aparaty wyszukiwania będą przypisywać wartość adresu URL funkcji optymalizacji aparatu wyszukiwania (SEO) do adresu URL, na który jest przekierowywany i aktualizuje rekord w celu wyświetlenia nowego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-157">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="2d366-158">**Tymczasowe przekierowanie (302)** — tę opcję należy wybrać, aby przekierować ruch bez aktualizowania aparatów wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="2d366-158">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="2d366-159">Ta metoda jest zazwyczaj używana, gdy zawartość zostanie wkrótce przywrócona do poprzedniego adresu URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-159">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="2d366-160">Po przygotowaniu się do zaimplementowania przekierowania zapisz i opublikuj adres URL.</span><span class="sxs-lookup"><span data-stu-id="2d366-160">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2d366-161">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2d366-161">Additional resources</span></span>

[<span data-ttu-id="2d366-162">Dostosowywanie nawigacji w witrynie</span><span class="sxs-lookup"><span data-stu-id="2d366-162">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="2d366-163">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="2d366-163">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="2d366-164">Konfigurowanie nazwy domeny</span><span class="sxs-lookup"><span data-stu-id="2d366-164">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="2d366-165">Dodawanie języków do witryny</span><span class="sxs-lookup"><span data-stu-id="2d366-165">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
