---
title: Moduł szczegółów zamówienia
description: W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
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
ms.openlocfilehash: 5876b953a3b3d960c106acf37731fde13b93f8e7
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661179"
---
# <a name="order-details-module"></a>Moduł szczegółów zamówienia

[!include [banner](includes/banner.md)]

W tym temacie opisano szczegóły modułów potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł szczegółów zamówienia służy do wyświetlania szczegółów potwierdzenia zamówienia po jego złożeniu. Zawiera on identyfikator potwierdzenia zamówienia, informacje kontaktowe zamówienia oraz inne szczegóły zamówienia, takie jak zakupione towary, informacje o płatności oraz metodę wysyłki.

## <a name="order-details-module-properties"></a>Właściwości modułu szczegółów zamówienia

| Nazwa właściwości  | Wartości | opis |
|----------------|--------|-------------|
| Nagłówek        | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Moduł szczegółów zamówienia może mieć nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |
| Numer osoby kontaktowej | Tekst | Numer kontaktowy może być podawany dla pytań związanych z zamówieniami. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Moduły, których można używać na stronie szczegółów zamówienia

Podczas tworzenia strony szczegóły zamówienia można dodać także inne odpowiednie moduły oprócz modułu szczegółów zamówienia. Oto kilka przykładów:

- **Moduł Rekomendacje** — moduł rekomendacji może zostać dodany do strony szczegółów zamówienia w celu zaproponowania odbiorcy innych produktów.
- **Moduły marketingowe** — dowolny moduł marketingowy można dodać do strony Szczegóły zamówień, aby wyświetlić zawartość marketingową.

## <a name="add-an-order-details-module-to-a-page"></a>Dodawanie modułu szczegółów zamówienia do strony

Aby dodać moduł szczegółów zamówienia do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon szczegółów zamówienia**, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Szczegółóy zamówienia** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd szablonu. Moduł szczegółów zamówienia nie będzie renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz opcję **Szablon szczegółów zamówienia**. W sekcji **Nazwa strony** przejdź do **Strona szczegółów zamówienia**, a następnie wybierz przycisk **OK**.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Szczegółóy zamówienia** i wybierz przycisk **OK**.
1. W okienku właściwości modułu szczegółów zamówienia wybierz pozycję **Nagłówek** obok symbolu ołówka.
1. W polu **Tekst nagłówka** okna dialogowego **Nagłówek** wpisz tekst **Szczegóły zamówienia**, a następnie wybierz **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł Opcje dostawy](delivery-options-module.md)

[Moduł karty upominkowej](add-giftcard.md)
