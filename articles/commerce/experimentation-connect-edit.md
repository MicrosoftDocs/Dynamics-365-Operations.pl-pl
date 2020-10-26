---
title: Łączenie eksperymentu i edytowanie odmian
description: W tym temacie opisano sposób łączenia eksperymentów z usługą innej firmy z systemem Dynamics 365 Commerce i edytowania odmian eksperymentu.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ea1da0a7dc90b7197f3ee532bccc55d2ddbe4ddd
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930270"
---
# <a name="connect-an-experiment-and-edit-variations"></a><span data-ttu-id="e6c6c-103">Łączenie eksperymentu i edytowanie odmian</span><span class="sxs-lookup"><span data-stu-id="e6c6c-103">Connect an experiment and edit variations</span></span>

<span data-ttu-id="e6c6c-104">W tym temacie opisano sposób łączenia doświadczenia w Commerce i wprowadzania zmian w odmianach, dzięki czemu są one zgodne z hipotezą.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-104">This topic describes how to connect your experiment in Commerce and make changes to your variations so they align with your hypothesis.</span></span> <span data-ttu-id="e6c6c-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="e6c6c-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="e6c6c-107">[ ![Proces użytkownika eksperymentu — łączenie i edycja](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e6c6c-107">[ ![Experimentation user journey - Connect & Edit](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span></span>

<span data-ttu-id="e6c6c-108">Po [skonfigurowaniu eksperymentu](experimentation-setup.md) w usłudze innej firmy nastąpi połączenie eksperymentu w Dynamics 365 Commerce i edycja odmian eksperymentów.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-108">After you've [set up your experiment](experimentation-setup.md) in a third-party service, you'll connect the experiment in Dynamics 365 Commerce and edit the experiment variations.</span></span>

## <a name="planning-considerations"></a><span data-ttu-id="e6c6c-109">Uwagi dotyczące planowania</span><span class="sxs-lookup"><span data-stu-id="e6c6c-109">Planning considerations</span></span>

<span data-ttu-id="e6c6c-110">Przed połączeniem eksperymentu w Commerce trzeba wprowadzić kilka decyzji, które wpływają na sposób zarządzania zawartością przez Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-110">Before you connect your experiment in Commerce, you'll need to make some decisions that impact the way Commerce manages your content.</span></span>

### <a name="determine-the-scope-of-your-experiment"></a><span data-ttu-id="e6c6c-111">Określanie zakresu eksperymentu</span><span class="sxs-lookup"><span data-stu-id="e6c6c-111">Determine the scope of your experiment</span></span>
<span data-ttu-id="e6c6c-112">Po połączeniu eksperymentu zostanie wyświetlony monit o zdefiniowanie zakresu eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-112">When you connect an experiment, you are prompted to define the scope of the experiment.</span></span> <span data-ttu-id="e6c6c-113">Eksperymenty są zdefiniowane jako zakres **częściowy** lub **cały**.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-113">Experiments are defined as **partial** scope or **entire** scope.</span></span>
- <span data-ttu-id="e6c6c-114">Wybierz opcję **częściowy**, jeśli chcesz przeprowadzić eksperyment na konkretnej części strony.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-114">Choose **partial** if you want to conduct an experiment on a specific portion of a page.</span></span> <span data-ttu-id="e6c6c-115">Po wybraniu tej opcji należy określić, które moduły mają być uwzględniane w eksperymencie.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-115">If you select this option, you must identify which modules are included in the experiment.</span></span> <span data-ttu-id="e6c6c-116">Zmiany wprowadzane w częściach domyślnej strony lub fragmentu, które nie są związane z eksperymentem, są automatycznie synchronizowane w różnych odmianach.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-116">Changes that are made to parts of the default page or fragment that aren't related to the experiment are automatically synchronized across variations.</span></span>
- <span data-ttu-id="e6c6c-117">Wybierz opcję **cały**, jeśli chcesz prowadzić eksperyment na całej stronie lub fragmencie.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-117">Choose **entire** if you want to conduct an experiment on an entire page or fragment.</span></span> <span data-ttu-id="e6c6c-118">Zostaną utworzone oddzielne kopie domyślnej strony lub fragmentu.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-118">Separate copies of the default page or fragment are created.</span></span> <span data-ttu-id="e6c6c-119">Nie trzeba wybierać modułów, które zostaną uwzględnione w eksperymencie, ponieważ cała powierzchnia edycji jest dostępna do zmiany.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-119">You won't have to select which modules are included in the experiment because the whole editing surface is available to change.</span></span> <span data-ttu-id="e6c6c-120">W razie potrzeby można dodawać, usuwać i ponownie zamawiać moduły.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-120">You can add, delete, and re-order modules as needed.</span></span> <span data-ttu-id="e6c6c-121">Jeśli jednak zostaną wprowadzone jakiekolwiek zmiany do strony domyślnej lub fragmentu, z którym jest skojarzona eksperyment, zmiany te muszą być synchronizowane ręcznie we wszystkich odmianach.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-121">However, if any changes are made to the default page or fragment that the experiment is associated with, those changes have to be manually synchronized across all variations.</span></span>

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> <span data-ttu-id="e6c6c-122">Jeśli użytkownik skojarzy eksperyment ze stroną korzystającą z układu, może wybrać tylko **cały** zakres eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-122">If you associate your experiment with a page that uses a layout, you can only scope the experiment as **entire**.</span></span>

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a><span data-ttu-id="e6c6c-123">Określanie, czy chcesz zaplanować, kiedy eksperyment jest opublikowany</span><span class="sxs-lookup"><span data-stu-id="e6c6c-123">Decide if you want to schedule when your experiment is published</span></span>
<span data-ttu-id="e6c6c-124">Aby zaplanować, kiedy eksperyment zostanie opublikowany w działającej witrynie, upewnij się, że zawartość, którą chcesz skojarzyć z eksperymentem, jest dostępna w grupie publikowania *przed* połączeniem eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-124">If you want to schedule when your experiment is published to your live site, make sure the content you want to associate with the experiment is available in a publish group *before* you connect the experiment.</span></span> 

<span data-ttu-id="e6c6c-125">Aby uzyskać więcej informacji o grupach publikacji, zobacz temat [Praca z grupami publikacji](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e6c6c-125">For more information about publish groups, refer to [Work with publish groups](publish-groups.md).</span></span>


## <a name="connect-your-experiment"></a><span data-ttu-id="e6c6c-126">Łączenie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="e6c6c-126">Connect your experiment</span></span>
<span data-ttu-id="e6c6c-127">Aby połączyć eksperyment, należy uruchomić kreatora **Łączenie eksperymentów**.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-127">To connect your experiment, you'll launch the **Connect experiment** wizard.</span></span> <span data-ttu-id="e6c6c-128">Kreator przeprowadzi Cię przez kroki wymagane do połączenia eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-128">The wizard walks you through the steps required to connect your experiment.</span></span> <span data-ttu-id="e6c6c-129">Po zakończeniu pracy kreatora eksperyment jest połączony, a zmiany są tworzone i gotowe do edycji.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-129">When you complete the wizard, your experiment is connected and variations are created and ready to be edited.</span></span>

1. <span data-ttu-id="e6c6c-130">Aby uruchomić kreatora, wybierz kartę **Eksperymenty** w konstruktorze witryn, a następnie wybierz opcję **Połącz**.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-130">To launch the wizard, select the **Experiments** tab in site builder and then select **Connect**.</span></span> <span data-ttu-id="e6c6c-131">Alternatywnie można uzyskać dostęp do kreatora ze strony lub z edytora fragmentów.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-131">Alternatively, the wizard can be accessed from a page or fragment editor.</span></span> <span data-ttu-id="e6c6c-132">W trybie edycji wybierz opcję **Połącz eksperyment** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-132">In edit mode, select **Connect experiment** in the command bar.</span></span>

> [!NOTE]
> <span data-ttu-id="e6c6c-133">Strona może być połączona tylko z jednym eksperymentem naraz.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-133">A page can only be connected to one experiment at a time.</span></span> <span data-ttu-id="e6c6c-134">Aby połączyć stronę z innym eksperymentem, należy najpierw usunąć eksperyment, z którym jest obecnie połączona strona.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-134">To connect a page to a different experiment, first delete the experiment that the page is currently connected to.</span></span>

1. <span data-ttu-id="e6c6c-135">Wybierz stronę lub fragment, na którym ma być uruchomiony eksperyment.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-135">Choose the page or fragment you want to run your experiment on.</span></span>
1. <span data-ttu-id="e6c6c-136">Umożliwia ustawienie zakresu eksperymentów na **częściowy** lub **cały** w zależności od wyboru dokonanego w sekcji [Określ zakres doświadczenia](#determine-the-scope-of-your-experiment) powyżej.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-136">Set the experimentation scope to **partial** or **entire**, based on the choice you made in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>
    > [!NOTE]
    > <span data-ttu-id="e6c6c-137">Aby eksperymentować z pełną stroną lub fragmentem, należy włączyć flagę funkcji **Eksperymentowanie ze stronami lub fragmentami**.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-137">The **Experiment on pages or fragments** feature flag must be enabled if you want to experiment on a full page or fragment.</span></span> <span data-ttu-id="e6c6c-138">Aby uzyskać więcej informacji, zobacz temat [Eksperymentowanie w programie Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e6c6c-138">Refer to the [Experimentation in Dynamics 365 Commerce](experimentation-overview.md) topic for more information.</span></span>
    
1. <span data-ttu-id="e6c6c-139">W ostatnim kroku kreatora wybierz opcję **Wygeneruj odmiany i zakończ kreatora**.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-139">In the final step of the wizard, select **Generate variations and exit wizard**.</span></span> <span data-ttu-id="e6c6c-140">Zostaną utworzone odmiany eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-140">Variations are created for the experiment.</span></span> 

## <a name="edit-your-variations"></a><span data-ttu-id="e6c6c-141">Edycja odmian</span><span class="sxs-lookup"><span data-stu-id="e6c6c-141">Edit your variations</span></span>
<span data-ttu-id="e6c6c-142">Po zamknięciu kreatora zostaną utworzone odmiany.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-142">When you exit the wizard, variations are created for you.</span></span> 

<span data-ttu-id="e6c6c-143">Następnie dokonasz edycji odmian, aby odzwierciedlały opcje, które trzeba zweryfikować w hipotezie.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-143">Next, you'll edit the variations so they reflect the choices that you need to verify in the experiment hypothesis.</span></span> <span data-ttu-id="e6c6c-144">Wybierz jedną z poniższych procedur, która odpowiada zakresowi wybranemu dla eksperymentu w powyższej sekcji [Określanie zakresu eksperymentu](#determine-the-scope-of-your-experiment).</span><span class="sxs-lookup"><span data-stu-id="e6c6c-144">Choose one of following procedures that corresponds to the scope you chose for your experiment in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>

### <a name="edit-variations-for-experiments-with-partial-scope"></a><span data-ttu-id="e6c6c-145">Edycja odmian eksperymentów z częściowym zakresem</span><span class="sxs-lookup"><span data-stu-id="e6c6c-145">Edit variations for experiments with partial scope</span></span>
<span data-ttu-id="e6c6c-146">Wykonaj poniższe kroki, jeśli w kreatorze **łączenia eksperymentów** został zdefiniowany **częściowy** zakres eksperymentu.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-146">Follow these steps if you defined the scope of your experiment as **partial** in the **Connect experiment** wizard.</span></span>

1. <span data-ttu-id="e6c6c-147">W widoku edytora za pomocą menu rozwijanego odmiany, znajdującego się pod paskiem poleceń, można edytować każdą odmianę w oparciu o hipotezę oryginalną.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-147">In editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> <span data-ttu-id="e6c6c-148">Można również określić kontrolę lub zmianę bazową, pozostawiając niezmienioną jedną z odmian.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-148">You may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>
1. <span data-ttu-id="e6c6c-149">Wybierz moduł do eksperymentowania, wybierz wielokropek (...), a następnie wybierz opcję **Dodaj do eksperymentu**.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-149">Select the module to be experimented on, select the ellipsis (...), and then select **Add to experiment**.</span></span>

### <a name="edit-variations-for-experiments-with-entire-scope"></a><span data-ttu-id="e6c6c-150">Edycja odmian eksperymentów z całkowitym zakresem</span><span class="sxs-lookup"><span data-stu-id="e6c6c-150">Edit variations for experiments with entire scope</span></span>
<span data-ttu-id="e6c6c-151">Jeśli zdefiniowano **całkowity** zakres eksperymentu w kreatorze **Łączenie eksperymentów**, to w widoku edytora należy skorzystać z menu rozwijanego odmiany poniżej paska poleceń, aby edytować poszczególne odmiany na podstawie hipotezy pierwotnej.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-151">If you defined the scope of your experiment as **entire** in the **Connect experiment** wizard, while in editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> 

> [!NOTE]
> <span data-ttu-id="e6c6c-152">W każdym przypadku można również określić kontrolę lub zmianę bazową, pozostawiając niezmienioną jedną z odmian.</span><span class="sxs-lookup"><span data-stu-id="e6c6c-152">In either case, you may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>

## <a name="previous-step"></a><span data-ttu-id="e6c6c-153">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="e6c6c-153">Previous step</span></span>
[<span data-ttu-id="e6c6c-154">Konfigurowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="e6c6c-154">Set up an experiment</span></span>](experimentation-setup.md) 


## <a name="next-step"></a><span data-ttu-id="e6c6c-155">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="e6c6c-155">Next step</span></span>
[<span data-ttu-id="e6c6c-156">Podgląd i publikowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="e6c6c-156">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)
