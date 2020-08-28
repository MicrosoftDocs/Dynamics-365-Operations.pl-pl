---
title: Moduł płatności
description: W tym temacie omówiono moduł płatności i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f4f6baa3c4a42a2994cab772c98d373996e2648b
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661221"
---
# <a name="payment-module"></a>Moduł płatności

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie omówiono moduł płatności i wyjaśniono, jak go skonfigurować w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Odbiorcy przysługujący modułowi płatności płacą za zamówienia za pomocą kart kredytowych lub debetowych. Integrację płatności dla tego modułu zapewnia Dynamics 365 Payment Connector dla Adyen. Aby uzyskać więcej informacji na temat konfigurowania i konfigurowania łącznika płatności, zobacz temat [Łącznik płatności usługi Dynamics 365 dla Adyen](dev-itpro/adyen-connector.md).

Moduł płatności obsługuje informacje o płatności, które są obsługiwane za pośrednictwem Adyen w ramce w wierszu HTML (iframe). Moduł płatności współdziała z Commerce Scale Unit, aby pobrać informacje o płatności Adyen. W ramach interakcji Commerce Scale Unit moduł płatności może umożliwić podawanie informacji o adresie rozliczeniowym w ramce iframe lub jako oddzielny moduł. W motywie Fabrikam adres bilingowy jest pokazywany w oddzielnym module. Takie podejście pozwala na większą elastyczność formatowania, ponieważ wiersze adresu mogą być renderowane w taki sposób, aby były podobne do wierszy adresu wysyłkowego.

Ponadto moduł płatności umożliwia odbiorcom zalogowanych zapisanie informacji o płatności. Informacje o płatności i adres rozliczeniowy są zapisywane i zarządzane za pośrednictwem łącznika płatności Adyen.

Moduł płatności obejmuje wszelkie opłaty za zamówienia, które nie są jeszcze objęte punktami lojalnościowymi lub kartami upominkowymi. Jeśli suma dla zamówienia jest w pełni objęta punktami lojalnościowymi lub kredytami upominkowymi, moduł płatności zostanie ukryty, a odbiorca będzie mógł je złożyć bez tego zamówienia.

Złącze płatności Adyen obsługuje również silne uwierzytelnianie klienta (SCA). Część dyrektywy Unii Europejskiej (UE) w sprawie usług płatniczych 2.0 (PSD2.0) wymaga, aby kupujący online byli uwierzytelniani poza doświadczeniem związanym z zakupami online, gdy używają elektronicznej metody płatności. Podczas przepływu realizacji transakcji odbiorcy są przekierowywani do swoich oddziałów bankowych. Następnie po uwierzytelnieniu są przekierowywani z powrotem do przepływu realizacji transakcji w usłudze Commerce. Podczas tego przekierowania informacje, które klient wprowadził w procesie realizacji transakcji (na przykład adres wysyłki, opcje dostawy, informacje o karcie upominkowej i informacje o lojalności) zostaną zachowane. Aby można było włączyć tę funkcję, łącznik płatności musi być skonfigurowany dla SCA w module Commerce Headquarter. Aby uzyskać więcej informacji, zajrzyj do [silnych uwierzytelnień klientów przy użyciu Adyen](adyen_redirect.md).

Poniższa ilustracja przedstawia przykład karty upominkowej, modułów lojalnościowych i płatności na stronie kasy.

![Przykład karty podarunkowej, modułów lojalnościowych i płatności na stronie kasy](./media/ecommerce-payments.PNG)

## <a name="payment-module-properties"></a>Właściwości modułu płatności

| Nazwa właściwości | Wartości | opis |
|---------------|--------|-------------|
| Nagłówek | Tekst nagłówka | Opcjonalny nagłówek modułu płatności. |
| Wysokość ramki iframe | Piksele | Wysokość ramki iframe (w pikselach). W razie potrzeby można regulować wysokość. |
| Pokaż adres do faktury | **Prawda** lub **Fałsz** | Jeśli dla tej właściwości ustawiono wartość **Prawda**, adres bilingowy będzie obsługiwany przez Adyen w module iframe modułu płatności. Jeśli zostanie ustawiona wartość **Fałsz**, adres bilingowy nie będzie obsługiwany przez Adyen, a użytkownik Commerce musi skonfigurować moduł w celu wyświetlenia adresu na fakturze na stronie realizacja zamówienia. |
| Zastąpienie stylu płatności | Kod arkuszy stylów kaskadowych (CSS) | Ponieważ moduł płatności jest obsługiwany w iframe, istnieje ograniczona możliwość tworzenia stylów. Aby uzyskać więcej stylów, należy użyć tej właściwości. Aby zastąpić style witryny, musisz wkleić kod CSS jako wartość tej właściwości. Zastąpienia i style konstruktora witryn CSS nie mają zastosowania do tego modułu. |

## <a name="billing-address"></a>Adres na fakturze

Odbiorcy na moduł płatności zapewniają adres bilingowy dla swoich informacji o płatności. Ponadto pozwala im wykorzystać adresy wysyłkowe jako adres bilingowy, aby ułatwić i przyspieszyć przepływ realizacji transakcji. Jeśli **Właściwość pokazuj adres bilingowy** ma wartość **Fałsz**, moduł płatności powinien być skonfigurowany na stronie realizacja zamówienia.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Dodaj moduł płatności do strony kasy i ustaw wymagane właściwości

Moduł płatności można dodać tylko do modułu realizacji transakcji. Aby uzyskać więcej informacji na temat konfigurowania modułu płatności dla strony kasy, zapoznaj się z tematem [Moduł realizacji transakcji](add-checkout-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł Opcje dostawy](delivery-options-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Moduł karty upominkowej](add-giftcard.md)

[Łącznik płatności usługi Dynamics 365 dla Adyen](dev-itpro/adyen-connector.md)

[Silne uwierzytelnianie klienta za pomocą Adyen](adyen_redirect.md)
