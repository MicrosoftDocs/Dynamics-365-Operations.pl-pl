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
ms.sourcegitcommit: a53c1997f74ebe572b17cc3090d2e236b6fe78f6
ms.openlocfilehash: 8a84cfe9b73f0c72f3cb0c3843749754c6b3d538
ms.contentlocale: pl-pl
ms.lasthandoff: 01/31/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Inicjowanie oprogramowania Microsoft Dynamics 365 for Talent
Ten temat przeprowadzi użytkownika przez proces inicjacji nowego środowiska dla oprogramowania Microsoft Dynamics 365 for Talent. Temat te opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Talent u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). Jeśli masz już licencję na oprogramowanie Microsoft Dynamics 365 uwzględniającą plan aplikacji Talent, a nie jesteś w stanie wykonać kroków opisanych w tym temacie, skontaktuj się z pomocą techniczną.

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

    Nowe środowisko pojawi się na liście środowisk w okienku nawigacji po lewej stronie. Jednak nie można rozpocząć korzystania ze środowiska, dopóki stan wdrożenia nie zostanie zaktualizowany do **Wdrożony**. Ten proces zajmuje zwykle tylko kilka minut. Jeśli inicjacja się nie powiedzie, należy skontaktować się z pomocą techniczną.

6. Aby skorzystać z nowego środowiska, wybierz opcję **Zaloguj się do rozwiązania Talent**.

> [!NOTE]
> Jeszcze przez spełnienie wymagań końcowych można wdrożyć wystąpienie testowe rozwiązania Talent w projekcie. Korzystając z tego wystąpienia, można testować swoje rozwiązanie do momentu sfinalizowania zakupu. W przypadku korzystania z nowego środowiska do testowania należy powtórzyć tę procedurę, aby utworzyć środowisko produkcyjne.

## <a name="create-a-new-powerapps-environment-if-required"></a>Tworzenie nowego środowiska PowerApps (jeśli wymagane)

Wizja stojąca za integracją modułu Talent ze środowiskami PowerApps to umożliwienie integracji danych i obsługi rozszerzeń poprzez stosowanie narzędzi PowerApps do danych modułu Talent. W związku z tym ważna jest znajomość przeznaczenia środowisk PowerApps przy wybieraniu środowiska dla modułu Talent. Aby uzyskać więcej informacji na temat środowisk PowerApps, w tym o ich zakresie, uzyskiwaniu dostępu oraz zasadach tworzenia i wybierania środowiska, zobacz [Zapowiedź środowisk PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/).  Każda dzierżawa jest automatycznie obsługiwana w środowisku PowerApps Default, jednak może to nie być najlepsze środowisko dla konkretnego wdrożenia aplikacji Talent. Na tym etapie należy wziąć pod uwagę integrację danych i strategie testowania, dlatego zalecamy rozważenie różnych skutków wdrożenia, ponieważ później trudno wprowadzać modyfikacje.

1. Wybierz opcję **Zarządzaj środowiskami** w usłudze LCS. Nastąpi przejście [Centrum administracyjnego usługi PowerApps](https://preview.admin.powerapps.com/environments), gdzie można przeglądać istniejące środowiska i tworzyć nowe.
2. Kliknij przycisk (**+**) **Nowe środowisko**.
3. Wprowadź niepowtarzalną nazwę środowiska i wybierz lokalizację jego wdrożenia.

    > [!NOTE]
    > Aplikacja Talent nie jest dostępna we wszystkich regionach. W związku z tym przed wybraniem lokalizacji dla środowiska należy sprawdzić jej dostępność.

4. Po wyświetleniu zapytania o utworzenie bazy danych wybierz opcję **Utwórz bazę danych**, aby utworzyć bazę danych Common Data Service (CDS), która musi obsługiwać część danych aplikacji Talent. Tworząc bazę danych, można także zintegrować z aplikacje środowiska PowerApps z aplikacją Talent.
5. Pojawi się monit o poziom dostępu do bazy danych. Zaleca się wybranie opcji **Ograniczenie dostępu**, ponieważ uniemożliwia ona użytkownikom aplikacji Talent bezpośredni dostęp do poufnych danych za pomocą aplikacji PowerApps.
6. Utworzona baza danych CDS zawiera dane demonstracyjne. Te dane demonstracyjne są przydatne, ponieważ można wykorzystać firmę w niej zawartą do wykonania testów lub utworzyć na ich podstawie nagrania zadań lub przewodniki do zadań. Jednak dane demonstracyjne powodują dodanie do środowiska produkcyjnego między innymi nieaktywnych pracowników etatowych i fikcyjnych adresów. Aby usunąć dane demonstracyjne po utworzeniu bazy danych CDS, wykonaj następujące czynności:

    > [!IMPORTANT]
    > Jeśli uprzednio utworzono bazę danych CDS i wprowadzono do niej jakiekolwiek dane produkcyjne firmy, należy pamiętać, że wykonanie tych czynności spowoduje usunięcie **wszystkich** danych w wybranej bazie danych, nawet danych produkcyjnych firmy.

    1. Zaloguj się na platformie [PowerApps](https://preview.web.powerapps.com/home), a następnie z listy rozwijanej w prawej części strony wybierz środowisko utworzone w kroku 2.
    2. W okienku nawigacyjnym z lewej strony rozwiń węzeł **Common Data Service** i wybierz opcję **Jednostki**.
    3. Po prawej stronie strony kliknij przycisk elipsy (**...**), a następnie wybierz opcję **Wyczyść wszystkie dane**.
    4. Wybierz opcję **Usuń dane**, aby potwierdzić usunięcie danych. Ta akcja spowoduje usunięcie wszystkich danych demonstracyjnych umieszczonych domyślnie w CDS. Usunięte zostaną również wszelkie inne dane wprowadzone do wybranej bazy danych.
    
Teraz można korzystać z nowego środowiska.

## <a name="granting-access-to-the-environment"></a>Przyznawanie dostępu do środowiska
Globalny administrator, który utworzył środowisko, będzie miał dostęp domyślnie, ale dodatkowym użytkownikom aplikacji trzeba jednoznacznie przyznać dostęp. Można to zrobić poprzez [dodanie użytkowników](../dev-itpro/sysadmin/tasks/create-new-users.md) i [przypisanie im odpowiednich ról](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) w środowisku Core HR. Dodatkowo należy również dodać tych użytkowników do środowiska PowerApps, tak aby mieli oni dostęp do aplikacji Attract i Onboard.  Wpis w blogu [Wprowadzenie do centrum administracyjnego usługi PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/) może pomóc w wykonaniu kroków opisanych tutaj:

> 1.    Globalny administrator, który wdrożył środowisko Talent, powinien przejść do [centrum administracyjnego usługi PowerApps](https://preview.admin.powerapps.com/environments).   
> 2.    Zaznacz interesujące Cię środowiska.
> 3.    Na karcie Zabezpieczenia dodaj potrzebnych użytkowników do roli „Twórca środowiska”.

Należy zauważyć, że ten ostatni krok dodawania użytkowników do środowiska PowerApps jest tymczasowy. Docelowo dodamy funkcję, która będzie to robiła automatycznie podczas dodawania użytkownika w środowisku Core HR.


