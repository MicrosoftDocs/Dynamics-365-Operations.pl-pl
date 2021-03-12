---
title: Tworzenie nowych użytkowników
description: Użytkownikami są wewnętrzni pracownicy organizacji lub zewnętrznych odbiorcy i dostawcy, którzy potrzebują dostępu do systemu w celu wykonywania swoich zadań.
author: peakerbl
manager: AnnBe
ms.date: 01/12/2021
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
ms.openlocfilehash: ca062ddd49f1c206c503fb6160ed436fe2d6f7e9
ms.sourcegitcommit: 9e27a097b7eb3c8f2df66011ccc597ad18bc5445
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/13/2021
ms.locfileid: "4878664"
---
# <a name="create-new-users"></a>Tworzenie nowych użytkowników

[!include [banner](../../includes/banner.md)]

Aby można było uzyskać dostęp do aplikacji Finance and Operations, należy najpierw dodać siebie do strony **Użytkownicy** (**Administrowanie systemem \> Użytkownicy \> Użytkownicy**). Do użytkowników należą wewnętrzni pracownicy organizacji oraz zewnętrzni odbiorcy i dostawcy. Użytkownicy mogą być importowani lub dodawani ręcznie. Wszyscy użytkownicy muszą mieć poprawne licencje zgodnie ze zgodnym standardem.

Aby uzyskać informacje dotyczące sposobu kupowania i licencji na aplikacje Finance and Operations, zobacz [Podręcznik licencjonowania Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).

## <a name="assign-a-license-to-a-user"></a>Przypisywanie licencji do użytkownika
Administratorzy systemów mogą [przypisywać licencje do użytkowników](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) w [centrum administracyjnym Microsoft 365](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Dodaj użytkownika zewnętrznego w usłudze Azure AD i przypisz licencję 
Użytkownicy zewnętrzni muszą być reprezentowani w katalogu dzierżawcy (Azure Active Directory (Azure AD)), aby można było im przypisać licencje. Użytkownicy zewnętrzni powinni zostać dodani do dzierżawy Azure AD jako użytkownik gość, a następnie przypisani do odpowiednich licencji. Wymaganie dotyczące aplikacji Finance and Operations jest takie, aby użytkownik-gość korzystał z usługi Azure AD. Aby uzyskać więcej informacji, odwiedź sekcję [Dodawanie użytkowników współpracy w module B2B Azure Active Directory w portalu Azure Portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="import-new-users-from-azure-ad"></a>Importowanie nowych użytkowników z usługi Azure AD 
1. Wybierz kolejno opcje **Administrowanie systemem** \> **Użytkownicy** \> **Użytkownicy**.
2. W okienku akcji wybierz pozycję **Importuj użytkowników**.
3. Wybierz użytkowników do zaimportowania. Lista zawiera użytkowników usługi Azure AD, którzy obecnie nie są użytkownikami w tym środowisku.
4. Wybierz **Importuj użytkowników**.
5. Kliknij przycisk **Zamknij**.

> [!NOTE]
> Wartość w polu **Firma** będzie ustawiana na podstawie bieżącej firmy dla sesji administratora. Po zaimportowaniu musisz przypisać role i odpowiednie organizacje. Więcej informacji można znaleźć w [Przypisywanie użytkowników do ról zabezpieczeń](assign-users-security-roles.md). Warunkowo może być również wymagane skojarzenie użytkownika z **osobą** i zaktualizowanie opcji użytkownika, takich jak język.

## <a name="manually-add-a-new-user"></a>Ręczne dodawanie nowego użytkownika
1. Wybierz kolejno opcje **Administrowanie systemem** \> **Użytkownicy** \> **Użytkownicy**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Identyfikator użytkownika** wprowadź unikatowy identyfikator dla użytkownika.   
4. W polu **Nazwa użytkownika** wprowadź nazwę użytkownika.  
5. W polu **Dostawca**:
 - Dla użytkowników wewnętrznych użyj wartości domyślnej. Na przykład dzierżawca usługi Azure AD z prefiksem https://sts.windows.net/.  
 - W przypadku użytkowników usługi Azure AD innych niż konta „usługa do usługi” wprowadź podstawową wartość tekstową. Na przykład Nie dotyczy. Ta wartość pomaga uniknąć niepoprawnych wywołań uwierzytelniania, które mogą spowodować błędy, jeśli zostanie użyta prawidłowa wartość dostawcy tożsamości.  
 - Dla użytkowników zewnętrznych lub gości dodaj nazwę dzierżawcy usługi Azure AD po ciągu https://sts.windows.net/.
6. W polu **Adres e-mail** wprowadź pełen adres e-mail/nazwę główną użytkownika.  
7. W polu **Firma** wybierz domyślną firmę startową dla użytkownika. 
8. Wybierz opcję **Zapisz**.

Wartości dla dostawcy tożsamości i identyfikatora telemetrii zostaną zaktualizowane na podstawie wywołania programu [Microsoft Graph](https://docs.microsoft.com/graph/overview) po zapisaniu rekordu użytkownika. Identyfikator telemetrii jest oparty na identyfikatorze obiektu/identyfikatorze zabezpieczeń (SID) w usłudze Azure AD.

> [!NOTE]
> Po dodaniu użytkownika musisz przypisać role i odpowiednie organizacje. Więcej informacji można znaleźć w [Przypisywanie użytkowników do ról zabezpieczeń](assign-users-security-roles.md). Warunkowo może być również wymagane skojarzenie użytkownika z **osobą** i zaktualizowanie **opcji użytkownika**, takich jak język.

## <a name="change-a-user-id"></a>Zmienianie identyfikatora użytkownika
Aby zmienić identyfikator użytkownika, należy zmienić nazwę klucza w bazie danych. Jeśli identyfikator użytkownika zostanie zmieniony za pomocą tej procedury, wszystkie powiązane ustawienia użytkownika zostaną zmodyfikowane tak, aby używać nowego identyfikatora użytkownika. Na przykład informacje o użyciu w tabeli **SysLastValue** są aktualizowane w celu odwołania do nowego identyfikatora użytkownika.

> [!NOTE]
> Identyfikator użytkownika jest kluczem podstawowym tabeli informacji o użytkowniku. Zmiana nazwy klucza podstawowego może zająć trochę czasu dla istniejących użytkowników, ponieważ wszystkie odwołania do tego klucza są także aktualizowane w bazie danych. 

1. Wybierz kolejno opcje **Administrowanie systemem \> Użytkownicy \> Użytkownicy**.
2. Wybierz użytkownika z listy i wybierz pozycję **Opcje \> Informacje o rekordzie**.
3. Wybierz polecenie **Zmień nazwę**.
4. Wprowadź nową i unikatową wartość identyfikatora użytkownika, a następnie wybierz przycisk **OK**. 
5. Wybierz przycisk **Tak**, aby potwierdzić.

## <a name="additional-resources"></a>Dodatkowe zasoby

Aby uzyskać więcej opcji implementacji użytkowników B2B, zobacz temat [Eksportowanie użytkowników B2B do usługi Azure AD](../implement-b2b.md).

Aby uzyskać informacje o wstępnie skonfigurowanych kontach systemowych, zobacz temat [Wstępnie skonfigurowane konta systemowe](../pre-configured-system-accounts.md)
