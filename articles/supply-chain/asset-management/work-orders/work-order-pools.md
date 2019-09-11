---
title: Pule zleceń pracy
description: W tym temacie opisano pracę z pulami zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875841"
---
# <a name="work-order-pools"></a><span data-ttu-id="fb607-103">Pule zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="fb607-103">Work order pools</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="fb607-104">Pul zleceń pracy można używać do grupowania zleceń, które mają coś wspólnego.</span><span class="sxs-lookup"><span data-stu-id="fb607-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="fb607-105">Można na przykład utworzyć pule zleceń pracy dla</span><span class="sxs-lookup"><span data-stu-id="fb607-105">For example, you can create work order pools for</span></span>

- <span data-ttu-id="fb607-106">załóg roboczych, na przykład załoga konserwacji A, załoga konserwacji B</span><span class="sxs-lookup"><span data-stu-id="fb607-106">work crews, for example, Maintenance Crew A, Maintenance Crew B</span></span>  

- <span data-ttu-id="fb607-107">kwalifikacji zawodowych, na przykład elektrycy lub hydraulicy</span><span class="sxs-lookup"><span data-stu-id="fb607-107">professional skills, for example, electricians or plumbers</span></span>  

- <span data-ttu-id="fb607-108">fizyczne lokalizacje</span><span class="sxs-lookup"><span data-stu-id="fb607-108">physical locations</span></span>  

- <span data-ttu-id="fb607-109">harmonogramy czasu, na przykład tygodnie lub inne okresy</span><span class="sxs-lookup"><span data-stu-id="fb607-109">time schedules, for example, weeks or other periods</span></span>  


<span data-ttu-id="fb607-110">W razie potrzeby jedno zlecenie pracy może zostać umieszczone w wielu pulach zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-110">If required, one work order can be placed in many work order pools.</span></span>


## <a name="create-work-order-pool"></a><span data-ttu-id="fb607-111">Utwórz pulę zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="fb607-111">Create work order pool</span></span>

<span data-ttu-id="fb607-112">We **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy** można uzyskać przegląd pul zleceń pracy i utworzyć nowe pule.</span><span class="sxs-lookup"><span data-stu-id="fb607-112">In **All work order pools** or **Active work order pools**, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="fb607-113">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="fb607-113">Click **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="fb607-114">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="fb607-114">Click **New**.</span></span>

3. <span data-ttu-id="fb607-115">Wstaw Identyfikator puli zleceń pracy w polu **Pula** oraz nazwę w polu **Nazwa**.</span><span class="sxs-lookup"><span data-stu-id="fb607-115">Insert a work order pool ID in the **Pool** field and a name in the **Name** field.</span></span>

4. <span data-ttu-id="fb607-116">Wybierz wartość tak na **aktywnym** przycisku przełącznika, aby wskazać, że Pula zleceń pracy jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="fb607-116">Select "Yes" on the **Active** toggle button to indicate that the work order pool is active.</span></span>

5. <span data-ttu-id="fb607-117">Jeśli chcesz, aby zlecenia pracy były automatycznie usuwane z puli zleceń pracy, wybierz wartość tak w przycisku **Usuń relację zlecenia produkcyjnego**.</span><span class="sxs-lookup"><span data-stu-id="fb607-117">Select "Yes" on the **Delete work order relations** toggle button if you want work orders to be automatically removed from the work order pool.</span></span>

6. <span data-ttu-id="fb607-118">W polu **Usuń stan cyklu życia** wybierz stan cyklu życia zamówienia pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-118">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="fb607-119">Na przykład stan cyklu życia zlecenia produkcyjnego służącego do ukończenia zlecenia produkcyjnego może zostać skonfigurowany w taki sposób, aby automatycznie usuwać relacje do pul zleceń</span><span class="sxs-lookup"><span data-stu-id="fb607-119">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

7. <span data-ttu-id="fb607-120">Można natychmiast rozpocząć dodawanie zleceń roboczych do puli zleceń roboczych.</span><span class="sxs-lookup"><span data-stu-id="fb607-120">You can start adding work orders to your work order pool right away.</span></span> <span data-ttu-id="fb607-121">Na skróconej karcie **Zlecenia pracy**, należy kliknąć przycisk **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="fb607-121">On the **Work orders** FastTab, click **Add line**.</span></span>

8. <span data-ttu-id="fb607-122">W polu **Zlecenie pracy** wybierz zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-122">Select a work order in the **Work order** field.</span></span> <span data-ttu-id="fb607-123">Pola pokrewne są automatycznie aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="fb607-123">The related fields are automatically updated.</span></span>

9. <span data-ttu-id="fb607-124">Jeśli chcesz dodać więcej zleceń pracy, powtórz kroki 7-8</span><span class="sxs-lookup"><span data-stu-id="fb607-124">Repeat steps 7-8 if you want to add more work orders.</span></span>

10. <span data-ttu-id="fb607-125">W polu **porządek sortowania** można określić, czy zlecenia pracy powinny być wykonywane w określonym zamówieniu.</span><span class="sxs-lookup"><span data-stu-id="fb607-125">In the **Sort order** field, you can indicate if the work orders should be carried out in a certain order.</span></span> <span data-ttu-id="fb607-126">Wstaw numery 1, 2, 3 i tak dalej, aby wskazać określoną sekwencję dla wybranych zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-126">Insert numbers 1, 2, 3, and so on to indicate a specific sequence for the selected work orders.</span></span>

11. <span data-ttu-id="fb607-127">Kliknij przycisk **zlecenia pracy**, aby wyświetlić listę wszystkich zleceń pracy uwzględnionych w puli zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-127">Click the **Work orders** button to see a list of all the work orders included in the work order pool.</span></span>

12. <span data-ttu-id="fb607-128">Kliknij przycisk **Obciążenie wydajności**, aby otworzyć **Obciążenie wydajności** w celu obliczenia i wyświetlenia obciążenia zdolności produkcyjnych w harmonogramie konserwacji, a nie zaplanowanych zleceń pracy i zaplanowanych zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-128">Click the **Capacity load** button to open **Capacity load** to calculate and view capacity load for maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

13. <span data-ttu-id="fb607-129">Kliknij przycisk **Prognoza dla pozycji**, aby otworzyć **Prognoza dla pozycji** i wyświetlić prognozy dla towarów (części zamienne i inne wymagane towary) związane z harmonogramem obsługi, niezaplanowanymi zleceniami produkcyjnymi i zaplanowanymi zleceniami produkcyjnymi.</span><span class="sxs-lookup"><span data-stu-id="fb607-129">Click the **Item forecast** button to open **Item forecast** to calculate and view forecasts for items (spare parts and other required items) related to maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

14. <span data-ttu-id="fb607-130">Kliknij przycisk **Zapotrzebowanie na zakup zlecenia pracy**, aby otworzyć listę **Zapotrzebowanie na zakup zlecenia pracy** w celu wyświetlenia listy zapotrzebowań zakupu związanych z zleceniami roboczymi w puli zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-130">Click the **Work order purchase requisition** button to open the **Work order purchase requisition** list to see a list of purchase requisitions related to the work orders in the work order pool.</span></span>

15. <span data-ttu-id="fb607-131">Kliknij przycisk **Zapotrzebowanie na zakup zlecenia pracy**, aby otworzyć listę **Zapotrzebowanie na zakup zlecenia pracy** w celu wyświetlenia listy zamówień zakupu związanych z zleceniami roboczymi w puli zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-131">Click the **Work order purchase** button to open the **Work order purchase** list to see a list of purchase orders related to the work orders in the work order pool.</span></span>

>[!NOTE]
><span data-ttu-id="fb607-132">Jeśli pula zleceń roboczych nie jest już odpowiednia dla planowania pracy, należy w widoku listy **Pula zleceń pracy** skonfigurować pole wyboru **aktywne** dla tej puli na wartość nie</span><span class="sxs-lookup"><span data-stu-id="fb607-132">When a work order pool is no longer relevant for your work planning, set the **Active** check box for that pool to "No" in the **Work order pool** list view.</span></span>

<span data-ttu-id="fb607-133">Zaznacz pole **Usuń relacje zlecenia pracy**, jeśli chcesz usunąć wszystkie wiersze zlecenia, na przykład w celu utworzenia pustej puli, którą można później używać w innych zleceniach produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="fb607-133">Select the **Delete work order relations** check box if you want to delete all work order lines, for example to create an empty pool that you can later use for other work orders.</span></span> <span data-ttu-id="fb607-134">Pamiętaj, aby wyczyścić **Usuń relacje zlecenia pracy**, jeśli chcesz użyć puli zleceń roboczych do późniejszego utworzenia relacji zleceń</span><span class="sxs-lookup"><span data-stu-id="fb607-134">Remember to clear the **Delete work order relations** check box if you want to use the work order pool to create new work order relations later.</span></span>


![Rysunek 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a><span data-ttu-id="fb607-136">Dodaj zlecenie pracy do puli zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="fb607-136">Add work order to a work order pool</span></span>

<span data-ttu-id="fb607-137">Jak opisano w sekcji powyżej, podczas tworzenia puli można dodawać zlecenia produkcyjne do puli zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="fb607-137">As described in the section above, you can add work orders to a work order pool when you create the pool.</span></span> <span data-ttu-id="fb607-138">Można również dodać zlecenie pracy do puli zleceń pracy z jednej z list **Wszystkie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="fb607-138">You can also add a work order to a work order pool from one of the **All work orders** list.</span></span>

1. <span data-ttu-id="fb607-139">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="fb607-139">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fb607-140">Wybierz zlecenie pracy z listy i kliknij przycisk **Pula zleceń pracy.**</span><span class="sxs-lookup"><span data-stu-id="fb607-140">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="fb607-141">Wybierz opcję „Dodaj” w **Dodaj/Usuń**.</span><span class="sxs-lookup"><span data-stu-id="fb607-141">Select "Add" in the **Add/remove** field.</span></span>

4. <span data-ttu-id="fb607-142">Wybierz pulę zleceń pracy w polu **Pula**.</span><span class="sxs-lookup"><span data-stu-id="fb607-142">Select the work order pool in the **Pool** field.</span></span>

5. <span data-ttu-id="fb607-143">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb607-143">Click **OK**.</span></span>

6. <span data-ttu-id="fb607-144">Po dodaniu zlecenia pracy do puli zleceń pracy, jeśli zlecenie ma zostać umieszczone w konkretnej kolejności w puli: Otwórz jedną z stron listy pul zleceń, wybierz pulę i kliknij przycisk **Edytuj**i dostosuj kolejność sortowania zleceń pracy w puli w formularzu **Pula zleceń roboczych** > karta skrócona **Zlecenia pracy** > pole **Porządek sortowania**.</span><span class="sxs-lookup"><span data-stu-id="fb607-144">After you have added a work order to a work order pool, if you want to place the work order in a specific sequence in the pool: Open one of the work order pools list pages, select the pool and click **Edit**, and adjust the sort order of the work orders included in pool in the **Work order pool** form > **Work orders** FastTab > **Sort order** field.</span></span>

<span data-ttu-id="fb607-145">Jeśli chcesz usunąć wybrane zlecenie pracy z puli zleceń pracy, wybierz opcję „Usuń” w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="fb607-145">If you want to remove the selected work order from a work order pool, select "Remove" in step 3.</span></span>

