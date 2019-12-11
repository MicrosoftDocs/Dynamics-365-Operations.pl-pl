---
title: Praca z fragmentami
description: W tym temacie opisano, dlaczego, kiedy i jak stosować fragmenty w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: d92b9077f8584bfa0710bbaacbc7caa3220baa4a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698103"
---
# <a name="work-with-fragments"></a><span data-ttu-id="59cad-103">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="59cad-103">Work with fragments</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="59cad-104">W tym temacie opisano, dlaczego, kiedy i jak stosować fragmenty w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="59cad-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="59cad-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="59cad-105">Overview</span></span>

<span data-ttu-id="59cad-106">Fragmenty umożliwiają scentralizowane tworzenie konfiguracji modułów, które muszą być ponownie używane w całym serwisie.</span><span class="sxs-lookup"><span data-stu-id="59cad-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="59cad-107">Na przykład nagłówki, stopki i transparenty są często konfigurowane jako fragmenty, ponieważ są współużytkowane przez wiele stron.</span><span class="sxs-lookup"><span data-stu-id="59cad-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="59cad-108">Fragmenty można traktować jako miniaturowe strony sieci Web, które można wstawiać do innych stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="59cad-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="59cad-109">Fragmenty mają własny cykl życia.</span><span class="sxs-lookup"><span data-stu-id="59cad-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="59cad-110">Innymi słowy, są one tworzone, przywoływane, aktualizowane i usuwane jako niezależne jednostki w narzędziach autorskich.</span><span class="sxs-lookup"><span data-stu-id="59cad-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="59cad-111">Po skonfigurowaniu fragmentów można ich używać wszędzie tam, gdzie moduły mogą być używane w strukturze oddziałów.</span><span class="sxs-lookup"><span data-stu-id="59cad-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="59cad-112">Do fragmentów można odwoływać się na stronach, w układach, w szablonach i w innych fragmentach.</span><span class="sxs-lookup"><span data-stu-id="59cad-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="59cad-113">Fragmenty można zagnieżdżać do siedmiu poziomów głębokości w innych fragmentach.</span><span class="sxs-lookup"><span data-stu-id="59cad-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="59cad-114">Jeśli na przykład chcesz promować wydarzenie sezonowe w dużej liczbie stron w naszej witrynie, możesz użyć fragmentu.</span><span class="sxs-lookup"><span data-stu-id="59cad-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="59cad-115">Pierwszym krokiem w procesie tworzenia nowego fragmentu jest wybranie typu modułu, od którego chcesz zacząć.</span><span class="sxs-lookup"><span data-stu-id="59cad-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="59cad-116">W tym przykładzie można zbudować fragment z modułu głównego.</span><span class="sxs-lookup"><span data-stu-id="59cad-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="59cad-117">Fragmenty można utworzyć na podstawie dowolnego typu modułu.</span><span class="sxs-lookup"><span data-stu-id="59cad-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="59cad-118">Następnie można skonfigurować fragment głównego o konkretnej zawartości promocyjnej.</span><span class="sxs-lookup"><span data-stu-id="59cad-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="59cad-119">Można je również zlokalizować w miarę potrzeb.</span><span class="sxs-lookup"><span data-stu-id="59cad-119">You can also localize it as you require.</span></span> <span data-ttu-id="59cad-120">Nowy autonomiczny fragment główny może zostać wykorzystany jako wstępnie skonfigurowany moduł w całej witrynie.</span><span class="sxs-lookup"><span data-stu-id="59cad-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="59cad-121">Można go łatwo dodać do szablonów, do konkretnych stron lub do innych fragmentów, które mogą zawierać moduły główne.</span><span class="sxs-lookup"><span data-stu-id="59cad-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="59cad-122">Wszystkie miejsca, w których jest dodawany fragment, są odwołaniami do utworzonego centralnego fragmentu głównego.</span><span class="sxs-lookup"><span data-stu-id="59cad-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="59cad-123">W przypadku publikowania zmian w fragmencie zmiany te są natychmiast odzwierciedlane we wszystkich miejscach odwołujących się do danego fragmentu w całej witrynie.</span><span class="sxs-lookup"><span data-stu-id="59cad-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="59cad-124">Dlatego fragmenty stanowią wydajny i efektywny sposób ponownego użycia i centralnego zarządzania konfiguracjami modułów w witrynie.</span><span class="sxs-lookup"><span data-stu-id="59cad-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="59cad-125">Efektywnie wykorzystując je, można znacząco zwiększyć dynamikę i zmniejszyć koszt związany z zarządzaniem zawartością witryny.</span><span class="sxs-lookup"><span data-stu-id="59cad-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="59cad-126">Na poniższej ilustracji pokazano, jak fragmenty mogą być używane do scentralizowanego tworzenia konfiguracji modułu udostępnionego w witrynie e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="59cad-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Na ilustracji pokazano, jak fragmenty mogą być używane do scentralizowanego tworzenia konfiguracji modułu udostępnionego w witrynie e-Commerce](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="59cad-128">Tworzenie fragmentu</span><span class="sxs-lookup"><span data-stu-id="59cad-128">Create a fragment</span></span>

<span data-ttu-id="59cad-129">Można utworzyć nowy fragment lub zapisać istniejącą konfigurację modułu jako fragment.</span><span class="sxs-lookup"><span data-stu-id="59cad-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="create-a-new-fragment"></a><span data-ttu-id="59cad-130">Utwórz nowy fragment.</span><span class="sxs-lookup"><span data-stu-id="59cad-130">Create a new fragment</span></span>

<span data-ttu-id="59cad-131">Aby utworzyć nowy fragment, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="59cad-131">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="59cad-132">W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="59cad-132">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="59cad-133">Wybierz **Nowy fragment strony**.</span><span class="sxs-lookup"><span data-stu-id="59cad-133">Select **New Page Fragment**.</span></span> <span data-ttu-id="59cad-134">Zostanie wyświetlone okno dialogowe, w którym są wyświetlane wszystkie dostępne typy modułów.</span><span class="sxs-lookup"><span data-stu-id="59cad-134">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="59cad-135">Jak wspomniano wcześniej, fragmenty można tworzyć z poziomu dowolnego typu modułu.</span><span class="sxs-lookup"><span data-stu-id="59cad-135">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="59cad-136">Wybierz typ modułu dla swojego fragmentu, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="59cad-136">Select a module type for your fragment, and then select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="59cad-137">Wybór typu ogólnego modułu kontenera zapewnia największą elastyczność, jeśli trzeba później zaktualizować i skonfigurować fragment.</span><span class="sxs-lookup"><span data-stu-id="59cad-137">By selecting a generic container module type, you get the most flexibility when you must update and configure your fragment later.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="59cad-138">Zapisz istniejącą konfigurację modułu jako fragment</span><span class="sxs-lookup"><span data-stu-id="59cad-138">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="59cad-139">Aby przekonwertować poprzednio skonfigurowany moduł na fragment do ponownego użycia, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="59cad-139">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="59cad-140">Otwórz stronę lub szablon zawierający moduł, który chcesz przekonwertować na fragment.</span><span class="sxs-lookup"><span data-stu-id="59cad-140">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="59cad-141">W okienku konspektu z lewej strony wybierz przycisk wielokropka (**...**) obok nazwy modułu, a następnie wybierz opcję **Zapisz jako fragment**.</span><span class="sxs-lookup"><span data-stu-id="59cad-141">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module, and then select **Save as Fragment**.</span></span> <span data-ttu-id="59cad-142">Zostanie wyświetlone okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="59cad-142">A dialog box appears.</span></span>
1. <span data-ttu-id="59cad-143">Wprowadź nazwę i metadane dla fragmentu.</span><span class="sxs-lookup"><span data-stu-id="59cad-143">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="59cad-144">Wybierz przycisk **OK**, aby zapisać konfigurację modułu jako fragment, który można dodać do innych stron.</span><span class="sxs-lookup"><span data-stu-id="59cad-144">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="59cad-145">Dodawanie, usuwanie i edytowanie fragmentów na stronie</span><span class="sxs-lookup"><span data-stu-id="59cad-145">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="59cad-146">W poniższych procedurach opisano sposób dodawania, usuwania i edytowania fragmentów.</span><span class="sxs-lookup"><span data-stu-id="59cad-146">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="59cad-147">Dodaj fragment</span><span class="sxs-lookup"><span data-stu-id="59cad-147">Add a fragment</span></span>

<span data-ttu-id="59cad-148">Aby dodać fragment do strony, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="59cad-148">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="59cad-149">W okienku konspektu z lewej strony wybierz kontener lub gniazdo, do którego można dodać moduły podrzędne.</span><span class="sxs-lookup"><span data-stu-id="59cad-149">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="59cad-150">Wybierz przycisk wielokropka obok nazwy kontenera lub gniazda, a następnie wybierz opcję **Dodaj fragment**.</span><span class="sxs-lookup"><span data-stu-id="59cad-150">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="59cad-151">Zostanie wyświetlone okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="59cad-151">A dialog box appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59cad-152">Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj fragment** jest niedostępna</span><span class="sxs-lookup"><span data-stu-id="59cad-152">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>

1. <span data-ttu-id="59cad-153">W oknie dialogowym wyszukaj i wybierz fragment do dodania.</span><span class="sxs-lookup"><span data-stu-id="59cad-153">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="59cad-154">Jeśli na liście nie ma dostępnych fragmentów, może być konieczne utworzenie fragmentu z typu modułu, który jest obsługiwany przez wybrany kontener lub gniazdo.</span><span class="sxs-lookup"><span data-stu-id="59cad-154">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="59cad-155">Wybierz przycisk **OK**, aby dodać wybrany fragment do wybranego kontenera lub gniazda na stronie.</span><span class="sxs-lookup"><span data-stu-id="59cad-155">Select **OK** to add the selected fragment to the selected container or slot on your page.</span></span>

> [!NOTE]
> <span data-ttu-id="59cad-156">Moduły dozwolone w kontenerze lub gnieździe są definiowane przez szablon strony lub definicje modułów.</span><span class="sxs-lookup"><span data-stu-id="59cad-156">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="59cad-157">Usuwanie fragmentu</span><span class="sxs-lookup"><span data-stu-id="59cad-157">Remove a fragment</span></span>

<span data-ttu-id="59cad-158">Aby usunąć fragment z gniazda lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="59cad-158">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="59cad-159">W okienku konspektu z lewej strony wybierz przycisk wielokropka obok nazwy fragmentu do usunięcia, a następnie wybierz ikonkę kosza na śmieci.</span><span class="sxs-lookup"><span data-stu-id="59cad-159">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="59cad-160">Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia fragmentu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="59cad-160">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="59cad-161">Usunięcie fragmentu ze strony powoduje jedynie usunięcie odwołania do niego z tej strony.</span><span class="sxs-lookup"><span data-stu-id="59cad-161">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="59cad-162">**Nie** można usunąć tego fragmentu z witryny.</span><span class="sxs-lookup"><span data-stu-id="59cad-162">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="59cad-163">Aby usunąć fragmenty z witryny, należy skorzystać z interfejsu użytkownika inspektora fragmentów (UI).</span><span class="sxs-lookup"><span data-stu-id="59cad-163">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="59cad-164">Fragmenty można usuwać z witryny tylko w przypadku, gdy nie odwołują się do nich żadne strony, szablony i inne fragmenty.</span><span class="sxs-lookup"><span data-stu-id="59cad-164">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="59cad-165">Edytuj fragment</span><span class="sxs-lookup"><span data-stu-id="59cad-165">Edit a fragment</span></span>

<span data-ttu-id="59cad-166">Aby edytować fragmenty, należy skorzystać z interfejsu użytkownika edytora fragmentów.</span><span class="sxs-lookup"><span data-stu-id="59cad-166">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="59cad-167">Jest to celowe ograniczenie.</span><span class="sxs-lookup"><span data-stu-id="59cad-167">This restriction is by design.</span></span> <span data-ttu-id="59cad-168">Pomaga zagwarantować, że autorzy nie będą mylić procesu edycji modułów dla konkretnej strony z procesem edycji fragmentów, które mogą być współużytkowane przez wiele stron.</span><span class="sxs-lookup"><span data-stu-id="59cad-168">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="59cad-169">Aby edytować fragment, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="59cad-169">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="59cad-170">W okienku nawigacji po lewej stronie zaznacz **Fragmenty**.</span><span class="sxs-lookup"><span data-stu-id="59cad-170">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="59cad-171">W obszarze **Fragmenty** wybierz fragment do edycji.</span><span class="sxs-lookup"><span data-stu-id="59cad-171">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="59cad-172">Edytuj właściwości i strukturę modułu fragmentu stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="59cad-172">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="59cad-173">Proces ten przypomina proces edycji modułów, który jest edytowany w widoku edytora stron.</span><span class="sxs-lookup"><span data-stu-id="59cad-173">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="59cad-174">Fragment można również edytować, zaznaczając go na stronie, w szablonie lub w fragmencie nadrzędnym, a następnie wybierając opcję **Edytuj fragment** w okienku właściwości po prawej stronie.</span><span class="sxs-lookup"><span data-stu-id="59cad-174">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59cad-175">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="59cad-175">Additional resources</span></span>

[<span data-ttu-id="59cad-176">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="59cad-176">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="59cad-177">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="59cad-177">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="59cad-178">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="59cad-178">Work with preset layouts</span></span>](work-with-layouts.md)
