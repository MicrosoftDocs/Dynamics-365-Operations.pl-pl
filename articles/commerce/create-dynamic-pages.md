---
title: Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL
description: W tym temacie opisano, jak skonfigurować stronę handlu elektronicznego Microsoft Dynamics 365 Commerce, która może obsługiwać zawartość dynamiczną na podstawie parametrów adresu URL.
author: StuHarg
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8f59b80880e6947e1b45c110df0e78d4bdd57c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795818"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a><span data-ttu-id="890cb-103">Tworzenie dynamicznych stron handlu elektronicznego na podstawie parametrów adresu URL</span><span class="sxs-lookup"><span data-stu-id="890cb-103">Create dynamic e-commerce pages based on URL parameters</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="890cb-104">W tym temacie opisano, jak skonfigurować stronę handlu elektronicznego Microsoft Dynamics 365 Commerce, która może obsługiwać zawartość dynamiczną na podstawie parametrów adresu URL.</span><span class="sxs-lookup"><span data-stu-id="890cb-104">This topic describes how to set up a Microsoft Dynamics 365 Commerce e-commerce page that can serve dynamic content, based on URL parameters.</span></span>

<span data-ttu-id="890cb-105">Stronę w usługach handlu elektronicznego można skonfigurować tak, aby obsługiowała inną zawartość, w zależności od segmentu w ścieżce adresu URL.</span><span class="sxs-lookup"><span data-stu-id="890cb-105">An e-commerce page can be configured to serve different content, based on a segment in the URL path.</span></span> <span data-ttu-id="890cb-106">Dlatego strona jest znana jako strona dynamiczna.</span><span class="sxs-lookup"><span data-stu-id="890cb-106">Therefore, the page is known as a dynamic page.</span></span> <span data-ttu-id="890cb-107">Segment jest używany jako parametr pobierania zawartości strony.</span><span class="sxs-lookup"><span data-stu-id="890cb-107">The segment is used as a parameter to retrieve the page content.</span></span> <span data-ttu-id="890cb-108">Na przykład strona o nazwie **blog\_viewer** została utworzona i skojarzona z adresem URL `https://fabrikam.com/blog`.</span><span class="sxs-lookup"><span data-stu-id="890cb-108">For example, a page that is named **blog\_viewer** is created and associated with the URL `https://fabrikam.com/blog`.</span></span> <span data-ttu-id="890cb-109">Następnie można użyć tej strony, aby wyświetlić inną zawartość, opartą na ostatnim segmencie ścieżki adresu URL.</span><span class="sxs-lookup"><span data-stu-id="890cb-109">This page can then be used to show different content, based on the last segment in the URL path.</span></span> <span data-ttu-id="890cb-110">Na przykład ostatnim segmentem adresu URL `https://fabrikam.com/blog/article-1` jest **artykuł-1**.</span><span class="sxs-lookup"><span data-stu-id="890cb-110">For example, the last segment in the URL `https://fabrikam.com/blog/article-1` is **article-1**.</span></span>

<span data-ttu-id="890cb-111">Oddzielne strony niestandardowe, które zastępują stronę dynamiczną, można również powiązać z segmentami w ścieżce adresu URL.</span><span class="sxs-lookup"><span data-stu-id="890cb-111">Separate custom pages that override the dynamic page can also be associated with segments in the URL path.</span></span> <span data-ttu-id="890cb-112">Na przykład strona o nazwie **blog\_summary** została utworzona i skojarzona z adresem URL `https://fabrikam.com/blog/about-this-blog`.</span><span class="sxs-lookup"><span data-stu-id="890cb-112">For example, a page that is named **blog\_summary** is created and associated with the URL `https://fabrikam.com/blog/about-this-blog`.</span></span> <span data-ttu-id="890cb-113">Gdy zostanie żądany ten adres URL, strona **blog\_summary** skojarzona z parametrem **/about-this-blog** zostanie zwrócona zamiast strony **blog\_viewer**.</span><span class="sxs-lookup"><span data-stu-id="890cb-113">When this URL is requested, the **blog\_summary** page that is associated with the **/about-this-blog** parameter is returned instead of the **blog\_viewer** page.</span></span>

> [!NOTE]
> <span data-ttu-id="890cb-114">Funkcjonalność hostingu, pobierania i wyświetlania dynamicznej zawartości strony jest implementowana przy użyciu modułu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="890cb-114">The functionality for hosting, retrieving, and showing dynamic page content is implemented by using a custom module.</span></span> <span data-ttu-id="890cb-115">Więcej informacji jest dostępnych w artykule [Rozszerzanie kanału online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="890cb-115">For more information, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="set-up-a-dynamic-e-commerce-page"></a><span data-ttu-id="890cb-116">Skonfiguruj dynamiczną stronę handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="890cb-116">Set up a dynamic e-commerce page</span></span>

<span data-ttu-id="890cb-117">Aby skonfigurować dynamiczną stronę handlu elektronicznego, musisz utworzyć stronę dynamiczną, utworzyć podstawowy adres URL i skonfigurować trasę do strony dynamicznej.</span><span class="sxs-lookup"><span data-stu-id="890cb-117">To set up a dynamic e-commerce page, you must create the dynamic page, create the base URL, and configure the route to the dynamic page.</span></span>

### <a name="create-the-page-that-will-serve-dynamic-content"></a><span data-ttu-id="890cb-118">Utwórz stronę, która będzie obsługi zawartości dynamicznej</span><span class="sxs-lookup"><span data-stu-id="890cb-118">Create the page that will serve dynamic content</span></span>

<span data-ttu-id="890cb-119">Aby utworzyć stronę, która będzie obsługiwać zawartość dynamiczną, wykonaj kroki w witrynie [Dodawanie nowej strony witryny](add-new-page.md).</span><span class="sxs-lookup"><span data-stu-id="890cb-119">To create a page that will serve dynamic content, follow the steps in [Add a new site page](add-new-page.md).</span></span> <span data-ttu-id="890cb-120">Utworzona strona będzie wymagała implementacji modułu, który używa ostatniego segmentu ścieżki URL do pobierania treści z zewnętrznego źródła danych.</span><span class="sxs-lookup"><span data-stu-id="890cb-120">The page that you create will require implementation of a module that uses the last segment in the URL path to retrieve content from an external data source.</span></span> <span data-ttu-id="890cb-121">Aby uzyskać więcej informacji dotyczących tworzenia modułów niestandardowych, zobacz [Możliwości rozszerzania kanału online](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="890cb-121">For more information about custom module development, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

### <a name="create-the-base-url-for-the-dynamic-page"></a><span data-ttu-id="890cb-122">Utwórz podstawowy adres URL strony dynamicznej</span><span class="sxs-lookup"><span data-stu-id="890cb-122">Create the base URL for the dynamic page</span></span>

<span data-ttu-id="890cb-123">Aby utworzyć podstawowy adres URL strony dynamicznej w Konstruktorze witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="890cb-123">To create the base URL for the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="890cb-124">Przejdź do obszaru **Adresy URL**, a następnie wybierz pozycję **Nowy \> Nowy adres URL**.</span><span class="sxs-lookup"><span data-stu-id="890cb-124">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="890cb-125">W oknie dialogowym **Tworzenie nowego adresu URL** wybierz pozycję **Strona wewnętrzna**.</span><span class="sxs-lookup"><span data-stu-id="890cb-125">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="890cb-126">W obszarze **Ścieżka adresu URL** wprowadź ścieżkę, która będzie pełnić funkcję katalogu głównego strony dynamicznej (w tym przykładzie jest to **/blog**).</span><span class="sxs-lookup"><span data-stu-id="890cb-126">Under **URL path**, enter the path that will serve as the root for the dynamic page (in this example, **/blog**).</span></span> <span data-ttu-id="890cb-127">Następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="890cb-127">Then select **Next**.</span></span>
1. <span data-ttu-id="890cb-128">W oknie dialogowym **Wybieranie strony** wybierz utworzoną przez siebie stronę, która ma służyć jako strona dynamiczna, a następnie wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="890cb-128">In the **Select a page** dialog box, select the page that you created to serve as the dynamic page, and then select **Save**.</span></span>
1. <span data-ttu-id="890cb-129">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="890cb-129">Select **Publish**.</span></span>

### <a name="configure-the-route-to-the-dynamic-page"></a><span data-ttu-id="890cb-130">Konfigurowanie marszruty do strony dynamicznej</span><span class="sxs-lookup"><span data-stu-id="890cb-130">Configure the route to the dynamic page</span></span>

<span data-ttu-id="890cb-131">Aby skonfigurować trasę do strony dynamicznej w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="890cb-131">To configure the route to the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="890cb-132">Przejdź do **Ustawień witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="890cb-132">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="890cb-133">W obszarze **Ścieżki parametrów adresu URL** wybierz opcję **Dodaj**, a następnie wprowadź ścieżkę URL wprowadzona podczas tworzenia adresu URL (w tym przykładzie jest to **/blog**).</span><span class="sxs-lookup"><span data-stu-id="890cb-133">Under **Parameterized URL paths**, select **Add**, and then enter the URL path that you entered when you created the URL (in this example, **/blog**).</span></span>
1. <span data-ttu-id="890cb-134">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="890cb-134">Select **Save and publish**.</span></span>

<span data-ttu-id="890cb-135">Po skonfigurowaniu trasy wszystkie żądania skierowane do sparametryzowanej ścieżki adresu URL spowodują zwrócenie strony skojarzonej z tym adresem URL.</span><span class="sxs-lookup"><span data-stu-id="890cb-135">After the route is configured, all requests to the parameterized URL path will return the page that is associated with that URL.</span></span> <span data-ttu-id="890cb-136">Jeśli jakiekolwiek żądania zawierają dodatkowy segment, skojarzona strona zostanie zwrócona, a zawartość strony zostanie pobrana przy użyciu segmentu jako parametru.</span><span class="sxs-lookup"><span data-stu-id="890cb-136">If any requests contain an additional segment, the associated page will be returned, and the page content will be retrieved by using the segment as a parameter.</span></span> <span data-ttu-id="890cb-137">Na przykład `https://fabrikam.com/blog/article-1` zwróci stronę **blog\_summary**, a zawartość strony zostanie pobrana przy użyciu parametru **/article-1**.</span><span class="sxs-lookup"><span data-stu-id="890cb-137">For example, `https://fabrikam.com/blog/article-1` will return the **blog\_summary** page, and the page content will be retrieved by using the **/article-1** parameter.</span></span>

## <a name="override-a-parameterized-url-with-a-custom-page"></a><span data-ttu-id="890cb-138">Zastąp sparametryzowany adres URL stroną niestandardową</span><span class="sxs-lookup"><span data-stu-id="890cb-138">Override a parameterized URL with a custom page</span></span>

<span data-ttu-id="890cb-139">Aby zastąpić sparametryzowany adres URL niestandardową stroną w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="890cb-139">To override a parameterized URL with a custom page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="890cb-140">Przejdź do obszaru **Adresy URL**, a następnie wybierz pozycję **Nowy \> Nowy adres URL**.</span><span class="sxs-lookup"><span data-stu-id="890cb-140">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="890cb-141">W oknie dialogowym **Tworzenie nowego adresu URL** wybierz pozycję **Strona wewnętrzna**.</span><span class="sxs-lookup"><span data-stu-id="890cb-141">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="890cb-142">W obszarze **Ścieżka adresu URL** wprowadź ścieżkę, która zawiera segment, który ma być zastąpiony (w tym przykładzie jest to **/blog/about-this-blog**).</span><span class="sxs-lookup"><span data-stu-id="890cb-142">Under **URL path**, enter the path that includes the segment to override (in this example, **/blog/about-this-blog**).</span></span> <span data-ttu-id="890cb-143">Następnie kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="890cb-143">Then select **Next**.</span></span>
1. <span data-ttu-id="890cb-144">W oknie dialogowym **Wybierz stronę** wybierz stronę niestandardową, a następnie wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="890cb-144">In the **Select a page** dialog box, select the custom page, and then select **Save**.</span></span>
1. <span data-ttu-id="890cb-145">Wybierz opcję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="890cb-145">Select **Publish**.</span></span>
1. <span data-ttu-id="890cb-146">Jeśli strona niestandardowa nie została jeszcze opublikowana, przejdź na **Strony**, wybierz niestandardową stronę, a następnie wybierz pozycję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="890cb-146">If the custom page hasn't yet been published, go to **Pages**, select the custom page, and then select **Publish**.</span></span>

<span data-ttu-id="890cb-147">Po opublikowaniu strony niestandardowej będzie ona wyświetlana zamiast strony dynamicznej, która ma sparametryzowaną zawartość.</span><span class="sxs-lookup"><span data-stu-id="890cb-147">After the custom page is published, it will be served instead of the dynamic page that has parameterized content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="890cb-148">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="890cb-148">Additional resources</span></span>

[<span data-ttu-id="890cb-149">Modyfikacja istniejącej strony witryny</span><span class="sxs-lookup"><span data-stu-id="890cb-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="890cb-150">Dodawanie nowej strony witryny</span><span class="sxs-lookup"><span data-stu-id="890cb-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="890cb-151">Wybieranie układów stron</span><span class="sxs-lookup"><span data-stu-id="890cb-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="890cb-152">Zarządzanie metadanymi SEO</span><span class="sxs-lookup"><span data-stu-id="890cb-152">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="890cb-153">Zapisywanie, pogląd i publikowanie strony</span><span class="sxs-lookup"><span data-stu-id="890cb-153">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="890cb-154">Wzbogacanie strony produktu</span><span class="sxs-lookup"><span data-stu-id="890cb-154">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="890cb-155">Wzbogacanie strony docelowej kategorii</span><span class="sxs-lookup"><span data-stu-id="890cb-155">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="890cb-156">Weryfikowanie dostępności zawartości strony</span><span class="sxs-lookup"><span data-stu-id="890cb-156">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="890cb-157">Rozszerzanie kanału online</span><span class="sxs-lookup"><span data-stu-id="890cb-157">Online channel extensibility</span></span>](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
