---
title: Tworzenie nowych użytkowników
description: Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.
author: maertenm
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a542ece226750330262e0c44427e5654fa4f6369
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916491"
---
# <a name="create-new-users"></a><span data-ttu-id="6d3e6-103">Tworzenie nowych użytkowników</span><span class="sxs-lookup"><span data-stu-id="6d3e6-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6d3e6-104">Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="6d3e6-105">Administratorzy systemu mogą wykonać tę procedurę, aby dodać użytkowników do systemu.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="6d3e6-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="6d3e6-107">Dodawanie nowego użytkownika</span><span class="sxs-lookup"><span data-stu-id="6d3e6-107">Add a new user</span></span>
1. <span data-ttu-id="6d3e6-108">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Użytkownicy > Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-108">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="6d3e6-109">W **okienku akcji** kliknij **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-109">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="6d3e6-110">W polu **Identyfikator użytkownika** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-110">In the **User ID** field, type a value.</span></span> <span data-ttu-id="6d3e6-111">Wprowadź unikatowy identyfikator użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="6d3e6-112">Identyfikator użytkownika jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-112">A user ID is required.</span></span>  
4. <span data-ttu-id="6d3e6-113">W polu **Nazwa użytkownika** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-113">In the **User name** field, type a value.</span></span> <span data-ttu-id="6d3e6-114">Wprowadź nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="6d3e6-115">W polu **Domena** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-115">In the **Domain** field, type a value.</span></span> <span data-ttu-id="6d3e6-116">Wprowadź domenę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="6d3e6-117">W polu **Alias** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-117">In the **Alias** field, type a value.</span></span> <span data-ttu-id="6d3e6-118">Wprowadź alias użytkownika.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="6d3e6-119">W polu **Firma** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-119">In the **Company** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="6d3e6-120">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-120">In the list, find and select the desired record.</span></span> 
9. <span data-ttu-id="6d3e6-121">W sekcji **Role użytkownika** kliknij opcję **Przypisz role**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-121">In the **User's roles** section, click **Assign roles**.</span></span>
10. <span data-ttu-id="6d3e6-122">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-122">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="6d3e6-123">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-123">Click **OK**.</span></span>
12. <span data-ttu-id="6d3e6-124">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-124">Click **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="6d3e6-125">Importuj użytkowników</span><span class="sxs-lookup"><span data-stu-id="6d3e6-125">Import users</span></span>
1. <span data-ttu-id="6d3e6-126">W **okienku akcji** kliknij pozycję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-126">On the **Action pane**, click **Import users**.</span></span>
2. <span data-ttu-id="6d3e6-127">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-127">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="6d3e6-128">Kliknij opcję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-128">Click **Import users**.</span></span>
4. <span data-ttu-id="6d3e6-129">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="6d3e6-129">Click **Close**.</span></span>

