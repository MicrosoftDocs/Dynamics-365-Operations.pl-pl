---
title: Przypisywanie użytkowników do ról zabezpieczeń
description: Aby mieć dostęp do aplikacji Finance and Operations, użytkownicy muszą być przypisani do ról zabezpieczeń.
author: ChrisGarty
manager: AnnBe
ms.date: 09/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4daecc1acd589cd1656402244e5325382a407e7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180974"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="04b84-103">Przypisywanie użytkowników do ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="04b84-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04b84-104">Aby można było skorzystać z innych funkcji niż typowe, użytkownicy muszą być przypisani do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="04b84-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="04b84-105">W tej procedurze pokazano, jak administratorzy systemu mogą automatycznie przypisywać użytkowników do ról, na podstawie danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="04b84-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="04b84-106">Automatyczne przypisywanie użytkowników do ról</span><span class="sxs-lookup"><span data-stu-id="04b84-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="04b84-107">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="04b84-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="04b84-108">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="04b84-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="04b84-109">Zaznacz rolę, dla której chcesz skonfigurować regułę.</span><span class="sxs-lookup"><span data-stu-id="04b84-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="04b84-110">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="04b84-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="04b84-111">Kliknij **Dodaj zasadę**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="04b84-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="04b84-112">Na liście **Wybierz kwerendę**odnajdź i wybierz odpowiednią pozycję.</span><span class="sxs-lookup"><span data-stu-id="04b84-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="04b84-113">Zaznacz zapytanie, którego chcesz używać dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="04b84-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="04b84-114">Na liście **Nazwa zasady członkowstwa** kliknij link w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="04b84-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="04b84-115">Kliknij **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="04b84-115">Click **Edit query**.</span></span> <span data-ttu-id="04b84-116">Edytuj kwerendę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="04b84-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="04b84-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="04b84-117">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="04b84-118">Wykluczanie użytkowników z automatycznego przypisywania ról</span><span class="sxs-lookup"><span data-stu-id="04b84-118">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="04b84-119">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="04b84-119">Close the page.</span></span>
2. <span data-ttu-id="04b84-120">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="04b84-120">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="04b84-121">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="04b84-121">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="04b84-122">Służy do wybierania roli.</span><span class="sxs-lookup"><span data-stu-id="04b84-122">Select a role.</span></span> <span data-ttu-id="04b84-123">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="04b84-123">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="04b84-124">W menu **Użytkownicy przypisani do roli** wybierz **Ręcznie przypisz / wyklucz użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="04b84-124">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="04b84-125">Na liście **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** zaznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="04b84-125">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="04b84-126">Wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="04b84-126">Select a user.</span></span>  
6. <span data-ttu-id="04b84-127">W **Panelu akcji** wybierz **Wyklucz z roli**.</span><span class="sxs-lookup"><span data-stu-id="04b84-127">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="04b84-128">Kliknij **Wyklucz użytkowników z roli**, aby wykluczyć wybranych użytkowników z roli.</span><span class="sxs-lookup"><span data-stu-id="04b84-128">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="04b84-129">Żeby usunąć wykluczenia, wybierz użytkowników, których wyluczenia chcesz usunąć i kliknij **Zresetuj status**.</span><span class="sxs-lookup"><span data-stu-id="04b84-129">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="04b84-130">Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola.</span><span class="sxs-lookup"><span data-stu-id="04b84-130">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="04b84-131">Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli.</span><span class="sxs-lookup"><span data-stu-id="04b84-131">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="04b84-132">Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.</span><span class="sxs-lookup"><span data-stu-id="04b84-132">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
