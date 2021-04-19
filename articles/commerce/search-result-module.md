---
title: Moduł wyników wyszukiwania
description: W tym temacie omówiono moduły wyników wyszukiwania i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3409e9e99329def55b173eb78cf03db4a6764c92
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794122"
---
# <a name="search-results-module"></a><span data-ttu-id="cd0f9-103">Moduł wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="cd0f9-103">Search results module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cd0f9-104">W tym temacie omówiono moduły wyników wyszukiwania i opisano, jak dodać je do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-104">This topic covers search results modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="cd0f9-105">Moduł wyników wyszukiwania zwraca wyniki wyszukiwania produktów oraz listę odpowiednich rafinerów dla produktów.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-105">The search results module returns product search results and a list of applicable refiners for the products.</span></span> <span data-ttu-id="cd0f9-106">Moduły wyników wyszukiwania w witrynach Dynamics 365 Commerce mogą służyć do renderowania stron w następujących scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="cd0f9-106">Search results modules on Dynamics 365 Commerce sites can be used to render pages for the following scenarios:</span></span>

- <span data-ttu-id="cd0f9-107">Wyniki wyszukiwania inicjowane przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="cd0f9-107">Search results that are initiated by a user search</span></span>
- <span data-ttu-id="cd0f9-108">Wyniki wyszukiwania, w których jest pokazywany określony zestaw produktów, na przykład „Kup podobne"</span><span class="sxs-lookup"><span data-stu-id="cd0f9-108">Search results that show a specific set of products, such as "Shop similar looks"</span></span>
- <span data-ttu-id="cd0f9-109">Lista produktów należących do danej kategorii</span><span class="sxs-lookup"><span data-stu-id="cd0f9-109">Lists of products that belong to a category</span></span>

<span data-ttu-id="cd0f9-110">Aby uzyskać więcej informacji o kategoriach i stronach wyników wyszukiwania, zobacz [Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania](category-search-page-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cd0f9-110">For more information about category and search results pages, see [Default category landing page and search results page overview](category-search-page-overview.md).</span></span>

<span data-ttu-id="cd0f9-111">Poniższa ilustracja przedstawia przykład strony wyników wyszukiwania dla kategorii w witrynie Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-111">The following illustration shows an example of a search results page for a category on the Fabrikam site.</span></span>

![Przykład strony wyników wyszukiwania w witrynie Fabrikam](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a><span data-ttu-id="cd0f9-113">Właściwości modułu wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="cd0f9-113">Search results module properties</span></span>

<span data-ttu-id="cd0f9-114">W poniższej tabeli przedstawiono właściwości modułów wyników wyszukiwania wraz z ich wartościami i opisami.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-114">The following table lists the properties of search result modules, together with their values and descriptions.</span></span>

| <span data-ttu-id="cd0f9-115">Właściwość</span><span class="sxs-lookup"><span data-stu-id="cd0f9-115">Property</span></span> | <span data-ttu-id="cd0f9-116">Wartości</span><span class="sxs-lookup"><span data-stu-id="cd0f9-116">Values</span></span> | <span data-ttu-id="cd0f9-117">opis</span><span class="sxs-lookup"><span data-stu-id="cd0f9-117">Description</span></span> |
|----------|--------|-------------|
| <span data-ttu-id="cd0f9-118">Liczba pozycji na stronie</span><span class="sxs-lookup"><span data-stu-id="cd0f9-118">Items per page</span></span> | <span data-ttu-id="cd0f9-119">Wartość całkowita</span><span class="sxs-lookup"><span data-stu-id="cd0f9-119">Integer</span></span> | <span data-ttu-id="cd0f9-120">Liczba pozycji, które powinny być wyświetlane na każdej stronie.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-120">The number of items that should be shown on each page.</span></span> |
| <span data-ttu-id="cd0f9-121">Pozwól na powrót na PDP</span><span class="sxs-lookup"><span data-stu-id="cd0f9-121">Allow back on PDP</span></span> | <span data-ttu-id="cd0f9-122">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="cd0f9-122">**True** or **False**</span></span> | <span data-ttu-id="cd0f9-123">Jeśli właściwość ma wartość **Prawda**, po wybraniu produktu na stronie wyników wyszukiwania na otwartej stronie szczegółów produktu (PDP) będzie wyświetlane łącze „Powrót do wyników”.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-123">If this property is set to **True**, when a user selects a product on the search results page, the breadcrumb navigation on the product details page (PDP) that is opened will show a "Back to results" link.</span></span> |
| <span data-ttu-id="cd0f9-124">Rozwiń elementy uściślające</span><span class="sxs-lookup"><span data-stu-id="cd0f9-124">Expand Refiners</span></span> | <span data-ttu-id="cd0f9-125">**Wszystkie**, **1**, **2**, **3** lub **4**</span><span class="sxs-lookup"><span data-stu-id="cd0f9-125">**All**, **1**, **2**, **3**, or **4**</span></span> | <span data-ttu-id="cd0f9-126">Liczba najlepszych rafinerów, które powinny zostać rozwinięte po załadowaniu strony.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-126">The number of top refiners that should be expanded when a page is loaded.</span></span> <span data-ttu-id="cd0f9-127">Na przykład, jeśli właściwość ma wartość **3**, zostaną rozwinięte pierwsze trzy udoskonalenia na stronie.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-127">For example, if this property is set to **3**, the first three refiners on the page will be expanded.</span></span> |
| <span data-ttu-id="cd0f9-128">Ukryj wyświetlanie hierarchii kategorii</span><span class="sxs-lookup"><span data-stu-id="cd0f9-128">Hide category hierarchy display</span></span> | <span data-ttu-id="cd0f9-129">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="cd0f9-129">**True** or **False**</span></span> | <span data-ttu-id="cd0f9-130">Jeśli właściwość ma wartość **Prawda**, hierarchia kategorii wyświetlana na stronie będzie ukryta.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-130">If this property is set to **True**, the category hierarchy display on the page will be hidden.</span></span> <span data-ttu-id="cd0f9-131">Właściwość powinna mieć wartość **Prawda**, jeśli do pokazywania hierarchii kategorii jest używany [moduł nawigacyjny](add-breadcrumb.md).</span><span class="sxs-lookup"><span data-stu-id="cd0f9-131">This property should be set to **True** if you're using the [breadcrumb module](add-breadcrumb.md) to show the category hierarchy.</span></span>|
| <span data-ttu-id="cd0f9-132">Uwzględnij atrybuty produktu w wynikach wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="cd0f9-132">Include product attributes in search results</span></span> | <span data-ttu-id="cd0f9-133">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="cd0f9-133">**True** or **False**</span></span> | <span data-ttu-id="cd0f9-134">Jeśli właściwość ma wartość **Prawda**, w wynikach wyszukiwania zostaną zwrócone atrybuty.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-134">If this property is set to **True**, attributes will be returned for the products in the search results.</span></span> <span data-ttu-id="cd0f9-135">Chociaż te atrybuty mogą być wyświetlane w witrynie Commerce, wymagane jest rozszerzenie.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-135">Although these attributes can be shown on a Commerce site, an extension is required.</span></span>|
| <span data-ttu-id="cd0f9-136">Pokaż ceny przynależności</span><span class="sxs-lookup"><span data-stu-id="cd0f9-136">Show affiliation prices</span></span> | <span data-ttu-id="cd0f9-137">**Prawda** lub **Fałsz**</span><span class="sxs-lookup"><span data-stu-id="cd0f9-137">**True** or **False**</span></span> | <span data-ttu-id="cd0f9-138">Jeśli właściwość ma wartość **Prawda**, ceny przynależności produktów będą wyświetlane w wynikach wyszukiwania, gdy zalogowany użytkownik przegląda stronę.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-138">If this property is set to **True**, affiliation prices for products will be shown in the search results when a signed-in user browses the page.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="cd0f9-139">W wersji Dynamics 365 Commerce 10.0.16 i nowszych, konfiguracja **Pokaż ceny przynależności** może służyć do wyświetlania cen przynależności na stronie.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-139">In the Dynamics 365 Commerce 10.0.16 release and later, the **Show affiliation prices** configuration can be used to show affiliation prices on the page.</span></span>

## <a name="supported-modules"></a><span data-ttu-id="cd0f9-140">Obsługiwane moduły</span><span class="sxs-lookup"><span data-stu-id="cd0f9-140">Supported modules</span></span>

<span data-ttu-id="cd0f9-141">Moduł wyników wyszukiwania obsługuje [moduł szybkiego poglądu](quick-view-module.md), który umożliwia użytkownikom przeglądanie informacji o produktach i dodawanie produkty do koszyka ze strony wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-141">The search results module supports the [quick view module](quick-view-module.md), which lets users view product information and add items to the cart from the search results page.</span></span>

## <a name="add-a-search-results-module-to-a-category-page"></a><span data-ttu-id="cd0f9-142">Dodawanie modułu wyników wyszukiwania do strony kategorii</span><span class="sxs-lookup"><span data-stu-id="cd0f9-142">Add a search results module to a category page</span></span>

<span data-ttu-id="cd0f9-143">Aby dodać moduł wyników wyszukiwania do strony kategorii, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-143">To add a search results module to a category page, follow these steps.</span></span>

1. <span data-ttu-id="cd0f9-144">Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-144">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="cd0f9-145">W oknie dialogowym **Nowy szablon**, w obszarze **Wyniki wyszukiwania** wprowadź nazwę, a następnie wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-145">In the **New template** dialog box, enter the name **Search results**, and then select **OK**.</span></span>
1. <span data-ttu-id="cd0f9-146">W gnieździe **Treść** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-146">In the **Body** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cd0f9-147">W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-147">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="cd0f9-148">W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (...), a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-148">In the **Main** slot of the **Default Page** module, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cd0f9-149">W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-149">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="cd0f9-150">W gnieździe **Kontener** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-150">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cd0f9-151">W oknie dialogowym **Dodaj moduł** wybierz moduł **Nawigacyjny** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-151">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="cd0f9-152">W okienku właściwości **szlaków nawigacyjnych** wprowadź wartość **1** dla wartości **Minimalne wystąpienia**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-152">In the **Breadcrumb** properties pane, enter the value **1** for **Min Occurs**.</span></span>
1. <span data-ttu-id="cd0f9-153">W gnieździe **Kontener** wybierz wielokropek (...), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-153">In the **Container** slot, select the ellipsis (...), and then select **Add Module**.</span></span>
1. <span data-ttu-id="cd0f9-154">W oknie dialogowym **Dodaj moduł** wybierz moduł **Wyniki wyszukiwania** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-154">In the **Add Module** dialog box, select the **Search results** module, and then select **OK**.</span></span>
1. <span data-ttu-id="cd0f9-155">W okienku właściwości **Wyników wyszukiwania** wprowadź wartość **1** dla **Wartości Minimalne** występują, a następnie ustaw inne wymagane właściwości modułu wyników wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-155">In the **Search results** properties pane, enter the value **1** for **Min Occurs**, and then set any other required properties for the search results module.</span></span> <span data-ttu-id="cd0f9-156">Ustawiając te właściwości w szablonie, zapewniasz, że wszelkie dostosowania do konkretnej strony kategorii będą automatycznie uwzględniać te ustawienia.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-156">By setting these properties in the template, you ensure that any customizations to a specific category page will automatically include these settings.</span></span>
1. <span data-ttu-id="cd0f9-157">Wybierz pozycję **Zakończ edycję**, a następnie wybierz pozycję **Publikuj**, aby opublikować szablon.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-157">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>
1. <span data-ttu-id="cd0f9-158">Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-158">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="cd0f9-159">W oknie dialogowym **Wybierz szablon** wybierz utworzony szablon **Wyników wyszukiwania**, wprowadź **Kategorię strony** dla **Nazwy strony**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-159">In the **Choose a template** dialog box, select the **Search results** template that you created, enter **Category page** for **Page name**, and then select **OK**.</span></span> <span data-ttu-id="cd0f9-160">Ponieważ wszystkie wartości są ustawione w szablonie, strona jest gotowa do opublikowania.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-160">Because all the values are set in the template, the page is ready to be published.</span></span>
1. <span data-ttu-id="cd0f9-161">Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="cd0f9-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cd0f9-162">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="cd0f9-162">Additional resources</span></span>

[<span data-ttu-id="cd0f9-163">Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="cd0f9-163">Default category landing page and search results page overview</span></span>](category-search-page-overview.md)

[<span data-ttu-id="cd0f9-164">Przegląd biblioteki modułów</span><span class="sxs-lookup"><span data-stu-id="cd0f9-164">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="cd0f9-165">Moduł szybkiego podglądu</span><span class="sxs-lookup"><span data-stu-id="cd0f9-165">Quick view module</span></span>](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
