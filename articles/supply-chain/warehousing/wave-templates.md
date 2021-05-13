---
title: Szablony grupy czynności
description: W tym temacie opisano sposób konfigurowania kryteriów, które określają, czy grupy czynności są przetwarzane ręcznie czy automatycznie, a pracę, która jest generowana dla magazynu podczas przetwarzania grupy czynności.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b02283a6e0a4ef0d61be8b66f82be8c125028cb0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813634"
---
# <a name="wave-templates"></a><span data-ttu-id="e4d16-103">Szablony grupy czynności</span><span class="sxs-lookup"><span data-stu-id="e4d16-103">Wave templates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4d16-104">W tym temacie opisano sposób konfigurowania kryteriów, które określają, czy grupy czynności są przetwarzane ręcznie czy automatycznie, a pracę, która jest generowana dla magazynu podczas przetwarzania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-104">This topic describes how to set up the criteria that determine whether waves are processed manually or automatically, and the work that is generated for a warehouse when a wave is processed.</span></span> <span data-ttu-id="e4d16-105">Kryteria można określić, definiując szablony grupy czynności i kwerendy, które dopasowują grupy czynności do zwolnionych wierszy w zamówieniach sprzedaży, zleceniach produkcyjnych i kartach Kanban.</span><span class="sxs-lookup"><span data-stu-id="e4d16-105">You specify the criteria by setting up wave templates and queries that match a wave with released lines in sales orders, production orders, and kanbans.</span></span>

## <a name="settings-for-wave-templates"></a><span data-ttu-id="e4d16-106">Ustawienia szablonów grupy czynności</span><span class="sxs-lookup"><span data-stu-id="e4d16-106">Settings for wave templates</span></span>

<span data-ttu-id="e4d16-107">Podczas konfigurowania szablonu grupy czynności, można określić następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="e4d16-107">When you set up a wave template, you specify the following:</span></span>

- <span data-ttu-id="e4d16-108">**Oddział** i **magazyn**, dla których szablon utworzy pracę.</span><span class="sxs-lookup"><span data-stu-id="e4d16-108">The **Site** and **Warehouse** that the template will create work for.</span></span>
- <span data-ttu-id="e4d16-109">Kolejność, w jakiej szablony będą oceniane.</span><span class="sxs-lookup"><span data-stu-id="e4d16-109">The order in which the templates will be evaluated.</span></span> <span data-ttu-id="e4d16-110">Kolejność, w jakiej szablony są zestawiane ze zwolnionymi wierszami w zamówieniach sprzedaży, zleceniach produkcyjnych i kartach Kanban.</span><span class="sxs-lookup"><span data-stu-id="e4d16-110">The sequence in which the templates are matched to released lines on sales orders, production orders, and kanbans.</span></span> <span data-ttu-id="e4d16-111">Po zwolnieniu wiersza system stosuje pierwszy szablon grupy czynności, dla których wiersz spełnia kryteria.</span><span class="sxs-lookup"><span data-stu-id="e4d16-111">When a line is released, the system applies the first wave template that the line meets the criteria for.</span></span> <span data-ttu-id="e4d16-112">Im większe jest prawdopodobieństwo spełnienia kryteriów, tym większy prawdopodobieństwo ma wiersz, więc na początku listy należy umieścić szablony z najbardziej określonymi kryteriami.</span><span class="sxs-lookup"><span data-stu-id="e4d16-112">The broader the criteria, the more likely it is for a line to meet the criteria, so you should put the templates with the most specific criteria at the top of the list.</span></span> <span data-ttu-id="e4d16-113">Przyciski **Przenieś w górę** i **Przenieś w dół** w okienku akcji służą do rozmieszczania szablonów na liście.</span><span class="sxs-lookup"><span data-stu-id="e4d16-113">Use the **Move up** and **Move down** buttons on the Action Pane to arrange templates in the list.</span></span>
- <span data-ttu-id="e4d16-114">Akcje podejmowane przez każdy szablon.</span><span class="sxs-lookup"><span data-stu-id="e4d16-114">The actions taken by each template.</span></span> <span data-ttu-id="e4d16-115">**Metody** grupy czynności, które wykonują akcje tworzone przez szablon, tworzą lub dystrybuują pracę dla każdego typu szablonu grup czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-115">The wave **Methods** perform the actions that are created by the template, such creating or distributing work for each type of wave template.</span></span>
- <span data-ttu-id="e4d16-116">Atrybuty (filtry) grupy czynności, które muszą być stosowane w szablonie grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-116">The wave attributes (filters) that must apply for the wave template to be used.</span></span>

> [!NOTE]
> <span data-ttu-id="e4d16-117">W razie potrzeby deweloper może utworzyć dodatkowe metody.</span><span class="sxs-lookup"><span data-stu-id="e4d16-117">If needed, a developer can create additional methods.</span></span> <span data-ttu-id="e4d16-118">Możesz przejrzeć pełną listę metod na stronie **Metody przetwarzania grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-118">You can view the full list of methods on the **Wave process methods** page.</span></span>

<span data-ttu-id="e4d16-119">Niektóre ustawienia reprezentują strategiczne decyzje dla przetwarzania grupy czynności w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e4d16-119">Some settings represent strategic decisions for wave processing, as follows:</span></span>

- <span data-ttu-id="e4d16-120">Jeśli szablon jest używany do wysłania towarów dla zamówień sprzedaży i zamówień przeniesienia lub do przenoszenia towarów do produkcji dla zleceń produkcyjnych lub zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="e4d16-120">If the template is used for shipping items for sales orders and transfer orders, or used for moving items to production for production orders or kanbans.</span></span>
- <span data-ttu-id="e4d16-121">Jeśli przetwarzanie grupy czynności następuje ręcznie lub automatycznie, ma miejsce, co następuje:</span><span class="sxs-lookup"><span data-stu-id="e4d16-121">If a wave is processed manually or automatically, as follows:</span></span>

  - <span data-ttu-id="e4d16-122">**Ręczne przetwarzanie** — wiersz zostanie dodany do grupy czynności i zarezerwowane zostają zapasy, jednak należy kliknąć opcję **przetwórz** na stronie listy **Wszystkie grupy czynności**, aby utworzyć pracę pobrania dla zamówienia.</span><span class="sxs-lookup"><span data-stu-id="e4d16-122">**Manual processing** – The line is added to a wave and the inventory is reserved, however, you must select **Process** on the **All waves** list page to create the picking work for the order.</span></span>
  - <span data-ttu-id="e4d16-123">**Automatyczne przetwarzanie** — można całkowicie lub częściowo zautomatyzować przetwarzania grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-123">**Automatic processing** – You can fully or partially automate wave processing.</span></span> <span data-ttu-id="e4d16-124">Jeśli w pełni zautomatyzuje się proces przetwarzania grupy czynności, tworzona grupa czynności zawiera wiersz z zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban podczas tworzenia zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban.</span><span class="sxs-lookup"><span data-stu-id="e4d16-124">If you fully-automate wave processing, a wave is created that includes the line from the sales order, production order, or kanban when a sales order, production order, or kanban is created.</span></span> <span data-ttu-id="e4d16-125">Towary są odejmowane od dostępnych zapasów i tworzona jest praca pobierania.</span><span class="sxs-lookup"><span data-stu-id="e4d16-125">The items are deducted from on-hand inventory and the picking work is created.</span></span> <span data-ttu-id="e4d16-126">Jeśli częściowo zautomatyzuje się proces przetwarzania grupy czynności, można określić wartości, które będą powodowały przetwarzanie grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-126">If you partially automate wave processing, you can specify values that will trigger wave processing.</span></span> <span data-ttu-id="e4d16-127">Na przykład można określić maksymalną wagę dla dostaw, która będzie powodowała przetwarzanie grupy czynności, gdy łączna waga wierszy w grupie czynności osiągnie daną wartość.</span><span class="sxs-lookup"><span data-stu-id="e4d16-127">For example, you can specify a maximum weight for shipments that will trigger wave processing when the total weight of the lines in the wave reaches the value.</span></span>

- <span data-ttu-id="e4d16-128">Po przypisaniu wysyłek do otwartych grup czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-128">If you assign shipments to an open wave.</span></span> <span data-ttu-id="e4d16-129">Na przykład jeśli użytkownik zobowiązuje się wobec odbiorców do dostarczana zamówień złożonych do 12:00w ciągu 24 godzin, można ustawić szablon grupy czynności tak, aby automatycznie przypisywał do otwartej grupy czynności wiersze zamówienia do złożone do 12:00.</span><span class="sxs-lookup"><span data-stu-id="e4d16-129">For example, if you promise customers that an order placed by 12:00 PM will ship within 24 hours, you can set up the wave template to automatically assign order lines to an open wave until 12:00 PM.</span></span> <span data-ttu-id="e4d16-130">W takim przypadku grupa czynności jest przetwarzana automatycznie.</span><span class="sxs-lookup"><span data-stu-id="e4d16-130">At that time, the wave is automatically processed.</span></span>

<span data-ttu-id="e4d16-131">Podczas przetwarzania grupy czynności, tworzona praca pobrania jest oparta szablonie pracy i na dyrektywie lokalizacji, która jest określona dla magazynu.</span><span class="sxs-lookup"><span data-stu-id="e4d16-131">When a wave is processed, the picking work that is created is based on the work template and the location directive that is specified for the warehouse.</span></span> <span data-ttu-id="e4d16-132">Szablon pracy określa sposób tworzenia pracy pobierania, a dyrektywa lokalizacji określa lokalizacje pobrania i odłożenia.</span><span class="sxs-lookup"><span data-stu-id="e4d16-132">The work template specifies how the picking work is created, and the location directive specifies the pick and put locations.</span></span>

## <a name="create-a-wave-template"></a><span data-ttu-id="e4d16-133">Tworzenie szablonu grupy czynności</span><span class="sxs-lookup"><span data-stu-id="e4d16-133">Create a wave template</span></span>

<span data-ttu-id="e4d16-134">Aby skonfigurować szablon grupy czynności, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e4d16-134">To set up a wave template, follow these steps:</span></span>

1. <span data-ttu-id="e4d16-135">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Grupy czynności** \> **Szablony grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-135">Go to **Warehouse management** \> **Setup** \> **Waves** \> **Wave templates**.</span></span>
1. <span data-ttu-id="e4d16-136">Wybierz pozycję **Nowy**, aby utworzyć nowy szablon grupy.</span><span class="sxs-lookup"><span data-stu-id="e4d16-136">Select **New** to create a new wave template.</span></span>
1. <span data-ttu-id="e4d16-137">W polu **Typ szablonu grupy czynności** wybierz jeden z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="e4d16-137">In the **Wave template type** field, select one of the following options:</span></span>

    - <span data-ttu-id="e4d16-138">*Wysyłka* - Użyj szablonu grupy czynności do wysyłania towarów dla zamówień sprzedaży i zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="e4d16-138">*Shipping* - Use the wave template for shipping items for sales orders and transfer orders.</span></span>
    - <span data-ttu-id="e4d16-139">*Zlecenia produkcji* - Użyj szablonu grupy czynności do przeniesienia towarów dla zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="e4d16-139">*Production orders* - Use the wave template to move items for production orders.</span></span>
    - <span data-ttu-id="e4d16-140">*Kanban* - Użyj szablonu grupy czynności do przeniesienia towarów dla zleceń kanban.</span><span class="sxs-lookup"><span data-stu-id="e4d16-140">*Kanban* - Use the wave template to move items for kanban orders.</span></span>

1. <span data-ttu-id="e4d16-141">W polach **Nazwa szablonu grupy czynności** i **Opis szablonu grupy czynności** wprowadź nazwę i opis szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-141">In the **Wave template name** and **Wave template description** fields, enter a name and a description for the wave template.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4d16-142">Jeśli dla magazynu jest tworzony więcej niż jeden szablon, numer w polu **Sekwencja szablonów grupy czynności** wskazuje pozycję szablonu w kolejności, w jakiej szablony są stosowane po spełnia kryteriów szablonu.</span><span class="sxs-lookup"><span data-stu-id="e4d16-142">If more than one template is created for a warehouse, the number in the **Wave template sequence** field indicates the position of the template in the sequence in which the templates are applied when the template’s criteria is met.</span></span> <span data-ttu-id="e4d16-143">Można wybrać opcję **Przenieś w górę** lub **Przenieś w dół**, aby zmienić sekwencję szablonów.</span><span class="sxs-lookup"><span data-stu-id="e4d16-143">You can select **Move up** or **Move down** to rearrange the sequence of templates.</span></span>

1. <span data-ttu-id="e4d16-144">W polach **Oddział** i **Magazyn** wybierz witrynę i magazyn, dla których szablon grupy czynności utworzy grupy czynności i pracę pobierania.</span><span class="sxs-lookup"><span data-stu-id="e4d16-144">In the **Site** and **Warehouse** fields, select the site and warehouse that the wave template will create waves and picking work for.</span></span>
1. <span data-ttu-id="e4d16-145">Aby zautomatyzować przetwarzanie grupy czynności, w razie potrzeby należy wprowadzić następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="e4d16-145">If you want to automate wave processing, make the following settings as needed:</span></span>

    - <span data-ttu-id="e4d16-146">**Automatyczne tworzenie grupy czynności** -Wybierz opcję *Tak*, aby automatycznie utworzyć grupę czynności po zwolnieniu do magazynu zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban.</span><span class="sxs-lookup"><span data-stu-id="e4d16-146">**Automate wave creation** - Set this to *Yes* to automatically create a wave when a sales order, production order, or kanban is released to the warehouse.</span></span>
    - <span data-ttu-id="e4d16-147">**Przypisz do otwartych grupy czynności** — ustaw wartość *Tak*, aby automatycznie przypisywać wiersze do otwartej grupy czynności po zwolnieniu wierszy.</span><span class="sxs-lookup"><span data-stu-id="e4d16-147">**Assign to open waves** - Set this to *Yes* to automatically assign lines to an open wave when the lines are released.</span></span> <span data-ttu-id="e4d16-148">Wiersze są przypisywane do grup czynności w oparciu o filtr kwerendy dla szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-148">Lines are assigned to waves based on the query filter for the wave template.</span></span>
    - <span data-ttu-id="e4d16-149">**Przetwarzaj grupy czynności podczas zwalniania do magazynu** — ustaw wartość *Tak*, aby automatycznie przetwarzać grupy czynności i tworzyć pracę, gdy wiersz jest zwalniany do magazynu.</span><span class="sxs-lookup"><span data-stu-id="e4d16-149">**Process wave at release to warehouse** - Set this to *Yes* to automatically process the wave and create work when a line is released to the warehouse.</span></span>
    - <span data-ttu-id="e4d16-150">**Automatyczne przetwarzanie grupy czynności na progu** - Wybierz opcję *Tak*, aby automatycznie wykonywać grupy czynności po osiągnięciu przez jego wartości progów dla wagi, wysyłki i wierszy określonych w grupie pól **Progi grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-150">**Process wave automatically at threshold** - Set this to *Yes* to automatically process the wave when its values reach the thresholds for weight, shipment, and lines specified in the **Wave thresholds** field group.</span></span> <span data-ttu-id="e4d16-151">Ta opcja jest dostępna aktywna po wybraniu opcji *Wysyłka* w polu **Typ szablonu grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-151">This setting is only active if *Shipping* is selected in the **Wave template type** field.</span></span>
    - <span data-ttu-id="e4d16-152">**Automatyczne zwalnianie grupy czynności** — ustaw dla tego przycisku wartość *Tak*, aby automatycznie zwolnić grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-152">**Automate wave release** - Set this to *Yes* to automatically release the wave.</span></span> <span data-ttu-id="e4d16-153">Praca pobierania jest tworzona i udostępniana na urządzeniach przenośnych.</span><span class="sxs-lookup"><span data-stu-id="e4d16-153">The picking work is created and made available on mobile devices.</span></span>
    - <span data-ttu-id="e4d16-154">**Zautomatyzuj wydawanie prac związanych z uzupełnianiem zapasów** - ustaw opcję na *Tak*, aby tworzyć pracę uzupełnienia opartą na żądaniu, i zwalniać ją automatycznie.</span><span class="sxs-lookup"><span data-stu-id="e4d16-154">**Automate replenishment work release** - Set this to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="e4d16-155">Należy dodać do szablonu grupy czynności metodę grupy czynności uzupełnienia i utworzyć szablon uzupełnienia typu *Popyt grupy czynności*.</span><span class="sxs-lookup"><span data-stu-id="e4d16-155">You must add the replenishment wave method to the wave template, and create a replenishment template using the *Wave demand* type.</span></span> <span data-ttu-id="e4d16-156">Konfigurowanie szablonu uzupełniania zapasów znajdujących się na stronie **Szablony uzupełniania zapasów**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-156">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="e4d16-157">Wymaga to dodania metody uzupełnienie do szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-157">This requires that you add the replenish method to the wave template.</span></span>
    - <span data-ttu-id="e4d16-158">**Kontynuuj przetwarzanie grupowe, gdy tworzenie pracy nie powiedzie się** - ustwiając *Tak* system użyje pustej lokalizacji, jeśli nie może zarezerwować zapasów w lokalizacji proponowanej przez dyrektywę dotyczącą lokalizacji (na przykład, ponieważ zapasy nie są już dostępne).</span><span class="sxs-lookup"><span data-stu-id="e4d16-158">**Continue wave processing when work creation fails** - When set to *Yes*, the system will use a blank location if it can't reserve inventory at the location proposed by the location directive (for example, because the inventory is no longer available).</span></span> <span data-ttu-id="e4d16-159">Gdy jest *Nie*, fala zakończy się niepowodzeniem, jeśli system nie będzie mógł zarezerwować zapasów.</span><span class="sxs-lookup"><span data-stu-id="e4d16-159">When set to *No*, the wave will fail if the system can't reserve the inventory.</span></span>

1. <span data-ttu-id="e4d16-160">Ustaw grupę pól **Progi grupy czynności** w razie potrzeby:</span><span class="sxs-lookup"><span data-stu-id="e4d16-160">Set the **Wave thresholds** field group as needed:</span></span>
    - <span data-ttu-id="e4d16-161">**Próg wagi grupy czynności** — wprowadź maksymalną wagę, jaka może zawierać grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-161">**Wave weight threshold** - Enter the maximum weight a wave can contain.</span></span>
    - <span data-ttu-id="e4d16-162">**Próg wysyłki** — wprowadź maksymalną liczbę wysyłek, które można do grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-162">**Shipment threshold** - Enter the maximum number of shipments that can be included in a wave.</span></span>
    - <span data-ttu-id="e4d16-163">**Wierz wysyłki** — wprowadź maksymalną liczbę wierszy, które można do grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-163">**Line threshold** - Enter the maximum number of lines that can be included in a wave.</span></span>

1. <span data-ttu-id="e4d16-164">W grupie pól **Domyślne wartości**, wybierz atrybuty grupy czynności używanej jako dodatkowe kryteria dla szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-164">In the **Default values** field group, select the wave attributes to use as additional criteria for the wave template.</span></span> <span data-ttu-id="e4d16-165">Atrybuty grupy czynności są przydatne do przypisywania dodatkowych kryteriów, takich jak nazwa określonego odbiorcy, do szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-165">Wave attributes are useful for assigning additional criteria, such as a specific customer name, to a wave template.</span></span> <span data-ttu-id="e4d16-166">Utwórz atrybuty na stronie **Atrybuty grupy czynności**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-166">You create these attributes on the **Wave attributes** page.</span></span> 

1. <span data-ttu-id="e4d16-167">Ustaw **zasady dotyczące powiadomień grupy czynności** na zasady, których chcesz używać do generowania powiadomień związanych z grupy czynności, które używają tego szablonu.</span><span class="sxs-lookup"><span data-stu-id="e4d16-167">Set **Wave notification policy** to the policy you want to use for generating notifications related to waves that use this template.</span></span> <span data-ttu-id="e4d16-168">Aby uzyskać przykład zasad dotyczących powiadomień o grupy czynności, zobacz [Powiadomienia dotyczące wykonywania grupy czynności](wave-execution-notifications.md)c</span><span class="sxs-lookup"><span data-stu-id="e4d16-168">For an example of a wave notification policy, see [Wave execution notifications](wave-execution-notifications.md).</span></span>

1. <span data-ttu-id="e4d16-169">Na skróconej karcie **Metody** okienko **Wybrane metody** wymienia metody dla wybranego typu szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-169">On the **Methods** FastTab, the **Selected methods** pane lists the methods for the selected wave template.</span></span> <span data-ttu-id="e4d16-170">Metody grupy czynności, które wykonują akcje tworzone przez szablon, tworzą lub dystrybuują pracę.</span><span class="sxs-lookup"><span data-stu-id="e4d16-170">The wave methods perform the actions that are created by the template, such creating or distributing work.</span></span> <span data-ttu-id="e4d16-171">Te akcje są również zwane krokami grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-171">These actions are also referred to as wave steps.</span></span> <span data-ttu-id="e4d16-172">Metody grupy czynności są wstępnie zdefiniowane dla każdego typu szablonu grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-172">Wave methods are predefined for each type of wave template.</span></span> <span data-ttu-id="e4d16-173">Nie można usunąć wstępnie zdefiniowanych metod grupy czynności, można jednak zmienić kolejność metod i dodać dodatkowe metody.</span><span class="sxs-lookup"><span data-stu-id="e4d16-173">You cannot remove the predefined wave methods, however, you can rearrange the order of the methods and add additional methods.</span></span> <span data-ttu-id="e4d16-174">Na przykład jeśli tworzysz szablon grupy czynności do wysyłki, możesz dodać metody uzupełniania zapasów i tworzenia kontenerów.</span><span class="sxs-lookup"><span data-stu-id="e4d16-174">For example, if you’re creating a wave template for shipping, you can add methods for replenishment and containerization.</span></span> <span data-ttu-id="e4d16-175">Można dodawać tworzenia kontenerów grupy czynności do metod grupy czynności w celu definiowania tworzenia kontenerów wierszy przetworzonych w szablonie grupy czynności.</span><span class="sxs-lookup"><span data-stu-id="e4d16-175">Wave containerization can be added to a sequence of wave methods to define the containerization of the lines processed in a wave template.</span></span> <span data-ttu-id="e4d16-176">Aby dodać dodatkową metodę, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e4d16-176">To add an additional method, do the following:</span></span>

    - <span data-ttu-id="e4d16-177">W okienku **Pozostałe metody** wybierz metodę, a następnie wybierz przycisk  **Lewej** strzałki, aby dodać go do okienka **Wybrane metody**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-177">Select a method on the **Remaining methods** pane, and then select the **Left** arrow to add it to the **Selected methods** pane.</span></span>
    - <span data-ttu-id="e4d16-178">Aby zmienić kolejność, wybierz metodę, a następnie kliknij strzałki **w górę** lub **w dół**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-178">To change the sequence, select a method, and then select **Up** or **Down** arrows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4d16-179">Po dodaniu metody jest ona automatycznie wyświetlana w odpowiednim miejscu w sekwencji etapów.</span><span class="sxs-lookup"><span data-stu-id="e4d16-179">When you add a method, it’s automatically listed in the appropriate location in the sequence of steps.</span></span>

1. <span data-ttu-id="e4d16-180">Aby skonfigurować kwerendę, która dopasuje zwolnione wiersze do odpowiedniej grupy czynności, wybierz opcję **Edytuj kwerendę** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="e4d16-180">To set up the query that will match released lines to an appropriate wave, select **Edit query** on the Action Pane.</span></span>
1. <span data-ttu-id="e4d16-181">Aby sprawdzić, czy ustawienia szablonu grupy czynności są prawidłowe, kliknij **Zatwierdź szablon**.</span><span class="sxs-lookup"><span data-stu-id="e4d16-181">To verify that the wave template settings are valid, select **Validate template**.</span></span>