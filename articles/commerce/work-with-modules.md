---
title: Praca z modułami
description: W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.
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
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 769d6754fa944830b989d657e0dad9cc42212932
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025886"
---
# <a name="work-with-modules"></a><span data-ttu-id="06bea-103">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="06bea-103">Work with modules</span></span>

<span data-ttu-id="06bea-104">W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="06bea-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>


[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="06bea-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="06bea-105">Overview</span></span>

<span data-ttu-id="06bea-106">Moduły są logicznymi blokami konstrukcyjnymi, które tworzą strukturę strony i mają różne cele i zakresy.</span><span class="sxs-lookup"><span data-stu-id="06bea-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="06bea-107">Niektóre moduły są kontenerami wysokiego poziomu, a jedynym celem jest przechowywanie i organizowanie innych modułów (modułów podrzędnych).</span><span class="sxs-lookup"><span data-stu-id="06bea-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="06bea-108">Inne moduły, takie jak prosty moduł rozmieszczenia obrazów, mają ściśle określony cel.</span><span class="sxs-lookup"><span data-stu-id="06bea-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="06bea-109">Inne moduły, takie jak moduł karuzeli, znajdują się gdzieś między tymi dwiema kategoriami.</span><span class="sxs-lookup"><span data-stu-id="06bea-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="06bea-110">Domyślnie witryna Dynamics 365 Commerce zawiera bibliotekę w module zestaw początkowy, która umożliwia osiągnięcie większości podstawowych scenariuszy e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="06bea-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="06bea-111">Korzystając z tych modułów, można utworzyć kompleksową witrynę e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="06bea-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="06bea-112">Jednak można również dostosować te moduły lub utworzyć nowe niestandardowe moduły dla konkretnych potrzeb.</span><span class="sxs-lookup"><span data-stu-id="06bea-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="06bea-113">Jeśli użytkownik chce zbudować moduły niestandardowe, dostępny jest zestaw projektów Software Development Kit (SDK), który ułatwia tworzenie niestandardowych bibliotek modułów.</span><span class="sxs-lookup"><span data-stu-id="06bea-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="06bea-114">Moduły i gniazda kontenera</span><span class="sxs-lookup"><span data-stu-id="06bea-114">Container modules and slots</span></span>

<span data-ttu-id="06bea-115">Jak wspomniano wcześniej, niektóre moduły są przeznaczone do przechowywania modułów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="06bea-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="06bea-116">Moduły te są nazywane *kontenerami* i umożliwiają tworzenie hierarchii zagnieżdżonych modułów.</span><span class="sxs-lookup"><span data-stu-id="06bea-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="06bea-117">Moduły kontenera zawierają *gniazda*.</span><span class="sxs-lookup"><span data-stu-id="06bea-117">Container modules include *slots*.</span></span> <span data-ttu-id="06bea-118">Gniazda służą do obsługi układu i celu modułów podrzędnych w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="06bea-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="06bea-119">Przykładem jest podstawowy moduł kontenera strony (moduł najwyższego poziomu dla dowolnej strony), który definiuje kilka ważnych gniazd:</span><span class="sxs-lookup"><span data-stu-id="06bea-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="06bea-120">Gniazdo nagłówka</span><span class="sxs-lookup"><span data-stu-id="06bea-120">A header slot</span></span>
- <span data-ttu-id="06bea-121">Gniazdo treści</span><span class="sxs-lookup"><span data-stu-id="06bea-121">A body slot</span></span>
- <span data-ttu-id="06bea-122">Gniazdo stopki</span><span class="sxs-lookup"><span data-stu-id="06bea-122">A footer slot</span></span>

<span data-ttu-id="06bea-123">Programista modułu definiuje te gniazda i określa, które moduły podrzędne i ile modułów podrzędnych może być bezpośrednio w nim umieszczonych.</span><span class="sxs-lookup"><span data-stu-id="06bea-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="06bea-124">Na przykład gniazdo nagłówka może obsługiwać tylko jeden **moduł nagłówka**, podczas gdy miejsce w treści może obsługiwać nieograniczoną liczbę modułów dowolnego typu (z wyjątkiem innych modułów kontenerów stron).</span><span class="sxs-lookup"><span data-stu-id="06bea-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="06bea-125">W narzędziach autorskich autorzy stron nie muszą znać z góry, które moduły mogą zostać umieszczone w poszczególnych gniazdach.</span><span class="sxs-lookup"><span data-stu-id="06bea-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="06bea-126">Gdy autorzy stron wybierają gniazdo, a następnie próbują wybrać moduł, który ma zostać dodany, zobaczą filtrowany widok typów modułów obsługiwanych dla tego gniazda.</span><span class="sxs-lookup"><span data-stu-id="06bea-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="06bea-127">Moduły zawartości</span><span class="sxs-lookup"><span data-stu-id="06bea-127">Content modules</span></span>

<span data-ttu-id="06bea-128">Moduły zawartości zawierają zawartość i elementy multimedialne, takie jak tekst (na przykład nagłówki, akapity, łącza) lub odwołania do składników aktywów (np. obrazy, pliki wideo i pliki PDF).</span><span class="sxs-lookup"><span data-stu-id="06bea-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="06bea-129">Przykłady typowych typów modułów zawartości **bohatera**, **funkcji** i **baner**.</span><span class="sxs-lookup"><span data-stu-id="06bea-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="06bea-130">Moduły tych trzech typów mogą zawierać tekst lub nośniki i nie wymagają żadnych modułów podrzędnych, aby coś nie było widoczne na stronie.</span><span class="sxs-lookup"><span data-stu-id="06bea-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="06bea-131">Większość typowych działań na stronie codzienne i tworzenie zawartości obejmuje moduły zawartości, głównie dlatego, że moduły te definiują rzeczywistą zawartość renderowaną w ich nadrzędnych modułach kontenera.</span><span class="sxs-lookup"><span data-stu-id="06bea-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="06bea-132">Dostępnych jest wiele modułów zawartości, a zazwyczaj te moduły są zwykle ostatnimi fragmentami, które zostaną dodane do hierarchii zagnieżdżonych modułów strony.</span><span class="sxs-lookup"><span data-stu-id="06bea-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="06bea-133">Na poniższej ilustracji pokazano, jak moduły są zagnieżdżone w gniazdach nadrzędnego modułu kontenera.</span><span class="sxs-lookup"><span data-stu-id="06bea-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Moduły zagnieżdżone](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="06bea-135">Dodaj lub usuń moduły</span><span class="sxs-lookup"><span data-stu-id="06bea-135">Add or remove modules</span></span>

<span data-ttu-id="06bea-136">W poniższych procedurach opisano sposób dodawania i usuwania modułów.</span><span class="sxs-lookup"><span data-stu-id="06bea-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="06bea-137">Dodaj moduł</span><span class="sxs-lookup"><span data-stu-id="06bea-137">Add a module</span></span>

<span data-ttu-id="06bea-138">Aby dodać moduł do boksu lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="06bea-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="06bea-139">W okienku konspektu z lewej strony wybierz kontener lub gniazdo, do którego można dodać moduł podrzędny.</span><span class="sxs-lookup"><span data-stu-id="06bea-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06bea-140">Projektant modułu definiuje listę typów modułów, które można dodać do określonego gniazda modułu.</span><span class="sxs-lookup"><span data-stu-id="06bea-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="06bea-141">Autorzy szablonów mogą następnie dostosować dozwolone opcje modułu, aby zapewnić spójną optymalizację aparatu wyszukiwania (SEO) i wydajność tworzenia dla wszystkich stron stron, które zostały utworzone na podstawie określonego szablonu.</span><span class="sxs-lookup"><span data-stu-id="06bea-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="06bea-142">Wybierz przycisk wielokropka (**...**) dla modułu, a następnie wybierz opcję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="06bea-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="06bea-143">Zostanie wyświetlone okno dialogowe **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="06bea-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="06bea-144">To okno dialogowe jest automatycznie filtrowane, więc pokazuje tylko te moduły, które są obsługiwane w wybranym kontenerze lub gnieździe.</span><span class="sxs-lookup"><span data-stu-id="06bea-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="06bea-145">Lista modułów jest określana na podstawie szablonu strony lub definicji modułu kontenerów.</span><span class="sxs-lookup"><span data-stu-id="06bea-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06bea-146">Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj moduł** jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="06bea-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="06bea-147">W oknie dialogowym wyszukaj i wybierz moduł, który chcesz dodać do swojej strony.</span><span class="sxs-lookup"><span data-stu-id="06bea-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="06bea-148">**Funkcje** i **bohater** są dobrymi typami modułów dla początkujących do pracy z systemem.</span><span class="sxs-lookup"><span data-stu-id="06bea-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="06bea-149">Wybierz przycisk **OK**, aby dodać wybrany moduł do wybranego kontenera lub gniazda na stronie.</span><span class="sxs-lookup"><span data-stu-id="06bea-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="06bea-150">Usuń moduł</span><span class="sxs-lookup"><span data-stu-id="06bea-150">Remove a module</span></span>

<span data-ttu-id="06bea-151">Aby usunąć moduł z gniazda lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="06bea-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="06bea-152">W okienku konspektu z lewej strony wybierz przycisk wielokropka obok nazwy modułu do usunięcia, a następnie wybierz ikonkę kosza na śmieci.</span><span class="sxs-lookup"><span data-stu-id="06bea-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="06bea-153">Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia modułu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="06bea-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="06bea-154">Konfiguracja modułów</span><span class="sxs-lookup"><span data-stu-id="06bea-154">Configure modules</span></span>

<span data-ttu-id="06bea-155">Poniższe procedury opisują sposób konfigurowania modułów zawartości i kontenera.</span><span class="sxs-lookup"><span data-stu-id="06bea-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="06bea-156">Konfiguruj moduł zawartości</span><span class="sxs-lookup"><span data-stu-id="06bea-156">Configure a content module</span></span>

<span data-ttu-id="06bea-157">Aby skonfigurować moduł zawartości na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="06bea-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="06bea-158">W okienku konspektu z lewej strony rozwiń drzewo i wybierz jakikolwiek moduł zawartości (np. **funkcji**, **bohater** lub **baner**).</span><span class="sxs-lookup"><span data-stu-id="06bea-158">In the outline pane on the left, expand the tree and select any content module (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="06bea-159">W okienku właściwości po prawej stronie Znajdź elementy sterujące treścią i ustawieniami modułu.</span><span class="sxs-lookup"><span data-stu-id="06bea-159">In the properties pane on the right, find the module's content and settings controls.</span></span>
1. <span data-ttu-id="06bea-160">Wprowadź właściwości dla żądanych formantów modułu.</span><span class="sxs-lookup"><span data-stu-id="06bea-160">Enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="06bea-161">Na pasku poleceń wybierz pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="06bea-161">Select **Save** in the command bar.</span></span> <span data-ttu-id="06bea-162">Spowoduje to również odświeżenie kanwy podglądu.</span><span class="sxs-lookup"><span data-stu-id="06bea-162">This will also refresh the preview canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="06bea-163">Konfigurowanie modułu kontenera</span><span class="sxs-lookup"><span data-stu-id="06bea-163">Configure a container module</span></span>

<span data-ttu-id="06bea-164">Aby skonfigurować moduł kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="06bea-164">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="06bea-165">Wybierz moduł kontenera na stronie (np. karuzela lub moduł kontener płynny).</span><span class="sxs-lookup"><span data-stu-id="06bea-165">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="06bea-166">W okienku właściwości po prawej stronie rozwiń formanty zagnieżdżone, zaznaczając nagłówki i ustawiając wymagane wartości kontrolne.</span><span class="sxs-lookup"><span data-stu-id="06bea-166">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="06bea-167">W okienku konspektu po lewej wybierz przycisk wielokropka obok nazwy kontenera lub dowolnych szczelin w kontenerze, a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="06bea-167">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="06bea-168">Następnie Dodaj moduły podrzędne do wybranego kontenera.</span><span class="sxs-lookup"><span data-stu-id="06bea-168">Then, add child modules to the selected container.</span></span> <span data-ttu-id="06bea-169">Aby uzyskać więcej informacji, zobacz sekcję [Praca z modułami](#add-a-module) we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="06bea-169">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="06bea-170">Jeśli w kontenerze nadrzędnym istnieje wiele modułów podrzędnych jako elementy równorzędne, można zmienić kolejność wyświetlania w kontenerze nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="06bea-170">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="06bea-171">Wybierz przycisk wielokropek dla modułu, a następnie użyj przycisków strzałki w górę i strzałki w dół.</span><span class="sxs-lookup"><span data-stu-id="06bea-171">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="06bea-172">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="06bea-172">Additional resources</span></span>

[<span data-ttu-id="06bea-173">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="06bea-173">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="06bea-174">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="06bea-174">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="06bea-175">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="06bea-175">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="06bea-176">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="06bea-176">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="06bea-177">Dodawanie modułu kontenera do strony</span><span class="sxs-lookup"><span data-stu-id="06bea-177">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="06bea-178">Praca z grupami publikowania</span><span class="sxs-lookup"><span data-stu-id="06bea-178">Work with publish groups</span></span>](publish-groups.md)

