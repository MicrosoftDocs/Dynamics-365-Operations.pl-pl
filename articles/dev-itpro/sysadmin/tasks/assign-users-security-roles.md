---
title: Przypisywanie użytkowników do ról zabezpieczeń
description: Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 55cb085bb5170aa4894a2240a12f6ca451b922fb
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "349959"
---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="6e6ef-103">Przypisywanie użytkowników do ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="6e6ef-103">Assign users to security roles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e6ef-104">Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="6e6ef-105">W tej procedurze pokazano, jak administratorzy systemu mogą przypisywać użytkowników do ról automatycznie, na podstawie danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="6e6ef-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="6e6ef-107">Automatyczne przypisywanie użytkowników do ról</span><span class="sxs-lookup"><span data-stu-id="6e6ef-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="6e6ef-108">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="6e6ef-109">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="6e6ef-110">Zaznacz rolę, dla której chcesz skonfigurować regułę.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="6e6ef-111">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="6e6ef-112">Kliknij przycisk Dodaj regułę, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="6e6ef-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6e6ef-114">Zaznacz zapytanie, którego chcesz używać dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="6e6ef-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6e6ef-116">Kliknij opcję Edytuj kwerendę.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-116">Click Edit query.</span></span>
    * <span data-ttu-id="6e6ef-117">Edytuj kwerendę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="6e6ef-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="6e6ef-119">Wykluczanie użytkowników z automatycznego przypisywania ról</span><span class="sxs-lookup"><span data-stu-id="6e6ef-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="6e6ef-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-120">Close the page.</span></span>
2. <span data-ttu-id="6e6ef-121">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="6e6ef-122">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="6e6ef-123">Służy do wybierania roli.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-123">Select a role.</span></span> <span data-ttu-id="6e6ef-124">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="6e6ef-125">Kliknij opcję Ręcznie przypisz/wyklucz użytkowników.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="6e6ef-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6e6ef-127">Wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-127">Select a user.</span></span>  
6. <span data-ttu-id="6e6ef-128">Kliknij opcję Wyklucz z roli.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="6e6ef-129">Kliknij opcję Wyklucz z roli, aby wykluczyć wybranych użytkowników z roli.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="6e6ef-130">Aby usunąć wykluczenia, zaznacz użytkowników, których wykluczenia chcesz usunąć, a następnie kliknij przycisk Resetuj stan.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="6e6ef-131">Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="6e6ef-132">Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="6e6ef-133">Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.</span><span class="sxs-lookup"><span data-stu-id="6e6ef-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  

