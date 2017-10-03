---
title: "Reguły płatności podatkowych i zaokrąglania"
description: "W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: c4f5dae90c5fcaaa52a7087d7c20b2de343b7da0
ms.openlocfilehash: 8de01b77fcbeb65321e60614b6a11d264460208f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/01/2017

---

# <a name="sales-tax-payments-and-rounding-rules"></a>Reguły płatności podatkowych i zaokrąglania

[!include[banner](../includes/banner.md)]


W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.

Okresowo należy zgłaszać i płacić podatek w urzędzie skarbowym. Można to zrobić, uruchamiając proces rozliczenia i księgowania podatku na stronie Podatek. Podatek od sprzedaży w danym okresie zostanie rozliczony dla kont podatku, a saldo podatku zostanie zaksięgowane na koncie rozliczenia podatku. Saldo podatku, który jest księgowany na koncie rozliczenie podatku, może być zaokrąglane zgodnie z wymogami urzędu skarbowego przez skonfigurowanie reguły zaokrąglania na stronie podatku od sprzedaży. 

Różnica wynikająca z zaokrąglenia jest księgowana na koncie zaokrąglania podatku wybranym w polu Konta do transakcji automatycznych w księdze głównej.

Poniższy przykład pokazuje mechanizm działania reguły zaokrąglania na potrzeby urzędu skarbowego.

### <a name="example"></a>Przykład:

Łączny podatek za okres zawiera saldo faktury w wysokości -98 765,43. Podmiot prawny zebrał więcej podatku, niż zapłacił. Z tego względu firma jest winna pieniądze urzędowi skarbowemu. 

Firma chce użyć metody zaokrąglania, która zaokrągla saldo do najbliższego 1,00 EUR. Użytkownik odpowiedzialny za księgowanie podatku musi wykonać następujące czynności:

1.  Wybierz kolejno opcje Podatek &gt; Podatki pośrednie &gt; Podatek &gt; Urzędy skarbowe.
2.  Na skróconej karcie Ogólne zaznacz opcję Normalne w polu Metoda zaokrąglenia.
3.  W polu Zaokrąglenie wpisz 1,00.
4.  Gdy przyjdzie czas zapłacenia podatku urzędowi skarbowemu, otwórz stronę Rozlicz i zaksięguj podatek. (Wybierz kolejno opcje Podatek &gt; Deklaracje &gt; Podatek &gt; Rozlicz i zaksięguj podatek).
5.  Na koncie rozliczenie podatku kwota zobowiązań z tytułu podatku 98 765,43 jest zaokrąglana do 98 765.

W poniższej tabeli przedstawiono, jak kwota 98 765,43 jest zaokrąglana przy użyciu każdej metody zaokrąglania, która jest dostępna w polu Metoda zaokrąglania na stronie urzędu skarbowego.

| Zaokrąglanie z opcji                | Wartość zaokrąglenia = 0,01 | Wartość zaokrąglenia = 0,10 | Wartość zaokrąglenia = 1,00 | Wartość zaokrąglenia = 100,00 |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| Normalna                              | 98 765,43              | 98 765,40              | 98 765,00              | 98 800,00                |
| W dół                            | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Zaokrąglenie w górę                         | 98 765,43              | 98 765,50              | 98 766,00              | 98 800,00                |
| Na korzyść firmy, salda kredytowe | 98 765,43              | 98 765,40              | 98 765,00              | 98 700,00                |
| Na korzyść firmy, salda debetowe  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                |

> [!NOTE]                                                                                  
> Jeśli wybierzesz Na korzyść firmy, zaokrąglanie jest zawsze na korzyść firmy. 

Aby uzyskać więcej informacji, zobacz następujące tematy:
- [Omówienie podatku](indirect-taxes-overview.md)
- [Tworzenie płatności podatku](tasks/create-sales-tax-payment.md)
- [Tworzenie transakcji sprzedaży w dokumentach](tasks/create-sales-tax-transactions-documents.md)
- [Wyświetlanie zaksięgowanych transakcji podatkowych](tasks/view-posted-sales-tax-transactions.md)



