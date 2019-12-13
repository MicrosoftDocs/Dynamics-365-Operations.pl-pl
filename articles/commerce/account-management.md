---
title: Strony i moduły zarządzania kontem
description: Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3986505a7e0e8d33d5b8ff2c06f493335731a8d9
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785395"
---
# <a name="account-management-pages-and-modules"></a>Strony i moduły zarządzania kontem

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Zarządzanie kontami odnosi się do grupy stron służącej do zarządzania informacjami powiązanymi z kontem użytkownika w programie Dynamics 365 Commerce. Strony zarządzania kontami obejmują stronę docelową zarządzanie kontami, atrona profil użytkownika, atrona adres użytkownika, strona historia zamówień, strona szczegóły zamówienia, strona lojalnościowa i strona listy życzeń.

### <a name="account-management-landing-page"></a>Strona docelowa zarządzania kontami

Na stronie docelowej zarządzania kontami są używane następujące moduły:

- **Rozmieszczenie zawartości** — ten moduł to moduł kontenera przechowujący wszystkie moduły na stronie docelowej zarządzania kontami.
- **Element powitalny konta** — ten moduł służy do dostarczania wiadomości powitalnej na stronie zarządzania kontami. Zawiera on właściwości nagłówka i rozmiaru kafelka. Właściwość **Rozmiar kafelka** definiuje szerokość modułu w module umieszczania zawartości. Wartości mieszczą się w zakresie od **1** do **12**, gdzie **12** oznacza pełną szerokość kontenera umieszczania zawartości.
- **Element rozmieszczenia zamówienia konta** — ten moduł służy do podsumowania liczby zamówień ustawionych przez konto użytkownika. Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”. Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony historia zamówień.
- **Element rozmieszczenia profilu konta** — ten moduł służy do podawania podsumowania profilu użytkownika. Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”. Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony profil użytkownika.
- **Pozycja listy życzeń konta** — ten moduł służy do podania podsumowania towarów z listy życzeń odbiorcy. Na przykład może to być stan, „na liście życzeń znajduje się 10 pozycji”. Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”. Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony lista życzeń.
- **Element adresu konta** — ten moduł służy do podawania podsumowania adresu użytkownika. Na przykład może to być stan, „Dwa adresy dodane do konta”. Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły”. Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony adres użytkownika.
- **Pozycja lojalnościowa** — ten moduł służy do wyświetlania informacji o programie lojalnościowym i łączenia ich z tymi informacjami. Zawiera on właściwości nagłówka, rozmiaru kafelka i łącze „wyświetl szczegóły” i łącze „zostań członkiem”. Łącze „wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony program lojalnościowy użytkownika. Łącze „stanie się członkiem” powinno być skonfigurowane tak, aby przekierowywać na stronę, na której użytkownicy mogą dołączać się do programu lojalnościowego.

### <a name="order-history-page"></a>Strona historii zamówień

Strona historia zamówień korzysta z modułu historia zamówień w celu wyświetlenia wszystkich ostatnich zamówień złożonych przez tego użytkownika.

### <a name="order-details-page"></a>Strona szczegółów zamówienia

Strona szczegóły zamówienia zawiera szczegółowe informacje dotyczące poszczególnych zamówień i jest dostępna na stronie historia zamówień. Używa modułu szczegóły zamówienia, który wymaga identyfikatora sprzedaży lub identyfikatora transakcji w celu pobrania szczegółów zamówienia.

### <a name="user-profile-page"></a>Strona profil użytkownika

Na stronie profil użytkownika są wyświetlane szczegóły dotyczące konta użytkownika, takie jak nazwa użytkownika i adres e-mail. Korzysta z niego moduł profilu użytkownika. Chociaż adresu e-mail nie da się usunąć, można go edytować.

### <a name="user-address-page"></a>Strona adres e-mail użytkownika

Na stronie adres użytkownika jest wyświetlana lista adresów skojarzonych z danym kontem użytkownika. Użytkownik albo dostarczył te adresy w trakcie realizacji transakcji, albo dodał je bezpośrednio na tej stronie. Używany jest moduł adres użytkownika służący do dodawania i edytowania adresów, ustawiania adresu podstawowego oraz renderowania istniejących adresów na stronie.

### <a name="wish-list-page"></a>Strona listy życzeń

Na stronie listy życzeń są wyświetlane towary dodane do listy życzeń odbiorcy. Moduł listy życzeń używa do renderowania elementów listy życzeń.

### <a name="loyalty-page"></a>Strona lojalnościowa

Na stronie lojalnościowej odbiorcy można przyłączyć się do programu lojalnościowego lub, jeśli są już członkami programów lojalnościowych, wyświetlać szczegóły dotyczące programu. Mogą również wyświetlać punkty zdobyte i zrealizowane w ostatnich transakcjach.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
