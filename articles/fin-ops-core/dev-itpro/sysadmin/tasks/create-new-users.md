---
title: Tworzenie nowych użytkowników
description: Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.
author: maertenm
manager: AnnBe
ms.date: 10/08/2019
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
ms.openlocfilehash: 3c347a34a389c32d005cc8086c4a1349ecb8a698
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570528"
---
# <a name="create-new-users"></a><span data-ttu-id="67656-103">Tworzenie nowych użytkowników</span><span class="sxs-lookup"><span data-stu-id="67656-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="67656-104">Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu do swoich zadań.</span><span class="sxs-lookup"><span data-stu-id="67656-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="67656-105">Skojarz użytkownika z licencją (tylko nowe typy licencji)</span><span class="sxs-lookup"><span data-stu-id="67656-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="67656-106">W przypadku klientów, którzy znajdują się w jednym z nowych typów licencji dodanych w październiku 2019, użytkownicy muszą być powiązani z licencją.</span><span class="sxs-lookup"><span data-stu-id="67656-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="67656-107">Użytkownicy, którzy są powiązani z licencją, są automatycznie dodawani jako użytkownicy systemu, którzy nie mają ról przy pierwszym logowaniu.</span><span class="sxs-lookup"><span data-stu-id="67656-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span> <span data-ttu-id="67656-108">W przypadku użytkowników, którzy nie są powiązani z licencją, pojawia się komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="67656-108">Users who aren't associated with a licence receive a warning message.</span></span>

<span data-ttu-id="67656-109">Administratorzy systemów mogą [przypisywać licencje do użytkowników](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) w [centrum administracyjnym Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="67656-109">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="67656-110">Dodawanie nowego użytkownika</span><span class="sxs-lookup"><span data-stu-id="67656-110">Add a new user</span></span>
1. <span data-ttu-id="67656-111">Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="67656-111">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="67656-112">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="67656-112">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="67656-113">W polu **Identyfikator użytkownika** wprowadź unikatowy identyfikator dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="67656-113">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="67656-114">Identyfikator użytkownika jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="67656-114">A user ID is required.</span></span>  
4. <span data-ttu-id="67656-115">W polu **Nazwa użytkownika** wprowadź nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="67656-115">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="67656-116">W polu **Domena** wprowadź domenę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="67656-116">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="67656-117">W polu **Alias** wprowadź alias użytkownika.</span><span class="sxs-lookup"><span data-stu-id="67656-117">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="67656-118">W polu **Firma** wybierz pożądaną firmę.</span><span class="sxs-lookup"><span data-stu-id="67656-118">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="67656-119">Na skróconej karcie **Role użytkownika** wybierz opcję **Przypisz role**, aby [przypisać użytkowników do ról zabezpieczeń](assign-users-security-roles.md)</span><span class="sxs-lookup"><span data-stu-id="67656-119">On the **User's roles** FastTab, select **Assign roles** to [assign users to security roles](assign-users-security-roles.md)</span></span>
9. <span data-ttu-id="67656-120">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="67656-120">Select **OK**.</span></span>
10. <span data-ttu-id="67656-121">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="67656-121">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="67656-122">Importuj użytkowników</span><span class="sxs-lookup"><span data-stu-id="67656-122">Import users</span></span>
1. <span data-ttu-id="67656-123">W okienku akcji wybierz pozycję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="67656-123">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="67656-124">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="67656-124">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="67656-125">Wybierz **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="67656-125">Select **Import users**.</span></span>
4. <span data-ttu-id="67656-126">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="67656-126">Select **Close**.</span></span>

