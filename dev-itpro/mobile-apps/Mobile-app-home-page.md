---
title: "Strona główna aplikacji komórkowej Dynamics 365 for Operations"
description: "W tym temacie opisano aplikację mobilną Microsoft Dynamics 365 for Operations oraz zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji."
author: sericks007
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e1a9e0eeb45f011ccb2aa091e68aff92782e1ae7
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="dynamics-365-for-operations-mobile-app-home-page"></a>Strona główna aplikacji komórkowej Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]


W tym temacie opisano aplikację mobilną Microsoft Dynamics 365 for Operations oraz zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji.

<a name="overview"></a>Przegląd
--------

Aplikacja komórkowa Microsoft Dynamics 365 for Operations umożliwia organizacji udostępnianie procesów biznesowych na urządzeniach przenośnych. Gdy administrator systemów informatycznych włączy funkcję komórkowych obszarów roboczych w organizacji, użytkownicy mogą się logować do aplikacji i natychmiast zacząć wykonywać procesy biznesowe na swoich urządzeniach komórkowych. Aplikacja mobilna Dynamics 365 for Operations zawiera następujące funkcje, które mogą pomóc zwiększyć wydajność pracy:

-   Użytkownicy mogą przeglądać, edytować i przetwarzać dane biznesowe, nawet jeśli mają przerywaną łączność z siecią albo ich urządzenia przenośne są całkowicie w trybie offline. Gdy urządzenie ponownie nawiąże połączenie sieciowe, operacje na danych wykonane w trybie offline są synchronizowane automatycznie z programem Dynamics 365 for Operations.
-   Administratorzy IT i programiści mogą tworzyć i publikować mobilne obszary robocze spersonalizowane do organizacji. Aplikacja wykorzystuje istniejące środowisko oprogramowania. W związku z tym nie jest konieczne ponowne implementowanie procedur sprawdzania poprawności, logiki biznesowej ani konfiguracji zabezpieczeń.
-   Administratorzy IT i deweloperzy mogą łatwo projektować komórkowe obszary robocze za pomocą projektanta obszarów roboczych typu „wskaż i kliknij”, który jest zawarty w kliencie internetowym usługi Dynamics 365 for Operations.
-   Administratorzy IT i deweloperzy mogą opcjonalnie optymalizować funkcje offline obszarów roboczych za pomocą struktury rozszerzania logiki biznesowej. Ponieważ dane są cały czas przetwarzane, gdy urządzenie jest w trybie offline, scenariusz użytkowania mobilnego pozostaje bogaty funkcjonalnie i płynny, nawet jeśli urządzenia nie mają stałej łączności z siecią.

## <a name="elements-of-the-mobile-app"></a>Elementy aplikacji mobilnej
Nawigacja w aplikacji mobilnej jest podzielona na cztery proste koncepcje: pulpit nawigacyjny, obszary robocze, strony i akcje. 

[![Koncepcje nawigacyjne w aplikacji mobilnej](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

-   Po uruchomieniu aplikacji przechodzisz do **pulpitu nawigacyjnego**.
-   Na pulpicie nawigacyjnym widać listę **obszarów roboczych**, które są opublikowane w środowisku Dynamics 365 for Operations.
-   W każdym obszarze roboczym widać listę **stron** dostępnych dla tego obszaru roboczego.
-   Na stronie można przeglądać dane zbierane z jednej lub więcej stron w programie Dynamics 365 for Operations.
-   Ze strony można przejść do innych stron zawierających pokrewne dane, takie jak szczegóły jednostek lub wiersze.
-   Na stronie widać także listę **akcji** dostępnych dla tej strony.
-   Akcje umożliwiają tworzenie nowych i edytowanie istniejących danych.

## <a name="implementation-process"></a>Projekt wdrażania
Na poniższej ilustracji przedstawiono proces wdrażania aplikacji komórkowej Dynamics 365 for Operations w organizacji. 

[![](./media/mobile-implementation-process_4.png)](./media/mobile-implementation-process_4.png) 

Tabela poniżej zawiera łącza do zasobów, które mogą pomóc w zaimplementowaniu aplikacji mobilnej Dynamics 365 for Operations w organizacji. Numery w pierwszej kolumnie odpowiadają ponumerowanym krokom na poprzedniej ilustracji.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Krok</th>
<th>Rola</th>
<th>Akcja</th>
<th>Zasoby pomagające wykonać akcję</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Administrator systemu</td>
<td>Wdrożenie programu Dynamics 365 for Operations w organizacji.</td>
<td>Jeśli w organizacji jeszcze nie wdrożono programu Dynamics 365 for Operations zobacz <a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Wdrażanie środowiska demonstracyjnego programu Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrator systemu</td>
<td>Pobranie i zainstalowanie aktualizacji KB, które włączą obsługę mobilnych obszarów roboczych dostarczanych przez Microsoft.</td>
<td>Zobacz sekcję &quot;Wymagania wstępne&quot; w temacie o komórkowych obszarach roboczych, który chce używać Twoja organizacja:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Mobilny obszar roboczy Kontrola kosztów</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Mobilny obszar roboczy Dostępne zapasy</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Mobilny obszar roboczy Zamówienia sprzedaży</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Mobilny obszar roboczy współpracy z dostawcami</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Mobilny obszar roboczy Wprowadzanie czasu projektu</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrator systemu</td>
<td>Opublikowanie mobilnych obszarów roboczych dostarczonych przez Microsoft.</td>
<td>Zobacz sekcję &quot;Wymagania wstępne&quot; w temacie o komórkowych obszarach roboczych, który chce używać Twoja organizacja:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Mobilny obszar roboczy Kontrola kosztów</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Mobilny obszar roboczy Dostępne zapasy</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Mobilny obszar roboczy Zamówienia sprzedaży</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Mobilny obszar roboczy współpracy z dostawcami</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Mobilny obszar roboczy Wprowadzanie czasu projektu</a></li>
</ul></td>
</tr>
<tr class="even">
<td>4</td>
<td>Programista lub niezależny dostawca oprogramowania (ISV)</td>
<td>Tworzenie niestandardowych mobilnych obszarów roboczych za pomocą platformy komórkowej Dynamics 365 for Operations.</td>
<td><ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Platforma komórkowa Dynamics 365 for Operations</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">Interfejsy API języka X++ dla obszarów roboczych programu Dynamics 365 for Operations</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>Niezależny dostawca oprogramowania</td>
<td>Utworzenie wdrażalnego pakietu zawierającego niestandardowe mobilne obszary robocze i przekazanie pakietu do usługi Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Generowanie wdrażalnego pakietu</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrator systemu</td>
<td>Zastosowanie wdrażalnego pakietu zawierającego niestandardowe obszary robocze dostarczonego przez niezależnego dostawcę oprogramowania.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Stosowanie wdrażalnego pakietu w systemie Microsoft Dynamics 365 for Operations</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrator systemu</td>
<td>Opublikowanie niestandardowych mobilnych obszarów roboczych dostarczonych przez niezależnego dostawcę oprogramowania.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Użytkownik</td>
<td>Pobranie i zainstalowanie aplikacji komórkowej Dynamics 365 for Operations.</td>
<td><ul>
<li>Android: <a href="https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile">Dynamics 365 for Operations w sklepie Google Play</a></li>
<li>iPhone: <a href="https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8">Dynamics 365 for Operations w sklepie z aplikacjami iTunes</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Użytkownik</td>
<td>Zalogowanie się do aplikacji komórkowej Dynamics 365 for Operations i jej używanie. Aplikacja zawiera mobilne obszary robocze, które zostały opublikowane.</td>
<td>Firma Microsoft dostarczyła następujące komórkowe obszary robocze:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Mobilny obszar roboczy Kontrola kosztów</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Mobilny obszar roboczy Dostępne zapasy</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Mobilny obszar roboczy Zamówienia sprzedaży</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Mobilny obszar roboczy współpracy z dostawcami</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Mobilny obszar roboczy Wprowadzanie czasu projektu</a></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Informacje dodatkowe
--------

[Mobilne obszary robocze ostatnio wydane dla aplikacji komórkowej Dynamics 365 for Operations](mobile-workspaces-released.md)





