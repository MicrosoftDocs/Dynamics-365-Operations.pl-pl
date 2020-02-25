---
title: Moduł szczegółów zamówienia
description: W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026024"
---
# <a name="order-details-module"></a>Moduł szczegółów zamówienia


[!include [banner](includes/banner.md)]

W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł szczegółów zamówienia służy do wyświetlania szczegółów potwierdzenia zamówienia po jego złożeniu. Zawiera on identyfikator potwierdzenia zamówienia, informacje kontaktowe zamówienia oraz inne szczegóły zamówienia, takie jak zakupione towary, informacje o płatności oraz metodę wysyłki.

## <a name="order-confirmation-module-properties"></a>Właściwości modułu potwierdzenia zamówienia

| Nazwa właściwości  | Wartości | Opis |
|----------------|--------|-------------|
| Nagłówek        | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Moduł potwierdzający zamówienie może mieć nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |
| Numer osoby kontaktowej | Tekst | Numer kontaktowy może być podawany dla pytań związanych z zamówieniami. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Moduły, których można używać na stronie szczegółów zamówienia

Podczas tworzenia strony szczegóły zamówienia można dodać także inne odpowiednie moduły oprócz modułu szczegółów zamówienia. Oto kilka przykładów:

- **Moduł Rekomendacje** — moduł rekomendacji może zostać dodany do strony szczegółów zamówienia w celu zaproponowania odbiorcy innych produktów.
- **Moduły marketingowe** — dowolny moduł marketingowy można dodać do strony Szczegóły zamówień, aby wyświetlić zawartość marketingową.

## <a name="create-an-order-details-page-module"></a>Tworzenie modułu strony szczegółów zamówienia

1. Utwórz szablon strony o nazwie nazwa **szablon szczegółów zamówienia**.
1. W gnieździe **Główne** na stronie domyślnej dodaj moduł szczegółów zamówienia.
1. W module szczegóły zamówienia dodaj moduł rekomendacji.
1. Zapisz i zobacz podgląd szablonu. Moduł szczegółów zamówienia nie będzie renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.
1. Zakończ edytowanie szablonu i opublikuj go.
1. Za pomocą utworzonego właśnie szablonu szczegółów zamówienia utwórz stronę o nazwie **strona szczegółów zamówienia**.
1. Dodaj stronę domyślną do konspektu strony.
1. W gnieździe **nagłówka** w dodaj fragment nagłówka.
1. W gnieździe **stopki** w dodaj fragment stopki.
1. W gnieździe **Główne** dodaj moduł szczegółów zamówienia.
1. W okienku właściwości dla modułu szczegółów zamówienia dodaj nagłówek **Szczegóły zamówienia**.
1. Poniżej modułu szczegółów zamówienia dodaj moduł rekomendacji i skonfiguruj go tak, aby korzystał z ustawień list **Nowości** i **Bestsellery**.
1. Zapisz i zobacz podgląd strony.
1. Zakończ edytowanie strony i opublikuj go.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
