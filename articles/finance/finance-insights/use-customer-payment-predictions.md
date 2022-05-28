---
title: Korzystanie z prognoz płatności odbiorcy
description: Ten temat omawia wymagania wstępne i ogólne czynności, które są niezbędne do korzystania z wersji próbnej modułu Szczegółowe dane finansowe.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: ecc864485dfc106df22b48e92a85f2c73d58e0e8
ms.sourcegitcommit: d70f66a98eff0a2836e3033351b482466bd9c290
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740632"
---
# <a name="use-customer-payment-predictions"></a>Korzystanie z prognoz płatności odbiorcy

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób korzystania z funkcji Prognozy płatności odbiorcy. Przed użyciem tej funkcji upewnij się, że wykonano dla niej czynności konfiguracyjne. Aby uzyskać więcej informacji, zobacz [Włączanie prognoz płatności odbiorcy](enable-cust-paymnt-prediction.md).

Przewidywania płatności od odbiorców można przeglądać w obszarze roboczym **Zarządzanie kredytami i windykacjami odbiorców** oraz na dwóch nowych stronach listy: **Przewidywania płatności transakcji** i **Prognozy płatności odbiorcy**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Obszar roboczy Zarządzanie kredytami i windykacjami odbiorców

Obszar roboczy **Zarządzanie kredytami i windykacjami odbiorców** zawiera dwa nowe kafelki, **Przewidywania płatności transakcji** i **Prognozy płatności odbiorcy**.

### <a name="transaction-payment-predictions-list-page"></a>Strona z listą prognoz płatności transakcji

Na stronie listy **Przewidywania płatności transakcji** można wyświetlić prawdopodobieństwo płatności dla otwartych transakcji w przedziałach **Na czas**, **Opóźnione** i **Bardzo opóźnione**. Dla każdej transakcji w siatce kolumna **Prawdopodobieństwo zapłaty na czas** pokazuje prawdopodobieństwo, że faktura zostanie zapłacona nie później niż w wyznaczonym terminie. Jeśli prawdopodobieństwo zapłaty na czas jest mniejsze niż 50 procent, obok wartości procentowej w kolumnie **Prawdopodobieństwo zapłaty na czas** pojawi się czerwone kółko, które wskazuje na ryzyko opóźnienia płatności.

[![Strona Prognozowanie płatności za poszczególne transakcje.](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

W okienku **Informacje pokrewne** przy prawej krawędzi strony znajdują się bardziej szczegółowe informacje dotyczące prognoz:

- Dla transakcji zaznaczonej w siatce skrócona karta **Prognozy płatności** przedstawia szczegóły prognoz płatności w przedziałach **Na czas**, **Opóźnione** i **Bardzo opóźnione**. Sekcja **Najważniejsze czynniki** przedstawia najistotniejsze czynniki, które miały wpływ na przewidywania. Najważniejsze czynniki są atrybutami wybranej transakcji i/lub odbiorcy w danej transakcji.
- Skrócona karta **Wgląd w odbiorcę** zawiera bieżącej statystyki faktury, płatności i windykacji dla odbiorcy w wybranej transakcji.
- Na skróconej karcie **Historia odbiorcy** jest wyświetlana historia płatności od odbiorcy w przedziałach **Na czas**, **Opóźnione** i **Bardzo opóźnione**.

Dane znajdujące się w sekcji **Najważniejsze czynniki** oraz na skróconych kartach **Wgląd w odbiorcę** i **Historia odbiorcy** pomagają objaśniać prognozy płatności. W ten sposób zwiększają zaufanie do trafności prognoz.

[![Graficzne wskaźniki prognoz płatności w okienku Informacje pokrewne.](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="customer-payment-predictions-list-page"></a>Strona z listą prognoz płatności klienta

Strona listy **Prognozy płatności odbiorcy** pokazuje łączne otwarte saldo oraz kwotę przewidywaną do zapłaty w przedziałach **Na czas**, **Opóźnione** i **Bardzo opóźnione**.

[![Strona Prognozowanie płatności od poszczególnych odbiorców.](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

Kwota płatności w każdym przedziale jest obliczana jako suma średniej ważonej salda transakcji. Kwota ta jest obliczana na podstawie prawdopodobieństwa zapłaty w każdym przedziale.

Na przykład odbiorca ma trzy otwarte transakcje, które mają następujące prawdopodobieństwa zapłaty w każdym przedziale.

| Transakcji | Liczba dni | Prawdopodobieństwo zapłaty na czas | Prawdopodobieństwo zapłaty z opóźnieniem | Prawdopodobieństwo zapłaty z dużym opóźnieniem |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10 procent                  | 50 procent               | 40 procent                    |
| T2          | 1 000  | 50 procent                  | 30 procent               | 20 procent                    |
| T3          | 10,000 | 1 procent                   | 4 procent                | 95 procent                    |

W tym przypadku płatności są prognozowane dla każdego przedziału w następujący sposób.

| Przedziały   | Transakcja T1      | Transakcja T2         | Transakcja T3            | Razem |
|-----------|---------------------|------------------------|---------------------------|-------|
| Na czas   | 100 × 10 ÷ 100 = 10 | 1000 × 50 ÷ 100 = 500 | 10 000 × 1 ÷ 100 = 100    | 610   |
| Późno      | 100 × 50 ÷ 100 = 50 | 1000 × 30 ÷ 100 = 300 | 10 000 × 4 ÷ 100 = 400    | 750   |
| Duże opóźnienie | 100 × 40 ÷ 100 = 40 | 1000 × 20 ÷ 100 = 200 | 10 000 × 95 ÷ 100 = 9500 | 9,740 |

W sekcji **Informacje pokrewne** przy prawej krawędzi strony znajdują się bardziej szczegółowe informacje dotyczące prognoz:

- Dla transakcji zaznaczonej w siatce skrócona karta **Prognozy płatności** przedstawia szczegóły prognoz płatności w przedziałach **Na czas**, **Opóźnione** i **Bardzo opóźnione**.
- Skrócona karta **Wgląd w odbiorcę** zawiera bieżącej statystyki faktury, płatności i windykacji dla odbiorcy w wybranej transakcji.
- Na skróconej karcie **Historia odbiorcy** jest wyświetlana historia płatności od odbiorcy w przedziałach **Na czas**, **Opóźnione** i **Bardzo opóźnione**.

Dane znajdujące się w sekcji **Wgląd w odbiorcę** i **Historia odbiorcy** pomagają objaśniać prognozy płatności. W ten sposób zwiększają zaufanie do trafności prognoz.

## <a name="improving-the-accuracy-of-payment-predictions"></a>Zwiększanie dokładności prognoz płatności

Aby wyświetlić dokładność prognoz płatności, należy wybrać kolejno opcje **Kredyty i windykacje \> Ustawienia \> Finance Insights \> Parametry Finance Insights**. Na karcie **Wgląd w płatności od odbiorców** w sekcji **Model przewidywania** jest wyświetlana procentowa dokładność modelu przewidywania.

Jeśli dokładność nie jest zadowalająca, wybierz łącze **Zwiększ dokładność modelu**, aby otworzyć środowisko rozszerzenia AI Builder. W środowisku rozszerzenia AI Builder można zaznaczać i anulować zaznaczenie pól do momentu, aż wybierzesz pola, które uznasz za najistotniejsze dla dokładnego przewidywania prawdopodobieństwa zapłaty. Po zakończeniu można łatwo ponownie wytrenować model przewidywania i opublikować zmiany. Nowo wytrenowany model przewidywania będzie automatycznie wybierany na potrzeby prognozowania w rozwiązaniu Dynamics 365 Finance.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
