---
title: Podgląd i publikowanie eksperymentu
description: W tym temacie opisano sposób podglądu i publikowania eksperymentu z Dynamics 365 Commerce.
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
ms.openlocfilehash: 91e2e4840a2d53f195d881279050b6415d48b070
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930269"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="90040-103">Podgląd i publikowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="90040-103">Preview and publish an experiment</span></span>

<span data-ttu-id="90040-104">W tym temacie opisano sposób wyświetlania podglądu i publikowania eksperymentu w Dynamics 365 Commerce po [połączeniu eksperymentu i edytowaniu odmian](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="90040-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="90040-105">Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="90040-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="90040-106">Dodatkowe kroki są zawarte w odrębnych tematach.</span><span class="sxs-lookup"><span data-stu-id="90040-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="90040-107">[ ![Proces użytkownika eksperymentu — podgląd i publikowanie](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="90040-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="90040-108">Podgląd odmian eksperymentu</span><span class="sxs-lookup"><span data-stu-id="90040-108">Preview your experiment variations</span></span>
<span data-ttu-id="90040-109">Możesz wyświetlić podgląd odmiany i kontynuować ich edycję, dopóki nie będą wyglądać odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="90040-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

1. <span data-ttu-id="90040-110">W konstruktorze witryn należy użyć menu rozwijanego odmiany pod paskiem poleceń, aby wybrać zawartość, której podgląd chcesz wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="90040-110">In site builder, use the variations drop-down menu below the command bar to select the content you want to preview.</span></span> 
1. <span data-ttu-id="90040-111">Wybierz opcję **Podgląd** na górnym pasku.</span><span class="sxs-lookup"><span data-stu-id="90040-111">Select **Preview** in the top bar.</span></span> <span data-ttu-id="90040-112">Zostanie wyświetlony podgląd zawartości, taki jak po opublikowaniu.</span><span class="sxs-lookup"><span data-stu-id="90040-112">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="90040-113">Aby wyświetlić podgląd innej odmiany, wybierz ją z listy rozwijanej odmian i wybierz ponownie **Podgląd**.</span><span class="sxs-lookup"><span data-stu-id="90040-113">To preview a different variation, select it from the variation drop-down and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="90040-114">Publikowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="90040-114">Publish your experiment</span></span>
<span data-ttu-id="90040-115">Jeśli nie używasz grupy publikowania do planowania, kiedy eksperymenty są aktywne i chcesz publikować natychmiast, wybierz opcję **Publikuj** na pasku poleceń.</span><span class="sxs-lookup"><span data-stu-id="90040-115">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="90040-116">Wszystkie odmiany należące do eksperymentu zostaną opublikowane.</span><span class="sxs-lookup"><span data-stu-id="90040-116">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="90040-117">Jeśli strona zawiera nieopublikowany adres URL, należy najpierw opublikować adres URL inaczej nie będzie widoczny dla użytkowników witryny internetowej.</span><span class="sxs-lookup"><span data-stu-id="90040-117">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="90040-118">Szczegółowe informacje zawiera temat [Zapisywanie, pogląd i publikowanie strony](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="90040-118">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="90040-119">Za pomocą grup publikacji można planować czas uruchomienia eksperymentu</span><span class="sxs-lookup"><span data-stu-id="90040-119">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="90040-120">Odmiany utworzone w konstruktorze witryn mogą być planowane do opublikowania za pomocą grupy publikacji.</span><span class="sxs-lookup"><span data-stu-id="90040-120">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="90040-121">W grupie publikacji można połączyć stronę lub fragment z eksperymentem, przechodząc na kartę**Eksperymenty**, **Strony** lub **Fragmenty**. Aby uzyskać więcej informacji, zobacz temat [Łączenie eksperymentu i edycja odmian](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="90040-121">Within a publish group, you can connect a page or fragment to your experiment by going to the **Experiments** tab or the **Pages** or **Fragments** tab. For more information, see [Connect an experiment and edit variations](experimentation-connect-edit.md) topic.</span></span> <span data-ttu-id="90040-122">Aby uzyskać informacje o grupach publikacji, zobacz temat [Praca z grupami publikacji](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="90040-122">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="90040-123">W przypadku korzystania z grup publikacji z eksperymentami należy pamiętać o pewnych ważnych kwestiach.</span><span class="sxs-lookup"><span data-stu-id="90040-123">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="90040-124">Po dodaniu do grupy publikacji strony lub fragmentu z uruchomionym eksperymentem zostanie on usunięty ze strony lub fragmentu w grupie publikacji.</span><span class="sxs-lookup"><span data-stu-id="90040-124">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="90040-125">Eksperymenty, które są połączone ze stronami w działającej witrynie, nie są dostępne dla stron w grupach publikacji i na odwrót.</span><span class="sxs-lookup"><span data-stu-id="90040-125">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="90040-126">Podobnie strony, które mają uruchomione eksperymenty w działającej witrynie, nie są dostępne dla innych eksperymentów w grupach publikacji i na odwrót.</span><span class="sxs-lookup"><span data-stu-id="90040-126">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="90040-127">Podczas publikowania lub planowania grupy publikacji cała zawartość w grupie publikacji jest publikowana niezależnie od tego, czy istnieje doświadczenie związane z grupą publikacji.</span><span class="sxs-lookup"><span data-stu-id="90040-127">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="90040-128">Ponieważ grupa publikacji nadal utrzymuje się po opublikowaniu jej w działającej witrynie, eksperymenty z grupy publikacji również będą się utrzymywać.</span><span class="sxs-lookup"><span data-stu-id="90040-128">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="90040-129">Dlatego nie będzie można kojarzyć innych eksperymentów z tą samą stroną lub fragmentem.</span><span class="sxs-lookup"><span data-stu-id="90040-129">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="90040-130">Aby uniknąć tego ograniczenia, usuń wszystkie grupy publikacji z trwałymi eksperymentami.</span><span class="sxs-lookup"><span data-stu-id="90040-130">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="90040-131">Podobnie, jeśli chcesz usunąć eksperyment w działającej witrynie, które istnieje również w grupie publikowania, najpierw usuń go z grupy publikacji.</span><span class="sxs-lookup"><span data-stu-id="90040-131">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="90040-132">Poprzedni krok</span><span class="sxs-lookup"><span data-stu-id="90040-132">Previous step</span></span>
[<span data-ttu-id="90040-133">Łączenie i edytowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="90040-133">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="90040-134">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="90040-134">Next step</span></span>
[<span data-ttu-id="90040-135">Uruchamianie i monitorowanie eksperymentu</span><span class="sxs-lookup"><span data-stu-id="90040-135">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
