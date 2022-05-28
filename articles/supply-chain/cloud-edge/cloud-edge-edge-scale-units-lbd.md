---
title: Rozmieszczanie jednostek skalowania urządzenia brzegowego na niestandardowym sprzęcie przy użyciu danych LBD
description: W tym temacie opisano sposób ustanawiania lokalnych jednostek skalowania na krawędzi przy użyciu niestandardowego sprzętu i wdrożenia opartego na lokalnych danych biznesowych (LBD).
author: Mirzaab
ms.date: 01/24/2022
ms.topic: article
ms.prod: dynamics-365
ms.service: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 540ac1f6d69d869256f49b8501e18966575903fa
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674094"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Rozmieszczanie jednostek skalowania urządzenia brzegowego na niestandardowym sprzęcie przy użyciu danych LBD

[!include [banner](../includes/banner.md)]

Jednostki skalowania na krawędzi mają znaczenie w dystrybuowanej topologii hybrydowej w aplikacji Supply Chain Management. W topologii hybrydowej można dystrybuować obciążenia między piastą w chmurze Supply Chain Management oraz dodatkowymi jednostkami skalowania w chmurze lub na krawędzi.

Jednostki skalowania na krawędzi można wdrożyć, tworząc lokalne dane biznesowe (LBD) [w środowisku lokalnym](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md), a następnie konfigurując je, aby działały jako jednostka skalowania w dystrybuowanej topologii hybrydowej na potrzeby aplikacji Supply Chain Management. Można to osiągnąć przez skojarzenie lokalnego środowiska LBD ze środowiskiem Supply Chain Management w chmurze, które zostało skonfigurowane do działania jako piasta.  

W tym temacie opisano sposób skonfigurowania lokalnego środowiska LBD jako jednostki skalowania na krawędzi, a następnie skojarzenia go z piastą.

## <a name="infrastructure-considerations"></a>Uwagi dotyczące infrastruktury

Jednostki brzegowe działają w środowisku lokalnym, więc wymagania dotyczące infrastruktury są dość podobne. Należy jednak zwrócić uwagę na pewne różnice:

- Jednostki o skali brzegowej nie korzystają z Financial Reporting, więc nie potrzebują węzłów Financial Reporting.
- Obciążenia produkcyjne i magazynowe nie są intensywne obliczeniowo, więc zastanów się nad odpowiednim doborem mocy obliczeniowej dla węzłów AOS.

## <a name="deployment-overview"></a>Omówienie wdrożenia

Poniżej znajduje się omówienie kroków wdrożenia.

1. **Włącz przedział LBD w projekcie LBD w usługach Microsoft Dynamics Lifecycle Services (LCS).**

1. **Skonfiguruj i rozmieść środowisko LBD z *pustą* bazą danych.**

    Użyj usług LCS, aby rozmieścić środowisko LBD z najnowszą topologią i pustą bazą danych. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie i rozmieszczanie środowiska LBD z pustą bazą danych](#set-up-deploy) w dalszej części tego tematu. Musisz używać aplikacji Supply Chain Management w wersji 10.0.21 lub nowszą w środowiskach piasty i jednostek skalowania.

1. **Przekaż pakiety docelowe do zasobów projektu LBD w usługach LCS.**

    Przygotuj pakiety aplikacji, platformy i dostosowywania, których używasz w piaście i jednostce skalowania na krawędzi. Aby uzyskać więcej informacji, zobacz sekcję [Przekazywanie pakietów docelowych do zasobów projektu LBD w usługach LCS](#upload-packages) w dalszej części tego tematu.

1. **Serwisuj środowisko LBD przy użyciu pakietów docelowych.**

    Dzięki temu krokowi ta sama kompilacja i dostosowywania zostaną rozmieszczone w obrębie piasty i satelity. Aby uzyskać więcej informacji, zobacz sekcję [Serwisowanie środowiska LBD przy użyciu pakietów docelowych](#service-target-packages) w dalszej części tego tematu.

1. **Ukończ konfigurację jednostki skalowania i przypisanie obciążenia.**

    Aby uzyskać więcej informacji, zobacz sekcję [Przypisywanie jednostki skalowania na krawędzi LBD do piasty](#assign-edge-to-hub) w dalszej części tego tematu.

Pozostałe sekcje tego tematu zawierają szczegółowe informacje o wykonywaniu tych kroków.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Konfigurowanie i rozmieszczanie środowiska LBD z pustą bazą danych

Ten krok powoduje utworzenie funkcjonalnego środowiska LBD. Jednak środowisko nie musi mieć tej samej wersji aplikacji i platformy co środowisko piasty. Ponadto nadal brakuje w nim dostosowywania i nie włączono go do pracy jako jednostki skalowania.

1. Wykonaj instrukcje z tematu [Ustawianie i wdrażanie środowisk lokalnych z użyciem aktualizacji Platform update 41 i nowszych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Musisz używać aplikacji Supply Chain Management w wersji 10.0.21 lub nowszą w środowiskach piasty i jednostek skalowania. Ponadto skrypty infrastruktury muszą być w wersji 2.12.0 lub nowszej. 

    > [!IMPORTANT]
    > Przeczytaj pozostałą część tej sekcji **przed** ukończeniem kroków w tym temacie.

1. Przed opisaniem konfiguracji w pliku infrastructure\\ConfigTemplate.xml uruchom następujący skrypt:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Ten skrypt spowoduje usunięcie całej konfiguracji, która nie jest potrzebna do rozmieszczenia jednostek skalowania na krawędzi.

1. Skonfiguruj bazę danych zawierającą puste dane, zgodnie z opisem w temacie [Konfigurowanie baz danych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Użyj pustego pliku data.bak dla tego kroku.
1. Po zakończeniu kroku [Konfigurowanie baz danych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) uruchom następujący skrypt, aby skonfigurować bazę danych Scale Unit Alm Orchestrator.

    > [!NOTE]
    > Nie konfiguruj bazy danych Financial Reporting podczas kroku [Konfigurowanie baz danych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb).

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    Skrypt Initialize-Database.ps1 wykonuje następujące akcje:

    1. Utwórz pustą bazę danych o nazwie **ScaleUnitAlmDb**.
    2. Mapuj użytkowników na role bazy danych na podstawie poniższej tabeli.

        | Użytkownik            | Typ | Rola bazy danych |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | db\_owner     |

1. Wykonaj dalej instrukcje z tematu [Ustawianie i wdrażanie środowisk lokalnych z użyciem aktualizacji Platform update 41 i nowszych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. Po zakończeniu kroku [Konfigurowanie oprogramowania AD FS](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb) należy wykonać następujące czynności:

    1. Utwórz nową aplikację Active Directory Federation Services (AD FS), która umożliwi komunikację usługi Alm Orchestration z serwerem obiektów aplikacji (AOS).

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Utwórz nową aplikację Azure Active Directory (Azure AD), która umożliwi usłudze Alm Orchestration komunikację z usługą Scale Unit Management.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Wykonaj dalej instrukcje z tematu [Ustawianie i wdrażanie środowisk lokalnych z użyciem aktualizacji Platform update 41 i nowszych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Gdy trzeba wprowadzić konfigurację dla lokalnego agenta, należy włączyć funkcje jednostki skalowania krawędzi i podać wszystkie wymagane parametry.

    ![Włączanie funkcji jednostki skali krawędzi.](media/EnableEdgeScaleUnitFeatures.png "Włączanie funkcji jednostki skali krawędzi.")

1. Przed wdrożeniem środowiska z usługi LCS skonfiguruj skrypt wstępnego wdrożenia. Aby uzyskać więcej informacji, zobacz temat [Skrypty przedwdrożeniowe i powdrożeniowe agenta lokalnego](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Skopiuj skrypt Configure-CloudAndEdge.ps1 z folderu **ScaleUnit** w **skryptach infrastruktury** do folderu **Skrypty** w udostępnionym magazynie plików agenta, który został skonfigurowany w środowisku. Typowa ścieżka to \\\\lbdiscsi01\\agent\\Scripts.
    2. Utwórz skrypt **PreDeployment.ps1**, który wywoła skrypty przy użyciu wymaganych parametrów. Skrypt wstępnego wdrożenia musi być umieszczany w folderze **Scripts** w udziale magazynu plików agenta. W przeciwnym razie nie można go uruchomić. Typowa ścieżka to \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Zawartość skryptu PreDeployment.ps1 przypomina poniższy przykład.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        . $PSScriptRoot\Configure-CloudAndEdge.ps1 -AgentShare $agentShare -InstanceId '@A'
        ```

        > [!NOTE]
        > Parametr InstanceId powinien mieć tylko dwa znaki. Pierwszy znak to @, a drugi może być dowolną literą w alfabecie angielskim.
        >
        > - Prawidłowe wartości:
        >   - @D
        >   - @X
        > - Nieprawidłowe wartości:
        >   - @a
        >   - @4
        >   - @#

1. Wdróż środowisko, używając najnowszej dostępnej topologii podstawowej.
1. Po wdrożeniu środowiska wykonaj następujące kroki:

    1. Uruchom następujące polecenia SQL w firmowej bazie danych (AXDB).

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Zwiększ równocześnie maksymalną liczbę sesji przetwarzania wsadowego do wartości większej niż 4.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Sprawdź, czy śledzenie zmian zostało włączone w firmowej bazie danych (AXDB).

        1. Otwórz program SQL Server Management Studio (SSMS).
        1. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) swoją biznesową bazę danych (AXDB), a następnie wybierz **Właściwości**.
        1. W wyświetlonym oknie wybierz **Śledzenie zmian**, a następnie ustaw następujące wartości:

            - **Śledzenie zmian:** *Prawda*
            - **Okres przechowywania:** *7*
            - **Jednostki przechowywania:** *dni*
            - **Automatyczne oczyszczanie:** *Prawda*

    1. Dodaj utworzony wcześniej identyfikator aplikacji AD FS (przy użyciu skryptu Create-ADFSServerApplicationForEdgeScaleUnits.ps1) do tabeli aplikacji usługi Azure AD w jednostce skalowania. Ten krok można wykonać ręcznie za pośrednictwem interfejsu użytkownika. Można je również ukończyć za pośrednictwem bazy danych, korzystając z następującego skryptu.

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a>Skonfiguruj klucz systemu Azure i aplikację Azure AD, aby umożliwić komunikację między jednostkami skali

1. Po wdrożeniu środowiska utwórz dodatkową aplikację Azure AD, aby włączyć zaufaną komunikację między centrum a jednostką skalowania.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. Po utworzeniu aplikacji musisz utworzyć tajny klucz klienta i zapisać informacje w kluczu systemu Azure. Ponadto należy udzielić dostępu do utworzonej aplikacji Azure AD, aby była ona w stanie pobrać plik użytkownika przechowywany w kluczu. Dla zapewnienia wygody poniższy skrypt automatycznie wykona wszystkie wymagane akcje.

    ```powershell
    .\Create-SpokeToHubAADAppSecrets.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                         -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                         -SubscriptionName '<Any subscription within your tenant>' `
                                         -ResourceGroupName '<Any resource group within your subscription>' `
                                         -KeyVaultName '<Any key vault within your resource group>' `
                                         -Location '<Any Azure location where Azure Key Vault is available>' `
                                         -LCSEnvironmentId '<The LCS environment ID of your deployed scale unit>' `
    ```

    > [!NOTE]
    > Jeśli nie istnieje klucz o określonej **wartości KeyVaultName**, skrypt automatycznie je utworzy.

1. Dodaj właśnie utworzony identyfikator aplikacji usługi Azure AD (w przypadku korzystania ze skryptu Create-SpokeToHubAADApplication.ps1) do tabeli aplikacji usługi Azure AD w centrum. Ten krok można wykonać ręcznie za pośrednictwem interfejsu użytkownika.

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Przekaż pakiety docelowe do zasobów projektu LBD w usługach LCS

Ten krok obejmuje przygotowanie wersji aplikacji, wersji platformy i dostosowań, które zostaną przeniesione do środowiska jednostek skalowania LBD.

1. Przekaż ten sam połączony pakiet aplikacji/platformy, który został zastosowany do środowiska piasty do biblioteki zasobów lokalnego projektu usługi LCS.
1. Utwórz kopię niestandardowego pakietu do wdrożenia, który został zastosowany do środowiska piasty i przekaż go do biblioteki zasobów lokalnego projektu usługi LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Serwisuj środowisko LBD przy użyciu pakietów docelowych

Ten krok obejmuje dopasowanie wersji aplikacji, wersji platformy i dostosowań w środowisku jednostek skalowania LBD przy użyciu piasty.

1. Serwisuj środowisko LBD przy użyciu połączonego pakietu aplikacji/platformy, który został przekazany w poprzednim kroku.
1. Serwisuj środowisko LBD przy użyciu niestandardowego pakietu z możliwością wdrożenia, który został przekazany w poprzednim kroku.

    ![Stosowanie aktualizacji w u usługi LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Stosowanie aktualizacji w u usługi LCS")

    ![Wybieranie pakietu dostosowywania.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Wybieranie pakietu dostosowywania")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Przypisz jednostkę skalowania LDB na krawędzi do piasty

Jednostkę skalowania krawędzi można skonfigurować za pomocą portalu zarządzania jednostkami skalowania. Aby uzyskać więcej informacji, zobacz [temat Zarządzanie jednostkami skalowania i obciążeniami za pomocą portalu Menedżer jednostek skalowania.](./cloud-edge-landing-page.md#scale-unit-manager-portal)

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
