---
title: Rozmieszczanie jednostek skalowania urządzenia brzegowego na niestandardowym sprzęcie przy użyciu danych LBD (wersja zapoznawcza)
description: W tym temacie opisano sposób ustanawiania lokalnych jednostek skalowania na krawędzi przy użyciu niestandardowego sprzętu i wdrożenia opartego na lokalnych danych biznesowych (LBD).
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ebbdaab9d6f040497d3158db2712e102b6e9aa8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678988"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd-preview"></a>Rozmieszczanie jednostek skalowania urządzenia brzegowego na niestandardowym sprzęcie przy użyciu danych LBD (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)] <!--KFM: Until 11/1/2021 -->

Jednostki skalowania na krawędzi mają znaczenie w dystrybuowanej topologii hybrydowej w aplikacji Supply Chain Management. W topologii hybrydowej można dystrybuować obciążenia między piastą w chmurze Supply Chain Management oraz dodatkowymi jednostkami skalowania w chmurze lub na krawędzi.

Jednostki skalowania na krawędzi można wdrożyć, tworząc lokalne dane biznesowe (LBD) [w środowisku lokalnym](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md), a następnie konfigurując je, aby działały jako jednostka skalowania w dystrybuowanej topologii hybrydowej na potrzeby aplikacji Supply Chain Management. Można to osiągnąć przez skojarzenie lokalnego środowiska LBD ze środowiskiem Supply Chain Management w chmurze, które zostało skonfigurowane do działania jako piasta.  

Jednostki skalowana na krawędzi są obecnie dostępne w wersji zapoznawczej. Dlatego środowisko tego typu może być wykorzystywane tylko zgodnie z [postanowieniami dotyczącymi wersji zapoznawczej](https://aka.ms/scmcnepreviewterms).

W tym temacie opisano sposób skonfigurowania lokalnego środowiska LBD jako jednostki skalowania na krawędzi, a następnie skojarzenia go z piastą.

## <a name="deployment-overview"></a>Omówienie wdrożenia

Poniżej znajduje się omówienie kroków wdrożenia.

1. **Włącz przedział LBD w projekcie LBD w usługach Microsoft Dynamics Lifecycle Services (LCS).**

    W okresie wersji zapoznawczej jednostki skalowania na krawędzi LDB są docelowe dla istniejących klientów LBD. Dodatkowy 60-dniowy przedział piaskownicy LDB jest dostępny tylko w określonych sytuacjach.

1. **Skonfiguruj i rozmieść środowisko LBD z *pustą* bazą danych.**

    Użyj usług LCS, aby rozmieścić środowisko LBD z najnowszą topologią i pustą bazą danych. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie i rozmieszczanie środowiska LBD z pustą bazą danych](#set-up-deploy) w dalszej części tego tematu. Musisz używać aplikacji Supply Chain Management w wersji 10.0.19 z aktualizacją platformy 43 lub nowszą w środowiskach piasty i jednostek skalowania.

1. **Przekaż pakiety docelowe do zasobów projektu LBD w usługach LCS.**

    Przygotuj pakiety aplikacji, platformy i dostosowywania, których używasz w piaście i jednostce skalowania na krawędzi. Aby uzyskać więcej informacji, zobacz sekcję [Przekazywanie pakietów docelowych do zasobów projektu LBD w usługach LCS](#upload-packages) w dalszej części tego tematu.

1. **Serwisuj środowisko LBD przy użyciu pakietów docelowych.**

    Dzięki temu krokowi ta sama kompilacja i dostosowywania zostaną rozmieszczone w obrębie piasty i satelity. Aby uzyskać więcej informacji, zobacz sekcję [Serwisowanie środowiska LBD przy użyciu pakietów docelowych](#service-target-packages) w dalszej części tego tematu.

1. **Ukończ konfigurację jednostki skalowania i przypisanie obciążenia.**

    Aby uzyskać więcej informacji, zobacz sekcję [Przypisywanie jednostki skalowania na krawędzi LBD do piasty](#assign-edge-to-hub) w dalszej części tego tematu.

Pozostałe sekcje tego tematu zawierają szczegółowe informacje o wykonywaniu tych kroków.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Konfigurowanie i rozmieszczanie środowiska LBD z pustą bazą danych

Ten krok powoduje utworzenie funkcjonalnego środowiska LBD. Jednak środowisko nie musi mieć tej samej wersji aplikacji i platformy co środowisko piasty. Ponadto nadal brakuje w nim dostosowywania i nie włączono go do pracy jako jednostki skalowania.

1. Wykonaj instrukcje z tematu [Ustawianie i wdrażanie środowisk lokalnych z użyciem aktualizacji Platform update 41 i nowszych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Musisz używać aplikacji Supply Chain Management w wersji 10.0.19 z aktualizacją platformy 43 lub nowszą w środowiskach piasty i jednostek skalowania

    > [!IMPORTANT]
    > Przeczytaj pozostałą część tej sekcji **przed** ukończeniem kroków w tym temacie.

1. Przed opisaniem konfiguracji w pliku infrastructure\\ConfigTemplate.xml uruchom następujący skrypt:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Ten skrypt spowoduje usunięcie całej konfiguracji, która nie jest potrzebna do rozmieszczenia jednostek skalowania na krawędzi.

1. Skonfiguruj bazę danych zawierającą puste dane, zgodnie z opisem w temacie [Konfigurowanie baz danych](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Użyj pustego pliku data.bak dla tego kroku.
1. Skonfiguruj skrypt wstępnego wdrożenia. Aby uzyskać więcej informacji, zobacz temat [Skrypty przedwdrożeniowe i powdrożeniowe agenta lokalnego](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Skopiuj zawartość z folderu **ScaleUnit** w **skryptach infrastruktury** do folderu **Scripts** w udostępnionym magazynie plików agenta, który został skonfigurowany w środowisku. Typowa ścieżka to \\\\lbdiscsi01\\agent\\Scripts.
    2. Utwórz skrypt **PreDeployment.ps1**, który wywoła skrypty przy użyciu wymaganych parametrów. Skrypt wstępnego wdrożenia musi być umieszczany w folderze **Scripts** w udziale magazynu plików agenta. W przeciwnym razie nie można go uruchomić. Typowa ścieżka to \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Zawartość skryptu PreDeployment.ps1 przypomina poniższy przykład.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        & $agentShare\Scripts\Configure-CloudandEdge.ps1 -AgentShare $agentShare -InstanceId '@A' -DatabaseServer 'lbdsqla01.contoso.com' -DatabaseName 'AXDB'
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

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Przekaż pakiety docelowe do zasobów projektu LBD w usługach LCS

Ten krok obejmuje przygotowanie wersji aplikacji, wersji platformy i dostosowań, które zostaną przeniesione do środowiska jednostek skalowania LBD.

1. Przekaż ten sam połączony pakiet aplikacji/platformy, który został zastosowany do środowiska piasty do biblioteki zasobów lokalnego projektu usługi LCS.
1. Utwórz kopię niestandardowego pakietu do wdrożenia, który został zastosowany do środowiska piasty i przekaż go do biblioteki zasobów lokalnego projektu usługi LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Serwisuj środowisko LBD przy użyciu pakietów docelowych

Ten krok obejmuje dopasowanie wersji aplikacji, wersji platformy i dostosowań w środowisku jednostek skalowania LBD przy użyciu piasty.

1. Serwisuj środowisko LBD przy użyciu połączonego pakietu aplikacji/platformy, który został przekazany w poprzednim kroku.
1. Serwisuj środowisko LBD przy użyciu niestandardowego pakietu z możliwością wdrożenia, który został przekazany w poprzednim kroku.

    ![Wybieranie pozycji Obsługa > Zastosuj aktualizacje w usługach LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Wybieranie pozycji Obsługa > Zastosuj aktualizacje w usługach LCS")

    ![Wybieranie pakietu dostosowywania.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Wybieranie pakietu dostosowywania")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Przypisz jednostkę skalowania LDB na krawędzi do piasty

Dopóki jednostki skalowania na krawędzi są nadal dostępne w wersji zapoznawczej, należy użyć [narzędzi wdrażania jednostek skalowania i konfiguracji](https://github.com/microsoft/SCMScaleUnitDevTools) dostępnych w serwisie GitHub, aby przypisać jednostkę skalowania krawędzi LBD do piasty. Proces ten umożliwia funkcję konfiguracji LBD jako jednostki skalowania na krawędzi i kojarzenie jej z piastą. Ten proces jest podobny do konfigurowania środowiska developmentu z jednym polem.

1. Pobierz najnowszą wersję narzędzia [SCMScaleUnitDevTools](https://github.com/microsoft/SCMScaleUnitDevTools/releases) i rozpakuj zawartość pliku.
1. Utwórz kopię pliku `UserConfig.sample.xml` i nadaj jej nazwę `UserConfig.xml`.
1. Utwórz aplikację Microsoft Azure Active Directory (Azure AD) w kliencie Azure AD, tak jak opisano w [Podręczniku wdrażania dla jednostki skalowania i obciążeń](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#aad-application-registrations).
    1. Po utworzeniu przejdź do formularza aplikacji Azure AD (SysAADClientTable) w piaście.
    1. Utwórz nowy wpis i ustaw **identyfikator klienta** jako identyfikator utworzonej aplikacji. Ustaw wartość **Nazwa** na *ScaleUnits*, a **identyfikator użytkownika** na *Administrator*.

1. Utwórz aplikację Active Directory Federation Service (AD FS), tak jak opisano w [Podręczniku wdrażania dla jednostki skalowania i obciążeń](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#adfs-application-registrations).
    1. Po utworzeniu przejdź do formularza aplikacji Azure AD (SysAADClientTable) w jednostce skalowania na krawędzi.
    1. Utwórz nowy wpis i ustaw **identyfikator klienta** jako identyfikator utworzonej aplikacji. Ustaw **Identyfikator użytkownika** na *Administrator*.

1. Zmodyfikuj plik `UserConfig.xml`.
    1. W sekcji `InterAOSAADConfiguration` wprowadź informacje z aplikacji Azure AD utworzonej wcześniej.
        - W elemencie `AppId` wprowadź identyfikator aplikacji platformy Azure.
        - W elemencie `AppSecret` wprowadź wpis tajny aplikacji platformy Azure.
        - Element `Authority` musi zawierać adres URL określający urząd zabezpieczeń dla Twojego dzierżawcy.

        ```xml
        <InterAOSAADConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopty56TGUedDTVhtER-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </InterAOSAADConfiguration>
        ```

    1. W sekcji `ScaleUnitConfiguration`, dla pierwszego elementu `ScaleUnitInstance` zmodyfikuj sekcję `AuthConfiguration`.
        - W elemencie `AppId` wprowadź identyfikator aplikacji platformy Azure.
        - W elemencie `AppSecret` wprowadź wpis tajny aplikacji platformy Azure.
        - Element `Authority` musi zawierać adres URL określający urząd zabezpieczeń dla Twojego dzierżawcy.

        ```xml
        <AuthConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopdz.6d3DTVOtf9Lo-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </AuthConfiguration>
        ```

    1. Dodatkowo dla tego samego elementu `ScaleUnitInstance` ustaw następujące wartości:
        - Określ adres URL piasty w elemencie `Domain`. Na przykład: `https://cloudhub.sandbox.operations.dynamics.com/`
        - Upewnij się, że element `EnvironmentType` ma ustawioną wartość `LCSHosted`.

    1. W sekcji `ScaleUnitConfiguration`, dla drugiego elementu `ScaleUnitInstance` zmodyfikuj sekcję `AuthConfiguration`.
        - W elemencie `AppId` wprowadź identyfikator aplikacji usług AD FS.
        - W elemencie `AppSecret` wprowadź wpis tajny aplikacji usług ADFS.
        - Element `Authority` musi zawierać adres URL wystąpienia usług AD FS.

        ```xml
        <AuthConfiguration>
            <AppId>26b16f25-21d8-4d36-987b-62df292895aa</AppId>
            <AppSecret>iZFfObgI6lLtY9kEbBjEFV98NqI5_YZ0e5SBcWER</AppSecret>
            <Authority>https://adfs.contoso.com/adfs</Authority>
        </AuthConfiguration>
        ```

    1. Dodatkowo dla tego samego elementu `ScaleUnitInstance` ustaw następujące wartości:
        - Określ adres URL jednostki skalowania na krawędzi w elemencie `Domain`. Na przykład: https://ax.contoso.com/
        - Upewnij się, że element `EnvironmentType` ma ustawioną wartość LBD.
        - Wprowadź w elemencie `ScaleUnitId` tę samą wartość, jaką określono dla `InstanceId` podczas konfigurowania skryptu przedwdrożeniowego `Configure-CloudandEdge.ps1`.

        > [!NOTE]
        > Jeśli nie używasz identyfikatora domyślnego (@A), upewnij się, że zaktualizowano identyfikator ScaleUnitId dla każdego elementu ConfiguredWorkload w sekcji obciążeń.

1. Otwórz program PowerShell i przejdź do folderu zawierającego plik `UserConfig.xml`.

1. Uruchom narzędzie za pomocą tego polecenia.

    ```powershell
    .\CLI.exe
    ```

    > [!NOTE]
    > Po każdej akcji należy uruchomić narzędzie ponownie.

1. W narzędziu wybierz opcję **2. Przygotuj środowiska do instalacji obciążeń**. Następnie uruchom następujące kroki:
    1. Wybierz opcję **1. Przygotuj piastę**.
    1. Wybierz opcję **2. Przygotuj jednostkę skalowania**.

    > [!NOTE]
    > Jeśli polecenie nie jest uruchomione z czystej instalacji i wystąpi błąd, należy wykonać następujące czynności:
    >
    > - Usuń wszystkie foldery z folderu `aos-storage` (z wyjątkiem `GACAssemblies`).
    > - Uruchom następujące polecenie SQL w firmowej bazie danych (AXDB):
    >
    > ```sql 
    > delete from storagefoler
    > ```

1. Uruchom następujące polecenia SQL w firmowej bazie danych (AXDB):

    ```sql
    delete from FEATUREMANAGEMENTMETADATA
    delete from FEATUREMANAGEMENTSTATE
    delete from NUMBERSEQUENCESCOPE
    ```

1. Sprawdź, czy śledzenie zmian zostało włączone w firmowej bazie danych (AXDB)
    1. Uruchom program SQL Server Management Studio (SSMS).
    1. Kliknij prawym przyciskiem myszy firmową bazę danych (AXDB) i wybierz właściwości.
    1. W otwartym oknie wybierz opcję **Śledzenie zmian** i określ następujące ustawienia:

        - **Śledzenie zmian:** *Prawda*
        - **Okres przechowywania:** *7*
        - **Jednostki przechowywania:** *dni*
        - **Automatyczne oczyszczanie:** *Prawda*

1. W narzędziu wybierz opcję **3. Instaluj obciążenia**. Następnie uruchom następujące kroki:
    1. Wybierz opcję **1. Instaluj w piaście**.
    1. Wybierz **2. Instaluj w jednostce skalowania**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
