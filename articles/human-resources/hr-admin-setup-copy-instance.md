---
title: Kopiowanie wystąpienia
description: Można skorzystać z usługi cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services (usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Human Resources do środowiska piaskownicy (sandbox).
author: twheeloc
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 935c2e6cb45df193e6cbf70634f3561154c6fe38
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178542"
---
# <a name="copy-an-instance"></a>Kopiowanie wystąpienia

_**Zastosowanie:** Ustanowienie rozwiązania Human Resources w samodzielnym wystąpieniu infrastruktury_ 

> [!NOTE]
> Od czerwca 2022 roku środowiska zasobów ludzkich mogą być wdrażane tylko na infrastrukturze aplikacji finansowych i operacyjnych. Więcej informacji: [Ustanowienie rozwiązania Human Resources w infrastrukturze związanej z finansami i operacjami](hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> Infrastruktura finansowa i operacyjna nie obsługuje funkcji instancji kopiowania. Możesz wdrażać nowe środowiska i używać ruchów bazy danych do tworzenia kopii. Aby uzyskać więcej informacji na temat samoobsługowych stanowisk, zobacz [Przegląd samoobsługowych stanowisk](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md). Więcej informacji na temat ruchów baz danych w infrastrukturze finansowej i operacyjnej można znaleźć na stronie głównej [Operacje ruchów baz danych](../fin-ops-core/dev-itpro/database/dbmovement-operations.md).

Można skorzystać z usługi cyklu pomocy technicznej Microsoft Dynamics Lifecycle Services (usługi LCS), aby skopiować bazę danych firmy Microsoft Dynamics 365 Human Resources do środowiska piaskownicy (sandbox). Jeśli masz inne środowisko piaskownicy, możesz również skopiować bazę danych z tego środowiska do docelowego środowiska piaskownicy.

Aby skopiować wystąpienie, należy pamiętać o następujących wskazówkach:

- Instancja Human Resources, którą chcesz zastąpić, musi być środowiskiem piaskownicy.

- Środowisko kopiowane z systemu i do systemu musi znajdować się w tym samym regionie. Nie można kopiować między regionami.

- Użytkownik musi być administratorem w środowisku docelowym, aby mógł się w nim zalogować po skopiowaniu instancji.

- Podczas kopiowania bazy danych Human Resources nie są kopiowane elementy (aplikacje lub dane) zawarte w środowisku Microsoft Power Apps. Aby uzyskać informacje o kopiowaniu elementów w środowisku Power Apps, zapoznaj się z tematem [Kopiuj środowisko](/power-platform/admin/copy-environment). Środowisko Power Apps, które chcesz zastąpić, musi być środowiskiem piaskownicy. Musisz być globalnym administratorem dzierżawy, aby zmienić środowisko produkcyjne Power Apps w środowisko piaskownicy. Aby uzyskać więcej informacji o zmienianiu środowiska Power Apps, zapoznaj się z tematem [Przełącz wystąpienie](/dynamics365/admin/switch-instance).

- Jeśli użytkownik skopiuje wystąpienie do środowiska piaskownicy i chce zintegrować środowisko piaskownicy z systemem Dataverse, należy ponownie zastosować pola niestandardowe do tabeli Dataverse. Zobacz [Zastosuj niestandardowe pola do Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).

## <a name="effects-of-copying-a-human-resources-database"></a>Efekty kopiowania bazy danych Human Resources

Podczas kopiowania bazy danych Human Resources zachodzą następujące zdarzenia:

- Proces kopiowania kasuje istniejącą bazę danych w środowisku docelowym. Po zakończeniu procesu kopiowania nie można odzyskać istniejącej bazy danych.

- Środowisko docelowe nie będzie dostępne do czasu zakończenia procesu kopiowania.

- Dokumenty w magazynie obiektów BLOB Microsoft Azure nie są kopiowane z jednego środowiska do drugiego. Z tego też powodu żadne dołączone dokumenty i szablony nie zostaną skopiowane i pozostaną w środowisku źródłowym.

- Wszyscy użytkownicy z wyjątkiem tych z rolą zabezpieczeń „Administrator systemu” i innymi wewnętrznymi kontami użytkowników usługi nie będą dostępne. Administrator może usunąć dane, zanim inni użytkownicy zostaną ponownie wpuszczeni do systemu.

- Użytkownik (rola zabezpieczeń Administrator systemu) musi wprowadzić wymagane zmiany konfiguracji, takie jak ponowne podłączenie punktów końcowych integracji do określonych usług lub adresów URL.

## <a name="copy-the-human-resources-database"></a>Kopiowanie bazy danych Human Resources

Aby wykonać to zadanie, najpierw należy skopiować instancję, a następnie zalogować się do centrum administracyjnego Microsoft Power Platform w celu skopiowania swojego środowiska Power Apps.

> [!WARNING]
> Po skopiowaniu isntancji baza danych jest usuwana w obiekcie docelowym. Instancja docelowa jest niedostępna w trakcie tego procesu.

1. Zaloguj się do usługi LCS i wybierz projekt usługi LCS zawierający instancję, którą chcesz skopiować.

2. W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.

3. Wybierz instancję do skopiowania, a następnie wybierz **Kopiuj**.

4. W okienku zadań **Kopiuj instancję** wybierz instancję, która ma zostać zastąpiona, a następnie wybierz **Kopiuj**. Poczekaj na zaktualizowanie pola **Stan kopiowania** na **Zakończone**.

   ![[Wybierz instancję do zastąpienia.](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Wybierz **Power Platform**, zaloguj się do Centrum administracyjnego Microsoft Power Platform.

   ![[Wybierz Power Platform.](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Wybierz środowisko Power Apps do skopiowania, a następnie wybierz **Kopiuj**.

Więcej informacji o kopiowaniu środowisk Power Apps znajdziesz w rozdziale [Kopiowanie środowiska](/power-platform/admin/copy-environment#copy-an-environment-1).

7. Po zakończeniu procesu kopiowania zaloguj się do instancji docelowej i włącz integrację Dataverse. Aby uzyskać więcej informacji i instrukcji, zobacz [Konfigurowanie integracji Dataverse dla przestrzeni roboczych](./hr-admin-integration-common-data-service.md).

## <a name="data-elements-and-statuses"></a>Elementy danych i stany

Następujące elementy danych nie są kopiowane podczas kopiowania instancji Human Resources:

- Adresy e-mail w tabeli **LogisticsElectronicAddress**

- Historia zadań wsadowych w tabelach **BatchJobHistory**, **BatchHistory** i **BatchConstraintHistory**

- Hasło protokołu SMTP (Simple Mail Transfer Protocol) w tabeli **SysEmailSMTPPassword**

- Serwer przekaźnika SMTP w tabeli **SysEmailParameters**

- Ustawienia zarządzania drukowaniem w tabelach **PrintMgmtSettings** oraz **PrintMgmtDocInstance**

- Rekordy właściwe dla środowiska w tabelach **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** i **BatchServerGroup**

- Załączniki dokumentów w tabeli DocuValue. Do tych załączników należą wszystkie szablony Microsoft Office, które zostały zastąpione w środowisku źródłowym

- Ciąg połączenia w tabeli **PersonnelIntegrationConfiguration**

Niektóre z tych elementów nie są kopiowane, ponieważ są specyficzne dla środowiska. Przykłady to m.in. rekordy **BatchServerConfig** czy **SysCorpNetPrinters**. Inne elementy nie są kopiowane z powodu wolumenu biletów pomocy technicznej. Na przykład:

- Mogą zostać wysłane zduplikowane wiadomości e-mail, ponieważ protokół SMTP jest nadal włączony w środowisku testowania akceptacji użytkowników (piaskownicy).

- Mogą zostać wysłane nieprawidłowe komunikaty integracji, ponieważ zadania wsadowe są nadal włączone.

- Dostęp użytkowników może być włączony zanim administratorzy będą mogli wykonywać akcje oczyszczania po odświeżeniu.

Ponadto podczas kopiowania istnieją zmieniają się następujące stany:

- Wszyscy użytkownicy z wyjątkiem tych z rolą zabezpieczeń „Administrator systemu” są ustawieni na **Wyłączone**.

- Wszystkie zadania wsadowe, z wyjątkiem niektórych zadań systemowych, są ustawione na **Wstrzymane**.

## <a name="environment-admin"></a>Administrator środowiska

Wszyscy użytkownicy w docelowym środowisku piaskownicy, w tym Administratorzy, są zastępowani przez użytkowników środowiska źródłowego. Przed skopiowaniem wystąpienia należy upewnić się, że jesteś Administratorem w środowisku źródłowym. Jeśli nie, po zakończeniu kopiowania nie będzie można zalogować się do docelowego środowiska piaskownicy.

Wszyscy użytkownicy niebędący Administratorami w docelowym środowisku piaskownicy są wyłączeni w celu zapobiegania niepotrzebnego rejestrowania w środowisku piaskownicy. W razie potrzeby Administratorzy mogą ponownie włączyć użytkowników.

## <a name="apply-custom-fields-to-dataverse"></a>Zastosuj niestandardowe pola do Dataverse

Jeśli użytkownik skopiuje wystąpienie do środowiska piaskownicy i chce zintegrować środowisko piaskownicy z systemem Dataverse, należy ponownie zastosować pola niestandardowe do tabeli Dataverse.

Dla każdego pola niestandardowego, które jest uwidocznione na tabelach Dataverse należy wykonać następujące kroki:

1. Przejdź do pola niestandardowego i wybierz opcję **Edytuj**.

2. Usuń zaznaczenie pola **Włączone** dla każdej jednostki cdm_*, dla której włączono pole niestandardowe.

3. Wybierz opcję **Zastosuj zmiany**.

4. Wybierz ponownie przycisk **Edytuj**.

5. Wybierz pole **Włączone** dla każdej jednostki cdm_*, dla której włączono pole niestandardowe.

6. Ponownie wybierz opcję **Zastosuj zmiany**.

Proces cofania wyboru, stosowania zmian, ponownego wybierania i ponownego stosowania zmian powoduje wyświetlenie w schemacie, w którym w Dataverse będą uwzględniane pola niestandardowe.

Aby uzyskać więcej informacji na temat tworzenia pól niestandardowych, zobacz [Tworzenie pól niestandardowych i praca z nimi](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).

## <a name="see-also"></a>Informacje dodatkowe

[Aprowizowanie rozwiązania Human Resources](hr-admin-setup-provision.md)</br>
[Usuwanie wystąpienie](hr-admin-setup-remove-instance.md)</br>
[Aktualizowanie procesu](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
