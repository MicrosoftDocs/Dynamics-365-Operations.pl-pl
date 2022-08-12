---
title: Ustanowienie rozwiązania Human Resources w infrastrukturze związanej z finansami i operacjami
description: Ten artykuł wyjaśnia proces tworzenia nowego środowiska produkcyjnego dla Microsoft Dynamics 365 Human Resources w infrastrukturze finansowej i operacyjnej.
author: twheeloc
ms.date: 01/07/2022
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
ms.openlocfilehash: 15060d8bdd598476081c22d7280319da3db0cb31
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178421"
---
# <a name="provision-human-resources-in-the-finance-and-operations-infrastructure"></a>Ustanowienie rozwiązania Human Resources w infrastrukturze związanej z finansami i operacjami

_**Dotyczy:** Zasobów ludzkich w infrastrukturze aplikacji finansowych i operacyjnych_ 

> [!NOTE]
> Od lipca 2022 roku nie można tworzyć nowych środowisk Human Resources na samodzielnej infrastrukturze Human Resources, ani nowych projektów Lifecycle Services (LCS) Microsoft Dynamics. Klienci mogą wdrażać środowiska zasobów ludzkich na infrastrukturze finansowej i operacyjnej.

Ten artykuł wyjaśnia proces tworzenia nowego środowiska produkcyjnego dla Microsoft Dynamics 365 Human Resources w infrastrukturze finansowej i operacyjnej.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem tworzenia nowego środowiska należy spełnić następujące warunki wstępne:

- Użytkownik dokonał zakupu aplikacji Human Resources u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). Jeśli masz już licencję na oprogramowanie Dynamics 365 uwzględniającą plan rozwiązania Human Resources, a nie jesteś w stanie wykonać kroków opisanych w tym artykule, skontaktuj się z pomocą techniczną.
- Administrator globalny musi się zarejestrować w usłudze [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com) i stworzył nowy projekt dotyczący finansów i operacji.

## <a name="provision-a-human-resources-trial-environment"></a>Inicjowanie obsługi środowiska próbnego Human Resources

> [!NOTE]
> Począwszy od kwietnia 2022 roku środowiska próbne zasobów ludzkich nie będą dostępne w samodzielnym aplikacji. Potencjalni klienci, którzy są zainteresowani oceną możliwości zasobów ludzkich w aplikacjach finansowych i operacyjnych, mogą skorzystać z bezpłatnego 30-dniowego okresu próbnego wraz z danymi demonstracyjnymi. Dynamics 365 Finance będzie obejmował funkcje kadrowe wprowadzone do infrastruktury finansowej poprzez połączenie samodzielnej aplikacji. Aby uzyskać więcej informacji, zobacz [Połączenie ofert HR daje klientom wspólne możliwości](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). Więcej informacji na temat prób Dynamics 365 Finance można znaleźć w [przewodniku](../fin-ops-core/fin-ops/get-started/before-you-buy.md) krok po kroku.

## <a name="plan-human-resources-environments"></a>Planuj środowiska zasobów ludzkich

Zanim utworzysz swoje pierwsze środowisko kadrowe, powinieneś dokładnie zaplanować jego potrzeby w swoim projekcie. Podstawowa subskrypcja HR zawiera dwa środowiska: środowisko produkcyjne i domyślne standardowe środowisko testów akceptacyjnych (Sandbox). W zależności od złożoności projektu możesz zakupić dodatkowe środowiska do wspierania działań projektowych.

Oto kilka uwag dotyczących dodatkowych środowisk opcjonalnych:

- **Migracja danych**: Działania związane z migracją danych umożliwiają wykorzystanie środowiska piaskownicy do celów testowych w trakcie trwania projektu. Jeśli masz dodatkowe środowisko, możesz kontynuować działania związane z migracją danych, podczas gdy testowanie i konfiguracja odbywają się jednocześnie w innym środowisku.
- **Integracja** – Konfiguracja i testowanie integracji, które mogą obejmować integracje natywne lub niestandardowe, takie jak integracje z listą płac, systemami śledzenia kandydatów czy systemami i dostawcami świadczeń.
- **Szkolenie** - Możesz potrzebować osobnego środowiska skonfigurowanego z zestawem danych szkoleniowych, aby móc przeszkolić swoich pracowników w zakresie obsługi nowego systemu. 
- **Projekt wieloetapowy** - Dodatkowe środowisko może być potrzebne do obsługi konfiguracji, migracji danych, testowania lub innych działań w fazie projektu, która jest planowana po pierwszym uruchomieniu projektu.
- **Rozwój** — W infrastrukturze finansowej i operacyjnej możesz teraz rozszerzać rozwiązanie i tworzyć własne modyfikacje. Każdy programista musi używać swojego własnego środowiska programistycznego. Aby uzyskać więcej informacji, zobacz [Rozmieszczanie i dostęp do środowisk programistycznych](/fin-ops-core/dev-itpro/dev-tools/access-instances).
- **ZŁOTA** — W przypadku nowych wdrożeń częstą praktyką jest korzystanie z oddzielnego środowiska GOLD, które jest utrzymywane w stanie nieskazitelnym na potrzeby konfiguracji i migracji danych. To środowisko może być wykorzystywane w trakcie całego wdrożenia do odświeżania innych środowisk. Zostanie ono wykorzystane do stworzenia nowego środowiska produkcyjnego, które będzie miało podstawową konfigurację i migrację danych. Nie możesz wdrożyć środowiska produkcyjnego w infrastrukturze finansowej i operacyjnej, dopóki nie zakończysz procesu gotowości do działania. Aby uzyskać więcej informacji, zobacz [Przygotuj się do startu](/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live).

<!--NOTE: Need to come back and verify Tier-1 can be used and if a customer cannot purchase tier 3-5 need specific documentation about this.-->

> [!IMPORTANT]
> Rozważając swoje środowiska, zalecamy następujące podejście:
>
> - Użyj domyślnego standardowego środowiska testów akceptacyjnych (dawniej Sandbox) lub innego środowiska, aby przeprowadzić próbne przejście przed rozpoczęciem pracy.
> - Przechowuj szczegółową listę kontrolną, zawierającą każdy pakiet danych, który jest wymagany do migracji ostatecznych danych do środowiska produkcyjnego podczas przejścia na nową generację. To zalecenie jest szczególnie ważne, jeśli nie masz osobnego środowiska GOLD do przechowywania konfiguracji.
> - W całym projekcie używaj domyślnego standardowego środowiska testów akceptacyjnych (dawniej Sandbox) lub innego środowiska warstwy drugiej lub wyższej jako środowiska TEST. Jeśli potrzebujesz dodatkowych środowisk, twoja organizacja może je zakupić za dodatkową opłatą.

## <a name="create-an-lcs-project"></a>Tworzenie projektu LCS

Aby zarządzać swoimi środowiskami oprogramowania Human Resources za pomocą usługi LCS, należy najpierw utworzyć projekt LCS. Jeśli migrujesz środowisko zasobów ludzkich do infrastruktury finansów i operacji, musisz stworzyć nowy projekt LCS dla aplikacji finansowych i operacyjnych. Aby uzyskać więcej informacji, zajrzyj do [Migracja środowiska HR](hr-admin-migrate-overview). Jeśli masz już projekt LCS dla innych aplikacji finansowych i operacyjnych, możesz włączyć funkcje zasobów ludzkich w przestrzeni roboczej **Zarządzanie funkcjami**. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Kiedy nowy klient rejestruje się w programie HR, subskrypcja obejmuje obszar roboczy projektu wdrożenia. Po aktywacji usługi przez klienta administrator lokatora musi zalogować się na stronie <https://lcs.dynamics.com> przy użyciu konta lokatora. Przestrzeń robocza projektu jest automatycznie tworzona dla organizacji. Więcej informacji uzyskasz w [Usługi Lifecycle Services (LCS) dla klientów aplikacji finansowych i operacyjnych](/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs).

> [!NOTE]
> Aby zapewnić udane tworzenie rezerw, konto używane do tworzenia rezerw w środowisku Human Resources musi być przypisane do roli **Administratora systemu** lub **Dostawcy systemu** w środowisku Power Apps, które jest powiązane ze środowiskiem Human Resources. Aby uzyskać więcej informacji na temat przypisywania ról zabezpieczeń użytkownikom w Microsoft Power Platform, zobacz temat [Konfigurowanie zabezpieczeń użytkownika do zasobów](/power-platform/admin/database-security).

Zanim zaczniesz wdrażać środowiska, musisz zakończyć proces wdrażania projektu LCS. Aby uzyskać więcej informacji, zobacz [Wprowadzanie do projektu](/fin-ops-core/dev-itpro/lifecycle-services/project-onboarding). Więcej informacji o tym, jak korzystać z LCS, można znaleźć w [Przewodniku użytkownika Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide).

## <a name="deploy-human-resources-environments"></a>Wdrożenie środowisk HR

Wdrażanie aplikacji finansowych i operacyjnych, w tym HR, w chmurze wymaga zrozumienia środowiska i subskrypcji, w której są wdrażane, tego, kto może wykonywać poszczególne zadania, oraz tego, jakimi danymi i dostosowaniami trzeba zarządzać. Zalecamy, aby podczas wdrażania nowych środowisk używać konta serwisowego zamiast użytkownika nazwanego. Więcej informacji o tym, jak wdrażać środowiska w infrastrukturze finansowej i operacyjnej, można znaleźć w sekcji [Przegląd wdrażania chmury](/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

Aby wdrożyć środowisko produkcyjne HR na infrastrukturze finansowo-operacyjnej, musisz wykonać proces gotowości do działania. Aby uzyskać więcej informacji, zobacz [Przygotuj się do startu](/fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live). Proces ten obejmuje estymator subskrypcji w LCS. Aby uzyskać więcej informacji, zobacz [Estymator subskrypcji](/fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator).

## <a name="integrate-microsoft-power-platform-with-human-resources"></a>Integracja z rozwiązania Human Resources do rozwiązania Microsoft Power Platform

Microsoft Power Platform zapewnia pakiet możliwości dla aplikacji Dynamics 365 za pośrednictwem centrum administracyjnego Power Platform. Korzystanie z danych Human Resources można zintegrować i rozszerzać za pomocą Microsoft Power Platform. Aby uzyskać informacje na temat integracji działu kadr z Microsoft Power Platform, zobacz [Integracja Microsoft Power Platform z aplikacjami finansowymi i operacyjnymi](/fin-ops-core/dev-itpro/power-platform/overview).

## <a name="supported-geographies"></a>Obsługiwane regiony geograficzne

Aby uzyskać informacje o językach i regionach geograficznych obsługiwanych przez dział zasobów ludzkich, zobacz [Global by design: poznaj obsługiwane kraje i języki](https://dynamics.microsoft.com/availability-reports/).

## <a name="grant-access-to-the-environment"></a>Przyznawanie dostępu do środowiska

Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Musisz przyznać dostęp dodatkowym użytkownikom aplikacji. Trzeba dodać użytkowników i przypisać im odpowiednie role w środowisku Human Resources. Aby uzyskać więcej informacji, zobacz [tworzenie nowych użytkowników](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) i [przypisywanie użytkowników do ról zabezpieczeń](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles).

## <a name="additional-resources"></a>Dodatkowe zasoby
Możesz dowiedzieć się więcej o tym, jak używać i zarządzać projektami w LCS w infrastrukturze aplikacji finansowych i operacyjnych, korzystając z następujących zasobów:

- [Zasoby usługi Lifecycle Services](/fin-ops-core/dev-itpro/lifecycle-services/lcs.md)
- [Przewodnik użytkownika usługi Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Omówienie wdrożenia samoobsługowego](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md)
- [Strona główna: Operacje przenoszenia bazy danych](../fin-ops-core/dev-itpro/database/dbmovement-operations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
