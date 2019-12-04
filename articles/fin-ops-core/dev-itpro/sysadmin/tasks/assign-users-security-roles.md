---
title: Przypisywanie użytkowników do ról zabezpieczeń
description: Aby mieć dostęp do aplikacji Finance and Operations, użytkownicy muszą być przypisani do ról zabezpieczeń.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
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
ms.openlocfilehash: e4f4ef4535de9e371829c2d86d4fdc1400510c7b
ms.sourcegitcommit: 6aa74f66f1abd3a7977050a5339b0b17e62ff053
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2019
ms.locfileid: "2808003"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="4fbfd-103">Przypisywanie użytkowników do ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="4fbfd-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4fbfd-104">Aby można było skorzystać z innych funkcji niż typowe, użytkownicy muszą być przypisani do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-104">To use anything other than common capabilities, users must be assigned to security roles.</span></span> <span data-ttu-id="4fbfd-105">W tej procedurze pokazano, jak administratorzy systemu mogą automatycznie przypisywać użytkowników do ról, na podstawie danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-105">This procedure explains how system administrators can automatically assign users to roles, based on business data.</span></span> 

## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="4fbfd-106">Automatyczne przypisywanie użytkowników do ról</span><span class="sxs-lookup"><span data-stu-id="4fbfd-106">Automatically assign users to roles</span></span>
1. <span data-ttu-id="4fbfd-107">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-107">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="4fbfd-108">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-108">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="4fbfd-109">Zaznacz rolę, dla której chcesz skonfigurować regułę.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-109">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="4fbfd-110">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-110">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="4fbfd-111">Kliknij **Dodaj zasadę**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-111">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="4fbfd-112">Na liście **Wybierz kwerendę**odnajdź i wybierz odpowiednią pozycję.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-112">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="4fbfd-113">Zaznacz zapytanie, którego chcesz używać dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-113">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="4fbfd-114">Na liście **Nazwa zasady członkowstwa** kliknij link w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-114">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4fbfd-115">Kliknij **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-115">Click **Edit query**.</span></span> <span data-ttu-id="4fbfd-116">Edytuj kwerendę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-116">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="4fbfd-117">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-117">Click **OK**.</span></span>
8. <span data-ttu-id="4fbfd-118">Kliknij **Uruchom automatyczne przypisanie roli**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-118">Click **Run automatic role assignment**.</span></span>
9. <span data-ttu-id="4fbfd-119">Przejdź do **Okienko nawigacji > Moduły > Administrowanie systemem > Użytkownicy > Użytkownicy** (najlepiej w osobnej karcie przeglądarki)</span><span class="sxs-lookup"><span data-stu-id="4fbfd-119">Go to **Navigation pane > Modules > System administration > Users > Users** (ideally in a separate browser tab).</span></span>
10. <span data-ttu-id="4fbfd-120">Przejrzyj role przypisane różnym użytkownikom, aby potwierdzić, że kwerenda przypisania roli była poprawna.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-120">Review the roles assigned to various users to confirm that the role assignment query was correct.</span></span> <span data-ttu-id="4fbfd-121">W razie potrzeby skoryguj i uruchom ponownie.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-121">Adjust and re-run if needed.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="4fbfd-122">Wykluczanie użytkowników z automatycznego przypisywania ról</span><span class="sxs-lookup"><span data-stu-id="4fbfd-122">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="4fbfd-123">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-123">Close the page.</span></span>
2. <span data-ttu-id="4fbfd-124">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-124">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="4fbfd-125">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-125">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="4fbfd-126">Służy do wybierania roli.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-126">Select a role.</span></span> <span data-ttu-id="4fbfd-127">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-127">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="4fbfd-128">W menu **Użytkownicy przypisani do roli** wybierz **Ręcznie przypisz / wyklucz użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-128">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="4fbfd-129">Na liście **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** zaznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-129">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="4fbfd-130">Wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-130">Select a user.</span></span>  
6. <span data-ttu-id="4fbfd-131">W **Panelu akcji** wybierz **Wyklucz z roli**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-131">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="4fbfd-132">Kliknij **Wyklucz użytkowników z roli**, aby wykluczyć wybranych użytkowników z roli.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-132">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="4fbfd-133">Żeby usunąć wykluczenia, wybierz użytkowników, których wyluczenia chcesz usunąć i kliknij **Zresetuj status**.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-133">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="4fbfd-134">Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-134">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="4fbfd-135">Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-135">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="4fbfd-136">Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.</span><span class="sxs-lookup"><span data-stu-id="4fbfd-136">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
