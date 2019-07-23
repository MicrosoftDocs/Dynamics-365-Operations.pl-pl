---
title: Przypisywanie użytkowników do ról zabezpieczeń
description: Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab9f2f5ea07ae1d616c48dffa8810b966f7dbb2f
ms.sourcegitcommit: 33e98f89294086334fe9c0a350abb6a52ef9dacb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2019
ms.locfileid: "1711138"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="d2ff4-103">Przypisywanie użytkowników do ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="d2ff4-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2ff4-104">Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="d2ff4-105">W tej procedurze pokazano, jak administratorzy systemu mogą przypisywać użytkowników do ról automatycznie, na podstawie danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="d2ff4-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="d2ff4-107">Automatyczne przypisywanie użytkowników do ról</span><span class="sxs-lookup"><span data-stu-id="d2ff4-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="d2ff4-108">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-108">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
2. <span data-ttu-id="d2ff4-109">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-109">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="d2ff4-110">Zaznacz rolę, dla której chcesz skonfigurować regułę.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="d2ff4-111">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-111">In this example, select Accounting supervisor.</span></span> 
3. <span data-ttu-id="d2ff4-112">Kliknij **Dodaj zasadę**, aby otworzyć listę rozwijania.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-112">Click **Add rule** to open the drop dialog.</span></span>
4. <span data-ttu-id="d2ff4-113">Na liście **Wybierz kwerendę**odnajdź i wybierz odpowiednią pozycję.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-113">In the **Select a query**list, find and select the desired record.</span></span> <span data-ttu-id="d2ff4-114">Zaznacz zapytanie, którego chcesz używać dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="d2ff4-115">Na liście **Nazwa zasady członkowstwa** kliknij link w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-115">In the **Membership rule name** list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d2ff4-116">Kliknij **Edytuj kwerendę**.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-116">Click **Edit query**.</span></span> <span data-ttu-id="d2ff4-117">Edytuj kwerendę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="d2ff4-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-118">Click **OK**.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="d2ff4-119">Wykluczanie użytkowników z automatycznego przypisywania ról</span><span class="sxs-lookup"><span data-stu-id="d2ff4-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="d2ff4-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-120">Close the page.</span></span>
2. <span data-ttu-id="d2ff4-121">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-121">Go to **Navigation pane > Modules > System administration > Security > Assign users to roles**.</span></span>
3. <span data-ttu-id="d2ff4-122">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-122">In the tree, select 'Accounting supervisor'.</span></span> <span data-ttu-id="d2ff4-123">Służy do wybierania roli.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-123">Select a role.</span></span> <span data-ttu-id="d2ff4-124">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="d2ff4-125">W menu **Użytkownicy przypisani do roli** wybierz **Ręcznie przypisz / wyklucz użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-125">In the **Users assigned to role** menu, select **Manually assign / exclude users**.</span></span>
5. <span data-ttu-id="d2ff4-126">Na liście **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** zaznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-126">In the **Assign users to or exclude users from role** list, mark the selected row.</span></span> <span data-ttu-id="d2ff4-127">Wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-127">Select a user.</span></span>  
6. <span data-ttu-id="d2ff4-128">W **Panelu akcji** wybierz **Wyklucz z roli**.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-128">On the **Action pane**, select **Exclude from role**.</span></span>
    
    <span data-ttu-id="d2ff4-129">Kliknij **Wyklucz użytkowników z roli**, aby wykluczyć wybranych użytkowników z roli.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-129">Click **Exclude from role** to exclude the selected users from the role.</span></span> <span data-ttu-id="d2ff4-130">Żeby usunąć wykluczenia, wybierz użytkowników, których wyluczenia chcesz usunąć i kliknij **Zresetuj status**.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-130">To remove exclusions, select the users that you want to remove exclusions for, and then click **Reset status**.</span></span> <span data-ttu-id="d2ff4-131">Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="d2ff4-132">Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="d2ff4-133">Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  
