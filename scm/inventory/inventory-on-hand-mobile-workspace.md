---
title: "Mobilny obszar roboczy Dostępne zapasy"
description: "W tym temacie omówiono mobilny obszar roboczy Dostępne zapasy, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Operations. Ten obszar roboczy pomaga uzyskać na urządzeniach komórkowych w każdym miejscu i czasie wgląd w zapasy zarezerwowane i dostępne."
author: YuyuScheller
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e703ae80800b993ebca1c7bee455af1be41c7d5f
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Mobilny obszar roboczy Dostępne zapasy

[!include[banner](../includes/banner.md)]


W tym temacie omówiono mobilny obszar roboczy Dostępne zapasy, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Operations. Ten obszar roboczy pomaga uzyskać na urządzeniach komórkowych w każdym miejscu i czasie wgląd w zapasy zarezerwowane i dostępne.

<a name="overview-of-the-inventory-on-hand-mobile-workspace"></a>Omówienie komórkowego obszaru roboczego Dostępne zapasy
--------------------------------------------------

Zazwyczaj firmy codziennie wykonują wiele wydań i przyjęć zapasów. Te przesunięcia cały czas zmieniają stan dostępnych zapasów. Mobilny obszar roboczy **Dostępne zapasy** pozwala widzieć stan dostępnych zapasów w całej organizacji, wykorzystując do tego dowolne urządzenie komórkowe. Niezależnie od tego, czy pracujesz w magazynie, zakupach, sprzedaży, produkcji czy administracji, lub czy masz inne role, informacje o dostępnych zapasach możesz sprawdzać w każdym miejscu i czasie. Mobilny obszar roboczy zapewnia natychmiastowy wgląd w stan dostępnych zapasów we wszystkich zakładach. Pokazuje m.in. dostępne zapasy w poszczególnych obiektach, bieżące rezerwacje materiałów oraz niezarezerwowane dostępne zapasy. Można również wpisać numery towarów, aby sprawdzić dostępność zapasów, i wykonywać filtrowane wyszukiwanie dostępnych produktów lub wariantów. W szczególności mobilny obszar roboczy oferuje następujące funkcje:

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
Aby można było używać mobilnego obszaru roboczego **Dostępne zapasy**, administrator systemu musi zapewnić spełnienie następujących warunków wstępnych:

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
<td>Należy zainstalować program Microsoft Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą.</td>
<td>Administrator systemu</td>
<td>Jeśli w organizacji jeszcze nie wdrożono programu Dynamics 365 for Operations, administrator systemu powinien przeczytać temat <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Wdrażanie środowiska demonstracyjnego programu Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>Należy zainstalować poprawkę KB 4013633.</td>
<td>Administrator systemu</td>
<td>KB 4013633 (aktualizacja platformy języka X++ lub poprawka metadanych) zawiera cztery komórkowe obszary robocze dla zarządzania łańcuchem dostaw. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li>Pobierz poprawkę KB 4013633 z usługi Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Zastosuj wdrażalny pakiet</a> do systemu Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Mobilny obszar roboczy <strong>Dostępne zapasy</strong> musi zostać opublikowany w aplikacji komórkowej Dynamics 365 for Operations.</td>
<td>Administrator systemu</td>
<td><ol>
<li>Uruchom program Dynamics 365 for Operations w przeglądarce internetowej.</li>
<li>Na stronie <strong>Parametry systemu</strong> zaznacz opcję <strong>Zarządzaj mobilnymi obszarami roboczymi</strong>.</li>
<li>Wybierz obszar roboczy <strong>Dostępne zapasy</strong>.</li>
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

## <a name="view-the-onhand-inventory-for-a-product-by-using-the-inventory-onhand-mobile-workspace"></a>Wyświetlanie dostępnych zapasów produktu za pomocą mobilnego obszaru roboczego Dostępne zapasy
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Dostępne zapasy**.
2.  Wybierz opcję **Sprawdź dostępne zapasy towaru**. Zobacz listę produktów załadowanych do Twojej aplikacji z przeznaczeniem do używania w trybie offline. Domyślnie jest ładowanych 50 pozycji, ale programista może zmienić tę liczbę. Aby uzyskać więcej informacji, programiści powinni zapoznać się z tematem [Platforma komórkowa Dynamics 365 for Operations](http://ax.help.dynamics.com/en/wiki/mobile-development-handbook/).
3.  Jeśli towaru nie ma na liście, wybierz opcję **Wyszukaj więcej**, aby wykonać wyszukiwanie online w usłudze Dynamics 365 for Operations. Poszukaj według numeru produktu lub przełącz na wyszukiwanie według nazwy produktu.
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






