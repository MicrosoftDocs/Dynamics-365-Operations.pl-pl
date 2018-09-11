--- 
title: "Przypisywanie użytkowników do ról zabezpieczeń"
description: "Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń."
author: maertenm
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: c08c9ee27bef3ec8c51df558766f55d3ea4ac48a
ms.contentlocale: pl-pl
ms.lasthandoff: 09/11/2018

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="81d36-103">Przypisywanie użytkowników do ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="81d36-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="81d36-104">Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="81d36-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="81d36-105">W tej procedurze pokazano, jak administratorzy systemu mogą przypisywać użytkowników do ról automatycznie, na podstawie danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="81d36-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="81d36-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="81d36-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="81d36-107">Automatyczne przypisywanie użytkowników do ról</span><span class="sxs-lookup"><span data-stu-id="81d36-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="81d36-108">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="81d36-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="81d36-109">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="81d36-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="81d36-110">Zaznacz rolę, dla której chcesz skonfigurować regułę.</span><span class="sxs-lookup"><span data-stu-id="81d36-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="81d36-111">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="81d36-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="81d36-112">Kliknij przycisk Dodaj regułę, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="81d36-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="81d36-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="81d36-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="81d36-114">Zaznacz zapytanie, którego chcesz używać dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="81d36-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="81d36-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="81d36-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="81d36-116">Kliknij opcję Edytuj kwerendę.</span><span class="sxs-lookup"><span data-stu-id="81d36-116">Click Edit query.</span></span>
    * <span data-ttu-id="81d36-117">Edytuj kwerendę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="81d36-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="81d36-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="81d36-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="81d36-119">Wykluczanie użytkowników z automatycznego przypisywania ról</span><span class="sxs-lookup"><span data-stu-id="81d36-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="81d36-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="81d36-120">Close the page.</span></span>
2. <span data-ttu-id="81d36-121">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="81d36-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="81d36-122">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="81d36-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="81d36-123">Służy do wybierania roli.</span><span class="sxs-lookup"><span data-stu-id="81d36-123">Select a role.</span></span> <span data-ttu-id="81d36-124">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="81d36-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="81d36-125">Kliknij opcję Ręcznie przypisz/wyklucz użytkowników.</span><span class="sxs-lookup"><span data-stu-id="81d36-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="81d36-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="81d36-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="81d36-127">Wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="81d36-127">Select a user.</span></span>  
6. <span data-ttu-id="81d36-128">Kliknij opcję Wyklucz z roli.</span><span class="sxs-lookup"><span data-stu-id="81d36-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="81d36-129">Kliknij opcję Wyklucz z roli, aby wykluczyć wybranych użytkowników z roli.</span><span class="sxs-lookup"><span data-stu-id="81d36-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="81d36-130">Aby usunąć wykluczenia, zaznacz użytkowników, których wykluczenia chcesz usunąć, a następnie kliknij przycisk Resetuj stan.</span><span class="sxs-lookup"><span data-stu-id="81d36-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="81d36-131">Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola.</span><span class="sxs-lookup"><span data-stu-id="81d36-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="81d36-132">Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli.</span><span class="sxs-lookup"><span data-stu-id="81d36-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="81d36-133">Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.</span><span class="sxs-lookup"><span data-stu-id="81d36-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


