---
title: Strony i moduły zarządzania kontem
description: Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5b26f9f83ad368a7e0fbc0ffe1263a8fec86f99b8a66ee6c4a28d5e061efbc21
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716257"
---
# <a name="account-management-pages-and-modules"></a>Strony i moduły zarządzania kontem

[!include [banner](includes/banner.md)]

Ten temat obejmuje strony i moduły zarządzania kontami w Microsoft Dynamics 365 Commerce.

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

### <a name="my-profile-page"></a>Strona Mój profil

Na stronie Mój profil można wyświetlić szczegóły profilu konta użytkownika, korzystając z modułu profilu konta. Na stronie pokazano adres e-mail skojarzony z kontem użytkownika, a także preferencje ustawione dla tego konta. W przypadku konfigurowania niestandardowych atrybutów odbiorcy, w sekcji „Informacje dodatkowe” są także wyświetlane te atrybuty. Użytkownicy mogą edytować swoje imię i nazwisko, preferencje lub dodatkowe informacje (jeśli są dostępne).

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]