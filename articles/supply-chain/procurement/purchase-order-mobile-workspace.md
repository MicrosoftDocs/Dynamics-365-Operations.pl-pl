---
title: Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu
description: Ten artykuł zawiera informacje dotyczące komórkowego obszaru roboczego Zatwierdzenia zamówienia zakupu, w którym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne czynności. Można na przykład zatwierdzić lub odrzucić zamówienie zakupu.
author: GalynaFedorova
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b5336549937edca6beb94137896f84b460f257f7
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111339"
---
# <a name="purchase-order-approval-mobile-workspace"></a>Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Ten artykuł zawiera informacje o komórkowym obszarze roboczym **Zatwierdzenie zamówienia zakupu**. W tym obszarze roboczym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne akcje. Można na przykład zatwierdzić lub odrzucić zamówienie zakupu.
 
## <a name="overview"></a>Przegląd 
Zamówienia zakupu wymagające zatwierdzenia przechodzą przez przepływ pracy zatwierdzania. Przepływ pracy może obejmować różne kroki, które wymagają wykonania różnych operacji przez jedną lub więcej osób. Na przykład osoba może być zobowiązana wykonać zadanie lub zatwierdzić zamówienie zakupu. 

Mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu** pozwala łatwo wyświetlać zamówienia zakupu i na nie reagować z urządzenia komórkowego. Ten obszar roboczy umożliwia także podejmowanie tych samych akcji przepływu pracy, jak na kliencie internetowym.

## <a name="prerequisites"></a>Wymagania wstępne
Wymagania wstępne różnią się w zależności od wersji programu Supply Chain Management wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Warunki wstępne, jeśli jest używane Supply Chain Management 
Jeśli w organizacji wdrożono rozwiązanie Supply Chain Management, administrator systemu musi opublikować mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

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
<td>Zainstalowanie poprawki KB 4017918.</td>
<td>Administrator systemu</td>
<td>KB 4017918 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Zatwierdzenie zamówienia zakupu</strong>. W celu zainstalowania poprawki KB 4017918 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></li>
</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Zatwierdzenie zamówienia zakupu</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej
Pobieranie i instalowanie mobilnych aplikacji finansowych i operacyjnych:

- [Telefony Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej

1. Uruchom aplikację na urządzeniu komórkowym.
2. Wprowadź swój adres URL w usłudze Microsoft Dynamics 365.
3. Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

![Obszar roboczy Zatwierdzenie zamówienia zakupu na liście dostępnych obszarów roboczych.](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>Wyświetlanie zamówień, które są Ci przypisane
1. Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenie zamówienia zakupu**.
2. Kliknij opcję **Zamówienia przypisane do mnie**, z zostaną wyświetlone wszystkie zamówienia zakupu, którymi musisz się zająć w przepływie pracy zatwierdzania zamówień zakupu.
3. Zaznacz zamówienie. Na stronie **Szczegóły zamówienia** zobaczysz informacje nagłówka i wiersze zamówienia. W zadaniu przepływu pracy są również wyświetlane wytyczne postępowania.
4. Kliknij opcję **Zasady podziału księgowań**, aby otworzyć stronę **Zasady podziału księgowań dotyczące nagłówka**.
5. Wróć do strony **Szczegóły zamówienia** i zaznacz wiersz. Z poziomu szczegółów wiersza zamówienia możesz też przeglądać zasady podziału księgowań specyficzne dla wiersza.

## <a name="complete-an-action-on-the-purchase-order"></a>Wykonywanie operacji w zamówieniu zakupu
Po przejrzeniu przypisanego Ci zamówienia zakupu i zapoznaniu się z instrukcjami przepływu pracy możesz przystąpić do faktycznego działania.

1. Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenie zamówienia zakupu**.
2. Kliknij opcję **Zamówienia przypisane do mnie**, z zostaną wyświetlone wszystkie zamówienia zakupu, którymi musisz się zająć w przepływie pracy zatwierdzania zamówień zakupu.
3. Zaznacz zamówienie i wyświetl stronę szczegółów.
4. Kliknij opcję **Akcje**, aby wyświetlić dostępne akcje. Dostępne czynności zależą od zadania, które Ci przypisano.

    | Czynność zadania    | Czynność zatwierdzenia  |
    |----------------|------------------|
    | Wykonane       | Zatwierdzanie          |
    | Powrót         | Odrzuć           |
    | Żądaj zmiany | Żądaj zmiany   |
    | Użytkownik delegowany       | Użytkownik delegowany         |

5. Wybierz odpowiednią akcję.
6. Na stronie **Wykonaj zadanie** wprowadź komentarz. Należy zauważyć, że po wybraniu akcji **Delegowanie** musisz wybrać użytkownika, któremu zadanie zostanie delegowane.
7. Wybierz opcję **Gotowe**. Po odświeżeniu obszaru roboczego zamówienie zakupu przestanie być widoczne na liście. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

