---
title: "Mobilny obszar roboczy Kontrola kosztów"
description: "Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego Kontrola kosztów. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie."
author: YuyuScheller
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: dbedf75a6f61a9e2bc644056f0dd1e7499cedc42
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Mobilny obszar roboczy Kontrola kosztów
<a id="cost-controlling-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego **Kontrola kosztów**. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie.

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations.

## Przegląd
<a id="overview" class="xliff"></a>
Mobilny obszar roboczy **Kontrola kosztów** zapewnia natychmiastowy podgląd wyników działania centrów kosztów poprzez porównanie kosztów rzeczywistych z kosztami budżetowymi. W widoku można przechodzić do stanów poszczególnych składników kosztów.

Na przykład pracownik otrzymuje zaproszenie na międzynarodową konferencję, ale organizacja musi pokryć wszystkie wydatki na podróż. Pracownik pyta przełożonego, czy może wziąć udział w konferencji. Przełożony otwiera mobilny obszar roboczy **Kontrola kosztów** na swoim telefonie komórkowym i sprawdza, czy ma budżet na pokrycie kosztów udziału pracownika w konferencji.

### Bezpieczeństwo danych
<a id="data-security" class="xliff"></a>
Dane w komórkowym obszarze roboczym **Kontrola kosztów** są zabezpieczone poświadczeniami użytkownika. Menedżerowie centrów kosztów mają pozwolenie na wgląd tylko w dane swoich centrów kosztów. Zabezpieczenia na poziomie dostępu są administrowane w module **Rachunek kosztów**.

Księgowi kosztów definiują konfigurację mobilnego obszaru roboczego **Kontrola kosztów** w module **Rachunek kosztów**. Po opublikowaniu obszaru roboczego w aplikacji komórkowej jest on dostępny w tej aplikacji. Dzięki temu menedżerowie centrów kosztów w organizacji mogą wyświetlać dane w tym samym formacie.

### Akcje, widoki i łącza
<a id="actions-views-and-links" class="xliff"></a>
Mobilny obszar roboczy **Kontrola kosztów** oferuje następujące czynności, widoki i łącza:

-   **Akcje:**

    -   Użyj **Wybierz konfigurację**, aby wybrać układ.
    -   Użyj **Wybierz obiekt kosztu**, aby wybrać centra kosztów, według których mają zostać wyfiltrowane dane.
    
        > [!NOTE]
        > Centra kosztów wyświetlane na liście zależą od dostępu udzielonego w module **Rachunek kosztów**.

-   **Widoki:** Zależnie od wybranych akcji oraz konfiguracji w module **Rachunek kosztów** można przeglądać poniższe informacje na kartach:

    -   Rzeczywisty a budżetowy (bieżący okres)
    -   Rzeczywisty a skorygowany budżetowy (bieżący okres)
    -   Wartości rzeczywiste a budżet (poprzedni okres)
    -   Wartości rzeczywiste a skorygowany budżet (poprzedni okres)
    -   Wartości rzeczywiste a budżet (od początku roku)
    -   Wartości rzeczywiste a skorygowany budżet (od początku roku)

    Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie i % odchylenia.

-   **Linki:**

    -   Szczegóły bieżącego okresu
    -   Szczegóły poprzedniego okresu
    -   Szczegóły okresu od początku roku

    Po wybraniu łącza jest wyświetlana karta dla każdego składnika kosztów. Na każdej karcie są wyświetlane następujące kwoty: wartości rzeczywiste, budżet, odchylenie budżetu, % odchylenia budżetu, skorygowany budżet, odchylenie skorygowanego budżetu i % odchylenia skorygowanego budżetu.
    
    [![Karta składnika kosztu ](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## Wymagania wstępne
<a id="prerequisites" class="xliff"></a>
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r.
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a>
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r., administrator systemu musi opublikować mobilny obszar roboczy **Kontrola kosztów**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later" class="xliff"></a>
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne.

<table>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Rola</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zainstalowanie poprawki KB 4013633.</td>
<td>Administrator systemu</td>

<td>KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Kontrola kosztów</strong>. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Kontrola kosztów</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>


## Pobieranie i instalowanie aplikacji mobilnej
<a id="download-and-install-the-mobile-app" class="xliff"></a>
Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:

-   [Telefony z systemem Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## Logowanie do aplikacji mobilnej
<a id="sign-in-to-the-mobile-app" class="xliff"></a>

1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL usługi Dynamics 365.
3.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

[![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## Wyświetlanie wyników działania centrum kosztów przy użyciu mobilnego obszaru roboczego Kontrola kosztów
<a id="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace" class="xliff"></a>

1.  Na urządzeniu przenośnym wybierz obszar roboczy **Kontrola kosztów**.
2.  Wybierz opcję **Kontrola obiektów kosztów**.
3.  Wybierz opcję **Akcje**.
4.  Wybierz opcję **Wybierz konfigurację** i wybierz układ kontroli kosztów.
5.  Wybierz opcję **Gotowe**.
6.  Wybierz opcję **Akcje**.
7.  Wybierz opcję **Wybierz obiekt kosztu** i zaznacz centra kosztów, do których przyznano Ci uprawnienie dostępu.
8.  Wybierz opcję **Gotowe**.
9.  Wyświetl całościowe wyniki działania centrum kosztów.
10. Kliknij łącze **Szczegóły bieżącego okresu**.
11. Wyświetl wyniki działania poszczególnych składników kosztów.
12. Można także wyszukiwać konkretne składniki kosztów.


