---
title: Moduł ikony koszyka
description: W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9e3850d98e716d1bbea2017f6e8c9d75f19adc9
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638008"
---
# <a name="cart-icon-module"></a>Moduł ikony koszyka

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł ikon koszyka reprezentuje koszyk w module nagłówka strony i pokazuje liczbę pozycji w koszyku. Moduł ikony koszyka wyświetla także podsumowanie koszyka (znane również jako mini wózek), gdy ikona wózka jest najechana kursorem. Mini koszyk zapewnia użytkownikowi podsumowanie pozycji w koszyku bez konieczności przechodzenia do strony koszyka. Ponadto pozwala również użytkownikowi przejść bezpośrednio do strony kasy, jeśli jest zadowolony z podsumowania. Zmniejsza to liczbę nawigacji na stronach i przyspiesza finalizację transakcji. 

Poniższy obraz pokazuje przykład modułu ikony koszyka, który wyświetla mini koszyk w nagłówku Fabrikam.

![Przykład modułu na ikonie koszyka.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Właściwości modułu

- **Wyświetlanie koszyka mini** — gdy ma wartość prawda, ta właściwość umożliwia wyświetlenie podsumowania koszyka (w postaci najminiego koszyka) po aktywowaniu ikony koszyka. Ta funkcja jest obsługiwana tylko w przypadku portów widoku pulpitu.

## <a name="module-properties-in-the-adventure-works-theme"></a>Właściwości modułu w motywie Adventure Works

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
