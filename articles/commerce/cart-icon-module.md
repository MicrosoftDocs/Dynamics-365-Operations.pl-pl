---
title: Moduł ikony koszyka
description: W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ebc5cfa490a4c8538fd081aced0844ed01d63a26
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415100"
---
# <a name="cart-icon-module"></a>Moduł ikony koszyka

[!include [banner](includes/banner.md)]

W tym temacie opisano moduł ikony koszyka i opisano, jak dodać go do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł ikon koszyka reprezentuje koszyk w module nagłówka strony i pokazuje liczbę pozycji w koszyku. Moduł ikony koszyka wyświetla także podsumowanie koszyka (znane również jako mini wózek), gdy ikona wózka jest najechana kursorem. Mini koszyk zapewnia użytkownikowi podsumowanie pozycji w koszyku bez konieczności przechodzenia do strony koszyka. Ponadto pozwala również użytkownikowi przejść bezpośrednio do strony kasy, jeśli jest zadowolony z podsumowania. Zmniejsza to liczbę nawigacji na stronach i przyspiesza finalizację transakcji. 

> [!NOTE]
> Obsługa korzystania z modułu ikon koszyka w Dynamics 365 Commerce w wydaniu 10.0.11.

Poniższy obraz pokazuje przykład modułu ikony koszyka, który wyświetla mini koszyk w nagłówku Fabrikam.

![Przykład modułu na ikonie koszyka](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Właściwości modułu

- **Wyświetlanie koszyka mini** — gdy ma wartość prawda, ta właściwość umożliwia wyświetlenie podsumowania koszyka (w postaci najminiego koszyka) po aktywowaniu ikony koszyka. Ta funkcja jest obsługiwana tylko w przypadku portów widoku pulpitu.

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