---
title: Opcja pobrania nie jest wyświetlana na stronach szczegółów koszyka lub produktu
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy opcja pobrania w sklepie nie jest wyświetlana na stronie koszyka lub stronach szczegółów produktu.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 46eeed18bb547035603d7e9a01e8f131a2393f01
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801634"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a>Opcja „Odbierz” nie pojawia się na stronach koszyka ani szczegółów produktu

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy opcja pobrania w sklepie nie jest wyświetlana na stronie koszyka lub stronach szczegółów produktu.

## <a name="description"></a>opis

Opcja **Odbierz** nie pojawia się na stronach koszyka ani szczegółów produktu.

Na poniższej ilustracji pokazano przykład strony, która zawiera przycisk **Pobierz**.

![Pobierz ten przycisk](media/pickup-button-missing.jpg)

## <a name="resolution"></a>Rozdzielczość

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a>Włączanie rozszerzenia BOPIS w konstruktorze witryn portalu Commerce

Aby włączyć rozszerzenie „zakup online, odbiór w sklepie” (BOPIS) w Konstruktorze witryn commerce, należy wykonać następujące kroki.

1. Wybieranie witryny.
1. Wybierz **Ustawienia witryny**, a następnie wybierz **Rozszerzenia**.
1. Upewnij się, że opcja **Wyłącz BOPIS** jest wyczyszczona.

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a>Konfigurowanie trybów dostawy w programie Commerce Headquarters

Aby skonfigurować funkcję metod dostawy w siedzibie firmy Commerce, wykonaj następujące kroki.

1. Przejdź do **Zaopatrzenie i sourcing \> Ustawienia \> Metody dostawy**.
1. Upewnij się, że został utworzony tryb dostawy **Odbioru Klienta** oraz że są do niego przypisane produkty i adresy.
1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry**.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Zamówienia klienta**.
1. Upewnij się, że tryb **Metoda dostawy: odbiór** jest poprawnie skonfigurowany.

### <a name="configure-customer-orders-payments"></a>Konfigurowanie płatności zamówień odbiorcy

Aby skonfigurować płatności za zamówienia klientów w centrali Commerce, wykonaj następujące kroki.

1. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry**.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Zamówienia klienta**.
1. Na skróconej karcie **Płatności** upewnij się, że pola **Warunki płatności** i **Metoda płatności** są poprawnie skonfigurowane.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfiguruj BOPIS](../cpe-bopis.md)

[Włączanie wielu metod dostawy dla zamówień klientów](../multiple-pickup-modes.md)

[Płatności zamówień wielokanałowych rozwiązania Commerce](../dev-itpro/commerce-payments.md)

[Moduł wyboru sklepu](../store-selector.md)
