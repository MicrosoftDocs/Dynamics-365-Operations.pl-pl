---
title: Moduł ikony koszyka
description: W tym artykule opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: e35b0ee5341b8b5531ad2c80c868ca4c07ebd315
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280510"
---
# <a name="cart-icon-module"></a>Moduł ikony koszyka

[!include [banner](includes/banner.md)]

W tym artykule opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł ikon koszyka reprezentuje koszyk w module nagłówka strony i pokazuje liczbę pozycji w koszyku. Moduł ikony koszyka wyświetla także podsumowanie koszyka (znane również jako mini wózek), gdy ikona wózka jest najechana kursorem. Mini koszyk zapewnia użytkownikowi podsumowanie pozycji w koszyku bez konieczności przechodzenia do strony koszyka. Ponadto pozwala również użytkownikowi przejść bezpośrednio do strony kasy, jeśli jest zadowolony z podsumowania. Zmniejsza to liczbę nawigacji na stronach i przyspiesza finalizację transakcji. 

Poniższy obraz pokazuje przykład modułu ikony koszyka, który wyświetla mini koszyk w nagłówku Fabrikam.

![Przykład modułu na ikonie koszyka.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Właściwości modułu

- **Wyświetlanie koszyka mini** — gdy ma wartość **True**, ta właściwość umożliwia wyświetlenie podsumowania koszyka (w postaci najmniejszego koszyka) po najechaniu myszą na koszyk. Ta funkcja jest obsługiwana tylko w przypadku portów widoku pulpitu.
- **Zezwól na anonimowe przejście do kasy** – Kiedy ta właściwość jest ustawiona na **True**, mini koszyk pozwala użytkownikom, którzy nie są zalogowani na przejście do kasy, jako gość. Ta właściwość jest dostępna w wersji Commerce 10.0.21, jako część pakietu biblioteki modułów Commerce.
- **Kolejność elementów** — ta właściwość kontroluje kolejność, w jakiej elementy są wyświetlane w mini koszyku. Po wybraniu opcji **Nowe elementy dodane do górnej części listy**, nowe produkty, które są dodawane do koszyka, pojawiają się u góry listy elementów mini koszyka. Po wybraniu domyślnej opcji **Nowe elementy dodane do dolnej części listy**, nowe produkty, które są dodawane do koszyka, pojawiają się na dole listy elementów mini koszyka. Ta właściwość jest dostępna w wersji Commerce 10.0.21, jako część pakietu biblioteki modułów Commerce.

> [!IMPORTANT]
> Właściwości **Zezwól na anonimowe przejście do kasy** i **Kolejność elementów** są dostępne od wersji Commerce w wersji 10.0.21. Wymagają pakietu biblioteki modułów Commerce w wersji 9.31.

## <a name="module-properties-and-slots-in-the-adventure-works-theme"></a>Właściwości i gniazda modułu w motywie Adventure Works

W motywie Adventure Works moduł ikon koszyka zawiera dwa dodatkowe miejsca na mini wózek. Gniazda te są uwzględniane jako rozszerzenie definicji modułu.

- **Opróżnij promocje w koszyku** — w tym gnieździe jest zablokowany moduł zawartości. Gdy koszyk jest pusty, wyświetlany jest określony moduł blokowania zawartości. Modułu blokowania zawartości można używać w przypadku promocji, zawartości marketingowej i łączy do stron kategorii, aby ułatwić klientom kontynuowanie zakupów.
- **Zawartość promocyjna** — tego gniazda można używać do awansów, takich jak „Bezpłatne wysyłki w przypadku zamówień $100” Moduły bloku treści, bloku tekstowego i listy obrazów mogą być używane w gnieździe zawartości promocyjnej.

Poniższy obraz przedstawia przykład modułu ikony koszyka w motywie Adventure Works, który wyświetla zawartość promocyjną w minikoszyku.

![Przykład modułu ikony koszyka w kompozycji Adventure Works](./media/AW_minicart.PNG)

> [!IMPORTANT]
> Gniazda motywów Adventure Works są dostępne od wersji Dynamics 365 Commerce 10.0.20.

## <a name="add-a-cart-icon-module-to-a-page"></a>Dodawanie modułu ikonu koszyka do strony

Aby dodać moduł ikony koszyka, zobacz [Moduł nagłówka](author-header-module.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł opcji dostawy](delivery-options-module.md)

[Moduł informacji o odbiorze](pickup-info-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Moduł karty upominkowej](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
