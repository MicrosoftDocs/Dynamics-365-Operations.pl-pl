---
title: Towary bez zapasów mogą zostać wyewidencjonowane
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.
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
ms.openlocfilehash: af44def901d3aa7d4b24ab6abfac60d066a8d1a3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801754"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Towary bez zapasów mogą zostać wyewidencjonowane

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.

## <a name="description"></a>opis

Użytkownicy mogą dodać towar do koszyka, nawet jeśli w sklepie nie ma dostępnych zapasów, i przejdź do strony realizacji zamówienia.

## <a name="resolution"></a>Rozdzielczość

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a>Włączanie właściwości Pokaż błędy w magazynie w konstruktorze witryn portalu Commerce

Aby włączyć właściwości **Pokaż błędy w magazynie** w konstruktorze witryn portalu Commerce, wykonaj te kroki.

1. Wybierz witrynę, nad która pracujesz.
1. W okienku nawigacji po lewej stronie wybierz pozycję **Strony**.
1. Wybierz pozycję **CartPage**, aby ją otworzyć.
1. Zaznacz gniazdo **Koszyk 1**, wybierz opcję **Edytuj**, a następnie w okienku właściwości zaznacz pole wyboru **Pokaż błędy w magazynie**.
1. Zapisz i opublikuj podgląd strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zastosuj ustawienia zapasów](../inventory-settings.md)

[Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](../calculated-inventory-retail-channels.md)

[Konfigurowanie buforów zapasów i poziomów zapasów](../inventory-buffers-levels.md)
