---
title: Typem płatności musi być błąd karty kredytowej na stronie zamówienia sprzedaży
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy po zsynchronizowaniu zamówienia na stronie zamówienia sprzedaży zostanie wyświetlony komunikat o błędzie.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: 20f18507dee330fd1affedeee092b3dfa7cc10bc
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585484"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>Błąd „Typ płatności musi być kartą kredytową” na stronie zamówienia sprzedaży

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku, gdy po zsynchronizowaniu zamówienia na stronie zamówienia sprzedaży zostanie wyświetlony komunikat o błędzie.

## <a name="description"></a>opis

Po otwarciu strony zamówienia sprzedaży po zsynchronizowaniu zamówienia pojawia się następujący komunikat o błędzie: „Typ płatności musi być kartą kredytową, ponieważ określono numer karty kredytowej”.

![Typem płatności musi być błąd karty kredytowej](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Rozdzielczość

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Ustawianie typu płatności w programie Commerce Headquarters

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia płatności \> Warunki płatności**.
1. W lewym okienku wybierz warunki płatności.
1. Upewnij się, że w polu **Typ płatności** wybrano **Kartę kredytową**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Księgowanie sprzedaży i płatności online](../tasks/posting-online-sales-payments.md)
