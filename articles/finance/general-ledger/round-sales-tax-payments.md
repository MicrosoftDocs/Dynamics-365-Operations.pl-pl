---
title: Reguły płatności podatkowych i zaokrąglania
description: W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998dbd01352d3fa5040187e81b564d14133464db
ms.sourcegitcommit: 092ef6a45f515b38be2a4481abdbe7518a636f85
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4446968"
---
# <a name="sales-tax-payments-and-rounding-rules"></a>Reguły płatności podatkowych i zaokrąglania

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono działanie konfiguracji reguły zaokrąglania w ustawieniach urzędu skarbowego oraz sposób zaokrąglania salda podatku podczas zadania rozliczania i księgowania podatku.

Okresowo należy zgłaszać i płacić podatek w urzędzie skarbowym. Można to zrobić, uruchamiając proces rozliczenia i księgowania podatku na stronie Podatek. Podatek od sprzedaży w danym okresie zostanie rozliczony dla kont podatku, a saldo podatku zostanie zaksięgowane na koncie rozliczenia podatku. Saldo podatku, który jest księgowany na koncie rozliczenie podatku, może być zaokrąglane zgodnie z wymogami urzędu skarbowego przez skonfigurowanie reguły zaokrąglania na stronie podatku od sprzedaży. 

Różnica wynikająca z zaokrąglenia jest księgowana na koncie zaokrąglania podatku wybranym w polu Konta do transakcji automatycznych w księdze głównej.

Poniższy przykład pokazuje mechanizm działania reguły zaokrąglania na potrzeby urzędu skarbowego.

## <a name="examples"></a>Przykłady

Łączny podatek za okres zawiera saldo faktury w wysokości -98 765,43. Podmiot prawny zebrał więcej podatku, niż zapłacił. Z tego względu firma jest winna pieniądze urzędowi skarbowemu. 

Firma chce użyć metody zaokrąglania, która zaokrągla saldo do najbliższego 1,00 EUR. Użytkownik odpowiedzialny za księgowanie podatku musi wykonać następujące czynności:

1. Wybierz kolejno opcje **Podatek** > **Podatki pośrednie** > **Podatek** > **Urzędy skarbowe**.
2. Na skróconej karcie **Ogólne** w polu **Metoda zaokrąglenia** zaznacz opcję **Normalne**.
3. W polu **Zaokrąglenie** wpisz 1,00.
4. Gdy przyjdzie czas zapłacenia podatku urzędowi skarbowemu, przejdź do **Podatek** > **Deklaracje** > **Podatek** > **Rozlicz i zaksięguj podatek**. Na koncie rozliczenie podatku kwota zobowiązań z tytułu podatku **98,765.43** jest zaokrąglana do **98,765**.

W poniższej tabeli przedstawiono, jak kwota 98 765,43 jest zaokrąglana przy użyciu każdej metody zaokrąglania, która jest dostępna w polu **Metoda zaokrąglania** na stronie **Urząd skarbowy**.

> [!NOTE]                                                                                  
> Jeśli wartość zaokrąglenia jest ustawiona jako 0,00, to:
>
> - W przypadku zwykłego zaokrąglania zachowanie zaokrąglania jest takie samo, jak dla **Zaokrąglenie = 0,01**.
> - W przypadku **Opcji formularza zaokrąglania** w **Dół**, **W górę** i **Na korzyść firmy**, zachowanie jest takie samo, jak dla **Zaokrąglenie = 1,00**.

| Zaokrąglanie z opcji                | Wartość zaokrąglenia = 0,01 | Wartość zaokrąglenia = 0,10 | Wartość zaokrąglenia = 1,00 | Wartość zaokrąglenia = 100,00 | Wartość zaokrąglenia = 0,00   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| Normalnie                              | 98,765.43              | 98,765.40              | 98,765.00              | 98,800.00                | 98,765.43                |
| W dół                            | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Zaokrąglenie w górę                         | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |
| Na korzyść firmy, salda kredytowe | 98,765.43              | 98,765.40              | 98,765.00              | 98,700.00                | 98,765.00                |
| Na korzyść firmy, salda debetowe  | 98,765.43              | 98,765.50              | 98,766.00              | 98,800.00                | 98,766.00                |

### <a name="normal-round-and-round-precision-is-001"></a>Normalne zaokrąglenie i normalna dokładność wynoszą 0,01

<table>
  <tr>
    <td>Zaokrąglanie
    </td>
    <td>Procedury obliczania
    </td>
  </tr>
    <tr>
    <td>round(1.015, 0.01) = 1.02
    </td>
    <td>
      <ol>
        <li>round(1.015 / 0.01, 0) = round(101.5, 0) = 102
        </li>
        <li>102 * 0.01 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.014, 0.01) = 1.01
    </td>
    <td> <ol>
        <li>round(1.014 / 0.01, 0) = round(101.4, 0) = 101
        </li>
        <li>101 * 0.01 = 1.01
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.011, 0.02) = 1.02
    </td>
    <td> <ol>
        <li>round(1.011 / 0.02, 0) = round(50.55, 0) = 51
        </li>
        <li>51 * 0.02 = 1.02
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td>round(1.009, 0.02) = 1.00
    </td>
    <td> <ol>
        <li>round(1.009 / 0.02, 0) = round(50.45, 0) = 50
        </li>
        <li>50 * 0.02 = 1.00
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> Jeśli wybierzesz Na korzyść firmy, zaokrąglanie jest zawsze na korzyść firmy. 

Aby uzyskać więcej informacji, zobacz następujące tematy:
- [Omówienie podatku](indirect-taxes-overview.md)
- [Tworzenie płatności podatku](tasks/create-sales-tax-payment.md)
- [Tworzenie transakcji podatku w dokumentach](tasks/create-sales-tax-transactions-documents.md)
- [Wyświetlanie zaksięgowanych transakcji podatkowych](tasks/view-posted-sales-tax-transactions.md)
- [Funkcja zaokrąglanie](https://msdn.microsoft.com/library/aa850656.aspx)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]