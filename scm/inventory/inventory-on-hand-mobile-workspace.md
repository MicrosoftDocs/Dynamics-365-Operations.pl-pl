---
title: "Mobilny obszar roboczy Dostępne zapasy"
description: "Ten temat zawiera informacje o komórkowym obszarze roboczym Dostępne zapasy. Ten obszar roboczy pomaga uzyskać na urządzeniach komórkowych w każdym miejscu i czasie wgląd w zapasy zarezerwowane i dostępne."
author: Mirzaab
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: db41b3873755f93895aea7a32b65f2a8ed6a57fd
ms.openlocfilehash: 6e062ffa459b7d008fc5d24f27538f8df04d7e82
ms.contentlocale: pl-pl
ms.lasthandoff: 08/10/2017

---

# <a name="inventory-on-hand-mobile-workspace"></a>Mobilny obszar roboczy Dostępne zapasy

[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Dostępne zapasy**. Ten obszar roboczy pomaga uzyskać w każdym miejscu i czasie wgląd w zapasy zarezerwowane i dostępne.

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations.

## <a name="overview"></a>Przegląd
Zazwyczaj firmy codziennie wykonują wiele wydań i przyjęć zapasów. Te przesunięcia cały czas zmieniają stan dostępnych zapasów. Mobilny obszar roboczy **Dostępne zapasy** pozwala widzieć stan dostępnych zapasów w całej organizacji, wykorzystując do tego dowolne urządzenie komórkowe. Niezależnie od tego, czy pracujesz w magazynie, zakupach, sprzedaży, produkcji czy administracji, lub czy masz inne role, informacje o dostępnych zapasach możesz sprawdzać w każdym miejscu i czasie. 

Mobilny obszar roboczy zapewnia natychmiastowy wgląd w stan dostępnych zapasów we wszystkich zakładach. Pokazuje m.in. dostępne zapasy w poszczególnych obiektach, bieżące rezerwacje materiałów oraz niezarezerwowane dostępne zapasy. Można również wpisać numery towarów, aby sprawdzić dostępność zapasów, i wykonywać filtrowane wyszukiwanie dostępnych produktów lub wariantów. 

W szczególności mobilny obszar roboczy oferuje następujące funkcje:

-   Można szukać według numeru produktu lub nazwy produktu, aby znaleźć produkty, dla których chcesz sprawdzić stan dostępności zapasów.
-   Dla wybranych produktów można wyświetlić następujące informacje:

    -   Dostępne zapasy według oddziału
    -   Dostępne zapasy według magazynu
    -   Dostępne zapasy według lokalizacji
    -   Dostępne zapasy według partii (dla produktów wchodzących w skład partii)
    -   Dostępne zapasy według stanu zapasów
    
-   Dostępne zapasy produktów są pokazywane w następujący sposób:

    -   Według zapasów fizycznych (widok przedstawia łączną ilość)
    -   Według fizycznie zarezerwowanych zapasów (widok przedstawia ilość zarezerwowaną)
    -   Według fizycznie dostępnych zapasów (ten widok przedstawia dostępną ilość, która nie ma żadnych rezerwacji)

## <a name="prerequisites"></a>Wymagania wstępne
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update"></a>Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r. 
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r., administrator systemu musi opublikować mobilny obszar roboczy **Dostępne zapasy**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
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

<td>KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Dostępne zapasy</strong>. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Dostępne zapasy</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej

Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:

-   [Telefony z systemem Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej

1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL usługi Dynamics 365.
3.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

    [![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Wyświetlanie dostępnych zapasów produktu za pomocą mobilnego obszaru roboczego Dostępne zapasy

1.  Na urządzeniu przenośnym wybierz obszar roboczy **Dostępne zapasy**.

2.  Wybierz opcję **Sprawdź dostępne zapasy towaru**. Zobacz listę produktów załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma mobilna](/dynamics365/unified-operations/dev-itpro/mobile-apps/platform/mobile-platform-home-page).
3.  Jeśli Twojego towaru nie ma na liście, kliknij przycisk **Wyszukaj więcej**. Poszukaj według numeru produktu lub przełącz na wyszukiwanie według nazwy produktu.

4.  Wybierz produkt. Jeśli towar ma ilustrację, zostanie ona wyświetlona.
5.  Wybierz jedną z poniższych opcji, aby wyświetlić stan dostępnych zapasów:

    -   Wyświetl dostępne wg oddziału
    -   Wyświetl dostępne wg magazynu
    -   Wyświetl dostępne wg lokalizacji
    -   Wyświetl dostępne wg partii (dla produktów wchodzących w skład partii)
    -   Wyświetl dostępne wg stanu zapasów

    Dostępne zapasy produktów są pokazywane w następujący sposób:
    -   Według zapasów fizycznych (widok przedstawia łączną ilość)
    -   Według fizycznie zarezerwowanych zapasów (widok przedstawia ilość zarezerwowaną)
    -   Według fizycznie dostępnych zapasów (ten widok przedstawia dostępną ilość, która nie ma żadnych rezerwacji)

