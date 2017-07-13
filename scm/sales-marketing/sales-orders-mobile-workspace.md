---
title: "Mobilny obszar roboczy Zamówienia sprzedaży"
description: "Ten temat zawiera informacje o komórkowym obszarze roboczym Zamówienia sprzedaży. Ten obszar roboczy pomaga być na bieżąco z zamówieniami sprzedaży w dowolnym miejscu i czasie."
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
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: a0edbad63c51d111d7c8985aa7fdf7312da6149d
ms.openlocfilehash: 1a05c6c12d4b6d98886e418aadcc0bdb2c2fc8ef
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Mobilny obszar roboczy Zamówienia sprzedaży
<a id="sales-orders-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Zamówienia sprzedaży**. Ten obszar roboczy pomaga być na bieżąco z zamówieniami sprzedaży w dowolnym miejscu i czasie. 

Ten mobilny obszar roboczy jest przeznaczony do używania w aplikacji komórkowej Microsoft Dynamics 365 for Unified Operations.

## Przegląd
<a id="overview" class="xliff"></a>
Mobilny obszar roboczy **Zamówienia sprzedaży** umożliwia przeglądanie szczegółowych informacji o poszczególnych zamówieniach sprzedaży. Informacje te obejmują stan zamówienia, informacje kontaktowe odbiorcy oraz informacje kontaktowe osoby przyjmującej zamówienie. Mobilny obszar roboczy **Zamówienia sprzedaży** zapewnia natychmiastowy podgląd zamówień sprzedaży. Można wyświetlić wszystkie zamówienia sprzedaży, zamówienia dla poszczególnych odbiorców albo informacje o określonym zamówieniu sprzedaży. 

Mobilny obszar roboczy oferuje dwa widoki pomagające dogłębnie analizować zamówienia sprzedaży.

### Wyświetl wszystkie zamówienia sprzedaży
<a id="view-all-sales-orders" class="xliff"></a>
Ten widok wyświetla listę wszystkich zamówień sprzedaży.

-   Użyj jednego z następujących filtrów, aby wybrać zamówienia sprzedaży do wyświetlenia:

    -   Wyszukaj wg zamówień sprzedaży
    -   Wyszukaj wg konta odbiorcy
    -   Wyszukaj wg nazwy odbiorcy
    -   Wyszukaj wg stanu
    -   Wyszukaj wg stanu zwolnienia
    -   Wyszukaj wg daty i godziny utworzenia
    
-   Po wybraniu zamówień sprzedaży można wyświetlić ich szczegółowe informacje. W szczególności można wyświetlić następujące informacje:

    -   Nazwa i informacje adresowe odbiorcy
    -   Różne daty dotyczące zamówienia sprzedaży, takie jak żądana data wysyłki i potwierdzona data wysyłki
    -   Informacje kontaktowe osoby przyjmującej zamówienie
    -   Informacje kontaktowe odbiorcy
    -   Wiersze zamówienia
    -   Wysyłki, które pokazują, jak i kiedy wysłano towary z zamówienia sprzedaży

### Wyświetl zamówienia odbiorcy
<a id="view-orders-for-a-customer" class="xliff"></a>
Ten widok pokazuje zamówienia sprzedaży z podziałem na odbiorców.

-   Użyj jednego z następujących filtrów, aby wyświetlić zamówienia wybranego odbiorcy:

    -   Wyszukaj wg nazwy
    -   Wyszukaj wg konta

-   Po wybraniu odbiorcy można wyświetlać następujące informacje:

    -   Nazwa i grupa odbiorcy
    -   Informacje kontaktowe odbiorcy
    -   Zamówienia sprzedaży odbiorcy i szczegółowe informacje o tych zamówieniach:
    
        -   Nazwa i informacje adresowe odbiorcy
        -   Różne daty dotyczące zamówień sprzedaży
        -   Informacje kontaktowe osoby przyjmującej zamówienie
        -   Informacje kontaktowe odbiorcy
        -   Wiersze zamówienia
        -   Wysyłki, które pokazują, jak i kiedy wysłano towary z zamówienia sprzedaży

## Wymagania wstępne
<a id="prerequisites" class="xliff"></a>
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### Warunki wstępne, jeśli jest używany program Microsoft Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r.
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a> 
Jeśli w organizacji wdrożono oprogramowanie Dynamics 365 for Finance and Operations Enterprise Edition z aktualizacją z lipca 2017 r., administrator systemu musi opublikować mobilny obszar roboczy **Zamówienia sprzedaży**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### Warunki wstępne, jeśli jest używany program Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
<a id="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later" class="xliff"></a>
Jeśli w organizacji wdrożono oprogramowanie Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą, administrator systemu musi wykonać następujące zadania wstępne. 

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

<td>KB 4013633 jest aktualizacją platformy języka X++ lub poprawką metadanych, która zawiera mobilny obszar roboczy <strong>Zamówienia sprzedaży</strong>. W celu zainstalowania poprawki KB 4013633 administrator systemu musi wykonać następującą procedurę:
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Zamówienia sprzedaży</strong>.</td>
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

## Wyświetlanie informacji o zamówieniach sprzedaży dla odbiorcy przy użyciu mobilnego obszaru roboczego Zamówienia sprzedaży
<a id="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace" class="xliff"></a>

1.  Na urządzeniu przenośnym wybierz obszar roboczy **Zamówienia sprzedaży**.
2.  Wybierz opcję **Wyświetl zamówienia odbiorcy**.
3.  Użyj nazwy konta lub odbiorcy w celu znalezienia żądanego odbiorcy.
4.  Zaznacz odbiorcę.
5.  Wybierz opcję **Informacje kontaktowe** lub **Zamówienia sprzedaży**. Jeśli zaznaczono opcję **Zamówienia sprzedaży**, zostanie wyświetlona lista zamówień sprzedaży dla wybranego odbiorcy.
6.  Wybierz opcję **Zamówienie sprzedaży**. Teraz można obejrzeć informacje o wierszach zamówienia sprzedaży, informacje o wysyłkach, informacje kontaktowe odbiorcy i informacje kontaktowe osoby przyjmującej zamówienie.

