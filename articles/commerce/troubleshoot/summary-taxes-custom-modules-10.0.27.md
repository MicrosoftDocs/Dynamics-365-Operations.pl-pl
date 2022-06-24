---
title: Suma częściowa podsumowania zamówienia nie uwzględnia podatków od opłat podczas korzystania z niestandardowych modułów podsumowania zamówień
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy używasz niestandardowych modułów podsumowania zamówienia, a suma częściowa podsumowania zamówienia nie zawiera podatków od opłat w scenariuszu "cena zawiera podatek od sprzedaży".
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 260dcb6bc1585615195e32adfcd1da6bfbca294e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848844"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>Suma częściowa podsumowania zamówienia nie uwzględnia podatków od opłat podczas korzystania z niestandardowych modułów podsumowania zamówień

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy używasz niestandardowych modułów podsumowania zamówienia, a suma częściowa podsumowania zamówienia nie zawiera podatków od opłat w scenariuszu "cena zawiera podatek od sprzedaży".

## <a name="description"></a>Opis

Od wersji 10.0.27 Microsoft Dynamics 365 Commerce wprowadzono następujące zmiany w scenariuszu "cena zawiera podatek od sprzedaży", aby zapewnić spójne działanie modułów podsumowujących zamówienia na stronach witryn e-commerce.

- Dodano dwa nowe pola: **TaxOnShippingCharge** i **TaxOnNonShippingCharges**.
- Interfejsy programowania aplikacji (API) **GetSalesOrderBySalesId** i **GetSalesOrderByTransactionId** mają dokładne wartości dla następujących pól w scenariuszu "cena zawiera podatek od sprzedaży":

    - SubtotalSalesAmount
    - SubtotalAmountWithoutTax
    - SubtotalAmount
    - ShippingChargeAmount
    - OtherChargeAmount

Jeśli jednak używasz niestandardowych modułów podsumowujących zamówienia, zmiany te mogą wpłynąć na wartości sum częściowych podsumowania zamówienia, ponieważ nie będą uwzględniać podatków od opłat.

## <a name="resolution"></a>Rozwiązanie

Jeśli używasz niestandardowych modułów podsumowujących zamówienia i nie chcesz dziedziczyć zmian, które zostały wprowadzone do scenariusza "cena zawiera podatek od sprzedaży" w Commerce w wersji 10.0.27 i nowszych, postępuj zgodnie z instrukcjami zawartymi w tej sekcji

Przywracając poprzednie (sprzed wersji 10.0.27) zachowanie pól **salesTransaction.SubtotalAmount** i **salesTransaction.SubtotalAmountWithoutTax** w podsumowaniu zamówienia, przywracasz uwzględnianie całkowitej kwoty podatku (**TaxOnShippingCharge** i **TaxOnNonShippingCharges**) w kwotach cząstkowych (**SubtotalAmount** i **SubtotalAmountWithoutTax**).

Aby powrócić do poprzedniego zachowania podsumowania zamówienia, wykonaj poniższe kroki.

1. W centrali Commerce otwórz stronę z parametrami Commerce (**Handel detaliczny i inny \> Ustawienia centrali \> Parametry \> Parametry Commerce**).
1. W lewym okienku nawigacji wybierz opcję **Parametry konfiguracyjne**.
1. Dodaj następujące parametry konfiguracyjne i ustaw wartość każdego z nich na **true**:

    - IsLegacyTaxOnChargeInSubtotalAmountIncludedInTaxIncusiveEnabled
    - IsLegacyOrderSummaryHydrationEnabled

> [!NOTE]
> Jeśli wcześniej używałeś parametru konfiguracyjnego **IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** i chcesz zachować to samo zachowanie dla właściwości **order.NetAmountWithoutTax**, powinieneś również dodać parametr konfiguracyjny **IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled** i ustawić jego wartość na **true**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Ukrywanie informacji o podziałach podatkowych w podsumowaniach zamówień](../hide-taxes-breakup.md)
