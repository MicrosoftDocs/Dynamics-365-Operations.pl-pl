---
title: "Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu"
description: "Ten temat zawiera informacje dotyczące komórkowego obszaru roboczego Zatwierdzenia zamówienia zakupu, w którym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne czynności. Można na przykład zatwierdzić lub odrzucić zamówienie zakupu."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: a2ab719b971c325be184d1d950f6c03815e4cea2
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Mobilny obszar roboczy Zatwierdzenie zamówienia zakupu
<a id="purchase-order-approval-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Zatwierdzenie zamówienia zakupu**. W tym obszarze roboczym można wyświetlać zamówienia zakupu i reagować na niej poprzez różne akcje. Można na przykład zatwierdzić lub odrzucić zamówienie zakupu.
 
## Przegląd
<a id="overview" class="xliff"></a> 
Zamówienia zakupu wymagające zatwierdzenia przechodzą przez przepływ pracy zatwierdzania. Przepływ pracy może obejmować różne kroki, które wymagają wykonania różnych operacji przez jedną lub więcej osób. Na przykład osoba może być zobowiązana wykonać zadanie lub zatwierdzić zamówienie zakupu. 

Mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu** pozwala łatwo wyświetlać zamówienia zakupu i na nie reagować z urządzenia komórkowego. Ten obszar roboczy umożliwia także podejmowanie tych samych akcji przepływu pracy, jak na kliencie internetowym usługi Microsoft Dynamics 365 for Finance and Operations Enterprise Edition.

## Wymagania wstępne
<a id="prerequisites" class="xliff"></a>
Wymagania wstępne różnią się w zależności od wersji programu Finance and Operations wdrożonej w organizacji.

### Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r.
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a> 
Jeśli w organizacji wdrożono oprogramowanie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r., administrator systemu musi opublikować mobilny obszar roboczy **Zatwierdzenie zamówienia zakupu**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

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
<td>Zainstalowanie poprawki KB 4017918.</td>
<td>Administrator systemu</td>
<td>KB 4017918 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Zatwierdzenie zamówienia zakupu</strong>. W celu zainstalowania poprawki KB 4017918 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></li>
</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Zatwierdzenie zamówienia zakupu</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>

## Pobieranie i instalowanie aplikacji mobilnej
<a id="download-and-install-the-mobile-app" class="xliff"></a>
Pobierz i zainstaluj aplikację komórkową Microsoft Dynamics 365 for Unified Operations:

- [Telefony z systemem Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)


## Logowanie do aplikacji mobilnej
<a id="sign-in-to-the-mobile-app" class="xliff"></a>

1. Uruchom aplikację na urządzeniu komórkowym.
2. Wprowadź adres URL usługi Microsoft Dynamics 365.
3. Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

![Obszar roboczy Zatwierdzenie zamówienia zakupu na liście dostępnych obszarów roboczych](./media/po-workspaces.png)

## Wyświetlanie zamówień, które są Ci przypisane
<a id="view-orders-that-are-assigned-to-you" class="xliff"></a>
1. Na urządzeniu przenośnym wybierz obszar roboczy **Zatwierdzenie zamówienia zakupu**.
2. Kliknij opcję **Zamówienia przypisane do mnie**, z zostaną wyświetlone wszystkie zamówienia zakupu, którymi musisz się zająć w przepływie pracy zatwierdzania zamówień zakupu.
3. Zaznacz zamówienie. Na stronie **Szczegóły zamówienia** zobaczysz informacje nagłówka i wiersze zamówienia. W zadaniu przepływu pracy są również wyświetlane wytyczne postępowania.
4. Kliknij opcję **Zasady podziału księgowań**, aby otworzyć stronę **Zasady podziału księgowań dotyczące nagłówka**.
5. Wróć do strony **Szczegóły zamówienia** i zaznacz wiersz. Z poziomu szczegółów wiersza zamówienia możesz też przeglądać zasady podziału księgowań specyficzne dla wiersza.

## Wykonywanie operacji w zamówieniu zakupu
<a id="complete-an-action-on-the-purchase-order" class="xliff"></a>
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

