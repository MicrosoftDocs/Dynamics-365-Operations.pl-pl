---
title: Rekordy odbiorcy nie są wyświetlane w programie Commerce Headquarters
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy rekordy klientów nie są natychmiast wyświetlane w programie Commerce Headquarters.
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
ms.openlocfilehash: 5cdc96c9829be4d34e9346b2c99d300c2349bc41
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876552"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Rekordy odbiorcy nie są wyświetlane w programie Commerce Headquarters

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy rekordy klientów nie są natychmiast wyświetlane w programie Commerce Headquarters.

## <a name="description"></a>opis

Gdy tworzysz nowy rekord odbiorcy za pomocą przepływu rejestracji w sklepie e-commerce, odpowiadający mu rekord odbiorcy nie zostanie natychmiast wyświetlony w programie Commerce Headquarters.

## <a name="resolution"></a>Rozdzielczość

### <a name="disable-customer-creation-in-async-mode"></a>Wyłącz tworzenie odbiorcy w trybie asynchronicznym

> [!IMPORTANT]
> Wyłączenie asynchronicznego tworzenia odbiorcy może mieć wpływ na wydajność systemu, ponieważ utworzenie każdego rekordu spowoduje utworzenie żądania w czasie rzeczywistym do programu Commerce Headquarters. Ponadto jeśli w programie Commerce Headquarters zostanie u dołu (na przykład podczas przepływów obsługi), wszelkie nowe przepływy tworzenia odbiorcy będą powodować błędy.

Aby wyłączyć tworzenie odbiorcy w trybie asynchronicznym w programie Commerce Headquarters, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia sklepu online \> Profile funkcji**.
1. Jeśli nie używasz jeszcze profilu funkcji kanału online, utwórz go.
1. Upewnij się, że opcja **Utwórz klienta w trybie asynchronicznym** ma wartość **Nie**.
1. Wybierz kolejno opcje **Commerce \> Kanały \> Sklepy internetowe**.
1. Wybierz sklep internetowy, dla których chcesz wyłączyć asynchroniczne tworzenie odbiorcy.
1. Na karcie **Ogólne** upewnij się, że w polu **Profil funkcji** jest ustawiony profil funkcji, który jest ustawiony dla kanału online.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie dzierżawy B2C w module Commerce](../set-up-b2c-tenant.md)
