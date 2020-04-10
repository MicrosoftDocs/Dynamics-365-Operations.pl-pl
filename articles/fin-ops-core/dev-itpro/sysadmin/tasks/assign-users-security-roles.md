---
title: Przypisywanie użytkowników do ról zabezpieczeń
description: Aby mieć dostęp do aplikacji Finance and Operations, użytkownicy muszą być przypisani do ról zabezpieczeń.
author: ChrisGarty
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0744f45ac91dfb9b5aae35091e3675202c9144f9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143566"
---
# <a name="assign-users-to-security-roles"></a>Przypisywanie użytkowników do ról zabezpieczeń

[!include [banner](../../includes/banner.md)]

Aby można było skorzystać z innych funkcji niż typowe, użytkownicy muszą być przypisani do ról zabezpieczeń. W tej procedurze pokazano, jak administratorzy systemu mogą automatycznie przypisywać użytkowników do ról, na podstawie danych biznesowych. 

## <a name="automatically-assign-users-to-roles"></a>Automatyczne przypisywanie użytkowników do ról
1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
2. W drzewie zaznacz rolę „Kierownik ds. księgowania”. Zaznacz rolę, dla której chcesz skonfigurować regułę. W tym przykładzie wybierz rolę Kierownik ds. księgowania. 
3. Kliknij **Dodaj zasadę**, aby otworzyć listę rozwijania.
4. Na liście **Wybierz kwerendę**odnajdź i wybierz odpowiednią pozycję. Zaznacz zapytanie, którego chcesz używać dla tej reguły.  
5. Na liście **Nazwa zasady członkowstwa** kliknij link w wybranym wierszu.
6. Kliknij **Edytuj kwerendę**. Edytuj kwerendę stosownie do potrzeb.  
7. Kliknij przycisk **OK**.
8. Kliknij **Uruchom automatyczne przypisanie roli**.
9. Przejdź do **Okienko nawigacji > Moduły > Administrowanie systemem > Użytkownicy > Użytkownicy** (najlepiej w osobnej karcie przeglądarki)
10. Przejrzyj role przypisane różnym użytkownikom, aby potwierdzić, że kwerenda przypisania roli była poprawna. W razie potrzeby skoryguj i uruchom ponownie.

## <a name="exclude-users-from-automatic-role-assignment"></a>Wykluczanie użytkowników z automatycznego przypisywania ról
1. Zamknij stronę.
2. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
3. W drzewie zaznacz rolę „Kierownik ds. księgowania”. Służy do wybierania roli. W tym przykładzie wybierz rolę Kierownik ds. księgowania.  
4. W menu **Użytkownicy przypisani do roli** wybierz **Ręcznie przypisz / wyklucz użytkowników**.
5. Na liście **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** zaznacz wybrany wiersz. Wybierz użytkownika.  
6. W **Panelu akcji** wybierz **Wyklucz z roli**.
    
    Kliknij **Wyklucz użytkowników z roli**, aby wykluczyć wybranych użytkowników z roli. Żeby usunąć wykluczenia, wybierz użytkowników, których wyluczenia chcesz usunąć i kliknij **Zresetuj status**. Po usunięciu wykluczenia poprzez zresetowanie stanu użytkownika zostanie mu automatycznie ponownie przypisana rola. Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli. Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.  
