---
title: Tworzenie nowych użytkowników
description: Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.
author: maertenm
manager: AnnBe
ms.date: 06/08/2020
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
ms.openlocfilehash: d126b449074663772549b96b86acb53db971a5d4
ms.sourcegitcommit: 7d943499f302298c6ff127f56cecc34af6cee289
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435591"
---
# <a name="create-new-users"></a><span data-ttu-id="c2111-103">Tworzenie nowych użytkowników</span><span class="sxs-lookup"><span data-stu-id="c2111-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c2111-104">Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu do swoich zadań.</span><span class="sxs-lookup"><span data-stu-id="c2111-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="c2111-105">Skojarz użytkownika z licencją (tylko nowe typy licencji)</span><span class="sxs-lookup"><span data-stu-id="c2111-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="c2111-106">W przypadku klientów, którzy znajdują się w jednym z nowych typów licencji dodanych w październiku 2019, użytkownicy muszą być powiązani z licencją.</span><span class="sxs-lookup"><span data-stu-id="c2111-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="c2111-107">Użytkownicy, którzy są powiązani z licencją, są automatycznie dodawani jako użytkownicy systemu, którzy nie mają ról przy pierwszym logowaniu.</span><span class="sxs-lookup"><span data-stu-id="c2111-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span>

<span data-ttu-id="c2111-108">Administratorzy systemów mogą [przypisywać licencje do użytkowników](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) w [centrum administracyjnym Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c2111-108">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a><span data-ttu-id="c2111-109">Skojarz zewnętrznego użytkownika z licencją (tylko nowe typy licencji)</span><span class="sxs-lookup"><span data-stu-id="c2111-109">Associate an external user with a license (new license types only)</span></span>
<span data-ttu-id="c2111-110">Użytkownicy zewnętrzni dla dzierżawy, na którą wdrożono środowisko, muszą być reprezentowani w katalogu dzierżawy hosta (Azure Active Directory (Azure AD)), tak aby mogli oni przypisywać licencje.</span><span class="sxs-lookup"><span data-stu-id="c2111-110">Users external to the tenant that the environment was deployed into need to be represented in the host tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="c2111-111">Użytkownicy zewnętrzni powinni zostać dodani do dzierżawy Azure AD jako użytkownik gość, a następnie przypisani do odpowiednich licencji.</span><span class="sxs-lookup"><span data-stu-id="c2111-111">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="c2111-112">Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie użytkowników współpracy w module B2B Azure Active Directory w portalu Azure Portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="c2111-112">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="c2111-113">Dodawanie nowego użytkownika</span><span class="sxs-lookup"><span data-stu-id="c2111-113">Add a new user</span></span>
1. <span data-ttu-id="c2111-114">Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="c2111-114">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="c2111-115">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c2111-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="c2111-116">W polu **Identyfikator użytkownika** wprowadź unikatowy identyfikator dla użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c2111-116">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="c2111-117">Identyfikator użytkownika jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="c2111-117">A user ID is required.</span></span>  
4. <span data-ttu-id="c2111-118">W polu **Nazwa użytkownika** wprowadź nazwę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c2111-118">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="c2111-119">W polu **Domena** wprowadź domenę użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c2111-119">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="c2111-120">W polu **Alias** wprowadź alias użytkownika.</span><span class="sxs-lookup"><span data-stu-id="c2111-120">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="c2111-121">W polu **Firma** wybierz pożądaną firmę.</span><span class="sxs-lookup"><span data-stu-id="c2111-121">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="c2111-122">Na skróconej karcie **Role użytkownika** wybierz opcję **Przypisz role**, aby przypisać użytkowników do ról zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c2111-122">On the **User's roles** FastTab, select **Assign roles** to assign users to security roles.</span></span> <span data-ttu-id="c2111-123">Więcej informacji można znaleźć w [Przypisywanie użytkowników do ról zabezpieczeń](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c2111-123">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span>
9. <span data-ttu-id="c2111-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2111-124">Select **OK**.</span></span>
10. <span data-ttu-id="c2111-125">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c2111-125">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="c2111-126">Importuj użytkowników</span><span class="sxs-lookup"><span data-stu-id="c2111-126">Import users</span></span>
1. <span data-ttu-id="c2111-127">Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.</span><span class="sxs-lookup"><span data-stu-id="c2111-127">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="c2111-128">W okienku akcji wybierz pozycję **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="c2111-128">On the Action Pane, select **Import users**.</span></span>
3. <span data-ttu-id="c2111-129">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="c2111-129">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="c2111-130">Wybierz **Importuj użytkowników**.</span><span class="sxs-lookup"><span data-stu-id="c2111-130">Select **Import users**.</span></span>
5. <span data-ttu-id="c2111-131">Kliknij przycisk **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="c2111-131">Select **Close**.</span></span>

