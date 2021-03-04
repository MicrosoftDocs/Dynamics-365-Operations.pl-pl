---
title: Płynny przełącznik offline dla operacji na kartach upominkowych i notach kredytowych
description: Ten temat zawiera przegląd ulepszeń zapewniających płynny przełączenie w tryb offline dla konkretnych typów płatności.
author: rubendel
manager: AnnBe
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0bf37453740d1c2b09b5bd7ae4841f23da20a3ec
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687544"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>Płynny przełącznik offline dla operacji na kartach upominkowych i notach kredytowych

[!include [banner](../includes/banner.md)]

Jeśli urządzenie punktu sprzedaży (POS) utraci połączenie z bazą danych kanału, większość operacji i transakcji punktu sprzedaży, które były w toku, może być kontynuowane po otrzymaniu ostrzeżenia o utracie łączności przez Kasjera. Jednak w niektórych przypadkach transakcje mają elementy, które są zależne od usługi w czasie rzeczywistym, a te elementy nie są obsługiwane, gdy punkt sprzedaży jest w trybie offline. W tym temacie opisano pewne funkcje pomagające zmniejszyć wpływ utraty łączności w tych scenariuszach.

## <a name="completing-gift-card-transactions-in-offline-mode"></a>Zakończenie transakcji kartami upominkowymi w trybie offline

Wewnętrzne karty upominkowe są zależne od usługi w czasie rzeczywistym, ponieważ saldo kart upominkowych musi być centralnie utrzymywane w Microsoft Dynamics 365 Commerce Headquarters. Aby ułatwić zapobieganie nadużyciom finansowym lub innym problemom z synchronizacją, karty upominkowe są blokowane zaraz po ich dodaniu do transakcji. Funkcja blokowania gwarantuje, że karta upominkowa nie może być używana jednocześnie w wielu terminalach. Po zakończeniu transakcji karta upominkowa jest aktualizowana i odblokowywana.

Jeśli jednak w punkcie sprzedaży utraci się łączność po dodaniu karty upominkowej do transakcji, karta upominkowa może stać się niezdatna do użytku. Aby zapobiec tej sytuacji, w Dynamics 365 Commerce istnieje parametr umożliwiający ukończenie transakcji obejmujących wiersz karty upominkowej, gdy punkt sprzedaży jest w trybie offline. Gdy ten parametr jest włączony, transakcje kart upominkowych, które są wymuszane do przejścia w tryb offline, będą zapisywane razem z transakcjami w trybie offline i będą synchronizowane z Centralą Commerce podczas synchronizowania transakcji offline. Synchronizacja spowoduje również odblokowanie karty upominkowej, tak aby można było z niej korzystać w innym terminalu.

Aby włączyć funkcję do zawierania transakcji kart upominkowych po przełączeniu do trybu offline, przejdź na kartę **Księgowanie** na stronie **Parametry rozwiązania Commerce**. Na tej karcie zlokalizuj skróconej karcie **Karty upominkowe** i w **Zezwalaj na zawieranie transakcji kartami upominkowymi w trybie offline** określ wartość **Tak**.

![Ustawienie karty upominkowej w trybie offline](../media/gift.png)

Parametry rozwiązania Commerce są zazwyczaj buforowane. Po zaktualizowaniu tego parametru, harmonogram dystrybucji jest inicjowany w celu zsynchronizowania zmiany w kanale, wprowadzanie zmian może potrwać do 24 godzin. Aby zmiana zaczęła obowiązywać natychmiast, należy zresetować Internet Information Services (IIS) firmy Microsoft.

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>Zakończenie transakcji notą kredytową w trybie offline

Podobnie jak wewnętrzne karty upominkowe, noty kredytowe są obsługiwane centralnie w module Centrali Commerce. W Commerce znajduje się parametr, który umożliwia ukończenie transakcji not kredytowych, gdy punkt sprzedaży jest w trybie offline. Ten parametr działa podobnie do parametru karty upominkowej, który został wymieniony w poprzedniej sekcji. Gdy parametr jest włączony, transakcje noty kredytowej, które są wprowadzane w tryb offline, będą synchronizowane z powrotem do bazy danych kanału oraz z innymi transakcjami wykonanymi, gdy punkt sprzedaży był w trybie offline.

Aby włączyć funkcję do zawierania transakcji notami kredytowymi po przełączeniu do trybu offline, przejdź na kartę **Księgowanie** na stronie **Parametry rozwiązania Commerce**. Na tej karcie zlokalizuj skróconej karcie **Nota kredytowa** i w **Zezwalaj na zawieranie transakcji notami kredytowymi w trybie offline** określ wartość **Tak**.

![Ustawienie noty kredytowej w trybie offline](../media/creditmemo.png)

Parametry rozwiązania Commerce są zazwyczaj buforowane. Po zaktualizowaniu tego parametru, harmonogram dystrybucji jest inicjowany w celu zsynchronizowania zmiany w kanale, wprowadzanie zmian może potrwać do 24 godzin. Aby zmiana zaczęła obowiązywać, należy zresetować usługi IIS.

## <a name="related-topics"></a>Powiązane tematy

- [Funkcjonalność offline punktu sprzedaży (POS)](https://docs.microsoft.com/dynamics365/retail/pos-offline-functionality)
- [Operacje online i offline w punkcie sprzedaży (POS)](https://docs.microsoft.com/dynamics365/retail/pos-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]