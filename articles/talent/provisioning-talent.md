---
title: Inicjowanie obsługi rozwiązania Talent
description: Ten temat przeprowadzi użytkownika przez proces inicjacji nowego środowiska dla oprogramowania Microsoft Dynamics 365 for Talent.
author: andreabichsel
manager: AnnBe
ms.date: 00/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: 98f60e466b8b97215fdba0f48ca53ca57157283b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518843"
---
# <a name="provision-talent"></a>Inicjowanie obsługi rozwiązania Talent

[!include [banner](includes/banner.md)]

Ten temat przeprowadzi użytkownika przez proces inicjacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 for Talent. Temat te opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Talent u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). Jeśli masz już licencję na oprogramowanie Microsoft Dynamics 365 uwzględniającą plan aplikacji Talent, a nie jesteś w stanie wykonać kroków opisanych w tym temacie, skontaktuj się z pomocą techniczną.

Aby rozpocząć, administrator globalny powinien się zarejestrować w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) i utworzyć nowy projekt Talent. O ile problemy z licencją nie umożliwią zainicjowania aplikacji Talent, wsparcie działu pomocy technicznej ani przedstawicieli Dynamics Service Engineering (DSE) nie jest wymagane.

## <a name="create-an-lcs-project"></a>Tworzenie projektu LCS
Aby zarządzać swoimi środowiskami Talent za pomocą usługi LCS, należy najpierw utworzyć projekt LCS.

1. Zaloguj się w usłudze [LCS](https://lcs.dynamics.com/Logon/Index) za pomocą konta używanego do subskrypcji rozwiązania Talent.
2. Kliknij znak plus (**+**), aby utworzyć projekt.
3. Wybierz opcję **Microsoft Dynamics 365 for Talent** jako nazwę produktu oraz wersję produktu.
4. Wybierz metodologię **Dynamics 365 for Talent**.
5. Wybierz opcję **Utwórz**.

Aby uzyskać informacje dotyczące rozpoczęcia pracy z aplikacją talent, zapoznaj się z metodologią **Talent** utworzoną w nowym projekcie. Po utworzeniu projektu, wykonaj poniższą procedurę, aby zainicjować środowisko Talent.

## <a name="provision-a-talent-project"></a>Inicjowanie projektu w środowisku Talent
Po utworzeniu projektu LCS można zainicjować aplikację Talent w środowisku.

1. W projekcie LCS wybierz kafel **Zarządzanie aplikacją Talent**.
2. Aplikacja Talent jest zawsze inicjowana w środowisku Microsoft PowerApps, aby umożliwić integrację z PoweApps i możliwość rozszerzenia. Przed kontynuowaniem przeczytaj w tym temacie sekcję „Wybieranie środowiska usługi PowerApps”. Jeśli nie masz jeszcze środowiska PowerApps, wybierz opcję Zarządzaj środowiskami w oknie usługi LCS lub przejdź do Centrum administracyjnego usługi PowerApps. Następnie wykonaj procedurę [tworzenia środowiska usługi PowerApps](https://docs.microsoft.com/en-us/powerapps/administrator/create-environment).

    > [!NOTE]
    > Aby wyświetlić istniejące środowiska lub utworzyć nowe, należy przypisać delegowanego administratora odpowiedzialnego za inicjację aplikacji Talent do licencji P2 środowiska PowerApps. Jeśli organizacja nie posiada licencji P2 środowiska PowerApps, można ją uzyskać u CSP lub ze [strony cennika środowiska PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Wybierz opcję **Dodaj**, a następnie wybierz środowisko, w którym zostanie zainicjowana aplikacja Talent.
5. Zaznacz opcję **Dołącz dane demonstracyjne**, jeżeli chcesz, aby Twoje środowisko zawierało ten sam zestaw danych demonstracyjnych, jak używany w środowisku testowym aplikacji Talent. Jest to korzystne w środowiskach długoterminowych demonstracji lub szkoleń, natomiast nigdy nie należy używać tej opcji w środowisku produkcyjnym.  Należy wybrać tę opcję po wdrożeniu wstępnym. Nie można później zaktualizować istniejącego wdrożenia.
6. Wybierz opcję **Tak**, aby zaakceptować warunki i rozpocząć wdrażanie.

    Nowe środowisko pojawi się na liście środowisk w okienku nawigacji po lewej stronie. Jednak nie można rozpocząć korzystania ze środowiska, dopóki stan wdrożenia nie zostanie zaktualizowany do **Wdrożony**. Ten proces zajmuje zwykle tylko kilka minut. Jeśli proces inicjowania obsługi się nie powiedzie, należy się skontaktować z pomocą techniczną.

7. Aby skorzystać z nowego środowiska, wybierz opcję **Zaloguj się do rozwiązania Talent**.

    > [!NOTE]
    > Jeszcze przez spełnienie wymagań końcowych można wdrożyć wystąpienie testowe rozwiązania Talent w projekcie. Korzystając z tego wystąpienia, można testować swoje rozwiązanie do momentu sfinalizowania zakupu. W przypadku korzystania z nowego środowiska do testowania należy powtórzyć tę procedurę, aby utworzyć środowisko produkcyjne.

    > Ponieważ w ramach subskrypcji usługi Talent są dozwolone tylko dwa środowiska LCS, można również rozważyć wykorzystanie bezpłatnego 60-dniowego [środowiska próbnego aplikacji Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Chociaż właścicielem środowiska próbnego jest użytkownik, który je utworzył, można do niego zaprosić innych użytkowników za pośrednictwem interfejsu administratora systemu środowiska Core HR. Środowiska próbne zawierają fikcyjne dane, których można używać do eksplorowania programu w bezpieczny sposób. Nie są one przeznaczone do używania jako środowiska produkcyjne. Należy zauważyć, że po wygaśnięciu wersji próbnej środowiska po upływie 60 dni wszystkie zawarte w niej dane są usuwane nie można ich odzyskać. Po wygaśnięciu istniejącego środowiska można zarejestrować się na nowe środowisko próbne.

## <a name="select-a-powerapps-environment"></a>Wybieranie środowiska usługi PowerApps

Integracja środowisk Talent i PowerApps pozwala integrować i poszerzać stosowanie danych aplikacji Talent za pomocą narzędzi usługi PowerApps. Wiedza o przeznaczeniu środowisk usługi PowerApps nie tylko pomoże Ci tworzyć aplikacje rozszerzające funkcjonalność modułu Talent, ale może również pomóc wybrać odpowiednie środowisko podczas inicjowania obsługi modułu Talent. Aby uzyskać więcej informacji na temat środowisk PowerApps, w tym o ich zakresie, uzyskiwaniu dostępu oraz zasadach tworzenia i wybierania środowiska, zobacz [Zapowiedź środowisk PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Przy ustalaniu, w którym środowisku usługi PowerApps wdrożyć moduł Talent, kieruj się poniższymi wskazówkami: 

1. W usłudze LCS wybierz opcję **Zarządzaj środowiskami** lub przejdź bezpośrednio do centrum administracyjnego usługi PowerApps, gdzie możesz obejrzeć istniejące i tworzyć nowe środowiska.
2. Jedno środowisko aplikacji Talent jest mapowane na jedno środowisko usługi PowerApps.
3. Środowisko usługi PowerApps „zawiera” aplikację Talent wraz z towarzyszącymi aplikacjami środowisk PowerApps, Flow i Common Data Service. Usunięcie środowiska usługi PowerApps spowoduje wykasowanie znajdujących się w nim aplikacji. Podczas inicjowania obsługi administracyjnej środowiska aplikacji Talent można wybrać opcję „Wersja próbna” lub „Wersja produkcyjna”. Wybierz typ środowiska odpowiednio do tego, jak będzie używane. 
4. Należy wziąć pod uwagę strategie integracja i testowanie danych, na przykład piaskownicę (wirtualne środowisko testowe), testy akceptacji użytkownika czy produkcję. Zalecamy rozważenie różnych skutków dla danego wdrożenia, ponieważ później nie jest łatwo zmienić mapowanie środowiska aplikacji Talent na inne środowisko usługi PowerApps.
5. Następujące środowiska usługi PowerApps nie mogą być używane dla aplikacji Talent i będą odfiltrowane z listy wyboru w usłudze LCS:
 
    - **Domyślnie środowiska usługi PowerApps** Mimo że każda dzierżawa ma automatycznie włączoną obsługę w domyślnym środowisku usługi PowerApps, nie zalecamy używania tego środowiska w połączeniu z aplikacją Talent, ponieważ wszyscy użytkownicy dzierżawy mają dostęp do środowiska usługi PowerApps i mogą przypadkowo uszkodzić dane produkcyjne podczas testowania i eksplorowania integracji z usługami PowerApps lub Flow.
   
    - **Środowiska próbne** — te środowiska są tworzone z datą ważności. Po tym czasie przestają działać, co powoduje automatycznie usunięcie środowiska i powiązanych z nim wystąpień rozwiązania Talenty.
   
    - **Nieobsługiwana regiony** — obecnie aplikacja Talent jest obsługiwana tylko w następujących regionach: Stany Zjednoczone, Europa, Wielka Brytania i Australia.
  
6. Po określeniu odpowiedniego środowiska, które będzie używane, można kontynuować proces inicjowania obsługi. 
 
## <a name="grant-access-to-the-environment"></a>Przyznawanie dostępu do środowiska
Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Dodatkowym użytkownikom aplikacji trzeba jednoznacznie przyznać dostęp. W celu udzielenia dostępu trzeba dodać użytkowników i przypisać im odpowiednie role w środowisku Core HR. Globalny administrator, który wdrożył aplikację Talent, musi również uruchomić aplikacje Attract i Onboard, aby dokończyć inicjalizację i umożliwić dostęp innym użytkownikom dzierżawy.  Dopóki tak się nie stanie, inni użytkownicy nie będą mieli dostępu do aplikacji Attract i Onboard i będą im wyświetlane błędy naruszenia dostępu. Aby uzyskać więcej informacji, zobacz [tworzenie nowych użytkowników](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) i [przypisywanie użytkowników do ról zabezpieczeń](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
