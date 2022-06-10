---
title: Mobilny obszar roboczy Zamówienia sprzedaży
description: Ten temat zawiera informacje o komórkowym obszarze roboczym Zamówienia sprzedaży. Ten obszar roboczy pomaga być na bieżąco z zamówieniami sprzedaży w dowolnym miejscu i czasie.
author: Henrikan
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: be9fd32f5f5d80bb9bce5f0de7e4ff92d6f5d28f
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811575"
---
# <a name="sales-orders-mobile-workspace"></a>Mobilny obszar roboczy Zamówienia sprzedaży

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Ten temat zawiera informacje o komórkowym obszarze roboczym **Zamówienia sprzedaży**. Ten obszar roboczy pomaga być na bieżąco z zamówieniami sprzedaży w dowolnym miejscu i czasie. 

Ten mobilny obszar roboczy jest przeznaczony do używania w mobilnych aplikacjach finansowych i operacyjnych (Dynamics 365).

## <a name="overview"></a>Omówienie
Mobilny obszar roboczy **Zamówienia sprzedaży** umożliwia przeglądanie szczegółowych informacji o poszczególnych zamówieniach sprzedaży. Informacje te obejmują stan zamówienia, informacje kontaktowe odbiorcy oraz informacje kontaktowe osoby przyjmującej zamówienie. Mobilny obszar roboczy **Zamówienia sprzedaży** zapewnia natychmiastowy podgląd zamówień sprzedaży. Można wyświetlić wszystkie zamówienia sprzedaży, zamówienia dla poszczególnych odbiorców albo informacje o określonym zamówieniu sprzedaży. 

Mobilny obszar roboczy oferuje dwa widoki pomagające dogłębnie analizować zamówienia sprzedaży.

### <a name="view-all-sales-orders"></a>Wyświetl wszystkie zamówienia sprzedaży
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

### <a name="view-orders-for-a-customer"></a>Wyświetl zamówienia odbiorcy
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

## <a name="prerequisites"></a>Wymagania wstępne
Wymagania wstępne różnią się w zależności od wersji systemu Microsoft Dynamics 365 wdrożonej w organizacji.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Warunki wstępne, jeśli jest używane Supply Chain Management 
Jeśli w organizacji wdrożono oprogramowanie Supply Chain Management, administrator systemu musi opublikować mobilny obszar roboczy **Zamówienia sprzedaży**. Instrukcje znajdziesz w temacie [Publikowanie mobilnego obszaru roboczego](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Warunki wstępne w przypadku korzystania z Dynamics 365 for Operations w wersji 1611 z aktualizacją platformy 3 lub nowszą
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
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Pobierz poprawkę metadanych z usługi Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Zainstaluj poprawkę metadanych</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Utwórz wdrażalny pakiet</a> zawierający model <strong>SCMMobile</strong>, a następnie przekaż ten wdrażalny pakiet do usługi LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Zastosuj wdrażalny pakiet</a></li>

</ol></td>
</tr>
<tr class="even">
<td>Opublikowanie mobilnego obszaru roboczego <strong>Zamówienia sprzedaży</strong>.</td>
<td>Administrator systemu</td>
<td>Zobacz <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publikowanie mobilnego obszaru roboczego</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej
Pobierz i zainstaluj mobilne aplikacje finansowe i operacyjne (Dynamics 365):

-   [Telefony Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej

1.  Uruchom aplikację na urządzeniu komórkowym.
2.  Wprowadź adres URL usługi Dynamics 365.
3.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.
4.  Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, trzeba odświeżyć listę komórkowych obszarów roboczych.

[![Ściąganie w celu odświeżenia.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>Wyświetlanie informacji o zamówieniach sprzedaży dla odbiorcy przy użyciu mobilnego obszaru roboczego Zamówienia sprzedaży

1.  Na urządzeniu przenośnym wybierz obszar roboczy **Zamówienia sprzedaży**.
2.  Wybierz opcję **Wyświetl zamówienia odbiorcy**.
3.  Użyj nazwy konta lub odbiorcy w celu znalezienia żądanego odbiorcy.
4.  Zaznacz odbiorcę.
5.  Wybierz opcję **Informacje kontaktowe** lub **Zamówienia sprzedaży**. Jeśli zaznaczono opcję **Zamówienia sprzedaży**, zostanie wyświetlona lista zamówień sprzedaży dla wybranego odbiorcy.
6.  Wybierz opcję **Zamówienie sprzedaży**. Teraz można obejrzeć informacje o wierszach zamówienia sprzedaży, informacje o wysyłkach, informacje kontaktowe odbiorcy i informacje kontaktowe osoby przyjmującej zamówienie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
