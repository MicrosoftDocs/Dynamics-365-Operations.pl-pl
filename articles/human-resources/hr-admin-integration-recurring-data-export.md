---
title: Utwórz cykliczną aplikację eksportu danych
description: W tym artykule przedstawiono sposób tworzenia aplikacji logicznej Microsoft Azure, która eksportuje dane z rozwiązania Microsoft Dynamics 365 Human Resources w harmonogramie cyklicznym.
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
ms.openlocfilehash: edd4b999624a845fc145ed9ff348ae9cba782719
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010160"
---
# <a name="create-a-recurring-data-export-app"></a>Utwórz cykliczną aplikację eksportu danych

W tym artykule przedstawiono sposób tworzenia aplikacji logicznej Microsoft Azure, która eksportuje dane z rozwiązania Microsoft Dynamics 365 Human Resources w harmonogramie cyklicznym. Samouczek korzysta z pakietu usługi DMF zasobów ludzkich REST application programming interface (API), aby wyeksportować dane. Po wyeksportowaniu danych aplikacja logiczna zapisuje wyeksportowany pakiet danych w folderze rozwiązania Microsoft OneDrive for Business.

## <a name="business-scenario"></a>Scenariusz biznesowy

W jednym z typowych scenariuszy biznesowych dla integracji Microsoft Dynamics 365 dane muszą zostać wyeksportowane do systemu podrzędnego w harmonogramie cyklicznym. Ten samouczek przedstawia sposób eksportowania wszystkich rekordów pracowników z rozwiązania Microsoft Dynamics 365 Human Resources i zapisywania listy pracowników w folderze biznesowym OneDrive for Business.

> [!TIP]
> Określone dane eksportowane w tym samouczku oraz miejsce docelowe eksportowanych danych są tylko przykładami. Można je łatwo zmienić, aby spełniały wymagania użytkownika.

## <a name="technologies-used"></a>Używane technologie

W tym samouczku są używane następujące technologie:

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**— Główne źródło danych dla pracowników, które zostanie wyeksportowane.
- **[Aplikacje logiki Azure](https://azure.microsoft.com/services/logic-apps/)** — technologia, która zapewnia aranżację i planowanie eksportu cyklicznego.

    - **[Łączniki](https://docs.microsoft.com/azure/connectors/apis-list)** — technologia używana do łączenia aplikacji logiki z wymaganymi punktami końcowymi.

        - Łącznik [HTTP z Azure AD](https://docs.microsoft.com/connectors/webcontents/)
        - łącznik [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness)

- **[Interfejs REST API w pakiecie DMF](../dev-itpro/data-entities/data-management-api.md)** — technologia używana do wyzwalania eksportu i monitorowania postępu.
- **[OneDrive dla firm](https://onedrive.live.com/about/business/)** — miejsce docelowe dla eksportowanych pracowników.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem wykonywania czynności w tym samouczku należy dysponować następującymi pozycjami:

- Środowisko zasobów ludzkich, które ma uprawnienia na poziomie administratora w środowisku
- [Subskrypcja systemu Azure](https://azure.microsoft.com/free/) do obsługi aplikacji logicznej

## <a name="the-exercise"></a>Ćwiczenie

Na zakończenie tego ćwiczenia będzie dostępna aplikacja logiczna, która jest połączona ze środowiskiem zasobów ludzkich i kontem użytkownika OneDrive for Business. Aplikacja logiczna wyeksportuje pakiet danych z zasobów ludzkich, poczekaj na zakończenie eksportu, Następnie pobierz wyeksportowany pakiet danych i Zapisz pakiet danych w określonym folderze biznesowym OneDrive.

Zakończona aplikacja logiki będzie podobna do poniższej ilustracji.

![Omówienie aplikacji logiki](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>Krok 1: Tworzenie projektu eksportu danych w module Human Resources

Stwórz projekt eksportu danych w module Human Resources, który zaekksportuje pracowników. Nadaj projektowi **Eksport pracowników**nazwę i upewnij się, że opcja **Generuj pakiet danych** ma wartość **Tak**. Dodaj jedną jednostkę (**Pracownik**) do projektu i wybierz format, który ma zostać wyeksportowany. (w tym samouczku jest używany format Microsoft Excel.)

![Projekt danych eksportowanie pracowników](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> Pamiętaj nazwę projektu eksportu tabeli danych. Będzie on potrzebny podczas tworzenia aplikacji logicznej w następnym kroku.

### <a name="step-2-create-the-logic-app"></a>Krok 2: Tworzenie aplikacji logicznej

Większość tego ćwiczenia pociąga za sobą utworzenie aplikacji logicznej.

1. W portalu Azure utwórz aplikację logiczną.

    ![Strona tworzenia aplikacji logicznej](media/integration-logic-app-creation-1.png)

2. W konstruktorze aplikacji logicznych należy rozpocząć od pustej aplikacji logicznej.
3. Dodaj [Wyzwalacz harmonogramu cyklu](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) w celu uruchomienia aplikacji logicznej co 24 godziny (lub zgodnie z wybranym harmonogramem).

    ![Okno dialogowe harmonogramu](media/integration-logic-app-recurrence-step.png)

4. Skontaktuj się z interfejsem API REST [ExportToPackage DMF](../dev-itpro/data-entities/data-management-api.md#exporttopackage), aby zaplanować eksport pakietu danych.

    1. Należy skorzystać z akcji **Wywołania żądania HTTP** z poziomu protokołu HTTP z łącznikiem Azure AD.

        - **Adres URL zasobu podstawowego:** adres URL środowiska Human Resources (nie zawierają informacji o ścieżce/przestrzeni nazw.)
        - **Adres URL zasobu Azure AD:** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > Usługa Human Resoources nie udostępnia jeszcze łącznika, który udostępniałby wszystkie interfejsy API tworzące interfejs API REST pakietu DMF, takie jak **ExportToPackage**. Zamiast tego trzeba wywołać interfejsy API, używając nieprzetworzonych żądań HTTPS za pośrednictwem protokołu HTTP z łącznikiem Azure AD. Ten łącznik używa Azure Active Directory (Azure AD) do uwierzytelniania i autoryzacji dla Human Resources.

        ![HTTP z łącznikiem Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. Zaloguj się do swojego środowiska zasobów ludzkich za pośrednictwem protokołu HTTP z łącznikiem Azure AD.
    3. Skonfiguruj żądanie HTTP **POST** w celu wywołania interfejsu API **ExportToPackage** DMF REST.

        - **Metoda:** POST
        - **Adres URL żądania:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **Zawartość żądania:**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Wywołaj akcję żądania HTTP](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > Można zmienić nazwę każdego kroku, tak aby była bardziej czytelna niż domyślna nazwa, **Wywołaj żądanie HTTP**. Można na przykład zmienić nazwę tego kroku **ExportToPackage**.

5. [Umożliwia zainicjowanie zmiennej](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) w celu zapisania stanu wykonania żądania **ExportToPackage**.

    ![Akcja inicjowania zmiennej](media/integration-logic-app-initialize-variable-step.png)

6. Poczekaj, aż stan wykonania eksportu danych zakończy się **Sukcesem**.

    1. Dodaj [Pętlę until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop), która powtarza się, dopóki wartość zmiennej **ExecutionStatus** nie zakończy się **Sukcesem**.
    2. Dodaj akcję **Opóźnienia**, która czeka pięć sekund przed sondowaniem w poszukiwaniu bieżącego stanu wykonania eksportu.

        ![Kontener Pętli until](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > Należy określić limit na wartość równą **15**, aby czas realizacji eksportu był wykonywany maksymalnie 75 sekund (15 iteracji × 5 sekund). Jeśli eksport trwa dłużej, dostosuj odpowiedni limit.        

    3. Dodaj akcję **Wywołaj żądanie HTTP** w celu wywołania interfejsu API REST DMF [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) i ustaw zmienną **ExecutionStatus** na wynik odpowiedzi **GetExecutionSummaryStatus**.

        > Ta próbka nie sprawdza pod kątem błędów. Interfejs API **GetExecutionSummaryStatus** może zwracać niepomyślne stany terminalowe (to znaczy Stany inne niż **Zakończone pomyślnie**). Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją usług API](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).

        - **Metoda:** POST
        - **Adres URL żądania:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **Treść żądania:** body('Invoke\_an\_HTTP\_request')?['value']

            > [!NOTE]
            > Konieczne może być wprowadzenie **Treści żądania** w widoku kod lub w edytorze funkcji projektanta.

        ![Wywołaj akcję żądania HTTP 2](media/integration-logic-app-get-execution-status-step.png)

        ![Akcja ustawiania zmiennej](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > Wartość dla akcji **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) różni się od wartości treści **Wywołania żądania HTTP o wartości 2**, nawet jeśli projektant wyświetli te wartości w ten sam sposób.

7. Zdobądź link do pobrania wyeksportowanego pakietu.

    - Dodaj akcję **Wywołaj żądanie HTTP** w celu wywołania interfejsu API REST DMF [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).

        - **Metoda:** POST
        - **Adres URL żądania:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **Treść żądania:** {"executionId": body('GetExportedPackageURL')?['value']}

        ![Akcja GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. Pobierz wyeksportowany pakiet.

    - Dodaj żądanie HTTP **GET** (wbudowaną [akcję łącznika HTTP](https://docs.microsoft.com/azure/connectors/connectors-native-http)), aby pobrać pakiet z adresu URL zwróconego w poprzednim kroku.

        - **Metoda:** GET
        - **URI:** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > Konieczne może być wprowadzenie wartości **URL** w widoku kodu lub w edytorze funkcji projektanta.

        ![Akcja HTTP GET](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > To żądanie nie wymaga dodatkowego uwierzytelniania, ponieważ adres URL zwracany przez interfejs API **GetExportedPackageUrl** zawiera token sygnatur dostępu współdzielonego, który przyznaje dostęp do pobierania pliku.

9. Zapisz pobrany pakiet za pomocą łącznika [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness).

    - Dodaj akcję OneDrive for Business: [Tworzenie pliku](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file).
    - W razie potrzeby, połącz się z kontem OneDrive for Business.

        - **Ścieżka folderu:** Wybrany folder
        - **Nazwa pliku:** worker\_package.zip
        - **Zawartość pliku:** treść z poprzedniego kroku (zawartość dynamiczna)

        ![Akcja utwórz plik](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>Krok 3: Testowanie aplikacji logicznej

Aby przetestować aplikację logiczną, wybierz przycisk **Uruchom** w projektancie. Zostaną wyświetlone kolejne kroki aplikacji logicznej. Po 30 do 40 sekundach aplikacja logiczna powinna zakończyć działanie, a OneDrive for Business powinien zawierać nowy plik pakietu zawierający wyeksportowanych pracowników.

Jeśli zgłoszono błąd dla dowolnego kroku, wybierz krok niepowodzenia w Projektancie i sprawdź dla niego pola **Wejściowe** i **Wyjściowe**. Aby poprawić błędy, należy wykonać debugowanie i dostosować krok do wymagań.

Na poniższej ilustracji przedstawiono działanie projektanta aplikacji logicznych, gdy wszystkie kroki aplikacji logicznej są wykonywane pomyślnie.

![Pomyślne uruchomienie aplikacji logicznej](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>Sumarycznie

W tym samouczku przedstawiono sposób użycia aplikacji logicznej do eksportowania danych z modułu zasoby ludzkie i zapisywania eksportowanych danych do folderu OneDrive for Business. Kroki tego samouczka można modyfikować zgodnie z wymaganiami firmy.


