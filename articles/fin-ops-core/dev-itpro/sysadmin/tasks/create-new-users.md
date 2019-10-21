---
title: Tworzenie nowych użytkowników
description: Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.
author: maertenm
manager: AnnBe
ms.date: 08/30/2019
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
ms.openlocfilehash: 4a5635f96132b2e52227b569e7e480fa55e82d61
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180951"
---
# <a name="create-new-users"></a>Tworzenie nowych użytkowników

[!include [task guide banner](../../includes/task-guide-banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu do swoich zadań.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Skojarz użytkownika z licencją (tylko nowe typy licencji)
W przypadku klientów, którzy znajdują się w jednym z nowych typów licencji dodanych w październiku 2019, użytkownicy muszą być powiązani z licencją. Użytkownicy, którzy są powiązani z licencją, są automatycznie dodawani jako użytkownicy systemu, którzy nie mają ról przy pierwszym logowaniu. W przypadku użytkowników, którzy nie są powiązani z licencją, pojawia się komunikat ostrzegawczy.

Administratorzy systemów mogą [przypisywać licencje do użytkowników](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) w [centrum administracyjnym Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-a-new-user"></a>Dodawanie nowego użytkownika
1. Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Identyfikator użytkownika** wprowadź unikatowy identyfikator dla użytkownika. Identyfikator użytkownika jest wymagany.  
4. W polu **Nazwa użytkownika** wprowadź nazwę użytkownika.  
5. W polu **Domena** wprowadź domenę użytkownika.  
6. W polu **Alias** wprowadź alias użytkownika.  
7. W polu **Firma** wybierz pożądaną firmę. 
8. Na skróconej karcie **Role użytkownika** wybierz opcję **Przypisz role**, aby [przypisać użytkowników do ról zabezpieczeń](assign-users-security-roles.md)
9. Kliknij przycisk **OK**.
10. Wybierz opcję **Zapisz**.

## <a name="import-users"></a>Importuj użytkowników
1. W okienku akcji wybierz pozycję **Importuj użytkowników**.
2. Na liście oznacz wybrany wiersz.
3. Wybierz **Importuj użytkowników**.
4. Kliknij przycisk **Zamknij**.

