---
title: Ukrywanie informacji o podziałach podatkowych w podsumowaniach zamówień
description: W tym artykule opisano, jak ukryć informacje o podziale podatku w podsumowaniach zamówień na stronach koszyka, kasy, potwierdzenia zamówienia i szczegółów zamówienia w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 669534a6611860ac73439460afedce341310cc7d
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027342"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Ukrywanie informacji o podziałach podatkowych w podsumowaniach zamówień

[!include [banner](includes/banner.md)]

W tym artykule opisano, jak ukryć informacje o podziale podatku w podsumowaniach zamówień na stronach koszyka, kasy, potwierdzenia zamówienia i szczegółów zamówienia w Microsoft Dynamics 365 Commerce.

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

> [!NOTE]
> Jeśli masz niestandardowe moduły podsumowujące zamówienia i nie chcesz odziedziczyć funkcji "ukrywania informacji o wysokości podatku w podsumowaniach zamówień" w Commerce w wersji 10.0.27 lub nowszej, zobacz [Suma częściowa podsumowania zamówienia nie zawiera podatków od opłat, gdy używasz niestandardowych modułów podsumowania zamówienia](troubleshoot/summary-taxes-custom-modules-10.0.27.md#resolution).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie podatku](/finance/general-ledger/indirect-taxes-overview)

[Konfigurowanie podatku dla zamówień online](sales-tax-config.md)

[Rozwiązywanie problemów: Podatki w zamówieniach online są niepoprawnie obliczone](troubleshoot/tax-miscalculated-online-order.md)
