---
title: Inicjowanie oprogramowania Microsoft Dynamics 365 for Talent
description: "Ten temat przeprowadzi użytkownika przez proces inicjacji nowego środowiska dla oprogramowania Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: b4b54e97bdebc158adc3bc6d57a6661cd536f5fb
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Inicjowanie oprogramowania Microsoft Dynamics 365 for Talent

[!INCLUDE [banner](includes/banner.md)]

Ten temat przeprowadzi użytkownika przez proces inicjacji nowego środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 for Talent. Temat te opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Talent u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). Jeśli masz już licencję na oprogramowanie Microsoft Dynamics 365 uwzględniającą plan aplikacji Talent, a nie jesteś w stanie wykonać kroków opisanych w tym temacie, skontaktuj się z pomocą techniczną.

Aby rozpocząć, administrator globalny powinien się zarejestrować w usłudze [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) i utworzyć nowy projekt Talent. O ile problemy z licencją nie umożliwią zainicjowania aplikacji Talent, wsparcie działu pomocy technicznej ani przedstawicieli Dynamics Service Engineering (DSE) nie jest wymagane.

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
2. Aplikacja talent jest zawsze inicjowana w środowisku Microsoft PowerApps, aby umożliwić integrację z PoweApps i możliwość rozszerzenia. Przed kontynuowaniem przeczytaj w tym temacie sekcję „Wybieranie środowiska usługi PowerApps”. 
3. Jeśli nie masz jeszcze środowiska PowerApps, wykonaj najpierw kroki zawarte w sekcji „Tworzenie nowego środowiska PowerApps (jeśli wymagane)” znajdującej się w tym temacie.

    > [!NOTE]
    > Aby wyświetlić istniejące środowiska lub utworzyć nowe, należy przypisać delegowanego administratora odpowiedzialnego za inicjację aplikacji Talent do licencji P2 środowiska PowerApps. Jeśli organizacja nie posiada licencji P2 środowiska PowerApps, można ją uzyskać u CSP lub ze [strony cennika środowiska PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Wybierz opcję **Dodaj**, a następnie wybierz środowisko, w którym zostanie zainicjowana aplikacja Talent.
5. Wybierz opcję **Tak**, aby zaakceptować warunki i rozpocząć wdrażanie.

    Nowe środowisko pojawi się na liście środowisk w okienku nawigacji po lewej stronie. Jednak nie można rozpocząć korzystania ze środowiska, dopóki stan wdrożenia nie zostanie zaktualizowany do **Wdrożony**. Ten proces zajmuje zwykle tylko kilka minut. Jeśli proces inicjowania obsługi się nie powiedzie, należy się skontaktować z pomocą techniczną.

6. Aby skorzystać z nowego środowiska, wybierz opcję **Zaloguj się do rozwiązania Talent**.

> [!NOTE]
> Jeszcze przez spełnienie wymagań końcowych można wdrożyć wystąpienie testowe rozwiązania Talent w projekcie. Korzystając z tego wystąpienia, można testować swoje rozwiązanie do momentu sfinalizowania zakupu. W przypadku korzystania z nowego środowiska do testowania należy powtórzyć tę procedurę, aby utworzyć środowisko produkcyjne.

> [!NOTE]
> Środowiska rozwiązania Talent, których obsługa administracyjna jest inicjowana za pośrednictwem usługi LCS, nie zawierają danych demonstracyjnych skonfigurowanych dla zadań modułu Zasoby ludzkie (HR) ani specyficznych dla modułu Talent. Jeśli potrzebujesz środowiska, które zawiera dane demonstracyjne, zalecamy zasubskrybowanie bezpłatnego 60-dniowego [środowiska próbnego rozwiązania Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Chociaż właścicielem środowiska próbnego jest użytkownik, który je utworzył, można do niego zaprosić innych użytkowników za pośrednictwem interfejsu administratora systemu środowiska Core HR. Środowiska próbne zawierają fikcyjne dane, których można używać do eksplorowania programu w bezpieczny sposób. Nie są one przeznaczone do używania jako środowiska produkcyjne. Należy zauważyć, że po wygaśnięciu wersji próbnej środowiska po upływie 60 dni wszystkie zawarte w niej dane są usuwane nie można ich odzyskać. Po wygaśnięciu istniejącego środowiska można zarejestrować się na nowe środowisko próbne.

## <a name="select-a-powerapps-environment"></a>Wybieranie środowiska usługi PowerApps

Integracja środowisk Talent i PowerApps pozwala integrować i poszerzać stosowanie danych aplikacji Talent za pomocą narzędzi usługi PowerApps. Wiedza o przeznaczeniu środowisk usługi PowerApps nie tylko pomoże Ci tworzyć aplikacje rozszerzające funkcjonalność modułu Talent, ale może również pomóc wybrać odpowiednie środowisko podczas inicjowania obsługi modułu Talent. Aby uzyskać więcej informacji na temat środowisk PowerApps, w tym o ich zakresie, uzyskiwaniu dostępu oraz zasadach tworzenia i wybierania środowiska, zobacz [Zapowiedź środowisk PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Przy ustalaniu, w którym środowisku usługi PowerApps wdrożyć moduł Talent, kieruj się poniższymi wskazówkami: 
1. W usłudze LCS wybierz opcję Zarządzaj środowiskami lub przejdź bezpośrednio do centrum administracyjnego usługi PowerApps, gdzie możesz obejrzeć istniejące i tworzyć nowe środowiska.
2. Jedno środowisko aplikacji Talent jest mapowane na jedno środowisko usługi PowerApps.
3. Środowisko usługi PowerApps „zawiera” aplikację Talent wraz z towarzyszącymi aplikacjami środowisk PowerApps, Flow i CDS. Usunięcie środowiska usługi PowerApps spowoduje wykasowanie znajdujących się w nim aplikacji.
4. Należy wziąć pod uwagę strategie integracja i testowanie danych, na przykład piaskownicę (wirtualne środowisko testowe), testy akceptacji użytkownika czy produkcję. Dlatego zalecamy rozważenie różnych skutków dla danego wdrożenia, ponieważ później nie jest łatwo zmienić mapowanie środowiska aplikacji Talent na inne środowisko usługi PowerApps.
5. Następujące środowiska usługi PowerApps nie mogą być używane dla aplikacji Talent i będą odfiltrowane z listy wyboru w usłudze LCS:
 
    **Środowiska usługi CDS w wersji 2.0** Usługa CDS w wersji 2.0 zostanie udostępniona publicznie 21 marca 2018 roku, jednak aplikacja Talent jeszcze nie obsługuje tej wersji. Chociaż można wyświetlać i tworzyć bazy danych w wersji CDS 2.0 w centrum administracyjnym usługi PowerApps, będą one bezużyteczne w aplikacji Talent. Opcja używania środowisk usługi CDS 2.0 we wdrożeniach modułu Talent będzie dostępna w przyszłości.
   
   > [!Note]
   > Aby rozróżnić między środowiskami usługi CDS w wersjach 1.0 i 2.0 w portalu administracyjnego, zaznacz środowisko i przyjrzyj się sekcji **Szczegóły**. Wszystkie środowiska w wersji CDS 2.0 mają dopisek „Tymi ustawieniami można zarządzać w centrum administracyjnym usługi Dynamics 365”, wskazują wersję wystąpienia i nie mają karty Baza danych. 
 
   **Domyślnie środowiska usługi PowerApps** Mimo że każda dzierżawa ma automatycznie włączoną obsługę w domyślnym środowisku usługi PowerApps, nie zalecamy używania tego środowiska w połączeniu z aplikacją Talent, ponieważ wszyscy użytkownicy dzierżawy mają dostęp do środowiska usługi PowerApps i mogą przypadkowo uszkodzić dane produkcyjne podczas testowania i eksplorowania integracji z usługami PowerApps lub Flow.
   
   <strong>Środowiska testowe</strong> Środowiska z nazwą taką jak „TestDrive — alias@domain” są tworzone z 60-dniowym okresem ważności. Po tym czasie przestają działać, co powoduje automatycznie usunięcie środowiska.
   
   **Nieobsługiwana regiony** Obecnie aplikacja Talent jest obsługiwana tylko w następujących regionach: Stany Zjednoczone, Europa i Australia.
  
6. Po ustaleniu odpowiedniego środowiska, które ma być używane, nie istnieje żadne konkretne działanie do wykonania. Kontynuuj proces inicjowania obsługi. 
 
## <a name="create-a-new-powerapps-environment-if-required"></a>Tworzenie nowego środowiska PowerApps (jeśli wymagane)

Za pomocą skryptu programu PowerShell utwórz nowe środowisko usługi PowerApps dla modułu Talent w kontekście administratora dzierżawy, który ma licencję Plan 2 na usługę PowerApps. Skrypt automatyzuje następujące czynności:


 + Tworzenie środowiska usługi PowerApps
 + Tworzenie bazy danych usługi CDS 1.0
 + Usuwanie wszystkich przykładowych danych z bazy danych usługi CDS 1.0


Wykonaj poniższe instrukcje, aby uruchomić skrypt:

1. Pobierz plik ProvisionCDSEnvironment.zip z następującej lokalizacji: [Skrypty inicjowania obsługi środowiska CDS](https://go.microsoft.com/fwlink/?linkid=870436)  

2. Rozpakuj całą zawartość pliku ProvisionCDSEnviroinment.zip do folderu.

3. Uruchom program Windows PowerShell lub Windows PowerShell ISE jako administrator.

   Przejdź do tematu [Ustawianie zasad wykonywania](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6), aby dowiedzieć się więcej o konfigurowaniu zasad wykonywania pozwalających na uruchamianie skryptów.
  
4. W programie PowerShell przejdź do folderu, w którym rozpakowano plik, i uruchom następujące polecenie, zastępując wartości zgodnie ze wskazówkami poniżej:
 
   ```.\ProvisionCDSEnvironment -EnvironmentName MyNewEnvironment -Location YourLocation```

    
   W miejsce **MyNewEnvironment** wpisz nazwę swojego środowiska. Ta nazwa będzie wyświetlana w usłudze LCS i widziana przez użytkowników podczas wybierania środowiska, które ma być stosowane dla aplikacji Talent. 

   W miejsce **YourLocation** wpisz jeden z obsługiwanych regionów aplikacji Talent: unitedsates, europe, australia. 

   Parametr **-Verbose** jest opcjonalny i powoduje generowanie szczegółowych informacji, które można wysłać działowi pomocy technicznej w razie problemów.

5. Kontynuuj proces inicjowania obsługi.
 


## <a name="grant-access-to-the-environment"></a>Przyznawanie dostępu do środowiska
Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Dodatkowym użytkownikom aplikacji trzeba jednoznacznie przyznać dostęp. W celu udzielenia dostępu trzeba [dodać użytkowników](../dev-itpro/sysadmin/tasks/create-new-users.md) i [przypisać im odpowiednie role](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) w środowisku Core HR. Należy również dodać tych użytkowników do środowiska PowerApps, tak aby mieli oni dostęp do aplikacji Attract i Onboard. Procedura jest opisana poniżej. Jeśli potrzebujesz pomocy przy wykonywaniu tych czynności, zobacz wpis na blogu [Wprowadzenie do centrum administracyjnego usługi PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/).

Procedurę wykonuje administrator globalny, który wdrożył środowisko Talent.

1. Otwórz [centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/environments).
2. Zaznacz odpowiednie środowiska.
3. Na karcie **Zabezpieczenia** dodaj wymaganych użytkowników do roli **Twórca środowiska**.

    Należy zauważyć, że ten ostatni krok, w którym ręcznie dodajesz użytkowników do środowiska PowerApps, jest tymczasowy. Docelowo będzie on wykonywany automatycznie podczas dodawania użytkowników w środowisku Core HR.

