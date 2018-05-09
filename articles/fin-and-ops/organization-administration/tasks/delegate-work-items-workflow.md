--- 
title: "Delegowanie elementów pracy w przepływie pracy"
description: "Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 752c52431049093d0d9a1961d8f8bab604621f12
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="delegate-work-items-in-a-workflow"></a><span data-ttu-id="7d79e-103">Delegowanie elementów pracy w przepływie pracy</span><span class="sxs-lookup"><span data-stu-id="7d79e-103">Delegate work items in a workflow</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7d79e-104">Jeśli nie będzie Cię w pracy lub z innego powodu nie będziesz w stanie zająć się elementami pracy, możesz delegować, czyli przepisać, swoje elementy pracy do innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="7d79e-104">If you plan to be out of the office or otherwise unavailable to act on work items, you can delegate, or reassign, your work items to other users.</span></span> <span data-ttu-id="7d79e-105">Ta procedura służy do takiego konfigurowania systemu, aby automatycznie delegował Twoje elementy pracy do innego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d79e-105">This procedure helps you configure the system to automatically delegate your work items to another user.</span></span>



<span data-ttu-id="7d79e-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="7d79e-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-automatic-delegation"></a><span data-ttu-id="7d79e-107">Ustawienie automatycznej delegacji</span><span class="sxs-lookup"><span data-stu-id="7d79e-107">Set up automatic delegation</span></span>
1. <span data-ttu-id="7d79e-108">Wybierz kolejno opcje Wspólne > Ustawienia > Opcje użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d79e-108">Go to Common > Setup > User options.</span></span>
2. <span data-ttu-id="7d79e-109">Kliknij kartę Przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="7d79e-109">Click the Workflow tab.</span></span>
    * <span data-ttu-id="7d79e-110">Upewnij się, że jest rozwinięta sekcja Delegacja.</span><span class="sxs-lookup"><span data-stu-id="7d79e-110">Make sure the Delegation section is expanded.</span></span>    <span data-ttu-id="7d79e-111">Aby skonfigurować w systemie automatyczne delegowanie elementów pracy do innych użytkowników, należy utworzyć reguły delegowania, które określają, kiedy wybrane typy elementów pracy są delegowane.</span><span class="sxs-lookup"><span data-stu-id="7d79e-111">To configure the system to automatically delegate your work items to other users, you must create delegation rules, which specify when certain types of work items are delegated.</span></span> <span data-ttu-id="7d79e-112">Aby utworzyć reguły delegowania, należy wykonać poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="7d79e-112">Follow these steps to create a delegation rule.</span></span>  
3. <span data-ttu-id="7d79e-113">Kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="7d79e-113">Click Add.</span></span>
4. <span data-ttu-id="7d79e-114">W polu Zakres wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="7d79e-114">In the Scope field, select an option.</span></span>
    * <span data-ttu-id="7d79e-115">Wszystkie — umożliwia delegowanie wszystkich elementów pracy przypisanych do użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7d79e-115">All – Delegate all work items that are assigned to you.</span></span>    <span data-ttu-id="7d79e-116">Moduł — umożliwia delegowanie tylko elementów pracy związanych z określonym typem przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="7d79e-116">Module – Delegate only the work items that are related to a specific type of workflow.</span></span> <span data-ttu-id="7d79e-117">Jeśli zostanie wybrana ta opcja, należy wybrać typ przepływu pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="7d79e-117">If you select this option, you must select the type of workflow in the Name field.</span></span>    <span data-ttu-id="7d79e-118">Przepływ pracy — umożliwia delegowanie tylko elementów pracy związanych z określonym przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="7d79e-118">Workflow – Delegate only the work items that are related to a specific workflow.</span></span> <span data-ttu-id="7d79e-119">Jeśli zostanie wybrana ta opcja, należy wybrać przepływ pracy w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="7d79e-119">If you select this option, you must select the workflow in the Name field.</span></span>  
5. <span data-ttu-id="7d79e-120">W polu Delegowanie wybierz użytkownika, do którego chcesz delegować elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="7d79e-120">In the Delegate field, select the user to delegate the work items to.</span></span>
    * <span data-ttu-id="7d79e-121">W polach Data/godzina rozpoczęcia i Data/godzina zakończenia określ, kiedy elementy pracy mają być automatycznie delegowane.</span><span class="sxs-lookup"><span data-stu-id="7d79e-121">Use the Start date/time and End date/time fields to specify when you want the work items to be automatically delegated.</span></span>  
6. <span data-ttu-id="7d79e-122">W polu Data/godzina rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="7d79e-122">In the Start date/time field, enter a date and time.</span></span>
7. <span data-ttu-id="7d79e-123">W polu Data/godzina zakończenia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="7d79e-123">In the End date/time field, enter a date and time.</span></span>
8. <span data-ttu-id="7d79e-124">Aby aktywować regułę delegowania, zaznacz pole wyboru Włączone.</span><span class="sxs-lookup"><span data-stu-id="7d79e-124">Select the Enabled check box to activate the delegation rule.</span></span>
    * <span data-ttu-id="7d79e-125">Jeśli w ustawieniu Zakres zaznaczysz wartość Moduł, należy wybrać moduł w polu Nazwa.</span><span class="sxs-lookup"><span data-stu-id="7d79e-125">If you selected Module as the Scope, then you must select the module in the Name field.</span></span>    <span data-ttu-id="7d79e-126">Jeśli w ustawieniu Zakres zaznaczysz wartość Przepływ pracy, w polu Nazwa należy wybrać konkretny przepływ pracy, który ma być delegowany.</span><span class="sxs-lookup"><span data-stu-id="7d79e-126">If you selected Workflow as the Scope, then you must select the specific workflow to delegate in the Name field.</span></span>  
9. <span data-ttu-id="7d79e-127">W polu Komentarz wprowadź komentarz wyjaśniający, dlaczego delegujesz elementy pracy.</span><span class="sxs-lookup"><span data-stu-id="7d79e-127">In the Comment field, enter a comment that explains why you are delegating the work items.</span></span>


