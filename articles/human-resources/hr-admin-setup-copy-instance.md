---
title: Kopiowanie wystąpienia
description: Można skorzystać z usługi cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services (usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Human Resources do środowiska piaskownicy (sandbox).
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8385b7dfcd1d7294542c7f54f609b26b7988ac4
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431252"
---
# <a name="copy-an-instance"></a>Kopiowanie wystąpienia

Można skorzystać z usługi cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services (usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Human Resources do środowiska piaskownicy (sandbox). Jeśli masz inne środowisko piaskownicy, możesz również skopiować bazę danych z tego środowiska do docelowego środowiska piaskownicy.

Aby skopiować instancję, należy upewnić się, co następuje:

- Instancja Human Resources, którą chcesz zastąpić, musi być środowiskiem piaskownicy.

- Środowisko kopiowane z systemu i do systemu musi znajdować się w tym samym regionie. Nie można kopiować między regionami.

- Użytkownik musi być administratorem w środowisku docelowym, aby mógł się w nim zalogować po skopiowaniu instancji.

- Podczas kopiowania bazy danych Human Resources nie są kopiowane elementy (aplikacje lub dane) zawarte w środowisku Microsoft PowerApps. Aby uzyskać informacje o kopiowaniu elementów w środowisku PowerApps, zapoznaj się z tematem [Kopiuj środowisko](https://docs.microsoft.com/power-platform/admin/copy-environment). Środowisko PowerApps, które chcesz zastąpić, musi być środowiskiem piaskownicy. Musisz być globalnym administratorem dzierżawy, aby zmienić środowisko produkcyjne PowerApps w środowisko piaskownicy. Aby uzyskać więcej informacji o zmienianiu środowiska PowerApps, zapoznaj się z tematem [Przełącz wystąpienie](https://docs.microsoft.com/dynamics365/admin/switch-instance).

## <a name="effects-of-copying-a-human-resources-database"></a>Efekty kopiowania bazy danych Human Resources

Podczas kopiowania bazy danych Human Resources zachodzą następujące zdarzenia:

- Proces kopiowania kasuje istniejącą bazę danych w środowisku docelowym. Po zakończeniu procesu kopiowania nie można odzyskać istniejącej bazy danych.

- Środowisko docelowe nie będzie dostępne do czasu zakończenia procesu kopiowania.

- Dokumenty w magazynie obiektów BLOB Microsoft Azure nie są kopiowane z jednego środowiska do drugiego. Z tego powodu wszystkie dołączone dokumenty i szablony nie zostaną skopiowane i pozostaną w środowisku źródłowym.

- Wszyscy użytkownicy, z wyjątkiem użytkownika o statusie Administrator i innych wewnętrznych użytkowników usługi, będą niedostępni. W związku z tym Administrator może usunąć lub ukryć dane, zanim inni użytkownicy nie będą mogli z powrotem w systemie.

- Administrator musi wprowadzić wymagane zmiany konfiguracji, takie jak ponowne podłączenie punktów końcowych integracji do określonych usług lub adresów URL.

## <a name="copy-the-human-resources-database"></a>Kopiowanie bazy danych Human Resources

Aby wykonać to zadanie, najpierw należy skopiować instancję, a następnie zalogować się do centrum administracyjnego Microsoft Power Platform w celu skopiowania swojego środowiska PowerApps.

> [!WARNING]
> Po skopiowaniu isntancji baza danych jest usuwana w obiekcie docelowym. Instancja docelowa jest niedostępna w trakcie tego procesu.

1. Zaloguj się do usługi LCS i wybierz projekt usługi LCS zawierający instancję, którą chcesz skopiować.

2. W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.

3. Wybierz instancję do skopiowania, a następnie wybierz **Kopiuj**.

4. W okienku zadań **Kopiuj instancję** wybierz instancję, która ma zostać zastąpiona, a następnie wybierz **Kopiuj**. Poczekaj na zaktualizowanie wartości pola **Stan kopiowania** na **Zakończone**.

   ![[Wybierz wystąpienie do zastąpienia](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Wybierz **Power Platform**, zaloguj się do Centrum administracyjnego Microsoft Power Platform.

   ![[Wybierz Power Platform](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Wybierz środowisko PowerApps do skopiowania, a następnie wybierz **Kopiuj**.

7. Po zakończeniu procesu kopiowania zaloguj się do instancji docelowej i włącz integrację Common Data Service. Aby uzyskać więcej informacji i instrukcji, zobacz [Konfigurowanie integracji Common Data Service dla przestrzeni roboczych](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

## <a name="data-elements-and-statuses"></a>Elementy danych i stany

Następujące elementy danych nie są kopiowane podczas kopiowania instancji Human Resources:

- Adresy e-mail w tabeli **LogisticsElectronicAddress**

- Historia zadań wsadowych w tabelach **BatchJobHistory**, **BatchHistory**i **BatchConstraintHistory**

- Hasło protokołu SMTP (Simple Mail Transfer Protocol) w tabeli **SysEmailSMTPPassword**

- Serwer przekaźnika SMTP w tabeli **SysEmailParameters**

- Ustawienia zarządzania drukowaniem w tabelach **PrintMgmtSettings** oraz **PrintMgmtDocInstance**

- Rekordy właściwe dla środowiska w tabelach **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** i **BatchServerGroup**

- Załączniki dokumentów w tabeli DocuValue. Do tych załączników należą wszystkie szablony Microsoft Office, które zostały zastąpione w środowisku źródłowym

- Ciąg połączenia w tabeli **PersonnelIntegrationConfiguration**

Niektóre z tych elementów nie są kopiowane, ponieważ są specyficzne dla środowiska. Przykłady to m.in. rekordy **BatchServerConfig** czy **SysCorpNetPrinters**. Inne elementy nie są kopiowane z powodu wolumenu biletów pomocy technicznej. Na przykład mogą zostać wysłane zduplikowane wiadomości e-mail, ponieważ protokół SMTP jest nadal włączony w środowisku testowania akceptacji użytkownika (piaskownicy), mogą zostać wysłane nieprawidłowe komunikaty integracji, ponieważ zadania wsadowe są nadal włączone, a użytkownicy mogą być włączani przed wykonaniem przez administratora akcji oczyszczania po odświeżeniu.

Ponadto podczas kopiowania istnieją zmieniają się następujące stany:

- Wszyscy użytkownicy z wyjątkiem administratora są **Wyłączeni**.

- Wszystkie zadania wsadowe, z wyjątkiem niektórych zadań systemowych, są ustawione na **Wstrzymane**.

## <a name="environment-admin"></a>Administrator środowiska

Wszyscy użytkownicy w docelowym środowisku piaskownicy, w tym Administratorzy, są zastępowani przez użytkowników środowiska źródłowego. Przed skopiowaniem wystąpienia należy upewnić się, że jesteś Administratorem w środowisku docelowym. Jeśli nie, po zakończeniu kopiowania nie będzie można zalogować się do docelowego środowiska piaskownicy.

Wszyscy użytkownicy niebędący Administratorami w docelowym środowisku piaskownicy są wyłączeni w celu zapobiegania niepotrzebnego rejestrowania w środowisku piaskownicy. W razie potrzeby Administratorzy mogą ponownie włączyć użytkowników.
