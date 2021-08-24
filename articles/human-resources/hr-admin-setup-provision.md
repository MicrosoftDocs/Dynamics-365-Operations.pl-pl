---
title: Inicjowanie obsługi administracyjnej rozwiązania Human Resources
description: Ten temat przeprowadzi użytkownika przez proces inicjacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 58ffce072c8b73f4907b18c6c60b022f9a3b55f26cb785238367254021afdc28
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756155"
---
# <a name="provision-human-resources"></a>Inicjowanie obsługi administracyjnej rozwiązania Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat przeprowadzi użytkownika przez proces inicjacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources. Temat ten opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Human Resources u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). Jeśli masz już licencję na oprogramowanie Microsoft Dynamics 365 uwzględniającą plan rozwiązania Human Resources, a nie jesteś w stanie wykonać kroków opisanych w tym artykule, skontaktuj się z pomocą techniczną.

Aby rozpocząć, administrator globalny powinien się zarejestrować w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) i utworzyć nowy projekt programu Human Resources. O ile problemy z licencją nie umożliwią zainicjowania modułu Human Resources, wsparcie działu pomocy technicznej ani przedstawicieli Dynamics Service Engineering (DSE) nie jest wymagane.

## <a name="provision-a-human-resources-trial-environment"></a>Inicjowanie obsługi środowiska próbnego Human Resources

Przed rozpoczęciem inicjowania obsługi pierwszej piaskownicy lub środowiska produkcyjnego można zaimprowizować [środowisko próbne Human Resources](https://go.microsoft.com/fwlink/p/?LinkId=2115962) w celu weryfikacji funkcji Human Resources. Środowiska próbne zawierają fikcyjne dane, których można używać do eksplorowania programu w bezpieczny sposób. Chociaż właścicielem środowiska próbnego jest użytkownik, który je utworzył, można do niego zaprosić innych użytkowników za pośrednictwem interfejsu administratora systemu środowiska Human Resources. 

Środowiska wersji zapoznawczych nie są one przeznaczone do używania jako środowiska produkcyjne. Są one ograniczone do 60-dniowego okresu próbnego. Po wygaśnięciu okresu próbnego środowisko i wszystkie znajdujące się w nim dane zostają usunięte i nie można ich odzyskać. Środowisko nie może zostać przekształcone w środowisko piaskownicy lub produkcyjne. Po wygaśnięciu istniejącego środowiska można zarejestrować się na nowe środowisko próbne.

## <a name="plan-human-resources-environments"></a>Planuj środowiska zasobów ludzkich

Zanim utworzysz swoje pierwsze środowisko kadrowe, powinieneś dokładnie zaplanować jego potrzeby w swoim projekcie. Podstawowa subskrypcja działu kadr obejmuje dwa środowiska: środowisko produkcyjne i środowisko sandbox. W zależności od złożoności projektu może być konieczne zakupienie dodatkowych środowisk piaskownicy w celu obsługi działań projektowych. 

Rozważania dotyczące dodatkowych środowisk obejmują między innymi następujące kwestie:

- **Migracja danych**: Konieczne może być rozważenie dodatkowego środowiska do działań związanych z migracją danych, aby umożliwić używanie środowiska piaskownicy do celów testowych w całym projekcie. Dodatkowe środowisko umożliwia kontynuowanie działań migracji danych podczas jednoczesnego testowania i konfigurowania działań w innym środowisku.
- **Integracja**: W celu skonfigurowania i testowania integracji należy wziąć pod uwagę dodatkowe środowisko. Może to obejmować natywne integracje, takie jak integracje Ceridian Dayforce LinkedIn Talent Hub, lub niestandardowe integracje, takie jak te dotyczące płac, systemów śledzenia kandydatów lub systemów świadczeń i dostawców.
- **Szkolenie**: Możesz potrzebować osobnego środowiska, które jest skonfigurowane z zestawem danych szkoleniowych, aby przeszkolić pracowników w zakresie korzystania z nowego systemu. 
- **Projekt wieloetapowy**: Możesz potrzebować dodatkowego środowiska do obsługi konfiguracji, migracji danych, testowania lub innych działań w fazie projektu, która jest planowana po początkowym uruchomieniu projektu.

 > [!IMPORTANT]
 > Zalecamy używanie środowiska produkcyjnego w całym projekcie jako środowiska konfiguracyjnego GOLD. Jest to ważne, ponieważ nie można skopiować środowiska piaskownicy do środowiska produkcyjnego. Dlatego po uruchomieniu środowisko GOLD jest środowiskiem produkcyjnym i w tym środowisku zakończysz działania związane z przełączaniem.</br></br>
 > Zalecamy użycie piaskownicy lub innego środowiska do wykonania próbnego przełączenia przed uruchomieniem. Możesz to zrobić, odświeżając środowisko produkcyjne za pomocą konfiguracji GOLD w środowisku piaskownicy.</br></br>
 > Zalecamy przechowywanie szczegółowej listy kontrolnej przełączania, która zawiera każdy z pakietów danych wymaganych do migracji ostatecznych danych do środowiska produkcyjnego podczas przełączania na żywo.</br></br>
 > Zalecamy również, aby w całym projekcie używać środowiska piaskownicy jako środowiska TESTOWEGO. Jeśli potrzebujesz dodatkowych środowisk, Twoja organizacja może je kupić za dodatkową opłatą.</br></br>

## <a name="create-an-lcs-project"></a>Tworzenie projektu LCS

Aby zarządzać swoimi środowiskami oprogramowania Human Resources za pomocą usługi LCS, należy najpierw utworzyć projekt LCS.

1. Zaloguj się w usłudze [LCS](https://lcs.dynamics.com/Logon/Index) za pomocą konta używanego do subskrypcji rozwiązania Human Resources.

   > [!NOTE]
   > Aby zapewnić pomyślne inicjowanie, konto, którego używasz do inicjowania środowiska Human Resources, musi być przypisane do roli **Administrator systemu** lub **Dostosowywanie systemu** w środowisku Power Apps skojarzonym ze środowiskiem Human Resources. Aby uzyskać więcej informacji dotyczących przypisywania ról zabezpieczeń do użytkowników w Power Platform, zobacz temat [Konfigurowanie zabezpieczeń użytkownika do zasobów](/power-platform/admin/database-security).

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

5. Nie można stosować następujących środowisk Power Apps dla Human Resources. Są one filtrowane z listy wyboru w obszarze usługi LCS:
 
    - **Środowiska domyślne Power Apps** — podczas gdy każdy dzierżawca jest automatycznie inicjowany z użyciem domyślnego środowiska Power Apps, nie zaleca się używania ich z Human Resources. Wszyscy użytkownicy dzierżaw mogą uzyskiwać dostęp do środowiska Power Apps i mogą przypadkowo uszkodzić dane dotyczące produkcji podczas testowania i eksplorowania Power Apps lub integracji Power Automate.
   
    - **Środowiska wersji próbnej** — te środowiska są tworzone z datą wygaśnięcia. Po wygaśnięciu tego środowisko i wszystkie wystąpienia Human Resources zawarte w tym środowisku zostaną usunięte automatycznie.
   
    - **Nieobsługiwane regiony geograficzne** — środowisko musi znajdować się w obsługiwanym regionie geograficznym. Aby uzyskać więcej informacji, zobacz [Obsługiwane regiony geograficzne](hr-admin-setup-provision.md#supported-geographies).

6. Po określeniu odpowiedniego środowiska, które będzie używane, można kontynuować proces inicjowania obsługi. 

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

Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Musisz przyznać dostęp dodatkowym użytkownikom aplikacji. Trzeba dodać użytkowników i przypisać im odpowiednie role w środowisku Human Resources. Globalny administrator, który wdrożył program Human Resources, musi również uruchomić Attract i Onboard, aby dokończyć inicjalizację i umożliwić dostęp innym użytkownikom dzierżawy. Dopóki tak się nie stanie, inni użytkownicy nie będą mieli dostępu do Attract i Onboard i będą im wyświetlane błędy naruszenia dostępu. Aby uzyskać więcej informacji, zobacz [tworzenie nowych użytkowników](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) i [przypisywanie użytkowników do ról zabezpieczeń](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
