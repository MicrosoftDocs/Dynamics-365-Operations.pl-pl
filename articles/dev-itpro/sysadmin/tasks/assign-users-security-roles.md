--- 
title: "Przypisywanie użytkowników do ról zabezpieczeń"
description: "Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń."
author: maertenm
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 551048af26f46d334c562d1968963aed262a5e03
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="assign-users-to-security-roles"></a>Przypisywanie użytkowników do ról zabezpieczeń

[!include [task guide banner](../../includes/task-guide-banner.md)]

Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń. W tej procedurze pokazano, jak administratorzy systemu mogą przypisywać użytkowników do ról automatycznie, na podstawie danych biznesowych. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="automatically-assign-users-to-roles"></a>Automatyczne przypisywanie użytkowników do ról
1. Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.
2. W drzewie zaznacz rolę „Kierownik ds. księgowania”.
    * Zaznacz rolę, dla której chcesz skonfigurować regułę. W tym przykładzie wybierz rolę Kierownik ds. księgowania.  
3. Kliknij przycisk Dodaj regułę, aby otworzyć rozwijane okno dialogowe.
4. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz zapytanie, którego chcesz używać dla tej reguły.  
5. Na liście kliknij łącze w wybranym wierszu.
6. Kliknij opcję Edytuj kwerendę.
    * Edytuj kwerendę stosownie do potrzeb.  
7. Kliknij przycisk OK.

## <a name="exclude-users-from-automatic-role-assignment"></a>Wykluczanie użytkowników z automatycznego przypisywania ról
1. Zamknij stronę.
2. Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Przypisywanie użytkowników do ról.
3. W drzewie zaznacz rolę „Kierownik ds. księgowania”.
    * Służy do wybierania roli. W tym przykładzie wybierz rolę Kierownik ds. księgowania.  
4. Kliknij opcję Ręcznie przypisz/wyklucz użytkowników.
5. Na liście oznacz wybrany wiersz.
    * Wybierz użytkownika.  
6. Kliknij opcję Wyklucz z roli.
    * Kliknij opcję Wyklucz z roli, aby wykluczyć wybranych użytkowników z roli. Aby usunąć wykluczenia, zaznacz użytkowników, których wykluczenia chcesz usunąć, a następnie kliknij przycisk Resetuj stan. Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola. Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli. Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.  


