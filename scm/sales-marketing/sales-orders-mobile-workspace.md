---
title: "Mobilny obszar roboczy Zamówienia sprzedaży"
description: "W tym temacie omówiono mobilny obszar roboczy Zamówienia sprzedaży, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Operations. Ten obszar roboczy pomaga być na bieżąco z zamówieniami sprzedaży w dowolnym miejscu i czasie."
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
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 11898146a13756a6bb22a769e37e8773484e0d04
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="sales-orders-mobile-workspace"></a>Mobilny obszar roboczy Zamówienia sprzedaży

[!include[banner](../includes/banner.md)]


W tym temacie omówiono mobilny obszar roboczy Zamówienia sprzedaży, który jest dostępny w aplikacji komórkowej Microsoft Dynamics 365 for Operations. Ten obszar roboczy pomaga być na bieżąco z zamówieniami sprzedaży w dowolnym miejscu i czasie. 

<a name="overview-of-the-sales-orders-mobile-workspace"></a>Omówienie komórkowego obszaru roboczego Zamówienia sprzedaży
---------------------------------------------

Komórkowy obszar roboczy **Zamówienia sprzedaży** uzyskuje dostęp do programu Microsoft Dynamics 365 for Operations i umożliwia przeglądanie szczegółowych informacji o poszczególnych zamówieniach sprzedaży. Informacje te obejmują stan zamówienia, informacje kontaktowe odbiorcy oraz informacje kontaktowe osoby przyjmującej zamówienie. Mobilny obszar roboczy **Zamówienia sprzedaży** zapewnia natychmiastowy podgląd zamówień sprzedaży. Można wyświetlić wszystkie zamówienia sprzedaży, zamówienia dla poszczególnych odbiorców albo informacje o określonym zamówieniu sprzedaży. 

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
Aby można było używać mobilnego obszaru roboczego **Zamówienia sprzedaży**, administrator systemu musi zapewnić spełnienie następujących warunków wstępnych:

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
<td>Jeśli w organizacji jeszcze nie wdrożono programu Dynamics 365 for Operations, administrator systemu powinien przeczytać temat <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment/">Wdrażanie środowiska demonstracyjnego programu Microsoft Dynamics 365 for Operations</a>.</td>
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
<td>Mobilny obszar roboczy <strong>Zamówienia sprzedaży</strong> musi zostać opublikowany w aplikacji komórkowej Dynamics 365 for Operations.</td>
<td>Administrator systemu</td>
<td><ol>
<li>Uruchom program Dynamics 365 for Operations w przeglądarce internetowej.</li>
<li>Na stronie <strong>Parametry systemu</strong> zaznacz opcję <strong>Zarządzaj mobilnymi obszarami roboczymi</strong>.</li>
<li>Wybierz obszar roboczy <strong>Zamówienia sprzedaży</strong>.</li>
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

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-mobile-workspace"></a>Wyświetlanie informacji o zamówieniach sprzedaży dla odbiorcy przy użyciu mobilnego obszaru roboczego
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Zamówienia sprzedaży**.
2.  Wybierz opcję **Wyświetl zamówienia odbiorcy**.
3.  Użyj nazwy konta lub odbiorcy w celu znalezienia żądanego odbiorcy.
4.  Zaznacz odbiorcę.
5.  Wybierz opcję **Informacje kontaktowe** lub **Zamówienia sprzedaży**. Jeśli zaznaczono opcję **Zamówienia sprzedaży**, zostanie wyświetlona lista zamówień sprzedaży dla wybranego odbiorcy.
6.  Wybierz opcję **Zamówienie sprzedaży**. Teraz można obejrzeć informacje o wierszach zamówienia sprzedaży, informacje o wysyłkach, informacje kontaktowe odbiorcy i informacje kontaktowe osoby przyjmującej zamówienie.





