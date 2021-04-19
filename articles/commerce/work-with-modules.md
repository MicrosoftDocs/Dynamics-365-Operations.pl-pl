---
title: Praca z modułami
description: W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6d872719d3b1aa27ccfdcf36d7739c883e7b4996
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801368"
---
# <a name="work-with-modules"></a><span data-ttu-id="56cc0-103">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="56cc0-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="56cc0-104">W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="56cc0-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="56cc0-105">Moduły są logicznymi blokami konstrukcyjnymi, które tworzą strukturę strony i mają różne cele i zakresy.</span><span class="sxs-lookup"><span data-stu-id="56cc0-105">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="56cc0-106">Niektóre moduły są kontenerami wysokiego poziomu, a jedynym celem jest przechowywanie i organizowanie innych modułów (modułów podrzędnych).</span><span class="sxs-lookup"><span data-stu-id="56cc0-106">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="56cc0-107">Inne moduły, takie jak prosty moduł rozmieszczenia obrazów, mają ściśle określony cel.</span><span class="sxs-lookup"><span data-stu-id="56cc0-107">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="56cc0-108">Inne moduły, takie jak moduł karuzeli, znajdują się gdzieś między tymi dwiema kategoriami.</span><span class="sxs-lookup"><span data-stu-id="56cc0-108">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="56cc0-109">Domyślnie witryna Dynamics 365 Commerce zawiera bibliotekę modułów, która umożliwia osiągnięcie większości podstawowych scenariuszy e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="56cc0-109">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="56cc0-110">Korzystając z tych modułów, można utworzyć kompleksową witrynę e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="56cc0-110">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="56cc0-111">Jednak można również dostosować te moduły lub utworzyć nowe niestandardowe moduły dla konkretnych potrzeb.</span><span class="sxs-lookup"><span data-stu-id="56cc0-111">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="56cc0-112">Jeśli użytkownik chce zbudować moduły niestandardowe, dostępny jest zestaw projektów Software Development Kit (SDK), który ułatwia tworzenie niestandardowych bibliotek modułów.</span><span class="sxs-lookup"><span data-stu-id="56cc0-112">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="56cc0-113">Moduły i gniazda kontenera</span><span class="sxs-lookup"><span data-stu-id="56cc0-113">Container modules and slots</span></span>

<span data-ttu-id="56cc0-114">Jak wspomniano wcześniej, niektóre moduły są przeznaczone do przechowywania modułów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="56cc0-114">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="56cc0-115">Moduły te są nazywane *kontenerami* i umożliwiają tworzenie hierarchii zagnieżdżonych modułów.</span><span class="sxs-lookup"><span data-stu-id="56cc0-115">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="56cc0-116">Moduły kontenera zawierają *gniazda*.</span><span class="sxs-lookup"><span data-stu-id="56cc0-116">Container modules include *slots*.</span></span> <span data-ttu-id="56cc0-117">Gniazda służą do obsługi układu i celu modułów podrzędnych w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="56cc0-117">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="56cc0-118">Przykładem jest podstawowy moduł kontenera strony (moduł najwyższego poziomu dla dowolnej strony), który definiuje kilka ważnych gniazd:</span><span class="sxs-lookup"><span data-stu-id="56cc0-118">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="56cc0-119">Gniazdo nagłówka</span><span class="sxs-lookup"><span data-stu-id="56cc0-119">A header slot</span></span>
- <span data-ttu-id="56cc0-120">Miejsce na nagłówek podrzędny</span><span class="sxs-lookup"><span data-stu-id="56cc0-120">A sub-header slot</span></span>
- <span data-ttu-id="56cc0-121">Miejsce główne</span><span class="sxs-lookup"><span data-stu-id="56cc0-121">A main slot</span></span>
- <span data-ttu-id="56cc0-122">Gniazdo stopki</span><span class="sxs-lookup"><span data-stu-id="56cc0-122">A footer slot</span></span>
- <span data-ttu-id="56cc0-123">Miejsce na stopkę podrzędną</span><span class="sxs-lookup"><span data-stu-id="56cc0-123">A sub-footer slot</span></span>

<span data-ttu-id="56cc0-124">Programista modułu definiuje te gniazda i określa, które moduły podrzędne i ile modułów podrzędnych może być bezpośrednio w nim umieszczonych.</span><span class="sxs-lookup"><span data-stu-id="56cc0-124">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="56cc0-125">Na przykład gniazdo nagłówka może obsługiwać tylko jeden **moduł nagłówka**, podczas gdy miejsce w treści może obsługiwać nieograniczoną liczbę modułów dowolnego typu (z wyjątkiem innych modułów kontenerów stron).</span><span class="sxs-lookup"><span data-stu-id="56cc0-125">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="56cc0-126">W narzędziach autorskich autorzy stron nie muszą znać z góry, które moduły mogą zostać umieszczone w poszczególnych gniazdach.</span><span class="sxs-lookup"><span data-stu-id="56cc0-126">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="56cc0-127">Gdy autorzy stron wybierają gniazdo, a następnie próbują wybrać moduł, który ma zostać dodany, zobaczą filtrowany widok typów modułów obsługiwanych dla tego gniazda.</span><span class="sxs-lookup"><span data-stu-id="56cc0-127">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="56cc0-128">Moduły zawartości</span><span class="sxs-lookup"><span data-stu-id="56cc0-128">Content modules</span></span>

<span data-ttu-id="56cc0-129">Moduły zawartości zawierają zawartość i elementy multimedialne, takie jak tekst (na przykład nagłówki, akapity, łącza) lub odwołania do składników aktywów (np. obrazy, pliki wideo i pliki PDF).</span><span class="sxs-lookup"><span data-stu-id="56cc0-129">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="56cc0-130">Typowe typy modułów treści obejmują bloki treści, bloki tekstowe i moduły banerów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="56cc0-130">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="56cc0-131">Moduły tych trzech typów mogą zawierać tekst lub nośniki i nie wymagają żadnych modułów podrzędnych, aby coś nie było widoczne na stronie.</span><span class="sxs-lookup"><span data-stu-id="56cc0-131">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="56cc0-132">Większość typowych działań na stronie codzienne i tworzenie zawartości obejmuje moduły zawartości, głównie dlatego, że moduły te definiują rzeczywistą zawartość renderowaną w ich nadrzędnych modułach kontenera.</span><span class="sxs-lookup"><span data-stu-id="56cc0-132">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="56cc0-133">Dostępnych jest wiele modułów zawartości, a zazwyczaj te moduły są zwykle ostatnimi fragmentami, które zostaną dodane do hierarchii zagnieżdżonych modułów strony.</span><span class="sxs-lookup"><span data-stu-id="56cc0-133">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="56cc0-134">Na poniższej ilustracji pokazano, jak moduły są zagnieżdżone w gniazdach nadrzędnego modułu kontenera.</span><span class="sxs-lookup"><span data-stu-id="56cc0-134">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Moduły zagnieżdżone](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="56cc0-136">Dodaj lub usuń moduły</span><span class="sxs-lookup"><span data-stu-id="56cc0-136">Add or remove modules</span></span>

<span data-ttu-id="56cc0-137">W poniższych procedurach opisano sposób dodawania i usuwania modułów.</span><span class="sxs-lookup"><span data-stu-id="56cc0-137">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="56cc0-138">Dodaj moduł</span><span class="sxs-lookup"><span data-stu-id="56cc0-138">Add a module</span></span>

<span data-ttu-id="56cc0-139">Aby dodać moduł do boksu lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-139">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-140">W panelu konturu po lewej stronie lub bezpośrednio w głównym obszarze roboczym wybierz kontener lub boks, do którego można dodać moduł podrzędny.</span><span class="sxs-lookup"><span data-stu-id="56cc0-140">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56cc0-141">Projektant modułu definiuje listę typów modułów, które można dodać do określonego gniazda modułu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-141">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="56cc0-142">Autorzy szablonów mogą następnie doprecyzować dozwolone opcje modułu, aby zagwarantować spójną optymalizację pod kątem wyszukiwarek (SEO) i wydajność tworzenia dla wszystkich stron utworzonych na podstawie określonego szablonu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-142">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="56cc0-143">Po dodaniu modułu do miejsca, okno dialogowe **Dodaj moduł** jest automatycznie filtrowane, więc pokazuje tylko te moduły, które są obsługiwane w wybranym kontenerze lub gnieździe.</span><span class="sxs-lookup"><span data-stu-id="56cc0-143">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="56cc0-144">Ta lista dozwolonych modułów jest określana przez szablon strony lub definicję modułu kontenera.</span><span class="sxs-lookup"><span data-stu-id="56cc0-144">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="56cc0-145">Jeśli korzystasz z okienka konturu, wybierz wielokropek (**...**) obok nazwy modułu, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="56cc0-145">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="56cc0-146">W przypadku używania kontrolek bezpośrednio na obszarze roboczym wybierz symbol plus (**+**) w pustym gnieździe lub obok aktualnie wybranego modułu, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="56cc0-146">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56cc0-147">Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj moduł** jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="56cc0-147">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="56cc0-148">W oknie dialogowym **Dodaj moduł** wybierz moduł, który chcesz dodać do swojej strony.</span><span class="sxs-lookup"><span data-stu-id="56cc0-148">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="56cc0-149">**Blok zawartości** jest dobrym typem modułu dla początkujących do pracy z systemem.</span><span class="sxs-lookup"><span data-stu-id="56cc0-149">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="56cc0-150">Wybierz przycisk **OK**, aby dodać wybrany moduł do wybranego kontenera lub gniazda na stronie.</span><span class="sxs-lookup"><span data-stu-id="56cc0-150">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="56cc0-151">Usuń moduł</span><span class="sxs-lookup"><span data-stu-id="56cc0-151">Remove a module</span></span>

<span data-ttu-id="56cc0-152">Aby usunąć moduł z gniazda lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-152">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-153">W panelu konturu po lewej stronie wybierz wielokropek (**...**) obok nazwy modułu do usunięcia, a następnie wybierz symbol kosza.</span><span class="sxs-lookup"><span data-stu-id="56cc0-153">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="56cc0-154">Alternatywnie, w głównym obszarze roboczym możesz wybrać symbol kosza na pasku narzędzi wybranego modułu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-154">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="56cc0-155">Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia modułu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="56cc0-155">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="56cc0-156">Przenieś moduł w nowe miejsce</span><span class="sxs-lookup"><span data-stu-id="56cc0-156">Move a module to a new position</span></span>

<span data-ttu-id="56cc0-157">Aby przenieść moduł w nowe miejsce na stronie, należy skorzystać z dowolnej z poniższych metod.</span><span class="sxs-lookup"><span data-stu-id="56cc0-157">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="56cc0-158">Przenoszenie modułu za pomocą okienka konturu</span><span class="sxs-lookup"><span data-stu-id="56cc0-158">Move a module using the outline pane</span></span>

<span data-ttu-id="56cc0-159">Aby przenieść moduł za pomocą okienka konturu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-159">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-160">Wybierz i przytrzymaj moduł, który chcesz przenieść w okienku konspektu, a następnie przeciągnij moduł do nowego położenia w konturu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-160">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="56cc0-161">Niebieska linia w konspekcie i na kanwie wskazuje miejsce, w którym można umieścić moduł.</span><span class="sxs-lookup"><span data-stu-id="56cc0-161">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="56cc0-162">Zwolnij moduł, aby przenieść go do nowego miejsca.</span><span class="sxs-lookup"><span data-stu-id="56cc0-162">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="56cc0-163">Przenoszenie modułu bezpośrednio w obszarze roboczym</span><span class="sxs-lookup"><span data-stu-id="56cc0-163">Move a module directly within the canvas</span></span>

<span data-ttu-id="56cc0-164">Aby przenieść moduł bezpośrednio w obszarze roboczym, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-164">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-165">Wybierz moduł, który chcesz przenieść w kanwie.</span><span class="sxs-lookup"><span data-stu-id="56cc0-165">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="56cc0-166">Wybierz symbol strzałki skierowanej w górę lub w dół na pasku narzędzi modułu, a następnie przeciągnij strzałkę w nowe miejsce na stronie.</span><span class="sxs-lookup"><span data-stu-id="56cc0-166">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="56cc0-167">Niebieska linia na płótnie i kontur wskazuje, gdzie można umieścić moduł.</span><span class="sxs-lookup"><span data-stu-id="56cc0-167">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="56cc0-168">Jeśli modułu nie można przesunąć w górę lub w dół, ten symbol strzałki będzie wyszarzony.</span><span class="sxs-lookup"><span data-stu-id="56cc0-168">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="56cc0-169">Zwolnij moduł, aby przenieść go do nowego miejsca.</span><span class="sxs-lookup"><span data-stu-id="56cc0-169">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="56cc0-170">Przenoszenie modułu za pomocą menu elipsy</span><span class="sxs-lookup"><span data-stu-id="56cc0-170">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="56cc0-171">Aby przenieść moduł za pomocą manu elipsy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-171">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-172">Umożliwia wybranie modułu w konturze lub obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="56cc0-172">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="56cc0-173">Wybierz wielokropek (**...**) obok nazwy modułu w okienku konturu lub na pasku narzędzi modułu na kanwie.</span><span class="sxs-lookup"><span data-stu-id="56cc0-173">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="56cc0-174">Jeśli moduł może być przesunięty w górę lub w dół w kontenerze lub gnieździe, zostaną wyświetlone opcje **Przenoszenia w górę** lub **W dół**.</span><span class="sxs-lookup"><span data-stu-id="56cc0-174">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="56cc0-175">Wybierz odpowiednią opcję przenoszenia, aby przenieść moduł w górę lub w dół w stosunku do jego elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="56cc0-175">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="56cc0-176">Konfiguracja modułów</span><span class="sxs-lookup"><span data-stu-id="56cc0-176">Configure modules</span></span>

<span data-ttu-id="56cc0-177">Poniższe procedury opisują sposób konfigurowania modułów zawartości i kontenera.</span><span class="sxs-lookup"><span data-stu-id="56cc0-177">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="56cc0-178">Konfiguruj moduł zawartości</span><span class="sxs-lookup"><span data-stu-id="56cc0-178">Configure a content module</span></span>

<span data-ttu-id="56cc0-179">Aby skonfigurować moduł zawartości na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-179">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-180">W okienku konspektu z lewej strony rozwiń drzewo i wybierz jakikolwiek moduł zawartości (np. **Blok zawartości**).</span><span class="sxs-lookup"><span data-stu-id="56cc0-180">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="56cc0-181">Alternatywnie możesz wybrać moduł w głównym obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="56cc0-181">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="56cc0-182">W okienku właściwości modułu po prawej stronie wprowadź właściwości dla dowolnych kontrolek modułu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-182">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="56cc0-183">Na pasku poleceń wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="56cc0-183">On the command bar, select **Save**.</span></span> <span data-ttu-id="56cc0-184">Spowoduje to również odświeżenie kanwy podglądu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-184">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="56cc0-185">Edytuj właściwości tekstu modułu</span><span class="sxs-lookup"><span data-stu-id="56cc0-185">Edit module text properties</span></span>

<span data-ttu-id="56cc0-186">Właściwości tekstu modułu, które nie są tylko do odczytu, można edytować bezpośrednio na kanwie.</span><span class="sxs-lookup"><span data-stu-id="56cc0-186">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="56cc0-187">Aby edytować właściwości tekstu modułu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-187">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-188">Wybierz kontrolkę tekstu w obszarze roboczym, a następnie umieść kursor w miejscu, w którym chcesz edytować tekst.</span><span class="sxs-lookup"><span data-stu-id="56cc0-188">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="56cc0-189">Wpisz treść tekstu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-189">Enter your text content.</span></span>
1. <span data-ttu-id="56cc0-190">Wybierz gdziekolwiek poza zawartością tekstową, aby kontynuować edytowanie innej zawartości.</span><span class="sxs-lookup"><span data-stu-id="56cc0-190">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="56cc0-191">Wybór obrazu wbudowanego</span><span class="sxs-lookup"><span data-stu-id="56cc0-191">Inline image selection</span></span>

<span data-ttu-id="56cc0-192">Obrazy modułów, które nie są tylko do odczytu, można zmienić bezpośrednio z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="56cc0-192">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="56cc0-193">Aby wybrać nowy obraz dla modułu zawartości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-193">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-194">Kliknij dwukrotnie obraz w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="56cc0-194">In the canvas, double-click the image.</span></span> <span data-ttu-id="56cc0-195">Spowoduje to wyświetlenie okna selektor nośników.</span><span class="sxs-lookup"><span data-stu-id="56cc0-195">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="56cc0-196">Znajdź i wybierz nowy obraz, którego chcesz użyć, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="56cc0-196">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="56cc0-197">Nowy obraz jest teraz odwzorowany na kanwie.</span><span class="sxs-lookup"><span data-stu-id="56cc0-197">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="56cc0-198">Konfigurowanie modułu kontenera</span><span class="sxs-lookup"><span data-stu-id="56cc0-198">Configure a container module</span></span>

<span data-ttu-id="56cc0-199">Aby skonfigurować moduł kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="56cc0-199">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="56cc0-200">Wybierz moduł kontenera na stronie (np. karuzela lub moduł kontener płynny).</span><span class="sxs-lookup"><span data-stu-id="56cc0-200">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="56cc0-201">W okienku właściwości po prawej stronie rozwiń formanty zagnieżdżone, zaznaczając nagłówki i ustawiając wymagane wartości kontrolne.</span><span class="sxs-lookup"><span data-stu-id="56cc0-201">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="56cc0-202">W okienku konspektu po lewej wybierz przycisk wielokropka obok nazwy kontenera lub dowolnych szczelin w kontenerze, a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="56cc0-202">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="56cc0-203">Następnie Dodaj moduły podrzędne do wybranego kontenera.</span><span class="sxs-lookup"><span data-stu-id="56cc0-203">Then, add child modules to the selected container.</span></span> <span data-ttu-id="56cc0-204">Aby uzyskać więcej informacji, zobacz sekcję [Praca z modułami](#add-a-module) we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="56cc0-204">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="56cc0-205">Jeśli w kontenerze nadrzędnym istnieje wiele modułów podrzędnych jako elementy równorzędne, można zmienić kolejność wyświetlania w kontenerze nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="56cc0-205">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="56cc0-206">Wybierz przycisk wielokropek dla modułu, a następnie użyj przycisków strzałki w górę i strzałki w dół.</span><span class="sxs-lookup"><span data-stu-id="56cc0-206">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56cc0-207">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="56cc0-207">Additional resources</span></span>

[<span data-ttu-id="56cc0-208">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="56cc0-208">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="56cc0-209">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="56cc0-209">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="56cc0-210">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="56cc0-210">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="56cc0-211">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="56cc0-211">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="56cc0-212">Dodawanie modułu kontenera do strony</span><span class="sxs-lookup"><span data-stu-id="56cc0-212">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="56cc0-213">Praca z grupami publikowania</span><span class="sxs-lookup"><span data-stu-id="56cc0-213">Work with publish groups</span></span>](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
