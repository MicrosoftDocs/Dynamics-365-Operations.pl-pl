---
title: Konfigurowanie i generowanie informacji o wiekowaniu rozrachunków z odbiorcami
description: Ten podręcznik pomoże skonfigurować definicję okresu wiekowania, wiekować salda odbiorców oraz wyświetlać salda na liście Wiekowane saldo i stronie Windykacja.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19b60d5fcfba995d08f12d0548f41a0c3d2781fb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012093"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="1464a-103">Konfigurowanie i generowanie informacji o wiekowaniu rozrachunków z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="1464a-103">Set up and generate accounts receivable aging information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1464a-104">Ten podręcznik pomoże skonfigurować definicję okresu wiekowania, wiekować salda odbiorców oraz wyświetlać salda na liście Wiekowane saldo i stronie Windykacja.</span><span class="sxs-lookup"><span data-stu-id="1464a-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="1464a-105">To nagranie wykorzystuje firmę demonstracyjną USMF.</span><span class="sxs-lookup"><span data-stu-id="1464a-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="1464a-106">Tworzenie definicji okresu wiekowania</span><span class="sxs-lookup"><span data-stu-id="1464a-106">Create an aging period definition</span></span>
1. <span data-ttu-id="1464a-107">Otwórz **Okienko nawigacji > Moduły > Kredyty i windykacja > Ustawienia > Definicje okresów wiekowania**.</span><span class="sxs-lookup"><span data-stu-id="1464a-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Aging period definitions**.</span></span>
2. <span data-ttu-id="1464a-108">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="1464a-108">Click **New**.</span></span>
3. <span data-ttu-id="1464a-109">W polu **Definicja okresu wiekowania** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1464a-109">In the **Aging period definition** field, type a value.</span></span>
4. <span data-ttu-id="1464a-110">W polu **Opis** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="1464a-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="1464a-111">Kliknij przycisk **Dodaj poniżej**, aby wstawić nowy okres wiekowania.</span><span class="sxs-lookup"><span data-stu-id="1464a-111">Click **Add below** to insert a new aging period.</span></span>
6. <span data-ttu-id="1464a-112">W polu **Okres** wprowadź opis, który ma być wyświetlany w raportach o wiekowaniu.</span><span class="sxs-lookup"><span data-stu-id="1464a-112">In the **Period** field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="1464a-113">W polu **Jednostka** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="1464a-113">In the **Unit** field, enter a number.</span></span>
8. <span data-ttu-id="1464a-114">W polu **Interwał** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="1464a-114">In the **Interval** field, select an option.</span></span> <span data-ttu-id="1464a-115">Okres finansowy odpowiada okresowi w kalendarzu księgi.</span><span class="sxs-lookup"><span data-stu-id="1464a-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="1464a-116">Dzień, tydzień, miesiąc, kwartał i lata określają wielkość zakresu według typu daty.</span><span class="sxs-lookup"><span data-stu-id="1464a-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="1464a-117">Opcja Nieograniczony powoduje zaznaczenie wszystkich transakcji przed lub po poprzednim okresie, w zależności od tego, czy jest to pierwszy czy ostatni okres.</span><span class="sxs-lookup"><span data-stu-id="1464a-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="1464a-118">W polu **Wskaźnik wiekowania** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="1464a-118">In the **Aging indicator** field, select an option.</span></span>
10. <span data-ttu-id="1464a-119">Zaznacz okres w górnej części siatki.</span><span class="sxs-lookup"><span data-stu-id="1464a-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="1464a-120">Zaktualizuj opis, aby dotyczył najstarszego okresu w definicji okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="1464a-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="1464a-121">W polu **Okres** wprowadź nowy opis okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="1464a-121">In the **Period** field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="1464a-122">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1464a-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="1464a-123">Wiekowanie sald</span><span class="sxs-lookup"><span data-stu-id="1464a-123">Age the balances</span></span>
1. <span data-ttu-id="1464a-124">Wybierz kolejno opcje **Kredyty i windykacja > Zadania okresowe > Wiekuj salda odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="1464a-124">Go to **Credit and collections > Periodic tasks > Age customer balances**.</span></span>
2. <span data-ttu-id="1464a-125">W polu **Definicja okresu wiekowania** zaznacz utworzoną przez siebie definicję okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="1464a-125">In the **Aging period definition** field, select the aging period definition that you created.</span></span>
    + <span data-ttu-id="1464a-126">Może istnieć jedna aktywna migawka dla każdej definicji okresu wiekowania.</span><span class="sxs-lookup"><span data-stu-id="1464a-126">You can have one active snapshot for each aging period definition.</span></span>  
    + <span data-ttu-id="1464a-127">Domyślnie są przetwarzani wszyscy odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1464a-127">All customers are processed by default.</span></span> <span data-ttu-id="1464a-128">Można użyć tej opcji, aby obliczyć jedną pulę windykacji dla wszystkich odbiorców.</span><span class="sxs-lookup"><span data-stu-id="1464a-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    + <span data-ttu-id="1464a-129">Wybierz datę z transakcji, która będzie używana do wiekowania.</span><span class="sxs-lookup"><span data-stu-id="1464a-129">Select the date from the transaction that you will use for the aging.</span></span>  
    + <span data-ttu-id="1464a-130">Wybierz dla wiekowania datę „na dzień”.</span><span class="sxs-lookup"><span data-stu-id="1464a-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="1464a-131">Wartością domyślną jest Dzisiaj, ale jeśli wartość pola zostanie zmieniona na Wybrana data, będzie można wybrać żądaną datę.</span><span class="sxs-lookup"><span data-stu-id="1464a-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="1464a-132">Dla przetwarzania wsadowego użyj opcji Data dzisiejsza.</span><span class="sxs-lookup"><span data-stu-id="1464a-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="1464a-133">Rozwiń węzeł **Zakres** firm.</span><span class="sxs-lookup"><span data-stu-id="1464a-133">Expand the **Company** range.</span></span> <span data-ttu-id="1464a-134">Można wybrać firmy, które zostaną uwzględnione w migawce.</span><span class="sxs-lookup"><span data-stu-id="1464a-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="1464a-135">Bieżąca firma jest zaznaczona domyślnie.</span><span class="sxs-lookup"><span data-stu-id="1464a-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="1464a-136">Kliknij przycisk **OK**, aby wykonać przetwarzanie migawki.</span><span class="sxs-lookup"><span data-stu-id="1464a-136">Click **Ok** to process the snapshot.</span></span> <span data-ttu-id="1464a-137">Trochę to potrwa, dlatego poczekaj, aż suwak zniknie, i poszukaj komunikatu w centrum komunikatów.</span><span class="sxs-lookup"><span data-stu-id="1464a-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="1464a-138">Wyświetlanie sald na liście Wiekowane salda i na stronie Windykacja</span><span class="sxs-lookup"><span data-stu-id="1464a-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="1464a-139">Wybierz kolejno opcje **Kredyty i windykacja > Windykacja > Wiekowane salda**.</span><span class="sxs-lookup"><span data-stu-id="1464a-139">Go to **Credit and collections > Collections > Aged balances**.</span></span> <span data-ttu-id="1464a-140">Strona listy pokazuje salda odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="1464a-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="1464a-141">Ikona wiekowania pokazuje okres wiekowania dla najstarszej transakcji.</span><span class="sxs-lookup"><span data-stu-id="1464a-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="1464a-142">Wybierz odbiorcę z saldem.</span><span class="sxs-lookup"><span data-stu-id="1464a-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="1464a-143">Rozwiń pole informacji **Wiekowanie** i obejrzyj wiekowane salda.</span><span class="sxs-lookup"><span data-stu-id="1464a-143">Expand the **Aging fact** box area to view the aged balances.</span></span> <span data-ttu-id="1464a-144">Definicja okresu wiekowania dla pola informacji jest pobierana z domyślnej definicji okresu wiekowania określonej w parametrach.</span><span class="sxs-lookup"><span data-stu-id="1464a-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="1464a-145">Można ją zmienić za pomocą menu Zbierz.</span><span class="sxs-lookup"><span data-stu-id="1464a-145">You can change it using the Collect menu.</span></span>  

