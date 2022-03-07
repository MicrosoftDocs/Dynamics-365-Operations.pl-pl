---
title: Konfigurowanie tabel wirtualnych usługi Dataverse
description: W tym temacie jest pokazany sposób konfigurowania, generowania i aktualizowania istniejących tabel wirtualnych oraz analizowania wygenerowanych i dostępnych tabel dla aplikacji Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f7ffe522f0f17a21280e53728c6efc2823743733
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069153"
---
# <a name="configure-dataverse-virtual-tables"></a>Konfigurowanie tabel wirtualnych usługi Dataverse


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Dynamics 365 Human Resources jest wirtualnym źródłem danych w usłudze Microsoft Dataverse. Obsługuje on pełne operacje tworzenia, odczytu, aktualizacji i usuwania (CRUD) z Dataverse i Microsoft Power Platform. Dane dla tabel wirtualnych nie są przechowywane w usłudze Dataverse, ale w bazie danych aplikacji.

Aby włączyć operacje CRUD dla jednostek zasobów ludzkich z usługi Dataverse, należy udostępnić jednostki jako tabele wirtualne w usłudze Dataverse. Pozwala to na wykonywanie operacji CRUD z usługi Dataverse i Microsoft Power Platform na danych znajdujących się w module Zasoby ludzkie. Operacje te obsługują również pełne sprawdzanie poprawności logiki biznesowej w celu zapewnienia integralności danych podczas zapisywania danych w jednostkach.

> [!NOTE]
> Jednostki Human Resources odpowiadają tabelom Dataverse. Aby uzyskać więcej informacji o Dataverse (poprzednio Common Data Service) i aktualizacjach terminologii, zobacz [Co to jest Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>Dostępne tabele wirtualne dla modułu Zasoby ludzkie

Wszystkie jednostki protokołu OData (Open Data Protocol) w module Zasoby ludzkie są dostępne jako tabele wirtualne w usłudze Dataverse. Są one również dostępne w programie Power Platform. Teraz możesz tworzyć aplikacje i środowiska z danymi bezpośrednio z modułu Zasoby ludzkie z pełnymi funkcjami CRUD bez kopiowania lub synchronizowania danych do usługi Dataverse. Portale Power Apps umożliwiają tworzenie zewnętrznych stron internetowych, które pozwalają realizować scenariusze współpracy w zakresie procesów biznesowych w module Zasoby ludzkie.

Można wyświetlić listę tabel wirtualnych włączonych w środowisku i rozpocząć pracę z tabelami w [Power Apps](https://make.powerapps.com) w rozwiązaniu **Dynamics 365 HR tabel miarowych**.

![Tabele wirtualne HR Dynamics 365 w Power Apps.](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Tabele wirtualne a tabele macierzyste

Tabele wirtualne dla modułu Zasoby ludzkie nie są takie same jak tabele natywne Dataverse utworzone dla modułu Zasoby ludzkie. 

Tabele natywne dla modułu Zasoby ludzkie są generowane oddzielnie i utrzymywane w rozwiązaniu HCM Common w Dataverse. W przypadku tabel natywnych dane są przechowywane w usłudze Dataverse i wymagają synchronizacji z bazą danych aplikacji Zasoby ludzkie.

> [!NOTE]
> Aby uzyskać listę tabel natywnych usługi Dataverse dla modułu Zasoby ludzkie, zobacz temat [Tabele usługi Dataverse](./hr-developer-entities.md).

## <a name="setup"></a>Konfiguracja

Wykonaj te kroki konfiguracji, aby włączyć tabele wirtualne w danym środowisku.

### <a name="enable-virtual-tables-in-human-resources"></a>Włącz tabele wirtualne w module Zasoby ludzkie

Najpierw musisz włączyć tabele wirtualne w obszarze roboczym **Zarządzanie funkcjami**.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz kafelek **Zarządzanie funkcjami**.

3. Wybierz **Obsługę tabel wirtualnych dla HR w Dataverse**, a następnie wybierz opcję **Włącz**.

Aby uzyskać więcej informacji na temat włączania i wyłączania funkcji, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Rejestracja aplikacji w usłudze Microsoft Azure

Najpierw należy zarejestrować wystąpienie modułu Zasoby ludzkie w witrynie Azure Portal, aby platforma tożsamości Microsoft mogła udostępniać usługi uwierzytelniania i autoryzacji aplikacjom i użytkowników. Aby uzyskać więcej informacji o rejestrowaniu aplikacji na platformie Azure, zobacz temat [Szybki Start: rejestracja aplikacji na platformie tożsamości Microsoft](/azure/active-directory/develop/quickstart-register-app).

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

11. Zanotuj wartość tajnych właściwości tabeli **Wartość**. Te informacje wprowadzisz podczas [Konfigurowania źródła danych tabeli wirtualnej](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > Pamiętaj, aby w tym momencie zapisać wartość klucza tajnego. Klucz tajny nie jest nigdy wyświetlany ponownie po opuszczeniu tej strony.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Instalacja aplikacji Dynamics 365 HR Virtual Entity

Zainstaluj aplikację Dynamics 365 HR Virtual Table w środowisku Power Apps, aby wdrożyć pakiet rozwiązania tabel wirtualnych w usłudze Dataverse.

1. W module Zasoby ludzkie otwórz stronę **Integracja Microsoft Dataverse**.

2. Wybierz kartę **Tabele wirtualne**.

3. Wybierz opcję **Zainstaluj aplikację tabeli wirtualnej**.

### <a name="configure-the-virtual-table-data-source"></a>Konfiguracja źródła danych tabeli wirtualnej

Następnym krokiem jest skonfigurowanie źródła danych tabeli wirtualnej w środowisku Power Apps.

1. Otwórz [Centrum administracyjne Power Platform](https://admin.powerplatform.microsoft.com).

2. Na liście **Środowiska** wybierz środowisko Power Apps skojarzone z wystąpieniem modułu Zasoby ludzkie.

3. Wybierz **Adres URL środowiska** w sekcji **Szczegóły** strony.

4. W oknie **Centrum kondycji rozwiązania** wybierz ikonę **Wyszukiwanie zaawansowane** w prawym górnym rogu strony aplikacji.

5. Na stronie **Wyszukiwanie zaawansowane**, z listy rozwijanej **Wyszukaj** wybierz pozycję **Konfiguracje wirtualnego źródła danych Finanse i Działania**.

   > [!NOTE]
   > Instalacja aplikacji tabel wirtualnych z poprzedniego kroku konfiguracji może potrwać kilka minut. Jeśli na liście nie opcji **Konfiguracje wirtualnego źródła danych Finanse i Działania**, zaczekaj minutę i odśwież listę.

6. Wybierz opcję **Wyniki**.

7. Wybierz rekord **Microsoft HR Data Source**.

8. Wprowadź wymagane informacje dotyczące konfiguracji źródła danych:

   - **Docelowy adres URL**: adres URL obszaru nazw modułu Zasoby ludzkie. Docelowy adres URL ma format:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Na przykład:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Pamiętaj, aby umieścić znak „**/**” na końcu adresu URL, aby uniknąć błędu.

     >[!NOTE]
     >Docelowy adres URL wyznacza środowisko Human Resources, które będą wskazywały dane tabel wirtualnych. Jeśli jest tworzona kopia bieżącego środowiska produkcyjnego jako środowisko piaskownicy, wartość tę należy zmodyfikować na adres URL przestrzeni nazw środowiska piaskownicy. Dzięki temu tabele wirtualne będą połączone z danymi środowiska piaskownicy zamiast wskazywania środowiska produkcyjnego.

   - **Identyfikator dzierżawcy**: identyfikator dzierżawcy Azure Active Directory (Azure AD).

   - **Identyfikator aplikacji w usłudze AAD**: identyfikator aplikacji (klienta) utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure. Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Wpis tajny aplikacji w usłudze AAD**: wpis tajny utworzony dla aplikacji zarejestrowanej w portalu Microsoft Azure. Te informacje uzyskano wcześniej w tym kroku [Rejestracja aplikacji w Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Źródło danych Microsoft HR.](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

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

1. W module Zasoby ludzkie otwórz stronę **Integracja Microsoft Dataverse**.

2. Wybierz kartę **Tabele wirtualne**.

> [!NOTE]
> **Włączenie przełączania tabel wirtualnych** będzie automatycznie ustawiane na wartość **Tak**, gdy wszystkie wymagane ustawienia zostaną zakończone. Jeśli przełącznik ma wartość **Nie**, sprawdź kroki w poprzednich sekcjach tego dokumentu, aby upewnić się, że wszystkie ustawienia wymagań wstępnych zostały zakończone.

3. Wybierz tabelę lub tabele, w których chcesz utworzyć w Dataverse.

4. Wybierz opcję **Generuj/Odśwież**.

![Integracja z usługą Dataverse.](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>Sprawdź stan generacji tabel

Tabele wirtualne są generowane w Dataverse w trakcie asynchronicznego procesu w tle. Aktualizacje w procesie są wyświetlane w centrum akcji. Szczegóły procesu, w tym dzienniki błędów, znajdują się na stronie **Automatyzacja procesów**.

1. W module Human Resources otwórz stronę listy **Automatyzacja procesów**.

2. Wybierz kartę **Procesy w tle**.

3. Wybierz **Proces w tle asynchronicznego sondowania tabeli wirtualnej**.

4. Służy do **Wyświetl ostatnie wyniki**.

W okienku slideout wyświetlane są najnowsze wyniki wykonania procesu. Można przejrzeć dziennik procesu, w tym wszystkie błędy zwrócone przez system Dataverse.

## <a name="see-also"></a>Informacje dodatkowe

[Co to jest usługa Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Tabele w Dataverse](/powerapps/maker/common-data-service/entity-overview)<br>
[Omówienie relacji tabel](/powerapps/maker/common-data-service/relationships-overview)<br>
[Tworzenie i edytowanie tabel wirtualnych zawierających dane z zewnętrznego źródła danych](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Co to są portale Power Apps?](/powerapps/maker/portals/overview)<br>
[Omówienie tworzenia aplikacji w Power Apps](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
