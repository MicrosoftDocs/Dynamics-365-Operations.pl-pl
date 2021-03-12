---
title: Konfigurowanie zarządzania zadaniami
description: W tym temacie opisano sposób konfigurowania funkcji zarządzania zadaniami w Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: e880305d02fd9f10464fe3f65a2774a44da258c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006242"
---
# <a name="configure-task-management"></a><span data-ttu-id="44938-103">Konfigurowanie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="44938-103">Configure task management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="44938-104">W tym temacie opisano sposób konfigurowania funkcji zarządzania zadaniami w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="44938-104">This topic describes how to configure task management features in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="44938-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="44938-105">Overview</span></span>

<span data-ttu-id="44938-106">Aby menedżerowie i pracownicy Dynamics 365 Commerce mogli skorzystać z funkcji zarządzania zadaniami w Commerce, należy skonfigurować funkcję zarządzania zadaniami.</span><span class="sxs-lookup"><span data-stu-id="44938-106">Before Dynamics 365 Commerce managers and employees can use the task management features in Commerce, task management must be configured.</span></span> <span data-ttu-id="44938-107">Kroki konfiguracyjne obejmują przyznawanie uprawnień menedżerom i pracownikom, dystrybuowanie uprawnień do klientów punktu sprzedaży (POS), konfigurowanie powiadomień punktu sprzedaży oraz konfigurowanie kafelka **Zadania** na stronie głównej aplikacji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="44938-107">Configuration steps include granting permissions to managers and employees, distributing permissions to point of sale (POS) clients, setting up POS notifications, and configuring the **Tasks** tile on the home page of a POS application.</span></span>

## <a name="configure-permissions-for-store-managers"></a><span data-ttu-id="44938-108">Konfigurowanie uprawnień dla menedżerów sklepów</span><span class="sxs-lookup"><span data-stu-id="44938-108">Configure permissions for store managers</span></span>

<span data-ttu-id="44938-109">Każdy pracownik w danym sklepie może wyświetlać wszystkie zadania przypisane do danego sklepu.</span><span class="sxs-lookup"><span data-stu-id="44938-109">Every worker in a given store can view all tasks that are assigned to that store.</span></span> <span data-ttu-id="44938-110">Mogą również aktualizować stan przypisanych do nich zadań.</span><span class="sxs-lookup"><span data-stu-id="44938-110">They can also update the status of the tasks that are assigned to them.</span></span> <span data-ttu-id="44938-111">Jednak osoby, takie jak kierownicy sklepów, muszą mieć uprawnienia do zarządzania zadaniami, aby zarządzać zadaniami przypisanymi do sklepu i tworzyć zadania jednorazowe.</span><span class="sxs-lookup"><span data-stu-id="44938-111">However, personas such as store managers must have task management permissions to manage tasks that are assigned to the store and to create single-purpose tasks.</span></span>

<span data-ttu-id="44938-112">Aby skonfigurować uprawnienia zarządzania zadaniami dla menedżerów sklepów, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="44938-112">To configure task management permissions for store managers, follow these steps.</span></span>

1. <span data-ttu-id="44938-113">Wybierz kolejno opcje **Retail i Commerce \> Pracownicy \> Grupy uprawnień**.</span><span class="sxs-lookup"><span data-stu-id="44938-113">Go to **Retail and Commerce \> Employees \> Permission groups**.</span></span>
1. <span data-ttu-id="44938-114">Wybierz określoną grupę uprawnień (na przykład **Menedżer**), a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="44938-114">Select a specific permission group (for example, **Manager**), and then select **Edit**.</span></span>
1. <span data-ttu-id="44938-115">Na skróconej karcie **Uprawnienia**, w opcji **Zezwalaj na zarządzanie zadaniami** określ wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="44938-115">On the **Permissions** FastTab, set the **Allow task management** option to **Yes**.</span></span>
1. <span data-ttu-id="44938-116">Na skróconej karcie **Powiadomień** dodaj operację **Zarządzania zadaniami** i wprowadź wartość w polu **Kolejność wyświetlania**.</span><span class="sxs-lookup"><span data-stu-id="44938-116">On the **Notifications** FastTab, add the **Task management** operation, and enter a value in the **Display order** field.</span></span> <span data-ttu-id="44938-117">Na przykład wprowadzenie wartości **2**, jeśli dla operacji **Realizacji zamówienia** istnieje już wartość **Kolejność wyświetlania** **1**.</span><span class="sxs-lookup"><span data-stu-id="44938-117">For example, enter **2** if the **Order fulfillment** operation already has a **Display order** value of **1**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="44938-118">Jeśli osoba niebędąca na stanowisku menedżera musi mieć uprawnienia do zarządzania zadaniami w punkcie sprzedaży, można udzielić uprawnienia do danej osoby.</span><span class="sxs-lookup"><span data-stu-id="44938-118">If a non-manager persona must have task management permissions in the POS, you can grant permission to the individual.</span></span> <span data-ttu-id="44938-119">Można również utworzyć nową grupę uprawnień dla innych niż menedżerów i ustawić opcję **Zezwalaj na zarządzanie zadaniami** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="44938-119">Alternatively, you can create a new permission group for non-managers and set the **Allow task management** option to **Yes**.</span></span>

<span data-ttu-id="44938-120">Poniższa ilustracja pokazuje, jak skonfigurować uprawnienia do zarządzania zadaniami dla menedżerów sklepów.</span><span class="sxs-lookup"><span data-stu-id="44938-120">The following illustration shows how to configure task management permissions for store managers.</span></span>

![Konfigurowanie uprawnienia zarządzania zadaniami dla menedżerów sklepów](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a><span data-ttu-id="44938-122">Konfigurowanie uprawnień pracowników</span><span class="sxs-lookup"><span data-stu-id="44938-122">Configure permissions for employees</span></span>

<span data-ttu-id="44938-123">Pracownicy muszą mieć uprawnienia do tworzenia list zadań, zarządzania kryteriami przypisywania i konfigurowania powtarzania dowolnej listy zadań.</span><span class="sxs-lookup"><span data-stu-id="44938-123">Employees must have permissions to create task lists, manage assignment criteria, and configure the recurrence of any task list.</span></span> <span data-ttu-id="44938-124">Aby skonfigurować te uprawnienia, należy przypisać pracowników do roli **Menedżer zadań sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="44938-124">To configure these permissions, you assign employees to the **Retail task manager** role.</span></span>

<span data-ttu-id="44938-125">Aby skonfigurować uprawnienia dla pracownika, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="44938-125">To configure permissions for an employee, follow these steps.</span></span>

1. <span data-ttu-id="44938-126">Wybierz kolejno opcje **Retail and Commerce \> Pracownicy \> Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="44938-126">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="44938-127">Wybierz pracownika.</span><span class="sxs-lookup"><span data-stu-id="44938-127">Select an employee.</span></span>
1. <span data-ttu-id="44938-128">Na karcie skróconej **Role użytkownika** wybierz opcję **Przypisz role**.</span><span class="sxs-lookup"><span data-stu-id="44938-128">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="44938-129">W oknie dialogowym **Przypisz role do użytkownika** wybierz rolę **Menedżer zadań sieci sprzedaży**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="44938-129">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

## <a name="distribute-permissions-to-pos-clients"></a><span data-ttu-id="44938-130">Dystrybuuj uprawnienia do klientów punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="44938-130">Distribute permissions to POS clients</span></span>

<span data-ttu-id="44938-131">Zanim pracownicy będą mogli skorzystać z klientów punktu sprzedaży, muszą być oni dystrybuowane i zsynchronizowane z tymi klientami.</span><span class="sxs-lookup"><span data-stu-id="44938-131">Before employees can use POS clients, permissions must be distributed and synced to those clients.</span></span>

<span data-ttu-id="44938-132">Aby dystrybuować uprawnienia do klientów punktu sprzedaży, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="44938-132">To distribute permissions to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="44938-133">Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="44938-133">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="44938-134">Wybierz harmonogram dystrybucji **1060** (**Personel**), a następnie wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="44938-134">Select the **1060** (**Staff**) distribution schedule, and then select **Run now**.</span></span>
1. <span data-ttu-id="44938-135">Wybierz harmonogram dystrybucji **1070** (**Konfiguracja kanału**), a następnie wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="44938-135">Select the **1070** (**Channel configuration**) distribution schedule, and then select **Run now**.</span></span>

## <a name="configure-pos-notifications-for-tasks"></a><span data-ttu-id="44938-136">Konfigurowanie powiadomień punktu sprzedaży dla zadań</span><span class="sxs-lookup"><span data-stu-id="44938-136">Configure POS notifications for tasks</span></span>

<span data-ttu-id="44938-137">Należy skonfigurować zarządzanie zadaniami, aby były dostępne powiadomienia w aplikacji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="44938-137">Task management must be configured so that notifications are available in the POS application.</span></span>

<span data-ttu-id="44938-138">Aby skonfigurować powiadomienia punktu sprzedazy dla zadań, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="44938-138">To configure POS notifications for tasks, follow these steps.</span></span>

1. <span data-ttu-id="44938-139">Przejdź do **Retail and Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Operacje punktu sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="44938-139">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="44938-140">Znajdź operację **1400** (**Zarządzanie zadaniami**) i zaznacz pole wyboru **Włącz powiadomienia**.</span><span class="sxs-lookup"><span data-stu-id="44938-140">Find operation **1400** (**Task management**), and select the **Enable notifications** check box for it.</span></span>

<span data-ttu-id="44938-141">Na poniższej ilustracji przedstawiono operację **Zarządzania zadaniami** na stronie **Operacje punktu sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="44938-141">The following illustration shows the **Task management** operation on the **POS operations** page.</span></span>

![Operacja zarządzania zadaniami na stronie operacji punktu sprzedaży](media/HQ-POS-Tasks-Notifications.png)

<span data-ttu-id="44938-143">Aby uzyskać więcej informacji o konfigurowaniu powiadomień punktu sprzedaży, zapoznaj się z tematem [Pokazywanie powiadomień o zamówieniach w aplikacji punktu sprzedaży (POS)](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="44938-143">For more information about how to configure POS notifications, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a><span data-ttu-id="44938-144">Konfiguruj kafelek zadania na stronie głównej aplikacji punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="44938-144">Configure the Tasks tile on a POS application home page</span></span>

<span data-ttu-id="44938-145">Przed skonfigurowaniem kafelka **Zadania** na stronie głównej aplikacji punktu sprzedaży należy zapoznać się z [Układy ekranu w aplikacji punktu sprzedaży (POS)](pos-screen-layouts.md), aby uzyskać informacje dotyczące konfigurowania i dodawania nowych przycisków do układu ekranu punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="44938-145">Before you configure the **Tasks** tile on the home page of a POS application, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information about how to configure and add new buttons to a POS screen layout.</span></span>

<span data-ttu-id="44938-146">Aby skonfigurować kafelek **Zadania** na stronie głównej aplikacji punktu sprzedaży, postępuj zgodnie z następującymi krokami.</span><span class="sxs-lookup"><span data-stu-id="44938-146">To configure the **Tasks** tile on a POS application home page, follow these steps.</span></span>

1. <span data-ttu-id="44938-147">Wybierz kolejno opcje **Retail and Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Punkt sprzedaży \> Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="44938-147">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> Screen layouts**.</span></span>
1. <span data-ttu-id="44938-148">Wybierz układ ekranu, wybierz rozmiar układu i wybierz siatkę przycisków.</span><span class="sxs-lookup"><span data-stu-id="44938-148">Select a screen layout, select a layout size, and select a button grid.</span></span>
1. <span data-ttu-id="44938-149">Na skróconej karcie **Siatki przycisków** wybierz opcję **Projektant**, aby edytować wybraną siatkę przycisków.</span><span class="sxs-lookup"><span data-stu-id="44938-149">On the **Button grids** FastTab, select **Designer** to edit the selected button grid.</span></span>
1. <span data-ttu-id="44938-150">Dodaj kafelek **Zadania** do odpowiedniej sekcji strony głównej.</span><span class="sxs-lookup"><span data-stu-id="44938-150">Add a **Tasks** tile to the appropriate section of the home page.</span></span>

<span data-ttu-id="44938-151">Poniższa ilustracja przedstawia przykład kafelka **Zadania** na stronie głównej punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="44938-151">The following illustration shows an example of a **Tasks** tile on a POS home page.</span></span>

![Kafelek zadań na stronie głównej punktu sprzedaży](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a><span data-ttu-id="44938-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="44938-153">Additional resources</span></span>

[<span data-ttu-id="44938-154">Omówienie zarządzania zadaniami</span><span class="sxs-lookup"><span data-stu-id="44938-154">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="44938-155">Tworzenie list zadań i dodawanie zadań</span><span class="sxs-lookup"><span data-stu-id="44938-155">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="44938-156">Przypisywanie list zadań do sklepów lub pracowników etatowych</span><span class="sxs-lookup"><span data-stu-id="44938-156">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="44938-157">Zarządzanie zadaniami w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="44938-157">Task management in POS</span></span>](task-mgmt-POS.md)
