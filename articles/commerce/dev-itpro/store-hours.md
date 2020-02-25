---
title: Tworzenie i aktualizacja godzin w sklepie
description: W tym temacie opisano sposób tworzenia i aktualizowania godzin sklepu w programie Commerce Headquarters.
author: josaw1
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Retail 10.0.1 update
ms.openlocfilehash: 96ae5f33b1ab5fda98da4fc48b1fb883ca4d54b8
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024485"
---
# <a name="create-and-update-store-hours"></a><span data-ttu-id="8b970-103">Tworzenie i aktualizacja godzin w sklepie</span><span class="sxs-lookup"><span data-stu-id="8b970-103">Create and update store hours</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="8b970-104">Omówienie</span><span class="sxs-lookup"><span data-stu-id="8b970-104">Overview</span></span>

<span data-ttu-id="8b970-105">Z jednego miejsca Detaliści mogą tworzyć, obsługiwać i zarządzać godzinami przechowywania różnych sklepów w regionach geograficznych.</span><span class="sxs-lookup"><span data-stu-id="8b970-105">From a single place, retailers can create, maintain, and manage the store hours for different stores across geographic regions.</span></span> <span data-ttu-id="8b970-106">Godziny sklepu mogą być następnie wyświetlane w terminalach punkt sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="8b970-106">The store hours can then be shown on point of sale (POS) terminals.</span></span> <span data-ttu-id="8b970-107">W ten sposób kasjerzy mogą współużytkować godziny w sklepie z odbiorcami, a lepsza pomoc Shoppers osób zainteresowanych zapasami w innych sklepach.</span><span class="sxs-lookup"><span data-stu-id="8b970-107">In this way, cashiers can share store hours with customers and better help shoppers who are interested in inventory in other stores.</span></span> <span data-ttu-id="8b970-108">Godziny sklepu mogą być również drukowane na paragonach, na wypadek, gdyby odbiorcy mogli później powrócić do sklepu.</span><span class="sxs-lookup"><span data-stu-id="8b970-108">The store hours can also be printed on receipts, in case customers want to return to the store later.</span></span>

<span data-ttu-id="8b970-109">Wiele godzin sklepu można skonfigurować w różnych kanałach.</span><span class="sxs-lookup"><span data-stu-id="8b970-109">Multiple store hours can be configured across different channels.</span></span> <span data-ttu-id="8b970-110">Te kanały obejmują sklepy fizyczne, biura obsługi, urządzenia przenośne oraz witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="8b970-110">These channels include brick-and-mortar stores, call centers, mobile devices, and e-Commerce sites.</span></span>

<span data-ttu-id="8b970-111">Jeśli odbiorca ma zamówienie pobrania dla innego sklepu, kasjer może wybrać daty, kiedy pobranie będzie dostępne w tym sklepie.</span><span class="sxs-lookup"><span data-stu-id="8b970-111">If a customer has a pickup order for a different store, the cashier can select dates when the pickup will be available in that store.</span></span> <span data-ttu-id="8b970-112">Wyszukiwanie w sklepie będzie zawierać odwołanie do dat i godzin przechowywania.</span><span class="sxs-lookup"><span data-stu-id="8b970-112">The store lookup will provide a reference to the dates and store times.</span></span> <span data-ttu-id="8b970-113">Kasjer może wybrać datę i lokalizację, a także wydrukować przyjęcie do pobrania zawierające godziny sklepowe.</span><span class="sxs-lookup"><span data-stu-id="8b970-113">The cashier can select a date and location, and can also print a pickup receipt that includes the store hours.</span></span>

<span data-ttu-id="8b970-114">Ta funkcja jest dostępna w Microsoft Dynamics 365 Retail wersjach 8.1.2 i nowszych.</span><span class="sxs-lookup"><span data-stu-id="8b970-114">This functionality is available in Microsoft Dynamics 365 Retail versions 8.1.2 and later.</span></span>

## <a name="configure-store-hours"></a><span data-ttu-id="8b970-115">Konfiguruj godziny pracy sklepu</span><span class="sxs-lookup"><span data-stu-id="8b970-115">Configure store hours</span></span>

<span data-ttu-id="8b970-116">Aby skonfigurować godziny pracy sklepu, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8b970-116">Follow these steps to configure store hours.</span></span>

1. <span data-ttu-id="8b970-117">Przejdź do **Handel detaliczny i inny** \> **Ustawienia kanału** \> **Godziny otwarcia sklepu**.</span><span class="sxs-lookup"><span data-stu-id="8b970-117">Go to **Retail and Commerce** \> **Channel Setup** \> **Store hours**.</span></span>
2. <span data-ttu-id="8b970-118">Naciśnij przycisk **Nowy**, aby utworzyć nowy szablon godzin pracy.</span><span class="sxs-lookup"><span data-stu-id="8b970-118">Select **New** to create a new store hours template.</span></span> <span data-ttu-id="8b970-119">Aby skorzystać z istniejącego szablonu, wybierz szablon w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="8b970-119">To use an existing template, select the template in the left pane.</span></span>
3. <span data-ttu-id="8b970-120">W oknie dialogowym **Dodaj zakres** określ zakres dat, godziny sklepu oraz wszelkie wymagane święta.</span><span class="sxs-lookup"><span data-stu-id="8b970-120">In the **Add range** dialog box, define the date range, the store hours, and any holidays that are required.</span></span>

    - <span data-ttu-id="8b970-121">Jeśli godziny sklepu nie zmieniają się, należy wybrać opcję **Nigdy nie zakończone** w polu **Data zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="8b970-121">If store hours don't change, select **Never ends** in the **End date** field.</span></span>
    - <span data-ttu-id="8b970-122">Jeśli godziny w sklepie dotyczą określonego miesiąca, tygodnia lub dnia, należy określić odpowiednie daty w polach **Data początkowa** i **Data końcowa**.</span><span class="sxs-lookup"><span data-stu-id="8b970-122">If the store hours are for a specific month, week, or day, set the appropriate dates in the **Start Date** and **End date** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b970-123">Można utworzyć wiele szablonów mających nakładające się daty rozpoczęcia i zakończenia.</span><span class="sxs-lookup"><span data-stu-id="8b970-123">You can create multiple templates that have overlapping start and end dates.</span></span> <span data-ttu-id="8b970-124">Można więc na przykład zdefiniować godziny sklepu w różnych strefach czasowych.</span><span class="sxs-lookup"><span data-stu-id="8b970-124">Therefore, you can, for example, define store hours for stores in different time zones.</span></span>

    <span data-ttu-id="8b970-125">![Dodaj zakres okna dialogowego](../dev-itpro/media/Storehours1.png "Dodaj zakres okna dialogowego")</span><span class="sxs-lookup"><span data-stu-id="8b970-125">![Add range dialog box](../dev-itpro/media/Storehours1.png "Add range dialog box")</span></span>

4. <span data-ttu-id="8b970-126">Szablonem godzin sklepu należy skojarzyć z magazynami, w których będzie używany.</span><span class="sxs-lookup"><span data-stu-id="8b970-126">Associate the store hours template with the stores where it will be used.</span></span> <span data-ttu-id="8b970-127">W oknie dialogowym **Wybieranie węzłów organizacji** wybierz sklepy, regiony i organizacje, z którymi szablon ma być skojarzony.</span><span class="sxs-lookup"><span data-stu-id="8b970-127">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>

    - <span data-ttu-id="8b970-128">Z każdym sklepem można skojarzyć tylko jeden szablon godzin sklepu.</span><span class="sxs-lookup"><span data-stu-id="8b970-128">Only one store hours template can be associated with each store.</span></span>
    - <span data-ttu-id="8b970-129">Za pomocą przycisków strzałek wybierz sklepy, regiony lub organizacje</span><span class="sxs-lookup"><span data-stu-id="8b970-129">Use the arrow buttons to select stores, regions, or organizations.</span></span> <span data-ttu-id="8b970-130">Kalendarz będzie dostępny dla sklepów lub grup sklepów i będzie widoczny w punkcie sprzedaży dla celów referencyjnych.</span><span class="sxs-lookup"><span data-stu-id="8b970-130">The calendar will be available to the stores or store groups, and it will be visible at the POS for reference.</span></span>

    <span data-ttu-id="8b970-131">![Wybierz okienko dialogowe węzły organizacji](../dev-itpro/media/Storehours2.png "Wybierz okienko dialogowe węzły organizacji")</span><span class="sxs-lookup"><span data-stu-id="8b970-131">![Choose organization nodes dialog box](../dev-itpro/media/Storehours2.png "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="8b970-132">Na stronie **harmonogramdystrybucji** uruchom zadania **1070** i **1090**, aby udostępnić godziny sklepu w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8b970-132">On the **Distribution schedule** page, run the **1070** and **1090** jobs to make the store hours available to the POS.</span></span>

## <a name="add-store-hours-to-printed-receipts"></a><span data-ttu-id="8b970-133">Dodawanie godzin sklepu do przyjęć drukowanych</span><span class="sxs-lookup"><span data-stu-id="8b970-133">Add store hours to printed receipts</span></span>

<span data-ttu-id="8b970-134">Wykonaj poniższe kroki, aby dodać godziny sklepu do wydrukowanych przyjęć w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8b970-134">Follow these steps to add store hours to the printed POS receipts.</span></span>

1. <span data-ttu-id="8b970-135">Otwórz projektanta formatu paragonu.</span><span class="sxs-lookup"><span data-stu-id="8b970-135">Open the receipt designer.</span></span>
2. <span data-ttu-id="8b970-136">Zaznacz **Stopkę** w lewym dolnym rogu.</span><span class="sxs-lookup"><span data-stu-id="8b970-136">Select **Footer** in the lower-left corner.</span></span>
3. <span data-ttu-id="8b970-137">Przeciągnij element **Godziny pracy sklepu** z lewego okienka do stopki w dolnej części szablonu paragonu.</span><span class="sxs-lookup"><span data-stu-id="8b970-137">Drag the **Store hours** element from the left pane to the footer at the bottom of the receipt template.</span></span>
4. <span data-ttu-id="8b970-138">W razie konieczności można edytować domyślną etykietę w **Godziny pracy sklepu**.</span><span class="sxs-lookup"><span data-stu-id="8b970-138">You can edit the default label on the **Store hours** element as you require.</span></span>
5. <span data-ttu-id="8b970-139">Zapisz paragon i zamknij projektanta formatu paragonu.</span><span class="sxs-lookup"><span data-stu-id="8b970-139">Save the receipt, and close the receipt designer.</span></span>
6. <span data-ttu-id="8b970-140">Na stronie **harmonogram dystrybucji** ruchom zadania **1070** and **1090**.</span><span class="sxs-lookup"><span data-stu-id="8b970-140">On the **Distribution schedule** page, run the **1070** and **1090** jobs.</span></span>
7. <span data-ttu-id="8b970-141">Zaloguj się w kasie POS.</span><span class="sxs-lookup"><span data-stu-id="8b970-141">Sign in to the POS.</span></span>
8. <span data-ttu-id="8b970-142">Zakończ sprzedaż i wybierz opcję drukowania paragonu.</span><span class="sxs-lookup"><span data-stu-id="8b970-142">Complete a sale, and select to print a receipt.</span></span>

<span data-ttu-id="8b970-143">W przyjęciu w punkcie sprzedaży zostaną uwzględnione godziny sklepu.</span><span class="sxs-lookup"><span data-stu-id="8b970-143">POS receipts now include the store hours.</span></span> <span data-ttu-id="8b970-144">Jeśli w szablonie uwzględniono dni wolne od pracy, zostaną one wyświetlone na paragonie.</span><span class="sxs-lookup"><span data-stu-id="8b970-144">If any holidays were included in the template, they are shown on the receipt.</span></span>

<span data-ttu-id="8b970-145">![Przykład paragonu](../dev-itpro/media/Storehours3.png "Przykład paragonu")</span><span class="sxs-lookup"><span data-stu-id="8b970-145">![Receipt example](../dev-itpro/media/Storehours3.png "Receipt example")</span></span>
