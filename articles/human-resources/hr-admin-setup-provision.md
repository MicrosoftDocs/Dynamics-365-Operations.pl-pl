---
title: Aprowizowanie rozwiązania Human Resources
description: Ten artykuł przeprowadzi użytkownika przez proces inicjacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/23/2020
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
ms.openlocfilehash: 106976edfa2bd7efba41887d5e8f4243b56e7b2f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527806"
---
# <a name="provision-human-resources"></a>Aprowizowanie rozwiązania Human Resources

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten artykuł przeprowadzi użytkownika przez proces inicjacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources. Temat ten opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Human Resources u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). Jeśli masz już licencję na oprogramowanie Microsoft Dynamics 365 uwzględniającą plan rozwiązania Human Resources, a nie jesteś w stanie wykonać kroków opisanych w tym artykule, skontaktuj się z pomocą techniczną.

Aby rozpocząć, administrator globalny powinien się zarejestrować w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) i utworzyć nowy projekt programu Human Resources. O ile problemy z licencją nie umożliwią zainicjowania modułu Human Resources, wsparcie działu pomocy technicznej ani przedstawicieli Dynamics Service Engineering (DSE) nie jest wymagane.

## <a name="create-an-lcs-project"></a>Tworzenie projektu LCS

Aby zarządzać swoimi środowiskami oprogramowania Human Resources za pomocą usługi LCS, należy najpierw utworzyć projekt LCS.

1. Zaloguj się w usłudze [LCS](https://lcs.dynamics.com/Logon/Index) za pomocą konta używanego do subskrypcji rozwiązania Human Resources.

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

4. Rozwiązanie Human Resources jest zawsze inicjowane w Microsoft Power Apps, aby umożliwić integrację z Power Apps i możliwość rozszerzenia. Przed kontynuowaniem przeczytaj w tym artykule sekcję „Wybieranie środowiska usługi Power Apps”. Jeśli nie masz jeszcze środowiska Power Apps, wybierz opcję Zarządzaj środowiskami w oknie usługi LCS lub przejdź do Centrum administracyjnego usługi Power Apps. Następnie wykonaj procedurę [tworzenia środowiska usługi Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Wybierz środowisko, w którym ma zostać zainicjowany moduł Human Resources.

6. Wybierz opcję **Tak**, aby zaakceptować warunki i rozpocząć wdrażanie.

   Nowe środowisko pojawi się na liście środowisk w okienku nawigacji po lewej stronie. Jednak nie można rozpocząć korzystania ze środowiska, dopóki stan wdrożenia nie zostanie zaktualizowany do **Wdrożony**. Ten proces zajmuje zwykle tylko kilka minut. Jeśli proces inicjowania obsługi się nie powiedzie, należy się skontaktować z pomocą techniczną.

7. Aby skorzystać z nowego środowiska, wybierz opcję **Zaloguj się do rozwiązania Human Resources**.

    > [!NOTE]
    > Jeszcze przez spełnienie wymagań końcowych można wdrożyć wystąpienie testowe rozwiązania Human Resources w projekcie. Korzystając z tego wystąpienia, można testować swoje rozwiązanie do momentu sfinalizowania zakupu. W przypadku korzystania z nowego środowiska do testowania należy powtórzyć tę procedurę, aby utworzyć środowisko produkcyjne.

    > Można rozważyć wykorzystanie bezpłatnych 60 dni [Human Resources w środowisku próbnym](https://go.microsoft.com/fwlink/p/?LinkId=2115962). Chociaż właścicielem środowiska próbnego jest użytkownik, który je utworzył, można do niego zaprosić innych użytkowników za pośrednictwem interfejsu administratora systemu środowiska Human Resources. Środowiska próbne zawierają fikcyjne dane, których można używać do eksplorowania programu w bezpieczny sposób. Nie są one przeznaczone do używania jako środowiska produkcyjne. Należy zauważyć, że po wygaśnięciu wersji próbnej środowiska po upływie 60 dni wszystkie zawarte w niej dane są usuwane nie można ich odzyskać. Po wygaśnięciu istniejącego środowiska można zarejestrować się na nowe środowisko próbne.

## <a name="select-a-power-apps-environment"></a>Wybierz środowisko Power Apps

Korzystanie z danych Human Resources można zintegrować i rozszerzać za pomocą narzędzi Power Apps. Aby uzyskać więcej informacji na temat środowisk Power Apps, w tym o ich zakresie, uzyskiwaniu dostępu oraz zasadach tworzenia i wybierania środowiska, zobacz [Zapowiedź środowisk Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Przy ustalaniu, w którym środowisku usługi Power Apps wdrożyć moduł Human Resources, kieruj się poniższymi wskazówkami: 

1. W usłudze LCS wybierz opcję **Zarządzaj środowiskami**. Można przejść bezpośrednio do Centrum administracyjnego usługi Power Apps, gdzie można przeglądać istniejące środowiska i tworzyć nowe.

2. Jedno środowisko modułu Human Resources jest mapowane na jedno środowisko usługi Power Apps.

3. Środowisko usługi Power Apps zawiera rozwiązanie Human Resources wraz z towarzyszącymi Power Apps, Power Automate i aplikacjami Common Data Service. Usunięcie środowiska usługi Power Apps spowoduje wykasowanie znajdujących się w nim aplikacji. Podczas inicjowania obsługi administracyjnej środowiska programu Human Resources można wybrać środowisko **Wersja próbna** lub **Wersja produkcyjna**. Wybierz typ środowiska odpowiednio do tego, jak będzie używane. 

4. Należy wziąć pod uwagę strategie integracja i testowanie danych, na przykład piaskownicę (wirtualne środowisko testowe), testy akceptacji użytkownika czy produkcję. Zalecamy rozważenie skutków dla danego wdrożenia, ponieważ później nie jest łatwo zmienić mapowanie środowiska Human Resources na inne środowisko usługi Power Apps.

5. Nie można stosować następujących środowisk Power Apps dla Human Resources. Są one filtrowane z listy wyboru w obszarze usługi LCS:
 
    - **Środowiska domyślne Power Apps** — podczas gdy każdy dzierżawca jest automatycznie inicjowany z użyciem domyślnego środowiska Power Apps, nie zaleca się używania ich z Human Resources. Wszyscy użytkownicy dzierżaw mogą uzyskiwać dostęp do środowiska Power Apps i mogą przypadkowo uszkodzić dane dotyczące produkcji podczas testowania i eksplorowania Power Apps lub integracji Power Automate.
   
    - **Środowiska wersji próbnej** — te środowiska są tworzone z datą wygaśnięcia. Po wygaśnięciu tego środowisko i wszystkie wystąpienia Human Resources zawarte w tym środowisku zostaną usunięte automatycznie.
   
    - **Nieobsługiwane regiony** — obecnie moduł Human Resources jest obsługiwany tylko w następujących regionach: Stany Zjednoczone, Europa, Wielka Brytania, Australia, Kanada i Azja.

    > [!NOTE]
    > Środowisko zasobów ludzkich jest udostępniane w tym samym regionie, w którym zainicjowano obsługę środowiska Power Apps. Migrowanie środowiska Human Resources do innego regionu nie jest obsługiwane.

6. Po określeniu odpowiedniego środowiska, które będzie używane, można kontynuować proces inicjowania obsługi. 
 
## <a name="grant-access-to-the-environment"></a>Przyznawanie dostępu do środowiska

Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Musisz przyznać dostęp dodatkowym użytkownikom aplikacji. Trzeba dodać użytkowników i przypisać im odpowiednie role w środowisku Human Resources. Globalny administrator, który wdrożył program Human Resources, musi również uruchomić Attract i Onboard, aby dokończyć inicjalizację i umożliwić dostęp innym użytkownikom dzierżawy. Dopóki tak się nie stanie, inni użytkownicy nie będą mieli dostępu do Attract i Onboard i będą im wyświetlane błędy naruszenia dostępu. Aby uzyskać więcej informacji, zobacz [tworzenie nowych użytkowników](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) i [przypisywanie użytkowników do ról zabezpieczeń](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
