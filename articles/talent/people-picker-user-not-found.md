---
title: Nie można znaleźć użytkownika w selektorze osób w Attract lub Onboard
description: W tym temacie wyjaśniono, co zrobić, gdy użytkownicy w firmie dzierżawy nie są pokazywani w selektorze osób w aplikacjach Attract lub Onboard programu Dynamics 365 for Talent.
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
ms.openlocfilehash: d5a2c61fc21578d1db4c1bf0c3dfaf0c7a93298c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518830"
---
# <a name="azure-active-directory-users-not-found-in-people-picker"></a>Nie znaleziono użytkowników Azure Active Directory w selektorze osób

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Wystawienie

Niektórzy prawidłowi użytkownicy w Microsoft Azure Active Directory (Azure AD) dla dzierżawy nie pojawiają się przy wyszukiwaniu ich nazwiska w selektorze osób w aplikacjach Attract lub Onboard programu Dynamics 365 for Talent.

## <a name="cause"></a>Powód

Niektóre typy użytkowników nie są obecnie obsługiwane w aplikacjach Attract i Onboard. Sprawdź, czy użytkownik nie jest użytkownikiem-gościem Azure AD Business to Business (B2B). Informacje „Typ użytkownika” znajdują się na karcie Azure Active Directory w portalu Azure.

Aby uzyskać więcej informacji na temat Azure B2B, zobacz [Co to jest dostęp użytkownik-gość w Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b).

W przypadku użytkowników innych niż B2B niektórzy użytkownicy mogą mieć niekompletną właściwość „Typ użytkownika” w obiekcie **Użytkownik**. To może być zweryfikowane i naprawione za pomocą modułu Powershell Azure AD. Aby uzyskać więcej informacji, zobacz [Azure AD](https://docs.microsoft.com/en-us/powershell/module/azuread/?view=azureadps-2.0).

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
