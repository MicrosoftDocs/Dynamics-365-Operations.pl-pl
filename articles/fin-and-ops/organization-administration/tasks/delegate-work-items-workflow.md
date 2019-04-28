---
title: Delegowanie elementów pracy w przepływie pracy
description: Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników.
author: jasongre
manager: AnnBe
ms.date: 04/09/2019
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
ms.openlocfilehash: feace647d7acef6abf86b13fcb8019c622c55ff6
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/12/2019
ms.locfileid: "976788"
---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="2e8d3-103">Delegowanie pozycji pracy w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="2e8d3-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

## <a name="manually-delegate-a-work-item"></a><span data-ttu-id="2e8d3-104">Ręczne delegowanie elementu pracy</span><span class="sxs-lookup"><span data-stu-id="2e8d3-104">Manually delegate a work item</span></span>

<span data-ttu-id="2e8d3-105">Aby delegować pojedynczy element pracy, zaznacz opcję **Delegowanie** w menu **przepływu pracy**, a następnie wprowadź użytkownika, który ma być delegowany, wraz z komentarzem.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-105">To delegate an individual work item, select the **Delegate** option in the **Workflow** menu and then enter the user to be delegated to along with a comment.</span></span> <span data-ttu-id="2e8d3-106">To spowoduje ponowne przypisanie elementu pracy do tego użytkownika, umożliwiającego mu wykonywanie go.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-106">This will reassign the work item to that user so they can complete it.</span></span>

## <a name="automatically-delegate-work-items"></a><span data-ttu-id="2e8d3-107">Automatyczne delegowanie elementów pracy</span><span class="sxs-lookup"><span data-stu-id="2e8d3-107">Automatically delegate work items</span></span>

<span data-ttu-id="2e8d3-108">Jeśli zamierzasz być poza biurem lub nie będziesz mieć możliwości wykonywania elementów pracy przez jakiś czas, możesz automatycznie delegować nowe elementy pracy innym użytkownikom na stronie **opcje użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-108">If you plan to be out of the office or otherwise unavailable to act on work items for a period of time, you can automatically delegate new work items to other users using the **User options** page.</span></span>

### <a name="set-up-automatic-delegation"></a><span data-ttu-id="2e8d3-109">Ustawienie automatycznej delegacji</span><span class="sxs-lookup"><span data-stu-id="2e8d3-109">Set up automatic delegation</span></span>
1. <span data-ttu-id="2e8d3-110">Wybierz kolejno opcje Wspólne > Ustawienia > Opcje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-110">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="2e8d3-111">Kliknij kartę Przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-111">Click the Workflow tab.</span></span>
    * <span data-ttu-id="2e8d3-112">Upewnij się, że jest rozwinięta sekcja Delegacja.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-112">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="2e8d3-113">Aby skonfigurować w systemie automatyczne delegowanie elementów pracy do innych użytkowników, należy utworzyć reguły delegowania, które określają, kiedy wybrane typy elementów pracy są delegowane.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-113">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="2e8d3-114">Aby utworzyć reguły delegowania, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-114">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="2e8d3-115">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-115">Click Add.</span></span>
4. <span data-ttu-id="2e8d3-116">W polu Zakres wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-116">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="2e8d3-117">Wszystkie — umożliwia delegowanie wszystkich elementów pracy przypisanych do użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-117">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="2e8d3-118">Moduł — umożliwia delegowanie tylko elementów pracy związanych z określonym typem przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-118">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="2e8d3-119">Jeśli zostanie wybrana ta opcja, należy wybrać typ przepływu pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-119">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="2e8d3-120">Przepływ pracy — umożliwia delegowanie tylko elementów pracy związanych z określonym przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-120">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="2e8d3-121">Jeśli zostanie wybrana ta opcja, należy wybrać przepływ pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-121">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="2e8d3-122">W polu Delegowanie wybierz użytkownika, do którego chcesz delegować elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-122">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="2e8d3-123">W polach Data/godzina rozpoczęcia i Data/godzina zakończenia określ, kiedy elementy pracy mają być automatycznie delegowane.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-123">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="2e8d3-124">W polu Data/godzina rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-124">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="2e8d3-125">W polu Data/godzina zakończenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-125">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="2e8d3-126">Aby aktywować regułę delegowania, zaznacz pole wyboru Włączone.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-126">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="2e8d3-127">Jeśli w ustawieniu Zakres zaznaczysz wartość Moduł, należy wybrać moduł w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-127">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="2e8d3-128">Jeśli w ustawieniu Zakres zaznaczysz wartość Przepływ pracy, w polu Nazwa należy wybrać konkretny przepływ pracy, który ma być delegowany.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-128">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="2e8d3-129">W polu Komentarz wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="2e8d3-129">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>

