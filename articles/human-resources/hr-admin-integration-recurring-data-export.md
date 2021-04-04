---
title: Utwórz cykliczną aplikację eksportu danych
description: W tym artykule przedstawiono sposób tworzenia aplikacji logicznej Microsoft Azure, która eksportuje dane z rozwiązania Microsoft Dynamics 365 Human Resources w harmonogramie cyklicznym.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 5bc9b5c97f855f1d8eb44765c98473b69f96adec
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466984"
---
# <a name="create-a-recurring-data-export-app"></a><span data-ttu-id="af166-103">Utwórz cykliczną aplikację eksportu danych</span><span class="sxs-lookup"><span data-stu-id="af166-103">Create a recurring data export app</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="af166-104">W tym artykule przedstawiono sposób tworzenia aplikacji logicznej Microsoft Azure, która eksportuje dane z rozwiązania Microsoft Dynamics 365 Human Resources w harmonogramie cyklicznym.</span><span class="sxs-lookup"><span data-stu-id="af166-104">This article shows how to create a Microsoft Azure logic app that exports data from Microsoft Dynamics 365 Human Resources on a recurring schedule.</span></span> <span data-ttu-id="af166-105">Samouczek korzysta z pakietu usługi DMF zasobów ludzkich REST application programming interface (API), aby wyeksportować dane.</span><span class="sxs-lookup"><span data-stu-id="af166-105">The tutorial takes advantage of Human Resources' DMF package REST application programming interface (API) to export the data.</span></span> <span data-ttu-id="af166-106">Po wyeksportowaniu danych aplikacja logiczna zapisuje wyeksportowany pakiet danych w folderze rozwiązania Microsoft OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="af166-106">After the data has been exported, the logic app saves the exported data package to a Microsoft OneDrive for Business folder.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="af166-107">Scenariusz biznesowy</span><span class="sxs-lookup"><span data-stu-id="af166-107">Business scenario</span></span>

<span data-ttu-id="af166-108">W jednym z typowych scenariuszy biznesowych dla integracji Microsoft Dynamics 365 dane muszą zostać wyeksportowane do systemu podrzędnego w harmonogramie cyklicznym.</span><span class="sxs-lookup"><span data-stu-id="af166-108">In one typical business scenario for Microsoft Dynamics 365 integrations, data must be exported to a downstream system on a recurring schedule.</span></span> <span data-ttu-id="af166-109">Ten samouczek przedstawia sposób eksportowania wszystkich rekordów pracowników z rozwiązania Microsoft Dynamics 365 Human Resources i zapisywania listy pracowników w folderze biznesowym OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="af166-109">This tutorial shows how to export all worker records from Microsoft Dynamics 365 Human Resources and save the list of workers in a OneDrive for Business folder.</span></span>

> [!TIP]
> <span data-ttu-id="af166-110">Określone dane eksportowane w tym samouczku oraz miejsce docelowe eksportowanych danych są tylko przykładami.</span><span class="sxs-lookup"><span data-stu-id="af166-110">The specific data that is exported in this tutorial and the destination of the exported data are only examples.</span></span> <span data-ttu-id="af166-111">Można je łatwo zmienić, aby spełniały wymagania użytkownika.</span><span class="sxs-lookup"><span data-stu-id="af166-111">You can easily change them to meet your business needs.</span></span>

## <a name="technologies-used"></a><span data-ttu-id="af166-112">Używane technologie</span><span class="sxs-lookup"><span data-stu-id="af166-112">Technologies used</span></span>

<span data-ttu-id="af166-113">W tym samouczku są używane następujące technologie:</span><span class="sxs-lookup"><span data-stu-id="af166-113">This tutorial uses the following technologies:</span></span>

- <span data-ttu-id="af166-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**— Główne źródło danych dla pracowników, które zostanie wyeksportowane.</span><span class="sxs-lookup"><span data-stu-id="af166-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – The master data source for workers that will be exported.</span></span>
- <span data-ttu-id="af166-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** — technologia, która zapewnia aranżację i planowanie eksportu cyklicznego.</span><span class="sxs-lookup"><span data-stu-id="af166-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – The technology that provides orchestration and scheduling of the recurring export.</span></span>

    - <span data-ttu-id="af166-116">**[Łączniki](https://docs.microsoft.com/azure/connectors/apis-list)** — technologia używana do łączenia aplikacji logiki z wymaganymi punktami końcowymi.</span><span class="sxs-lookup"><span data-stu-id="af166-116">**[Connectors](https://docs.microsoft.com/azure/connectors/apis-list)** – The technology that is used to connect the logic app to the required endpoints.</span></span>

        - <span data-ttu-id="af166-117">Łącznik [HTTP z Azure AD](https://docs.microsoft.com/connectors/webcontents/)</span><span class="sxs-lookup"><span data-stu-id="af166-117">[HTTP with Azure AD](https://docs.microsoft.com/connectors/webcontents/) connector</span></span>
        - <span data-ttu-id="af166-118">łącznik [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness)</span><span class="sxs-lookup"><span data-stu-id="af166-118">[OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector</span></span>

- <span data-ttu-id="af166-119">**[Interfejs REST API w pakiecie DMF](../dev-itpro/data-entities/data-management-api.md)** — technologia używana do wyzwalania eksportu i monitorowania postępu.</span><span class="sxs-lookup"><span data-stu-id="af166-119">**[DMF package REST API](../dev-itpro/data-entities/data-management-api.md)** – The technology that is used to trigger the export and monitor its progress.</span></span>
- <span data-ttu-id="af166-120">**[OneDrive dla firm](https://onedrive.live.com/about/business/)** — miejsce docelowe dla eksportowanych pracowników.</span><span class="sxs-lookup"><span data-stu-id="af166-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – The destination for the exported workers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af166-121">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="af166-121">Prerequisites</span></span>

<span data-ttu-id="af166-122">Przed rozpoczęciem wykonywania czynności w tym samouczku należy dysponować następującymi pozycjami:</span><span class="sxs-lookup"><span data-stu-id="af166-122">Before you begin the exercise in this tutorial, you must have the following items:</span></span>

- <span data-ttu-id="af166-123">Środowisko zasobów ludzkich, które ma uprawnienia na poziomie administratora w środowisku</span><span class="sxs-lookup"><span data-stu-id="af166-123">A Human Resources environment that has admin-level permissions in the environment</span></span>
- <span data-ttu-id="af166-124">[Subskrypcja systemu Azure](https://azure.microsoft.com/free/) do obsługi aplikacji logicznej</span><span class="sxs-lookup"><span data-stu-id="af166-124">An [Azure subscription](https://azure.microsoft.com/free/) to host the logic app</span></span>

## <a name="the-exercise"></a><span data-ttu-id="af166-125">Ćwiczenie</span><span class="sxs-lookup"><span data-stu-id="af166-125">The exercise</span></span>

<span data-ttu-id="af166-126">Na zakończenie tego ćwiczenia będzie dostępna aplikacja logiczna, która jest połączona ze środowiskiem zasobów ludzkich i kontem użytkownika OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="af166-126">At the end of this exercise, you will have a logic app that is connected to your Human Resources environment and your OneDrive for Business account.</span></span> <span data-ttu-id="af166-127">Aplikacja logiczna wyeksportuje pakiet danych z zasobów ludzkich, poczekaj na zakończenie eksportu, Następnie pobierz wyeksportowany pakiet danych i Zapisz pakiet danych w określonym folderze biznesowym OneDrive.</span><span class="sxs-lookup"><span data-stu-id="af166-127">The logic app will export a data package from Human Resources, wait for the export to be completed, download the exported data package, and save the data package in the OneDrive for Business folder that you specified.</span></span>

<span data-ttu-id="af166-128">Zakończona aplikacja logiki będzie podobna do poniższej ilustracji.</span><span class="sxs-lookup"><span data-stu-id="af166-128">The completed logic app will resemble the following illustration.</span></span>

![Omówienie aplikacji logiki](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a><span data-ttu-id="af166-130">Krok 1: Tworzenie projektu eksportu danych w module Human Resources</span><span class="sxs-lookup"><span data-stu-id="af166-130">Step 1: Create a data export project in Human Resources</span></span>

<span data-ttu-id="af166-131">Stwórz projekt eksportu danych w module Human Resources, który zaekksportuje pracowników.</span><span class="sxs-lookup"><span data-stu-id="af166-131">In Human Resources, create a data export project that exports workers.</span></span> <span data-ttu-id="af166-132">Nadaj projektowi **Eksport pracowników** nazwę i upewnij się, że opcja **Generuj pakiet danych** ma wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="af166-132">Name the project **Export Workers**, and make sure that the **Generate data package** option is set to **Yes**.</span></span> <span data-ttu-id="af166-133">Dodaj jedną jednostkę (**Pracownik**) do projektu i wybierz format, który ma zostać wyeksportowany.</span><span class="sxs-lookup"><span data-stu-id="af166-133">Add a single entity (**Worker**) to the project, and select the format to export in.</span></span> <span data-ttu-id="af166-134">(w tym samouczku jest używany format Microsoft Excel.)</span><span class="sxs-lookup"><span data-stu-id="af166-134">(Microsoft Excel format is used in this tutorial.)</span></span>

![Projekt danych eksportowanie pracowników](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> <span data-ttu-id="af166-136">Pamiętaj nazwę projektu eksportu tabeli danych.</span><span class="sxs-lookup"><span data-stu-id="af166-136">Remember the name of the data export project.</span></span> <span data-ttu-id="af166-137">Będzie on potrzebny podczas tworzenia aplikacji logicznej w następnym kroku.</span><span class="sxs-lookup"><span data-stu-id="af166-137">You will need it when you create the logic app in the next step.</span></span>

### <a name="step-2-create-the-logic-app"></a><span data-ttu-id="af166-138">Krok 2: Tworzenie aplikacji logicznej</span><span class="sxs-lookup"><span data-stu-id="af166-138">Step 2: Create the logic app</span></span>

<span data-ttu-id="af166-139">Większość tego ćwiczenia pociąga za sobą utworzenie aplikacji logicznej.</span><span class="sxs-lookup"><span data-stu-id="af166-139">The bulk of the exercise involves creating the logic app.</span></span>

1. <span data-ttu-id="af166-140">W portalu Azure utwórz aplikację logiczną.</span><span class="sxs-lookup"><span data-stu-id="af166-140">In the Azure portal, create a logic app.</span></span>

    ![Strona tworzenia aplikacji logicznej](media/integration-logic-app-creation-1.png)

2. <span data-ttu-id="af166-142">W programie Logic Apps Designer należy rozpocząć od pustej aplikacji logicznej.</span><span class="sxs-lookup"><span data-stu-id="af166-142">In the Logic Apps Designer, start with a blank logic app.</span></span>
3. <span data-ttu-id="af166-143">Dodaj [Wyzwalacz harmonogramu cyklu](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) w celu uruchomienia aplikacji logicznej co 24 godziny (lub zgodnie z wybranym harmonogramem).</span><span class="sxs-lookup"><span data-stu-id="af166-143">Add a [Recurrence Schedule trigger](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) to run the logic app every 24 hours (or according to a schedule of your choice).</span></span>

    ![Okno dialogowe harmonogramu](media/integration-logic-app-recurrence-step.png)

4. <span data-ttu-id="af166-145">Skontaktuj się z interfejsem API REST [ExportToPackage DMF](../dev-itpro/data-entities/data-management-api.md#exporttopackage), aby zaplanować eksport pakietu danych.</span><span class="sxs-lookup"><span data-stu-id="af166-145">Call the [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API to schedule the export of your data package.</span></span>

    1. <span data-ttu-id="af166-146">Należy skorzystać z akcji **Wywołania żądania HTTP** z poziomu protokołu HTTP z łącznikiem Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af166-146">Use the **Invoke an HTTP request** action from the HTTP with Azure AD connector.</span></span>

        - <span data-ttu-id="af166-147">**Adres URL zasobu podstawowego:** adres URL środowiska Human Resources (nie zawierają informacji o ścieżce/przestrzeni nazw.)</span><span class="sxs-lookup"><span data-stu-id="af166-147">**Base Resource URL:** The URL of your Human Resources environment (Don't include path/namespace information.)</span></span>
        - <span data-ttu-id="af166-148">**Adres URL zasobu Azure AD:** `http://hr.talent.dynamics.com`</span><span class="sxs-lookup"><span data-stu-id="af166-148">**Azure AD Resource URI:** `http://hr.talent.dynamics.com`</span></span>

        > [!NOTE]
        > <span data-ttu-id="af166-149">Usługa Human Resoources nie udostępnia jeszcze łącznika, który udostępniałby wszystkie interfejsy API tworzące interfejs API REST pakietu DMF, takie jak **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="af166-149">The Human Resources service doesn't yet provide a connector that exposes all the APIs that make up the DMF package REST API, such as **ExportToPackage**.</span></span> <span data-ttu-id="af166-150">Zamiast tego trzeba wywołać interfejsy API, używając nieprzetworzonych żądań HTTPS za pośrednictwem protokołu HTTP z łącznikiem Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af166-150">Instead, you must call the APIs by using raw HTTPS requests through the HTTP with Azure AD connector.</span></span> <span data-ttu-id="af166-151">Ten łącznik używa Azure Active Directory (Azure AD) do uwierzytelniania i autoryzacji dla Human Resources.</span><span class="sxs-lookup"><span data-stu-id="af166-151">This connector uses Azure Active Directory (Azure AD) for authentication and authorization to Human Resources.</span></span>

        ![HTTP z łącznikiem Azure AD](media/integration-logic-app-http-aad-connector-step.png)

    2. <span data-ttu-id="af166-153">Zaloguj się do swojego środowiska zasobów ludzkich za pośrednictwem protokołu HTTP z łącznikiem Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af166-153">Sign in to your Human Resources environment through the HTTP with Azure AD connector.</span></span>
    3. <span data-ttu-id="af166-154">Skonfiguruj żądanie HTTP **POST** w celu wywołania interfejsu API **ExportToPackage** DMF REST.</span><span class="sxs-lookup"><span data-stu-id="af166-154">Set up an HTTP **POST** request to call the **ExportToPackage** DMF REST API.</span></span>

        - <span data-ttu-id="af166-155">**Metoda:** POST</span><span class="sxs-lookup"><span data-stu-id="af166-155">**Method:** POST</span></span>
        - <span data-ttu-id="af166-156">**Adres URL żądania:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span><span class="sxs-lookup"><span data-stu-id="af166-156">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span></span>
        - <span data-ttu-id="af166-157">**Zawartość żądania:**</span><span class="sxs-lookup"><span data-stu-id="af166-157">**Body of the request:**</span></span>

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
    > <span data-ttu-id="af166-159">Można zmienić nazwę każdego kroku, tak aby była bardziej czytelna niż domyślna nazwa, **Wywołaj żądanie HTTP**.</span><span class="sxs-lookup"><span data-stu-id="af166-159">You might want to rename each step so that it's more meaningful than the default name, **Invoke an HTTP request**.</span></span> <span data-ttu-id="af166-160">Można na przykład zmienić nazwę tego kroku **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="af166-160">For example, you can rename this step **ExportToPackage**.</span></span>

5. <span data-ttu-id="af166-161">[Umożliwia zainicjowanie zmiennej](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) w celu zapisania stanu wykonania żądania **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="af166-161">[Initialize a variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) to store the execution status of the **ExportToPackage** request.</span></span>

    ![Akcja inicjowania zmiennej](media/integration-logic-app-initialize-variable-step.png)

6. <span data-ttu-id="af166-163">Poczekaj, aż stan wykonania eksportu danych zakończy się **Sukcesem**.</span><span class="sxs-lookup"><span data-stu-id="af166-163">Wait until the execution status of the data export is **Succeeded**.</span></span>

    1. <span data-ttu-id="af166-164">Dodaj [Pętlę until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop), która powtarza się, dopóki wartość zmiennej **ExecutionStatus** nie zakończy się **Sukcesem**.</span><span class="sxs-lookup"><span data-stu-id="af166-164">Add an [Until loop](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) that repeats until the value of the **ExecutionStatus** variable is **Succeeded**.</span></span>
    2. <span data-ttu-id="af166-165">Dodaj akcję **Opóźnienia**, która czeka pięć sekund przed sondowaniem w poszukiwaniu bieżącego stanu wykonania eksportu.</span><span class="sxs-lookup"><span data-stu-id="af166-165">Add a **Delay** action that waits five seconds before it polls for the current execution status of the export.</span></span>

        ![Kontener Pętli until](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > <span data-ttu-id="af166-167">Należy określić limit na wartość równą **15**, aby czas realizacji eksportu był wykonywany maksymalnie 75 sekund (15 iteracji × 5 sekund).</span><span class="sxs-lookup"><span data-stu-id="af166-167">Set the limit count to **15** to wait a maximum of 75 seconds (15 iterations × 5 seconds) for the export to be completed.</span></span> <span data-ttu-id="af166-168">Jeśli eksport trwa dłużej, dostosuj odpowiedni limit.</span><span class="sxs-lookup"><span data-stu-id="af166-168">If your export takes more time, adjust the limit count as appropriate.</span></span>        

    3. <span data-ttu-id="af166-169">Dodaj akcję **Wywołaj żądanie HTTP** w celu wywołania interfejsu API REST DMF [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) i ustaw zmienną **ExecutionStatus** na wynik odpowiedzi **GetExecutionSummaryStatus**.</span><span class="sxs-lookup"><span data-stu-id="af166-169">Add an **Invoke HTTP request** action to call the [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, and set the **ExecutionStatus** variable to the result of the **GetExecutionSummaryStatus** response.</span></span>

        > <span data-ttu-id="af166-170">Ta próbka nie sprawdza pod kątem błędów.</span><span class="sxs-lookup"><span data-stu-id="af166-170">This sample doesn't do error checking.</span></span> <span data-ttu-id="af166-171">Interfejs API **GetExecutionSummaryStatus** może zwracać niepomyślne stany terminalowe (to znaczy Stany inne niż **Zakończone pomyślnie**).</span><span class="sxs-lookup"><span data-stu-id="af166-171">The **GetExecutionSummaryStatus** API can return non-successful terminal states (that is, states other than **Succeeded**).</span></span> <span data-ttu-id="af166-172">Aby uzyskać więcej informacji, zapoznaj się z [dokumentacją usług API](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span><span class="sxs-lookup"><span data-stu-id="af166-172">For more information, see the [API documentation](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span></span>

        - <span data-ttu-id="af166-173">**Metoda:** POST</span><span class="sxs-lookup"><span data-stu-id="af166-173">**Method:** POST</span></span>
        - <span data-ttu-id="af166-174">**Adres URL żądania:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span><span class="sxs-lookup"><span data-stu-id="af166-174">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span></span>
        - <span data-ttu-id="af166-175">**Treść żądania:** body('Invoke\_an\_HTTP\_request')?['value']</span><span class="sxs-lookup"><span data-stu-id="af166-175">**Body of the request:** body('Invoke\_an\_HTTP\_request')?['value']</span></span>

            > [!NOTE]
            > <span data-ttu-id="af166-176">Konieczne może być wprowadzenie **Treści żądania** w widoku kod lub w edytorze funkcji projektanta.</span><span class="sxs-lookup"><span data-stu-id="af166-176">You might have to enter the **Body of the request** value either in code view or in the function editor in the designer.</span></span>

        ![Wywołaj akcję żądania HTTP 2](media/integration-logic-app-get-execution-status-step.png)

        ![Akcja ustawiania zmiennej](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > <span data-ttu-id="af166-179">Wartość dla akcji **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) różni się od wartości treści **Wywołania żądania HTTP o wartości 2**, nawet jeśli projektant wyświetli te wartości w ten sam sposób.</span><span class="sxs-lookup"><span data-stu-id="af166-179">The value for the **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) will differ from the value for the **Invoke an HTTP request 2** body value, even though the designer will show the values in the same way.</span></span>

7. <span data-ttu-id="af166-180">Zdobądź link do pobrania wyeksportowanego pakietu.</span><span class="sxs-lookup"><span data-stu-id="af166-180">Get the download URL of the exported package.</span></span>

    - <span data-ttu-id="af166-181">Dodaj akcję **Wywołaj żądanie HTTP** w celu wywołania interfejsu API REST DMF [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).</span><span class="sxs-lookup"><span data-stu-id="af166-181">Add an **Invoke HTTP request** action to call the [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span></span>

        - <span data-ttu-id="af166-182">**Metoda:** POST</span><span class="sxs-lookup"><span data-stu-id="af166-182">**Method:** POST</span></span>
        - <span data-ttu-id="af166-183">**Adres URL żądania:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span><span class="sxs-lookup"><span data-stu-id="af166-183">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span></span>
        - <span data-ttu-id="af166-184">**Treść żądania:** {"executionId": body('GetExportedPackageURL')?['value']}</span><span class="sxs-lookup"><span data-stu-id="af166-184">**Body of the request:** {"executionId": body('GetExportedPackageURL')?['value']}</span></span>

        ![Akcja GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. <span data-ttu-id="af166-186">Pobierz wyeksportowany pakiet.</span><span class="sxs-lookup"><span data-stu-id="af166-186">Download the exported package.</span></span>

    - <span data-ttu-id="af166-187">Dodaj żądanie HTTP **GET** (wbudowaną [akcję łącznika HTTP](https://docs.microsoft.com/azure/connectors/connectors-native-http)), aby pobrać pakiet z adresu URL zwróconego w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="af166-187">Add an HTTP **GET** request (a built-in [HTTP connector action](https://docs.microsoft.com/azure/connectors/connectors-native-http)) to download the package from the URL that was returned in the previous step.</span></span>

        - <span data-ttu-id="af166-188">**Metoda:** GET</span><span class="sxs-lookup"><span data-stu-id="af166-188">**Method:** GET</span></span>
        - <span data-ttu-id="af166-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span><span class="sxs-lookup"><span data-stu-id="af166-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span></span>

            > [!NOTE]
            > <span data-ttu-id="af166-190">Konieczne może być wprowadzenie wartości **URL** w widoku kodu lub w edytorze funkcji projektanta.</span><span class="sxs-lookup"><span data-stu-id="af166-190">You might have to enter the **URI** value either in code view or in the function editor in the designer.</span></span>

        ![Akcja HTTP GET](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > <span data-ttu-id="af166-192">To żądanie nie wymaga dodatkowego uwierzytelniania, ponieważ adres URL zwracany przez interfejs API **GetExportedPackageUrl** zawiera token sygnatur dostępu współdzielonego, który przyznaje dostęp do pobierania pliku.</span><span class="sxs-lookup"><span data-stu-id="af166-192">This request doesn't require any additional authentication, because the URL that the **GetExportedPackageUrl** API returns includes a shared access signatures token that grants access to download the file.</span></span>

9. <span data-ttu-id="af166-193">Zapisz pobrany pakiet za pomocą łącznika [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness).</span><span class="sxs-lookup"><span data-stu-id="af166-193">Save the downloaded package by using the [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector.</span></span>

    - <span data-ttu-id="af166-194">Dodaj akcję OneDrive for Business: [Tworzenie pliku](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file).</span><span class="sxs-lookup"><span data-stu-id="af166-194">Add a OneDrive for Business [Create File](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) action.</span></span>
    - <span data-ttu-id="af166-195">W razie potrzeby, połącz się z kontem OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="af166-195">Connect to your OneDrive for Business account, as required.</span></span>

        - <span data-ttu-id="af166-196">**Ścieżka folderu:** Wybrany folder</span><span class="sxs-lookup"><span data-stu-id="af166-196">**Folder Path:** A folder of your choice</span></span>
        - <span data-ttu-id="af166-197">**Nazwa pliku:** worker\_package.zip</span><span class="sxs-lookup"><span data-stu-id="af166-197">**File Name:** worker\_package.zip</span></span>
        - <span data-ttu-id="af166-198">**Zawartość pliku:** treść z poprzedniego kroku (zawartość dynamiczna)</span><span class="sxs-lookup"><span data-stu-id="af166-198">**File Content:** The body from the previous step (dynamic content)</span></span>

        ![Akcja utwórz plik](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a><span data-ttu-id="af166-200">Krok 3: Testowanie aplikacji logicznej</span><span class="sxs-lookup"><span data-stu-id="af166-200">Step 3: Test the logic app</span></span>

<span data-ttu-id="af166-201">Aby przetestować aplikację logiczną, wybierz przycisk **Uruchom** w projektancie.</span><span class="sxs-lookup"><span data-stu-id="af166-201">To test your logic app, select the **Run** button in the designer.</span></span> <span data-ttu-id="af166-202">Zostaną wyświetlone kolejne kroki aplikacji logicznej.</span><span class="sxs-lookup"><span data-stu-id="af166-202">You will see that the steps of the logic app start to run.</span></span> <span data-ttu-id="af166-203">Po 30 do 40 sekundach aplikacja logiczna powinna zakończyć działanie, a OneDrive for Business powinien zawierać nowy plik pakietu zawierający wyeksportowanych pracowników.</span><span class="sxs-lookup"><span data-stu-id="af166-203">After 30 to 40 seconds, the logic app should finish running, and your OneDrive for Business folder should include a new package file that contains the exported workers.</span></span>

<span data-ttu-id="af166-204">Jeśli zgłoszono błąd dla dowolnego kroku, wybierz krok niepowodzenia w Projektancie i sprawdź dla niego pola **Wejściowe** i **Wyjściowe**.</span><span class="sxs-lookup"><span data-stu-id="af166-204">If a failure is reported for any step, select the failed step in the designer, and examine the **Inputs** and **Outputs** fields for it.</span></span> <span data-ttu-id="af166-205">Aby poprawić błędy, należy wykonać debugowanie i dostosować krok do wymagań.</span><span class="sxs-lookup"><span data-stu-id="af166-205">Debug and adjust the step as required to correct the errors.</span></span>

<span data-ttu-id="af166-206">Na poniższej ilustracji przedstawiono działanie programu Logic Apps Designer, gdy wszystkie kroki aplikacji logicznej są wykonywane pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="af166-206">The following illustration shows what the Logic Apps Designer looks like when all the steps of the logic app run successfully.</span></span>

![Pomyślne uruchomienie aplikacji logicznej](media/integration-logic-app-successful-run.png)

## <a name="summary"></a><span data-ttu-id="af166-208">Sumarycznie</span><span class="sxs-lookup"><span data-stu-id="af166-208">Summary</span></span>

<span data-ttu-id="af166-209">W tym samouczku przedstawiono sposób użycia aplikacji logicznej do eksportowania danych z modułu zasoby ludzkie i zapisywania eksportowanych danych do folderu OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="af166-209">In this tutorial, you learned how to use a logic app to export data from Human Resources and save the exported data to a OneDrive for Business folder.</span></span> <span data-ttu-id="af166-210">Kroki tego samouczka można modyfikować zgodnie z wymaganiami firmy.</span><span class="sxs-lookup"><span data-stu-id="af166-210">You can modify the steps of this tutorial as required to suit your business needs.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]