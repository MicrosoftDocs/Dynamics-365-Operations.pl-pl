---
title: Mobilny obszar roboczy Zatwierdzenia faktur
description: Ten temat zawiera informacje o komórkowym obszarze roboczym Zatwierdzenia faktur. Ten obszar roboczy wyświetla listę faktur, które zostały Ci przypisane przez proces przepływu pracy nagłówków faktur od dostawców.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ff726670e0fd7566a74e6def73555a7c53b86f97
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554423"
---
# <a name="invoice-approvals-mobile-workspace"></a>Mobilny obszar roboczy Zatwierdzenia faktur

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Zatwierdzenia faktur**. Ten obszar roboczy wyświetla listę faktur, które zostały Ci przypisane przez proces przepływu pracy nagłówków faktur od dostawców. 

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations Mobile.

## <a name="overview"></a>Przegląd

Komórkowy obszar roboczy **Zatwierdzenia faktur** pozwala pracownikom i kierownikom ds. rozrachunków z dostawcami wyświetlać faktury, które zostały im przypisane w procesie przepływu pracy nagłówków faktur od dostawców. Można wyświetlić informacje o fakturze, a nawet szczegóły wiersza i dystrybucji, aby podejmować najbardziej trafne decyzje o zatwierdzeniu. W obszarze roboczym można podjąć odpowiednie działania, aby przeprowadzić fakturę przez kolejne etapy przepływu pracy. 

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było używać tego mobilnego obszaru roboczego, muszą być spełnione następujące wymagania wstępne.

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
<td>W organizacji musi być wdrożone rozwiązanie Microsoft Dynamics 365 for Finance and Operations.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="../deployment/deploy-demo-environment.md">Wdrażanie środowiska demonstracyjnego</a>.
</td>
</tr>
<tr class="even">
<td>Mobilny obszar roboczy <strong>Zatwierdzenia faktur</strong> musi być opublikowany.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="publish-mobile-workspace.md">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej

Pobierz i zainstaluj aplikację komórkową Dynamics 365 for Unified Operations:

-   [Telefony Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej

1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź swój adres URL w usłudze Microsoft Dynamics 365.
3.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

    [![Ściąganie w celu odświeżenia](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a>Zatwierdzanie faktur w mobilnym obszarze roboczym Zatwierdzenia faktur
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenia faktur**.
2.  Zaznacz fakturę, która została Ci przypisana w procesie przepływu pracy nagłówków faktur od dostawców.
3.  Na stronie **Szczegóły faktury** przejrzyj informacje z nagłówka faktury, w tym o dostawcy i dacie.
4.  Zaznacz wiersz faktury, a zostaną wyświetlone jego bardziej szczegółowe informacje w widoku **Szczegóły wierszy faktury**.
5.  W widoku **Szczegóły wierszy faktury** wybierz opcję **Rozdzielenia**, aby wyświetlić rozdziały wierszy. Tutaj można obejrzeć rozksięgowanie wiersza faktury. Wyświetlane informacje obejmują wymiary finansowe i konto główne.
6.  Na stronie **Szczegóły faktury** wybierz opcję **Rozdzielenia**, a zostaną wyświetlone wszystkie dystrybucje. Tutaj można obejrzeć rozksięgowanie całej faktury. Wyświetlane informacje obejmują wymiary finansowe i konta główne. 
7.  Wybierz opcję **Załączniki**, aby wyświetlić wszelkie notatki lub pliki dołączone do faktury.
8.  Na stronie **Szczegóły faktury** zaznacz odpowiednią akcję przepływu pracy, aby ukończyć proces przeglądu.
9.  Wybierz opcję **Gotowe**.
