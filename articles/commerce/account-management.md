---
title: Strony i moduły zarządzania kontem
description: Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: b0f963bcf65ae622522fe52fd59996c6ec0ecf17
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414861"
---
# <a name="account-management-pages-and-modules"></a>Strony i moduły zarządzania kontem

[!include [banner](includes/banner.md)]

Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Zarządzanie kontami odnosi się do grupy stron służącej do zarządzania informacjami powiązanymi z kontem użytkownika w programie Dynamics 365 Commerce. Strony zarządzania kontami obejmują stronę docelową zarządzanie kontami, atrona profil użytkownika, atrona adres użytkownika, strona historia zamówień, strona szczegóły zamówienia, strona lojalnościowa i strona listy życzeń.

### <a name="account-management-landing-page"></a>Strona docelowa zarządzania kontami

Na stronie docelowej zarządzania kontami są używane następujące moduły:

- **Kontener** — wszystkie moduły strony ładunkowej modułu Zarządzanie kontami powinny być umieszczone w kontenerze. 
- **Kafelek powitalny konta** — ten moduł służy do dostarczania wiadomości powitalnej na stronie zarządzania kontami. Zawiera on właściwości nagłówka.
- **Ogólny kafelek konta** — ten moduł może służyć do udostępniania nagłówków i łączy do stron zarządzania kontami, np. stron historia zamówień lub „Mój profil”. Moduł kafelków ogólnych może być używany do konfigurowania kafelków na dowolnej stronie. W firmie Fabrikam ten moduł jest używany w łączach stron „Historia zamówień” i „Mój profil” na stronie spocznik zarządzania kontami.
- **Kafelek listy życzeń konta** — ten moduł służy do podania podsumowania towarów z listy życzeń odbiorcy. Na przykład może to być stan, „na liście życzeń znajduje się 10 pozycji”. Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”. Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony lista życzeń. 
- **Kafelek adresu konta** — ten moduł służy do podawania podsumowania adresu użytkownika. Na przykład może to być stan, „Dwa adresy dodane do konta”. Zawiera on właściwości nagłówka i łącze „Wyświetl szczegóły”. Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony adres użytkownika.
- **Kafelek lojalnościowy konta** — ten moduł służy do wyświetlania informacji o programie lojalnościowym i łączenia ich z tymi informacjami. Ten kafelek ma dwa stany: jeden stan przedstawia łącza, aby przyłączyć się do karty lojalnościowej, jeśli użytkownik nie jest już członkiem progamu. W innym stanie są wyświetlane łącza umożliwiające wyświetlenie strony szczegóły dotyczące lojalności, gdy użytkownik jest już członkiem. Właściwości obejmują nagłówek, łącze „Zarejestruj się” i łącze „Wyświetl lojalność”. Łącze „Wyświetl szczegóły” powinno być skonfigurowane do przekierowywania do strony program lojalnościowy użytkownika. Łącze „Zarejestruj się” powinno być skonfigurowane tak, aby przekierowywać na stronę, na której użytkownicy mogą dołączać się do programu lojalnościowego. 

### <a name="order-history-page"></a>Strona historii zamówień

Strona historia zamówień korzysta z modułu historia zamówień w celu wyświetlenia wszystkich ostatnich zamówień złożonych przez tego użytkownika.

### <a name="order-details-page"></a>Strona szczegółów zamówienia

Strona szczegóły zamówienia zawiera szczegółowe informacje dotyczące poszczególnych zamówień i jest dostępna na stronie historia zamówień. Używa modułu szczegóły zamówienia, który wymaga identyfikatora sprzedaży lub identyfikatora transakcji w celu pobrania szczegółów zamówienia.

### <a name="user-profile-page"></a>Strona profil użytkownika

Na stronie profilu użytkownika są wyświetlane szczegóły dotyczące konta użytkownika, takie jak nazwa użytkownika i adres e-mail. Używa on szczegółów profilu użytkownika i modułu edytuj profil użytkownika. Chociaż adresu e-mail nie da się usunąć, można go edytować. Strona profilu użytkownika zawiera także preferencje użytkownika, które umożliwiają użytkownikowi włączenie lub rezygnację z niektórych funkcji, takich jak personalizacja list rekomendacji. 

### <a name="user-address-page"></a>Strona adres e-mail użytkownika

Na stronie adres użytkownika jest wyświetlana lista adresów skojarzonych z danym kontem użytkownika. Użytkownik albo dostarczył te adresy w trakcie realizacji transakcji, albo dodał je bezpośrednio na tej stronie. Używany jest moduł adres użytkownika służący do dodawania i edytowania adresów, ustawiania adresu podstawowego oraz renderowania istniejących adresów na stronie.

### <a name="wish-list-page"></a>Strona listy życzeń

Na stronie listy życzeń są wyświetlane towary dodane do listy życzeń odbiorcy. Moduł listy życzeń używa do renderowania elementów listy życzeń.

### <a name="loyalty-page"></a>Strona lojalnościowa

Na stronie lojalnościowej odbiorcy można zobaczyć szczegóły programu lojalnościowego lub, jeśli są już członkami programów lojalnościowych. Mogą również wyświetlać punkty zdobyte i zrealizowane w ostatnich transakcjach. Na stronie jest używany moduł szczegóły lojalnościowe w celu pokazania szczegółów dotyczących lojalności. 

Aby dołączyć do programu lojalnościowego, strona marketingowa może zostać utworzona za pomocą konta lojalnościowego i modułów zasad lojalności. Jeśli użytkownik nie jest członkiem programu lojalnościowego, moduły te pozwolą użytkownikowi zarejestrować się.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
