---
title: Integracja z usługą LinkedIn Talent Hub
description: W tym temacie opisano sposób konfigurowania pul integracji Microsoft Dynamics 365 Human Resources i LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
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
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6f70e3a6ccf9770c75334d355db5e9df9ee912dd
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527892"
---
# <a name="integrate-with-linkedin-talent-hub"></a>Integracja z usługą LinkedIn Talent Hub

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) jest platformą systemu śledzenia kandydatów (ATS). Umożliwia on źródło, zarządzanie i zatrudnianie pracowników w jednym miejscu. Integrując Microsoft Dynamics 365 Human Resources z LinkedIn Talent Hub, można łatwo utworzyć rekordy pracowników w Human Resources dla kandydatów, którzy zostali zatrudnieni na stanowiskach.

## <a name="setup"></a>Konfiguracja

Administrator systemu musi wykonać zadania konfiguracyjne, aby włączyć integrację z LinkedIn Talent Hub. Najpierw w środowisku Power Apps należy skonfigurować użytkownika i rolę zabezpieczeń, aby LinkedIn Talent Hub odpowiednich uprawnień do zapisywania danych w Human Resources.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>Połącz środowisko z LinkedIn Talent Hub

1. Otwórz [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).

2. W menu rozwijanym użytkownik Wybierz opcję **Ustawienia produktu**.

3. W lewym okienku nawigacji w sekcji **Zaawansowane** wybierz opcję **Integracje**.

4. Wybierz **Autoryzację** dla integracji rozwiązania Microsoft Dynamics 365 Human Resources.

5. Na stronie **Dynamics 365 Human Resources** wybierz środowisko, którego ma dotyczyć łącze do LinkedIn Talent Hub, a następnie wybierz **Połącz**.

    ![Przygotowywanie LinkedIn Talent Hub](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > Możesz łączyć tylko ze środowiskami, w których konto użytkownika ma dostęp administratora zarówno do środowiska Human Resources, jak i skojarzonego środowiska Power Apps. Jeśli na stronie łączy Human Resources nie ma żadnych środowisk, upewnij się, że masz licencjonowane środowiska Human Resources w dzierżawie, a użytkownik, który zalogował się na stronie łącza, ma uprawnienia administratora zarówno dla środowiska Human Resources, jak i środowiska Power Apps.

### <a name="create-a-power-apps-security-role"></a>Tworzenie roli zabezpieczeń Power Apps

1. Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).

2. Na liście **Środowiska** wybierz środowisko skojarzone ze środowiskiem Human Resources, które chcesz połączyć z Twoim wystąpieniem LinkedIn Talent Hub.

3. Wybierz **Ustawienia**.

4. Rozwiń węzeł **Użytkownicy + uprawnienia** i wybierz pozycję **Role zabezpieczeń**.

5. Na stronie **Role zabezpieczeń** na pasku narzędzi wybierz opcję **Nowa rola**.

6. Na karcie **Szczegóły** wprowadź nazwę roli, na przykład **Integracja LinkedIn Talent Hub HRIS**.

7. Na karcie **Dostosowywanie** wybierz uprawnienia do **Odczytu** na poziomie organizacji dla następujących jednostek:

    - Jednostka
    - Pole
    - Pokrewieństwo

8. Zapisz i zamknij rolę zabezpieczeń.

### <a name="create-a-power-apps-application-user"></a>Utwórz użytkownika aplikacji Power Apps

Należy utworzyć użytkownika aplikacji dla adaptera LinkedIn Talent Hub, aby nadać adapterowi uprawnienia do zapisywania rekordów kandydatów w środowisku Power Apps.

1. Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).

2. Na liście **Środowiska** wybierz środowisko skojarzone ze środowiskiem Human Resources, które chcesz połączyć z Twoim wystąpieniem LinkedIn Talent Hub.

3. Wybierz **Ustawienia**.

4. Rozwiń węzeł **Użytkownicy + uprawnienia** i wybierz pozycję **Użytkownicy**.

5. Wybierz opcję **Zarządzaj użytkownikami w systemie Dynamics 365**.

6. Skorzystaj z menu rozwijanego powyżej listy, aby zmienić widok z domyślnego widoku **Włączeni użytkownicy** na **Użytkowników aplikacji**.

    ![Widok Użytkownicy aplikacji](./media/hr-admin-integration-power-apps-application-users.jpg)

7. Na pasku narzędzi wybierz **Nowy**.

8. Na stronie **Nowy użytkownik** wykonaj następujące kroki:

    1. Zmień wartość w polu **Tryb użytkownika** na **Użytkownik aplikacji**.
    2. W polu **Nazwa użytkownika** określ **Integracja Dynamics365 LinkedIn HRIS**.
    3. Ustaw wartość w polu **Identyfikator aplikacji** na **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    4. Wprowadź dowolną wartość w polach **Imię**, **Nazwisko** i **Podstawowy adres e-mail**.
    5. Wybierz **Zapisz \& Zamknij** na pasku narzędzi.

### <a name="assign-a-security-role-to-the-new-user"></a>Przypisz rolę zabezpieczeń do nowego użytkownika

Po zapisaniu i zamknięciu nowego użytkownika aplikacji w poprzedniej sekcji wrócisz do strony **Listy użytkowników**.

1. Na stronie **Listy użytkowników** zmień widok na **Użytkowników aplikacji**.

2. Wybierz użytkownika aplikacji, który został utworzony w poprzedniej sekcji.

3. Na pasku narzędzi wybierz opcję **Zarządzaj rolami**.

4. Wybierz utworzoną wcześniej rolę zabezpieczeń dla integracji.

5. Kliknij przycisk **OK**.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Dodaj aplikację Azure Active Directory w Human Resources

1. W Dynamics 365 Human Resources otwórz stronę **Aplikacje Azure Active Directory**.
2. Dodaj nowy rekord do listy i ustaw następujące pola:

    - **Identyfikator klienta**: Wpisz **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    - **Nazwa**: należy wprowadzić nazwę utworzonej wcześniej roli zabezpieczeń Power Apps, na przykład **Integracja LinkedIn Talent Hub HRIS**.
    - **Identyfikator użytkownika**: Wybierz użytkownika, który ma uprawnienia do zapisywania danych w zarządzaniu personelem.

### <a name="create-the-entity-in-common-data-service"></a>Utwórz jednostkę w Common Data Service

> [!IMPORTANT]
> Integracja z LinkedIn Talent Hub zależy od jednostek wirtualnych w module Common Data Service dla Human Resources. Jako warunek wstępny dla tego kroku w konfiguracji należy skonfigurować jednostki wirtualne. Aby uzyskać informacje o konfigurowaniu jednostek wirtualnych, zajrzyj do [Konfiguracja jednostek wirtualnych Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

1. W module Zasoby ludzkie otwórz stronę **Integracja Common Data Service (CDS)**.

2. Wybierz kartę **Jednostki wirtualne**.

3. Filtruj listę jednostek według etykiety jednostki, aby odnaleźć **Kandydata wyeksportowanego z serwisu LinkedIn**.

4. Wybierz jednostkę i wybierz przycisk **Generuj/odśwież**.

## <a name="exporting-candidate-records"></a>Eksportowanie rekordów kandydatów

Po zakończeniu instalacji pracownicy działu informatyki i specjaliści do zasobów ludzkich mogą skorzystać z funkcji **Eksportu do HRIS** w LinkedIn Talent Hub, aby wyeksportować zarejestrowane rekordy kandydatów z LinkedIn Talent Hub do Human Resources.

### <a name="export-records-from-linkedin-talent-hub"></a>Eksportuj rekordy z LinkedIn Talent Hub

Po przeniesieniu kandydata do procesu rekrutacji i po jego zatrudnieniu można wyeksportować rekord kandydata z LinkedIn Talent Hub do Human Resources.

1. W LinkedIn Talent Hub otwórz projekt, dla którego został zatrudniony nowy pracownik etatowy.

2. Wybierz rekord kandydata.

3. Wybierz pozycję **Zmień etap**, a następnie wybierz opcję **Zatrudniono**.

4. W menu wielokropka (**...**) dla kandydata wybierz **Eksportuj do HRIS**.

5. W okienku **Eksportuj do HRIS** wprowadź informacje, które muszą zostać wyeksportowane:

    - W polu **Dostawca HRIS** wybierz pozycję **Microsoft Dynamics 365 Human Resources**.
    - W polu **Data rozpoczęcia** wybierz wartość dla nowego pracownika.
    - W polu **Stanowisko** wprowadź stanowisko nowego pracownika etatowego.
    - W polu **Lokalizacja** wprowadź lokalizację, w której ma być oparty dany pracownik etatowy.
    - Wprowadź lub Sprawdź adres e-mail pracownika.

![Eksportowanie do okienka HRIS w LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Dokończ dołączanie do Human Resources

Rekordy kandydatów eksportowane z LinkedIn Talent Hub do Human Resources znajdują się w sekcji **Kandydaci do zatrudnienia** na stronie **Zarządzanie personelem**.

1. W module Human Resources otwórz stronę listy **Zarządzanie personelem**.

2. W sekcji **Kandydaci do zatrudnienia** wybierz opcję **Zatrudnij** dla wybranego kandydata.

3. W oknie dialogowym **Zatrudnij nowego pracownika** przejrzyj rekord i dodaj wszystkie wymagane informacje. Możesz również wybrać numer stanowiska, na które kandydat został zatrudniony.

Po wprowadzeniu wymaganych informacji można kontynuować procesy standardowe służące do tworzenia rekordów pracowników i dołączania pracowników.

Następujące szczegóły są importowane i uwzględniane w nowym rekordzie pracownika etatowego:

- Imię
- Nazwisko
- Data rozpoczęcia zatrudnienia
- Adres e-mail
- Numer telefonu

## <a name="see-also"></a>Informacje dodatkowe

[Konfigurowanie jednostek wirtualnych usługi Common Data Service](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Co to jest usługa Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
