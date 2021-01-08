---
title: Projektowanie interfejsu wykonania hal produkcyjnych
description: W tym temacie opisano sposób projektowania zawartości interfejsu użytkownika dla każdej konfiguracji.
author: johanhoffmann
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 81c5c83128bb81523dee6ede549eece7b0d80e30
ms.sourcegitcommit: d9d1ddce6a334ade8b32b5ea3ac4c1e1a8f72715
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2020
ms.locfileid: "4664279"
---
# <a name="design-the-production-floor-execution-interface"></a><span data-ttu-id="453b9-103">Projektowanie interfejsu wykonania hal produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="453b9-103">Design the production floor execution interface</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="453b9-104">Zawartość interfejsu użytkownika można zaprojektować dla każdej konfiguracji używanej przez interfejs wykonywania hali produkcyjnej.</span><span class="sxs-lookup"><span data-stu-id="453b9-104">You can design the content of the user interface for each configuration used by the production floor execution interface.</span></span> <span data-ttu-id="453b9-105">Na przykład pracownicy w jednej komórce roboczej mogą potrzebować możliwości otwierania instrukcji pracy na hali produkcyjnej, podczas gdy w innej komórce instrukcje nie są potrzebne.</span><span class="sxs-lookup"><span data-stu-id="453b9-105">For example, workers in one work cell might need to be able to open job instructions on the production floor, while in another work cell, instructions are not needed.</span></span> <span data-ttu-id="453b9-106">W takim przypadku należy utworzyć dwie konfiguracje, jedną z przyciskiem do otwierania załączników do dokumentów, a drugą bez tego przycisku.</span><span class="sxs-lookup"><span data-stu-id="453b9-106">In that case, two configurations should be created, one with a button for opening document attachments and one without this button.</span></span>

## <a name="design-a-tab"></a><span data-ttu-id="453b9-107">Projektowanie karty</span><span class="sxs-lookup"><span data-stu-id="453b9-107">Design a tab</span></span>

<span data-ttu-id="453b9-108">Na stronie **Konfigurowanie interfejsu wykonania hal produkcyjnych** można tworzyć i konfigurować karty, wybierając **Projektuj karty** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="453b9-108">On the **Configure production floor execution** page, you can create and configure tabs by selecting **Design tabs** on the Action Pane.</span></span>

<span data-ttu-id="453b9-109">Każda karta jest podzielona na cztery sekcje, jak to pokazano na poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="453b9-109">Each tab is divided into four sections, as shown in the following illustration.</span></span>

<span data-ttu-id="453b9-110">![Układ karty](media/pfe-tab-layout.png "Układ karty")</span><span class="sxs-lookup"><span data-stu-id="453b9-110">![Tab layout](media/pfe-tab-layout.png "Tab layout")</span></span>

<span data-ttu-id="453b9-111">Na ilustracji pokazano następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="453b9-111">The following elements are shown in the illustration:</span></span>

1. <span data-ttu-id="453b9-112">Podstawowy pasek narzędzi</span><span class="sxs-lookup"><span data-stu-id="453b9-112">Primary toolbar</span></span>
1. <span data-ttu-id="453b9-113">Dodatkowy pasek narzędzi</span><span class="sxs-lookup"><span data-stu-id="453b9-113">Secondary toolbar</span></span>
1. <span data-ttu-id="453b9-114">Widok główny</span><span class="sxs-lookup"><span data-stu-id="453b9-114">Main view</span></span>
1. <span data-ttu-id="453b9-115">Widok szczegółowy</span><span class="sxs-lookup"><span data-stu-id="453b9-115">Detailed view</span></span>

<span data-ttu-id="453b9-116">Aby utworzyć i skonfigurować nową kartę, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="453b9-116">To create and configure a new tab, follow these steps:</span></span>

1. <span data-ttu-id="453b9-117">Wybierz kolejno opcje **Kontrola produkcji &gt; Konfiguracja &gt; Wykonywanie produkcji**.</span><span class="sxs-lookup"><span data-stu-id="453b9-117">Go to **Production control &gt; Setup &gt; Manufacturing execution**.</span></span>

1. <span data-ttu-id="453b9-118">Wybierz opcję **Projektuj karty** w okienku akcji, aby otworzyć stronę **Projektuj karty**.</span><span class="sxs-lookup"><span data-stu-id="453b9-118">Select **Design tabs** on the Action Pane to open the **Design tabs** page.</span></span>

    <span data-ttu-id="453b9-119">![Strona Projektuj karty](media/pfe-design-tabs.png "Strona Projektuj karty")</span><span class="sxs-lookup"><span data-stu-id="453b9-119">![The Design tabs page](media/pfe-design-tabs.png "The Design tabs page")</span></span>

1. <span data-ttu-id="453b9-120">Wybierz pozycję **Nowy** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="453b9-120">Select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="453b9-121">W nagłówku strony wprowadź następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="453b9-121">Make the following settings in the header of the page:</span></span>

    - <span data-ttu-id="453b9-122">**Nazwa karty** — umożliwia określenie nazwy karty.</span><span class="sxs-lookup"><span data-stu-id="453b9-122">**Tab name** - Specify a name for the tab.</span></span>
    - <span data-ttu-id="453b9-123">**Widok główny** — umożliwia wybór spośród dwóch wstępnie zdefiniowanych list zadań (*Aktywnych zadań* lub *Wszystkich zadań*).</span><span class="sxs-lookup"><span data-stu-id="453b9-123">**Main view** - Select between the two pre-defined job lists (*Active jobs* or *All jobs*).</span></span>
    - <span data-ttu-id="453b9-124">**Widok szczegółów** — umożliwia wybór pustej wartości lub **Szczegółów zadania**.</span><span class="sxs-lookup"><span data-stu-id="453b9-124">**Details view** - Select between a blank value or **Job details**.</span></span> <span data-ttu-id="453b9-125">Jeśli wybierzesz pustą wartość, na karcie nie będzie widoku szczegółowego. Jeśli wybierzesz **Szczegóły zadania**, widok szczegółowy będzie zawierał szczegółowy opis oferty pracy wybranej na liście ofert pracy w widoku głównym.</span><span class="sxs-lookup"><span data-stu-id="453b9-125">If you select the blank value, there will be no detailed view in the tab. If you select **Job details**, the detailed view will contain a detailed description of the job selected in the job list in the main view.</span></span>

1. <span data-ttu-id="453b9-126">W sekcji **Główny pasek narzędzi** wybierz przyciski, które mają być dostępne na głównym pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="453b9-126">In the **Primary toolbar** section, choose which buttons should be available in the primary toolbar.</span></span> <span data-ttu-id="453b9-127">W kolumnie **Dostępne akcje** jest wyświetlana lista wszystkich przycisków, które można dodać.</span><span class="sxs-lookup"><span data-stu-id="453b9-127">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="453b9-128">Kolumna **Wybrane akcje** zawiera listę wszystkich przycisków zawartych w bieżącej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="453b9-128">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="453b9-129">Użyj przycisków między kolumnami, aby w razie potrzeby przenieść wybrane elementy między kolumnami.</span><span class="sxs-lookup"><span data-stu-id="453b9-129">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="453b9-130">Użyj przycisków w górę iw dół obok kolumny **Wybrane akcje**, aby kontrolować kolejność, w jakiej przyciski są prezentowane w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="453b9-130">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

1. <span data-ttu-id="453b9-131">W sekcji **pomocniczy** **pasek narzędzi** wybierz przyciski, które mają być dostępne na pomocniczym pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="453b9-131">In the **Secondary** **toolbar** section, choose which buttons should be available in the secondary toolbar.</span></span> <span data-ttu-id="453b9-132">W kolumnie **Dostępne akcje** jest wyświetlana lista wszystkich przycisków, które można dodać.</span><span class="sxs-lookup"><span data-stu-id="453b9-132">The **Available actions** column shows a list of all the buttons that can be added.</span></span> <span data-ttu-id="453b9-133">Kolumna **Wybrane akcje** zawiera listę wszystkich przycisków zawartych w bieżącej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="453b9-133">The **Selected actions** columns shows a list of all the buttons that are included in the current configuration.</span></span> <span data-ttu-id="453b9-134">Użyj przycisków między kolumnami, aby w razie potrzeby przenieść wybrane elementy między kolumnami.</span><span class="sxs-lookup"><span data-stu-id="453b9-134">Use the buttons between the columns to move selected items between the columns as needed.</span></span> <span data-ttu-id="453b9-135">Użyj przycisków w górę iw dół obok kolumny **Wybrane akcje**, aby kontrolować kolejność, w jakiej przyciski są prezentowane w interfejsie użytkownika.</span><span class="sxs-lookup"><span data-stu-id="453b9-135">Use the up and down buttons next to the **Selected actions** column to control the order in which the buttons are presented in the user interface.</span></span>

## <a name="associate-a-tab-with-a-configuration"></a><span data-ttu-id="453b9-136">Umożliwia skojarzenie karty z konfiguracją</span><span class="sxs-lookup"><span data-stu-id="453b9-136">Associate a tab with a configuration</span></span>

<span data-ttu-id="453b9-137">Po zaprojektowaniu wszystkich potrzebnych kart można je skojarzyć z konfiguracją.</span><span class="sxs-lookup"><span data-stu-id="453b9-137">After you designed all the tabs you need, you can associate them with a configuration.</span></span>

1. <span data-ttu-id="453b9-138">Wybierz kolejno opcje **Kontrola produkcji &gt; Konfiguracja &gt; Konfigurowanie interfejsu wykonania hal produkcyjnych**.</span><span class="sxs-lookup"><span data-stu-id="453b9-138">Go to **Production control &gt; Setup &gt; Configure production floor execution**.</span></span>

    <span data-ttu-id="453b9-139">![Konfigurowanie wykonania produkcji](media/pfe-config-prod-floor-execution.png "Konfigurowanie wykonania produkcji")</span><span class="sxs-lookup"><span data-stu-id="453b9-139">![Configure production floor execution](media/pfe-config-prod-floor-execution.png "Configure production floor execution")</span></span>

1. <span data-ttu-id="453b9-140">Na karcie skróconej **Wybór karty** wybierz pozycję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="453b9-140">On the **Tab selection** FastTab, select **Add**.</span></span>

1. <span data-ttu-id="453b9-141">Nowy wiersz zostanie dodany do siatki.</span><span class="sxs-lookup"><span data-stu-id="453b9-141">A new row is added to the grid.</span></span> <span data-ttu-id="453b9-142">W przypadku nowego wiersza należy wybrać nazwę karty, która ma zostać dodana do konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="453b9-142">For this new row, select the name of a tab that you want to add to the configuration.</span></span>

1. <span data-ttu-id="453b9-143">W razie potrzeby dodaj kolejne karty.</span><span class="sxs-lookup"><span data-stu-id="453b9-143">Continue to add additional tabs as needed.</span></span>

1. <span data-ttu-id="453b9-144">Przyciski **Przenieś w górę** i **Przenieś w dół** na pasku narzędzi służą do rozmieszczania kart według potrzeb.</span><span class="sxs-lookup"><span data-stu-id="453b9-144">Use the **Move up** and **Move down** buttons on the toolbar to arrange the tabs as needed.</span></span> <span data-ttu-id="453b9-145">Zakładki będą wyświetlane od lewej do prawej w kolejności pokazanej na powyższym zrzucie ekranu (zakładka u góry jest pokazana po lewej stronie).</span><span class="sxs-lookup"><span data-stu-id="453b9-145">The tabs will be displayed from left to right in the order shown in the above screenshot (the tab at the top is shown on the left).</span></span>
