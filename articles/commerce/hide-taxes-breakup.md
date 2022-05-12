---
title: Ukryj informacje o podziale podatku w podsumowaniach zamówień
description: W tym temacie opisano, jak ukryć informacje o podziale podatku w podsumowaniach zamówień na stronach koszyka, kasy, potwierdzenia zamówienia i szczegółów zamówienia w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 9890b5cd92f8c07e6feabb26f4fdd076cb7a02bc
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645222"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Ukryj informacje o podziale podatku w podsumowaniach zamówień

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym temacie opisano, jak ukryć informacje o podziale podatku w podsumowaniach zamówień na stronach koszyka, kasy, potwierdzenia zamówienia i szczegółów zamówienia w Microsoft Dynamics 365 Commerce.

Domyślnie Dynamics 365 Commerce pokazuje informacje o podziale podatku w podsumowaniach zamówień na stronach koszyka, kasy, potwierdzenia zamówienia i szczegółów zamówienia. Od wersji Commerce 10.0.27 kreator stron Commerce zawiera opcję, która pozwala ukryć informacje o podziale podatku w podsumowaniach zamówień.

Poniższa ilustracja przedstawia przykład dwóch podsumowań zamówień. Pierwsza z nich pokazuje informacje o podziale podatku, a druga je ukrywa.

![Przykłady wózków, w których informacje o podziale podatku są widoczne i ukryte.](media/prices-include-sales-tax-e-Commerce.png)

> [!NOTE]
> - Opcja ukrywania informacji o podziale podatku w podsumowaniach zamówień jest dostępna tylko wtedy, gdy opcja **Ceny zawierają podatek od sprzedaży** dla kanału e-commerce jest ustawiona na **Tak** w centrali Commerce, w zakładce **Retail i Commerce \> Kanały \> Sklepy \> Wszystkie sklepy**. 
> - Domyślnie opcja **Pokaż podział na podatki w podsumowaniu zamówienia** jest włączona w kreatorze stron.

## <a name="hide-tax-breakup-information-in-order-summaries"></a>Ukryj informacje o podziale podatku w podsumowaniach zamówień

Aby ukryć informacje o rozbiciu podatku w podsumowaniach zamówień, wykonaj poniższe kroki.

1. W kreatorze witryn Commerce przejdź do witryny, którą chcesz zaktualizować.
1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. Wyczyść pole wyboru **Pokaż podział podatków w podsumowaniu zamówienia**.

Aby pokazać informacje o podziale podatku w podsumowaniach zamówień, zaznacz pole wyboru **Pokaż podział na podatki w podsumowaniu zamówienia**.  

Poniższa ilustracja przedstawia pole wyboru **Pokaż rozbicie podatków w podsumowaniu zamówienia** zaznaczone i wybrane w module budowania witryny.

![Pokaż podział na podatki w opcji podsumowania zamówienia w kreatorze witryn.](media/prices-include-sales-tax-e-Commerce-site-settings.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie podatku](/finance/general-ledger/indirect-taxes-overview)

[Konfigurowanie podatku dla zamówień online](sales-tax-config.md)

[Rozwiązywanie problemów: Podatki w zamówieniach online są niepoprawnie obliczone](troubleshoot/tax-miscalculated-online-order.md)
