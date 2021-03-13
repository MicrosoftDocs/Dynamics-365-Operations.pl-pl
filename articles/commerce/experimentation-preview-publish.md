---
title: Podgląd i publikowanie eksperymentu
description: W tym temacie opisano sposób podglądu i publikowania eksperymentu z Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 32115378be00df771c6ff658da0c090446edf8b0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009955"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="878f8-103">Podgląd i publikowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="878f8-103">Preview and publish an experiment</span></span>

<span data-ttu-id="878f8-104">W tym temacie opisano sposób wyświetlania podglądu i publikowania eksperymentu w Dynamics 365 Commerce po [połączeniu eksperymentu i edytowaniu odmian](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="878f8-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="878f8-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="878f8-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="878f8-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="878f8-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="878f8-107">[ ![Proces użytkownika eksperymentu — podgląd i publikowanie](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="878f8-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="878f8-108">Podgląd odmian eksperymentu</span><span class="sxs-lookup"><span data-stu-id="878f8-108">Preview your experiment variations</span></span>
<span data-ttu-id="878f8-109">Możesz wyświetlić podgląd odmiany i kontynuować ich edycję, dopóki nie będą wyglądać odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="878f8-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

<span data-ttu-id="878f8-110">Aby wyświetlić podgląd odmian eksperymentu w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="878f8-110">To preview your experiment variations in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="878f8-111">Należy użyć menu rozwijanego odmiany pod paskiem poleceń, aby wybrać zawartość, której podgląd chcesz wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="878f8-111">From the variations drop-down menu below the command bar, select the content you want to preview.</span></span> 
1. <span data-ttu-id="878f8-112">Na pasku poleceń wybierz opcję **Podgląd**.</span><span class="sxs-lookup"><span data-stu-id="878f8-112">On the command bar, select **Preview**.</span></span> <span data-ttu-id="878f8-113">Zostanie wyświetlony podgląd zawartości, taki jak po opublikowaniu.</span><span class="sxs-lookup"><span data-stu-id="878f8-113">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="878f8-114">Aby wyświetlić podgląd innej odmiany, wybierz ją z menu rozwijanego odmian i wybierz ponownie **Podgląd**.</span><span class="sxs-lookup"><span data-stu-id="878f8-114">To preview a different variation, select it from the variation drop-down menu and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="878f8-115">Publikowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="878f8-115">Publish your experiment</span></span>
<span data-ttu-id="878f8-116">Jeśli nie używasz grupy publikowania do planowania, kiedy eksperymenty są aktywne i chcesz publikować natychmiast, wybierz opcję **Publikuj** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="878f8-116">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="878f8-117">Wszystkie odmiany należące do eksperymentu zostaną opublikowane.</span><span class="sxs-lookup"><span data-stu-id="878f8-117">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="878f8-118">Jeśli strona zawiera nieopublikowany adres URL, należy najpierw opublikować adres URL inaczej nie będzie widoczny dla użytkowników witryny internetowej.</span><span class="sxs-lookup"><span data-stu-id="878f8-118">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="878f8-119">Szczegółowe informacje zawiera temat [Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="878f8-119">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="878f8-120">Za pomocą grup publikacji można planować czas uruchomienia eksperymentu</span><span class="sxs-lookup"><span data-stu-id="878f8-120">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="878f8-121">Odmiany utworzone w konstruktorze witryn mogą być planowane do opublikowania za pomocą grupy publikacji.</span><span class="sxs-lookup"><span data-stu-id="878f8-121">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="878f8-122">W grupie publikacji można połączyć stronę lub fragment z eksperymentem, wybierając w lewym okienku nawigacji pozycję **Eksperymenty**.</span><span class="sxs-lookup"><span data-stu-id="878f8-122">Within a publish group, you can connect a page or fragment to your experiment by selecting **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="878f8-123">Można to również zrobić, wybierając **Strony** lub **Fragmenty** i postępując zgodnie z instrukcjami w [Łączenie eksperymentu i edytowanie odmian](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="878f8-123">You can also do this by selecting **Pages** or **Fragments** and following the instructions in [Connect an experiment and edit variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="878f8-124">Aby uzyskać informacje o grupach publikacji, zobacz temat [Praca z grupami publikacji](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="878f8-124">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="878f8-125">W przypadku korzystania z grup publikacji z eksperymentami należy pamiętać o pewnych ważnych kwestiach.</span><span class="sxs-lookup"><span data-stu-id="878f8-125">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="878f8-126">Po dodaniu do grupy publikacji strony lub fragmentu z uruchomionym eksperymentem zostanie on usunięty ze strony lub fragmentu w grupie publikacji.</span><span class="sxs-lookup"><span data-stu-id="878f8-126">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="878f8-127">Eksperymenty, które są połączone ze stronami w działającej witrynie, nie są dostępne dla stron w grupach publikacji i na odwrót.</span><span class="sxs-lookup"><span data-stu-id="878f8-127">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="878f8-128">Podobnie strony, które mają uruchomione eksperymenty w działającej witrynie, nie są dostępne dla innych eksperymentów w grupach publikacji i na odwrót.</span><span class="sxs-lookup"><span data-stu-id="878f8-128">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="878f8-129">Podczas publikowania lub planowania grupy publikacji cała zawartość w grupie publikacji jest publikowana niezależnie od tego, czy istnieje doświadczenie związane z grupą publikacji.</span><span class="sxs-lookup"><span data-stu-id="878f8-129">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="878f8-130">Ponieważ grupa publikacji nadal utrzymuje się po opublikowaniu jej w działającej witrynie, eksperymenty z grupy publikacji również będą się utrzymywać.</span><span class="sxs-lookup"><span data-stu-id="878f8-130">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="878f8-131">Dlatego nie będzie można kojarzyć innych eksperymentów z tą samą stroną lub fragmentem.</span><span class="sxs-lookup"><span data-stu-id="878f8-131">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="878f8-132">Aby uniknąć tego ograniczenia, usuń wszystkie grupy publikacji z trwałymi eksperymentami.</span><span class="sxs-lookup"><span data-stu-id="878f8-132">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="878f8-133">Podobnie, jeśli chcesz usunąć eksperyment w działającej witrynie, które istnieje również w grupie publikowania, najpierw usuń go z grupy publikacji.</span><span class="sxs-lookup"><span data-stu-id="878f8-133">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="878f8-134">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="878f8-134">Previous step</span></span>
[<span data-ttu-id="878f8-135">Łączenie i edytowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="878f8-135">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="878f8-136">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="878f8-136">Next step</span></span>
[<span data-ttu-id="878f8-137">Uruchamianie i monitorowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="878f8-137">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
