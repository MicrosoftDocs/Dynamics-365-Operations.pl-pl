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
# <a name="user-not-found-in-people-picker-in-attract-or-onboard"></a>Nie można znaleźć użytkownika w selektorze osób w Attract lub Onboard
[!include [banner](includes/banner.md)]

## <a name="issue"></a>Wystawienie

Niektórzy prawidłowi użytkownicy w Microsoft Azure Active Directory (Azure AD) dla dzierżawy nie pojawiają się przy wyszukiwaniu ich nazwiska w selektorze osób w Dynamics 365 Talent: Attract lub Dynamics 365 Talent: Onboard.

## <a name="cause"></a>Powód

Niektóre typy użytkowników nie są obecnie obsługiwane w Attract i Onboard. Sprawdź, czy użytkownik nie jest użytkownikiem-gościem Azure AD Business to Business (B2B). Informacje „Typ użytkownika” znajdują się na karcie Azure Active Directory w portalu Azure.

Aby uzyskać więcej informacji na temat Azure B2B, zobacz [Co to jest dostęp użytkownik-gość w Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).

W przypadku użytkowników innych niż B2B niektórzy użytkownicy mogą mieć niekompletną właściwość „Typ użytkownika” w obiekcie **Użytkownik**. To może być zweryfikowane i naprawione za pomocą modułu Powershell Azure AD. Aby uzyskać więcej informacji, zobacz [Azure AD](https://docs.microsoft.com/powershell/module/azuread/?view=azureadps-2.0).

## <a name="resolution"></a>Rozdzielczość

Aby wykonać poniższe kroki w celu rozwiązania tego problemu, trzeba mieć uprawnienia „Administrator globalny” Azure Active Directory dzierżawy lub uprawnienia do **User.ReadWrite.All**.

Aby sprawdzić „Typ użytkownika” dla danego użytkownika.

```
PS C:\>Get-AzureADUser -ObjectId "testUpn@tenant.com"
```
Polecenie zwraca następujące informacje.
```
ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
5e8b0f4d-2cd4-4e17-9467-b0f6a5c0c4d0 New user    testUpn@tenant.com     
```
Należy zwrócić uwagę na właściwość **UserType** użytkownika. Jeśli właściwość **UserType** jest pusta, na przykład nie jest to „Członek” ani „Gość”, należy zaktualizować **UserType** przy użyciu następującego polecenia.

```
PS C:\>Set-AzureADUser -ObjectId "testUpn@tenant.com" -UserType Member
```
