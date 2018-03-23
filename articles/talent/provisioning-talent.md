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
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: e4459e8be4bfab8e0789744eacd533286b6c05e0
ms.contentlocale: pl-pl
ms.lasthandoff: 03/08/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Inicjowanie oprogramowania Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

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
2. Aplikacja talent jest zawsze inicjowana w środowisku Microsoft PowerApps, aby umożliwić integrację z PoweApps i możliwość rozszerzenia. Jeśli nie masz jeszcze środowiska PowerApps, wykonaj najpierw kroki zawarte w sekcji „Tworzenie nowego środowiska PowerApps (jeśli wymagane)” znajdującej się w tym temacie.

    > [!NOTE]
    > Aby wyświetlić istniejące środowiska lub utworzyć nowe, należy przypisać delegowanego administratora odpowiedzialnego za inicjację aplikacji Talent do licencji P2 środowiska PowerApps. Jeśli organizacja nie posiada licencji P2 środowiska PowerApps, można ją uzyskać u CSP lub ze [strony cennika środowiska PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

3. Wybierz opcję **Dodaj**, a następnie wybierz środowisko, w którym zostanie zainicjowana aplikacja Talent.
4. Wybierz opcję **Tak**, aby zaakceptować warunki i rozpocząć wdrażanie.

    Nowe środowisko pojawi się na liście środowisk w okienku nawigacji po lewej stronie. Jednak nie można rozpocząć korzystania ze środowiska, dopóki stan wdrożenia nie zostanie zaktualizowany do **Wdrożony**. Ten proces zajmuje zwykle tylko kilka minut. Jeśli proces inicjowania obsługi się nie powiedzie, należy się skontaktować z pomocą techniczną.

6. Aby skorzystać z nowego środowiska, wybierz opcję **Zaloguj się do rozwiązania Talent**.

> [!NOTE]
> Jeszcze przez spełnienie wymagań końcowych można wdrożyć wystąpienie testowe rozwiązania Talent w projekcie. Korzystając z tego wystąpienia, można testować swoje rozwiązanie do momentu sfinalizowania zakupu. W przypadku korzystania z nowego środowiska do testowania należy powtórzyć tę procedurę, aby utworzyć środowisko produkcyjne.

> [!NOTE]
> Środowiska rozwiązania Talent, których obsługa administracyjna jest inicjowana za pośrednictwem usługi LCS, nie zawierają danych demonstracyjnych skonfigurowanych dla zadań modułu Zasoby ludzkie (HR) ani specyficznych dla modułu Talent. Jeśli potrzebujesz środowiska, które zawiera dane demonstracyjne, zalecamy zasubskrybowanie bezpłatnego 60-dniowego [środowiska próbnego rozwiązania Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Chociaż właścicielem środowiska próbnego jest użytkownik, który je utworzył, można do niego zaprosić innych użytkowników za pośrednictwem interfejsu administratora systemu środowiska Core HR. Środowiska próbne zawierają fikcyjne dane, których można używać do eksplorowania programu w bezpieczny sposób. Nie są one przeznaczone do używania jako środowiska produkcyjne. Należy zauważyć, że po wygaśnięciu wersji próbnej środowiska po upływie 60 dni wszystkie zawarte w niej dane są usuwane nie można ich odzyskać. Po wygaśnięciu istniejącego środowiska można zarejestrować się na nowe środowisko próbne.

## <a name="create-a-new-powerapps-environment-if-required"></a>Tworzenie nowego środowiska PowerApps (jeśli wymagane)
Integracja środowisk Talent i PowerApps pozwala integrować i poszerzać stosowanie danych aplikacji Talent za pomocą narzędzi usługi PowerApps. Wiedza o przeznaczeniu środowisk PowerApps pomoże tworzyć aplikacje spełniające potrzeby firmy w zakresie rozszerzania możliwości aplikacji Talent. Aby uzyskać więcej informacji na temat środowisk PowerApps, w tym o ich zakresie, uzyskiwaniu dostępu oraz zasadach tworzenia i wybierania środowiska, zobacz [Zapowiedź środowisk PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). Każda dzierżawa jest automatycznie obsługiwana w środowisku PowerApps Default, jednak może to nie być najlepsze środowisko dla konkretnego wdrożenia aplikacji Talent. Na tym etapie należy wziąć pod uwagę integrację danych i strategie testowania, dlatego zalecamy rozważenie różnych potencjalnych skutków wdrożenia, ponieważ później trudno cofnąć niektóre decyzje. 

Każda dzierżawa jest automatycznie obsługiwana w środowisku PowerApps Default, jednak może to nie być najlepsze środowisko dla konkretnego wdrożenia aplikacji Talent. Na tym etapie należy wziąć pod uwagę integrację danych i strategie testowania. Dlatego zalecamy rozważenie różnych skutków dla danego wdrożenia, ponieważ później nie jest łatwo zmodyfikować środowisko PowerApps.

1. W usłudze LCS wybierz opcję **Zarządzaj środowiskami**. Nastąpi przejście [Centrum administracyjnego usługi PowerApps](https://preview.admin.powerapps.com/environments), gdzie można przeglądać istniejące środowiska i tworzyć nowe.
2. Wybierz opcję **Nowe środowisko**.
3. Wprowadź niepowtarzalną nazwę środowiska i wybierz lokalizację jego wdrożenia.

    > [!NOTE]
    > Aplikacja Talent nie jest dostępna we wszystkich regionach. W związku z tym przed wybraniem lokalizacji dla środowiska należy sprawdzić jej dostępność.

4. Po wyświetleniu zapytania o utworzenie bazy danych wybierz opcję **Utwórz bazę danych**, aby utworzyć bazę danych Common Data Service (CDS), która musi obsługiwać część danych aplikacji Talent. Tworząc bazę danych, można także zintegrować z aplikacje środowiska PowerApps z aplikacją Talent.
5. Pojawi się monit o poziom dostępu do bazy danych. Zaleca się wybranie opcji **Ograniczenie dostępu**, ponieważ uniemożliwia ona użytkownikom aplikacji Talent bezpośredni dostęp do poufnych danych za pomocą aplikacji PowerApps.
6. Utworzona baza danych CDS zawiera dane demonstracyjne, które powodują dodanie do środowiska produkcyjnego między innymi nieaktywnych pracowników etatowych i fikcyjnych adresów. Aby usunąć dane demonstracyjne po utworzeniu bazy danych CDS, wykonaj następujące czynności:

    > [!IMPORTANT]
    > Jeśli uprzednio utworzono bazę danych CDS i wprowadzono do niej jakiekolwiek dane produkcyjne firmy, wykonanie tych czynności spowoduje usunięcie **wszystkich** danych w wybranej bazie danych, nawet danych produkcyjnych firmy.

    1. Zaloguj się w usłudze [PowerApps](https://preview.web.powerapps.com/home).
    2. Z listy rozwijanej w prawym górnym rogu wybierz środowisko utworzone w kroku 2.
    3. W okienku nawigacyjnym z lewej strony rozwiń węzeł **Common Data Service** i wybierz opcję **Jednostki**.
    4. Po prawej stronie strony kliknij przycisk elipsy (**...**), a następnie wybierz opcję **Wyczyść wszystkie dane**.
    5. Wybierz opcję **Usuń dane**, aby potwierdzić usunięcie danych. Ta akcja spowoduje usunięcie wszystkich danych demonstracyjnych umieszczonych domyślnie w CDS. Usunięte zostaną również wszelkie inne dane wprowadzone do wybranej bazy danych.

Teraz można korzystać z nowego środowiska.

## <a name="grant-access-to-the-environment"></a>Przyznawanie dostępu do środowiska
Domyślnie dostęp do środowiska ma globalny administrator, który je utworzył. Dodatkowym użytkownikom aplikacji trzeba jednoznacznie przyznać dostęp. W celu udzielenia dostępu trzeba [dodać użytkowników](../dev-itpro/sysadmin/tasks/create-new-users.md) i [przypisać im odpowiednie role](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) w środowisku Core HR. Należy również dodać tych użytkowników do środowiska PowerApps, tak aby mieli oni dostęp do aplikacji Attract i Onboard. Procedura jest opisana poniżej. Jeśli potrzebujesz pomocy przy wykonywaniu tych czynności, zobacz wpis na blogu [Wprowadzenie do centrum administracyjnego usługi PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/).

Procedurę wykonuje administrator globalny, który wdrożył środowisko Talent.

1. Otwórz [centrum administracyjne usługi PowerApps](https://preview.admin.powerapps.com/environments).
2. Zaznacz odpowiednie środowiska.
3. Na karcie **Zabezpieczenia** dodaj wymaganych użytkowników do roli **Twórca środowiska**.

Należy zauważyć, że ten ostatni krok, w którym ręcznie dodajesz użytkowników do środowiska PowerApps, jest tymczasowy. Docelowo będzie on wykonywany automatycznie podczas dodawania użytkowników w środowisku Core HR.

