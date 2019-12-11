---
title: Praca z modułami
description: W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.
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
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 06a26e5dfd35bf229e67ed27213210d0da726bdf
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698080"
---
# <a name="work-with-modules"></a><span data-ttu-id="97768-103">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="97768-103">Work with modules</span></span>

<span data-ttu-id="97768-104">W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="97768-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="97768-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="97768-105">Overview</span></span>

<span data-ttu-id="97768-106">Moduły są logicznymi blokami konstrukcyjnymi, które tworzą strukturę strony i mają różne cele i zakresy.</span><span class="sxs-lookup"><span data-stu-id="97768-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="97768-107">Niektóre moduły są kontenerami wysokiego poziomu, a jedynym celem jest przechowywanie i organizowanie innych modułów (modułów podrzędnych).</span><span class="sxs-lookup"><span data-stu-id="97768-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="97768-108">Inne moduły, takie jak prosty moduł rozmieszczenia obrazów, mają ściśle określony cel.</span><span class="sxs-lookup"><span data-stu-id="97768-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="97768-109">Inne moduły, takie jak moduł karuzeli, znajdują się gdzieś między tymi dwiema kategoriami.</span><span class="sxs-lookup"><span data-stu-id="97768-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="97768-110">Domyślnie witryna Dynamics 365 Commerce zawiera bibliotekę w module zestaw początkowy, która umożliwia osiągnięcie większości podstawowych scenariuszy e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="97768-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="97768-111">Korzystając z tych modułów, można utworzyć kompleksową witrynę e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="97768-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="97768-112">Jednak można również dostosować te moduły lub utworzyć nowe niestandardowe moduły dla konkretnych potrzeb.</span><span class="sxs-lookup"><span data-stu-id="97768-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="97768-113">Jeśli użytkownik chce zbudować moduły niestandardowe, dostępny jest zestaw projektów Software Development Kit (SDK), który ułatwia tworzenie niestandardowych bibliotek modułów.</span><span class="sxs-lookup"><span data-stu-id="97768-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="97768-114">Moduły i gniazda kontenera</span><span class="sxs-lookup"><span data-stu-id="97768-114">Container modules and slots</span></span>

<span data-ttu-id="97768-115">Jak wspomniano wcześniej, niektóre moduły są przeznaczone do przechowywania modułów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="97768-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="97768-116">Moduły te są nazywane *kontenerami* i umożliwiają tworzenie hierarchii zagnieżdżonych modułów.</span><span class="sxs-lookup"><span data-stu-id="97768-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="97768-117">Moduły kontenera zawierają *gniazda*.</span><span class="sxs-lookup"><span data-stu-id="97768-117">Container modules include *slots*.</span></span> <span data-ttu-id="97768-118">Gniazda służą do obsługi układu i celu modułów podrzędnych w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="97768-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="97768-119">Przykładem jest podstawowy moduł kontenera strony (moduł najwyższego poziomu dla dowolnej strony), który definiuje kilka ważnych gniazd:</span><span class="sxs-lookup"><span data-stu-id="97768-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="97768-120">Gniazdo nagłówka</span><span class="sxs-lookup"><span data-stu-id="97768-120">A header slot</span></span>
- <span data-ttu-id="97768-121">Gniazdo treści</span><span class="sxs-lookup"><span data-stu-id="97768-121">A body slot</span></span>
- <span data-ttu-id="97768-122">Gniazdo stopki</span><span class="sxs-lookup"><span data-stu-id="97768-122">A footer slot</span></span>

<span data-ttu-id="97768-123">Programista modułu definiuje te gniazda i określa, które moduły podrzędne i ile modułów podrzędnych może być bezpośrednio w nim umieszczonych.</span><span class="sxs-lookup"><span data-stu-id="97768-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="97768-124">Na przykład gniazdo nagłówka może obsługiwać tylko jeden **moduł nagłówka**, podczas gdy miejsce w treści może obsługiwać nieograniczoną liczbę modułów dowolnego typu (z wyjątkiem innych modułów kontenerów stron).</span><span class="sxs-lookup"><span data-stu-id="97768-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="97768-125">W narzędziach autorskich autorzy stron nie muszą znać z góry, które moduły mogą zostać umieszczone w poszczególnych gniazdach.</span><span class="sxs-lookup"><span data-stu-id="97768-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="97768-126">Gdy autorzy stron wybierają gniazdo, a następnie próbują wybrać moduł, który ma zostać dodany, zobaczą filtrowany widok typów modułów obsługiwanych dla tego gniazda.</span><span class="sxs-lookup"><span data-stu-id="97768-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="97768-127">Moduły zawartości</span><span class="sxs-lookup"><span data-stu-id="97768-127">Content modules</span></span>

<span data-ttu-id="97768-128">Moduły zawartości zawierają zawartość i elementy multimedialne, takie jak tekst (na przykład nagłówki, akapity, łącza) lub odwołania do składników aktywów (np. obrazy, pliki wideo i pliki PDF).</span><span class="sxs-lookup"><span data-stu-id="97768-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="97768-129">Przykłady typowych typów modułów zawartości **bohatera**, **funkcji** i **baner**.</span><span class="sxs-lookup"><span data-stu-id="97768-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="97768-130">Moduły tych trzech typów mogą zawierać tekst lub nośniki i nie wymagają żadnych modułów podrzędnych, aby coś nie było widoczne na stronie.</span><span class="sxs-lookup"><span data-stu-id="97768-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="97768-131">Większość typowych działań na stronie codzienne i tworzenie zawartości obejmuje moduły zawartości, głównie dlatego, że moduły te definiują rzeczywistą zawartość renderowaną w ich nadrzędnych modułach kontenera.</span><span class="sxs-lookup"><span data-stu-id="97768-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="97768-132">Dostępnych jest wiele modułów zawartości, a zazwyczaj te moduły są zwykle ostatnimi fragmentami, które zostaną dodane do hierarchii zagnieżdżonych modułów strony.</span><span class="sxs-lookup"><span data-stu-id="97768-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="97768-133">Na poniższej ilustracji pokazano, jak moduły są zagnieżdżone w gniazdach nadrzędnego modułu kontenera.</span><span class="sxs-lookup"><span data-stu-id="97768-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Moduły zagnieżdżone](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="97768-135">Dodaj lub usuń moduły</span><span class="sxs-lookup"><span data-stu-id="97768-135">Add or remove modules</span></span>

<span data-ttu-id="97768-136">W poniższych procedurach opisano sposób dodawania i usuwania modułów.</span><span class="sxs-lookup"><span data-stu-id="97768-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="97768-137">Dodaj moduł</span><span class="sxs-lookup"><span data-stu-id="97768-137">Add a module</span></span>

<span data-ttu-id="97768-138">Aby dodać moduł do boksu lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="97768-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="97768-139">W okienku konspektu z lewej strony wybierz kontener lub gniazdo, do którego można dodać moduł podrzędny.</span><span class="sxs-lookup"><span data-stu-id="97768-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97768-140">Projektant modułu definiuje listę typów modułów, które można dodać do określonego gniazda modułu.</span><span class="sxs-lookup"><span data-stu-id="97768-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="97768-141">Autorzy szablonów mogą następnie dostosować dozwolone opcje modułu, aby zapewnić spójną optymalizację aparatu wyszukiwania (SEO) i wydajność tworzenia dla wszystkich stron stron, które zostały utworzone na podstawie określonego szablonu.</span><span class="sxs-lookup"><span data-stu-id="97768-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="97768-142">Wybierz przycisk wielokropka (**...**) dla modułu, a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="97768-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="97768-143">Zostanie wyświetlone okno dialogowe **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="97768-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="97768-144">To okno dialogowe jest automatycznie filtrowane, więc pokazuje tylko te moduły, które są obsługiwane w wybranym kontenerze lub gnieździe.</span><span class="sxs-lookup"><span data-stu-id="97768-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="97768-145">Lista modułów jest określana na podstawie szablonu strony lub definicji modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="97768-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97768-146">Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj moduł** jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="97768-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="97768-147">W oknie dialogowym wyszukaj i wybierz moduł, który chcesz dodać do swojej strony.</span><span class="sxs-lookup"><span data-stu-id="97768-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="97768-148">**Funkcje** i **bohater** są dobrymi typami modułów dla początkujących do pracy z systemem.</span><span class="sxs-lookup"><span data-stu-id="97768-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="97768-149">Wybierz przycisk **OK**, aby dodać wybrany moduł do wybranego kontenera lub gniazda na stronie.</span><span class="sxs-lookup"><span data-stu-id="97768-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="97768-150">Usuń moduł</span><span class="sxs-lookup"><span data-stu-id="97768-150">Remove a module</span></span>

<span data-ttu-id="97768-151">Aby usunąć moduł z gniazda lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="97768-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="97768-152">W okienku konspektu z lewej strony wybierz przycisk wielokropka obok nazwy modułu do usunięcia, a następnie wybierz ikonkę kosza na śmieci.</span><span class="sxs-lookup"><span data-stu-id="97768-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="97768-153">Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia modułu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="97768-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="97768-154">Konfiguracja modułów</span><span class="sxs-lookup"><span data-stu-id="97768-154">Configure modules</span></span>

<span data-ttu-id="97768-155">Poniższe procedury opisują sposób konfigurowania modułów zawartości i kontenera.</span><span class="sxs-lookup"><span data-stu-id="97768-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="97768-156">Konfiguruj moduł zawartości</span><span class="sxs-lookup"><span data-stu-id="97768-156">Configure a content module</span></span>

<span data-ttu-id="97768-157">Aby skonfigurować moduł zawartości na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="97768-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="97768-158">W okienku konspektu z lewej strony wybierz typ modułu zawartości (na **funkcji**, **bohater** lub **baner**).</span><span class="sxs-lookup"><span data-stu-id="97768-158">In the outline pane on the left, select a content module type (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="97768-159">W okienku właściwości po prawej stronie rozwiń formanty zagnieżdżone, zaznaczając nagłówki i ustawiając wymagane wartości kontrolne.</span><span class="sxs-lookup"><span data-stu-id="97768-159">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="97768-160">Jeśli w okienku właściwości znajduje się sekcja **Konfiguracja danych**, zaznacz ją, aby ją rozwinąć.</span><span class="sxs-lookup"><span data-stu-id="97768-160">If the properties pane has a **Data Configuration** section, select it to expand it.</span></span> <span data-ttu-id="97768-161">W innym przypadku, przejdź do kroku 5.</span><span class="sxs-lookup"><span data-stu-id="97768-161">Otherwise, go to step 5.</span></span>
1. <span data-ttu-id="97768-162">Jeśli istnieje przycisk **Dodaj źródło danych**, zaznacz go, a następnie wybierz elementy zawartości, które mają zostać dodane.</span><span class="sxs-lookup"><span data-stu-id="97768-162">If there is a **Add Data Source** button, select it, and then select the content items to add.</span></span>
1. <span data-ttu-id="97768-163">Umożliwia wprowadzenie ustawień dla dowolnych wymaganych lub potrzebnych kontrolek modułu.</span><span class="sxs-lookup"><span data-stu-id="97768-163">Enter settings for any required or desired module controls.</span></span>
1. <span data-ttu-id="97768-164">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="97768-164">Select **Save**.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="97768-165">Konfigurowanie modułu kontenera</span><span class="sxs-lookup"><span data-stu-id="97768-165">Configure a container module</span></span>

<span data-ttu-id="97768-166">Aby skonfigurować moduł kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="97768-166">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="97768-167">Wybierz moduł kontenera na stronie (np. karuzela lub moduł kontener płynny).</span><span class="sxs-lookup"><span data-stu-id="97768-167">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="97768-168">W okienku właściwości po prawej stronie rozwiń formanty zagnieżdżone, zaznaczając nagłówki i ustawiając wymagane wartości kontrolne.</span><span class="sxs-lookup"><span data-stu-id="97768-168">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="97768-169">W okienku konspektu po lewej wybierz przycisk wielokropka obok nazwy kontenera lub dowolnych szczelin w kontenerze, a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="97768-169">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="97768-170">Następnie Dodaj moduły podrzędne do wybranego kontenera.</span><span class="sxs-lookup"><span data-stu-id="97768-170">Then add child modules to the selected container.</span></span> <span data-ttu-id="97768-171">Aby uzyskać więcej informacji, zajrzyj do procedury [dodawania modułu](#add-a-module) opisanej wcześniej w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="97768-171">For more information, see the [Add a module](#add-a-module) procedure earlier in this topic.</span></span>
1. <span data-ttu-id="97768-172">Jeśli w kontenerze nadrzędnym istnieje wiele modułów podrzędnych jako elementy równorzędne, można zmienić kolejność wyświetlania w kontenerze nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="97768-172">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="97768-173">Wybierz przycisk wielokropek dla modułu, a następnie użyj przycisków strzałki w górę i strzałki w dół.</span><span class="sxs-lookup"><span data-stu-id="97768-173">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="97768-174">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="97768-174">Additional resources</span></span>

[<span data-ttu-id="97768-175">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="97768-175">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="97768-176">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="97768-176">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="97768-177">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="97768-177">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="97768-178">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="97768-178">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="97768-179">Dodawanie modułu kontenera do strony</span><span class="sxs-lookup"><span data-stu-id="97768-179">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="97768-180">Dodawanie modułów umieszczania zawartości do strony</span><span class="sxs-lookup"><span data-stu-id="97768-180">Add content placement modules to a page</span></span>](add-content-placement-modules.md)

