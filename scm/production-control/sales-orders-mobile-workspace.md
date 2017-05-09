---
title: "Mobilny obszar roboczy Zamówienia sprzedaży dla aplikacji Microsoft Dynamics 365 for Operations"
description: "Mobilny obszar roboczy zamówień sprzedaży pozwala na bieżąco monitorować zamówienia sprzedaży w dowolnym miejscu i o dowolnej porze."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Mobilny obszar roboczy Zamówienia sprzedaży dla aplikacji Microsoft Dynamics 365 for Operations

Mobilny obszar roboczy zamówień sprzedaży pozwala na bieżąco monitorować zamówienia sprzedaży w dowolnym miejscu i o dowolnej porze. 

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                         | opis                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przeczytaj na temat platformy mobilnej Microsoft Dynamics 365 for Operations | [Platforma komórkowa Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Upewnij się, że używasz środowiska, w którym zainstalowano program Microsoft Dynamics 365 for Operations w wersji 1611 oraz aktualizację nr 3 platformy Microsoft Dynamics 365 for Operations (z listopada 2016 r.). |
| Poprawka KB 3215650                                                    | Zainstaluj poprawkę, która włączy obsługę obszarów roboczych zawartych w usłudze Microsoft Dynamics 365 for Operations.                                                                       |
| Urządzenie przenośne, które ma zainstalowaną aplikację Dynamics 365 for Operations | Pobierz aplikację Dynamics 365 for Operations ze sklepu z aplikacjami dla urządzeń komórkowych.                                                                                                      |

## <a name="overview"></a>Przegląd
Ten mobilny obszar roboczy uzyskuje dostęp do aplikacji Dynamics 365 for Operations i pozwala wyświetlać szczegółowe informacje o każdym zamówieniu sprzedaży, takie jak stan zamówienia, informacje kontaktowe odbiorcy i informacje kontaktowe osoby przyjmującej zamówienie. Mobilny obszar roboczy zapewnia natychmiastowy podgląd zamówień sprzedaży. Można wyświetlić zamówienia sprzedaży z podziałem na odbiorców lub wszystkie zamówienia sprzedaży albo informacje o określonym zamówieniu sprzedaży. Mobilny obszar roboczy oferuje dwa widoki pomagające dogłębnie analizować zamówienia sprzedaży.

### <a name="view-all-sales-orders"></a>Wyświetl wszystkie zamówienia sprzedaży

Ten widok wyświetla listę wszystkich zamówień sprzedaży.

-   Użyj jednego z następujących filtrów, aby wybrać zamówienia sprzedaży, które chcesz obejrzeć.
    -   Wyszukaj wg zamówień sprzedaży
    -   Wyszukaj wg konta odbiorcy
    -   Wyszukaj wg nazwy odbiorcy
    -   Wyszukaj wg stanu
    -   Wyszukaj wg stanu zwolnienia
    -   Wyszukaj wg daty i godziny utworzenia

<!-- -->

-   Po wybraniu zamówień sprzedaży można wyświetlić ich szczegółowe informacje. W szczególności można wyświetlać następujące dane:
    -   Nazwa i informacje adresowe odbiorcy
    -   Różne daty zamówień sprzedaży, takie jak żądana data wysyłki i potwierdzona data wysyłki
    -   Informacje kontaktowe osoby przyjmującej zamówienie
    -   Informacje kontaktowe odbiorcy
    -   Wiersze zamówienia
    -   Wysyłki, które pokazują, jak i kiedy wysłano towary z zamówienia sprzedaży

### <a name="view-orders-for-a-customer-"></a>Wyświetl zamówienia odbiorcy** **

Ten widok pokazuje zamówienia sprzedaży z podziałem na odbiorców.

-   Użyj jednego z następujących filtrów, aby wyświetlić zamówienia wybranego odbiorcy.
    -   Wyszukaj wg nazwy
    -   Wyszukaj wg konta

<!-- -->

-   Po wybraniu odbiorcy można wyświetlić następujące informacje:
    -   Nazwa i grupa odbiorcy
    -   Informacje kontaktowe odbiorcy
    -   Zamówienia sprzedaży odbiorcy i szczegółowe informacje o tych zamówieniach:
        -   Nazwa i informacje adresowe odbiorcy
        -   Różne daty zamówień sprzedaży
        -   Informacje kontaktowe osoby przyjmującej zamówienie
        -   Informacje kontaktowe odbiorcy
        -   Wiersze zamówienia
        -   Wysyłki, które pokazują, jak i kiedy wysłano towary z zamówień sprzedaży

## <a name="get-started"></a>Rozpocznij
Wykonaj poniższe czynności, aby rozpocząć korzystanie z mobilnego obszaru roboczego zamówień sprzedaży na swoim urządzeniu przenośnym.

1.  W sklepie z aplikacjami dla urządzeń komórkowych pobierz i zainstaluj aplikację Microsoft Dynamics 365 for Operations.
2.  Uruchom aplikację na urządzeniu.
3.  Wprowadź adres URL usługi Dynamics 365.
4.  Wpisz firmę, do której chcesz się zalogować. Na przykład wpisz **USMF**.
5.  Podczas pierwszego logowania zostanie wyświetlony monit o podanie nazwy użytkownika i hasła dostępu do konta programu Microsoft Dynamics 365 for Operations. Wprowadź swoje poświadczenia. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy.

Aby widzieć obszary robocze w aplikacji mobilnej, należy najpierw opublikować żądane obszary w aplikacji Dynamics 365 for Operations.

1.  Uruchom program Dynamics 365 for Operations.
2.  Wybierz kolejno opcje **Administrowanie systemem** &gt; **Ustawienia** &gt; **Parametry systemu**.
3.  Wybierz opcję **Zarządzaj aplikacją mobilną**.
4.  Wybierz obszar roboczy, aby go opublikować na platformie mobilnej.
5.  Wybierz opcję **Opublikuj obszar roboczy**.
6.  Odśwież swoje urządzenie, a zobaczysz opublikowane obszary robocze.

## <a name="view-information-about-sales-orders-for-a-customer"></a>Wyświetlanie informacji o zamówieniach sprzedaży wybranego odbiorcy
1.  Na urządzeniu przenośnym wybierz obszar roboczy **Zamówienia sprzedaży**.
2.  Wybierz opcję **Wyświetl zamówienia odbiorcy**.
3.  Użyj pól **Konto** i **Nazwa odbiorcy** w celu znalezienia żądanego odbiorcy.
4.  Zaznacz odbiorcę.
5.  Wybierz opcję **Informacje kontaktowe** lub **Zamówienia sprzedaży**.
6.  Jeśli zaznaczono opcję **Zamówienia sprzedaży**, zostanie wyświetlona lista zamówień sprzedaży dla wybranego odbiorcy.
7.  Wybierz opcję **Zamówienie sprzedaży**.
8.  W tym miejscu można obejrzeć informacje o wierszach zamówienia sprzedaży, dane wysyłek, informacje kontaktowe odbiorcy i informacje kontaktowe osoby przyjmującej zamówienie.




