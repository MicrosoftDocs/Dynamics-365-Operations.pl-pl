---
title: Opis usługi dla aplikacji Finance and Operations
description: Ten temat zawiera opis usługi dla aplikacji Finance and Operations.
author: tomhig
ms.date: 11/17/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: 262cf00bdca63876c284be40954ca5de559b993a
ms.sourcegitcommit: f11ad8d7ee8a4d2ee1a1bb601622b50e14955c4a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2021
ms.locfileid: "7825407"
---
# <a name="service-description-for-finance-and-operations-apps"></a>Opis usługi dla aplikacji Finance and Operations

[!include[banner](../includes/banner.md)]

Aplikacje Finance and Operations są produktami planowania zasobów przedsiębiorstwa (ERP) udostępnianymi w modelu „oprogramowanie jako usługa” (SaaS), które są oparte na platformie [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/) i do niej przeznaczone. Usługa Finance and Operations zapewnia organizacjom funkcje systemu ERP, które spełniają ich indywidualne wymagania i pomagają im adaptować się do stale zmieniającego się środowiska biznesowego, bez konieczności zarządzania infrastrukturą. Aplikacje Finance and Operations mogą zawierać dowolną liczbę następujących obszarów rozwiązania:

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

Wraz z [analizą biznesową](/power-bi/fundamentals/power-bi-service-overview), [Infrastrukturą](https://azure.microsoft.com/global-infrastructure/), [środowiskiem obliczeniowym](/azure/service-fabric/service-fabric-overview) i [usługami bazy danych](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/) te aplikacje pozwalają organizacjom wykonywać właściwe dla danej branży i operacyjne procesy biznesowe. Klienci obsługiwani przez partnerów wdrożeniowych sami określają konfigurację logiki aplikacji biznesowej, która najlepiej pasuje do ich indywidualnych procesów biznesowych. Funkcje i procesy biznesowe mogą być wzmacniane lub rozszerzane za pomocą następujących rozwiązań lub ich kombinacji:

- Wbudowane [funkcje personalizacji](personalize-user-experience.md)
- Narzędzia [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md)
- [Zestaw SDK Finance and Operations](../../dev-itpro/dev-tools/developer-home-page.md) oparty na [Visual Studio](https://visualstudio.microsoft.com) i [Azure DevOps automatyzacja kompilacji ](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- Rozwiązania niezależnych dostawców oprogramowania (ISV) od [AppSource](https://appsource.microsoft.com/partners)

Klienci sami wybierają podejście do rozwiązania według swoich wymagań. Razem z partnerem wdrożeniowym definiują, opracowują i testują swoje rozwiązanie przy użyciu narzędzi i najlepszych praktyk dostępnych w usługach [Microsoft Dynamics Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md). Istnieją cztery typowe scenariusze:

- Standardowe aplikacje Finance and Operations „gotowe do użytku” (bez rozszerzeń)
- Konfiguracja aplikacji Finance and Operations, która zawiera dowolną liczbę rozwiązań oprogramowania ISV
- Konfiguracja aplikacji Finance and Operations, która zawiera dowolną liczbę specjalnych rozszerzeń klienta
- Konfiguracja aplikacji Finance and Operations, która zawiera zarówno specjalne rozszerzenia klienta, jaki dowolną liczbę rozwiązań oprogramowania ISV

Organizacje mogą łatwo dodawać użytkowników i procesy biznesowe za pomocą prostego, przejrzystego modelu subskrypcji w miarę wzrostu swojej działalności. Aby uzyskać więcej informacji, zobacz [Przewodnik licencjonowania systemu Dynamics 365](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365).

## <a name="operating-model"></a>Model działania

Model działania aplikacji Finance and Operations wyznacza klientowi, partnerowi wdrożeniowemu i firmie Microsoft określone role i zakresy odpowiedzialności w trakcie cyklu życia usługi. Aby uzyskać więcej informacji, zobacz [Operacje i obsługa w chmurze](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md).

### <a name="customer-activities"></a>Działania klienta

Klienci pracują z partnerem i zespołem [Microsoft FastTrack](/dynamics365/fasttrack/) postępując zgodnie z [Przewodnikiem implementacji systemu Dynamics 365](https://community.dynamics.com/365/dynamics-365-fasttrack/p/dynamics365implementationguide), strukturą [Success by Design](/dynamics365/fasttrack/success-by-design-overview) oraz narzędziami i szablonami najlepszych praktyk dostępnymi w usługach [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md), aby zaimplementować swoje rozwiązanie. Do typowych działań należą między innymi następujące:

- Zarządzanie tożsamością użytkownika i zabezpieczeniami
- Definiowanie, opracowywanie i obsługa procesów biznesowych
- Definiowanie, opracowywanie, testowanie i obsługa rozszerzeń
- Monitorowanie wdrożeń nieprodukcyjnych i zarządzanie nimi
- Zarządzanie aktualizacjami aplikacji i sprawdzanie poprawności rozszerzeń
- Zarządzanie rozwiązaniami oprogramowania ISV i integracjami z produktami innych firm

### <a name="microsoft-responsibilities"></a>Zakres odpowiedzialności firmy Microsoft

Firma Microsoft zarządza usługą Finance and Operations, wdrażając, aktywnie monitorując i obsługując piaskownicę klientów oraz środowiska produkcyjne w subskrypcji usługi SaaS Microsoft. Zarządzanie to obejmuje alokowanie wymaganej infrastruktury systemowej w celu działania usługi i aktywne komunikowanie się z klientami w sprawie kondycji usługi. Zakres odpowiedzialności obejmuje:

**Zarządzanie infrastrukturą**
- Zabezpieczenia i izolacja
- Systemy operacyjne i wirtualizacja
- Serwery, przestrzeń dyskowa i sieć
- Zasilanie, łączność z siecią i chłodzenie centrum danych

**Zarządzanie platformą aplikacji**
- Monitorowanie i powiadomienia dotyczące aplikacji przez 24 godziny na dobę 7 dni w tygodniu
- Diagnostyka, aktualizacje platformy, poprawki, aktualizacje usługi
- Wybór trasy aplikacji, równoważenie obciążenia, replikacja witryny
- Inicjowanie obsługi środowiska i zarządzanie nim
- Zarządzanie bazą danych, wysoka dostępność / odzyskiwanie po awarii, skalowanie, operacje
- Wdrażanie, skalowanie w górę i skalowanie w dół środowiska obliczeniowego

## <a name="system-configuration"></a>Konfiguracja systemu

Aplikacje Finance and Operations są skalowane zależnie od wolumenu transakcji i obciążenia użytkownika. Każda implementacja klienta tworzy unikatowe rozwiązanie, które składa się z następujących elementów:

- **Kompozycja danych** — unikatowy zestaw parametrów sterujących zachowaniem, układem organizacji, strukturą danych głównych (takich jak wymiary finansowe i wymiary magazynowe) oraz szczegółowością śledzenia transakcji.
- **Rozszerzenie i konfiguracja** — mechanizmy rozszerzeń, które korzystają z rozszerzeń kodu, rozwiązań oprogramowania ISV oraz unikatowych konfiguracji, które obejmują przepływy pracy, integracje i konfiguracje raportów.
- **Wzorce użycia** — unikatowa kombinacja użycia online i wsadowego wraz z możliwością integracji z systemami na wejściu i wyjściu w celu utworzenia ujednoliconego przepływu danych oraz rozróżniania na podstawie widoków informacji używanych przez klientów w ich procesach biznesowych.

Firma Microsoft konfiguruje środowiska produkcyjne dla klientów o wielkości pozwalającej na obsługę wolumenu transakcji i współbieżności użytkowników. Firma Microsoft odpowiada za następujące zadania:

- Poprawne alokowanie zasobów środowiska produkcyjnego na podstawie informacji o profilowaniu klienta w [narzędziu do szacowania zapotrzebowania na subskrypcję usługi LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md)
- Ciągłe monitorowanie i diagnostyka dostępności usług w środowiskach produkcyjnych
- Analizowanie i rozwiązywanie problemów z wydajnością systemu związanych z aplikacjami Finance and Operations

Aby konfiguracja zapewniała wysoką wydajność, klienci muszą wykonać następujące zadania:

- Podanie dokładnych informacji dotyczących użycia implementacji Finance and Operations w [narzędziu do szacowania zapotrzebowania na subskrypcje usługi LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md).
- Kompilowanie i testowanie rozszerzeń pod kątem wydajności i skali.
- Odpowiednie testowanie konfiguracji danych pod kątem wydajności.
- Zapewnienie skalowalności poprzez [testowanie wydajności](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018) przed rozpoczęciem pracy.

## <a name="onboarding-and-implementation"></a>Dołączanie oraz implementacja

W poniższej tabeli pokazano typowe zdarzenia dołączania i implementacji.

| Wniosek | Oczekiwane działanie firmy Microsoft | Oczekiwane działanie klienta / partnera wdrożeniowego |
|---|---|---|
| Zakup początkowej oferty | Projekt usługi LCS jest tworzony po zakupieniu oferty na podstawie zdarzenia, które jest wyzwalane przez klienta. | Przejście przez [proces handlowy](before-you-buy.md) Enterprise Agreement (EA) lub Cloud Solution Provider (CSP). Partner tworzy dzierżawę dla klienta w razie potrzeby. |
| Zakup dodatku | Udzielenie klientowi dostępu do dodatku wybranego podczas implementacji. | Nie dotyczy |
| Planowanie i analiza implementacji | Udostępnienie odpowiednich narzędzi w LCS, jak [Narzędzie do modelowania procesów biznesowych (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md) i[współdziałanie z Azure DevOps](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md). | Wykonanie planowania projektu, skonfigurowanie Azure DevOps, dokończenie dołączania systemu i skonfigurowanie kont administratora. |

Aby uzyskać więcej informacji, zobacz [Przygotowanie do przeprowadzenia projektu implementacji](../imp-lifecycle/onboard.md).

## <a name="globalization"></a>Globalizacja

Aplikacje Finance and Operations są obsługiwane z różnych regionów świadczenia usługi Azure na świecie. Aplikacje Finance and Operations zawierają funkcje służące do obsługi różnych krajów/regionów oraz języków ojczystych. Aby uzyskać więcej informacji, zobacz [Funkcje związane z lokalizacją i wymagane przepisami prawa](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features).

### <a name="countryregion-specific-considerations"></a>Uwagi dotyczące niektórych krajów/regionów

- Klienci działające w branży regulowanej lub organizacje handlowe prowadzące interesy z podmiotami z Francji, które wymagają lokalnego przechowywania danych powinni zapoznać się z tematem [Aplikacje Finance and Operations we Francji](../../dev-itpro/deployment/france-local-deployment.md).
- Klienci prowadzący działalność w Chinach powinni zapoznać się z tematem [Finance and Operations — obsługiwane przez firmę 21Vianet w Chinach](../../dev-itpro/deployment/china-local-deployment.md).
- Klienci prowadzący działalność w Rosji powinni zapoznać się z [rosyjskimi przepisami lokalizacji danych osobowych](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia).

### <a name="general-data-protection-regulation-gdpr"></a>Ogólne rozporządzenie o ochronie danych (RODO)

W przypadku aplikacji Finance and Operations firma Microsoft jest podmiotem przetwarzającym dane. Jako podmiot przetwarzający dane dostarcza w Finance and Operations procesy i funkcje, które pomagają klientom wywiązywać się z obowiązków wynikających z roli administratora danych w rozumieniu RODO. Aby uzyskać więcej informacji, zobacz temat [Omówienie RODO](../../dev-itpro/gdpr/gdpr-guide.md).

## <a name="environment-and-data-management"></a>Zarządzanie środowiskiem i danymi

W tej sekcji opisano typowe zdarzenia zarządzania środowiskiem i danymi występujące w usłudze.

### <a name="environment-and-data-management-events-for-production-instances"></a>Zdarzenia zarządzania środowiskiem i danymi w wystąpieniach produkcyjnych

Usługa LCS dostarcza [samoobsługowe narzędzia](../../dev-itpro/deployment/infrastructure-stack.md) oraz [operacje przemieszczania bazy danych](../../dev-itpro/database/dbmovement-operations.md), które służą do wykonywania zadań zarządzania środowiskiem i danymi. Oto kilka przykładów:

**Zdarzenie:** [żądanie wystąpienia produkcyjnego](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- Wypełnienie [listy kontrolnej rozpoczynania eksploatacji](../imp-lifecycle/prepare-go-live.md) i przesłanie jej zespołowi [Microsoft FastTrack](/dynamics365/fasttrack/).
- Użycie [narzędzia do szacowania zapotrzebowania na subskrypcje](../../dev-itpro/lifecycle-services/subscription-estimator.md) przed zażądaniem wystąpienia produkcyjnego.
- Wykonanie wszystkich zadań implementacji określonych w [metodologii usługi LCS](../../dev-itpro/lifecycle-services/create-methodology.md).

**Zdarzenie:** [kopiowanie bazy danych piaskownicy do wystąpienia produkcyjnego](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Wykonano dla próbnego lub rzeczywistego przełączenia do rozpoczęcia eksploatacji.

**Zdarzenie:** [tryb konserwacji](../../dev-itpro/sysadmin/maintenance-mode.md)

1. Włączenie trybu konserwacji w LCS.
2. Wykonanie wymaganej konserwacji.
3. Wyłączenie trybu konserwacji w LCS.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>Zdarzenia zarządzania środowiskiem i danymi w wystąpieniach nieprodukcyjnych

Usługa LCS dostarcza [samoobsługową aprowizację](../../dev-itpro/deployment/infrastructure-stack.md) oraz [operacje przemieszczania bazy danych](../../dev-itpro/database/dbmovement-operations.md), które służą do wykonywania zadań zarządzania środowiskiem i danymi. Oto kilka przykładów:

**Zdarzenie:** [wdrażanie nowego wystąpienia piaskownicy](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- Upewnienie się, że wszystkie wymagane wystąpienia zostały [zaplanowane](../imp-lifecycle/environment-planning.md) i że zostały zakupione odpowiednie oferty dodatku.
- Uruchomienie procesu wdrażania w usługach LCS.
- Wykonanie wszystkich zadań określonych w listach kontrolnych usługi LCS.
    
>[!NOTE]
>Programistyczne środowisko piaskownicy to maszyna wirtualna, która jest [wdrażana w subskrypcji systemu Azure klienta](../../dev-itpro/dev-tools/access-instances.md) i zarządzana przez klienta.

**Zdarzenie:** [kopiowanie bazy danych złotej konfiguracji z piaskownicy do środowiska produkcyjnego](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Wykonano dla próbnego lub rzeczywistego przełączenia do rozpoczęcia eksploatacji.

**Zdarzenie:** przywracanie kopii zapasowej punktu [w czasie w wystąpieniu nieprodukcyjnym](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- Wykonanie opcji [Odśwież bazę danych](../../dev-itpro/database/database-refresh.md) w usłudze LCS.
- Po skopiowaniu: usunięcie lub ukrycie poufnych danych za pomocą skryptów, dostosowanie konfiguracji aplikacji specyficznych dla środowiska (jak punkty końcowe integracji) oraz włączenie lub dodanie użytkowników. Zmiany są dokonywane przez zastosowanie [pakietu danych](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package).

**Zdarzenie:** [przywracanie do punktu w czasie bazy danych wystąpienia nieprodukcyjnego](../../dev-itpro/database/database-point-in-time-restore.md)

- Zaakceptowanie, że procesu nie można cofnąć.
- Uruchomienie operacji przywracania punktu w czasie w usłudze LCS.

**Zdarzenie:** kopiowanie bazy danych piaskownicy warstwy 2 do piaskownicy programistycznej w celu rozwiązywania problemów i [debugowania](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- Uruchomienie operacji eksportu bazy danych w usługach LCS na środowisku piaskownicy warstwy 2.
- Zaimportowanie i zaktualizowanie bazy danych w środowisku programistycznym.

## <a name="data-backup-and-retention"></a>Tworzenie kopii zapasowej i przechowywanie danych

Bazy danych środowisk Finance and Operations w subskrypcji SaaS są chronione przez automatyczne kopie zapasowe. W środowiskach produkcyjnych automatyczne kopie zapasowe są przechowywane przez 28 dni, chyba że firma Microsoft wycofa dane. W środowiskach piaskownicy (warstwa 2+) są one przechowywane przez siedem dni. Wycofanie środowiska produkcyjnego jest możliwe, jeśli podczas planowanej aktualizacji konserwacyjnej wystąpi błąd.

Aby uzyskać więcej informacji o automatycznych kopiach zapasowych, zobacz temat [Automatyczne kopie zapasowe — baza danych Azure SQL Database i zarządzane wystąpienie SQL](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).

## <a name="service-activity-responsibilities"></a>Zakres odpowiedzialności za działanie usługi

W poniższej tabeli opisano typowe scenariusze i działania dotyczące usługi. Ponadto jest w niej wskazane, kto jest za nie odpowiedzialny: firma Microsoft, klient czy zarówno firma Microsoft, jak i klient.

| Działanie | Zakres odpowiedzialności firmy Microsoft | Zakres odpowiedzialności klienta |
|---|---|---|
| **Aprowizacja początkowych dzierżaw** | | |
| Prognozowanie wielkości obciążenia w LCS przy użyciu narzędzia do szacowania zapotrzebowania na subskrypcje i zażądanie aprowizacji takiego środowiska. | | X |
| Aprowizacja wszystkich wystąpień produkcyjnych i nieprodukcyjnych. | X | |
| Sprawdzenie poprawności wdrożonych wystąpień produkcyjnych i nieprodukcyjnych. | | X |
| **Aktualizacje usługi** | |
| Zastosuj aktualizacje usług do wyznaczonych wystąpień nieprodukcyjnych i produkcyjnych. | X | |
| Ręcznie zastosuj aktualizacje usługi z usługi LCS do wystąpień piaskownicy. Zdefiniuj, opracuj, przetestuj aktualizację i podaj pakiet aktualizacji kodu z powrotem do usługi LCS. | | X |
| Aktualizacje rozszerzeń żądań i harmonogramów są stosowane do wystąpienia produkcyjnego. | | X |
| Utworzenie kopii zapasową kodu i danych wystąpienia produkcyjnego przed zastosowaniem jakichkolwiek aktualizacji. | X | |
| W przypadku awarii należy wycofać wystąpienie produkcyjne za pomocą kopii zapasowej kodu i danych. | X | |
| **Zarządzanie danymi (kopia zapasowa, przywracanie i aktualizowanie)** | | |
| Wykonanie kopii zapasowej bazy danych. | X | |
| Określenie planu wysokiej dostępności i odzyskiwania po awarii. | X | |
| Monitorowanie wydajności bazy danych wystąpienia produkcyjnego. | X | |
| Dostrojenie wydajności bazy danych wystąpienia produkcyjnego. | X | |
| Wykonaj odświeżenie bazy danych instancji produkcyjnej do punktu w czasie do instancji nieprodukcyjnej. | | X |
| **Aktualizowanie infrastruktury** | | |
| Zaplanowanie regularnych aktualizacji infrastruktury. | X | |
| **Skalowanie w górę i w dół (użytkownicy, przestrzeń dyskowa i wystąpienia)** | | |
| Kupienie dodatkowych użytkowników i dodatków nieprodukcyjnych. | | X |
| Aktualizacja zmian użycia w narzędziu do szacowania zapotrzebowania na subskrypcje usługi LCS. | | X |
| Zgłaszanie wszelkich istotnych problemów z wydajnością, które mają wpływ na korzystanie z usługi. | | X |
| Aktywne zarządzanie zasobami wymaganymi przez daną usługę. | X | |
| Badanie zdarzeń i rozwiązywanie problemów. | X | |
| **Zabezpieczenia (dostęp użytkownika)** | | |
| Zapewnienie dostępu użytkowników do usługi. | | X |
| Zapewnienie dostępu do projektu usługi LCS w celu zarządzania i obsługi wystąpień, które zostały wdrożone za pomocą usługi LCS. | | X |
| **Monitorowanie wystąpień produkcyjnych** | | |
| Monitorowanie wystąpień produkcyjnych 24 godziny na dobę i 7 dni w tygodniu. | X | |
| Aktywne powiadamianie klienta o zdarzeniach wpływających na wystąpienie produkcyjne. | X | |
| **Zarządzanie wystąpieniami nieprodukcyjnymi i monitorowanie ich** | | |
| Zarządzanie wystąpieniami nieprodukcyjnymi przy użyciu usługi LCS. | | X |
| Monitorowanie wystąpień nieprodukcyjnych. | | X |

## <a name="service-update-strategy"></a>Strategia aktualizacji usługi

W rozumieniu [zasad cyklu życia oprogramowania](../../dev-itpro/migration-upgrade/versions-update-policy.md) aplikacje Finance and Operations podlegają zasadom [Modern Lifecycle Policy](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy) firmy Microsoft jako produkty serwisowane i obsługiwane w trybie ciągłym. 

Firma Microsoft co roku wydaje osiem aktualizacji usługi aplikacji Finance and Operations w następujących miesiącach:

- Styczeń
- luty
- kwiecień
- maj
- lipiec
- sierpień
- październik
- listopad

>[!NOTE]
>Aktualizacje kwietniowe i październikowe zawierają więcej nowych funkcji. Klienci mogą wstrzymać pojedynczą aktualizację usługi przez maksymalnie trzy kolejne cykle aktualizacji.

Aby uzyskać więcej informacji, zobacz następujące tematy:

- [Omówienie aktualizacji usługi One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [Konfigurowanie aktualizacji usługi w LCS](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [Wstrzymywanie aktualizacji usługi w LCS](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [Odbieranie powiadomień o aktualizacjach usługi w LCS](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [Narzędzia testowania regresji do sprawdzania poprawności aktualizacji usługi](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Plan rozwoju usługi Dynamics 365 i fale wydania](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>Zabezpieczenia i dostęp administracyjny

Dostęp administracyjny do środowiska produkcyjnego Finance and Operations jest ściśle kontrolowany i rejestrowany. Dane klientów są obsługiwane zgodnie z [warunkami świadczenia usług online firmy Microsoft](https://www.microsoft.com/licensing/terms/productoffering). 

### <a name="customer-administrative-access"></a>Dostęp administracyjny klienta

Administrator dzierżawy klienta może uzyskać dostęp do wystąpień produkcyjnych lub wystąpień nieprodukcyjnych w sposób opisany w następującej tabeli:

| Typ środowiska | Cel | Poziom dostępu klienta |
|---|---|---|
| **Nieprodukcyjne**<br>Piaskownica warstwy 1 | Środowisko nieprodukcyjne, które klienci wdrażają w celach programistycznych, demonstracyjnych lub szkoleniowych. | Piaskownica warstwy 1 (określana także jako środowisko hostowane w chmurze) to maszyna wirtualna zarządzana przez klienta, która jest wdrażana w subskrypcji platformy Azure klienta z usługi LCS. Ponieważ jest to maszyna wirtualna w subskrypcji platformy Azure klienta, klient ma pełny dostęp administracyjny do środowiska za pośrednictwem pulpitu zdalnego. |
| **Nieprodukcyjne**<br>Piaskownica warstwy 2 (lub wyższej) | Środowisko nieprodukcyjne, które klienci wdrażają w celu testowania akceptacji użytkownika, testowania integracji, szkolenia, przemieszczania lub jakichkolwiek innych scenariuszy przedprodukcyjnych. | Piaskownice warstwy 2 i wyższych są wdrażane w subskrypcji Finance and Operations w modelu SaaS. Dostęp do baz danych Azure SQL Database, które są skojarzone ze środowiskiem nieprodukcyjnym, jest udzielany za pośrednictwem [dostępu dokładnie na czas](../../dev-itpro/database/database-just-in-time-jit-access.md). Brak dostępu do pulpitu zdalnego. |
| **Produkcyjne** | Środowisko produkcyjne jest wdrażane, gdy projekt jest [gotowy do początkowego uruchomienia](/imp-lifecycle/environment-planning.md#production-system-readiness). | Środowiska produkcyjne są wdrażane w subskrypcji modelu SaaS. Dostęp odbywa się w całości przez przeglądarkę, punkty końcowe usługi lub usługę LCS. |

### <a name="microsoft-administrative-access"></a>Dostęp administracyjny firmy Microsoft

W poniższej tabeli są pokazane różne poziomy dostępu poszczególnych administratorów z firmy Microsoft:

| Administrator | Dane odbiorcy |
|---|---|
| Zespół szybkiej reakcji Operations<br>(Tylko dla kluczowych pracowników) | Dostęp jest udzielany za pomocą biletu pomocy technicznej. Dostęp podlega inspekcji i jest ograniczony do czasu trwania działania pomocy technicznej. |
| Usługi pomocy technicznej firmy Microsoft (CSS) | Brak bezpośredniego dostępu. Klient może używać funkcji udostępniania ekranu do pracy z pracownikami pomocy technicznej w celu debugowania problemów. |
| Projektowanie | Brak bezpośredniego dostępu. Zespół szybkiej reakcji Operations może współpracować z inżynierami w celu debugowania problemów korzystając z funkcji udostępniania ekranu. |
| Inne osoby w firmie Microsoft | Brak dostępu. |

## <a name="monitoring"></a>Monitorowanie

Firma Microsoft zainwestowała w rozbudowany zestaw narzędzi do monitorowania i diagnozowania wystąpień produkcyjnych klientów. Firma Microsoft monitoruje środowiska produkcyjne klientów 24 godziny na dobę, 7 dni w tygodniu. Aby uzyskać więcej informacji, zobacz [Obsługa i monitorowanie produkcji](../imp-lifecycle/production-support-monitoring.md).

| Zakres odpowiedzialności firmy Microsoft | Zakres odpowiedzialności klienta |
|---|---|
| <ul><li>Monitorowanie dostępności usługi.</li><li>Ciągłe monitorowanie i wysyłanie alertów za pomocą metryk kondycji i mechanizmów watchdog dla składników o znaczeniu krytycznym, takich jak serwer obiektów aplikacji (AOS), Batch, struktura importu/eksportu danych (DIXF), Commerce i Management Reporter.</li><li>Monitorowanie obniżenia wydajności spowodowanego przez usługi infrastruktury (takie jak Azure Active Directory \[Azure AD\] i Azure SQL).</li><li>Jeśli firma Microsoft ustali, że jeden proces lub zadanie wsadowe powoduje aberrację, proces lub zadanie zostanie przerwane po zakończeniu komunikacji z klientem.</li></ul> | <ul><li>Monitorowanie zmian konfiguracji i rozszerzeń aplikacji, które mogą powodować problemy z działaniem i wydajnością.</li><li>Błędy aplikacji muszą być diagnozowane przy użyciu narzędzi do monitorowania. Za pomocą tych narzędzi można diagnozować zgłoszone przez użytkownika aberracje dotyczące wydajności.</li><li>Należy informować firmę Microsoft, jeśli istnieje oczekiwane obciążenie systemu wykraczające poza prognozowane szczytowe użycie.</li><li>Jeśli w wystąpieniu produkcyjnym nie ma dostępnej właściwej usługi, klient może użyć usługi LCS do zgłoszenia [przestoju produkcyjnego](../../dev-itpro/lifecycle-services/report-production-outage.md).</li></ul> |

Przesyłając żądania pomocy technicznej w trybie online za pośrednictwem usługi LCS, klienci umożliwiają firmie Microsoft szybką i skuteczną reakcję z wykorzystaniem głębokiej wiedzy technicznej. Chociaż opcja telefonu jest dostępna, należy jej używać tylko w przypadku, gdy opcja online nie działa. Aby uzyskać więcej informacji, zobacz [Opcje telefonicznej pomocy technicznej](/power-platform/admin/support-overview.md?toc=/dynamics365/fin-ops-core/dev-itpro/toc.json&bc=/dynamics365/breadcrumb/toc.json#is-there-a-phone-number-i-can-call-to-contact-support).

## <a name="incident-management"></a>Zarządzanie zdarzeniami

Firma Microsoft reaguje na zdarzenia i eliminuje je na podstawie poziomów ważności. Poziomy ważności zdarzenia firmy Microsoft można zmienić podczas wstępnej oceny zdarzenia oraz gdy w miarę uzyskania więcej informacji dotyczących wpływu i zakresu. Jeśli zdarzenie zostanie zminimalizowane, ważność zdarzenia pozostanie niezmieniona.

Aby uzyskać więcej informacji o poziomach ważności, zobacz [tę tabelę ważności](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request).

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>Ciągłość biznesowa dzięki wysokiej dostępności i odzyskiwaniu po awarii 

Firma Microsoft zapewnia ciągłość biznesową i odzyskiwanie po awarii wystąpień produkcyjnych aplikacji Finance and Operations w przypadku awarii w całym regionie świadczenia usługi Azure. Aby uzyskać więcej informacji, zobacz temat [Ciągłość działania i odzyskiwanie po awarii](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md).

- **Wysoka dostępność** — funkcje wysokiej dostępności służą zapobiegania przestojom, które są spowodowane awarią jednego węzła w centrum danych platformy Azure. W każdej architekturze chmury zestawy dostępności platformy Azure są używane w warstwie środowiska obliczeniowego, aby zapobiegać zdarzeniom single point of failure. Wysoką dostępność baz danych zapewniają [funkcje wysokiej dostępności Azure SQL](/azure/azure-sql/database/high-availability-sla).
- **Odzyskiwanie po awarii** — [funkcje odzyskiwania po awarii platformy Azure](/azure/best-practices-availability-paired-regions) chronią każdą usługę przed awariami, które mają rozległy wpływ na całe centrum danych platformy Azure. Oto niektóre z tych funkcji:

    - Aktywna replikacja geograficzna Azure SQL podstawowej bazy danych (baza danych biznesowych).
    - Geograficznie nadmiarowe kopie magazynu Blob Storage platformy Azure (który zawiera załączniki dokumentów) w innych regionach świadczenia usługi Azure.
    - Region pomocniczy replikacji usługi SQL Azure i magazynu Blob Storage platformy Azure.

Replikacją są objęte podstawowe magazyny danych. Dlatego składniki każdej usługi, takie jak Management Reporter i magazyn jednostek, korzystają z przekształconych danych z podstawowej bazy danych. Te dane muszą zostać wygenerowane po skonfigurowaniu witryny odzyskiwania i uruchomieniu usługi. Artefakty kodu klienta i odzyskane magazyny danych służą do ponownego wdrożenia witryny. Ponowne wdrożenie umożliwia replikację stanu węzłów obliczeniowych, wraz z siecią i innymi składnikami, za pomocą odzyskanych magazynów danych w celu skonfigurowania witryny pomocniczej. Jeśli odzyskiwania po awarii zostanie użyte odzyskanie wystąpienia produkcyjnego klienta, firma Microsoft i klient będą wykonywać swoje obowiązki w zakresie [zarządzania zdarzeniami](service-description.md#incident-management).

Plany i procedury odzyskiwania po awarii firmy Microsoft są regularnie badane w audytach System and Organization Controls (SOC). Te audyty zgodności atestują proces techniczny i proceduralny odzyskiwania po awarii firmy Microsoft, w aplikacji Dynamics 365 Finance and Operations. Raporty audytów [zgodności SOC](/compliance/regulatory/offering-soc-2) i wszystkie inne raporty zgodności są dostępne w [ofercie rozwiązań do zapewniania zgodności Centrum zaufania Microsoft](/compliance/regulatory/offering-home).

| Zakres odpowiedzialności firmy Microsoft | Zakres odpowiedzialności klienta |
|---|---|
| Firma Microsoft rezerwuje środowisko pomocnicze w sparowanych centrum danych platformy Azure podczas wdrażania podstawowego wystąpienia produkcyjnego. Aby uzyskać więcej informacji, zobacz temat [Ciągłość działania i odzyskiwanie po awarii (BCDR): sparowane regiony świadczenia usługi Azure](/azure/best-practices-availability-paired-regions). | None |
| Podczas wdrażania podstawowego wystąpienia produkcyjnego firma Microsoft uaktywnia nadmiarowość geograficzną usługi Azure SQL i magazynu Blob Storage platformy Azure. | None |
| Firma Microsoft uaktywnia automatyczne tworzenie kopii zapasowych w bazach danych Azure SQL Database. | None |
| <p>Gdy wystąpi awaria, firma Microsoft ustala, czy dla klienta ma zostać wykonany tryb failover i czy zostaną utracone dane. Mogą zostać utracone dane z maksymalnie pięciu sekund. Aby uzyskać więcej informacji, zobacz temat [Przywracanie geograficzne bazy danych Azure SQL Database](https://azure.microsoft.com/blog/azure-sql-database-geo-restore).</p><p>W przypadku utraty danych firma Microsoft prosi klienta o wylogowanie w celu wykonania trybu failover.</p> | W przypadku utraty danych od klienta może być wymagane pisemne zatwierdzenie wyzwolenia trybu failover. |
| Gdy dochodzi do trybu failover, dana usługa działa w trybie ograniczonym. Nie można wyzwolić konserwacji aktualizacji w trybie failover. | W trybie failover klient nie może zażądać wdrożenia pakietu ani innych zwykłego żądania konserwacji. |
| Po przywróceniu sprawności centrum danych firma Microsoft włącza ponownie wystąpienie produkcyjne w podstawowym regionie świadczenia usługi Azure. Zostaje wznowione normalne działanie. | Od klienta może być wymagane pisemne zatwierdzenie przełączenia z powrotem na wystąpienie produkcyjne w podstawowym regionie świadczenia usługi Azure. |

## <a name="finance-and-operations-support-offerings"></a>Oferty pomocy technicznej Finance and Operations

Pomoc techniczna jest dostępna na rynkach, na których są oferowane usługi Finance and Operations. [Działania pomocy technicznej](../../dev-itpro/lifecycle-services/lcs-support.md) są wykonywane w usługach LCS lub aplikacjach Finance and Operations. Oto kilka przykładów:

- [Wyszukiwanie problemów](../../dev-itpro/lifecycle-services/issue-search-lcs.md) w LCS
- [Zintegrowana pomoc techniczna](../../dev-itpro/lifecycle-services/support-experience.md) w aplikacjach Finance and Operations
- [Pomoc techniczna w chmurze](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md) w usłudze LCS

Firma Microsoft oferuje klientom Finance and Operations trzy plany pomocy technicznej: Premier, Professional Direct oraz pomoc techniczną zawartą w subskrypcji. Poziom pomocy technicznej różni się w zależności od planu. W poniższej tabeli przedstawiono porównanie tych trzech planów.

| Element pomocy technicznej | Premier | Professional Direct | Subskrypcja |
|---|---|---|---|
| Przesyłanie nieograniczonej liczby zdarzeń przerwy/poprawki | Tak | Tak | Tak |
| Dostęp 24 godziny na dobę i 7 dni w tygodniu za pośrednictwem usługi LCS | Tak | Tak | Tak |
| Czas reakcji na zdarzenie | Mniej niż jedna godzina | Mniej niż jedna godzina | Następny dzień roboczy |
| Godziny udzielania porad | Pule są nabywane według umowy. | Nie | Nie |
| Dedykowany opiekun pomocy technicznej | Tak | Nie | Nie |
| Dedykowany inżynier pomocy technicznej | Angażowanie na mocy oddzielnej umowy | Nie | Nie |

Aby uzyskać więcej informacji, zobacz [Omówienie pomocy technicznej](/power-platform/admin/support-overview).

### <a name="process-to-engage-support"></a>Proces angażowania pomocy technicznej

W przypadku zdarzeń, które są związane z aplikacjami Finance and Operations, klienci przesyłają bilety pomocy technicznej do firmy Microsoft za pośrednictwem usługi LCS. CSS obsługuje zdarzenia na podstawie planu pomocy technicznej klienta oraz ważności zdarzenia przypisanej przez CSS.

### <a name="service-level-agreement"></a>Umowa dotycząca poziomu usług

Firma Microsoft zobowiązuje się do utrzymania dostępności usługi na poziomie 99,9 procent miesięcznie. Jeśli Firma Microsoft nie osiągnie i nie utrzyma poziomu danej usługi zgodnie z opisem w umowie dotyczącej poziomu usług, klientowi może przysługiwać kredyt na poczet części miesięcznych opłat za usługę. Aby uzyskać informacje dotyczące inicjowania kredytu na usługę, zobacz sekcję „Roszczenia” [umowy SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

## <a name="important-resources"></a>Ważne zasoby

- **[Centrum zaufania](https://www.microsoft.com/trust-center)** — zawiera informacje o miejscu przechowywania danych Finance and Operations oraz dodatkowe informacje o procedurach dotyczących prywatności, zgodności i zabezpieczeń
- **[Postanowienia licencyjne i dokumentacja](https://www.microsoftvolumelicensing.com/)** — umożliwia szybkie uzyskanie dostępu do postanowień licencyjnych i informacji dodatkowych dotyczących korzystania z produktów i usług licencjonowanych za pomocą programów licencjonowania zbiorczego firmy Microsoft.
- **[Postanowienia licencyjne](https://www.microsoft.com/licensing/product-licensing/)** — zasoby dostępne na tej stronie definiują warunki i zastrzeżenia dotyczące oprogramowania i usług online kupowanych za pośrednictwem handlowych programów licencjonowania firmy Microsoft.
- **[Zasady cyklu życia produktów i usług Microsoft](/lifecycle/)** — ta strona zawiera spójne i przewidywalne wytyczne dostępności pomocy technicznej przez cały okres użytkowania produktu.
- **[Przewodnik licencjonowania](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** — ten podręcznik zawiera więcej informacji na temat sposobu licencjonowania systemu Dynamics 365.
- **[Pomoc techniczna dla klientów](https://dynamics.microsoft.com/support/)** — uzyskiwanie najlepszej w branży pomocy technicznej do aplikacji systemu Dynamics 365.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)** — zarządzanie cyklem życia aplikacji i zapewnienie przewidywalnych, powtarzalnych implementacji o wysokiej jakości.

## <a name="definitions"></a>Definicje

### <a name="azure-region"></a>[Region systemu Azure](/azure/availability-zones/az-overview#regions)

Region geograficzny, w którym istnieje co najmniej jedno centrum danych platformy Azure. Przykłady: Stany Zjednoczone i Europa.

### <a name="business-process-modeler-bpm"></a>[Narzędzie do modelowania procesów biznesowych (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)

Narzędzie w usługach LCS, które pomaga wykonać analizę luk zdatności danej implementacji za pomocą definicji procesów biznesowych z American Productivity & Quality Center (APQC), które są obsługiwane w aplikacjach Finance and Operations.

### <a name="cloud-solution-provider"></a>Dostawca rozwiązania usług w chmurze

Partner, który bierze udział w programie Microsoft Cloud Solution Provider (CSP) i dostarcza klientom usługi w chmurze o wartości dodanej, pomoc techniczną, jedną fakturę oraz zarządzanie klientami stosownie do skali.

### <a name="customer"></a>Klient

Osoba prawna, który zużywa aplikacje Finance and Operations i jest reprezentowana przez dzierżawę w programie Office 365.

### <a name="development-environment"></a>Środowiska programistyczne

Nieprodukcyjne środowisko piaskownicy, które służy do opracowywania rozszerzeń. Klienci wdrażają to środowisko we własnej subskrypcji platformy Azure z usługi LCS. Tego środowiska można również używać do celów demonstracyjnych, szkoleniowych i innych zadań testowania. Jest również nazywane [piaskownicą warstwy 1](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher).

### <a name="downtime"></a>Przestój

Okres, w którym użytkownicy nie mogą się zalogować lub uzyskać dostępu do ich aktywnej dzierżawy z powodu awarii w ważnej platformie lub infrastrukturze usług, co zostało potwierdzone przez firmę Microsoft na podstawie automatycznego monitorowania kondycji i dzienników systemowych. Do przestoju nie zalicza się zaplanowanego przestoju, niedostępności funkcji dodatku usługi, braku możliwości dostępu do usługi z powodu modyfikacji usługi lub okresów, w których wyczerpano zdolności jednostki skalowania.

### <a name="implementation-partner"></a>Partner wykonujący implementację

Partner wybrany przez klienta w celu dostosowywania, konfigurowania, implementowania i zarządzania jego rozwiązaniami Finance and Operations.

### <a name="incident"></a>Zdarzenie

Problem, który klienci napotkają podczas korzystania z usługi Finance and Operations, i na temat którego przesyłają bilet za pośrednictwem usługi LCS.

### <a name="microsoft-customer-support-services-css"></a>Usługi pomocy technicznej firmy Microsoft (CSS)

Globalny zespół pomocy technicznej firmy Microsoft, który jest dedykowany do pilnowania jakości usługi aplikacji Finance and Operations.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

Portal administracyjny do zarządzania cyklem życia aplikacji Finance and Operations od wersji próbnej, przez implementację, do zarządzania poprodukcyjnego i pomocy technicznej. Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md).

### <a name="non-production-instance"></a>Wystąpienie nieprodukcyjne

Dowolne z następujących wystąpień usługi używane przez klienta do sprawdzania poprawności rozszerzeń i wykonywania innych zadań programistycznych:

- **Piaskownica warstwy 1** — wystąpienie programistyczne (hostowane przez klienta)
- **Piaskownica warstwy 2** — standardowe wystąpienie testowania akceptacji
- **Piaskownica warstw 3–5** — piaskownice dodatków

Aby uzyskać więcej informacji o warstwach 2–5, zobacz temat [Wybór poprawnego środowiska warstwy 2 lub wyższego](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment).

### <a name="production-instance"></a>Wystąpienie produkcyjne

Środowisko Finance and Operations używane przez klienta do zarządzania codziennymi transakcjami i procesami biznesowymi „na żywo”.

### <a name="sandbox-environment"></a>Środowisko piaskownicy

Środowisko nieprodukcyjne używane przez klienta do celów demonstracyjnych, szkoleniowych, testowania akceptacji użytkownika, sprawdzania poprawności rozszerzeń i innych zadań testowania.

### <a name="service"></a>Serwis

Wszystkie podstawowe usługi, które są zawarte w aplikacjach Finance and Operations.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Umowa dotyczące poziomu usług (SLA) usług online firmy Microsoft

Umowa SLA obejmująca usługi online firmy Microsoft. Aby uzyskać więcej informacji, zobacz [Umowy dotyczące poziomu usług](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

### <a name="service-update"></a>Aktualizacja usługi

Firma Microsoft regularnie serwisuje środowiska Finance and Operations, dokonując aktualizacji usług. Klienci, w zależności od własnych potrzeb biznesowych, wyznaczają własny kalendarz aktualizacji usług. Aby uzyskać więcej informacji, zobacz [Aktualizacje usługi One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="user"></a>Użytkownik

Osoba, która używa środowisk Finance and Operations i jest skojarzona z dzierżawą klienta.
