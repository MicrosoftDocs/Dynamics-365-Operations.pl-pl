---
title: Pule zleceń pracy
description: W tym temacie opisano pracę z pulami zleceń pracy w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3e95a4fdfaf4817867f3d2df7774df6a27ee6599
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889512"
---
# <a name="work-order-pools"></a><span data-ttu-id="23412-103">Pule zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="23412-103">Work order pools</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="23412-104">Pul zleceń pracy można używać do grupowania zleceń, które mają coś wspólnego.</span><span class="sxs-lookup"><span data-stu-id="23412-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="23412-105">Poniżej przedstawiono przykłady sposobów tworzenia pul zleceń pracy dla:</span><span class="sxs-lookup"><span data-stu-id="23412-105">Here are some examples of things that you can create  work order pools for:</span></span>

- <span data-ttu-id="23412-106">Załóg pracy, na przykład załoga konserwacji A lub załoga konserwacji B</span><span class="sxs-lookup"><span data-stu-id="23412-106">Work crews, for example, Maintenance Crew A or Maintenance Crew B</span></span>  

- <span data-ttu-id="23412-107">Kwalifikacji zawodowych, na przykład elektrycy lub hydraulicy</span><span class="sxs-lookup"><span data-stu-id="23412-107">Professional skills, such as electricians or plumbers</span></span>  

- <span data-ttu-id="23412-108">Fizyczne lokalizacje</span><span class="sxs-lookup"><span data-stu-id="23412-108">Physical locations</span></span>  

- <span data-ttu-id="23412-109">Harmonogramy czasu, na przykład tygodnie lub inne okresy</span><span class="sxs-lookup"><span data-stu-id="23412-109">Time schedules, such as weeks or other periods</span></span>  

<span data-ttu-id="23412-110">W razie konieczności można umieścić jedno zlecenie w wielu pulach zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-110">As you require, you can put one work order in multiple work order pools.</span></span>


## <a name="create-a-work-order-pool"></a><span data-ttu-id="23412-111">Utwórz pulę zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="23412-111">Create a work order pool</span></span>

<span data-ttu-id="23412-112">Na stronach list **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy** można uzyskać przegląd pul zleceń pracy i utworzyć nowe pule.</span><span class="sxs-lookup"><span data-stu-id="23412-112">On the **All work order pools** or **Active work order pools** list page, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="23412-113">Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Pule zleceń pracy** > **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-113">Select **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="23412-114">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="23412-114">Select **New**.</span></span>

3. <span data-ttu-id="23412-115">W polu **Pula** wpisz identyfikator dla puli zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-115">In the **Pool** field, enter an ID for the work order pool.</span></span>

4. <span data-ttu-id="23412-116">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="23412-116">the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="23412-117">W opcji **Aktywne** wybierz wartość **Tak**, aby wskazać, że pula zleceń pracy jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="23412-117">Set the **Active** option to **Yes** to indicate that the work order pool is active.</span></span>

6. <span data-ttu-id="23412-118">Jeśli chcesz, aby zlecenia pracy były automatycznie usuwane z puli zleceń pracy, ustaw opcję **Usuń relacje zlecenia pracy** jako **Tak**.</span><span class="sxs-lookup"><span data-stu-id="23412-118">Set the **Delete work order relations** option to **Yes** if work orders should automatically be removed from the work order pool.</span></span>

7. <span data-ttu-id="23412-119">W polu **Usuń stan cyklu życia** wybierz stan cyklu życia zamówienia pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-119">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="23412-120">Na przykład stan cyklu życia zlecenia produkcyjnego służącego do ukończenia zlecenia produkcyjnego może zostać skonfigurowany w taki sposób, aby automatycznie usuwać relacje do pul zleceń</span><span class="sxs-lookup"><span data-stu-id="23412-120">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

    <span data-ttu-id="23412-121">Można natychmiast rozpocząć dodawanie zleceń roboczych do puli zleceń roboczych.</span><span class="sxs-lookup"><span data-stu-id="23412-121">You can start adding work orders to your work order pool right away.</span></span>

8. <span data-ttu-id="23412-122">Na skróconej karcie **Zlecenia pracy**, należy wybrać przycisk **Dodaj wiersz**.</span><span class="sxs-lookup"><span data-stu-id="23412-122">On the **Work orders** FastTab, select **Add line**.</span></span>

9. <span data-ttu-id="23412-123">W polu **Zlecenie pracy** wybierz zlecenie pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-123">In the **Work order** field, select a work order.</span></span> <span data-ttu-id="23412-124">Pola pokrewne są automatycznie aktualizowane.</span><span class="sxs-lookup"><span data-stu-id="23412-124">The related fields are automatically updated.</span></span>

10. <span data-ttu-id="23412-125">Powtórz kroki od 8 do 9, aby dodać więcej zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-125">Repeat steps 8 through 9 to add more work orders.</span></span>

11. <span data-ttu-id="23412-126">Jeśli dodane zlecenia pracy powinny zostać wykonane w określonym porządku, w polu **Porządek sortowania** można wprowadzić numery **1**, **2**, **3** itd., aby określić takie zlecenie.</span><span class="sxs-lookup"><span data-stu-id="23412-126">If the work orders that you added should be done in a specific order, in the **Sort order** field, you can enter the numbers **1**, **2**, **3**, and so on, to specify that order.</span></span>

12. <span data-ttu-id="23412-127">Aby wyświetlić listę wszystkich zleceń pracy uwzględnionych w puli zleceń pracy, w okienku akcji, na karcie **Pula zleceń pracy**, w grupie **Przeglądanie powiązanej puli zleceń pracy** wybierz pozycję **Zlecenia pracy**, aby otworzyć stronę listy **Wszystkie zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-127">To view a list of all the work orders that are included in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Work orders** to open the **All work orders** list page.</span></span>

13. <span data-ttu-id="23412-128">Aby obliczyć i wyświetlić obciążenie wydajności dla harmonogramu konserwacji, niezaplanowane zlecenia pracy i zaplanowane zlecenia pracy, w okienku akcji na karcie **Pula zleceń pracy** w grupie **Przeglądanie powiązanej puli zleceń pracy** wybierz opcję **Obciążenie wydajności**, co spowoduje otwarcie okna dialogowego **Obliczanie obciążenia zdolności produkcyjnych**.</span><span class="sxs-lookup"><span data-stu-id="23412-128">To calculate and view capacity load for the maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Capacity load** to open the **Calculate capacity load** dialog.</span></span>

14. <span data-ttu-id="23412-129">Aby obliczyć i wyświetlić prognozę dla pozycji (części zamiennych i innych wymaganych pozycji), które są powiązane z harmonogramem konserwacji, niezaplanowanymi zleceniami pracy i zaplanowanymi zleceniami pracy, w okienku akcji na karcie **Pula zleceń pracy** w grupie **Przeglądanie powiązanej puli zleceń pracy** wybierz opcję **Prognoza dla pozycji**, co spowoduje otwarcie okna dialogowego **Obliczanie prognozy dla pozycji**.</span><span class="sxs-lookup"><span data-stu-id="23412-129">To calculate and view forecasts for items (spare parts and other required items) that are related to maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Item forecast** to open the **Calculate item forecast** dialog.</span></span>

15. <span data-ttu-id="23412-130">Aby wyświetlić listę zapotrzebowań na zakupy powiązanych ze wszystkimi zleceniami pracy uwzględnionmi w puli zleceń pracy, w okienku akcji na karcie **Pula zleceń pracy**, w grupie **Zaopatrzenie** wybierz pozycję **Zapotrzebowanie na zakup zlecenia pracy**, aby otworzyć stronę listy **Zapotrzebowanie na zakup zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-130">To view a list of purchase requisitions that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase requisition** to open the **Work order purchase requisition** list page.</span></span>

16. <span data-ttu-id="23412-131">Aby wyświetlić listę zamówień zakupu na zakupy powiązanych ze wszystkimi zleceniami pracy uwzględnionmi w puli zleceń pracy, w okienku akcji na karcie **Pula zleceń pracy**, w grupie **Zaopatrzenie** wybierz pozycję **Zakup zlecenia pracy**, aby otworzyć stronę listy **Zakup zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-131">To view a list of purchase orders that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase** to open the **Work order purchase** list page.</span></span>

>[!NOTE]
><span data-ttu-id="23412-132">Jeśli pula zleceń roboczych nie jest już odpowiednia dla planowania pracy, należy ustawić opcję **Aktywne** jako **Nie** na widoku listy na stronie **Pula zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-132">When a work order pool is no longer relevant to your work planning, set the **Active** option for that pool to **No** in the list view of the **Work order pool** page.</span></span>

<span data-ttu-id="23412-133">Aby usunąć wszystkie wiersze zlecenia pracownika, należy określić opcję **Usuń relacje zleceń pracy** jako wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="23412-133">To delete all worker order lines, set the **Delete work order relations** option to **Yes**.</span></span> <span data-ttu-id="23412-134">Ta opcja jest przydatna na przykład wtedy, gdy trzeba utworzyć pustą pulę, której można później użyć w przypadku innych zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-134">This option is useful if, for example, you want to create an empty pool that you can use later for other work orders.</span></span> <span data-ttu-id="23412-135">Pamiętaj, aby ustawić opcję **Usuń relacje zlecenia pracy** na wartość **Nie**, jeśli chcesz użyć puli zleceń pracy do późniejszego utworzenia nowych relacji zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-135">When you're ready to use the work order pool to create new work order relations later, remember to set the **Delete work order relations** option to **No**.</span></span>

<span data-ttu-id="23412-136">Na poniższej ilustracji przedstawiono przykład strony listy **Pula zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-136">The illustration below shows an example of the **Work order pool** list page.</span></span>

![Rysunek 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a><span data-ttu-id="23412-138">Dodaj zlecenie pracy do puli zleceń pracy</span><span class="sxs-lookup"><span data-stu-id="23412-138">Add a work order to a work order pool</span></span>

<span data-ttu-id="23412-139">Jak opisano w poprzednij sekcji, podczas tworzenia puli można dodawać zlecenia pracy do puli zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-139">As described in the previous section, you can add work orders to a work order pool when you create that pool.</span></span> <span data-ttu-id="23412-140">Można również dodawać zlecenia pracy do puli zleceń pracy na stronie listy **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-140">You can also add work orders to a work order pool on the **All work orders** or **Active work orders** list page.</span></span>

1. <span data-ttu-id="23412-141">Wybierz zlecenie pracy, a następnie w okienku akcji na karcie **Zlecenie pracy**, w grupie **Zarządzaj** wybierz pozycję **Pula zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="23412-141">Select the work order, and then, on the Action Pane, on the **Work order** tab, in the **Maintain** group, select **Work order pool**.</span></span>

2. <span data-ttu-id="23412-142">Wybierz zlecenie pracy z listy i kliknij przycisk **Pula zleceń pracy.**</span><span class="sxs-lookup"><span data-stu-id="23412-142">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="23412-143">W oknie dialogowym **Obsługa puli zleceń pracy**, w polu **Dodaj/Usuń** wybierz opcję **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="23412-143">In the **Maintain work order pool** dialog, in the **Add/remove** field, select **Add**.</span></span>

4. <span data-ttu-id="23412-144">W polu **Pula** wybierz pulę zleceń pracy.</span><span class="sxs-lookup"><span data-stu-id="23412-144">In the **Pool** field, select the work order pool.</span></span>

5. <span data-ttu-id="23412-145">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="23412-145">Select **OK**.</span></span>

6. <span data-ttu-id="23412-146">Aby umieścić zlecenie pracy dodane w określonym zleceniu w puli zleceń pracy, na stronie listy **Wszystkie pule zleceń pracy** lub **Aktywne pule zleceń pracy** wybierz pulę, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="23412-146">To put the work order that you added in a specific order in the work order pool, on the **All work order pools** or **Active work order pools** list page, select the pool, and then select **Edit**.</span></span> <span data-ttu-id="23412-147">Następnie na stronie **Pula zleceń pracy** na skróconej karcie **Zlecenia pracy** za pomocą pola **Porządek sortowania** można dostosowć kolejność sortowania zleceń pracy uwzględnionych w puli.</span><span class="sxs-lookup"><span data-stu-id="23412-147">Then, on the **Work order pool** page, on the **Work orders** FastTab, use the **Sort order** field to adjust the sort order of the work orders that are included in pool.</span></span>

<span data-ttu-id="23412-148">Jeśli chcesz usunąć wybrane zlecenie pracy z puli zleceń pracy, powtórz te kroki, ale wybierając opcję **Usuń** w kroku 3.</span><span class="sxs-lookup"><span data-stu-id="23412-148">To remove a work order from a work order pool, repeat these steps, but select **Remove** in step 3.</span></span>

