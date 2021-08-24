---
title: Błąd synchronizacji zamówienia związany z domyślną usługą płatności
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.
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
ms.openlocfilehash: 6f8e0ea7675ffc5cbada36207422b410234e33afcaec90636e90e573a90ac484
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715243"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Błąd synchronizacji zamówienia związany z domyślną usługą płatności

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.

## <a name="description"></a>opis

Podczas synchronizowania zamówienia online wyświetlany jest następujący komunikat o błędzie: „Do przetwarzania transakcji kartami kredytowymi musi być domyślna usługa płatności”.

![Brak domyślnego błędu usługi płatności.](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Rozwiązanie

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Potwierdź lub ustaw domyślną usługę płatności w programie Commerce Headquarters

Aby potwierdzić lub ustawić domyślną usługę płatności w Commerce headquarters, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia płatności \> Usługi płatności**.
1. Upewnij się, że w ustawieniach **domyślnego procesora dla nowych kart kredytowych** jest ustawiona wartość **Tak** dla jednej usługi płatności.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfiguracja, autoryzacja i przechwytywanie karty kredytowej](../../finance/accounts-receivable/credit-card-authorizations.md)