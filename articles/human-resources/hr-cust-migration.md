---
title: Migracja klienta rozwiązania Dynamics 365 Human Resources do infrastruktury finansowej i operacyjnej
description: W tym artykule opisano migrację klienta między z rozwiązania Microsoft Dynamics 365 Human Resources do infrastruktury finansowej i operacyjnej.
author: twheeloc
ms.date: 10/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4df9a68ea0128378224bf77bd66423fd2e13fa55
ms.sourcegitcommit: e5b290bac7e8f468167caa1a5607aac6eac9aaea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760370"
---
# <a name="dynamics-365-human-resources-customer-migration"></a>Migracja klienta rozwiązania Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

Migracja klientów jest migracją metodą „lift-and-shift” (przeniesienie) bazy danych klientów do infrastruktury finansowej i operacyjnej. Jest do tego używane automatyczne narzędzie migracji. W wyniku tego jest nowe środowisko finansowe i operacyjne, w którym jest używana baza danych Human Resources odbiorcy.

## <a name="prerequisites"></a>Wymagania wstępne

### <a name="user-access-and-permissions"></a>Dostęp i uprawnienia użytkownika

- Użytkownik Microsoft Dynamics Lifecycle Services powinien mieć rolę **Administrator organizacji**.
- Użytkownik powinien mieć możliwość [tworzenia projektów Azure DevOps](/azure/devops/organizations/projects/create-project) lub korzystania z istniejącego projektu Azure DevOps.
- Użytkownik powinien mieć dostęp do [tworzenia osobistego tokenu zabezpieczeń dostępu Azure DevOps](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate) lub powinien mieć token, który będzie dostępny do użycia.

### <a name="dataverse-environment-backup-sandbox"></a>Środowisko zapasowe usługi Dataverse (piaskownica)

 - Opcjonalne, ale zalecane: odśwież istniejące środowisko piaskownicy Human Resources, używając kopii środowiska produkcyjnego Human Resources.
 - Utwórz nowe środowisko Dataverse, używając centrum administracyjnego platformy Power Platform.
 - Skopiuj istniejące środowisko Dataverse, które jest połączone ze autonomiczną aplikacją Human Resources, do środowiska utworzonego w poprzednim kroku.

> [!NOTE]
> Podczas dodawania bazy danych upewnij się, że opcja **Włącz aplikacje Dynamics 365** ma wartość **Tak**. Aby uzyskać szczegółowe informacje, zobacz temat [Przygotowywanie środowiska Power Platform](hr-cust-migration.md#prepare-a-power-platform-environment)

### <a name="dataverse-capacity"></a>Pojemność Dataverse

1. Na stronie **Podsumowanie** w centrum administratora Power Platform sprawdź, czy [magazyn Dataverse](/power-platform/admin/finance-operations-storage-capacity) ma wystarczające dostępne zdolności produkcyjne dla kopii środowiska.
2. Jeśli brakuje dostępnej pojemności, skorzystaj z [wytycznych w celu zwolnienia przestrzeni dyskowej](/power-platform/admin/free-storage-space), by zmniejszyć ogólne zużycie. Odbiorcy mogą również [dodawać dodatkową pojemność dyskową](/power-platform/admin/add-storage).

## <a name="customer-migration-process"></a>Proces migracji odbiorcy

### <a name="create-a-lifecycle-services-project-for-human-resources-migration"></a>Utwórz projekt usługi Lifecycle Services dla migracji Human Resources

Pierwszym krokiem jest utworzenie nowego projektu implementacji finansów i operacji w u usługach Lifecycle Services. Odbiorca będzie mieć istniejący projekt usługi Lifecycle Services dla Human Resources. Istniejące środowiska Human Resources zostaną zmigrowane do nowego projektu implementacji finansów i operacji.

Aby utworzyć nowy projekt, należy wykonać następujące kroki.

1. Zaloguj się do usługi Lifecycle Services jako administrator globalny lub wyznaczony użytkownik konta usługi.
2. Na stronie głównej usługi Lifecycle Services wybierz **Utwórz/nowe (+)**.
3. Wybierz aplikacje finansowe i operacyjne jako produkt.
4. W polu **Cel projektu** zaznacz opcję **Implementacja**.
5. Wprowadź nazwę i opis projektu.
6. W polu **Typ niestandardowego projektu** wybierz **Migracja Microsoft Dynamics 365 Human Resources**.
7. Zaznacz pole wyboru, aby wyrazić zgodę na warunki i postanowienia.
8. Wybierz opcję **Utwórz**.

Po utworzeniu nowego projektu Lifecycle Services, wykonaj poniższe kroki, aby go skonfigurować.

1. Wybierz opcję **Dołączanie projektu**, aby zakończyć dołączanie projektu. Aby uzyskać więcej informacji, zobacz [Wprowadzanie do projektu](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md).

    - Wybierz ten sam region co bieżące środowiska. Ten wybór nie wpłynie na migrację.
    - W przypadku starszych systemów wybierz opcję **Inne**.

2. Dokończ konfigurowanie projektu. W ramach tego kroku należy skonfigurować bibliotekę SharePoint Online, Azure DevOps oraz połączenia systemu Azure, jeśli są one wymagane. Aby uzyskać więcej informacji, zobacz [Przewodnik użytkownika usługi Lifecycle Services (LCS)](../dev-itpro/lifecycle-services/lcs-user-guide.md).

> [!NOTE]
> Odbiorcy mogą używać istniejącego projektu Azure DevOps i skojarzonego z nim osobistego tokenu zabezpieczeń dostępu. Jeśli jest używany istniejący projekt, konfiguracje powiązane z projektem są automatycznie dostępne i można je przejrzeć kontem dokładności.

### <a name="migrate-a-human-resources-sandbox-environment"></a>Migrowanie środowiska piaskownicy Human Resources

#### <a name="prepare-to-migrate-the-sandbox-environment"></a>Przygotuj środowisko piaskownicy do migracji

Po utworzeniu nowego projektu usługi Lifecycle Services i zakończeniu procesu dołączania projektu można rozpocząć migrację pierwszego środowiska. Przed rozpoczęciem tego procesu zaleca się odświeżenie środowiska piaskownicy, które będzie umożliwiało migrowanie ze środowiska produkcyjnego w autonomicznej infrastrukturze.

#### <a name="prepare-a-power-platform-environment"></a>Przygotowanie środowiska Power Platform

> [!NOTE]
> Ten krok jest stosowany tylko do migracji środowiska piaskownicy. Podczas migrowania środowiska produkcyjnego istniejące środowisko centrum administracyjnego Power Platform dołączone do środowiska produkcyjnego zostanie przeniesione naprzód. Podczas dodawania bazy danych upewnij się, że przycisk **Włącz aplikacje Dynamics 365** ma wartość **Tak**. 

- W centrum administratora platformy Power Platform [utwórz środowisko z bazą danych](/power-platform/admin/create-environment#create-an-environment-with-a-database), które będzie umożliwiało migrację piaskownicy, lub wybierz istniejące środowisko.
- [Skopiuj środowisko](/power-platform/admin/copy-environment), aby odświeżyć środowisko Power Platform używane do mapowania.

#### <a name="migrate-the-sandbox-environment"></a>Migracja środowiska piaskownicy

1. Zaloguj się do usługi Lifecycle Services jako administrator globalny lub wyznaczony użytkownik konta usługi.

    > [!NOTE]
    > Zaleca się używanie nazwanego konta użytkownika. Zalogowany użytkownik powinien mieć rolę zabezpieczeń **Właściciel projektu** lub **Menedżer środowiska** w samodzielnym projekcie Lifecycle Services dla Human Resources.

2. Otwórz nowo utworzony projekt migracji Human Resources.
3. Przejrzyj i wykonaj odpowiednie fazy metodologii migracji i dołączania projektu.
4. Na pulpicie nawigacyjnym projektu w okienku **Domyślnie: test standardowej akceptacji** wybierz pozycję **Migracja HR**.
5. W okienku **Wybierz środowisko do migrowania** wybierz odpowiedni projekt usługi Lifecycle Services i źródłowe środowisko Human Resources (ze swojej autonomicznej aplikacji Human Resources).
6. Włącz **Mapowanie do nowego środowiska Power Platform** i wybierz odpowiednie środowisko Power Platform. Następnie kliknij przycisk **Dalej**.
7. Wykonaj zadania kreatora **Ustawienia wdrożenia (finanse i operacje — piaskownica)**, aby potwierdzić szczegóły i podpis odbiorcy, a następnie wybierz pozycję **Wdróż**.

Stan środowiska będzie pokazywał postęp. Stan zostanie zmieniony z **Ładowanie** na **Wdrażanie** na **Wdrożone**.

> [!NOTE]
> Okienko produkcji będzie niedostępne, dopóki nie zostanie zakończona lista kontrolna gotowości do pracy w projekcie. Aby uzyskać więcej informacji, zobacz [Przygotuj się do startu](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

#### <a name="considerations-and-assumptions"></a>Uwagi i założenia

Środowisko piaskownicy Human Resources istnieje w projekcie usługi Lifecycle Services w dzierżawie o następujących cechach:

- Środowisko piaskownicy Human Resources nie jest połączone z istniejącym scalony środowiskiem. W danym środowisku Human Resources może być tylko jedna migracja w danej chwili.
- Liczba środowisk piaskownicy dozwolonych w tym czasie jest oparta na licencji Human Resources. Jeśli dla dzierżawcy została zakupiona wystarczająca ilość licencji, dodatkowe środowiska piaskownicy zostaną wyświetlone w okienku **Środowiska** tego projektu.
- Migracje muszą zostać wykonane do środowisk tego samego typu. Innymi słowy, można wykonać tylko migracje piaskownicy do piaskownicy lub produkcyjnego do produkcyjnego.

    > [!NOTE]
    > Gdy jest określony stan produkcji lub piaskownicy, są traktowane tylko typy środowiska Human Resources. Jeśli środowiska są niepoprawnie sklasyfikowane (to jest środowisko produkcyjne jest oznaczone jako środowisko piaskownicy lub środowisko piaskownicy jest oznaczone jako środowisko produkcyjne), skontaktuj się z pomocą techniczną.

- Jeśli migracja nie powiodła się, wyświetlany jest komunikat o błędzie po awarii i dostępny jest przycisk **Usuń**. Ten przycisk umożliwia usunięcie nieudanej migracji. Następnie można ponownie zmigrować środowisko.

#### <a name="validate-the-sandbox-migration"></a>Sprawdź poprawność migracji piaskownicy

Po pomyślnym zakończeniu procesu migracji piaskownicy utwórz szczegółowy plan testowania w celu weryfikacji i podpisania wszystkich procesów biznesowych.

Przed rozpoczęciem testowania należy sprawdzić poprawność następujących szczegółów:

- Potwierdź, że zmigrowane środowisko jest dostępne pod adresem URL, który jest generowany.
- Potwierdź, że użytkownicy mają dostęp do migrowanej piaskownicy.
- Potwierdź , że środowisko Dataverse skojarzone ze zmigrowanym środowiskiem piaskownicy jest dostępne.
- Sprawdź losowo różne dane, aby potwierdzić, że są najbardziej aktualne.
- Zakończ procesy biznesowe o znaczeniu krytycznym na potrzeby weryfikacji.
- Potwierdź zastosowanie zasad zabezpieczeń.
- Potwierdź, że zadania wsadowe zostały wyzwolone zgodnie z oczekiwaniami.

Nie będziesz mieć dostępu z Pulpitu zdalnego do migrowana piaskownicy. Można używać samoobsługowych możliwości i narzędzi do wykonywania następujących akcji w środowiskach piaskownicy warstwy 2+:

- Dostęp do [bazy danych Azure SQL](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-the-azure-sql-database).
- Dostęp do [plików dziennika](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-log-files).
- Użyj [narzędzi perfmon](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#use-perfmon-tools).
- [Wyłącz/wyłącz tryb konserwacji](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-self-service-logs).
- Uruchom ponownie [usługi](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#restart-services).
- Skonfiguruj narzędzie [Regression Suite Automation Tool](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#configure-the-regression-suite-automation-tool).

Aby uzyskać więcej informacji, należy zapoznać się z tematem [Często zadawane pytania dotyczące samoobsługowego wdrożenia](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md).

### <a name="migrate-a-human-resources-production-environment"></a>Migrowanie środowiska produkcyjnego Human Resources

Po zakończeniu migracji i sprawdzania poprawności środowiska piaskownicy wykonaj następujące kroki, aby migrować środowisko produkcyjne.

#### <a name="prerequisites"></a>Wymagania wstępne

- Narzędzie do szacowania subskrypcji powinno być zakończone.
- [Ocena gotowości do pracy](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md) powinna być zakończona.

#### <a name="migrate-the-production-environment"></a>Migracja środowiska produkcyjnego

1. Zaloguj się do usługi Lifecycle Services jako administrator globalny lub wyznaczony użytkownik konta usługi.

    > [!NOTE]
    > Zaleca się używanie nazwanego konta użytkownika. Zalogowany użytkownik powinien mieć rolę zabezpieczeń **Właściciel projektu** lub **Menedżer środowiska** w samodzielnym projekcie Lifecycle Services.

2. Otwórz nowy projekt migracji Human Resources.
3. Przejrzyj i wykonaj odpowiednie fazy metodologii migracji i dołączania projektu.
4. Na pulpicie nawigacyjnym projektu w okienku **Produkcja** wybierz pozycję **Migracja HR**.
5. W okienku **Wybierz środowisko do migrowania** wybierz odpowiedni projekt usługi Lifecycle Services i źródłowe środowisko Human Resources (ze swojej autonomicznej aplikacji Human Resources). Następnie kliknij przycisk **Dalej**.
6. Wykonaj zadania kreatora **Ustawienia wdrożenia (finanse i operacje — piaskownica)**, aby potwierdzić szczegóły i podpis odbiorcy, a następnie wybierz pozycję **Wdróż**.

Stan środowiska będzie pokazywał postęp wdrożenia. Stan zostanie zmieniony z **Ładowanie** na **Wdrażanie** na **Wdrożone**.

#### <a name="post-migration-considerations"></a>Uwagi dotyczące działań po migracji

- Stosowanie [najnowszych aktualizacji](/fin-ops-core/fin-ops/get-started/quality-updates) do środowisk.
- Jeśli używasz [tabel wirtualnych](hr-admin-integration-common-data-service-virtual-entities.md), ponownie skonfiguruj punkty końcowe.
- Ponowne konfigurowanie integracji podwójnego zapisu. Oceń, które jednostki muszą być włączone.
- Rozważ użycie tabel wirtualnych w celu zastąpienia podwójnego zapisu w celu integracji.

#### <a name="dual-write-integration"></a>Integracja o podwójnym zapisie

##### <a name="set-up-microsoft-power-platform-dual-write-integration"></a>Konfigurowanie integracji podwójnego zapisu Microsoft Power Platform

1. Przejdź do centrum administracyjnego Power Platform i wybierz nazwę **Środowiska** w lewej stronie.
2. Wybierz środowisko poprzednio skopiowane/odświeżone i potwierdź, że stan jest **Gotowy**.
3. Przejdź do usługi Lifecycle Services i potwierdź, że stan projektu migracji jest **Wdrożony**.
4. W zmigrowanym środowisku wybierz opcję **Pełne szczegóły**, aby przejrzeć dodatkowe szczegóły i [skonfigurować aplikację podwójnego zapisu](../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#set-up-dual-write-for-new-or-existing-dataverse-environments).
5. W okienku **Konfiguracji aplikacji podwójnego zapisu** zaznacz to pole wyboru, aby zgodzić się na mapowanie i synchronizację danych między bazami danych, a następnie wybierz pozycję **Konfiguruj**.
6. Gdy okno komunikatu powiadamia o pomyślnej konfiguracji podwójnego zapisu, wybierz przycisk **OK**.
7. W szczegółach można monitorować postęp konfiguracji.
8. Po zakończeniu konfigurowania wybierz opcję **Łącze do środowiska Power Platform**, aby zsynchronizować dostępne jednostki danych.
9. Gdy stan wskazuje, że środowiska zostały pomyślnie połączone, przejdź do centrum administracyjnego Power Platform, aby przejrzeć i wybrać odpowiednie jednostki danych.
10. W lewym okienku wybierz pozycję **Aplikacje Dynamics 365 \> Zasoby**.
11. Potwierdź, że stan aplikacji Human Resources podwójnego zapisu jest **Włączone**.
12. Wybierz aplikację Human Resources podwójnego zapisu, a następnie wybierz pozycję **Zainstaluj**.
13. W okienku **Instalowanie aplikacji Dynamics 365 Human Resources podwójnego zapisu** wybierz odpowiednie środowisko, w którym ma być zainstalowany pakiet.
14. Zaznacz pole wyboru, aby zaakceptować warunki użytkowania usługi, a następnie wybierz pozycję **Zainstaluj**.
15. W środowisku aplikacji systemu Dynamics 365 w trakcie instalacji będzie miał stan **Instalowanie**. Po zakończeniu instalacji zostanie ona zaktualizowana na **Zainstalowano**.

##### <a name="review-and-apply-a-dual-write-solution"></a>Przejrzyj i zastosuj rozwiązanie podwójnego zapisu

1. W nowym środowisku finansów i operacji przejdź do tematu **Zarządzanie danymi \> Podwójny zapis**.
2. Wybierz opcję **Zastosuj rozwiązanie**.
3. W okienku wybierz **Zainstalowane rozwiązania systemu Dynamics**, **Mapy jednostek podstawowych aplikacji podwójnego zapisu** i **Mapy Dynamics 365 Human Resources**. Następnie wybierz opcję **Zastosuj**. Komunikat potwierdza, że rozwiązanie zostało zastosowane. Po pomyślnym zastosowaniu rozwiązania zostaną wyświetlone wszystkie dostępne mapy tabel.
4. Przejrzyj dostępne mapy tabel, aby wybrać i uruchomić integrację przy użyciu funkcji podwójnego zapisu.
5. Przy pierwszym uruchomieniu integracji podwójnego zapisu dla map tabel zaznacz pole wyboru **Wstępna synchronizacja**. Jeśli istnieje integracja ze źródłowego środowiska Human Resources, nie trzeba zaznaczać pola wyboru **Synchronizacja początkowa** po uruchomieniu integracji dla map tabel.

#### <a name="recommended-practices"></a>Zalecane wskazówki

W tej sekcji przedstawiono zalecenia dotyczące migrowania z autonomicznej infrastruktury do infrastruktury finansów i operacji.

- Zdecydowanie zaleca się, aby współpracować ze swoim partnerem Microsoft Dynamics, aby uzyskać pomoc na temat migracji środowiska Human Resources.
- Zaplanuj odpowiedni czas, aby wykonać pełne testowanie akceptacji użytkownika (UAT) w środowisku zmigrowanej piaskownicy.
- Zaplanuj i udokumentuj szczegółowe kroki w celu zmigrowania integracji do migrowanych środowisk.
- Utwórz szczegółową listę kontrolną, aby zarysować proces migracji.
- Zaplanuj odpowiednią ilość przestoju dla swojej firmy podczas migracji.
- Zdecydowanie zaleca się, aby odbiorcy o kwalifikacjach do pracy z architektem rozwiązań FastTrack współpracowali, aby pomóc w nadzorowaniu procesu migracji.
- Zdecydowanie zaleca się odświeżenie środowiska piaskownicy w autonomicznej infrastrukturze przed pierwszą migracją. To odświeżanie powinno zawierać środowisko Dataverse połączone ze środowiskiem piaskownicy, do którego będzie przeprowadzana migracja.
- Zdecydowanie zaleca się, aby podczas wdrażania, migrowania i tworzenia projektu usługi Lifecycle Services używać konta usługi.
- Zaplanuj uaktualnienie środowiska piaskownicy na celu weryfikacji UAT w najnowszej wersji dostępności ogólnej (GA). Więcej informacji zawiera temat [Zagadnienia](hr-infrastructure-merge.md#considerations).
