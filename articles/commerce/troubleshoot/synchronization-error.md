---
title: Błąd synchronizacji zamówienia związany z domyślną usługą płatności
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.
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
ms.openlocfilehash: 45eeae751051b58e1c9e725eb4ed4b5240026e7f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801442"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Błąd synchronizacji zamówienia związany z domyślną usługą płatności

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemu, który może wystąpić podczas synchronizacji zamówienia online.

## <a name="description"></a>opis

Podczas synchronizowania zamówienia online wyświetlany jest następujący komunikat o błędzie: „Do przetwarzania transakcji kartami kredytowymi musi być domyślna usługa płatności”.

![Brak domyślnego błędu usługi płatności](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Rozdzielczość

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Potwierdź lub ustaw domyślną usługę płatności w programie Commerce Headquarters

Aby potwierdzić lub ustawić domyślną usługę płatności w Commerce headquarters, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Ustawienia płatności \> Usługi płatności**.
1. Upewnij się, że w ustawieniach **domyślnego procesora dla nowych kart kredytowych** jest ustawiona wartość **Tak** dla jednej usługi płatności.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfiguracja, autoryzacja i przechwytywanie karty kredytowej](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
