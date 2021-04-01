---
title: Pulpit kompilowania ładunku
description: W tym temacie opisano, jak pracować z pulpitem kompilowania ładunku.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSLoadBuildWorkbench,TMSLoadBuildTemplateCreate,TMSLoadBuildStrategy,TMSLoadBuildTemplateApply
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 480006a6d091acdf5c88fdbf0d9e625088d660d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247245"
---
# <a name="load-building-workbench"></a><span data-ttu-id="f89c9-103">Pulpit kompilowania ładunku</span><span class="sxs-lookup"><span data-stu-id="f89c9-103">Load building workbench</span></span>

<span data-ttu-id="f89c9-104">Pulpit kompilowania ładunku umożliwia stosowanie strategii kompilowania ładunku podczas tworzenia ładunków.</span><span class="sxs-lookup"><span data-stu-id="f89c9-104">The load building workbench lets you apply load building strategies when you create loads.</span></span>

## <a name="create-a-load-building-strategy"></a><span data-ttu-id="f89c9-105">Tworzenie strategii kompilowania ładunku</span><span class="sxs-lookup"><span data-stu-id="f89c9-105">Create a load building strategy</span></span>

<span data-ttu-id="f89c9-106">Strategie kompilowania ładunku są używane do automatycznego kompilowania ładunków.</span><span class="sxs-lookup"><span data-stu-id="f89c9-106">You use load building strategies to automatically build loads.</span></span> <span data-ttu-id="f89c9-107">Ta funkcja przydaje się w następujących sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="f89c9-107">This capability can be beneficial in the following situations:</span></span>

- <span data-ttu-id="f89c9-108">Jeśli regularnie wysyłasz określony zestaw produktów, strategie te pozwalają zaoszczędzić czas, ponieważ nie musisz za każdym razem od nowa kompilować tego samego ładunku.</span><span class="sxs-lookup"><span data-stu-id="f89c9-108">If you regularly ship a specific set of products, load strategies help save time, because you don't have to build the same load every time.</span></span>
- <span data-ttu-id="f89c9-109">Jeśli zależy Ci na maksymalizacji wydajności i chcesz uniknąć połowicznych ładunków, strategie te pomogą Ci wypełnić każdy ładunek w jak największym zakresie.</span><span class="sxs-lookup"><span data-stu-id="f89c9-109">If you want to avoid half-full loads to maximize efficiency, load strategies can help fill each load as much as possible.</span></span>

<span data-ttu-id="f89c9-110">Klasa strategii kompilowania ładunku o nazwie `TMSLoadBuildingVolumeStrategy` zawiera strategię kompilowania ładunku o nazwie *Strategia kompilowania ładunku na podstawie objętości*.</span><span class="sxs-lookup"><span data-stu-id="f89c9-110">A load building strategy class that is named `TMSLoadBuildingVolumeStrategy` provides a load building strategy that is named *Volume-based load building strategy*.</span></span> <span data-ttu-id="f89c9-111">Pozwala ona stosować maksymalne wartości wysokości i wagi określone w szablonie ładunku albo zastępować te ustawienia wprowadzaniem nowych wartości.</span><span class="sxs-lookup"><span data-stu-id="f89c9-111">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="f89c9-112">Ta strategia jest jedyną strategią, która jest dostarczana jako gotowa.</span><span class="sxs-lookup"><span data-stu-id="f89c9-112">This strategy is the only strategy that is included out of the box.</span></span> <span data-ttu-id="f89c9-113">(Możesz jednak również korzystać z kilku strategii niestandardowych).</span><span class="sxs-lookup"><span data-stu-id="f89c9-113">(However, you might have some custom strategies.)</span></span>

<span data-ttu-id="f89c9-114">Aby korzystać z gotowej *Strategii kompilowania ładunku na podstawie objętości*, należy zaznaczyć ją w polu **Strategia kompilowania ładunku** na stronie **Pulpitu kompilowania ładunku** (**Zarządzanie transportem &gt; Planowanie &gt; Pulpit kompilowania ładunku**).</span><span class="sxs-lookup"><span data-stu-id="f89c9-114">To use the out-of-box *Volume-based load building strategy* strategy, select it in the **Load building strategy** field on the **Load building workbench** page (**Transportation management &gt; Planning &gt; Load building workbench**).</span></span>

<span data-ttu-id="f89c9-115">Aby utworzyć strategię kompilowania ładunku, wykonaj poniższe czynności.</span><span class="sxs-lookup"><span data-stu-id="f89c9-115">To create a load building strategy, follow these steps.</span></span>

1. <span data-ttu-id="f89c9-116">Wybierz kolejno **Zarządzanie transportem &gt; Ustawienia &gt; Kompilowanie ładunku &gt; Strategie kompilowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-116">Go to **Transportation management &gt; Setup &gt; Load building &gt; Load building strategies**.</span></span>
1. <span data-ttu-id="f89c9-117">W okienku akcji wybierz opcję **Generuj listę klas**, aby upewnić się, że masz najnowsze wersje wszystkich dostępnych klas.</span><span class="sxs-lookup"><span data-stu-id="f89c9-117">On the Action Pane, select **Generate class list** to make sure that you have the latest versions of all available classes.</span></span>
1. <span data-ttu-id="f89c9-118">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-118">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="f89c9-119">Wprowadź unikatową nazwę strategii, wybierz dla niej klasę strategii kompilowania ładunku i wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="f89c9-119">Enter a unique name for the strategy, select the load building strategy class for it, and enter a description.</span></span>
1. <span data-ttu-id="f89c9-120">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-120">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f89c9-121">W okienku akcji wybierz pozycję **Parametry**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-121">On the Action Pane, select **Parameters**.</span></span>
1. <span data-ttu-id="f89c9-122">Na stronie **Parametry strategii tworzenia ładunku** wybierz z listy pozycję **Maksymalna objętość**, a następnie w polu **Wartość** wprowadź wartość procentową łącznej objętości ładunku, która powinna zostać zastosowana do nowej strategii kompilowania ładunku.</span><span class="sxs-lookup"><span data-stu-id="f89c9-122">On the **Load building strategy parameters** page, select **Volume capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total volume capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="f89c9-123">Wybierz z listy pozycję **Maksymalna masa**, a następnie w polu **Wartość** wprowadź wartość procentową łącznej masy ładunku, która powinna zostać zastosowana do nowej strategii kompilowania ładunku.</span><span class="sxs-lookup"><span data-stu-id="f89c9-123">Select **Weight capacity** in the list, and then, in the **Value** field, enter the percentage of the load's total weight capacity that should be applied for the new load building strategy.</span></span>
1. <span data-ttu-id="f89c9-124">Zamknij stronę **Parametry strategii tworzenia ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-124">Close the **Load building strategy parameters** page.</span></span>
1. <span data-ttu-id="f89c9-125">Zamknij stronę **Strategie kompilowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-125">Close the **Load building strategies** page.</span></span>

<span data-ttu-id="f89c9-126">Możesz teraz przypisać strategię kompilowania ładunku do szablonu kompilowania ładunku albo</span><span class="sxs-lookup"><span data-stu-id="f89c9-126">You can now assign the load building strategy to a load building template.</span></span> <span data-ttu-id="f89c9-127">skorzystać z niej bezpośrednio na poziomie pulpitu planowania wysyłki ładunku.</span><span class="sxs-lookup"><span data-stu-id="f89c9-127">Alternatively, you can use it directly in the load planning workbench.</span></span>

## <a name="use-a-load-building-strategy-in-the-load-building-workbench"></a><span data-ttu-id="f89c9-128">Korzystanie ze strategii kompilowania ładunku na poziomie pulpitu kompilowania ładunku</span><span class="sxs-lookup"><span data-stu-id="f89c9-128">Use a load building strategy in the load building workbench</span></span>

1. <span data-ttu-id="f89c9-129">Wybierz kolejno opcje **Zarządzanie transportem &gt; Planowanie &gt; Pulpit kompilowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-129">Go to **Transportation management &gt; Planning &gt; Load building workbench**.</span></span>
1. <span data-ttu-id="f89c9-130">Wykonaj jeden z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="f89c9-130">Follow one of these steps:</span></span>

    - <span data-ttu-id="f89c9-131">Wybierz strategię w polu **Strategia kompilowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-131">Select a strategy in the **Load building strategy** field.</span></span>
    - <span data-ttu-id="f89c9-132">Jeśli masz zdefiniowany szablon kompilowania ładunku i przypisano do niego strategię kompilowania ładunku, w okienku akcji na karcie **Zarządzaj szablonami** wybierz opcję **Zastosuj szablon**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-132">If you've defined a load building template and assigned the load building strategy to it, on the Action Pane, on the **Manage templates** tab, select **Apply template**.</span></span> <span data-ttu-id="f89c9-133">Następnie w rozwijanym oknie dialogowym **Zastosuj szablon kompilowania ładunku** wybierz szablon w polu **Nazwa szablonu kompilowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-133">Then, in the **Apply load building template** drop-down dialog box, select a template in the **Load building template name** field.</span></span>

1. <span data-ttu-id="f89c9-134">Na skróconej karcie **Ładuj sekwencję szablonów** wybierz co najmniej jeden [szablon ładunku](load-template.md).</span><span class="sxs-lookup"><span data-stu-id="f89c9-134">On the **Load templates sequence** FastTab, select one or more [load templates](load-template.md).</span></span> <span data-ttu-id="f89c9-135">Pulpit spróbuje dopasować ładunek do kontenerów wybranych typów w kolejności określonej w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="f89c9-135">The workbench will try to fit the load into these types of containers, in the sequence that is specified here.</span></span> <span data-ttu-id="f89c9-136">Zazwyczaj należy umieścić najmniejsze kontenery u góry listy, aby najmniejszy dostępny kontener został wybrany jako pierwszy.</span><span class="sxs-lookup"><span data-stu-id="f89c9-136">Typically, you should put the smallest containers at the top of the list to ensure that the smallest possible container is selected first.</span></span>
1. <span data-ttu-id="f89c9-137">W okienku akcji wybierz pozycję **Proponuj ładunki**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-137">On the Action Pane, select **Propose loads**.</span></span>
1. <span data-ttu-id="f89c9-138">Przejrzyj proponowane ładunki i proponowane wiersze ładunku.</span><span class="sxs-lookup"><span data-stu-id="f89c9-138">Review the proposed loads and proposed load lines.</span></span>
1. <span data-ttu-id="f89c9-139">W okienku akcji wybierz opcję **Utwórz ładunki**, aby utworzyć ładunki oparte na wierszach dokumentu źródłowego na skróconej karcie **Wiersze proponowanego ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-139">On the Action Pane, select **Create loads** to create loads that are based on the source document lines on the **Proposed load lines** FastTab.</span></span>
1. <span data-ttu-id="f89c9-140">Zamknij stronę **Pulpit kompilowania ładunku**.</span><span class="sxs-lookup"><span data-stu-id="f89c9-140">Close the **Load building workbench** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]