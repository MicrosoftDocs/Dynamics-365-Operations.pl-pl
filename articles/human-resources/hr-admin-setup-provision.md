---
title: Ustanowienie rozwiązania Human Resources
description: W tym artykule wyjaśniono proces aprowizacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.
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
ms.openlocfilehash: 341b14d493c85a1e94666fa7e07b80704645e5f1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858251"
---
# <a name="provision-human-resources"></a>Ustanowienie rozwiązania Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



W tym artykule wyjaśniono proces aprowizacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources. 

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można aprowizować nowe środowisko produkcyjne, muszą zostać spełnione następujące wymagania wstępne:

- Użytkownik dokonał zakupu aplikacji Human Resources u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). Jeśli masz już licencję na oprogramowanie Microsoft Dynamics 365 uwzględniającą plan rozwiązania Human Resources, a nie jesteś w stanie wykonać kroków opisanych w tym artykule, skontaktuj się z pomocą techniczną.

- Administrator globalny musi się zarejestrować w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) i utworzyć nowy projekt programu Human Resources. 

## <a name="provision-a-human-resources-trial-environment"></a>Inicjowanie obsługi środowiska próbnego Human Resources

>[!NOTE]
> Począwszy od kwietnia 2022 roku środowiska próbne zasobów ludzkich nie będą dostępne w samodzielnym aplikacji. Potencjalni klienci, którzy są zainteresowani oceną możliwości zasobów ludzkich w aplikacjach finansowych i operacyjnych, mogą to zrobić, korzystając z bezpłatnej 30-dniowej wersji próbnej oraz danych demonstracyjnych. Dynamics 365 Finance będzie obejmował funkcje kadrowe wprowadzone do infrastruktury finansowej poprzez połączenie samodzielnej aplikacji. Więcej informacji na ten temat można znaleźć w części [Łączenie ofert HR zapewnia klientom wspólne możliwości](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers) Więcej informacji na temat testów Dynamics 365 Finance można znaleźć w [przewodniku krok po kroku](../fin-ops-core/fin-ops/get-started/before-you-buy.md). 


Przed rozpoczęciem inicjowania obsługi pierwszej piaskownicy lub środowiska produkcyjnego można zaimprowizować [środowisko próbne Human Resources](https://go.microsoft.com/fwlink/p/?LinkId=2115962) w celu weryfikacji funkcji Human Resources. Środowiska próbne zawierają fikcyjne dane, których można używać do eksplorowania programu w bezpieczny sposób. Chociaż właścicielem środowiska próbnego jest użytkownik, który je utworzył, można do niego zaprosić innych użytkowników za pośrednictwem interfejsu administratora systemu środowiska Human Resources. 

Środowiska próbne zapewniają możliwość oceniania funkcji zasobów ludzkich dla osób, które nie mają jeszcze dostępu do środowiska Human Resources. Jeśli udostępniasz środowisko próbne, a uwierzytelniony użytkownik ma już dostęp do co najmniej jednego istniejącego środowiska zasobów ludzkich, użytkownik zostanie przekierowany do istniejącego środowiska lub listy środowisk.

Środowiska wersji zapoznawczych nie są one przeznaczone do używania jako środowiska produkcyjne. Są one ograniczone do 30-dniowego okresu próbnego. Po wygaśnięciu okresu próbnego środowisko i wszystkie znajdujące się w nim dane zostają usunięte i nie można ich odzyskać. Środowisko nie może zostać przekształcone w środowisko piaskownicy lub produkcyjne. Po wygaśnięciu istniejącego środowiska można zarejestrować się na nowe środowisko próbne.

Podczas tworzenia środowiska wersji próbnej Human Resources, jest również tworzone środowisko wersji próbnej Power Apps w dzierżawcy i łączone ze środowiskiem aplikacji Human Resources. Środowisko Power Apps o nazwie „TestDrive” ma ten sam okres próbny co środowisko Human Resources.

> [!NOTE]
> Aprowizacja obsługi środowiska wersji próbnej aplikacji Human Resources nie powiedzie się, jeśli uwierzytelniony użytkownik nie ma uprawnienia do tworzenia środowisk wersji próbnej Power Apps. Użytkownik musi być zawarty w grupie użytkowników, która może tworzyć środowiska próbne w centrum administracyjnym platformy Power Platform. Aby uzyskać więcej informacji, zobacz temat [Kontrolowanie osób, które mogą tworzyć środowiska i zarządzać nimi w centrum administracyjnym platformy Power Platform](/power-platform/admin/control-environment-creation).

## <a name="plan-human-resources-environments"></a>Planuj środowiska zasobów ludzkich

Zanim utworzysz swoje pierwsze środowisko kadrowe, powinieneś dokładnie zaplanować jego potrzeby w swoim projekcie. Podstawowa subskrypcja działu kadr obejmuje dwa środowiska: środowisko produkcyjne i środowisko sandbox. W zależności od złożoności projektu może być konieczne zakupienie dodatkowych środowisk piaskownicy w celu obsługi działań projektowych. 

Uwagi dotyczące dodatkowych środowisk:

- **Migracja danych**: Konieczne może być rozważenie dodatkowego środowiska do działań związanych z migracją danych, aby umożliwić używanie środowiska piaskownicy do celów testowych w całym projekcie. Dodatkowe środowisko umożliwia kontynuowanie działań migracji danych podczas jednoczesnego testowania i konfigurowania działań w innym środowisku.
- **Integracja**: W celu skonfigurowania i testowania integracji należy wziąć pod uwagę dodatkowe środowisko. Może to obejmować natywne integracje, takie jak integracje Ceridian Dayforce lub LinkedIn Talent Hub, lub niestandardowe integracje, takie jak te dotyczące płac, systemów śledzenia kandydatów lub systemów świadczeń i dostawców.
- **Szkolenie**: Możesz potrzebować osobnego środowiska, które jest skonfigurowane z zestawem danych szkoleniowych, aby przeszkolić pracowników w zakresie korzystania z nowego systemu. 
- **Projekt wieloetapowy**: Możesz potrzebować dodatkowego środowiska do obsługi konfiguracji, migracji danych, testowania lub innych działań w fazie projektu, która jest planowana po początkowym uruchomieniu projektu.

 > [!IMPORTANT]
 > W kwestii środowiska zalecenia są następujące:
 > - Używanie środowiska produkcyjnego w całym projekcie jako środowiska konfiguracyjnego GOLD. Jest to ważne, ponieważ nie można skopiować środowiska piaskownicy do środowiska produkcyjnego. Dlatego po uruchomieniu środowisko GOLD jest środowiskiem produkcyjnym i w tym środowisku zakończysz działania związane z przełączaniem.</br></br>
 > - Użycie piaskownicy lub innego środowiska do wykonania próbnego przełączenia przed uruchomieniem. Możesz to zrobić, odświeżając środowisko produkcyjne za pomocą konfiguracji GOLD w środowisku piaskownicy.</br></br>
 > - Przechowywanie szczegółowej listy kontrolnej przełączania, która zawiera każdy z pakietów danych wymaganych do migracji ostatecznych danych do środowiska produkcyjnego podczas przełączania na żywo.</br></br>
 > - Używanie środowiska piaskownicy w całym projekcie jako środowiska TEST. Jeśli potrzebujesz dodatkowych środowisk, Twoja organizacja może je kupić za dodatkową opłatą.</br></br>

## <a name="create-an-lcs-project"></a>Tworzenie projektu LCS

Aby zarządzać swoimi środowiskami oprogramowania Human Resources za pomocą usługi LCS, należy najpierw utworzyć projekt LCS.

1. Zaloguj się w usłudze [LCS](https://lcs.dynamics.com/Logon/Index) za pomocą konta używanego do subskrypcji rozwiązania Human Resources.

   > [!NOTE]
   > Aby zapewnić pomyślne inicjowanie, konto, którego używasz do inicjowania środowiska Human Resources, musi być przypisane do roli **Administrator systemu** lub **Dostosowywanie systemu** w środowisku Power Apps skojarzonym ze środowiskiem Human Resources. Aby uzyskać więcej informacji dotyczących przypisywania ról zabezpieczeń do użytkowników na platformie Power Platform, zobacz temat [Konfigurowanie zabezpieczeń użytkownika do zasobów](/power-platform/admin/database-security).

2. Kliknij znak plus (**+**), aby utworzyć projekt.

3. Wybierz opcję **Microsoft Dynamics 365 Human Resources** jako nazwę produktu oraz wersję produktu.

4. Wybierz metodologię **Dynamics 365 Human Resources**.

5. Wybierz opcję **Utwórz**.

Aby uzyskać informacje dotyczące rozpoczęcia pracy z rozwiązaniem Human Resources, zapoznaj się z metodologią **Human Resources** utworzoną w nowym projekcie. Po utworzeniu projektu wykonaj poniższą procedurę, aby zainicjować środowisko Human Resources.

## <a name="provision-a-human-resources-project"></a>Projekt inicjowania obsługi administracyjnej modułu Human Resources

Po utworzeniu projektu LCS można zainicjować moduł Human Resources w środowisku.

1. W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**.

2. Wskaż, czy jest to to środowisko piaskownicy czy produkcyjne Human Resources. Funkcje w wersji zapoznawczej mogą być dostępne w wystąpieniach piaskownicy, aby umożliwić wczesne przesłanie opinii i testowanie.
   
    > [!NOTE]
    > Po ustawieniu typu wystąpienia aplikacji Human Resources nie można go zmienić. Przed kontynuowaniem sprawdź, czy został wybrany poprawny typ wystąpienia.</br></br>
    > Typ wystąpienia modułu Human Resources jest niezależny od typu wystąpienia środowiska Microsoft Power Apps, które zostało ustawione w centrum administracyjnym Power Apps.
    
3. Zaznacz opcję **Dołącz dane demonstracyjne**, jeżeli chcesz, aby Twoje środowisko zawierało ten sam zestaw danych demonstracyjnych, jak używany w środowisku testowym modułu Human Resources. Dane demonstracyjne są korzystne w środowiskach długoterminowych demonstracji lub szkoleń, natomiast nigdy nie należy używać tej opcji w środowisku produkcyjnym. Należy wybrać tę opcję po wdrożeniu wstępnym. Nie można później zaktualizować istniejącego wdrożenia.

4. Rozwiązanie Human Resources jest zawsze inicjowane w Microsoft Power Apps, aby umożliwić integrację z Power Apps i możliwość rozszerzenia. Przed kontynuowaniem przeczytaj w tym artykule sekcję „Wybieranie środowiska usługi Power Apps”. Jeśli nie masz jeszcze środowiska Power Apps, wybierz opcję Zarządzaj środowiskami w oknie usługi LCS lub przejdź do Centrum administracyjnego usługi Power Apps. Następnie wykonaj procedurę [tworzenia środowiska usługi Power Apps](/powerapps/administrator/create-environment).

5. Wybierz środowisko, w którym ma zostać zainicjowany moduł Human Resources.

6. Wybierz opcję **Tak**, aby zaakceptować warunki i rozpocząć wdrażanie.

   Nowe środowisko pojawi się na liście środowisk w okienku nawigacji po lewej stronie. Jednak nie można rozpocząć korzystania ze środowiska, dopóki stan wdrożenia nie zostanie zaktualizowany do **Wdrożony**. Ten proces zajmuje zwykle tylko kilka minut. Jeśli proces inicjowania obsługi się nie powiedzie, należy się skontaktować z pomocą techniczną.

7. Aby skorzystać z nowego środowiska, wybierz opcję **Zaloguj się do rozwiązania Human Resources**.

    > [!NOTE]
    > Jeszcze przez spełnienie wymagań końcowych można wdrożyć wystąpienie testowe rozwiązania Human Resources w projekcie. Korzystając z tego wystąpienia, można testować swoje rozwiązanie do momentu sfinalizowania zakupu. W przypadku korzystania z nowego środowiska do testowania należy powtórzyć tę procedurę, aby utworzyć środowisko produkcyjne.

## <a name="select-a-power-apps-environment"></a>Wybierz środowisko Power Apps

Korzystanie z danych Human Resources można zintegrować i rozszerzać za pomocą narzędzi Power Apps. Aby uzyskać więcej informacji na temat środowisk Power Apps, w tym o ich zakresie, uzyskiwaniu dostępu oraz zasadach tworzenia i wybierania środowiska, zobacz [Zapowiedź środowisk Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Przy ustalaniu, w którym środowisku usługi Power Apps wdrożyć moduł Human Resources, kieruj się poniższymi wskazówkami: 

1. W usłudze LCS wybierz opcję **Zarządzaj środowiskami**. Można przejść bezpośrednio do Centrum administracyjnego usługi Power Apps, gdzie można przeglądać istniejące środowiska i tworzyć nowe.

2. Jedno środowisko modułu Human Resources jest mapowane na jedno środowisko usługi Power Apps.

3. Środowisko usługi Power Apps zawiera rozwiązanie Human Resources wraz z towarzyszącymi Power Apps, Power Automate i aplikacjami Dataverse. Usunięcie środowiska usługi Power Apps spowoduje wykasowanie znajdujących się w nim aplikacji. Podczas inicjowania obsługi administracyjnej środowiska programu Human Resources można wybrać środowisko **Wersja próbna** lub **Wersja produkcyjna**. Wybierz typ środowiska odpowiednio do tego, jak będzie używane. 

4. Należy wziąć pod uwagę strategie integracja i testowanie danych, na przykład piaskownicę (wirtualne środowisko testowe), testy akceptacji użytkownika czy produkcję. Zalecamy rozważenie skutków dla danego wdrożenia, ponieważ później nie jest łatwo zmienić mapowanie środowiska Human Resources na inne środowisko usługi Power Apps.

5. Następujące środowiska Power Apps nie mogą być stosowane dla Human Resources. Są one filtrowane z listy wyboru w obszarze usługi LCS:
 
    - **Środowiska domyślne Power Apps** — podczas gdy każdy dzierżawca jest automatycznie inicjowany z użyciem domyślnego środowiska Power Apps, nie zaleca się używania ich z Human Resources. Wszyscy użytkownicy dzierżaw mogą uzyskiwać dostęp do środowiska Power Apps i mogą przypadkowo uszkodzić dane dotyczące produkcji podczas testowania i eksplorowania Power Apps lub integracji Power Automate.
   
    - **Środowiska wersji próbnej** — te środowiska są tworzone z datą wygaśnięcia. Po wygaśnięciu tego środowisko i wszystkie wystąpienia Human Resources zawarte w tym środowisku zostaną usunięte automatycznie.
   
    - **Nieobsługiwane regiony geograficzne** — środowisko musi znajdować się w obsługiwanym regionie geograficznym. Aby uzyskać więcej informacji, zobacz [Obsługiwane regiony geograficzne](hr-admin-setup-provision.md#supported-geographies).

6. Możliwości podwójnego zapisu do integracji danych zasobów ludzkich ze środowiskiem Power Apps mogą być używane tylko wtedy, gdy dla środowiska wybrano opcję **Włącz aplikacje Dynamics 365**. Zobacz [Podwójny zapis](../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), aby uzyskać więcej informacji, zobacz temat Strona główna podwójnego zapisu.

    > [!NOTE]
    > Opcja **Włącz aplikacje Dynamics 365** musi być zaznaczona podczas tworzenia środowiska Power Apps. Jeśli opcja nie jest zaznaczona w momencie aprowizacji, nie będzie można używać podwójnego zapisu do integrowania danych między Dynamics 365 Human Resources a środowiskiem Power Apps ani instalować aplikacji Dynamics 365, takich jak Dynamics 365 Sales i Field Service na środowisko. Ta opcja jest nieodwracalna. Aby uzyskać więcej informacji, zobacz [Niektóre ważne uwagi dotyczące tworzenia nowego środowiska](/power-platform/admin/create-environment#some-important-considerations-when-creating-a-new-environment) w witrynie dokumentacji Power Platform.

7. Po określeniu odpowiedniego środowiska, które będzie używane, można kontynuować proces inicjowania obsługi. 

### <a name="supported-geographies"></a>Obsługiwane regiony geograficzne

Human Resources obecnie obsługuje następujące regiony geograficzne:

- Stany Zjednoczone
- Europa
- Wielka Brytania
- Australia
- Kanada
- Azja 

Podczas tworzenia środowiska Human Resources należy wybrać środowisko Power Apps, które ma być skojarzone ze środowiskiem Human Resources. Środowisko Human Resources jest następnie inicjowanie w tym samym regionie geograficznym systemu Azure, co wybrane środowisko Power Apps. Można wybrać miejsce fizycznej lokalizacji środowiska i bazy danych Human Resources, wybierając region geograficzny podczas tworzenia środowiska Power Apps, które będzie skojarzone ze środowiskiem Human Resources.

Możesz wybrać *region geograficzny* systemu Azure, w którym jest inicjowane środowisko, ale nie możesz wybrać określonego *regionu* świadczenia usługi Azure. Automatyzacja określa konkretny region świadczenia usługi w regionie geograficznym, w którym środowisko jest tworzone w celu zoptymalizowania równoważenia obciążenia i wydajności. Informacje na temat regionów geograficznych i regionów świadczenia usługi Azure można znaleźć w dokumentacji [regionów geograficznych systemu Azure](https://azure.microsoft.com/global-infrastructure/geographies).

Dane środowiska Human Resources będą zawsze znajdowały się w regionie geograficznym systemu Azure, w którym są tworzone. Jednak nie zawsze będzie znajdowały się w tym samym regionie świadczenia usługi Azure. Na potrzeby odzyskiwania awaryjnego dane zostaną zreplikowane zarówno w podstawowym regionie świadczenia usługi Azure, jak i w pomocniczym regionie trybu failover w tym samym regionie geograficznym.

 > [!NOTE]
 > Migrowanie środowiska Human Resources z jednego regionu świadczenia usługi Azure do innego nie jest obsługiwane.

## <a name="grant-access-to-the-environment"></a>Przyznawanie dostępu do środowiska

Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Musisz przyznać dostęp dodatkowym użytkownikom aplikacji. Trzeba dodać użytkowników i przypisać im odpowiednie role w środowisku Human Resources. Aby uzyskać więcej informacji, zobacz [tworzenie nowych użytkowników](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) i [przypisywanie użytkowników do ról zabezpieczeń](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
