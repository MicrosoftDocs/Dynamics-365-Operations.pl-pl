---
title: Praca z fragmentami
description: W tym temacie opisano, dlaczego, kiedy i jak stosować fragmenty w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f29046ded47ed9c49a2cc841aa7c1f6492b49aec
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026047"
---
# <a name="work-with-fragments"></a><span data-ttu-id="ed9ab-103">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="ed9ab-103">Work with fragments</span></span> 


[!include [banner](includes/banner.md)]

<span data-ttu-id="ed9ab-104">W tym temacie opisano, dlaczego, kiedy i jak stosować fragmenty w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ed9ab-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="ed9ab-105">Overview</span></span>

<span data-ttu-id="ed9ab-106">Fragmenty umożliwiają scentralizowane tworzenie konfiguracji modułów, które muszą być ponownie używane w całym serwisie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="ed9ab-107">Na przykład nagłówki, stopki i transparenty są często konfigurowane jako fragmenty, ponieważ są współużytkowane przez wiele stron.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="ed9ab-108">Fragmenty można traktować jako miniaturowe strony sieci Web, które można wstawiać do innych stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="ed9ab-109">Fragmenty mają własny cykl życia.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="ed9ab-110">Innymi słowy, są one tworzone, przywoływane, aktualizowane i usuwane jako niezależne jednostki w narzędziach autorskich.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="ed9ab-111">Po skonfigurowaniu fragmentów można ich używać wszędzie tam, gdzie moduły mogą być używane w strukturze oddziałów.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="ed9ab-112">Do fragmentów można odwoływać się na stronach, w układach, w szablonach i w innych fragmentach.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="ed9ab-113">Fragmenty można zagnieżdżać do siedmiu poziomów głębokości w innych fragmentach.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="ed9ab-114">Jeśli na przykład chcesz promować wydarzenie sezonowe w dużej liczbie stron w naszej witrynie, możesz użyć fragmentu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="ed9ab-115">Pierwszym krokiem w procesie tworzenia nowego fragmentu jest wybranie typu modułu, od którego chcesz zacząć.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="ed9ab-116">W tym przykładzie można zbudować fragment z modułu głównego.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="ed9ab-117">Fragmenty można utworzyć na podstawie dowolnego typu modułu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="ed9ab-118">Następnie można skonfigurować fragment głównego o konkretnej zawartości promocyjnej.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="ed9ab-119">Można je również zlokalizować w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-119">You can also localize it as you require.</span></span> <span data-ttu-id="ed9ab-120">Nowy autonomiczny fragment główny może zostać wykorzystany jako wstępnie skonfigurowany moduł w całej witrynie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="ed9ab-121">Można go łatwo dodać do szablonów, do konkretnych stron lub do innych fragmentów, które mogą zawierać moduły główne.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="ed9ab-122">Wszystkie miejsca, w których jest dodawany fragment, są odwołaniami do utworzonego centralnego fragmentu głównego.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="ed9ab-123">W przypadku publikowania zmian w fragmencie zmiany te są natychmiast odzwierciedlane we wszystkich miejscach odwołujących się do danego fragmentu w całej witrynie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="ed9ab-124">Dlatego fragmenty stanowią wydajny i efektywny sposób ponownego użycia i centralnego zarządzania konfiguracjami modułów w witrynie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="ed9ab-125">Efektywnie wykorzystując je, można znacząco zwiększyć dynamikę i zmniejszyć koszt związany z zarządzaniem zawartością witryny.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="ed9ab-126">Na poniższej ilustracji pokazano, jak fragmenty mogą być używane do scentralizowanego tworzenia konfiguracji modułu udostępnionego w witrynie e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Na ilustracji pokazano, jak fragmenty mogą być używane do scentralizowanego tworzenia konfiguracji modułu udostępnionego w witrynie e-Commerce](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="ed9ab-128">Tworzenie fragmentu</span><span class="sxs-lookup"><span data-stu-id="ed9ab-128">Create a fragment</span></span>

<span data-ttu-id="ed9ab-129">Można utworzyć nowy fragment lub zapisać istniejącą konfigurację modułu jako fragment.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="ed9ab-130">Zapisz istniejącą konfigurację modułu jako fragment</span><span class="sxs-lookup"><span data-stu-id="ed9ab-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="ed9ab-131">Aby przekonwertować poprzednio skonfigurowany moduł na fragment do ponownego użycia, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-131">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="ed9ab-132">Otwórz stronę lub szablon zawierający moduł, który chcesz przekonwertować na fragment.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="ed9ab-133">W okienku konspektu z lewej strony wybierz przycisk wielokropka (**...**) obok nazwy modułu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-133">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module.</span></span> 
1. <span data-ttu-id="ed9ab-134">Wybierz **Udostępnij jako fragment**.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-134">Select **Share as Fragment**.</span></span> 
1. <span data-ttu-id="ed9ab-135">Zostanie wyświetlone okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-135">A dialog box appears.</span></span> <span data-ttu-id="ed9ab-136">Wprowadź nazwę i metadane dla fragmentu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-136">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="ed9ab-137">Wybierz przycisk **OK**, aby zapisać konfigurację modułu jako fragment, który można dodać do innych stron.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

<span data-ttu-id="ed9ab-138">Poniższy obraz przedstawia sposób zapisywania konfiguracji modułu jako fragmentu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-138">The following image shows how to save a module configuration as a fragment.</span></span>

![Zrzut ekranu, jak zapisać konfigurację modułu jako fragment](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a><span data-ttu-id="ed9ab-140">Utwórz nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-140">Create a new fragment</span></span>

<span data-ttu-id="ed9ab-141">Aby utworzyć nowy fragment, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-141">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="ed9ab-142">W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-142">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="ed9ab-143">Wybierz **Nowy fragment strony**.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-143">Select **New Page Fragment**.</span></span> <span data-ttu-id="ed9ab-144">Zostanie wyświetlone okno dialogowe, w którym są wyświetlane wszystkie dostępne typy modułów.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-144">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="ed9ab-145">Jak wspomniano wcześniej, fragmenty można tworzyć z poziomu dowolnego typu modułu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-145">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="ed9ab-146">Wybierz typ modułu dla danego fragmentu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-146">Select a module type for your fragment.</span></span>

<span data-ttu-id="ed9ab-147">Poniższy rysunek przedstawia miejsce utworzenia nowego fragmentu.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-147">The following image shows where to create a new fragment.</span></span>

![Zrzut ekranu, gdzie należy utworzyć nowy fragment](./media/fragment-nav-menu.png)

> [!TIP]
> <span data-ttu-id="ed9ab-149">Wybór typu ogólnego modułu kontenera zapewnia największą elastyczność, jeśli należy później zaktualizować i skonfigurować fragment.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-149">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="ed9ab-150">Dodawanie, usuwanie i edytowanie fragmentów na stronie</span><span class="sxs-lookup"><span data-stu-id="ed9ab-150">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="ed9ab-151">W poniższych procedurach opisano sposób dodawania, usuwania i edytowania fragmentów.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-151">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="ed9ab-152">Dodaj fragment</span><span class="sxs-lookup"><span data-stu-id="ed9ab-152">Add a fragment</span></span>

<span data-ttu-id="ed9ab-153">Aby dodać fragment do strony, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-153">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="ed9ab-154">W okienku konspektu z lewej strony wybierz kontener lub gniazdo, do którego można dodać moduły podrzędne.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-154">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="ed9ab-155">Wybierz przycisk wielokropka obok nazwy kontenera lub gniazda, a następnie wybierz opcję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-155">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="ed9ab-156">Zostanie wyświetlone okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-156">A dialog box appears.</span></span>

    ![Zrzut ekranu, jak dodać istniejący fragment do gniazda lub kontenera](./media/add-fragment.png)
 
    > [!NOTE]
    > <span data-ttu-id="ed9ab-158">Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj fragment** jest niedostępna</span><span class="sxs-lookup"><span data-stu-id="ed9ab-158">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="ed9ab-159">W oknie dialogowym wyszukaj i wybierz fragment do dodania.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-159">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="ed9ab-160">Jeśli na liście nie ma dostępnych fragmentów, może być konieczne utworzenie fragmentu z typu modułu, który jest obsługiwany przez wybrany kontener lub gniazdo.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-160">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="ed9ab-161">Wybierz wybrany fragment do dodania go do kontenera lub gniazda na stronie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-161">Select your desired fragment to add it to the container or slot on your page.</span></span>

    ![Zrzut ekranu okna modalnego selektora fragmentów](./media/fragment-picker.png)

> [!NOTE]
> <span data-ttu-id="ed9ab-163">Moduły dozwolone w kontenerze lub gnieździe są definiowane przez szablon strony lub definicje modułów.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-163">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="ed9ab-164">Usuwanie fragmentu</span><span class="sxs-lookup"><span data-stu-id="ed9ab-164">Remove a fragment</span></span>

<span data-ttu-id="ed9ab-165">Aby usunąć fragment z gniazda lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-165">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="ed9ab-166">W okienku konspektu z lewej strony wybierz przycisk wielokropka obok nazwy fragmentu do usunięcia, a następnie wybierz ikonkę kosza na śmieci.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-166">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="ed9ab-167">Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia fragmentu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-167">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="ed9ab-168">Usunięcie fragmentu ze strony powoduje jedynie usunięcie odwołania do niego z tej strony.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-168">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="ed9ab-169">**Nie** można usunąć tego fragmentu z witryny.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-169">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="ed9ab-170">Aby usunąć fragmenty z witryny, należy skorzystać z interfejsu użytkownika inspektora fragmentów (UI).</span><span class="sxs-lookup"><span data-stu-id="ed9ab-170">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="ed9ab-171">Fragmenty można usuwać z witryny tylko w przypadku, gdy nie odwołują się do nich żadne strony, szablony i inne fragmenty.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-171">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="ed9ab-172">Edytuj fragment</span><span class="sxs-lookup"><span data-stu-id="ed9ab-172">Edit a fragment</span></span>

<span data-ttu-id="ed9ab-173">Aby edytować fragmenty, należy skorzystać z interfejsu użytkownika edytora fragmentów.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-173">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="ed9ab-174">Jest to celowe ograniczenie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-174">This restriction is by design.</span></span> <span data-ttu-id="ed9ab-175">Pomaga zagwarantować, że autorzy nie będą mylić procesu edycji modułów dla konkretnej strony z procesem edycji fragmentów, które mogą być współużytkowane przez wiele stron.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-175">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="ed9ab-176">Aby edytować fragment, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-176">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="ed9ab-177">W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-177">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="ed9ab-178">W obszarze **Fragmenty** wybierz fragment do edycji.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-178">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="ed9ab-179">Edytuj właściwości i strukturę modułu fragmentu stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-179">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="ed9ab-180">Proces ten przypomina proces edycji modułów, który jest edytowany w widoku edytora stron.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-180">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="ed9ab-181">Fragment można również edytować, zaznaczając go na stronie, w szablonie lub w fragmencie nadrzędnym, a następnie wybierając opcję **Edytuj fragment** w okienku właściwości po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="ed9ab-181">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ed9ab-182">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ed9ab-182">Additional resources</span></span>

[<span data-ttu-id="ed9ab-183">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="ed9ab-183">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="ed9ab-184">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="ed9ab-184">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="ed9ab-185">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="ed9ab-185">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="ed9ab-186">Praca z grupami publikowania</span><span class="sxs-lookup"><span data-stu-id="ed9ab-186">Work with publish groups</span></span>](publish-groups.md)
