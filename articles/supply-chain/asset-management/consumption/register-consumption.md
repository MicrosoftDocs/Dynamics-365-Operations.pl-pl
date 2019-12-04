---
title: Rejestracja zużycia
description: W tym temacie wyjaśniono, jak utworzyć rejestracje zużycia w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3d23375ec7ebe9b43c2d2e3e376e26c348131bd3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812267"
---
# <a name="register-consumption"></a><span data-ttu-id="d7690-103">Rejestracja zużycia</span><span class="sxs-lookup"><span data-stu-id="d7690-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="d7690-104">Po wykonaniu zadania konserwacji w zleceniu produkcyjnym następnym krokiem jest dokonanie rejestracji zużycia i zaksięgowanie arkuszy.</span><span class="sxs-lookup"><span data-stu-id="d7690-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="d7690-105">Rejestracje można przeprowadzać na następujących typach zużycia: godziny, towary i wydatki.</span><span class="sxs-lookup"><span data-stu-id="d7690-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="d7690-106">Różne typy zużycia są rejestrowane i księgowane na stronie **arkusze zleceń pracy**.</span><span class="sxs-lookup"><span data-stu-id="d7690-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="d7690-107">Ustawienia arkusza w module **zarządzanie składnikami majątku** służą do tworzenia i księgowania oddzielnych arkuszy godzin, towarów i wydatków w module **Zarządzanie projektami i ich księgowanie** .</span><span class="sxs-lookup"><span data-stu-id="d7690-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="d7690-108">W niektórych przypadkach istnieje możliwość dodawania lub usuwania wierszy prognozy w zleceniu pracy.</span><span class="sxs-lookup"><span data-stu-id="d7690-108">In some cases, you may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="d7690-109">Konfiguracja stanu cyklu życia zlecenia pracy, powiązanego typu projektu oraz reguł etapów związanych z typem projektu określa, czy można dodawać lub edytować wiersze arkuszy.</span><span class="sxs-lookup"><span data-stu-id="d7690-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="d7690-110">Aby uzyskać więcej informacji na temat stanów cyklu życia zlecenia pracy i etapów projektu należy zapoznać się z [Prognozy, zlecenia pracy i projekty](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="d7690-110">Read more about work order lifecycle states and related project stages in [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="d7690-111">Istnieje możliwość skonfigurowania automatycznego księgowania arkuszy w stanie cyklu życia zamówienia pracy.</span><span class="sxs-lookup"><span data-stu-id="d7690-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="d7690-112">Więcej informacji [Stany cyklu życia zlecenia pracy](../setup-for-work-orders/work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="d7690-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="d7690-113">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="d7690-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="d7690-114">Wybierz zlecenie pracy z listy i kliknij przycisk **Arkusze**.</span><span class="sxs-lookup"><span data-stu-id="d7690-114">Select the work order, and click **Journals**.</span></span>

3. <span data-ttu-id="d7690-115">Kliknij przycisk **Kopiuj z prognozy**, aby przenieść wiersze prognozy, które mogą być połączone ze zleceniem produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="d7690-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="d7690-116">Można wybrać typy zużycia, które mają zostać przeniesione.</span><span class="sxs-lookup"><span data-stu-id="d7690-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="d7690-117">W razie potrzeby można dodać więcej wierszy zużycia na odpowiednim skróconej karcie, klikając przycisk **Dodaj wiersz** i wypełniając dane w wierszu.</span><span class="sxs-lookup"><span data-stu-id="d7690-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="d7690-118">Kliknij przycisk **Sprawdź poprawność arkuszy,** aby sprawdzić poprawność wierszy arkusza przed zaksięgowaniem</span><span class="sxs-lookup"><span data-stu-id="d7690-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="d7690-119">Kliknij przycisk **Księguj arkusze**, aby zaksięgować wiersze arkusza lub arkusz.</span><span class="sxs-lookup"><span data-stu-id="d7690-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="d7690-120">Po zaksięgowaniu arkuszy zużycia można zaktualizować stan cyklu życia zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d7690-120">After you've posted the consumption journals, you can update the work order lifecycle state.</span></span> <span data-ttu-id="d7690-121">Na przykład, aby wskazać, że zlecenie pracy zostało zrealizowane, można zaktualizować stan cyklu eksploatacji na „zakończone”.</span><span class="sxs-lookup"><span data-stu-id="d7690-121">For example, to indicate that the work order has been completed, you can update the lifecycle state to "Ended".</span></span>

    - <span data-ttu-id="d7690-122">W polu **Pokaż** umieszczonym u góry strony **Arkusze zleceń pracy** wybierz wiersze arkusza, które mają być wyświetlane: **wszystkie**, **niezaksięgowane** lub **zaksięgowane**.</span><span class="sxs-lookup"><span data-stu-id="d7690-122">In the **Show** field at the top of the **Work order journals** page, select which journal lines you want to see: **All**, **Not posted**, or **Posted**.</span></span> <span data-ttu-id="d7690-123">W zaksięgowanych arkuszach zaznaczone jest pole wyboru **zaksięgowane**.</span><span class="sxs-lookup"><span data-stu-id="d7690-123">Posted journals have a check mark in the **Posted** check box.</span></span>  
    - <span data-ttu-id="d7690-124">Jeśli w arkuszu zlecenia produkcyjnego są tworzone wiersze towarów, wymiary produktu i wymiary śledzenia związane z towarem są automatycznie przenoszone do wiersza arkusza.</span><span class="sxs-lookup"><span data-stu-id="d7690-124">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="d7690-125">Poniższy zrzut ekranu przedstawia przykład rejestracji godzin i towarów w zleceniu produkcyjnym w **arkuszach zleceń roboczych.**</span><span class="sxs-lookup"><span data-stu-id="d7690-125">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![Rysunek 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="d7690-127">Dzielenie godzin na zleceniach roboczych z kilkoma zadaniami zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="d7690-127">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="d7690-128">Jeśli zlecenie produkcyjne zawiera kilka zadań zlecenia, można zarejestrować godziny pracy za pomocą funkcji **Podziel godziny**, co oznacza, że jeden wiersz rejestracji może być dystrybuowany równomiernie w każdym zleceniu produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="d7690-128">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="d7690-129">Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy** lub **Aktywne zlecenia pracy**.</span><span class="sxs-lookup"><span data-stu-id="d7690-129">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="d7690-130">Wybierz zlecenie pracy z listy i kliknij przycisk **Arkusze**.</span><span class="sxs-lookup"><span data-stu-id="d7690-130">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="d7690-131">Wybierz wiersz rejestracji godzin, który chcesz podzielić, i kliknij przycisk **Podziel godziny**.</span><span class="sxs-lookup"><span data-stu-id="d7690-131">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="d7690-132">W oknie dialogowym **zadania konserwacji dotyczącego podziału godzin w zleceniu pracy** nazwa zalogowanego pracownika jest automatycznie wyświetlana w polu **pracownik**.</span><span class="sxs-lookup"><span data-stu-id="d7690-132">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="d7690-133">W razie potrzeby można wybrać innego pracownika.</span><span class="sxs-lookup"><span data-stu-id="d7690-133">If required, you can select another worker.</span></span>

5. <span data-ttu-id="d7690-134">Wybierz kategorię rejestracji godzin w polu **Kategoria**.</span><span class="sxs-lookup"><span data-stu-id="d7690-134">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="d7690-135">Umożliwia wstawienie liczby godzin pracy do podziału w polu **Godziny**.</span><span class="sxs-lookup"><span data-stu-id="d7690-135">Insert number of work hours to be split in the **Hours** field.</span></span>

    ![Rysunek 2](media/02-consumption.png)

7. <span data-ttu-id="d7690-137">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7690-137">Click **OK**.</span></span>

<span data-ttu-id="d7690-138">*Przykład:* w poniższym zrzutie ekranu są wyświetlane wiersze arkusza dla zlecenia produkcyjnego zawierającego trzy zadania zlecenia roboczego.</span><span class="sxs-lookup"><span data-stu-id="d7690-138">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="d7690-139">Pierwszy wiersz, zawierający trzy godziny pracy, został podzielony, a jedna godzina robocza jest rejestrowana w każdym zadaniu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d7690-139">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="d7690-140">Po utworzeniu trzech wierszy rejestracji godzin należy zdecydować, co zrobić z oryginalnym wierszem rejestracji godzinowej (pierwszy wiersz w przykładzie).</span><span class="sxs-lookup"><span data-stu-id="d7690-140">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="d7690-141">Można ją zachować w stanie lub usunąć.</span><span class="sxs-lookup"><span data-stu-id="d7690-141">You can keep it as is or delete it.</span></span> 

![Rysunek 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="d7690-143">Wymiary finansowe w rejestracjach zużycia</span><span class="sxs-lookup"><span data-stu-id="d7690-143">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="d7690-144">Podczas rejestracji zużycia wymiary finansowe powiązane z różnymi typami rejestracji są dodawane do rejestracji w wybranej kolejności.</span><span class="sxs-lookup"><span data-stu-id="d7690-144">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

- <span data-ttu-id="d7690-145">*Rejestracje godzin i wydatków:* najpierw są dodawane wymiary finansowe z nagłówka arkusza, jeśli takie istnieją.</span><span class="sxs-lookup"><span data-stu-id="d7690-145">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="d7690-146">Następnie są dodawane wymiary finansowe z powiązanego projektu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d7690-146">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="d7690-147">Na koniec dodawane są wymiary finansowe od zasobu (pracownika).</span><span class="sxs-lookup"><span data-stu-id="d7690-147">Finally, financial dimensions from the resource (worker) are added.</span></span>

- <span data-ttu-id="d7690-148">*Rejestracje towarów:* najpierw są dodawane wymiary finansowe z nagłówka arkusza, jeśli takie istnieją.</span><span class="sxs-lookup"><span data-stu-id="d7690-148">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="d7690-149">Następnie, są dodawane wymiary finansowe z powiązanego projektu zlecenia pracy.</span><span class="sxs-lookup"><span data-stu-id="d7690-149">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="d7690-150">Następnie zostaną dodane wymiary finansowe z oddziału.</span><span class="sxs-lookup"><span data-stu-id="d7690-150">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="d7690-151">Na koniec dodawane są wymiary finansowe od towaru.</span><span class="sxs-lookup"><span data-stu-id="d7690-151">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="d7690-152">Dla wszystkich trzech typów rejestracji kombinacja wymiarów finansowych jest sprawdzana, a niewłaściwe kombinacje są puste.</span><span class="sxs-lookup"><span data-stu-id="d7690-152">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="d7690-153">Jest to standardowa konfiguracja z innymi aplikacjami Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d7690-153">This is standard setup with other Finance and Operations apps.</span></span>

