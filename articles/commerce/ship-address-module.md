---
title: Moduł adresu wysyłki
description: W tym temacie omówiono moduł adresu wysyłki i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2021
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
ms.openlocfilehash: 30baef62e03cdaa766133efc4b182c61da3dc7b67e077d80716a035f0b5e40e2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765201"
---
# <a name="shipping-address-module"></a>Moduł adresu wysyłki

[!include [banner](includes/banner.md)]

W tym temacie omówiono moduł adresu wysyłki i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.

Moduł adresu wysyłki umożliwia klientom dodanie lub wybranie adresu wysyłki dla zamówienia podczas realizacji transakcji. Jeśli klient jest zalogowany, wszystkie adresy, które zostały wcześniej zapisane dla tego klienta, są wyświetlane, a klient może wybrać jeden z nich. Odbiorca może również dodać nowy adres. Moduł adresu wysyłki jest używany dla wszystkich pozycji w zamówieniu, które wymagają wysyłki.

Formaty adresów wysyłkowych można definiować w module Commerce Headquarter dla każdego kraju lub regionu, a moduł adresów wysyłkowych wymusza reguły specyficzne dla kraju/regionu.

Gdy odbiorcy wprowadzają adres wysyłkowy podczas procesu realizacji transakcji, mają możliwość zapisania adresu jako adresu podstawowego. Ta opcja jest wyświetlana tylko wtedy, gdy odbiorca jest zalogowany do systemu.

Chociaż moduł adresu wysyłki nie zapewnia weryfikacji adresu, tę funkcję można wdrożyć poprzez dostosowanie.

Poniższa ilustracja przedstawia przykład nowego modułu adresu wysyłki na stronie kasy.

![Przykład modułu adresu wysyłki na stronie realizacja zamówienia.](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Właściwości modułu

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Opcjonalny nagłówek modułu adresu wysyłki. |
| Pokaż typ adresu | **Prawda** lub **Fałsz** | Jeśli ta właściwość opcjonalna ma wartość **Prawda**, wyświetlany jest typ adresu, np. **Dom** lub **Firma**. Jeśli nie określono typu adresu, adres zostanie automatycznie zapisany jako **Typ**=**Inny**. |
| Włącz automatyczne sugestie| **Prawda** lub **Fałsz** | Jeśli dla tej opcjonalnej właściwości zostanie ustawiona wartość **Prawda**, zostaną dostarczone automatyczne sugestie adresów. Te sugestie są oparte na mapach Bing. Aby uzyskać informacje dotyczące sposobu skonfigurowania integracji Map Bing dla swojej witryny, zobacz moduł [Selektor sklepu](store-selector.md). Ta funkcja jest dostępna w wersji Commerce 10.0.15.|
|Opcje automatycznych sugestii| Numer| Jeśli funkcja automatycznych sugestii adresów jest włączona, można określić dodatkowe opcje, takie jak maksymalna liczba sugerowanych danych.|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Dodaj moduł adresu wysyłki do strony realizacji zamówienia i ustaw wymagane właściwości

Moduł adresu wysyłki można dodać tylko do modułu realizacji transakcji. Aby uzyskać więcej informacji na temat konfigurowania modułu adresu wysyłki i dodania go do strony realizacji transakcji, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł opcji dostawy](delivery-options-module.md)

[Moduł informacji o odbiorze](pickup-info-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Moduł karty upominkowej](add-giftcard.md)

[Moduł wyboru sklepu](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]