---
title: Praca z modułami
description: W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: eddee09fa81c18bc464b7768921981e6b5159a3e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210906"
---
# <a name="work-with-modules"></a><span data-ttu-id="effbe-103">Praca z modułami</span><span class="sxs-lookup"><span data-stu-id="effbe-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="effbe-104">W tym temacie opisano, jak i kiedy używać modułów w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="effbe-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="effbe-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="effbe-105">Overview</span></span>

<span data-ttu-id="effbe-106">Moduły są logicznymi blokami konstrukcyjnymi, które tworzą strukturę strony i mają różne cele i zakresy.</span><span class="sxs-lookup"><span data-stu-id="effbe-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="effbe-107">Niektóre moduły są kontenerami wysokiego poziomu, a jedynym celem jest przechowywanie i organizowanie innych modułów (modułów podrzędnych).</span><span class="sxs-lookup"><span data-stu-id="effbe-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="effbe-108">Inne moduły, takie jak prosty moduł rozmieszczenia obrazów, mają ściśle określony cel.</span><span class="sxs-lookup"><span data-stu-id="effbe-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="effbe-109">Inne moduły, takie jak moduł karuzeli, znajdują się gdzieś między tymi dwiema kategoriami.</span><span class="sxs-lookup"><span data-stu-id="effbe-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="effbe-110">Domyślnie witryna Dynamics 365 Commerce zawiera bibliotekę modułów, która umożliwia osiągnięcie większości podstawowych scenariuszy e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="effbe-110">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="effbe-111">Korzystając z tych modułów, można utworzyć kompleksową witrynę e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="effbe-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="effbe-112">Jednak można również dostosować te moduły lub utworzyć nowe niestandardowe moduły dla konkretnych potrzeb.</span><span class="sxs-lookup"><span data-stu-id="effbe-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="effbe-113">Jeśli użytkownik chce zbudować moduły niestandardowe, dostępny jest zestaw projektów Software Development Kit (SDK), który ułatwia tworzenie niestandardowych bibliotek modułów.</span><span class="sxs-lookup"><span data-stu-id="effbe-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="effbe-114">Moduły i gniazda kontenera</span><span class="sxs-lookup"><span data-stu-id="effbe-114">Container modules and slots</span></span>

<span data-ttu-id="effbe-115">Jak wspomniano wcześniej, niektóre moduły są przeznaczone do przechowywania modułów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="effbe-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="effbe-116">Moduły te są nazywane *kontenerami* i umożliwiają tworzenie hierarchii zagnieżdżonych modułów.</span><span class="sxs-lookup"><span data-stu-id="effbe-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="effbe-117">Moduły kontenera zawierają *gniazda*.</span><span class="sxs-lookup"><span data-stu-id="effbe-117">Container modules include *slots*.</span></span> <span data-ttu-id="effbe-118">Gniazda służą do obsługi układu i celu modułów podrzędnych w kontenerze.</span><span class="sxs-lookup"><span data-stu-id="effbe-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="effbe-119">Przykładem jest podstawowy moduł kontenera strony (moduł najwyższego poziomu dla dowolnej strony), który definiuje kilka ważnych gniazd:</span><span class="sxs-lookup"><span data-stu-id="effbe-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="effbe-120">Gniazdo nagłówka</span><span class="sxs-lookup"><span data-stu-id="effbe-120">A header slot</span></span>
- <span data-ttu-id="effbe-121">Miejsce na nagłówek podrzędny</span><span class="sxs-lookup"><span data-stu-id="effbe-121">A sub-header slot</span></span>
- <span data-ttu-id="effbe-122">Miejsce główne</span><span class="sxs-lookup"><span data-stu-id="effbe-122">A main slot</span></span>
- <span data-ttu-id="effbe-123">Gniazdo stopki</span><span class="sxs-lookup"><span data-stu-id="effbe-123">A footer slot</span></span>
- <span data-ttu-id="effbe-124">Miejsce na stopkę podrzędną</span><span class="sxs-lookup"><span data-stu-id="effbe-124">A sub-footer slot</span></span>

<span data-ttu-id="effbe-125">Programista modułu definiuje te gniazda i określa, które moduły podrzędne i ile modułów podrzędnych może być bezpośrednio w nim umieszczonych.</span><span class="sxs-lookup"><span data-stu-id="effbe-125">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="effbe-126">Na przykład gniazdo nagłówka może obsługiwać tylko jeden **moduł nagłówka**, podczas gdy miejsce w treści może obsługiwać nieograniczoną liczbę modułów dowolnego typu (z wyjątkiem innych modułów kontenerów stron).</span><span class="sxs-lookup"><span data-stu-id="effbe-126">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="effbe-127">W narzędziach autorskich autorzy stron nie muszą znać z góry, które moduły mogą zostać umieszczone w poszczególnych gniazdach.</span><span class="sxs-lookup"><span data-stu-id="effbe-127">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="effbe-128">Gdy autorzy stron wybierają gniazdo, a następnie próbują wybrać moduł, który ma zostać dodany, zobaczą filtrowany widok typów modułów obsługiwanych dla tego gniazda.</span><span class="sxs-lookup"><span data-stu-id="effbe-128">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="effbe-129">Moduły zawartości</span><span class="sxs-lookup"><span data-stu-id="effbe-129">Content modules</span></span>

<span data-ttu-id="effbe-130">Moduły zawartości zawierają zawartość i elementy multimedialne, takie jak tekst (na przykład nagłówki, akapity, łącza) lub odwołania do składników aktywów (np. obrazy, pliki wideo i pliki PDF).</span><span class="sxs-lookup"><span data-stu-id="effbe-130">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="effbe-131">Typowe typy modułów treści obejmują bloki treści, bloki tekstowe i moduły banerów promocyjnych.</span><span class="sxs-lookup"><span data-stu-id="effbe-131">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="effbe-132">Moduły tych trzech typów mogą zawierać tekst lub nośniki i nie wymagają żadnych modułów podrzędnych, aby coś nie było widoczne na stronie.</span><span class="sxs-lookup"><span data-stu-id="effbe-132">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="effbe-133">Większość typowych działań na stronie codzienne i tworzenie zawartości obejmuje moduły zawartości, głównie dlatego, że moduły te definiują rzeczywistą zawartość renderowaną w ich nadrzędnych modułach kontenera.</span><span class="sxs-lookup"><span data-stu-id="effbe-133">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="effbe-134">Dostępnych jest wiele modułów zawartości, a zazwyczaj te moduły są zwykle ostatnimi fragmentami, które zostaną dodane do hierarchii zagnieżdżonych modułów strony.</span><span class="sxs-lookup"><span data-stu-id="effbe-134">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="effbe-135">Na poniższej ilustracji pokazano, jak moduły są zagnieżdżone w gniazdach nadrzędnego modułu kontenera.</span><span class="sxs-lookup"><span data-stu-id="effbe-135">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Moduły zagnieżdżone](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="effbe-137">Dodaj lub usuń moduły</span><span class="sxs-lookup"><span data-stu-id="effbe-137">Add or remove modules</span></span>

<span data-ttu-id="effbe-138">W poniższych procedurach opisano sposób dodawania i usuwania modułów.</span><span class="sxs-lookup"><span data-stu-id="effbe-138">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="effbe-139">Dodaj moduł</span><span class="sxs-lookup"><span data-stu-id="effbe-139">Add a module</span></span>

<span data-ttu-id="effbe-140">Aby dodać moduł do boksu lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-140">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="effbe-141">W panelu konturu po lewej stronie lub bezpośrednio w głównym obszarze roboczym wybierz kontener lub boks, do którego można dodać moduł podrzędny.</span><span class="sxs-lookup"><span data-stu-id="effbe-141">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="effbe-142">Projektant modułu definiuje listę typów modułów, które można dodać do określonego gniazda modułu.</span><span class="sxs-lookup"><span data-stu-id="effbe-142">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="effbe-143">Autorzy szablonów mogą następnie doprecyzować dozwolone opcje modułu, aby zagwarantować spójną optymalizację pod kątem wyszukiwarek (SEO) i wydajność tworzenia dla wszystkich stron utworzonych na podstawie określonego szablonu.</span><span class="sxs-lookup"><span data-stu-id="effbe-143">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="effbe-144">Po dodaniu modułu do miejsca, okno dialogowe **Dodaj moduł** jest automatycznie filtrowane, więc pokazuje tylko te moduły, które są obsługiwane w wybranym kontenerze lub gnieździe.</span><span class="sxs-lookup"><span data-stu-id="effbe-144">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="effbe-145">Ta lista dozwolonych modułów jest określana przez szablon strony lub definicję modułu kontenera.</span><span class="sxs-lookup"><span data-stu-id="effbe-145">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="effbe-146">Jeśli korzystasz z okienka konturu, wybierz wielokropek (**...**) obok nazwy modułu, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="effbe-146">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="effbe-147">W przypadku używania kontrolek bezpośrednio na obszarze roboczym wybierz symbol plus (**+**) w pustym gnieździe lub obok aktualnie wybranego modułu, a następnie wybierz pozycję **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="effbe-147">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="effbe-148">Jeśli kontener lub gniazdo nie obsługuje nowych modułów podrzędnych, opcja **Dodaj moduł** jest niedostępna.</span><span class="sxs-lookup"><span data-stu-id="effbe-148">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="effbe-149">W oknie dialogowym **Dodaj moduł** wybierz moduł, który chcesz dodać do swojej strony.</span><span class="sxs-lookup"><span data-stu-id="effbe-149">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="effbe-150">**Blok zawartości** jest dobrym typem modułu dla początkujących do pracy z systemem.</span><span class="sxs-lookup"><span data-stu-id="effbe-150">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="effbe-151">Wybierz przycisk **OK**, aby dodać wybrany moduł do wybranego kontenera lub gniazda na stronie.</span><span class="sxs-lookup"><span data-stu-id="effbe-151">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="effbe-152">Usuń moduł</span><span class="sxs-lookup"><span data-stu-id="effbe-152">Remove a module</span></span>

<span data-ttu-id="effbe-153">Aby usunąć moduł z gniazda lub kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-153">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="effbe-154">W panelu konturu po lewej stronie wybierz wielokropek (**...**) obok nazwy modułu do usunięcia, a następnie wybierz symbol kosza.</span><span class="sxs-lookup"><span data-stu-id="effbe-154">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="effbe-155">Alternatywnie, w głównym obszarze roboczym możesz wybrać symbol kosza na pasku narzędzi wybranego modułu.</span><span class="sxs-lookup"><span data-stu-id="effbe-155">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="effbe-156">Po wyświetleniu monitu o potwierdzenie zamiaru usunięcia modułu wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="effbe-156">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="effbe-157">Przenieś moduł w nowe miejsce</span><span class="sxs-lookup"><span data-stu-id="effbe-157">Move a module to a new position</span></span>

<span data-ttu-id="effbe-158">Aby przenieść moduł w nowe miejsce na stronie, należy skorzystać z dowolnej z poniższych metod.</span><span class="sxs-lookup"><span data-stu-id="effbe-158">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="effbe-159">Przenoszenie modułu za pomocą okienka konturu</span><span class="sxs-lookup"><span data-stu-id="effbe-159">Move a module using the outline pane</span></span>

<span data-ttu-id="effbe-160">Aby przenieść moduł za pomocą okienka konturu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-160">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="effbe-161">Wybierz i przytrzymaj moduł, który chcesz przenieść w okienku konspektu, a następnie przeciągnij moduł do nowego położenia w konturu.</span><span class="sxs-lookup"><span data-stu-id="effbe-161">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="effbe-162">Niebieska linia w konspekcie i na kanwie wskazuje miejsce, w którym można umieścić moduł.</span><span class="sxs-lookup"><span data-stu-id="effbe-162">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="effbe-163">Zwolnij moduł, aby przenieść go do nowego miejsca.</span><span class="sxs-lookup"><span data-stu-id="effbe-163">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="effbe-164">Przenoszenie modułu bezpośrednio w obszarze roboczym</span><span class="sxs-lookup"><span data-stu-id="effbe-164">Move a module directly within the canvas</span></span>

<span data-ttu-id="effbe-165">Aby przenieść moduł bezpośrednio w obszarze roboczym, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-165">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="effbe-166">Wybierz moduł, który chcesz przenieść w kanwie.</span><span class="sxs-lookup"><span data-stu-id="effbe-166">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="effbe-167">Wybierz symbol strzałki skierowanej w górę lub w dół na pasku narzędzi modułu, a następnie przeciągnij strzałkę w nowe miejsce na stronie.</span><span class="sxs-lookup"><span data-stu-id="effbe-167">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="effbe-168">Niebieska linia na płótnie i kontur wskazuje, gdzie można umieścić moduł.</span><span class="sxs-lookup"><span data-stu-id="effbe-168">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="effbe-169">Jeśli modułu nie można przesunąć w górę lub w dół, ten symbol strzałki będzie wyszarzony.</span><span class="sxs-lookup"><span data-stu-id="effbe-169">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="effbe-170">Zwolnij moduł, aby przenieść go do nowego miejsca.</span><span class="sxs-lookup"><span data-stu-id="effbe-170">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="effbe-171">Przenoszenie modułu za pomocą menu elipsy</span><span class="sxs-lookup"><span data-stu-id="effbe-171">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="effbe-172">Aby przenieść moduł za pomocą manu elipsy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-172">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="effbe-173">Umożliwia wybranie modułu w konturze lub obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="effbe-173">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="effbe-174">Wybierz wielokropek (**...**) obok nazwy modułu w okienku konturu lub na pasku narzędzi modułu na kanwie.</span><span class="sxs-lookup"><span data-stu-id="effbe-174">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="effbe-175">Jeśli moduł może być przesunięty w górę lub w dół w kontenerze lub gnieździe, zostaną wyświetlone opcje **Przenoszenia w górę** lub **W dół**.</span><span class="sxs-lookup"><span data-stu-id="effbe-175">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="effbe-176">Wybierz odpowiednią opcję przenoszenia, aby przenieść moduł w górę lub w dół w stosunku do jego elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="effbe-176">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="effbe-177">Konfiguracja modułów</span><span class="sxs-lookup"><span data-stu-id="effbe-177">Configure modules</span></span>

<span data-ttu-id="effbe-178">Poniższe procedury opisują sposób konfigurowania modułów zawartości i kontenera.</span><span class="sxs-lookup"><span data-stu-id="effbe-178">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="effbe-179">Konfiguruj moduł zawartości</span><span class="sxs-lookup"><span data-stu-id="effbe-179">Configure a content module</span></span>

<span data-ttu-id="effbe-180">Aby skonfigurować moduł zawartości na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-180">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="effbe-181">W okienku konspektu z lewej strony rozwiń drzewo i wybierz jakikolwiek moduł zawartości (np. **Blok zawartości**).</span><span class="sxs-lookup"><span data-stu-id="effbe-181">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="effbe-182">Alternatywnie możesz wybrać moduł w głównym obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="effbe-182">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="effbe-183">W okienku właściwości modułu po prawej stronie wprowadź właściwości dla dowolnych kontrolek modułu.</span><span class="sxs-lookup"><span data-stu-id="effbe-183">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="effbe-184">Na pasku poleceń wybierz **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="effbe-184">On the command bar, select **Save**.</span></span> <span data-ttu-id="effbe-185">Spowoduje to również odświeżenie kanwy podglądu.</span><span class="sxs-lookup"><span data-stu-id="effbe-185">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="effbe-186">Edytuj właściwości tekstu modułu</span><span class="sxs-lookup"><span data-stu-id="effbe-186">Edit module text properties</span></span>

<span data-ttu-id="effbe-187">Właściwości tekstu modułu, które nie są tylko do odczytu, można edytować bezpośrednio na kanwie.</span><span class="sxs-lookup"><span data-stu-id="effbe-187">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="effbe-188">Aby edytować właściwości tekstu modułu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-188">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="effbe-189">Wybierz kontrolkę tekstu w obszarze roboczym, a następnie umieść kursor w miejscu, w którym chcesz edytować tekst.</span><span class="sxs-lookup"><span data-stu-id="effbe-189">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="effbe-190">Wpisz treść tekstu.</span><span class="sxs-lookup"><span data-stu-id="effbe-190">Enter your text content.</span></span>
1. <span data-ttu-id="effbe-191">Wybierz gdziekolwiek poza zawartością tekstową, aby kontynuować edytowanie innej zawartości.</span><span class="sxs-lookup"><span data-stu-id="effbe-191">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="effbe-192">Wybór obrazu wbudowanego</span><span class="sxs-lookup"><span data-stu-id="effbe-192">Inline image selection</span></span>

<span data-ttu-id="effbe-193">Obrazy modułów, które nie są tylko do odczytu, można zmienić bezpośrednio z obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="effbe-193">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="effbe-194">Aby wybrać nowy obraz dla modułu zawartości, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-194">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="effbe-195">Kliknij dwukrotnie obraz w obszarze roboczym.</span><span class="sxs-lookup"><span data-stu-id="effbe-195">In the canvas, double-click the image.</span></span> <span data-ttu-id="effbe-196">Spowoduje to wyświetlenie okna selektor nośników.</span><span class="sxs-lookup"><span data-stu-id="effbe-196">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="effbe-197">Znajdź i wybierz nowy obraz, którego chcesz użyć, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="effbe-197">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="effbe-198">Nowy obraz jest teraz odwzorowany na kanwie.</span><span class="sxs-lookup"><span data-stu-id="effbe-198">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="effbe-199">Konfigurowanie modułu kontenera</span><span class="sxs-lookup"><span data-stu-id="effbe-199">Configure a container module</span></span>

<span data-ttu-id="effbe-200">Aby skonfigurować moduł kontenera na stronie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="effbe-200">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="effbe-201">Wybierz moduł kontenera na stronie (np. karuzela lub moduł kontener płynny).</span><span class="sxs-lookup"><span data-stu-id="effbe-201">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="effbe-202">W okienku właściwości po prawej stronie rozwiń formanty zagnieżdżone, zaznaczając nagłówki i ustawiając wymagane wartości kontrolne.</span><span class="sxs-lookup"><span data-stu-id="effbe-202">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="effbe-203">W okienku konspektu po lewej wybierz przycisk wielokropka obok nazwy kontenera lub dowolnych szczelin w kontenerze, a następnie wybierz **Dodaj moduł**.</span><span class="sxs-lookup"><span data-stu-id="effbe-203">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="effbe-204">Następnie Dodaj moduły podrzędne do wybranego kontenera.</span><span class="sxs-lookup"><span data-stu-id="effbe-204">Then, add child modules to the selected container.</span></span> <span data-ttu-id="effbe-205">Aby uzyskać więcej informacji, zobacz sekcję [Praca z modułami](#add-a-module) we wcześniejszej części tego tematu.</span><span class="sxs-lookup"><span data-stu-id="effbe-205">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="effbe-206">Jeśli w kontenerze nadrzędnym istnieje wiele modułów podrzędnych jako elementy równorzędne, można zmienić kolejność wyświetlania w kontenerze nadrzędnym.</span><span class="sxs-lookup"><span data-stu-id="effbe-206">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="effbe-207">Wybierz przycisk wielokropek dla modułu, a następnie użyj przycisków strzałki w górę i strzałki w dół.</span><span class="sxs-lookup"><span data-stu-id="effbe-207">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="effbe-208">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="effbe-208">Additional resources</span></span>

[<span data-ttu-id="effbe-209">Omówienie szablonów i układów</span><span class="sxs-lookup"><span data-stu-id="effbe-209">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="effbe-210">Praca z szablonami</span><span class="sxs-lookup"><span data-stu-id="effbe-210">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="effbe-211">Praca z układami predefiniowanymi</span><span class="sxs-lookup"><span data-stu-id="effbe-211">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="effbe-212">Praca z fragmentami</span><span class="sxs-lookup"><span data-stu-id="effbe-212">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="effbe-213">Dodawanie modułu kontenera do strony</span><span class="sxs-lookup"><span data-stu-id="effbe-213">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="effbe-214">Praca z grupami publikowania</span><span class="sxs-lookup"><span data-stu-id="effbe-214">Work with publish groups</span></span>](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]