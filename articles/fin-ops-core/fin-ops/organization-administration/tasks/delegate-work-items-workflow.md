---
title: Delegowanie elementów pracy w przepływie pracy
description: Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 44dc747543e32b54729d12c89a401b0187e25a61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189966"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="e7344-103">Delegowanie pozycji pracy w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="e7344-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="e7344-104">Ręczne delegowanie elementu pracy</span><span class="sxs-lookup"><span data-stu-id="e7344-104">Manually delegate a work item</span></span>

<span data-ttu-id="e7344-105">Aby delegować pojedynczy element pracy, zaznacz opcję **Delegowanie** w menu **przepływu pracy**, a następnie wprowadź użytkownika, który ma być delegowany, wraz z komentarzem.</span><span class="sxs-lookup"><span data-stu-id="e7344-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="e7344-106">To spowoduje ponowne przypisanie elementu pracy do tego użytkownika, umożliwiającego mu wykonywanie go.</span><span class="sxs-lookup"><span data-stu-id="e7344-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="e7344-107">Automatyczne delegowanie elementów pracy</span><span class="sxs-lookup"><span data-stu-id="e7344-107">Automatically delegate work items</span></span>

<span data-ttu-id="e7344-108">Jeśli zamierzasz być poza biurem lub nie będziesz mieć możliwości wykonywania elementów pracy przez jakiś czas, możesz automatycznie delegować nowe elementy pracy innym użytkownikom na stronie **opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="e7344-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="e7344-109">Ustawienie automatycznej delegacji</span><span class="sxs-lookup"><span data-stu-id="e7344-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="e7344-110">Wybierz kolejno opcje **Wspólne > Ustawienia > Opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="e7344-110">Go to **Common > Setup > User options**.</span></span>
2. <span data-ttu-id="e7344-111">Kliknij kartę **Przepływ pracy**. Upewnij się, że sekcja Delegacja została rozwinięta.</span><span class="sxs-lookup"><span data-stu-id="e7344-111">Click the **Workflow** tab. Make sure the Delegation section is expanded.</span></span> <span data-ttu-id="e7344-112">Aby skonfigurować w systemie automatyczne delegowanie elementów pracy do innych użytkowników, należy utworzyć reguły delegowania, które określają, kiedy wybrane typy elementów pracy są delegowane.</span><span class="sxs-lookup"><span data-stu-id="e7344-112">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="e7344-113">Aby utworzyć reguły delegowania, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="e7344-113">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="e7344-114">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="e7344-114">Click **Add**.</span></span>
4. <span data-ttu-id="e7344-115">W polu **Zakres** wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="e7344-115">In the **Scope** field, select an option.</span></span>
    - <span data-ttu-id="e7344-116">Wszystkie — umożliwia delegowanie wszystkich elementów pracy przypisanych do użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e7344-116">All – Delegate all work items that are assigned to you.</span></span>
    - <span data-ttu-id="e7344-117">Moduł — umożliwia delegowanie tylko elementów pracy związanych z określonym typem przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="e7344-117">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="e7344-118">Jeśli zostanie wybrana ta opcja, należy wybrać typ przepływu pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="e7344-118">If you select this option, you must select the type of workflow in the Name field.</span></span>
    - <span data-ttu-id="e7344-119">Przepływ pracy — umożliwia delegowanie tylko elementów pracy związanych z określonym przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="e7344-119">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="e7344-120">Jeśli zostanie wybrana ta opcja, należy wybrać przepływ pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="e7344-120">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="e7344-121">W polu **Delegacja** wybierz użytkownika, do którego chcesz delegować elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="e7344-121">In the **Delegate** field, select the user to delegate the work items to.</span></span> <span data-ttu-id="e7344-122">W polach Data/godzina rozpoczęcia i Data/godzina zakończenia określ, kiedy elementy pracy mają być automatycznie delegowane.</span><span class="sxs-lookup"><span data-stu-id="e7344-122">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="e7344-123">W polu **Data/godzina rozpoczęcia** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="e7344-123">In the **Start date/time** field, enter a date and time.</span></span>
7. <span data-ttu-id="e7344-124">W polu **Data/godzina zakończenia** wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="e7344-124">In the **End date/time** field, enter a date and time.</span></span>
8. <span data-ttu-id="e7344-125">Aby aktywować regułę delegowania, zaznacz pole wyboru **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="e7344-125">Select the **Enabled** check box to activate the delegation rule.</span></span> <span data-ttu-id="e7344-126">Jeśli w ustawieniu Zakres zaznaczysz wartość **Moduł**, należy wybrać moduł w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="e7344-126">If you selected **Module** as the Scope, then you must select the module in the Name field.</span></span> <span data-ttu-id="e7344-127">Jeśli w ustawieniu Zakres zaznaczysz wartość **Przepływ pracy**, w polu Nazwa należy wybrać konkretny przepływ pracy, który ma być delegowany.</span><span class="sxs-lookup"><span data-stu-id="e7344-127">If you selected **Workflow** as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="e7344-128">W polu **Komentarz** wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="e7344-128">In the **Comment** field, enter a comment that explains why you are delegating the work items.</span></span>

