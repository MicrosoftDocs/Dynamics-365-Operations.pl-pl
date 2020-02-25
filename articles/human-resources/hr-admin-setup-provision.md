---
title: Human Resources - wdrożenie
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f3a7987a9b385fb6ba0294dc46b0d66be8228f06
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026274"
---
# <a name="provision-human-resources"></a>Human Resources - wdrożenie

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

2. Wskaż, czy jest to wystąpienie produkcyjne czy piaskownicy rozwiązania Human Resources. Funkcje w wersji zapoznawczej mogą być dostępne w wystąpieniach piaskownicy, aby umożliwić wczesne przesłanie opinii i testowanie.
   
    > [!NOTE]
    > Po ustawieniu typu wystąpienia aplikacji Talent nie można go zmienić. Przed kontynuowaniem sprawdź, czy został wybrany poprawny typ wystąpienia.</br></br>
    > Typ wystąpienia modułu Human Resources jest niezależny od typu wystąpienia środowiska Microsoft Power Apps, które zostało ustawione w centrum administracyjnym Power Apps.
    
3. Zaznacz opcję **Dołącz dane demonstracyjne**, jeżeli chcesz, aby Twoje środowisko zawierało ten sam zestaw danych demonstracyjnych, jak używany w środowisku testowym modułu Human Resources. Jest to korzystne w środowiskach długoterminowych demonstracji lub szkoleń, natomiast nigdy nie należy używać tej opcji w środowisku produkcyjnym.  Należy wybrać tę opcję po wdrożeniu wstępnym. Nie można później zaktualizować istniejącego wdrożenia.

4. Rozwiązanie Human Resources jest zawsze inicjowane w Microsoft Power Apps, aby umożliwić integrację z Power Apps i możliwość rozszerzenia. Przed kontynuowaniem przeczytaj w tym artykule sekcję „Wybieranie środowiska usługi Power Apps”. Jeśli nie masz jeszcze środowiska Power Apps, wybierz opcję Zarządzaj środowiskami w oknie usługi LCS lub przejdź do Centrum administracyjnego usługi Power Apps. Następnie wykonaj procedurę [tworzenia środowiska usługi Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

    > [!NOTE]
    > Aby wyświetlić istniejące środowiska lub utworzyć nowe, należy przypisać delegowanego administratora odpowiedzialnego za inicjację programu Human Resources do licencji P2 środowiska Power Apps. Jeśli organizacja nie posiada licencji P2 środowiska Power Apps, można ją uzyskać u CSP lub ze strony [cennika Power Apps](https://powerapps.microsoft.com/pricing/).

5. Wybierz środowisko, w którym ma zostać zainicjowany moduł Human Resources.

6. Wybierz opcję **Tak**, aby zaakceptować warunki i rozpocząć wdrażanie.

   Nowe środowisko pojawi się na liście środowisk w okienku nawigacji po lewej stronie. Jednak nie można rozpocząć korzystania ze środowiska, dopóki stan wdrożenia nie zostanie zaktualizowany do **Wdrożony**. Ten proces zajmuje zwykle tylko kilka minut. Jeśli proces inicjowania obsługi się nie powiedzie, należy się skontaktować z pomocą techniczną.

7. Aby skorzystać z nowego środowiska, wybierz opcję **Zaloguj się do rozwiązania Human Resources**.

    > [!NOTE]
    > Jeszcze przez spełnienie wymagań końcowych można wdrożyć wystąpienie testowe rozwiązania Human Resources w projekcie. Korzystając z tego wystąpienia, można testować swoje rozwiązanie do momentu sfinalizowania zakupu. W przypadku korzystania z nowego środowiska do testowania należy powtórzyć tę procedurę, aby utworzyć środowisko produkcyjne.

    > Ponieważ w ramach subskrypcji usługi Human Resources są dozwolone tylko dwa środowiska LCS, można również rozważyć wykorzystanie bezpłatnego 60-dniowego [środowiska próbnego rozwiązania Human Resources](https://dynamics.microsoft.com/talent/overview/). Chociaż właścicielem środowiska próbnego jest użytkownik, który je utworzył, można do niego zaprosić innych użytkowników za pośrednictwem interfejsu administratora systemu środowiska Human Resources. Środowiska próbne zawierają fikcyjne dane, których można używać do eksplorowania programu w bezpieczny sposób. Nie są one przeznaczone do używania jako środowiska produkcyjne. Należy zauważyć, że po wygaśnięciu wersji próbnej środowiska po upływie 60 dni wszystkie zawarte w niej dane są usuwane nie można ich odzyskać. Po wygaśnięciu istniejącego środowiska można zarejestrować się na nowe środowisko próbne.

## <a name="select-a-power-apps-environment"></a>Wybierz środowisko Power Apps

Integracja środowisk Human Resources i Power Apps pozwala integrować i poszerzać stosowanie danych programu Human Resources za pomocą narzędzi usługi Power Apps. Wiedza o przeznaczeniu środowisk usługi Power Apps nie tylko pomoże Ci tworzyć aplikacje rozszerzające funkcjonalność modułu Human Resources, ale może również pomóc wybrać odpowiednie środowisko podczas inicjowania obsługi modułu Human Resources. Aby uzyskać więcej informacji na temat środowisk Power Apps, w tym o ich zakresie, uzyskiwaniu dostępu oraz zasadach tworzenia i wybierania środowiska, zobacz [Zapowiedź środowisk Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Przy ustalaniu, w którym środowisku usługi Power Apps wdrożyć moduł Human Resources, kieruj się poniższymi wskazówkami: 

1. W usłudze LCS wybierz opcję **Zarządzaj środowiskami** lub przejdź bezpośrednio do centrum administracyjnego usługi Power Apps, gdzie możesz obejrzeć istniejące i tworzyć nowe środowiska.

2. Jedno środowisko modułu Human Resources jest mapowane na jedno środowisko usługi Power Apps.

3. Środowisko usługi Power Apps zawiera rozwiązanie Human Resources wraz z towarzyszącymi Power Apps, Power Automate i aplikacjami Common Data Service. Usunięcie środowiska usługi Power Apps spowoduje wykasowanie znajdujących się w nim aplikacji. Podczas inicjowania obsługi administracyjnej środowiska programu Human Resources można wybrać środowisko **Wersja próbna** lub **Wersja produkcyjna**. Wybierz typ środowiska odpowiednio do tego, jak będzie używane. 

4. Należy wziąć pod uwagę strategie integracja i testowanie danych, na przykład piaskownicę (wirtualne środowisko testowe), testy akceptacji użytkownika czy produkcję. Zalecamy rozważenie różnych skutków dla danego wdrożenia, ponieważ później nie jest łatwo zmienić mapowanie środowiska programu Human Resources na inne środowisko usługi Power Apps.

5. Następujące środowiska usługi Power Apps nie mogą być używane dla modułu Human Resources i będą odfiltrowane z listy wyboru w usłudze LCS:
 
    - **Domyślnie środowiska usługi Power Apps** - Mimo że każda dzierżawa ma automatycznie włączoną obsługę w domyślnym środowisku usługi Power Apps, nie zalecamy używania tego środowiska w połączeniu z rozwiązaniem Human Resources, ponieważ wszyscy użytkownicy dzierżawy mają dostęp do środowiska usługi Power Apps i mogą przypadkowo uszkodzić dane produkcyjne podczas testowania i eksplorowania integracji z usługami Power Apps lub Power Automate.
   
    - **Środowiska próbne** — te środowiska są tworzone z datą ważności; po tym czasie przestają działać, co powoduje automatycznie usunięcie środowiska i powiązanych z nim wystąpień rozwiązania Human Resources.
   
    - **Nieobsługiwane regiony** — obecnie moduł Human Resources jest obsługiwany tylko w następujących regionach: Stany Zjednoczone, Europa, Wielka Brytania, Australia Kanada i Azja.
  
6. Po określeniu odpowiedniego środowiska, które będzie używane, można kontynuować proces inicjowania obsługi. 
 
## <a name="grant-access-to-the-environment"></a>Przyznawanie dostępu do środowiska

Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Dodatkowym użytkownikom aplikacji trzeba jednoznacznie przyznać dostęp. W celu udzielenia dostępu trzeba dodać użytkowników i przypisać im odpowiednie role w środowisku Human Resources. Globalny administrator, który wdrożył program Human Resources, musi również uruchomić Attract i Onboard, aby dokończyć inicjalizację i umożliwić dostęp innym użytkownikom dzierżawy.  Dopóki tak się nie stanie, inni użytkownicy nie będą mieli dostępu do Attract i Onboard i będą im wyświetlane błędy naruszenia dostępu. Aby uzyskać więcej informacji, zobacz [tworzenie nowych użytkowników](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) i [przypisywanie użytkowników do ról zabezpieczeń](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
