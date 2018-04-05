--- 
title: "Przypisywanie użytkowników do ról zabezpieczeń"
description: "Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations, użytkownicy muszą być przypisani do ról zabezpieczeń."
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: da96ec8357ea209fd958e32ab438b13e668735df
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---
# <a name="assign-users-to-security-roles"></a><span data-ttu-id="4fad1-103">Przypisywanie użytkowników do ról zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="4fad1-103">Assign users to security roles</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4fad1-104">Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations, użytkownicy muszą być przypisani do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="4fad1-104">To access Microsoft Dynamics 365 for Finance and Operations, users must be assigned to security roles.</span></span> <span data-ttu-id="4fad1-105">W tej procedurze pokazano, jak administratorzy systemu mogą przypisywać użytkowników do ról automatycznie, na podstawie danych biznesowych.</span><span class="sxs-lookup"><span data-stu-id="4fad1-105">This procedure explains how system administrators can assign users to roles automatically, based on business data.</span></span> <span data-ttu-id="4fad1-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="4fad1-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="automatically-assign-users-to-roles"></a><span data-ttu-id="4fad1-107">Automatyczne przypisywanie użytkowników do ról</span><span class="sxs-lookup"><span data-stu-id="4fad1-107">Automatically assign users to roles</span></span>
1. <span data-ttu-id="4fad1-108">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="4fad1-108">Go to System administration > Security > Assign users to roles.</span></span>
2. <span data-ttu-id="4fad1-109">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="4fad1-109">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="4fad1-110">Zaznacz rolę, dla której chcesz skonfigurować regułę.</span><span class="sxs-lookup"><span data-stu-id="4fad1-110">Select the role that you want to configure the rule for.</span></span> <span data-ttu-id="4fad1-111">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="4fad1-111">In this example, select Accounting supervisor.</span></span>  
3. <span data-ttu-id="4fad1-112">Kliknij przycisk Dodaj regułę, aby otworzyć rozwijane okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="4fad1-112">Click Add rule to open the drop dialog.</span></span>
4. <span data-ttu-id="4fad1-113">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="4fad1-113">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4fad1-114">Zaznacz zapytanie, którego chcesz używać dla tej reguły.</span><span class="sxs-lookup"><span data-stu-id="4fad1-114">Select the query to use for this rule.</span></span>  
5. <span data-ttu-id="4fad1-115">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="4fad1-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4fad1-116">Kliknij opcję Edytuj kwerendę.</span><span class="sxs-lookup"><span data-stu-id="4fad1-116">Click Edit query.</span></span>
    * <span data-ttu-id="4fad1-117">Edytuj kwerendę stosownie do potrzeb.</span><span class="sxs-lookup"><span data-stu-id="4fad1-117">Edit the query, as needed.</span></span>  
7. <span data-ttu-id="4fad1-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="4fad1-118">Click OK.</span></span>

## <a name="exclude-users-from-automatic-role-assignment"></a><span data-ttu-id="4fad1-119">Wykluczanie użytkowników z automatycznego przypisywania ról</span><span class="sxs-lookup"><span data-stu-id="4fad1-119">Exclude users from automatic role assignment</span></span>
1. <span data-ttu-id="4fad1-120">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="4fad1-120">Close the page.</span></span>
2. <span data-ttu-id="4fad1-121">Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.</span><span class="sxs-lookup"><span data-stu-id="4fad1-121">Go to System administration > Security > Assign users to roles.</span></span>
3. <span data-ttu-id="4fad1-122">W drzewie zaznacz rolę „Kierownik ds. księgowania”.</span><span class="sxs-lookup"><span data-stu-id="4fad1-122">In the tree, select 'Accounting supervisor'.</span></span>
    * <span data-ttu-id="4fad1-123">Służy do wybierania roli.</span><span class="sxs-lookup"><span data-stu-id="4fad1-123">Select a role.</span></span> <span data-ttu-id="4fad1-124">W tym przykładzie wybierz rolę Kierownik ds. księgowania.</span><span class="sxs-lookup"><span data-stu-id="4fad1-124">For this example, select Accounting supervisor.</span></span>  
4. <span data-ttu-id="4fad1-125">Kliknij opcję Ręcznie przypisz/wyklucz użytkowników.</span><span class="sxs-lookup"><span data-stu-id="4fad1-125">Click Manually assign / exclude users.</span></span>
5. <span data-ttu-id="4fad1-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="4fad1-126">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4fad1-127">Wybierz użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4fad1-127">Select a user.</span></span>  
6. <span data-ttu-id="4fad1-128">Kliknij opcję Wyklucz z roli.</span><span class="sxs-lookup"><span data-stu-id="4fad1-128">Click Exclude from role.</span></span>
    * <span data-ttu-id="4fad1-129">Kliknij opcję Wyklucz z roli, aby wykluczyć wybranych użytkowników z roli.</span><span class="sxs-lookup"><span data-stu-id="4fad1-129">Click Exclude from role to exclude the selected users from the role.</span></span> <span data-ttu-id="4fad1-130">Aby usunąć wykluczenia, zaznacz użytkowników, których wykluczenia chcesz usunąć, a następnie kliknij przycisk Resetuj stan.</span><span class="sxs-lookup"><span data-stu-id="4fad1-130">To remove exclusions, select the users that you want to remove exclusions for, and then click Reset status.</span></span> <span data-ttu-id="4fad1-131">Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola.</span><span class="sxs-lookup"><span data-stu-id="4fad1-131">When you remove an exclusion by resetting the user’s status, the user’s role is again assigned automatically.</span></span> <span data-ttu-id="4fad1-132">Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli.</span><span class="sxs-lookup"><span data-stu-id="4fad1-132">However, the user is not immediately assigned to the role or excluded from the role when you reset the status.</span></span> <span data-ttu-id="4fad1-133">Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.</span><span class="sxs-lookup"><span data-stu-id="4fad1-133">Instead, the user is either assigned to the role or removed from the role the next time that the rules for automatic role assignment are run.</span></span>  


