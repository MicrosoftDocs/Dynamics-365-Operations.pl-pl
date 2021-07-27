---
title: Moduł Opcje dostawy
description: W tym temacie omówiono moduły opcji dostarczania i wyjaśniono, jak je skonfigurować w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: af8cd65565a50341b0bf2dba84204d010486532c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350457"
---
# <a name="delivery-options-module"></a>Moduł opcji dostawy

[!include [banner](includes/banner.md)]

W tym temacie omówiono moduły opcji dostarczania i wyjaśniono, jak je skonfigurować w Microsoft Dynamics 365 Commerce.

Moduły opcji dostawy umożliwiają klientom wybranie metody dostawy, np. wysyłki lub odbioru, na potrzeby zamówienia online. Adres wysyłkowy jest wymagany w celu określenia metody dostawy. W przypadku zmiany adresu dostawy należy ponownie pobrać opcje dostawy. Jeśli zamówienie uwzględnia tylko towary, które zostaną odebrane w sklepie, ten moduł jest automatycznie ukrywany.

Aby uzyskać informacje dotyczące konfigurowania metod dostawy, należy zapoznać się z tematem [Konfiguracja kanału online](channel-setup-online.md) i [Ustaw metody dostawy](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Z każdym z trybów dostawy można przypisana opłata. Więcej informacji na temat konfigurowania opłat za sklep internetowy, należy zapoznać się z [Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md).

W programie Commerce w wersji 10.0.13 moduł opcji dostawy został zaktualizowany w taki sposób, aby obsługiwał funkcje **Opłata za nagłówek bez podziału** i **Wysyłka jako opłata liniowa**. Jeśli dopuszczalna wartość jest wyłączona, oczekuje się, że przepływ pracy w module handlu elektronicznego nie pozwoli na przetworzenie trybu dostawy dla towarów w koszyku (tzn. niektóre towary są wybierane do wysyłki, ale inne są wybierane do odbioru). Funkcja **Opłata za nagłówek bez podziału** wymaga włączenia flagi **Włącz obsługę spójnego trybu dostawy w kanale** w centrali Commerce. Po włączeniu tej flagi funkcji opłaty transportowe będą stosowane na poziomie nagłówka lub na poziomie wiersza, w zależności od konfiguracji w centrali Commerce.

Kompozycja Fabrikam obsługuje tryb mieszany dostawy, w którym niektóre towary są wybierane do wysyłki, ale inne zostały wybrane do pobrania. W tym trybie opłaty za wysyłkę będą klasyfikowane dla wszystkich towarów, które zostały wybrane w trybie dostawy. Aby można było korzystać z mieszanej metody dostawy, należy najpierw skonfigurować funkcję **Opłata za nagłówek bez podziału** w module Commerce Headquarter. Aby uzyskać więcej informacji o tej konfiguracji, przejrzyj [Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży](pro-rate-charges-matching-lines.md).

Jeśli opłaty transportowe mają zastosowanie do towarów w wierszach, można je wyświetlić w wierszu koszyka dla każdego towaru. Ta funkcja wymaga włączenia właściwości **Pokazuj pozycję online opłat za wysyłkę** dla modułu koszyka i modułu realizacji transakcji. Aby uzyskać więcej informacji, zobacz [Moduł koszyka](add-cart-module.md) i [Moduł realizacji transakcji](add-checkout-module.md).

Poniższa ilustracja pokazuje przykład opcji dostawy na stronie realizacji zamówienia.

![Przykład modułu opcji dostawy na stronie realizacja zamówienia.](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Właściwości modułu Opcje dostawy

| Właściwość | Wartości | opis |
|----------|--------|-------------|
| Nagłówek | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Opcjonalny nagłówek modułu opcje dostawy. |
| Niestandardowa nazwa klasy CSS | Tekst | Niestandardowa nazwa klasy arkuszy stylów kaskadowych (CSS), która będzie używana do renderowania tego modułu (jeśli ma zastosowanie). |
| Filtruj opcję trybu dostawy | **Nie filtruj** lub **Tryby bez wysyłki** | Wartość określająca, czy moduł opcji dostawy powinien filtrować wszystkie tryby dostaw inne niż wysyłkowe. |
| Automatyczne wybieranie opcji dostawy | **Nie filtruj**, **Automatycznie wybierz opcję dostawy i pokaż podsumowanie** lub **Automatycznie wybierz opcję dostawy i nie pokazuj podsumowania** | Ta właściwość automatycznie stosuje pierwszą dostępną opcję dostawy do realizacji zamówienia bez wymogu wybrania jej przez użytkownika. Należy jej używać tylko w przypadku, gdy istnieje jedna dostępna opcja dostawy. Ta właściwość jest obsługiwana od wersji 10.0.19 programu Commerce. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Dodaj moduł opcji dostawy do strony realizacji zamówienia i ustaw wymagane właściwości

Moduł opcji dostawy można dodać tylko do modułu realizacji transakcji. Aby uzyskać więcej informacji na temat konfigurowania modułu opcji dostawy i dodania go do strony realizacji transakcji, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł informacji o odbiorze](pickup-info-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Moduł karty upominkowej](add-giftcard.md)

[Konfiguracja kanału online](channel-setup-online.md)

[Wielokanałowe zaawansowane opłaty automatyczne](omni-auto-charges.md)

[Proporcjonalne dzielenie opłat z nagłówka między pasujące wiersze sprzedaży](pro-rate-charges-matching-lines.md)

[Ustaw metody dostawy](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
