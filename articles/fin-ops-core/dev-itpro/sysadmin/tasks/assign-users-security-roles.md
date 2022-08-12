---
title: Przypisywanie użytkowników do ról zabezpieczeń
description: Aby mieć dostęp do aplikacji finansowych i operacyjnych, użytkownicy muszą być przypisani do ról zabezpieczeń.
author: Peakerbl
ms.date: 02/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecRolesEditUsers, SysSecAssignmentQueryLookup, SysQueryForm, SysSecRoleExcludeUsers
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5e69a79f123daff3f85d0100647615ad818288e
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103877"
---
# <a name="manage-users-and-security-roles"></a>Zarządzaj użytkownikami i rolami bezpieczeństwa

[!include [banner](../../includes/banner.md)]

Aby można było skorzystać z innych funkcji niż typowe w aplikacjach finansowych i operacyjnych, użytkownicy muszą być przypisani do ról zabezpieczeń. Można przypisywać użytkowników do ról automatycznie, na podstawie reguł i danych biznesowych, wykluczać użytkowników z automatycznego przypisania ról lub dodawać użytkowników do ról ręcznie.

## <a name="automatically-assign-users-to-roles"></a>Automatyczne przypisywanie użytkowników do ról
W tej procedurze pokazano, jak administratorzy systemu mogą automatycznie przypisywać użytkowników do ról, na podstawie danych biznesowych. 
1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
2. W drzewie zaznacz rolę „Kierownik ds. księgowania”. Zaznacz rolę, dla której chcesz skonfigurować regułę. W tym przykładzie wybierz rolę Kierownik ds. księgowania. 
3. Wybierz pozycję **Dodaj regułę**, aby otworzyć menu okna dialogowego.
4. Na liście **Wybierz zapytanie** znajdź i wybierz odpowiedni rekord. Zaznacz zapytanie, którego chcesz używać dla tej reguły.  
5. Na liście **Nazwa zasady członkowstwa** kliknij link w wybranym wierszu.
6. Wybierz **Edytuj zapytanie**. Edytuj kwerendę stosownie do potrzeb.  
7. Kliknij przycisk **OK**.
8. Wybierz pozycję **Uruchom automatyczne przypisanie roli**.
9. Przejdź do **Okienko nawigacji > Moduły > Administrowanie systemem > Użytkownicy > Użytkownicy** (najlepiej w osobnej karcie przeglądarki)
10. Przejrzyj role przypisane różnym użytkownikom, aby potwierdzić, że kwerenda przypisania roli była poprawna. W razie potrzeby skoryguj i uruchom ponownie.

## <a name="exclude-users-from-automatic-role-assignment"></a>Wykluczanie użytkowników z automatycznego przypisywania ról
W tej procedurze popisano sposób wykluczenia użytkowników z automatycznego przypisywania ról.

1. Zamknij stronę.
2. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
3. W drzewie zaznacz rolę „Kierownik ds. księgowania”. Służy do wybierania roli. W tym przykładzie wybierz rolę Kierownik ds. księgowania.  
4. W menu **Użytkownicy przypisani do roli** wybierz **Ręcznie przypisz / wyklucz użytkowników**.
5. Na liście **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** zaznacz wybrany wiersz. Wybierz użytkownika.  
6. W **Panelu akcji** wybierz **Wyklucz z roli**.
7. Wybierz pozycję **Wyklucz użytkowników z roli**, aby wykluczyć wybranych użytkowników z roli. Żeby usunąć wykluczenia, wybierz użytkowników, których wyluczenia chcesz usunąć i kliknij **Zresetuj status**. Po usunięciu wykluczenia przez zresetowanie stanu użytkownika zostanie mu automatycznie przypisana rola. Jednak po resecie stanu użytkownik nie jest natychmiast przypisywany do roli ani wykluczany z roli. Zamiast tego użytkownik jest przypisywany do roli albo usuwany z roli podczas następnej sesji automatycznego przypisywania ról.  

## <a name="manually-assign-users-to-roles"></a>Ręczne przypisywanie użytkowników do ról
Użytkownicy ręcznie przypisani do ról zabezpieczeń muszą również zostać usunięci ręcznie przez administratora. Użytkownicy ci nie są usuwani z ról za pomocą reguł automatycznego przypisania ról.

1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
2. W drzewie wybierz rolę, a następnie w menu **Użytkownicy przypisani do roli** wybierz pozycję **Ręcznie przypisz/wyklucz użytkowników**.
4. W obszarze **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** użytkownicy, do których nie przypisano roli, są wyświetlani z **trybem przypisania** ustawionym na **Brak**. Wybierz co najmniej jednego użytkownika, do którego ma zostać przypisana rola.
5. W **okienku akcji** wybierz pozycję **Przypisz do roli**. **Tryb przypisania** jest aktualizowany do opcji **Ręcznie**, a użytkownicy mają teraz przypisaną nową rolę.

## <a name="manually-remove-users-from-roles"></a>Ręczne usuwanie użytkowników z ról
Użytkownicy ręcznie przypisani do ról zabezpieczeń muszą również zostać usunięci ręcznie przez administratora. Użytkownicy ci nie są usuwani z ról za pomocą reguł automatycznego przypisania ról.

1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Ochrona > Przypisz użytkowników do ról**.
2. Aby usunąć jednego użytkownika, należy wykonać następujące czynności:
   1. W drzewie wybierz rolę. 
   2. W obszarze **Użytkownicy przypisani do roli** wybierz użytkownika, który ma zostać usunięty.
   3. Wybierz **pozycję** Usuń, a użytkownik zostanie usunięty z roli.
3. Aby usunąć wielu użytkowników, wykonaj następujące kroki:
   1. W drzewie wybierz rolę. 
   2. W obszarze **Użytkownicy przypisani do roli** wybierz **Ręcznie przypisz / wyklucz użytkowników**.
   3. Na stronie **Przypisz użytkowników do roli lub wyklucz użytkowników z roli** użytkownicy, do których nie przypisano roli, są wyświetlani z **trybem przypisania** ustawionym na **Brak**. Wybierz użytkowników, których należy wykluczyć z roli.
   4. W **Panelu akcji** wybierz **Wyklucz z roli**. **Tryb przypisania** jest aktualizowany do opcji **Ręcznie** i użytkownicy są teraz wykluczeni z roli.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

