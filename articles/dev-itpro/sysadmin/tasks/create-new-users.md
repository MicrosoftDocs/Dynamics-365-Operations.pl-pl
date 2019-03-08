---
title: Tworzenie nowych użytkowników
description: Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12cf223d262c4e0f2a195e95c83a00fc1a3f07e5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "361965"
---
# <a name="create-new-users"></a><span data-ttu-id="d0603-103">Tworzenie nowych użytkowników</span><span class="sxs-lookup"><span data-stu-id="d0603-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d0603-104">Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.</span><span class="sxs-lookup"><span data-stu-id="d0603-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="d0603-105">Administratorzy systemu mogą wykonać tę procedurę, aby dodać użytkowników do systemu.</span><span class="sxs-lookup"><span data-stu-id="d0603-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="d0603-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="d0603-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="d0603-107">Dodawanie nowego użytkownika</span><span class="sxs-lookup"><span data-stu-id="d0603-107">Add a new user</span></span>
1. <span data-ttu-id="d0603-108">Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.</span><span class="sxs-lookup"><span data-stu-id="d0603-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="d0603-109">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="d0603-109">Click New.</span></span>
3. <span data-ttu-id="d0603-110">W polu Identyfikator użytkownika wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0603-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="d0603-111">Wprowadź unikatowy identyfikator użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0603-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="d0603-112">Identyfikator użytkownika jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="d0603-112">A user ID is required.</span></span>  
4. <span data-ttu-id="d0603-113">W polu Nazwa użytkownika wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0603-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="d0603-114">Wprowadź nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0603-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="d0603-115">W polu Domena wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0603-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="d0603-116">Wprowadź domenę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0603-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="d0603-117">W polu Alias wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="d0603-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="d0603-118">Wprowadź alias użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0603-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="d0603-119">W polu Firma kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="d0603-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="d0603-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d0603-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="d0603-121">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="d0603-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d0603-122">Wybierz firmę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="d0603-122">Select the user's company</span></span>  
10. <span data-ttu-id="d0603-123">Kliknij opcję Przypisz role.</span><span class="sxs-lookup"><span data-stu-id="d0603-123">Click Assign roles.</span></span>
11. <span data-ttu-id="d0603-124">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="d0603-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="d0603-125">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="d0603-125">Click OK.</span></span>
13. <span data-ttu-id="d0603-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="d0603-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="d0603-127">Importuj użytkowników</span><span class="sxs-lookup"><span data-stu-id="d0603-127">Import users</span></span>
1. <span data-ttu-id="d0603-128">Kliknij opcję Importuj użytkowników.</span><span class="sxs-lookup"><span data-stu-id="d0603-128">Click Import users.</span></span>
2. <span data-ttu-id="d0603-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="d0603-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="d0603-130">Kliknij opcję Importuj użytkowników.</span><span class="sxs-lookup"><span data-stu-id="d0603-130">Click Import users.</span></span>
4. <span data-ttu-id="d0603-131">Kliknij przycisk Zamknij.</span><span class="sxs-lookup"><span data-stu-id="d0603-131">Click Close.</span></span>

