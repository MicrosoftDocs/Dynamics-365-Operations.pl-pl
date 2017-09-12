--- 
title: "Przypisywanie użytkowników do ról zabezpieczeń"
description: "Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń."
author: maertenm
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 551048af26f46d334c562d1968963aed262a5e03
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="e1473-103">Przypisywanie użytkowników do ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="e1473-103">Assign users to security roles</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e1473-104">Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="e1473-104">To access Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, users must be assigned to security roles.</span></span> <span data-ttu-id="e1473-105">W tej procedurze pokazano, jak administratorzy systemu mogą przypisywać użytkowników do ról automatycznie, na podstawie danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="e1473-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="e1473-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e1473-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="e1473-107">Automatyczne przypisywanie użytkowników do ról</span><span class="sxs-lookup"><span data-stu-id="e1473-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="e1473-108">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="e1473-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="e1473-109">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="e1473-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="e1473-110">Zaznacz rolę, dla której chcesz skonfigurować regułę.</span><span class="sxs-lookup"><span data-stu-id="e1473-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="e1473-111">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="e1473-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="e1473-112">Kliknij przycisk Dodaj regułę, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="e1473-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="e1473-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="e1473-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e1473-114">Zaznacz zapytanie, którego chcesz używać dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="e1473-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="e1473-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="e1473-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="e1473-116">Kliknij opcję Edytuj kwerendę.</span><span class="sxs-lookup"><span data-stu-id="e1473-116">Click Edit query.</span></span>
    * <span data-ttu-id="e1473-117">Edytuj kwerendę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="e1473-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="e1473-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e1473-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="e1473-119">Wykluczanie użytkowników z automatycznego przypisywania ról</span><span class="sxs-lookup"><span data-stu-id="e1473-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="e1473-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="e1473-120">Close the page.</span></span>
2. <span data-ttu-id="e1473-121">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="e1473-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="e1473-122">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="e1473-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="e1473-123">Służy do wybierania roli.</span><span class="sxs-lookup"><span data-stu-id="e1473-123">Select a role.</span></span> <span data-ttu-id="e1473-124">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="e1473-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="e1473-125">Kliknij opcję Ręcznie przypisz/wyklucz użytkowników.</span><span class="sxs-lookup"><span data-stu-id="e1473-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="e1473-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="e1473-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e1473-127">Wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="e1473-127">Select a user.</span></span>  
6. <span data-ttu-id="e1473-128">Kliknij opcję Wyklucz z roli.</span><span class="sxs-lookup"><span data-stu-id="e1473-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="e1473-129">Kliknij opcję Wyklucz z roli, aby wykluczyć wybranych użytkowników z roli.</span><span class="sxs-lookup"><span data-stu-id="e1473-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="e1473-130">Aby usunąć wykluczenia, zaznacz użytkowników, których wykluczenia chcesz usunąć, a następnie kliknij przycisk Resetuj stan.</span><span class="sxs-lookup"><span data-stu-id="e1473-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="e1473-131">Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola.</span><span class="sxs-lookup"><span data-stu-id="e1473-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="e1473-132">Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli.</span><span class="sxs-lookup"><span data-stu-id="e1473-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="e1473-133">Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.</span><span class="sxs-lookup"><span data-stu-id="e1473-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


