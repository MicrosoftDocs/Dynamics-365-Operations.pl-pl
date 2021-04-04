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
ms.openlocfilehash: 28bea16c3266115cf09aa80a364344789d60af7a
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477840"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="2a83a-103">Tworzenie list zadań i dodawanie zadań</span><span class="sxs-lookup"><span data-stu-id="2a83a-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2a83a-104">W tym temacie opisano, jak tworzyć listy zadań i dodawać do nich zadania w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a83a-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2a83a-105">*Zadanie* definiuje określony element pracy lub akcję, którą ktoś musi zakończyć w dniu lub przed określonym terminem płatności.</span><span class="sxs-lookup"><span data-stu-id="2a83a-105">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="2a83a-106">W Dynamics 365 Commerce zadanie może zawierać szczegółowe instrukcje i informacje o osobie kontaktowej.</span><span class="sxs-lookup"><span data-stu-id="2a83a-106">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="2a83a-107">Może również zawierać łącza do operacji związanych z kopiami zapasowymi, operacje punktu sprzedaży (POS) lub stron witryny w celu zwiększenia produktywności i zapewnienia kontekstu potrzebnego właścicielowi zadania w celu efektywnego wykonania zadania.</span><span class="sxs-lookup"><span data-stu-id="2a83a-107">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="2a83a-108">*Lista zadań* to zbiór zadań, które należy wykonać w ramach procesu biznesowego.</span><span class="sxs-lookup"><span data-stu-id="2a83a-108">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="2a83a-109">Na przykład może to być lista zadań, którą nowy pracownik musi zakończyć w celu przechodzenia do systemu, listy zadań dla kasjerów, którzy pracują wieczorem lub z listy zadań, które muszą zostać wypełnione, aby przygotować sklep do nadchodzącego sezonu wakacyjnego.</span><span class="sxs-lookup"><span data-stu-id="2a83a-109">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="2a83a-110">W Commerce, każda lista zadań z datą docelową może zostać przypisana do dowolnej liczby sklepów lub pracowników i może zostać skonfigurowana do ponownego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="2a83a-110">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="2a83a-111">Zarówno kierownicy, jak i pracownicy mogą tworzyć listy zadań w biurze zaplecza w Commerce, a następnie przypisywać je do zbioru sklepów.</span><span class="sxs-lookup"><span data-stu-id="2a83a-111">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="2a83a-112">Utwórz nową listę zadań</span><span class="sxs-lookup"><span data-stu-id="2a83a-112">Create a task list</span></span>

<span data-ttu-id="2a83a-113">Aby utworzyć listę zadań, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2a83a-113">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="2a83a-114">Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="2a83a-114">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="2a83a-115">Wybierz **Nowy**, a następnie wprowadź wartości w polach **Nazwa**, **Opis** i **Właściciel**.</span><span class="sxs-lookup"><span data-stu-id="2a83a-115">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="2a83a-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2a83a-116">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="2a83a-117">Dodawanie zadań do listy zadań</span><span class="sxs-lookup"><span data-stu-id="2a83a-117">Add tasks to a task list</span></span>

<span data-ttu-id="2a83a-118">Aby dodać zadanie do listy zadań, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2a83a-118">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="2a83a-119">Na skróconej karcie **Zadania** istniejącej listy zadań wybierz opcję **Nowe**, aby dodać zadanie.</span><span class="sxs-lookup"><span data-stu-id="2a83a-119">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="2a83a-120">W nowym oknie dialogowym **Utwórz nowe zadanie**, w polu **Nazwa** wprowadź unikatową nazwę zadania.</span><span class="sxs-lookup"><span data-stu-id="2a83a-120">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="2a83a-121">W polu **Przesunięcie danych należnych od daty docelowej** wprowadź dodatnią lub ujemną wartość całkowitą.</span><span class="sxs-lookup"><span data-stu-id="2a83a-121">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="2a83a-122">Na przykład wprowadź **-2**, jeśli zadanie ma zostać wykonane dwa dni przed datą ukończenia listy zadań.</span><span class="sxs-lookup"><span data-stu-id="2a83a-122">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="2a83a-123">W polu **Uwagi** wprowadź szczegółowe instrukcje.</span><span class="sxs-lookup"><span data-stu-id="2a83a-123">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="2a83a-124">W polu **Osoba kontaktowa** wprowadź nazwisko eksperta, którego właściciel zadania może skontaktować się, jeśli wymaga tego pomoc.</span><span class="sxs-lookup"><span data-stu-id="2a83a-124">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="2a83a-125">W polu **Łącze zadania** wprowadź łącze na podstawie charakteru zadania.</span><span class="sxs-lookup"><span data-stu-id="2a83a-125">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="2a83a-126">Chociaż można skorzystać z pola **Przypisane do**, aby przydzielić zadania komuś podczas tworzenia listy zadań, zaleca się uniknięcie przypisywania zadań podczas tworzenia listy zadań.</span><span class="sxs-lookup"><span data-stu-id="2a83a-126">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="2a83a-127">Zamiast tego należy przypisywać zadania po utworzeniu wystąpienia listy dla poszczególnych sklepów.</span><span class="sxs-lookup"><span data-stu-id="2a83a-127">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="2a83a-128">Korzystanie z łączy zadań w celu poprawy produktywności pracowników</span><span class="sxs-lookup"><span data-stu-id="2a83a-128">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="2a83a-129">Commerce umożliwia połączenie zadań z określonymi operacjami w punkcie sprzedaży, takich jak raport sprzedaży, wyświetlanie materiałów wideo szkoleniowych w trybie online dla nowych pracowników lub wykonywanie operacji biura zaplecza.</span><span class="sxs-lookup"><span data-stu-id="2a83a-129">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="2a83a-130">Ta funkcja ułatwia właścicielom zadań uzyskiwanie informacji potrzebnych do wydajnego wykonania zadania.</span><span class="sxs-lookup"><span data-stu-id="2a83a-130">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="2a83a-131">Aby dodać łącza do zadań podczas tworzenia zadania, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2a83a-131">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="2a83a-132">Na skróconej karcie **Zadania** istniejącej listy zadań wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="2a83a-132">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="2a83a-133">W oknie dialogowym **Edytuj zadanie** w polu **Łącze zadania** wybierz jedną lub więcej z następujących opcji:</span><span class="sxs-lookup"><span data-stu-id="2a83a-133">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="2a83a-134">Wybierz **Element menu**, aby skonfigurować operację zaplecza (np. „zestawy produktów”).</span><span class="sxs-lookup"><span data-stu-id="2a83a-134">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="2a83a-135">Wybierz **Operację punktu sprzedaży**, aby skonfigurować operację punktu sprzedaży, taką jak „raporty o sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="2a83a-135">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="2a83a-136">Wybierz opcję **adres URL**, aby skonfigurować bezwzględny adres URL.</span><span class="sxs-lookup"><span data-stu-id="2a83a-136">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="2a83a-137">Na poniższej ilustracji przedstawiono wybór łączy zadań w oknie dialogowym **Edytuj zadanie**.</span><span class="sxs-lookup"><span data-stu-id="2a83a-137">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Wybieranie łączy zadań w oknie dialogowym Edytuj zadanie](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="2a83a-139">Skonfiguruj operację punktu sprzedaży, aby mogła być połączona z zadaniem</span><span class="sxs-lookup"><span data-stu-id="2a83a-139">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="2a83a-140">Aby skonfigurować operację punktu sprzedaży, aby można ją było połączyć z zadaniem, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2a83a-140">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="2a83a-141">Przejdź do **Retail and Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje punktu sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="2a83a-141">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="2a83a-142">Wybierz **Edytuj**, znajdź operację punktu sprzedaży, a następnie zaznacz pole wyboru **Włącz zarządzanie zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="2a83a-142">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a83a-143">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2a83a-143">Additional resources</span></span>

[<span data-ttu-id="2a83a-144">Omówienie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="2a83a-144">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="2a83a-145">Konfigurowanie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="2a83a-145">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="2a83a-146">Przypisywanie list zadań do sklepów lub pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="2a83a-146">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="2a83a-147">Zarządzanie zadaniami w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2a83a-147">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
