---
title: Konfigurowanie dodatku Widoczność magazynu
description: W tym temacie opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8573fe01abb1c6092012baf85e8b7df40b74a31f
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343591"
---
# <a name="set-up-inventory-visibility"></a>Konfigurowanie dodatku Widoczność magazynu

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

W tym temacie opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Microsoft Dynamics 365 Supply Chain Management.

Musisz korzystać z Microsoft Dynamics Lifecycle Services (LCS), aby zainstalować dodatek Widoczność magazynu. LCS to portal współpracy, który zapewnia środowisko i zbiór regularnie zaktualizowanych usług ułatwiających zarządzanie cyklem życia aplikacji w aplikacjach Finance and Operations.

Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Wymagania wstępne dodatku Widoczność magazynu

Aby można było zainstalować dodatek Widoczność magazynu, musisz wykonać następujące zadania:

- Uzyskaj projekt implementacji usługi LCS z co najmniej jednym wdrożonym środowiskiem.
- Upewnij się, że wymagania wstępne konfigurowania dodatków są spełnione. Więcej informacji o tych wymaganiach wstępnych zawiera temat [Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Widoczność zapasów nie wymaga podwójnego łączenia.
- Skontaktuj się z zespołem produktu Widoczność magazynu pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) aby uzyskać następujące wymagane pliki:

    - `InventoryServiceApplication.PackageDeployer.zip`
    - `Inventory Visibility Integration.zip` (jeśli uruchomiona wersja Supply Chain Management jest wcześniejsza niż 10.0.18)

> [!NOTE]
> Aktualnie obsługiwane kraje i regiony to Kanada (CCA, ECA), Stany Zjednoczone (WUS, EUS), Unia Europejska (NEU, WEU), Wielka Brytania (SUK, WUK) i Australia (EAU, SEAU).

Jeśli masz pytania dotyczące tych wymagań wstępnych, skontaktuj się z zespołem ds. produktu Widoczność magazynu.

## <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Ustaw Dataverse

W celu korzystania z Dataverse w połączeniu z dodatkiem Widoczność magazynu należy wdrożyć pakiet Widoczność magazynu przy użyciu narzędzia Package Deployer. W poniższych podrozdziałach opisano, jak wykonać poszczególne zadania.

> [!NOTE]
> Obecnie są obsługiwane tylko środowiska Dataverse utworzone za pomocą usługi LCS. Jeśli środowisko Dataverse zostało utworzone w inny sposób (na przykład za pomocą centrum administracyjnego Power Apps) i jest połączone ze środowiskiem Supply Chain Management, należy najpierw skontaktować się z zespołem ds. produktu Widoczność magazynu, aby rozwiązać ten problem z mapowaniem. Następnie można zainstalować dodatek Widoczność magazynu.

### <a name="migrate-from-an-old-version-of-the-dataverse-solution"></a>Migrowanie ze starej wersji rozwiązania Dataverse

Jeśli zainstalowano starszą wersję dodatku Widoczność magazynu rozwiązania Dataverse, należy skorzystać z poniższych instrukcji, aby zaktualizować tę wersję. Istnieją dwa przypadki:

- **Przypadek 1:** Jeśli ręcznie skonfigurujesz Dataverse, importując rozwiązanie `Inventory Visibility Dataverse Solution_1_0_0_2_managed.zip`, wykonaj następujące kroki:

    1. Pobierz następujące trzy pliki:

        - `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip`
        - `InventoryServiceBase_managed.cab`
        - `InventoryServiceApplication.PackageDeployer.zip`

    1. Ręcznie zaimportuj `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip` i `InventoryServiceBase_managed.cab` do Dataverse, wykonując następujące kroki:

        1. Otwórz adres URL środowiska Dataverse.
        1. Otwórz stronę **Rozwiązania**.
        1. Wybierz opcję **Importuj**.

    1. Użyj narzędzia Package Deployer, aby wdrożyć pakiet `InventoryServiceApplication.PackageDeployer.zip`. Stosowne instrukcje zawiera sekcja [Wdrażanie pakietu przy użyciu narzędzia Package Deployer](#deploy-package) w tym temacie.

- **Przypadek 2:** Jeśli Dataverse skonfigurowano przy użyciu narzędzia Package Deployer przed zainstalowaniem starszego pakietu `.*PackageDeployer.zip`, pobierz `InventoryServiceApplication.PackageDeployer.zip` i wykonaj aktualizację. Stosowne instrukcje zawiera sekcja [Wdrażanie pakietu przy użyciu narzędzia Package Deployer](#deploy-package).

### <a name="use-the-package-deployer-tool-to-deploy-the-package"></a><a name="deploy-package"></a>Wdrażanie pakietu przy użyciu narzędzia Package Deployer

1. Zainstaluj narzędzia deweloperskie zgodnie z opisem na stronie [Pobieranie narzędzi z NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).
1. Odblokuj plik `InventoryServiceApplication.PackageDeployer.zip` pobrany z grupy Teams, wykonując następujące kroki:

    1. Zaznacz plik i przytrzymaj go (lub kliknij prawym przyciskiem myszy), a następnie wybierz opcję **Właściwości**.
    1. W oknie dialogowym **Właściwości** na karcie **Ogólne** znajdź sekcję **Zabezpieczenia**, wybierz pozycję **Odblokuj** i zastosuj zmianę. Jeśli na karcie **Ogólne** nie ma sekcji **Zabezpieczenia**, plik nie jest zablokowany. W takim przypadku przejdź do następnego kroku.

    ![Odblokowywanie pobranego pliku](media/unblock-file.png "Odblokowywanie pobranego pliku")

1. Rozpakuj plik `InventoryServiceApplication.PackageDeployer.zip`, aby znaleźć następujące elementy:

    - Folder programu `InventoryServiceApplication`
    - Plik `[Content_Types].xml`
    - Plik `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`

1. Skopiuj te elementy do katalogu `.\Tools\PackageDeployment`. (Ten katalog został utworzony po zainstalowaniu narzędzi deweloperskich).
1. Uruchom plik `.\Tools\PackageDeployment\PackageDeployer.exe` i postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby zaimportować rozwiązania.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalowanie dodatku Widoczność magazynu

Przed zainstalowaniem tego dodatku zarejestruj aplikację i dodaj klucz tajny klienta do Azure Active Directory (Azure AD) w swojej subskrypcji Azure. Stosowne instrukcje zawierają tematy [Rejestrowanie aplikacji](/azure/active-directory/develop/quickstart-register-app) i [Dodawanie klucza tajnego klienta](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Pamiętaj o zanotowaniu wartości pól **Identyfikator aplikacji (klienta)**, **Klucz tajny klienta** i **Identyfikator dzierżawy**, ponieważ będą potrzebne później.

Po zarejestrowaniu aplikacji i dodaniu klucza tajnego klienta do Azure AD wykonaj następujące kroki, aby zainstalować dodatek Widoczność magazynu.

1. Zaloguj się w [LCS](https://lcs.dynamics.com/Logon/Index).
1. Na stronie głównej wybierz projekt, w którym jest wdrożone środowisko.
1. Na stronie projektu wybierz środowisko, w którym chcesz zainstalować dodatek.
1. Przewijaj stronę środowiska w dół do momentu, aż znajdziesz sekcję **Dodatki środowiska** w sekcji **Integracja Power Platform**. Tam znajdziesz nazwę środowiska Dataverse.
1. W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.

    ![Strona środowiska w LCS](media/inventory-visibility-environment.png "Strona środowiska w LCS")

1. Wybierz opcję **Zainstaluj nowy dodatek**. Zostanie otwarta lista dostępnych dodatków.
1. Z listy wybierz opcję **Widoczność magazynu**.
1. Ustaw następujące pola dla swojego środowiska:

    - **Identyfikator aplikacji AAD (klienta)** — wprowadź utworzony i zanotowany wcześniej identyfikator aplikacji Azure AD.
    - **Identyfikator dzierżawy AAD** — wprowadź identyfikator dzierżawy zanotowany wcześniej.

    ![Strona konfiguracji dodatku](media/inventory-visibility-setup.png "Strona konfiguracji dodatku")

1. Zaakceptuj regulamin, zaznaczając pole wyboru **Regulamin**.
1. Wybierz **Zainstaluj**. Stan dodatku będzie widoczny jako **Instalowany**. Po zakończeniu instalacji odśwież stronę. Stan powinien zostać zmieniony na **Zainstalowany**.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Odinstalowywanie dodatku Widoczność magazynu

Aby odinstalować dodatek Widoczność magazynu, wybierz opcję **Odinstaluj** na stronie usługi LCS. Proces odinstalowywania powoduje zakończenie pracy dodatku Widoczność magazynu oraz wyrejestrowanie dodatku z usługi LCS i usunięcie wszelkich tymczasowych danych przechowywanych w pamięci podręcznej danych dodatku Widoczność magazynu. Jednak podstawowe dane zapasów przechowywane w subskrypcji Dataverse nie są usuwane.

Aby odinstalować dane magazynu przechowywane w subskrypcji Dataverse, otwórz [Power Apps](https://make.powerapps.com), wybierz pozycję **Środowisko** na pasku nawigacyjnym i wybierz środowisko Dataverse, które jest połączone ze środowiskiem usługi LCS. Następnie przejdź do obszaru **Rozwiązania** i usuń następujące pięć rozwiązań:

- Zakotwiczone rozwiązanie aplikacji Widoczność magazynu w rozwiązaniach Dynamics 365
- Rozwiązanie aplikacji Widoczność magazynu Dynamics 365 FNO SCM
- Konfiguracja usługi zapasów
- Autonomiczna aplikacja Widoczność magazynu
- Rozwiązanie podstawowe Widoczność magazynu Dynamics 365 FNO SCM

Po usunięciu tych rozwiązań usuwane są także dane przechowywane w tabelach.

## <a name="set-up-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Konfigurowanie Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Wdróż pakiet integracyjny Widoczność magazynu

Jeśli korzystasz z rozwiązania Supply Chain Management w wersji 10.0.17 lub starszej, skontaktuj się z pokładowym zespołem pomocy technicznej ds. Widoczności zapasów pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com), aby uzyskać paczkę z plikami. Następnie wdróż pakiet w LCS.

> [!NOTE]
> Jeśli podczas wdrażania wystąpi błąd niezgodności wersji, należy ręcznie zaimportować projekt X ++ do środowiska programistycznego. Następnie utwórz pakiet do wdrożenia w swoim środowisku programistycznym i wdróż go w środowisku produkcyjnym.
>
> Kod jest dołączony do programu Supply Chain Management w wersji 10.0.18. Jeśli używasz tej lub nowszej wersji, wdrożenie nie jest wymagane.

Upewnij się, że poniższe funkcje są włączone w środowisku Supply Chain Management. (Domyślnie są włączone).

| Opis funkcji | Wersja kodu | Przełącz klasę |
|---|---|---|
| Włączanie lub wyłączanie korzystania z wymiarów magazynowych w tabeli InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Włączanie lub wyłączanie korzystania z wymiarów magazynowych w tabeli InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Konfiguracja integracji Widoczności zapasów

1. W Supply Chain Management otwórz obszar roboczy **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** i włącz funkcję *Integracja widoczności magazynu*.
1. Przejdź do witryny **Zarządzanie zapasami \> Konfiguracja \> Parametry integracji widoczności magazynu**, i wprowadź adres URL środowiska, w którym jest uruchamiana widoczność magazynu. Więcej informacji można znaleźć w temacie [Znajdowanie punktu końcowego usługi](inventory-visibility-power-platform.md#get-service-endpoint).
1. Przejdź do **Zarządzanie zapasami \> Okresowe \> Integracja widoczności magazynu** i włącz zadanie. Wszystkie zdarzenia zmiany zapasów z Supply Chain Management zostaną teraz zaksięgowane w widoczności magazynu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
