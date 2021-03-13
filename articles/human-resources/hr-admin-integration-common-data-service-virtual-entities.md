---
title: Konfiguruj tabele wirtualne usługi Dataverse
description: W tym temacie przedstawiono sposób konfigurowania tabel wirtualnych dla systemu Dynamics 365 Human Resources. Generuj i aktualizuj istniejące tabele wirtualne oraz analizuj wygenerowane i dostępne tabele.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cd299b51e38cc30c3e18f3ef9de1f43fa817b840
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113899"
---
# <a name="configure-dataverse-virtual-tables"></a>Konfiguruj tabele wirtualne usługi Dataverse

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Dynamics 365 Human Resources jest wirtualnym źródłem danych w usłudze Microsoft Dataverse. Obsługuje on pełne operacje tworzenia, odczytu, aktualizacji i usuwania (CRUD) z Dataverse i Microsoft Power Platform. Dane dla tabel wirtualnych nie są przechowywane w usłudze Dataverse, ale w bazie danych aplikacji.

Aby włączyć operacje CRUD dla jednostek zasobów ludzkich z usługi Dataverse, należy udostępnić jednostki jako tabele wirtualne w usłudze Dataverse. Pozwala to na wykonywanie operacji CRUD z usługi Dataverse i Microsoft Power Platform na danych znajdujących się w module Zasoby ludzkie. Operacje te obsługują również pełne sprawdzanie poprawności logiki biznesowej w celu zapewnienia integralności danych podczas zapisywania danych w jednostkach.

> [!NOTE]
> Jednostki Human Resources odpowiadają tabelom Dataverse. Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>Dostępne tabele wirtualne dla modułu Zasoby ludzkie

Wszystkie jednostki protokołu OData (Open Data Protocol) w module Zasoby ludzkie są dostępne jako tabele wirtualne w usłudze Dataverse. Są one również dostępne w programie Power Platform. Teraz możesz tworzyć aplikacje i środowiska z danymi bezpośrednio z modułu Zasoby ludzkie z pełnymi funkcjami CRUD bez kopiowania lub synchronizowania danych do usługi Dataverse. Portale Power Apps umożliwiają tworzenie zewnętrznych stron internetowych, które pozwalają realizować scenariusze współpracy w zakresie procesów biznesowych w module Zasoby ludzkie.

Można wyświetlić listę tabel wirtualnych włączonych w środowisku i rozpocząć pracę z tabelami w [Power Apps](https://make.powerapps.com) w rozwiązaniu **Dynamics 365 HR tabel miarowych**.

![Tabele wirtualne HR Dynamics 365 w Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Tabele wirtualne a tabele macierzyste

Tabele wirtualne dla modułu Zasoby ludzkie nie są takie same jak tabele natywne Dataverse utworzone dla modułu Zasoby ludzkie. 

Tabele natywne dla modułu Zasoby ludzkie są generowane oddzielnie i utrzymywane w rozwiązaniu HCM Common w Dataverse. W przypadku tabel natywnych dane są przechowywane w usłudze Dataverse i wymagają synchronizacji z bazą danych aplikacji Zasoby ludzkie.

> [!NOTE]
> Aby uzyskać listę tabel natywnych usługi Dataverse dla modułu Zasoby ludzkie, zobacz temat [Tabele usługi Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).

## <a name="setup"></a>Konfiguracja

Wykonaj te kroki konfiguracji, aby włączyć tabele wirtualne w danym środowisku.

### <a name="enable-virtual-tables-in-human-resources"></a>Włącz tabele wirtualne w module Zasoby ludzkie

Najpierw musisz włączyć tabele wirtualne w obszarze roboczym **Zarządzanie funkcjami**.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz kafelek **Zarządzanie funkcjami**.

3. Wybierz **Obsługę tabel wirtualnych dla HR w Dataverse**, a następnie wybierz opcję **Włącz**.

Aby uzyskać więcej informacji na temat włączania i wyłączania funkcji, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Rejestracja aplikacji w usłudze Microsoft Azure

Najpierw należy zarejestrować wystąpienie modułu Zasoby ludzkie w witrynie Azure Portal, aby platforma tożsamości Microsoft mogła udostępniać usługi uwierzytelniania i autoryzacji aplikacjom i użytkowników. Aby uzyskać więcej informacji o rejestrowaniu aplikacji na platformie Azure, zobacz temat [Szybki Start: rejestracja aplikacji na platformie tożsamości Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

1. Otwórz portal [Microsoft Azure](https://portal.azure.com).

2. Na liście usług Azure wybierz pozycję **Rejestracje aplikacji**.

3. Wybierz opcję **Nowa rejestracja**.

4. W polu **Nazwa** wprowadź opisową nazwę aplikacji. Na przykład **Tabele wirtualne Dynamics 365 Human Resources**.

5. W polu **Identyfikator URI przekierowania** wprowadź adres URL obszaru nazw wystąpienia moduły Zasoby ludzkie.

6. Wybierz opcję **Zarejestruj**.

7. Po zakończeniu rejestracji w module Azure Portal zostanie wyświetlone okienko **Przegląd** rejestracji aplikacji , które zawiera **Identyfikator aplikacji (klienta)**. Zapisz teraz **identyfikator aplikacji (klienta)**. Te informacje wprowadzisz podczas [Konfigurowania źródła danych tabeli wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

8. W lewym okienku nawigacji wybierz opcję **Certyfikaty i klucze tajne**.

9. W sekcji **Klucze tajne klienta** strony wybierz opcję **Nowy klucz tajny klienta**.

10. Podaj opis, wybierz czas trwania i wybierz przycisk **Dodaj**.

11. Zapisz wartość klucza tajnego. Te informacje wprowadzisz podczas [Konfigurowania źródła danych tabeli wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > Pamiętaj, aby w tym momencie zapisać wartość klucza tajnego. Klucz tajny nie jest nigdy wyświetlany ponownie po opuszczeniu tej strony.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Instalacja aplikacji Dynamics 365 HR Virtual Entity

Zainstaluj aplikację Dynamics 365 HR Virtual Table w środowisku Power Apps, aby wdrożyć pakiet rozwiązania tabel wirtualnych w usłudze Dataverse.

1. Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).

2. Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.

3. W sekcji **Zasoby** wybierz pozycję **Aplikacje Dynamics 365**.

4. Wybierz akcję **Zainstaluj aplikację**.

5. Wybierz **Dynamics 365 HR Virtual Table** i kliknij przycisk **Dalej**.

6. Przejrzyj i zaznacz pole wyboru, aby wyrazić zgodę na warunki użytkowania usługi.

7. Wybierz **Zainstaluj**.

Instalacja potrwa kilka minut. Po zakończeniu przejdź do kolejnych kroków.

![Instalacja aplikacji Dynamics 365 HR Virtual Table z centrum administracyjnego Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a>Konfiguracja źródła danych tabeli wirtualnej 

Następnym krokiem jest skonfigurowanie źródła danych tabeli wirtualnej w środowisku Power Apps. 

1. Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).

2. Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.

3. Wybierz **Adres URL środowiska** w sekcji **Szczegóły** strony.

4. W oknie **Centrum kondycji rozwiązania** wybierz ikonę **Wyszukiwanie zaawansowane** w prawym górnym rogu strony aplikacji.

5. Na stronie **Wyszukiwanie zaawansowane**, z listy rozwijanej **Wyszukaj** wybierz pozycję **Konfiguracje wirtualnego źródła danych Finance and Operations**.

6. Wybierz opcję **Wyniki**.

7. Wybierz rekord **Microsoft HR Data Source**.

8. Wprowadź wymagane informacje dotyczące konfiguracji źródła danych:

   - **Docelowy adres URL**: adres URL obszaru nazw modułu Zasoby ludzkie. Docelowy adres URL ma format:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Na przykład:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Pamiętaj, aby umieścić znak „**/**” na końcu adresu URL, aby uniknąć błędu.

   - **Identyfikator dzierżawcy**: identyfikator dzierżawcy Azure Active Directory (Azure AD).

   - **Identyfikator aplikacji w usłudze AAD**: identyfikator aplikacji (klienta) utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure. Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Wpis tajny aplikacji w usłudze AAD**: wpis tajny utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure. Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Źródło danych Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Wybierz opcję **Zapisz i zamknij**.

### <a name="grant-app-permissions-in-human-resources"></a>Udzielanie uprawnień aplikacji w module Zasoby ludzkie

Udziel uprawnień dwóm aplikacjom Azure AD w module zasoby ludzkie:

- Aplikacji utworzonej dla Twojej dzierżawy w portalu Microsoft Azure
- Aplikacji Dynamics 365 HR Virtual Table zainstalowanej w środowisku Power Apps 

1. W module Zasoby ludzkie otwórz stronę **Aplikacje Azure Active Directory**.

2. Wybierz pozycję **Nowy**, aby utworzyć nowy rekord aplikacji:

    - W polu **Identyfikator klienta** wprowadź identyfikator klienta aplikacji zarejestrowanej w portalu Microsoft Azure.
    - W polu **Nazwa** wprowadź nazwę aplikacji zarejestrowanej w portalu Microsoft Azure.
    - W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.

3. Wybierz pozycję **Nowy**, aby utworzyć drugi rekord aplikacji:

    - **Identyfikator klienta**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nazwa**: Dynamics 365 HR Virtual Table
    - W polu **Identyfikator użytkownika** wybierz identyfikator użytkownika z uprawnieniami administratora w module Zasoby ludzkie i środowisku Power Apps.

## <a name="generate-virtual-tables"></a>Generowanie tabel wirtualnych

Po zakończeniu pracy Instalatora można wybrać tabele wirtualne, które mają zostać wygenerowane i włączone w instancji usługi Dataverse.

1. W module Zasoby ludzkie otwórz stronę **Integracja Dataverse**.

2. Wybierz kartę **Tabele wirtualne**.

> [!NOTE]
> **Włączenie przełączania tabel wirtualnych** będzie automatycznie ustawiane na wartość **Tak**, gdy wszystkie wymagane ustawienia zostaną zakończone. Jeśli przełącznik ma wartość **Nie**, sprawdź kroki w poprzednich sekcjach tego dokumentu, aby upewnić się, że wszystkie ustawienia wymagań wstępnych zostały zakończone.

3. Wybierz tabelę lub tabele, w których chcesz utworzyć w Dataverse.

4. Wybierz opcję **Generuj/Odśwież**.

![Integracja z usługą Dataverse](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a>Sprawdź stan generacji tabel

Tabele wirtualne są generowane w Dataverse w trakcie asynchronicznego procesu w tle. Aktualizacje w procesie są wyświetlane w centrum akcji. Szczegóły procesu, w tym dzienniki błędów, znajdują się na stronie **Automatyzacja procesów**.

1. W module Human Resources otwórz stronę listy **Automatyzacja procesów**.

2. Wybierz kartę **Procesy w tle**.

3. Wybierz **Proces w tle asynchronicznego sondowania tabeli wirtualnej**.

4. Służy do **Wyświetl ostatnie wyniki**.

W okienku slideout wyświetlane są najnowsze wyniki wykonania procesu. Można przejrzeć dziennik procesu, w tym wszystkie błędy zwrócone przez system Dataverse.

## <a name="see-also"></a>Informacje dodatkowe

[Co to jest usługa Dataverse?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[Tabele w Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[Omówienie relacji tabel](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[Tworzenie i edytowanie tabel wirtualnych zawierających dane z zewnętrznego źródła danych](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Co to są portale Power Apps?](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[Omówienie tworzenia aplikacji w Power Apps](https://docs.microsoft.com/powerapps/maker/)
