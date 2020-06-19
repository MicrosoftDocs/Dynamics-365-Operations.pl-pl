---
title: Moduł nawigacyjny
description: W tym temacie opisano moduły nawigacyjne i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1c6d846686e3214e976a55271694382d7c5973ed
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417399"
---
# <a name="breadcrumb-module"></a><span data-ttu-id="fc445-103">Moduł nawigacyjny</span><span class="sxs-lookup"><span data-stu-id="fc445-103">Breadcrumb module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="fc445-104">W tym temacie opisano moduły nawigacyjne i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fc445-104">This topic covers breadcrumb modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fc445-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="fc445-105">Overview</span></span>

<span data-ttu-id="fc445-106">Moduły do stron nadrzędnych służą do tworzenia pomocniczej nawigacji na stronach witryny.</span><span class="sxs-lookup"><span data-stu-id="fc445-106">Breadcrumb modules are used to provide secondary navigation on site pages.</span></span> <span data-ttu-id="fc445-107">Zazwyczaj są one wyświetlane u góry strony, pod nagłówkiem.</span><span class="sxs-lookup"><span data-stu-id="fc445-107">They are typically shown at the top of a page, below the header.</span></span> <span data-ttu-id="fc445-108">Chociaż moduły stron nadrzędnych można dodawać do dowolnej strony, są one najczęściej używane na stronach szczegółów produktów (PDPs), do wyświetlania hierarchii kategorii produktów oraz szybkiego sposobu poruszania się po witrynie.</span><span class="sxs-lookup"><span data-stu-id="fc445-108">Although breadcrumb modules can be added to any page, they are most often used on product details pages (PDPs), to show the product category hierarchy and provide a quick way to move around a site.</span></span> <span data-ttu-id="fc445-109">Za pomocą modułu łączy wielokrotnych można również wyświetlić łącze „Powrót do wyników”, gdy użytkownicy otworzą PDP na stronie wyszukiwania lub listy.</span><span class="sxs-lookup"><span data-stu-id="fc445-109">A breadcrumb module can also be used to show a "Back to results" link when users open a PDP from a search or list page.</span></span> <span data-ttu-id="fc445-110">Dzięki temu użytkownicy mogą szybko powrócić do strony przefiltrowanej listy, aby kontynuować zakupy.</span><span class="sxs-lookup"><span data-stu-id="fc445-110">In this way, users can quickly return to their filtered list page to continue shopping.</span></span>

<span data-ttu-id="fc445-111">Na stronach z kontekstem kategorii produktów, takimi jak PDPs i strony kategorii, moduły do stron nadrzędnych pokazują hierarchię kategorii.</span><span class="sxs-lookup"><span data-stu-id="fc445-111">On pages that have product category context, such as PDPs and category pages, breadcrumb modules show the category hierarchy.</span></span> <span data-ttu-id="fc445-112">Na stronach, które nie mają kontekstu kategorii, moduły nawigacyjne pokazują domyślnie **&lt;Katalog główny witryny&gt; / &lt;Obecna strona&gt;**.</span><span class="sxs-lookup"><span data-stu-id="fc445-112">On pages that don't have category context, breadcrumb modules show **&lt;Site root&gt; / &lt;Current page&gt;** by default.</span></span> <span data-ttu-id="fc445-113">Moduły nawigacyjne można również skonfigurować ręcznie na innych typach stron witryny w celu wyświetlania łączy do konkretnych stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="fc445-113">Breadcrumb modules can also be manually configured on other types of site pages to show links to specific pages on the site.</span></span>

<span data-ttu-id="fc445-114">Poniższy obraz przedstawia przykład modułu nawigacyjnego, który pokazuje hierarchię kategorii dla PDP.</span><span class="sxs-lookup"><span data-stu-id="fc445-114">The following image shows an example of a breadcrumb module that shows the category hierarchy on a PDP.</span></span>

![Przykład modułu nawigacyjnego](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a><span data-ttu-id="fc445-116">Ustawienia modułu nawigacyjnego</span><span class="sxs-lookup"><span data-stu-id="fc445-116">Breadcrumb module settings</span></span>

<span data-ttu-id="fc445-117">Moduł łącza do stron nadrzędnych opiera się na ustawieniu **Typ widoku nawigacyjnego w PDP**, które jest zdefiniowane **Ustawienia witryny \> Rozszerzenia** w w konstruktorze witryn.</span><span class="sxs-lookup"><span data-stu-id="fc445-117">The breadcrumb module relies on the **Breadcrumb display type on PDP** setting, which is defined at **Site Settings \> Extensions** in site builder.</span></span> <span data-ttu-id="fc445-118">Tao ustawienie ma trzy możliwe wartości:</span><span class="sxs-lookup"><span data-stu-id="fc445-118">This setting has three possible values:</span></span>

- <span data-ttu-id="fc445-119">**Wyświetl hierarchię kategorii** — gdy ta wartość jest zaznaczona, w module nawigacyjnym zostanie wyświetlona pełna hierarchia kategorii produktu wyświetlanego na formularzu PDP.</span><span class="sxs-lookup"><span data-stu-id="fc445-119">**Show category hierarchy** – When this value is selected, the breadcrumb module will show the full category hierarchy of the product that is viewed on the PDP.</span></span>
- <span data-ttu-id="fc445-120">**Powrót do wyników** — po wybraniu tej wartości w module nawigacyjnym zostanie wyświetlone łącze „Powrót do wyników” na karcie PDP, jeśli użytkownik otworzy moduł PDP w module umożliwiającym wykonanie łącza „Powrót do wyników”.</span><span class="sxs-lookup"><span data-stu-id="fc445-120">**Show back to results** – When this value is selected, the breadcrumb module will show a "Back to results" link on a PDP if the user opened the PDP from a module that allows for a "Back to results" link.</span></span> <span data-ttu-id="fc445-121">Ta funkcja jest dostępna, gdy użytkownik nawiguje od stron kategorii, wyszukiwania, listy i rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="fc445-121">This functionality is available when users navigate from category, search, list, and recommendation lists pages.</span></span> <span data-ttu-id="fc445-122">Aby można było obsługiwać tę funkcję, moduły zbierania produktów i wyników wyszukiwania mają właściwość o nazwie **Zezwalaj na powrót do wyników na PDP**.</span><span class="sxs-lookup"><span data-stu-id="fc445-122">To support this functionality, product collection and search results modules have a property that is named **Allow back to results on PDP**.</span></span> <span data-ttu-id="fc445-123">Ta właściwość umożliwia określenie, które moduły powinny obsługiwać łącza „Powrót do wyników” dla zestawu PDP.</span><span class="sxs-lookup"><span data-stu-id="fc445-123">This property gives you the flexibility to define which modules should support the "Back to results" link functionality on the PDP.</span></span> <span data-ttu-id="fc445-124">Na przykład po wybraniu opcji **Powróć do wyników** w ustawieniu **Typ widoku nawigacyjnego w PDP** modułu nawigacyjnego i wybranie **Zezwalaj na powrót do wyników na PDP** dla modułu wyników wyszukiwania stron wyszukiwania, łącze „Powrót do wyników” będzie wyświetlane, gdy użytkownicy przejdą ze strony wyszukiwania do PDP.</span><span class="sxs-lookup"><span data-stu-id="fc445-124">For example, when **Show back to results** is selected for the **Breadcrumb display type on PDP** setting of the breadcrumb module, and **Allow back to results on PDP** is selected for the search page search results module, a "Back to results" link will be shown when users navigate from the search page to a PDP.</span></span>
- <span data-ttu-id="fc445-125">**Wyświetl hierarchię kategorii i wróć do wyników** — Ta wartość jest kombinacją dwóch poprzednich wartości.</span><span class="sxs-lookup"><span data-stu-id="fc445-125">**Show category hierarchy and back to results** – This value is a combination of the previous two.</span></span> <span data-ttu-id="fc445-126">Po wybraniu tej wartości w module nawigacyjnym będzie widoczna zarówno pełna hierarchia kategorii, jak i łącze „Powrót do wyników” (jeśli zostało skonfigurowane) na PDP.</span><span class="sxs-lookup"><span data-stu-id="fc445-126">When this value is selected, the breadcrumb module will show both the full category hierarchy and a "Back to results" link (if it's configured) on a PDP.</span></span>

## <a name="breadcrumb-module-properties"></a><span data-ttu-id="fc445-127">Właściwości modułu nawigacyjnego</span><span class="sxs-lookup"><span data-stu-id="fc445-127">Breadcrumb module properties</span></span>

| <span data-ttu-id="fc445-128">Nazwa właściwości</span><span class="sxs-lookup"><span data-stu-id="fc445-128">Property name</span></span> | <span data-ttu-id="fc445-129">Wartości</span><span class="sxs-lookup"><span data-stu-id="fc445-129">Values</span></span> | <span data-ttu-id="fc445-130">opis</span><span class="sxs-lookup"><span data-stu-id="fc445-130">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="fc445-131">Folder główny</span><span class="sxs-lookup"><span data-stu-id="fc445-131">Root</span></span> | <span data-ttu-id="fc445-132">Tekst lub łącze</span><span class="sxs-lookup"><span data-stu-id="fc445-132">Text or link</span></span>| <span data-ttu-id="fc445-133">Ta właściwość opcjonalna określa tekst łącza oraz cel łącza dla katalogu głównego witryny sieci Web.</span><span class="sxs-lookup"><span data-stu-id="fc445-133">This optional property specifies link text and a link target for the breadcrumb site root.</span></span> <span data-ttu-id="fc445-134">Jeśli ta właściwość nie jest skonfigurowana, nie zostanie zdefiniowany żaden katalog główny.</span><span class="sxs-lookup"><span data-stu-id="fc445-134">If this property isn't configured, no root will be defined.</span></span> |
| <span data-ttu-id="fc445-135">Łącze nawigacyjne</span><span class="sxs-lookup"><span data-stu-id="fc445-135">Breadcrumb link</span></span> | <span data-ttu-id="fc445-136">Łącze</span><span class="sxs-lookup"><span data-stu-id="fc445-136">Link</span></span> | <span data-ttu-id="fc445-137">Ta właściwość opcjonalna określa łącza do ręcznie skonfigurowanych łączy nawigacyjnych, jeśli te łącza są wymagane.</span><span class="sxs-lookup"><span data-stu-id="fc445-137">This optional property specifies links for a manually configured breadcrumb, if these links are required.</span></span> <span data-ttu-id="fc445-138">Łącza są wyświetlane w kolejności, w jakiej są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="fc445-138">Links appear in the order that they are listed in.</span></span> |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a><span data-ttu-id="fc445-139">Dodawanie modułu nawigacyjnego do nowej strony</span><span class="sxs-lookup"><span data-stu-id="fc445-139">Add a breadcrumb module to a new page</span></span>

<span data-ttu-id="fc445-140">Aby dodać moduł nawigacyjnego do PDP i ustawić wymagane właściwości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fc445-140">To add a breadcrumb module to a PDP and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="fc445-141">Przejdź do **Ustawień witryny /> Rozszerzeń**, a następnie dla ustawienia **Typ widoku nawigacyjnego w PDP** wybierz **Wyświetl hierarchię kategorii**.</span><span class="sxs-lookup"><span data-stu-id="fc445-141">Go to **Site Settings /> Extensions**, and then, for the **Breadcrumb display type on PDP** setting, select **Show category hierarchy**.</span></span>
1. <span data-ttu-id="fc445-142">Przejdź do **Szablony** i wybierz szablon PDP.</span><span class="sxs-lookup"><span data-stu-id="fc445-142">Go to **Templates**, and select the PDP template.</span></span>
1. <span data-ttu-id="fc445-143">W gnieździe **Kontener**, w którym znajduje się moduł pola zakupu wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="fc445-143">In the **Container** slot that contains the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="fc445-144">W oknie dialogowym **Dodaj moduł** wybierz moduł **Nawigacyjny** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc445-144">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="fc445-145">Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="fc445-145">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="fc445-146">Przejdź do **Stron** i otwórz element PDP, w którym jest używany szablon PDP.</span><span class="sxs-lookup"><span data-stu-id="fc445-146">Go to **Pages**, and open a PDP that uses the PDP template.</span></span> <span data-ttu-id="fc445-147">Jeśli PDP jeszcze nie istnieje, utwórz go.</span><span class="sxs-lookup"><span data-stu-id="fc445-147">If a PDP doesn't yet exist, create one.</span></span>
1. <span data-ttu-id="fc445-148">W gnieździe **Kontener**, w którym znajduje się moduł pola zakupu wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="fc445-148">In the **Container** slot that contains the buy box module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="fc445-149">W oknie dialogowym **Dodaj moduł** wybierz moduł **Nawigacyjny** i wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc445-149">In the **Add Module** dialog box, select the **Breadcrumb** module, and then select **OK**.</span></span>
1. <span data-ttu-id="fc445-150">W okienku właściwości gniazda **Nawigacyjne** w obszarze **Element główny** wybierz opcję **Tekst łącza**.</span><span class="sxs-lookup"><span data-stu-id="fc445-150">In the properties pane of the **Breadcrumb** slot, under **Root**, select **Link text**.</span></span>
1. <span data-ttu-id="fc445-151">W oknie dialogowym **Tekst łącza** wprowadź tekst **Strona główna**, a następnie w obszarze **Cel łącza** wybierz opcję **Dodaj łącze**.</span><span class="sxs-lookup"><span data-stu-id="fc445-151">In the **Link text** dialog box, enter **Home**, and then, under **Link target**, select **Add a link**.</span></span>
1. <span data-ttu-id="fc445-152">W oknie dialogowym **Dodaj łącze** wybierz łącze do źródła nawigacyjnego, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc445-152">In the **Add a link** dialog box, select a link for the breadcrumb root, and then select **OK**.</span></span>
1. <span data-ttu-id="fc445-153">Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.</span><span class="sxs-lookup"><span data-stu-id="fc445-153">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="fc445-154">Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.</span><span class="sxs-lookup"><span data-stu-id="fc445-154">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc445-155">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fc445-155">Additional resources</span></span>

[<span data-ttu-id="fc445-156">Omówienie zestawu początkowego</span><span class="sxs-lookup"><span data-stu-id="fc445-156">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="fc445-157">Omówienie domyślnej strony docelowej kategorii i strony wyników wyszukiwania</span><span class="sxs-lookup"><span data-stu-id="fc445-157">Overview of default category landing page and search results page</span></span>](category-search-page-overview.md)

[<span data-ttu-id="fc445-158">Moduły kolekcji produktów</span><span class="sxs-lookup"><span data-stu-id="fc445-158">Product collection modules</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="fc445-159">Moduł pola zakupu</span><span class="sxs-lookup"><span data-stu-id="fc445-159">Buy box module</span></span>](add-buy-box.md)
