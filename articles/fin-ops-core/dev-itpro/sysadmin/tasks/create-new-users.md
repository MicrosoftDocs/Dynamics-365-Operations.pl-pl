---
title: Tworzenie nowych użytkowników
description: Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.
author: peakerbl
manager: AnnBe
ms.date: 06/08/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f861b7493d039b332358be7df7d0198cbadcb7a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679847"
---
# <a name="create-new-users"></a>Tworzenie nowych użytkowników

[!include [banner](../../includes/banner.md)]

Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu do swoich zadań.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Skojarz użytkownika z licencją (tylko nowe typy licencji)
W przypadku klientów, którzy znajdują się w jednym z nowych typów licencji dodanych w październiku 2019, użytkownicy muszą być powiązani z licencją. Użytkownicy, którzy są powiązani z licencją, są automatycznie dodawani jako użytkownicy systemu, którzy nie mają ról przy pierwszym logowaniu.

Administratorzy systemów mogą [przypisywać licencje do użytkowników](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) w [centrum administracyjnym Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a>Skojarz zewnętrznego użytkownika z licencją (tylko nowe typy licencji)
Użytkownicy zewnętrzni dla dzierżawy, na którą wdrożono środowisko, muszą być reprezentowani w katalogu dzierżawy hosta (Azure Active Directory (Azure AD)), tak aby mogli oni przypisywać licencje. Użytkownicy zewnętrzni powinni zostać dodani do dzierżawy Azure AD jako użytkownik gość, a następnie przypisani do odpowiednich licencji. Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie użytkowników współpracy w module B2B Azure Active Directory w portalu Azure Portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="add-a-new-user"></a>Dodawanie nowego użytkownika
1. Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Identyfikator użytkownika** wprowadź unikatowy identyfikator dla użytkownika. Identyfikator użytkownika jest wymagany.  
4. W polu **Nazwa użytkownika** wprowadź nazwę użytkownika.  
5. W polu **Domena** wprowadź domenę użytkownika.  
6. W polu **Alias** wprowadź alias użytkownika.  
7. W polu **Firma** wybierz pożądaną firmę. 
8. Na skróconej karcie **Role użytkownika** wybierz opcję **Przypisz role**, aby przypisać użytkowników do ról zabezpieczeń. Więcej informacji można znaleźć w [Przypisywanie użytkowników do ról zabezpieczeń](assign-users-security-roles.md).
9. Kliknij przycisk **OK**.
10. Wybierz opcję **Zapisz**.

## <a name="import-users"></a>Importuj użytkowników
1. Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
2. W okienku akcji wybierz pozycję **Importuj użytkowników**.
3. Na liście oznacz wybrany wiersz.
4. Wybierz **Importuj użytkowników**.
5. Kliknij przycisk **Zamknij**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]