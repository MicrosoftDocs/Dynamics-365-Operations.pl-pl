---
title: Moduł potwierdzenia zamówienia
description: W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698333"
---
# <a name="order-confirmation-module"></a>Moduł potwierdzenia zamówienia

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich tworzenia w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł potwierdzenia zamówienia służy do wyświetlania komunikatu potwierdzającego na stronie potwierdzenia zamówienia po złożeniu zamówienia. W module potwierdzenia zamówienia wyświetlany jest numer potwierdzenia zamówienia oraz adres e-mail odbiorcy dostarczony podczas realizacji transakcji.

Jeśli zamówienie zostanie wykonane podczas procesu realizacji transakcji, numer potwierdzenia zamówienia i adres e-mail odbiorcy są przekazywane do strony potwierdzenia zamówienia jako ciąg kwerendy w adresie URL strony. Moduł potwierdzenie zamówienia odbiera te informacje i renderuje stan zamówienia na stronie potwierdzenia zamówienia. W module potwierdzenia zamówienia do podania stanu zamówienia wymagany jest kontekst strony.

## <a name="order-confirmation-module-properties"></a>Właściwości modułu potwierdzenia zamówienia

| Nazwa właściwości | Wartości | Opis |
|---------------|--------|-------------|
| Nagłówek       | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Moduł potwierdzający zamówienie może mieć nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a>Moduły, których można używać w module strony potwierdzenia zamówienia 

- **Rekomendacje** — moduł rekomendacji może zostać umieszczony na stronie potwierdzenia zamówienia w celu zaproponowania innym produktom odbiorcy.
- **Marketing** — moduł marketingowy umożliwia dodanie zawartości marketingowej do strony potwierdzenia zamówienia.

## <a name="create-an-order-confirmation-page-module"></a>Tworzenie strony modułu potwierdzenia zamówienia

1. Utwórz szablon strony o nazwie nazwa **szablon potwierdzenia zamówienia**.
1. W **Głównym** gnieździe na stronie domyślnej dodaj moduł potwierdzenia zamówienia.
1. W module potwierdzenia zamówienia dodaj moduł rekomendacji
1. Zapisz i zobacz podgląd szablonu. Moduł potwierdzenia zamówienia nie powinien być renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.
1. Zaewidencjonuj szablon i opublikuj go.
1. Za pomocą utworzonego właśnie szablonu potwierdzenia zamówienia utwórz stronę o nazwie **strona potwierdzenia zamówienia**.
1. Dodaj stronę domyślną do konspektu strony.
1. W gnieździe **nagłówka** w dodaj fragment nagłówka.
1. W gnieździe **stopki** w dodaj fragment stopki.
1. W **Głównym** gnieździe dodaj moduł potwierdzenia zamówienia.
1. W okienku właściwości modułu potwierdzenie zamówienia dodaj nagłówek **potwierdzenie zamówienia**.
1. Poniżej modułu potwierdzenia zamówienia Dodaj moduł rekomendacji i skonfiguruj go tak, aby korzystał z ustawień list **Nowości** i **Bestsellery**.
1. Zapisz i zobacz podgląd strony, zaewidencjonuj ją i opublikuj.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
