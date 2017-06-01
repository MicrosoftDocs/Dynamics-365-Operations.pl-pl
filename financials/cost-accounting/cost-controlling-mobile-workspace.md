---
title: "Mobilny obszar roboczy Kontrola kosztów"
description: "W tym temacie omówiono mobilny obszar roboczy Kontrola kosztów, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Operations. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 09383c24b0dd2ad61a836f6c8dc97f4389915772
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="cost-controlling-mobile-workspace"></a>Mobilny obszar roboczy Kontrola kosztów

[!include[banner](../includes/banner.md)]


W tym temacie omówiono mobilny obszar roboczy Kontrola kosztów, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Operations. Ten obszar roboczy umożliwia menedżerom centrów kosztów podgląd na działanie tych centrów zawsze i wszędzie. 

<a name="overview-of-the-cost-controlling-mobile-workspace"></a>Omówienie komórkowego obszaru roboczego Kontrola kosztów
-------------------------------------------------

Mobilny obszar roboczy **Kontrola kosztów** zapewnia natychmiastowy podgląd wyników działania centrów kosztów poprzez porównanie kosztów rzeczywistych z kosztami budżetowymi. W widoku można przechodzić do stanów poszczególnych składników kosztów. 

Na przykład pracownik otrzymuje zaproszenie na międzynarodową konferencję, ale organizacja musi pokryć wszystkie wydatki na podróż. Pracownik pyta przełożonego, czy może wziąć udział w konferencji. Przełożony otwiera mobilny obszar roboczy **Kontrola kosztów** na swoim telefonie komórkowym i sprawdza, czy ma budżet na pokrycie kosztów udziału pracownika w konferencji.

### <a name="data-security"></a>Bezpieczeństwo danych

Dane w komórkowym obszarze roboczym **Kontrola kosztów** są zabezpieczone poświadczeniami użytkownika. Menedżerowie centrów kosztów mają pozwolenie na wgląd tylko w dane swoich centrów kosztów. Zabezpieczenia na poziomie dostępu są administrowane w module **Rachunek kosztów**. 

Księgowi kosztów definiują konfigurację mobilnego obszaru roboczego **Kontrola kosztów** w module **Rachunek kosztów**. Po opublikowaniu obszaru roboczego w aplikacji komórkowej Microsoft Dynamics 365 for Operations jest on dostępny w tej aplikacji. Dzięki temu menedżerowie centrów kosztów w organizacji mogą wyświetlać dane w tym samym formacie.

### <a name="actions-views-and-links"></a>Akcje, widoki i łącza

Mobilny obszar roboczy **Kontrola kosztów** dla aplikacji Dynamics 365 for Operations oferuje następujące akcje, widoki i łącza:

-   **Akcje:**
    -   Użyj **Wybierz konfigurację**, aby wybrać układ.
    -   Użyj **Wybierz obiekt kosztu**, aby wybrać centra kosztów, według których mają zostać wyfiltrowane dane. **Uwaga:** Centra kosztów wyświetlane na liście zależą od dostępu udzielonego w module **Rachunek kosztów**.
-   **Widoki:** Zależnie od wybranych akcji oraz konfiguracji w module **Rachunek kosztów** można przeglądać poniższe informacje na kartach:
    -   Wartości rzeczywiste a budżet (bieżący okres)
    -   Wartości rzeczywiste a skorygowany budżet (bieżący okres)
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
    
    [![Karta składnika kosztu ](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="prerequisites"></a>Wymagania wstępne
Aby można było używać mobilnego obszaru roboczego **Kontrola kosztów**, administrator systemu musi zapewnić spełnienie następujących warunków wstępnych:

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Rola</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Należy zainstalować program Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą.</td>
<td>Administrator systemu</td>
<td>Jeśli w organizacji jeszcze nie wdrożono programu Dynamics 365 for Operations, administrator systemu powinien przeczytać temat <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Wdrażanie środowiska demonstracyjnego programu Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Należy zainstalować poprawkę KB 4013633.</td>
<td>Administrator systemu</td>
<td>KB 4013633 (aktualizacja platformy języka X++ lub poprawka metadanych) zawiera cztery komórkowe obszary robocze dla zarządzania łańcuchem dostaw. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li>Pobierz poprawkę KB 4013633 z usługi Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a> do systemu Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Mobilny obszar roboczy <strong>Kontrola kosztów</strong> musi zostać opublikowany w aplikacji komórkowej Dynamics 365 for Operations.</td>
<td>Administrator systemu</td>
<td><ol>
<li>Uruchom program Dynamics 365 for Operations w przeglądarce internetowej.</li>
<li>Na stronie <strong>Parametry systemu</strong> zaznacz opcję <strong>Zarządzaj mobilnymi obszarami roboczymi</strong>.</li>
<li>Wybierz obszar roboczy <strong>Przegląd obiektów kosztów</strong>.</li>
<li>Kliknij opcję <strong>Opublikuj mobilny obszar roboczy</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Pobieranie i instalowanie aplikacji komórkowej Dynamics 365 for Operations
W sklepie z aplikacjami dla urządzeń komórkowych pobierz i zainstaluj aplikację Dynamics 365 for Operations.

-   Android: [Dynamics 365 for Operations w sklepie Google Play](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   iPhone: [Dynamics 365 for Operations w sklepie z aplikacjami iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Logowanie do aplikacji komórkowej Dynamics 365 for Operations
1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL programu Dynamics 365 for Operations.
3.  Wpisz firmę, do której chcesz się zalogować. Na przykład wpisz **USMF**.
4.  Podczas pierwszego logowania zostanie wyświetlony monit o podanie nazwy użytkownika i hasła dostępu do konta programu Dynamics 365 for Operations. Wprowadź swoje poświadczenia.
5.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, można wykonać operację ściągania i odświeżyć listę komórkowych obszarów roboczych. 

    [![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Wyświetlanie wyników działania centrum kosztów przy użyciu mobilnego obszaru roboczego Kontrola kosztów
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





