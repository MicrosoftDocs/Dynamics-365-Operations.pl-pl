---
title: Przypisywanie użytkowników do ról zabezpieczeń
description: Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab9f2f5ea07ae1d616c48dffa8810b966f7dbb2f
ms.sourcegitcommit: 33e98f89294086334fe9c0a350abb6a52ef9dacb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/28/2019
ms.locfileid: "1711138"
---
# <a name="assign-users-to-security-roles"></a>Przypisywanie użytkowników do ról zabezpieczeń

[!include [task guide banner](../../includes/task-guide-banner.md)]

Aby mieć dostęp do programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, użytkownicy muszą być przypisani do ról zabezpieczeń. W tej procedurze pokazano, jak administratorzy systemu mogą przypisywać użytkowników do ról automatycznie, na podstawie danych biznesowych. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="automatically-assign-users-to-roles"></a>Automatyczne przypisywanie użytkowników do ról
1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
2. W drzewie zaznacz rolę „Kierownik ds. księgowania”. Zaznacz rolę, dla której chcesz skonfigurować regułę. W tym przykładzie wybierz rolę Kierownik ds. księgowania. 
3. Kliknij **Dodaj zasadę**, aby otworzyć listę rozwijania.
4. Na liście **Wybierz kwerendę**odnajdź i wybierz odpowiednią pozycję. Zaznacz zapytanie, którego chcesz używać dla tej reguły.  
5. Na liście **Nazwa zasady członkowstwa** kliknij link w wybranym wierszu.
6. Kliknij **Edytuj kwerendę**. Edytuj kwerendę stosownie do potrzeb.  
7. Kliknij przycisk **OK**.

## <a name="exclude-users-from-automatic-role-assignment"></a>Wykluczanie użytkowników z automatycznego przypisywania ról
1. Zamknij stronę.
2. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
3. W drzewie zaznacz rolę „Kierownik ds. księgowania”. Służy do wybierania roli. W tym przykładzie wybierz rolę Kierownik ds. księgowania.  
4. W menu **Użytkownicy przypisani do roli** wybierz **Ręcznie przypisz / wyklucz użytkowników**.
5. Na liście **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** zaznacz wybrany wiersz. Wybierz użytkownika.  
6. W **Panelu akcji** wybierz **Wyklucz z roli**.
    
    Kliknij **Wyklucz użytkowników z roli**, aby wykluczyć wybranych użytkowników z roli. Żeby usunąć wykluczenia, wybierz użytkowników, których wyluczenia chcesz usunąć i kliknij **Zresetuj status**. Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola. Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli. Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.  
