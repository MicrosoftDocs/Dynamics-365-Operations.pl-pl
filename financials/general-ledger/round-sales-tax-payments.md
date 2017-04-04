---
title: "Reguły płatności podatkowych i zaokrąglania"
description: "W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: 8f28ab4ea0fed975edbed60ddf5630d2d26ba0bc
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-payments-and-rounding-rules"></a>Reguły płatności podatkowych i zaokrąglania

W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.

Okresowo należy zgłaszać i płacić podatek w urzędzie skarbowym. To jest możliwe przez uruchomienie Rozlicz i po procesie podatku w stronę podatku od sprzedaży. Podatek od sprzedaży za okres zostaną rozliczone dla konta podatku od sprzedaży i Saldo podatku zostanie zaksięgowana na koncie rozliczenie podatku. Saldo podatku, który jest księgowany na koncie rozliczenie podatku, może być zaokrąglane zgodnie z wymogami urzędu skarbowego przez skonfigurowanie reguły zaokrąglania na stronie podatku od sprzedaży. 

Różnica wynikająca z zaokrąglenia jest księgowana na koncie zaokrąglania podatku wybranym w polu Konta do transakcji automatycznych w księdze głównej.

Poniższy przykład pokazuje mechanizm działania reguły zaokrąglania na potrzeby urzędu skarbowego.

### <a name="example"></a>Przykład:

Łączny podatek za okres zawiera saldo faktury w wysokości -98 765,43. Podmiot prawny zebrał więcej podatku, niż zapłacił. Z tego względu firma jest winna pieniądze urzędowi skarbowemu. 

Firma chce użyć metody zaokrąglania, która zaokrągla saldo do najbliższego 1,00 EUR. Użytkownik odpowiedzialny za księgowanie podatku musi wykonać następujące czynności:

1.  Kliknij opcję Podatek &gt;podatków pośrednich &gt;podatku &gt;urzędów skarbowych
2.  Na skróconej karcie Ogólne zaznacz opcję Normalne w polu Metoda zaokrąglenia.
3.  W polu Zaokrąglenie wpisz 1,00.
4.  Gdy przyjdzie czas zapłacenia podatku urzędowi skarbowemu, otwórz stronę Rozlicz i zaksięguj podatek. (Kliknij przycisk podatku &gt;deklaracje &gt;podatku &gt;rozliczenia i księgowanie podatku od sprzedaży.)
5.  Na koncie rozliczenie podatku kwota zobowiązań z tytułu podatku 98 765,43 jest zaokrąglana do 98 765.

W poniższej tabeli przedstawiono, jak kwota 98 765,43 jest zaokrąglana przy użyciu każdej metody zaokrąglania, która jest dostępna w polu Metoda zaokrąglania na stronie urzędu skarbowego.

| Zaokrąglanie z opcji                | Wartość zaokrąglenia = 0,01 | Wartość zaokrąglenia = 0,10 | Wartość zaokrąglenia = 1,00 | Wartość zaokrąglenia = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normalna                              | 98 765,43              | 98 765,40              | 98 765,00              | 98 800,00                |
| W dół                            | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Zaokrąglenie w górę                         | 98 765,43              | 98 765,50              | 98 766,00              | 98 800,00                |
| Na korzyść firmy, salda kredytowe | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Na korzyść firmy, salda debetowe  | 98 765,43              | 98 765,50              | 98 766,00              | 98 800,00                |

> [!NOTE]                                                                                  
> Jeśli wybierzesz Na korzyść firmy, zaokrąglanie jest zawsze na korzyść firmy. 

Aby uzyskać więcej informacji, zobacz [omówienie podatku](indirect-taxes-overview.md). 


