---
title: Strona główna aplikacji komórkowej Dynamics 365 for Unified Operations
description: W tym temacie opisano aplikację mobilną Microsoft Dynamics 365 for Unified Operations Mobile oraz zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji.
author: sericks007
manager: AnnBe
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: 5666bee776e3d97244ce4830ac59971831848e71
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554469"
---
# <a name="dynamics-365-for-unified-operations-mobile-app-home-page"></a>Strona główna aplikacji komórkowej Dynamics 365 for Unified Operations

[!include [banner](../includes/banner.md)]

W tym temacie opisano aplikację mobilną Microsoft Dynamics 365 for Unified Operations Mobile oraz zamieszczono łącza do zasobów, które mogą pomóc w jej zaimplementowaniu w organizacji.

> [!NOTE]
> Aplikacja mobilna nosiła wcześniej nazwę *Microsoft Dynamics 365 for Finance and Operations*.

<a name="overview"></a>Przegląd
--------

Aplikacja komórkowa umożliwia organizacji udostępnianie procesów biznesowych na urządzeniach przenośnych. Gdy administrator systemów informatycznych włączy komórkowe obszary robocze w organizacji, użytkownicy mogą się logować do aplikacji i natychmiast zacząć wykonywać procesy biznesowe na swoich urządzeniach komórkowych. Aplikacja mobilna zawiera następujące funkcje, które mogą pomóc zwiększyć wydajność pracy:

- Użytkownicy mogą przeglądać, edytować i przetwarzać dane biznesowe, nawet jeśli mają przerywaną łączność z siecią albo ich urządzenia przenośne są całkowicie w trybie offline. Gdy urządzenie ponownie nawiąże połączenie sieciowe, operacje na danych wykonane w trybie offline są synchronizowane automatycznie z programem Dynamics 365 for Finance and Operations.
- Administratorzy IT i programiści mogą tworzyć i publikować mobilne obszary robocze spersonalizowane do organizacji. Aplikacja wykorzystuje istniejące środowisko oprogramowania. W związku z tym nie jest konieczne ponowne implementowanie procedur sprawdzania poprawności, logiki biznesowej ani konfiguracji zabezpieczeń.
- Administratorzy IT i deweloperzy mogą łatwo projektować komórkowe obszary robocze za pomocą projektanta obszarów roboczych typu „wskaż i kliknij”, który jest zawarty w kliencie internetowym.
- Administratorzy IT i deweloperzy mogą opcjonalnie optymalizować funkcje offline obszarów roboczych za pomocą struktury rozszerzania logiki biznesowej. Ponieważ dane są cały czas przetwarzane, gdy urządzenie jest w trybie offline, scenariusz użytkowania mobilnego pozostaje bogaty funkcjonalnie i płynny, nawet jeśli urządzenia nie mają stałej łączności z siecią.

## <a name="elements-of-the-mobile-app"></a>Elementy aplikacji mobilnej
Nawigacja w aplikacji mobilnej jest podzielona na cztery podstawowe koncepcje: pulpit nawigacyjny, obszary robocze, strony i akcje. 

[![Koncepcje nawigacyjne w aplikacji mobilnej](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. Po uruchomieniu aplikacji przechodzisz do **pulpitu nawigacyjnego**.
2. Na pulpicie nawigacyjnym widać listę **obszarów roboczych**, które zostały opublikowane.
3. W każdym obszarze roboczym widać listę **stron** dostępnych dla tego obszaru roboczego.
4. Po przejściu do strony można wykonać kilka czynności. Oto kilka przykładów:

    - Wyświetlanie szczegółowych danych.
    - Przechodzenie do innych stron zawierających pokrewne dane, takie jak szczegóły jednostek lub wiersze.
    - Wyświetlanie listy **akcji** dostępnych dla tej strony. Akcje umożliwiają tworzenie nowych i edytowanie istniejących danych.

## <a name="implementation-process"></a>Projekt wdrażania
Na poniższej ilustracji przedstawiono proces wdrażania mobilnych obszarów roboczych dostarczanych przez Microsoft i niestandardowych mobilnych obszarów roboczych. 

[![Proces implementacji aplikacji mobilnych](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

Poniższa tabela zawiera łącza do zasobów, które mogą pomóc we wdrażaniu mobilnych obszarów roboczych dostarczanych przez Microsoft i niestandardowych mobilnych obszarów roboczych. Numery w pierwszej kolumnie odpowiadają ponumerowanym krokom na poprzedniej ilustracji.

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
<td>Przeprowadź wdrożenie rozwiązania Finance and Operations w swojej organizacji.</td>
<td><ul><li>Jeśli w organizacji jeszcze nie wdrożono wersji oprogramowania Microsoft Dynamics 365, zobacz <a href="../deployment/deploy-demo-environment.md">Wdrażanie środowiska demonstracyjnego</a>.</li><li>Aby wyświetlić listę komórkowych obszarów roboczych, których można używać, zobacz <a href="mobile-workspaces-released.md">Ostatnio wydane mobilne obszary robocze</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrator systemu</td>
<td><strong>Jeśli używasz Microsoft Dynamics 365 for Operations w wersji 1611:</strong> Pobranie i zainstalowanie aktualizacji KB, które włączą obsługę mobilnych obszarów roboczych dostarczanych przez Microsoft.</td>
<td>Aby uzyskać więcej informacji, zobacz następujące tematy:
<ul>

<li><a href="../../financials/cost-accounting/cost-controlling-mobile-workspace.md">Mobilny obszar roboczy Kontrola kosztów</a></li>
<li><a href="../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Mobilny obszar roboczy Dostępne zapasy</a></li>
<li><a href="../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Mobilny obszar roboczy Zamówienia sprzedaży</a></li>
<li><a href="../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Obszar roboczy współpracy z dostawcami za pomocą urządzeń przenośnych</a></li>
<li><a href="../../financials/project-management/project-time-entry-mobile-workspace.md">Mobilny obszar roboczy Wprowadzanie czasu projektu</a></li>
<li><a href="../../financials/expense-management/expense-management-mobile-workspace.md">Mobilny obszar roboczy Zarządzanie wydatkami</a></li>

</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrator systemu</td>
<td>Opublikowanie mobilnych obszarów roboczych dostarczonych przez Microsoft.</td>
<td><a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Programista lub niezależny dostawca oprogramowania (ISV)</td>
<td>Utworzenie niestandardowych mobilnych obszarów roboczych za pomocą platformy komórkowej.</td>
<td><a href="platform/mobile-platform-home-page.md">Platforma mobilna</a></td>
</tr>
<tr class="odd">
<td>5</td>
<td>Niezależny dostawca oprogramowania</td>
<td>Utworzenie wdrażalnego pakietu zawierającego niestandardowe mobilne obszary robocze i przekazanie pakietu do usługi Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="../deployment/create-apply-deployable-package.md">Tworzenie wdrażalnego pakietu</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrator systemu</td>
<td>Zastosowanie wdrażalnego pakietu zawierającego niestandardowe obszary robocze dostarczonego przez niezależnego dostawcę oprogramowania (ISV).</td>
<td><a href="../deployment/apply-deployable-package-system.md">Stosowanie wdrażalnego pakietu</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrator systemu</td>
<td>Opublikowanie niestandardowych mobilnych obszarów roboczych dostarczonych przez niezależnego dostawcę oprogramowania.</td>
<td><a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Użytkownik</td>
<td>Pobieranie i instalowanie aplikacji mobilnej.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Aplikacja Unified Operations dla systemu Android</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Aplikacja Unified Operations dla systemu iOS</a><BR/>
(system Windows Phone nie jest obsługiwany)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Użytkownik</td>
<td>Zalogowanie się do aplikacji mobilnej i jej używanie. Aplikacja zawiera mobilne obszary robocze, które zostały opublikowane przez administratora systemu.</td>
<td>Aby wyświetlić listę komórkowych obszarów roboczych dostarczonych przez Microsoft, zobacz <a href="mobile-workspaces-released.md">Ostatnio wydane mobilne obszary robocze</a>.
</td>
</tr>
</tbody>
</table>
