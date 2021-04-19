---
title: Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS
description: W tym temacie opisano sposób synchronizowania zarządzania zadaniami między punktami sprzedaży Microsoft Teams i Dynamics 365 Commerce (POS).
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ca0cb32ac3ee508ddcd5346a895fb9904fa92517
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842727"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a><span data-ttu-id="bc140-103">Synchronizowanie zarządzania zadaniami między punktami sprzedaży usług Microsoft Teams i Dynamics 365 Commerce POS</span><span class="sxs-lookup"><span data-stu-id="bc140-103">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="bc140-104">W tym temacie opisano sposób synchronizowania zarządzania zadaniami między punktami sprzedaży Microsoft Teams i Dynamics 365 Commerce (POS).</span><span class="sxs-lookup"><span data-stu-id="bc140-104">This topic describes how to synchronize task management between Microsoft Teams and Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="bc140-105">Jednym z głównych celów integracji zespołów jest włączenie synchronizacji zarządzania zadaniami między aplikacją POS a Teams.</span><span class="sxs-lookup"><span data-stu-id="bc140-105">One of the main purposes of Teams integration is to enable the synchronization of task management between the POS application and Teams.</span></span> <span data-ttu-id="bc140-106">W ten sposób pracownicy sklepu mogą używać aplikacji pos lub Teams do zarządzania zadaniami i nie muszą przełączać aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bc140-106">In this way, store employees can use either the POS application or Teams to manage tasks, and don't have to switch applications.</span></span>

<span data-ttu-id="bc140-107">Ponieważ planowanie jest używane jako repozytorium zadań w Teams, między zespołami musi być połączenie Teams z Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc140-107">Because Planner is used as a repository for tasks in Teams, there must be a link between Teams and Dynamics 365 Commerce.</span></span> <span data-ttu-id="bc140-108">To łącze jest ustanowione przy użyciu określonego identyfikatora planu dla danego zespołu sklepu.</span><span class="sxs-lookup"><span data-stu-id="bc140-108">This link is established by using a specific plan ID for a given store team.</span></span>

<span data-ttu-id="bc140-109">W poniższych procedurach popisano sposób skonfigurowania synchronizacji zarządzania zadaniami między aplikacją POS i Teams.</span><span class="sxs-lookup"><span data-stu-id="bc140-109">The following procedures show how to set up task management synchronization between the POS and Teams applications.</span></span>

## <a name="publish-a-test-task-list-in-teams"></a><span data-ttu-id="bc140-110">Publikowanie listy zadań testowych w Teams</span><span class="sxs-lookup"><span data-stu-id="bc140-110">Publish a test task list in Teams</span></span>

<span data-ttu-id="bc140-111">W poniższej procedurze założono, że zespoły sklepów po raz pierwszy korzysta z integracji zarządzania zadaniami Microsoft Teams z usługami Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc140-111">The following procedure assumes that your store teams are using Microsoft Teams task management integration with Commerce for the first time.</span></span>

<span data-ttu-id="bc140-112">Aby opublikować listę zadań testowych w Teams, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bc140-112">To publish a test task list in Teams, follow these steps.</span></span>

1. <span data-ttu-id="bc140-113">Zaloguj się do Teams jako kierownik ds. komunikacji.</span><span class="sxs-lookup"><span data-stu-id="bc140-113">Sign in to Teams as a communications manager.</span></span> <span data-ttu-id="bc140-114">Zazwyczaj kierownicy ds. komunikacji są użytkownikami, którzy mają rolę **Menedżer regionalny** w portalu Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc140-114">Typically, communications managers are users who have the **Regional manager** role in Commerce.</span></span>
1. <span data-ttu-id="bc140-115">W lewym okienku nawigacji wybierz pozycję **Zadania według programu Planner**.</span><span class="sxs-lookup"><span data-stu-id="bc140-115">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="bc140-116">Na karcie **Listy opublikowane** wybierz pozycję **Nowa lista** w lewym dolnym rogu i nadaj nazwę nowej liście **Lista zadań testowych**.</span><span class="sxs-lookup"><span data-stu-id="bc140-116">On the **Published lists** tab, select **New list** in the lower left, and name the new list **Test task list**.</span></span>
1. <span data-ttu-id="bc140-117">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="bc140-117">Select **Create**.</span></span> <span data-ttu-id="bc140-118">Nowa lista jest wyświetlana w obszarze **Wersje robocze**.</span><span class="sxs-lookup"><span data-stu-id="bc140-118">The new list appears under **Drafts**.</span></span>
1. <span data-ttu-id="bc140-119">W obszarze **Tytuł zadania** nadaj pierwsze zadanie tytuł **Testowania integracji Teams**.</span><span class="sxs-lookup"><span data-stu-id="bc140-119">Under **Task title**, give the first task the title **Testing Teams integration**.</span></span> <span data-ttu-id="bc140-120">Następnie wybierz opcję **Wprowadź**.</span><span class="sxs-lookup"><span data-stu-id="bc140-120">Then select **Enter**.</span></span>
1. <span data-ttu-id="bc140-121">Z listy **Wersji roboczych** wybierz listę zadań.</span><span class="sxs-lookup"><span data-stu-id="bc140-121">In the **Drafts** list, select the task list.</span></span> <span data-ttu-id="bc140-122">Następnie wybierz pozycję **Publikuj** w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="bc140-122">Then select **Publish** in the upper-right corner.</span></span>
1. <span data-ttu-id="bc140-123">W oknie dialogowym **Wybierz osoby, które mają zostać publikowane**, wybierz zespoły, które mają otrzymać listę zadań testowych.</span><span class="sxs-lookup"><span data-stu-id="bc140-123">In the **Select who to publish to** dialog box, select the teams that should receive the test task list.</span></span>
1. <span data-ttu-id="bc140-124">Wybierz **przycisk Dalej**, aby przejrzeć plan publikacji.</span><span class="sxs-lookup"><span data-stu-id="bc140-124">Select **Next** to review your publication plan.</span></span> <span data-ttu-id="bc140-125">Jeśli musisz wprowadzić zmiany, wybierz pozycję  **Wstecz**.</span><span class="sxs-lookup"><span data-stu-id="bc140-125">If you must make changes, select **Back**.</span></span> 
1. <span data-ttu-id="bc140-126">Wybierz **pozycję Potwierdź**, aby kontynuować, a następnie wybierz pozycję **Publikuj**.</span><span class="sxs-lookup"><span data-stu-id="bc140-126">Select **Confirm to proceed**, and then select **Publish**.</span></span>
1. <span data-ttu-id="bc140-127">Po zakończeniu publikowania u góry karty **Listy opublikowane** zostanie wyświetlony komunikat informujący, czy lista zadań została pomyślnie dostarczona.</span><span class="sxs-lookup"><span data-stu-id="bc140-127">After publishing is completed, a message at the top of the **Published lists** tab indicates whether your task list was successfully delivered.</span></span>

<span data-ttu-id="bc140-128">Aby uzyskać więcej informacji, zobacz [Publikowanie list zadań w celu utworzenia i śledzenia pracy w organizacji](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span><span class="sxs-lookup"><span data-stu-id="bc140-128">For more information, see [Publish task lists to create and track work in your organization](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span></span>

## <a name="link-pos-and-teams-for-task-management"></a><span data-ttu-id="bc140-129">Połącz POS z Teams w celu zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="bc140-129">Link POS and Teams for task management</span></span>

<span data-ttu-id="bc140-130">Aby połączyć aplikacje POS z Microsoft Teams do zarządzania zadaniami w programie Commerce Headquarters, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="bc140-130">To link the POS and Microsoft Teams applications for task management in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="bc140-131">Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Itnegracja zadań z Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="bc140-131">Go to **Retail and Commerce \> Task management \> Tasks integration with Microsoft Teams**.</span></span>
1. <span data-ttu-id="bc140-132">W okienku akcji wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="bc140-132">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="bc140-133">Zmień ustawienie opcji **Włącz integrację zarządzania zadaniami** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="bc140-133">Set the **Enable Task Management Integration** option to **Yes**.</span></span>
1. <span data-ttu-id="bc140-134">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="bc140-134">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="bc140-135">W okienku akcji wybierz **Konfiguracja zarządzania zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="bc140-135">On the Action Pane, select **Setup task management**.</span></span> <span data-ttu-id="bc140-136">Należy otrzymać powiadomienie informujące o utworzeniu zadania wsadowego o nazwie **Tworzenie Teams**.</span><span class="sxs-lookup"><span data-stu-id="bc140-136">You should receive a notification that indicates that a batch job that is named **Teams provision** is being created.</span></span>
1. <span data-ttu-id="bc140-137">Przejdź do **Administracja systemu \> Zapytania \> Zadania wsadowe** i znajdź ostatnie zadanie z opisem Inicjowanie **Obsługa Teams**.</span><span class="sxs-lookup"><span data-stu-id="bc140-137">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="bc140-138">Czekaj, aż to zadanie zakończy się.</span><span class="sxs-lookup"><span data-stu-id="bc140-138">Wait until this job has finished running.</span></span>
1. <span data-ttu-id="bc140-139">Uruchom zadanie **1070 usługi CDX**, aby opublikować identyfikator planu i odwołania do sklepu w programie Retail Server.</span><span class="sxs-lookup"><span data-stu-id="bc140-139">Run the **CDX job 1070** to publish the plan ID and store references to Retail Server.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bc140-140">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="bc140-140">Additional resources</span></span>

[<span data-ttu-id="bc140-141">Omówienie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc140-141">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="bc140-142">Włączanie integracji Dynamics 365 Commerce i Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc140-142">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="bc140-143">Obsługa Microsoft Teams z Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="bc140-143">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="bc140-144">Zarządzanie rolami użytkowników w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc140-144">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="bc140-145">Mapowanie sklepów i zespołów w przypadku, gdy istnieją już inne zespoły w usłudze Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bc140-145">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="bc140-146">Integracja z usługami Dynamics 365 Commerce i Microsoft Teams - FAQ</span><span class="sxs-lookup"><span data-stu-id="bc140-146">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
