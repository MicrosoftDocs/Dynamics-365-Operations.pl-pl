---
title: Tworzenie list zadań i dodawanie zadań
description: W tym temacie opisano, jak tworzyć listy zadań i dodawać do nich zadania w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cca5e0efd6516d02c372e8a616b6bb0c39f3088c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006217"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="6cea5-103">Tworzenie list zadań i dodawanie zadań</span><span class="sxs-lookup"><span data-stu-id="6cea5-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6cea5-104">W tym temacie opisano, jak tworzyć listy zadań i dodawać do nich zadania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6cea5-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6cea5-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="6cea5-105">Overview</span></span>

<span data-ttu-id="6cea5-106">*Zadanie* definiuje określony element pracy lub akcję, którą ktoś musi zakończyć w dniu lub przed określonym terminem płatności.</span><span class="sxs-lookup"><span data-stu-id="6cea5-106">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="6cea5-107">W Dynamics 365 Commerce zadanie może zawierać szczegółowe instrukcje i informacje o osobie kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="6cea5-107">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="6cea5-108">Może również zawierać łącza do operacji związanych z kopiami zapasowymi, operacje punktu sprzedaży (POS) lub stron witryny w celu zwiększenia produktywności i zapewnienia kontekstu potrzebnego właścicielowi zadania w celu efektywnego wykonania zadania.</span><span class="sxs-lookup"><span data-stu-id="6cea5-108">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="6cea5-109">*Lista zadań* to zbiór zadań, które należy wykonać w ramach procesu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="6cea5-109">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="6cea5-110">Na przykład może to być lista zadań, którą nowy pracownik musi zakończyć w celu przechodzenia do systemu, listy zadań dla kasjerów, którzy pracują wieczorem lub z listy zadań, które muszą zostać wypełnione, aby przygotować sklep do nadchodzącego sezonu wakacyjnego.</span><span class="sxs-lookup"><span data-stu-id="6cea5-110">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="6cea5-111">W Commerce, każda lista zadań z datą docelową może zostać przypisana do dowolnej liczby sklepów lub pracowników i może zostać skonfigurowana do ponownego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="6cea5-111">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="6cea5-112">Zarówno kierownicy, jak i pracownicy mogą tworzyć listy zadań w biurze zaplecza w Commerce, a następnie przypisywać je do zbioru sklepów.</span><span class="sxs-lookup"><span data-stu-id="6cea5-112">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="6cea5-113">Utwórz nową listę zadań</span><span class="sxs-lookup"><span data-stu-id="6cea5-113">Create a task list</span></span>

<span data-ttu-id="6cea5-114">Aby utworzyć listę zadań, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6cea5-114">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="6cea5-115">Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="6cea5-115">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="6cea5-116">Wybierz **Nowy**, a następnie wprowadź wartości w polach **Nazwa**, **Opis** i **Właściciel**.</span><span class="sxs-lookup"><span data-stu-id="6cea5-116">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="6cea5-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6cea5-117">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="6cea5-118">Dodawanie zadań do listy zadań</span><span class="sxs-lookup"><span data-stu-id="6cea5-118">Add tasks to a task list</span></span>

<span data-ttu-id="6cea5-119">Aby dodać zadanie do listy zadań, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6cea5-119">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="6cea5-120">Na skróconej karcie **Zadania** istniejącej listy zadań wybierz opcję **Nowe**, aby dodać zadanie.</span><span class="sxs-lookup"><span data-stu-id="6cea5-120">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="6cea5-121">W nowym oknie dialogowym **Utwórz nowe zadanie**, w polu **Nazwa** wprowadź unikatową nazwę zadania.</span><span class="sxs-lookup"><span data-stu-id="6cea5-121">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="6cea5-122">W polu **Przesunięcie danych należnych od daty docelowej** wprowadź dodatnią lub ujemną wartość całkowitą.</span><span class="sxs-lookup"><span data-stu-id="6cea5-122">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="6cea5-123">Na przykład wprowadź **-2**, jeśli zadanie ma zostać wykonane dwa dni przed datą ukończenia listy zadań.</span><span class="sxs-lookup"><span data-stu-id="6cea5-123">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="6cea5-124">W polu **Uwagi** wprowadź szczegółowe instrukcje.</span><span class="sxs-lookup"><span data-stu-id="6cea5-124">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="6cea5-125">W polu **Osoba kontaktowa** wprowadź nazwisko eksperta, którego właściciel zadania może skontaktować się, jeśli wymaga tego pomoc.</span><span class="sxs-lookup"><span data-stu-id="6cea5-125">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="6cea5-126">W polu **Łącze zadania** wprowadź łącze na podstawie charakteru zadania.</span><span class="sxs-lookup"><span data-stu-id="6cea5-126">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="6cea5-127">Chociaż można skorzystać z pola **Przypisane do**, aby przydzielić zadania komuś podczas tworzenia listy zadań, zaleca się uniknięcie przypisywania zadań podczas tworzenia listy zadań.</span><span class="sxs-lookup"><span data-stu-id="6cea5-127">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="6cea5-128">Zamiast tego należy przypisywać zadania po utworzeniu wystąpienia listy dla poszczególnych sklepów.</span><span class="sxs-lookup"><span data-stu-id="6cea5-128">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="6cea5-129">Korzystanie z łączy zadań w celu poprawy produktywności pracowników</span><span class="sxs-lookup"><span data-stu-id="6cea5-129">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="6cea5-130">Commerce umożliwia połączenie zadań z określonymi operacjami w punkcie sprzedaży, takich jak raport sprzedaży, wyświetlanie materiałów wideo szkoleniowych w trybie online dla nowych pracowników lub wykonywanie operacji biura zaplecza.</span><span class="sxs-lookup"><span data-stu-id="6cea5-130">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="6cea5-131">Ta funkcja ułatwia właścicielom zadań uzyskiwanie informacji potrzebnych do wydajnego wykonania zadania.</span><span class="sxs-lookup"><span data-stu-id="6cea5-131">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="6cea5-132">Aby dodać łącza do zadań podczas tworzenia zadania, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6cea5-132">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="6cea5-133">Na skróconej karcie **Zadania** istniejącej listy zadań wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="6cea5-133">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="6cea5-134">W oknie dialogowym **Edytuj zadanie** w polu **Łącze zadania** wybierz jedną lub więcej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="6cea5-134">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="6cea5-135">Wybierz **Element menu**, aby skonfigurować operację zaplecza (np. „zestawy produktów”).</span><span class="sxs-lookup"><span data-stu-id="6cea5-135">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="6cea5-136">Wybierz **Operację punktu sprzedaży**, aby skonfigurować operację punktu sprzedaży, taką jak „raporty o sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="6cea5-136">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="6cea5-137">Wybierz opcję **adres URL**, aby skonfigurować bezwzględny adres URL.</span><span class="sxs-lookup"><span data-stu-id="6cea5-137">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="6cea5-138">Na poniższej ilustracji przedstawiono wybór łączy zadań w oknie dialogowym **Edytuj zadanie**.</span><span class="sxs-lookup"><span data-stu-id="6cea5-138">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Wybieranie łączy zadań w oknie dialogowym Edytuj zadanie](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="6cea5-140">Skonfiguruj operację punktu sprzedaży, aby mogła być połączona z zadaniem</span><span class="sxs-lookup"><span data-stu-id="6cea5-140">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="6cea5-141">Aby skonfigurować operację punktu sprzedaży, aby można ją było połączyć z zadaniem, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6cea5-141">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="6cea5-142">Przejdź do **Retail and Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje punktu sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="6cea5-142">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="6cea5-143">Wybierz **Edytuj**, znajdź operację punktu sprzedaży, a następnie zaznacz pole wyboru **Włącz zarządzanie zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="6cea5-143">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6cea5-144">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6cea5-144">Additional resources</span></span>

[<span data-ttu-id="6cea5-145">Omówienie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="6cea5-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="6cea5-146">Konfigurowanie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="6cea5-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="6cea5-147">Przypisywanie list zadań do sklepów lub pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="6cea5-147">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="6cea5-148">Zarządzanie zadaniami w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6cea5-148">Task management in POS</span></span>](task-mgmt-POS.md)
