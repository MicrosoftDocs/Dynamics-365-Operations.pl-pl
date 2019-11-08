---
title: Nie można znaleźć użytkownika w selektorze osób w Attract lub Onboard
description: W tym temacie wyjaśniono, co zrobić, gdy użytkownicy w firmie dzierżawy nie są pokazywani w selektorze osób w Dynamics 365 Talent - Attract lub Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d84dd9c22738a1b4fc5edb5331d4aa213b82facb
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551940"
---
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a><span data-ttu-id="4d47f-103">Nie można znaleźć użytkownika w selektorze osób w Attract lub Onboard</span><span class="sxs-lookup"><span data-stu-id="4d47f-103">User not found in People Picker in Attract or Onboard</span></span>
[!include [banner](includes/banner.md)]

## <a name="issue"></a><span data-ttu-id="4d47f-104">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="4d47f-104">Issue</span></span>

<span data-ttu-id="4d47f-105">Niektórzy prawidłowi użytkownicy w Microsoft Azure Active Directory (Azure AD) dla dzierżawy nie pojawiają się przy wyszukiwaniu ich nazwiska w selektorze osób w Dynamics 365 Talent: Attract lub Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="4d47f-105">Certain valid users in Microsoft Azure Active Directory (Azure AD) for the tenant do not appear when searching for the name in the People Picker in Dynamics 365 Talent: Attract or Dynamics 365 Talent: Onboard.</span></span>

## <a name="cause"></a><span data-ttu-id="4d47f-106">Powód</span><span class="sxs-lookup"><span data-stu-id="4d47f-106">Cause</span></span>

<span data-ttu-id="4d47f-107">Niektóre typy użytkowników nie są obecnie obsługiwane w Attract i Onboard.</span><span class="sxs-lookup"><span data-stu-id="4d47f-107">Certain user types are not currently supported in Attract and Onboard.</span></span> <span data-ttu-id="4d47f-108">Sprawdź, czy użytkownik nie jest użytkownikiem-gościem Azure AD Business to Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="4d47f-108">Verify that the user is not an Azure AD Business to Business (B2B) guest user.</span></span> <span data-ttu-id="4d47f-109">Informacje „Typ użytkownika” znajdują się na karcie Azure Active Directory w portalu Azure.</span><span class="sxs-lookup"><span data-stu-id="4d47f-109">"User Type" information can be found in the Azure Active Directory blade on the Azure portal.</span></span>

<span data-ttu-id="4d47f-110">Aby uzyskać więcej informacji na temat Azure B2B, zobacz [Co to jest dostęp użytkownik-gość w Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span><span class="sxs-lookup"><span data-stu-id="4d47f-110">For more information about Azure B2B, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span>

<span data-ttu-id="4d47f-111">W przypadku użytkowników innych niż B2B niektórzy użytkownicy mogą mieć niekompletną właściwość „Typ użytkownika” w obiekcie **Użytkownik**.</span><span class="sxs-lookup"><span data-stu-id="4d47f-111">For non-B2B users, there are certain users who may have an incomplete "User Type" property on the **User** object.</span></span> <span data-ttu-id="4d47f-112">To może być zweryfikowane i naprawione za pomocą modułu Powershell Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4d47f-112">This can be verified and fixed using the Azure AD Powershell module.</span></span> <span data-ttu-id="4d47f-113">Aby uzyskać więcej informacji, zobacz [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="4d47f-113">For more information, see [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).</span></span>

## <a name="resolution"></a><span data-ttu-id="4d47f-114">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="4d47f-114">Resolution</span></span>

<span data-ttu-id="4d47f-115">Aby wykonać poniższe kroki w celu rozwiązania tego problemu, trzeba mieć uprawnienia „Administrator globalny” Azure Active Directory dzierżawy lub uprawnienia do **User.ReadWrite.All**.</span><span class="sxs-lookup"><span data-stu-id="4d47f-115">To complete the following steps to resolve the issue, you will need to have "Global Administrator" permissions on the Azure Active Directory tenant or permissions for **User.ReadWrite.All**.</span></span>

<span data-ttu-id="4d47f-116">Aby sprawdzić „Typ użytkownika” dla danego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4d47f-116">To verify the "User Type" for the affected user.</span></span>

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
<span data-ttu-id="4d47f-117">Polecenie zwraca następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="4d47f-117">The command returns the following information.</span></span>
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
<span data-ttu-id="4d47f-118">Należy zwrócić uwagę na właściwość **UserType** użytkownika.</span><span class="sxs-lookup"><span data-stu-id="4d47f-118">Note the **UserType** property on the user.</span></span> <span data-ttu-id="4d47f-119">Jeśli właściwość **UserType** jest pusta, na przykład nie jest to „Członek” ani „Gość”, należy zaktualizować **UserType** przy użyciu następującego polecenia.</span><span class="sxs-lookup"><span data-stu-id="4d47f-119">If the **UserType** is blank, for example not "Member" or "Guest", update the **UserType** using the following command.</span></span>

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
