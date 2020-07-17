---
title: Delegowanie elementów pracy w przepływie pracy
description: Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników.
author: ChrisGarty
manager: AnnBe
ms.date: 06/23/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d98d84b89f1f3322a9c896b74b63a3b6425b13b
ms.sourcegitcommit: 267864eb0dccd6e26d49d280bd4ad1b770a73a77
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "3515771"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="ca0ef-103">Delegowanie pozycji pracy w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="ca0ef-103">Delegate work items in a workflow</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="ca0ef-104">Ręczne delegowanie elementu pracy</span><span class="sxs-lookup"><span data-stu-id="ca0ef-104">Manually delegate a work item</span></span>

<span data-ttu-id="ca0ef-105">Aby delegować pojedynczy element pracy, zaznacz opcję **Delegowanie** w menu **przepływu pracy**, a następnie wprowadź użytkownika, który ma być delegowany, wraz z komentarzem.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="ca0ef-106">To spowoduje ponowne przypisanie elementu pracy do tego użytkownika, umożliwiającego mu wykonywanie go.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="manually-delegate-multiple-work-items"></a><span data-ttu-id="ca0ef-107">Ręczne delegowanie wielu elementów roboczych</span><span class="sxs-lookup"><span data-stu-id="ca0ef-107">Manually delegate multiple work items</span></span>

<span data-ttu-id="ca0ef-108">Wiele elementów roboczych można delegować razem z poziomu strony **Przypisane do mnie elementy robocze**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-108">Multiple work items can be delegated together from the **Work items assigned to me** page.</span></span> <span data-ttu-id="ca0ef-109">Następujące typy przepływów pracy kwalifikują się do delegacji grupowej: przepływ pracy zatwierdzania umowy zakupu, przepływ pracy zamówienia zakupu, przegląd zapotrzebowania na zakup i przepływ pracy faktury od dostawcy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-109">The following workflow types are eligible for mass delegation: Purchase agreement approval workflow, Purchase order workflow, Purchase requisition review, and Vendor invoice workflow.</span></span> <span data-ttu-id="ca0ef-110">Funkcja **Delegowania wielu elementów roboczych** jest domyślnie wyłączona i można ją włączyć w menu **Obszary robocze > Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-110">The **Delegate multiple work items** feature is disabled by default and can be enabled in **Workspaces > Feature management**.</span></span> <span data-ttu-id="ca0ef-111">Aby uzyskać pomoc we włączaniu tej funkcji, skontaktuj się z administratorem systemu.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-111">Contact your system administrator for help with enabling this feature.</span></span>
1.  <span data-ttu-id="ca0ef-112">Przejdź do **Typowe > Typowe > Elementy pracy > Elementy pracy przypisane do mnie**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-112">Go to **Common > Common > Work items > Work items assigned to me**.</span></span>
2.  <span data-ttu-id="ca0ef-113">Wybierz elementy pracy, które będą delegowane.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-113">Select the work items that will be delegated.</span></span>
3.  <span data-ttu-id="ca0ef-114">Kliknij menu **Delegowanie elementów roboczych**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-114">Click the **Delegate work items** menu.</span></span>
4.  <span data-ttu-id="ca0ef-115">W polu **Użytkownik** wybierz użytkownika, do którego chcesz delegować elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-115">In the **User** field, select the user to delegate the work items to.</span></span>
5.  <span data-ttu-id="ca0ef-116">W polu **Komentarz** wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-116">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>
6.  <span data-ttu-id="ca0ef-117">Kliknij przycisk **Deleguj elementy pracy**, aby zakończyć delegację elementu pracy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-117">Click the **Delegate work items** button to complete the work item delegation.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="ca0ef-118">Automatyczne delegowanie elementów pracy</span><span class="sxs-lookup"><span data-stu-id="ca0ef-118">Automatically delegate work items</span></span>

<span data-ttu-id="ca0ef-119">Jeśli zamierzasz być poza biurem lub nie będziesz mieć możliwości wykonywania elementów pracy przez jakiś czas, możesz automatycznie delegować nowe elementy pracy innym użytkownikom na stronie **opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-119">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="ca0ef-120">Ustawienie automatycznej delegacji</span><span class="sxs-lookup"><span data-stu-id="ca0ef-120">Set up automatic delegation</span></span>
1. <span data-ttu-id="ca0ef-121">Wybierz kolejno opcje **Wspólne > Ustawienia > Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-121">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="ca0ef-122">Kliknij kartę **Przepływ pracy**. Upewnij się, że sekcja Delegacja została rozwinięta.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-122">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="ca0ef-123">Aby skonfigurować w systemie automatyczne delegowanie elementów pracy do innych użytkowników, należy utworzyć reguły delegowania, które określają, kiedy wybrane typy elementów pracy są delegowane.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-123">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="ca0ef-124">Aby utworzyć reguły delegowania, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-124">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="ca0ef-125">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-125">Click **Add**.</span></span>
4. <span data-ttu-id="ca0ef-126">W polu **Zakres** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-126">In the **Scope** field, select an option.</span></span>
    - <span data-ttu-id="ca0ef-127">Wszystkie — umożliwia delegowanie wszystkich elementów pracy przypisanych do użytkownika.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-127">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="ca0ef-128">Moduł — umożliwia delegowanie tylko elementów pracy związanych z określonym typem przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-128">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="ca0ef-129">Jeśli zostanie wybrana ta opcja, należy wybrać typ przepływu pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-129">If you select this option, you must select the type of workflow in the Name field.</span></span>
    - <span data-ttu-id="ca0ef-130">Przepływ pracy — umożliwia delegowanie tylko elementów pracy związanych z określonym przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-130">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="ca0ef-131">Jeśli zostanie wybrana ta opcja, należy wybrać przepływ pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-131">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="ca0ef-132">W polu **Delegacja** wybierz użytkownika, do którego chcesz delegować elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-132">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="ca0ef-133">W polach Data/godzina rozpoczęcia i Data/godzina zakończenia określ, kiedy elementy pracy mają być automatycznie delegowane.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-133">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="ca0ef-134">W polu **Data/godzina rozpoczęcia** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-134">In the **Start date/time** field, enter a date and time.</span></span>
7. <span data-ttu-id="ca0ef-135">W polu **Data/godzina zakończenia** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-135">In the **End date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="ca0ef-136">Aby aktywować regułę delegowania, zaznacz pole wyboru **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-136">Select the **Enabled** check box to activate the delegation rule.</span></span> <span data-ttu-id="ca0ef-137">Jeśli w ustawieniu Zakres zaznaczysz wartość **Moduł**, należy wybrać moduł w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-137">If you selected **Module** as the Scope, then you must select the module in the Name field.</span></span> <span data-ttu-id="ca0ef-138">Jeśli w ustawieniu Zakres zaznaczysz wartość **Przepływ pracy**, w polu Nazwa należy wybrać konkretny przepływ pracy, który ma być delegowany.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-138">If you selected **Workflow** as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="ca0ef-139">W polu **Komentarz** wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="ca0ef-139">In the **Comment** field, enter a comment that explains why you're delegating the work items.</span></span>

