---
title: Korekty ceny i rabaty
description: Ten artykuł zawiera informacje dotyczące korekt cen i rabatów w Dynamics 365 Commerce.
author: scott-tucker
ms.date: 06/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 44c03ae0a04d648e788a72d8f6dcc3671c5736c7
ms.sourcegitcommit: 7c9d6be464db058511df9cb6ba162d21dc0554e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/11/2021
ms.locfileid: "6240949"
---
# <a name="price-adjustments-and-discounts"></a>Korekty ceny i rabaty

[!include [banner](includes/banner.md)]

Ten artykuł zawiera informacje dotyczące korekt cen i rabatów w Dynamics 365 Commerce.

W Commerce możesz korygować ceny produktów, a także skonfigurować rabaty stosowane do towaru lub transakcji w punkcie sprzedaży, zamówienia sprzedaży (POS) w biurze obsługi lub zamówienia online. Do grup cen mogą być podłączone zarówno korekty ceny i rabaty. Zarówno w przypadku korekty ceny, jak i rabatów, można określić pojedynczy datę rozpoczęcia i datę zakończenia lub okres cykliczny, kod rabatu i kilka dodatkowych atrybutów. 

Korekty ceny i rabaty mogą dotyczyć produktów, wariantów lub kategorii. W przypadku zastosowania więcej niż jednego rabatu do produktu odbiorca może otrzymać jeden rabat lub rabat połączony. Commerce automatycznie zastosuje rabat lub kombinację rabatów oferującą odbiorcy najlepszą cenę. Podczas ustawiania korekty ceny lub rabatu należy sprawdzić, czy grupy cen są przypisane do właściwych kanałów, katalogów, przynależności lub programów lojalnościowych, do których ma mieć zastosowanie rabat. Ponadto jeśli chcesz automatycznie wygenerować identyfikator rabatu, możesz ustawić sekwencje numerów na stronie **Parametry handlu** zanim zdefiniujesz nowy rabat lub korektę ceny lub rabat.

> [!NOTE]
> Korekty ceny lub rabaty można usunąć. Jednak informacje statystyczne zostaną utracone.

## <a name="types-of-discounts"></a>Typy rabatów

Istnieje wiele typów rabatów:

- **Prosty rabat** — pojedynczy procent lub kwota.
- **Rabat ilościowy** — stosowany przy zakupie co najmniej dwóch produktów.
- **Rabat łączony** — stosowany przy zakupie określonej kombinacji produktów.
- **Rabat progowy** — stosowany przy sumie transakcji powyżej określonej kwoty.
- **Rabat oparty na metodach płatności** — Rabat stosowany w przypadku, gdy suma transakcji jest większa niż określona kwota i określony typ płatności (na przykład gotówka, karta kredytowa lub debetowa) jest używany do celów płatności.
- **Rabat wysyłkowy** — Rabat stosowany, gdy suma transakcji przekracza określoną kwotę, a zamówienie jest objęte określonym sposobem dostawy (na przykład dostawa w ciągu dwóch dni lub dostawa z dnia na dzień).

Z grupami cen mogą być skojarzone zarówno korekty ceny i rabaty. Grupy cen mogą być następnie skojarzone z kanałami, katalogami, przynależnościami i programami lojalnościowymi.

> [!NOTE]
> Rabat typu „mieszaj dowolnie” oraz rabat progowy posiadają właściwości o nazwach odpowiednio „Licz produkty niedyskontowalne” oraz „Licz produkty niedyskontowalne względem progu”. Jeśli te właściwości są włączone, pozycja, która nie kwalifikuje się do żadnej zniżki, może nadal pomóc zakwalifikować transakcję do zniżki, ale niekwalifikująca się pozycja nie otrzyma zniżki. 
> 
> Na przykład, jeśli utworzysz rabat typu „mieszaj dowolnie” z dwoma liniami, A i B, gdzie klient powinien otrzymać 10% zniżki na obie pozycje, ale pozycja A ma zaznaczoną konfigurację „Zapobiegaj wszystkim rabatom”, to typowo uniemożliwiłoby to uwzględnienie pozycji A w rabacie. Jeśli jednak włączona jest właściwość „Licz produkty niedyskontowalne”, wówczas pozycja A może zostać użyta do uzyskania rabatu „mieszaj dowolnie”, ale rabat 10% zostanie zastosowany tylko do pozycji B. Podobna logika dotyczy rabatu progowego. 
>
> Właściwość „Licz produkty niedyskontowalne do progu” ma jednak dodatkową możliwość w porównaniu z właściwością „Licz produkty niedyskontowalne” dla rabatów typu „mieszaj dowolnie”. Jeśli rabat progowy jest włączony i jeśli istnieje pozycja, która ma istniejący rabat, który uniemożliwiłby tej pozycji jakiekolwiek inne rabaty, wtedy cena zapłacona za tę pozycję będzie kwalifikować się do spełnienia progu, ale ta pozycja nie otrzyma dodatkowego rabatu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
