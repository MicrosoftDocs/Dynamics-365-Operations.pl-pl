---
title: Przypisywanie list zadań do sklepów lub pracowników etatowych
description: W tym temacie opisano sposób przypisywania list zadań do sklepów lub pracowników w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ee924f5bf95d47814e7ca09b392a3d10b5e9b9dc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006267"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="a69d6-103">Przypisywanie list zadań do sklepów lub pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="a69d6-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a69d6-104">W tym temacie opisano sposób przypisywania list zadań do sklepów lub pracowników w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a69d6-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a69d6-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a69d6-105">Overview</span></span>

<span data-ttu-id="a69d6-106">Zarządzanie zadaniami w Dynamics 365 Commerce umożliwia przypisywanie listy zadań do wielu sklepów lub pracowników, a także na połączenie sklepów i pracowników.</span><span class="sxs-lookup"><span data-stu-id="a69d6-106">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="a69d6-107">Na przykład Menedżer regionalny dla 20 sklepów może chcieć przypisać listę zadań **Przygotowania do sezonu świątecznego** do wszystkich 20 sklepów.</span><span class="sxs-lookup"><span data-stu-id="a69d6-107">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="a69d6-108">Uruchamianie procesu przypisania listy zadań</span><span class="sxs-lookup"><span data-stu-id="a69d6-108">Start the task list assignment process</span></span>

<span data-ttu-id="a69d6-109">Aby rozpocząć proces przypisywania listy zadań, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a69d6-109">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="a69d6-110">Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-110">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="a69d6-111">Umożliwia wybór listy zadań do przypisania.</span><span class="sxs-lookup"><span data-stu-id="a69d6-111">Select the task list to assign.</span></span>
1. <span data-ttu-id="a69d6-112">Wybierz **Rozpocznij proces**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-112">Select **Start process**.</span></span>
1. <span data-ttu-id="a69d6-113">W oknie dialogowym **Rozpocznij proces**, na karcie **ogólne**, w polu **Nazwa procesu** wprowadź nazwę (na przykład **Sklepy regionu wschodniego**).</span><span class="sxs-lookup"><span data-stu-id="a69d6-113">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="a69d6-114">W polu **Data docelowa** wybierz datę.</span><span class="sxs-lookup"><span data-stu-id="a69d6-114">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="a69d6-115">Aby przypisać listę zadań do sklepów, na karcie **Sklepy** skorzystaj z filtru **Hierarchia organizacji**, aby znaleźć i wybrać sklepy.</span><span class="sxs-lookup"><span data-stu-id="a69d6-115">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="a69d6-116">Aby przypisać listę zadań do pracowników, na karcie **Pracownicy** znajdź i zaznacz pracowników.</span><span class="sxs-lookup"><span data-stu-id="a69d6-116">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="a69d6-117">Wybierz przycisk **OK**, aby rozpocząć proces.</span><span class="sxs-lookup"><span data-stu-id="a69d6-117">Select **OK** to start the process.</span></span> <span data-ttu-id="a69d6-118">Lista zadań jest przypisana do wybranych sklepów lub pracowników.</span><span class="sxs-lookup"><span data-stu-id="a69d6-118">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="a69d6-119">Na poniższej ilustracji przedstawiono przykład wyszukiwania i wybierania sklepów w oknie dialogowym **Rozpocznij proces**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-119">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Znajdowanie i wybieranie sklepów w oknie dialogowym Rozpocznij proces](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="a69d6-121">Umożliwia przypisywanie list zadań na podstawie cyklu</span><span class="sxs-lookup"><span data-stu-id="a69d6-121">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="a69d6-122">Czasami detalista ma powtarzalne zadania, takie jak „Lista kontrolna czwartek” lub „Lista kontrolna pierwszego dnia miesiąca”.</span><span class="sxs-lookup"><span data-stu-id="a69d6-122">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="a69d6-123">W związku z tym może zaistnieć konieczność cyklicznego przypisywania listy zadań.</span><span class="sxs-lookup"><span data-stu-id="a69d6-123">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="a69d6-124">Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Administracja zarządzania zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-124">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="a69d6-125">Umożliwia wybór listy zadań do przypisania.</span><span class="sxs-lookup"><span data-stu-id="a69d6-125">Select the task list to assign.</span></span>
1. <span data-ttu-id="a69d6-126">Wybierz **Rozpocznij proces**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-126">Select **Start process**.</span></span>
1. <span data-ttu-id="a69d6-127">W oknie dialogowym **Rozpocznij proces**, na karcie **ogólne**, w polu **Nazwa procesu** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="a69d6-127">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="a69d6-128">Ustaw opcję **Cykl** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-128">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="a69d6-129">W polu **Przesunięcie daty docelowej cyklu w dniach** wprowadź liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="a69d6-129">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="a69d6-130">Jeśli na przykład zostanie wprowadzona wartość **4**, datą docelową jest data cyklu plus cztery dni.</span><span class="sxs-lookup"><span data-stu-id="a69d6-130">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="a69d6-131">Na karcie **Uruchom w tle** wybierz **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-131">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="a69d6-132">W oknie dialogowym **Zdefiniuj cykl** wprowadź kryteria częstotliwości, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-132">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="a69d6-133">Na poniższej ilustracji przedstawiono przykład sposobu wprowadzania kryteriów częstotliwości w oknie dialogowym **Definiowanie cyklu**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-133">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Wprowadzanie kryteriów częstotliwości w oknie dialogowym Zdefiniuj cykl](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="a69d6-135">Śledzenie stanu listy zadań</span><span class="sxs-lookup"><span data-stu-id="a69d6-135">Track task list status</span></span>

<span data-ttu-id="a69d6-136">Jeśli jesteś menedżerem regionalnym lub menedżerem sklepu, możesz śledzić stan list zadań przypisanych do wielu sklepów lub pracowników.</span><span class="sxs-lookup"><span data-stu-id="a69d6-136">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="a69d6-137">Następnie można kontynuować działanie z sklepami lub pracownikami, które nie wypełnili przydzielonych im zadań w czasie.</span><span class="sxs-lookup"><span data-stu-id="a69d6-137">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="a69d6-138">Biuro zaplecza w Commerce umożliwia przeglądanie stanu list zadań, ponowne przypisywanie zadań lub zmianę stanu zadania.</span><span class="sxs-lookup"><span data-stu-id="a69d6-138">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="a69d6-139">Aby śledzić stan listy zadań dla wszystkich zadań, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a69d6-139">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="a69d6-140">Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Procesy zarządzania zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-140">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="a69d6-141">Wybierz kartę **Wszystkie listy zadań,** aby wyświetlić stan wszystkich list zadań przypisanych do różnych sklepów.</span><span class="sxs-lookup"><span data-stu-id="a69d6-141">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="a69d6-142">Aby śledzić stan listy zadań dla wszystkich zadań przypisanych do Ciebie, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a69d6-142">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="a69d6-143">Przejdź do **Retail i Commerce \> Zarządzanie zadaniami \> Procesy zarządzania zadaniami**.</span><span class="sxs-lookup"><span data-stu-id="a69d6-143">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="a69d6-144">Wybierz kartę **Moje zadania** lub **Wszystkie zadania**, aby wyświetlić lub zaktualizować stan przydzielonych zadań.</span><span class="sxs-lookup"><span data-stu-id="a69d6-144">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a69d6-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a69d6-145">Additional resources</span></span>

[<span data-ttu-id="a69d6-146">Omówienie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="a69d6-146">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="a69d6-147">Konfigurowanie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="a69d6-147">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="a69d6-148">Tworzenie list zadań i dodawanie zadań</span><span class="sxs-lookup"><span data-stu-id="a69d6-148">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="a69d6-149">Zarządzanie zadaniami w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a69d6-149">Task management in POS</span></span>](task-mgmt-POS.md)
