---
title: Wyszukiwanie akcji
description: W tym artykule opisano działanie funkcji wyszukiwania w Microsoft Dynamics 365 for Finance and Operations. Funkcja pomaga znajdować i wykonywać czynności na stronie.
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 960c715c487fbda5d93630327f07380e6d8fbd3c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547038"
---
# <a name="action-search"></a><span data-ttu-id="583dc-104">Wyszukiwanie akcji</span><span class="sxs-lookup"><span data-stu-id="583dc-104">Action search</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="583dc-105">W tym artykule opisano działanie funkcji wyszukiwania w Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="583dc-105">This article describes the action search functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="583dc-106">Funkcja pomaga znajdować i wykonywać czynności na stronie.</span><span class="sxs-lookup"><span data-stu-id="583dc-106">Action search will help you find and run actions on a page.</span></span>

## <a name="introduction"></a><span data-ttu-id="583dc-107">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="583dc-107">Introduction</span></span>

<span data-ttu-id="583dc-108">Strony w produkcie głównie Microsoft Dynamics 365 for Finance and Operations wyświetlają polecenia w okienkach akcji, zarówno w samodzielnym okienku akcji, które wyświetla się u góry strony, jak i na paskach narzędzi, które pojawiają się w różnych częściach strony.</span><span class="sxs-lookup"><span data-stu-id="583dc-108">Pages in Microsoft Dynamics 365 for Finance and Operations primarily expose commands on Action Panes, both the standard Action Pane that appears at the top of a page and the toolbars that appear in various sections of the page.</span></span> <span data-ttu-id="583dc-109">W poprzednich wersjach funkcja klawiszy skrótu dawała szybki dostęp do dowolnego przycisku w okienku akcji po naciśnięciu klawisza Alt w kombinacji z właściwą literą.</span><span class="sxs-lookup"><span data-stu-id="583dc-109">In previous versions, a Key Tips feature let you quickly access any button on an Action Pane by pressing the Alt key and then a series of letters.</span></span>

<span data-ttu-id="583dc-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span><span class="sxs-lookup"><span data-stu-id="583dc-110">[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png)</span></span>

<span data-ttu-id="583dc-111">W aktualnej wersji programu Finance and Operations klawisze skrótu nie są już dostępne i zostały zastąpione przez funkcję wyszukiwania akcji.</span><span class="sxs-lookup"><span data-stu-id="583dc-111">However, in the current version of Finance and Operations, Key Tips are no longer available but have been replaced by the action search feature.</span></span> <span data-ttu-id="583dc-112">Ta nowa funkcja umożliwia szybkie wyszukiwanie i korzystanie z przycisków w dowolnym widocznym okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="583dc-112">This new feature lets you quickly search for and run a button from any visible Action Pane.</span></span>

## <a name="using-action-search"></a><span data-ttu-id="583dc-113">Korzystanie z funkcji wyszukiwania akcji</span><span class="sxs-lookup"><span data-stu-id="583dc-113">Using action search</span></span>

<span data-ttu-id="583dc-114">Aby skorzystać z funkcji wyszukiwania akcji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="583dc-114">To use the action search feature, follow these steps.</span></span>

1. <span data-ttu-id="583dc-115">W okienku akcji kliknij pole **wyszukiwanie akcji**.</span><span class="sxs-lookup"><span data-stu-id="583dc-115">On the Action Pane, click in the **action search** field.</span></span> <span data-ttu-id="583dc-116">(Pole **wyszukiwanie akcji** zawiera ikonę lupy).</span><span class="sxs-lookup"><span data-stu-id="583dc-116">(The **action search** field contains a magnifying glass icon.)</span></span>
2. <span data-ttu-id="583dc-117">Wpisz całość lub część nazwy przycisku, którego chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="583dc-117">Type all or part of the name of the button that you want to run.</span></span> <span data-ttu-id="583dc-118">Można także wyszukiwać za pomocą słów znajdujących się w „ścieżce” przycisku.</span><span class="sxs-lookup"><span data-stu-id="583dc-118">You can also search by using words from the button's "path."</span></span> <span data-ttu-id="583dc-119">(Więcej informacji można znaleźć w następnej sekcji tego artykułu). Na ogół przycisk będzie widoczny w górnej części listy wyników po wpisaniu dwóch do czterech znaków.</span><span class="sxs-lookup"><span data-stu-id="583dc-119">(For more information, see the next section of this article.) Typically, a button will appear near the top of the results list after you've typed two to four characters.</span></span>
3. <span data-ttu-id="583dc-120">Znajdź i uruchom przycisk na liście wyników (za pomocą myszy lub klawiatury).</span><span class="sxs-lookup"><span data-stu-id="583dc-120">Find and run the button in the results list (by using your mouse or keyboard).</span></span>

<span data-ttu-id="583dc-121">Po uruchomieniu przycisku wyróżnienie na ekranie wraca do poprzedniego miejsca na stronie, umożliwiając kontynuowanie pracy.</span><span class="sxs-lookup"><span data-stu-id="583dc-121">After the button is run, the focus is returned to your last position on the page, so that you can continue to work.</span></span>

<span data-ttu-id="583dc-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span><span class="sxs-lookup"><span data-stu-id="583dc-122">[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)</span></span>

<span data-ttu-id="583dc-123">Wyszukiwanie akcji można też uruchomić za pomocą kombinacji klawiszy Ctrl+/ lub Alt+Q.</span><span class="sxs-lookup"><span data-stu-id="583dc-123">You can also start action search by pressing Ctrl+/ or Alt+Q.</span></span> <span data-ttu-id="583dc-124">Naciśnij skrót klawiaturowy ponownie, aby wyróżnienie wróciło do ostatniej pozycji na stronie.</span><span class="sxs-lookup"><span data-stu-id="583dc-124">Press the keyboard shortcut again to return the focus to your last position on the page.</span></span>

## <a name="understanding-the-results-list"></a><span data-ttu-id="583dc-125">Opis listy wyników</span><span class="sxs-lookup"><span data-stu-id="583dc-125">Understanding the results list</span></span>

<span data-ttu-id="583dc-126">Często w programie Finance and Operations trzeba znać zarówno lokalizację, jak kontekst przycisku, aby w pełni rozumieć, do czego służy.</span><span class="sxs-lookup"><span data-stu-id="583dc-126">Often, in Finance and Operations, you must know both the location and the context of a button to fully understand the purpose of that button.</span></span> <span data-ttu-id="583dc-127">Dlatego dla każdego elementu na liście wyników wyświetlane są dodatkowe informacje, które pomagają zorientować się, które przyciski są widoczne na liście.</span><span class="sxs-lookup"><span data-stu-id="583dc-127">Therefore, additional information is shown for each item in the results list, to help you understand exactly which buttons appear in the list.</span></span> <span data-ttu-id="583dc-128">W szczególności wyświetlana jest „ścieżka” przycisku.</span><span class="sxs-lookup"><span data-stu-id="583dc-128">In particular, the "path" of the button is shown.</span></span> <span data-ttu-id="583dc-129">Ścieżka może wyróżniać etykiety następujących elementów interfejsu użytkownika:</span><span class="sxs-lookup"><span data-stu-id="583dc-129">This path might include the labels of the following UI elements, as relevant:</span></span>

- <span data-ttu-id="583dc-130">Karta Okienko akcji</span><span class="sxs-lookup"><span data-stu-id="583dc-130">Action Pane tab</span></span>
- <span data-ttu-id="583dc-131">Grupa przycisków</span><span class="sxs-lookup"><span data-stu-id="583dc-131">Button group</span></span>
- <span data-ttu-id="583dc-132">Przycisk menu (jeśli przycisk jest wewnątrz przycisku menu)</span><span class="sxs-lookup"><span data-stu-id="583dc-132">Menu button (if the button is inside a menu button)</span></span>
- <span data-ttu-id="583dc-133">Separator menu (jeśli przycisk jest w nazwanej grupie wewnątrz przycisku menu)</span><span class="sxs-lookup"><span data-stu-id="583dc-133">Menu separator (if the button is inside a named group inside a menu button)</span></span>
- <span data-ttu-id="583dc-134">Grupa lub karta na stronie (na przykład nazwa skróconej karty)</span><span class="sxs-lookup"><span data-stu-id="583dc-134">Group or tab on the page (for example, the name of a FastTab)</span></span>

<span data-ttu-id="583dc-135">Na przykład w polu **wyszukiwania akcji** wpisujesz **tot** i sprawdzasz listę wyników.</span><span class="sxs-lookup"><span data-stu-id="583dc-135">For example, you typed **tot** in the **action search** field and are now examining the results list.</span></span> <span data-ttu-id="583dc-136">Wyróżniony jest pierwszy wpis, dla przycisku o nazwie **Sumy** (ang. Totals).</span><span class="sxs-lookup"><span data-stu-id="583dc-136">The first entry, for a button that is named **Totals**, is highlighted.</span></span> <span data-ttu-id="583dc-137">Widoczna jest również ścieżka przycisku **Zamówienie sprzedaży** &gt; **Widok**.</span><span class="sxs-lookup"><span data-stu-id="583dc-137">A button path of **Sales order** &gt; **View** is also shown.</span></span> <span data-ttu-id="583dc-138">Część **Zamówienie sprzedaży** w ścieżce odpowiada karcie **Zamówienie sprzedaży** w okienku akcji, a część **Widok** ścieżki odpowiada grupie **Widok** na tej karcie. Podobnie ścieżka przycisku **Rabat końcowy**(**Sprzedaj** &gt; **Oblicz**) informuje, że ten przycisk znajduje się w grupie **Oblicz** na karcie **Sprzedaj** okienka akcji.</span><span class="sxs-lookup"><span data-stu-id="583dc-138">The **Sales order** part of the path corresponds to the **Sales order** tab on the Action Pane, and the **View** part of the path corresponds to the **View** group on that tab. Similarly, the path of the **Total discount** button (**Sell** &gt; **Calculate**) informs you that this button is located in the **Calculate** group on the **Sell** tab of the Action Pane.</span></span> <span data-ttu-id="583dc-139">Te dane pomagają zrozumieć funkcje przycisków, które będą wywoływane przez wyszukiwanie akcji (jeśli dany zostanie wybrany na liście wyników).</span><span class="sxs-lookup"><span data-stu-id="583dc-139">Therefore, this information helps you understand exactly which button will be triggered by action search (if you select that button in the results list).</span></span>

<span data-ttu-id="583dc-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span><span class="sxs-lookup"><span data-stu-id="583dc-140">[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png)</span></span>

<span data-ttu-id="583dc-141">W poprzednim przykładzie wyszukiwanie akcji dało wyniki ze standardowego okienka akcji u góry strony.</span><span class="sxs-lookup"><span data-stu-id="583dc-141">In the previous example, action search showed results from the standard Action Pane at the top of a page.</span></span> <span data-ttu-id="583dc-142">Wyszukiwanie akcji zawiera jednak również wyniki z widocznych pasków narzędzi umieszczonych w innych miejscach na stronie.</span><span class="sxs-lookup"><span data-stu-id="583dc-142">However, action search also shows results from visible toolbars that are located in other places on the page.</span></span> <span data-ttu-id="583dc-143">Na przykład wyszukujesz przycisk **Dostępne zapasy**, który znajduje się na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="583dc-143">For example, you're searching for the **On-hand inventory** button that is located on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="583dc-144">W tym przypadku ścieżka do przycisku na liście wyników (**Wiersze zamówienia sprzedaży** &gt; **Zapasy** &gt; **Widok**) informuje, że ten przycisk znajduje się w nagłówku **Widok** w przycisku menu **Zapasy** na skróconej karcie **Wiersze zamówienia sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="583dc-144">In this case, the button path in the results list (**Sales order lines** &gt; **Inventory** &gt; **View**) informs you that this button is located under the **View** heading on the **Inventory** menu button on the **Sales order lines** FastTab.</span></span>

<span data-ttu-id="583dc-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="583dc-145">[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)</span></span>

## <a name="action-search-vs-navigation-search"></a><span data-ttu-id="583dc-146">Wyszukiwanie akcji a wyszukiwanie nawigacji</span><span class="sxs-lookup"><span data-stu-id="583dc-146">Action search vs. Navigation search</span></span>

<span data-ttu-id="583dc-147">Wyszukiwanie akcji służy do znajdowania i wykonywania akcji na stronie, Do znajdowania i elementów i poruszania się na stronach w programie Finance and Operations służy oddzielny mechanizm wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="583dc-147">Whereas action search is intended to find and run actions on a page, there is a separate search mechanism for finding and navigating to pages in Finance and Operations.</span></span> <span data-ttu-id="583dc-148">Aby uzyskać więcej informacji na temat tej funkcji, zobacz artykuł [Nawigacja z wyszukiwaniem](navigation-search.md).</span><span class="sxs-lookup"><span data-stu-id="583dc-148">For more information about that feature, see the [Navigation search](navigation-search.md) article.</span></span>