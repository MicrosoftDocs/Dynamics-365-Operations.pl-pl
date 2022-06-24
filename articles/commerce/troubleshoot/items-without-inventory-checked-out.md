---
title: Towary bez zapasów mogą zostać wyewidencjonowane
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 24400953d2a17384be8ab3000aa829bf2bcb7192
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877192"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Towary bez zapasów mogą zostać wyewidencjonowane

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc klientom w dodaniu towarów poza zapasami do koszyka i kontynuowaniu realizacji zamówienia.

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
