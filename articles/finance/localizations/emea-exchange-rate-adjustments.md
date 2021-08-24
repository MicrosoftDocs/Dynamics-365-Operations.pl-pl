---
title: Korekty kursów wymiany
description: Ten temat zawiera informacje o funkcji korekty kursu wymiany przeznaczonej dla użytkowników w firmach w Estonii, na Węgrzech, w Czechach, na Łotwie, na Litwie, w Polsce i w Rosji.
author: ShylaThompson
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 272683
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: kfend
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 82f9d51bb882ae83c6382a424fbdff65900fd3822d70f496c0956c2e57180ebf
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767607"
---
# <a name="exchange-rate-adjustments"></a>Korekty kursów wymiany

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o funkcji korekty kursu wymiany przeznaczonej dla użytkowników w firmach w Estonii, na Węgrzech, w Czechach, na Łotwie, na Litwie, w Polsce i w Rosji.

Funkcja korekty kursów wymiany dla Estonii, Węgier, Czech, Łotwy, Litwy, Polski i Rosji obejmuje następujące rozszerzenia dla modułów Rozrachunki z odbiorcami i Rozrachunki z dostawcami:

-   Księgowania korekt kursów wymiany można wycofywać jako korekty (kwoty ujemne) pierwotnych korekt.
-   Podczas księgowania następujących po sobie niezrealizowanych korekt kursu wymiany są używane to samo konto księgowania w księdze głównej i typ transakcji, bez względu na to, czy korekty reprezentują dodanie, czy ujemne różnice kursowe.
-   Obliczone dodatnie różnice kursowe są zawsze księgowane na kontach dodatnich różnic kursowych, a obliczone ujemne różnice kursowych są zawsze księgowane na kontach ujemnych różnic kursowych.

Firmy mające adres podstawowy w Czechach mogą stosować specjalną metodę do korygowania kursów wymiany. Ta metoda nosi nazwę metody przyrostowej. Gdy ta metoda jest włączona, zmiany wprowadzone przez bieżącą funkcję nie są stosowane. Niezrealizowane i zrealizowane dodatnie lub ujemne różnice kursowe są obliczane względem ostatniego użytego kursu wymiany. Skorygowana kwota jest używana zamiast oryginalnej kwoty jako podstawa obliczeń. Aby przełączyć na metodę przyrostową korekty kursu wymiany, na stronie **Parametry księgi głównej** w sekcji **Przeszacowanie w walucie obcej** w polu **Metoda obliczania** zaznacz opcję **Zwiększany**. W poniższym przykładzie pokazano, jak działa funkcja korekty kursu wymiany dla Estonii, Węgier, Czech, Łotwy, Litwy, Polski i Rosji. Oto scenariusz biznesowy dla tego przykładu:

-   Faktura w walucie obcej jest księgowana 1 grudnia 2012 r.
-   Płatność w walucie obcej jest księgowana 3 stycznia 2013 r.
-   Jest wykonywane rozliczenie w celu zastosowania płatności do faktury.
-   Korekta kursu wymiany jest wykonywana 31 grudnia 2012 r. (metoda = Standardowo).
-   Korekta kursu wymiany jest wykonywana 1 stycznia 2013 r. (metoda = Data faktury).

Oto kursy wymiany dolarów kanadyjskich (CAD) na dolary amerykańskie (USD) dla tego przykładu:

-   1 grudnia 2012: 400,0000
-   31 grudnia 2012: 450,0000
-   3 stycznia 2013: 420,0000

### <a name="invoice"></a>Faktura VAT

| Data                             | Strona debetowa/kredytowa | Kwoty               | Konto księgi głównej (KG)    | Typ transakcji             | Typ księgowania       | Strona kredytowa | Korekta |
|----------------------------------|--------------|-----------------------|--------------------------------|------------------------------|--------------------|--------|------------|
| 1-gru-12                         | Strona debetowa        | 10 000 CAD/40 000 USD | rozrachunki z odbiorcami                             | Faktura VAT                      | Saldo odbiorcy   |        |            |
| 1-gru-12                         | Strona kredytowa       | 10 000 CAD/40 000 USD | Kompensaty                         | Faktura VAT                      | Arkusz księgi     | X      |

### <a name="payment"></a>Płatność

| Data                             | Strona debetowa/kredytowa | Kwoty               | Konto księgi głównej (KG)    | Typ transakcji             | Typ księgowania       | Strona kredytowa | Korekta |
|----------------------------------|--------------|-----------------------|--------------------------------|------------------------------|--------------------|--------|------------|
| 3-sty-13                         | Strona debetowa        | 10 000 CAD/42 000 USD | Kompensaty                         | Płatność                      | Arkusz księgi     |        |            |
| 3-sty-13                         | Strona kredytowa       | 10 000 CAD/42 000 USD | rozrachunki z odbiorcami                             | Płatność                      | Saldo odbiorcy   | X      |            |

### <a name="settlement"></a>Miejscowość

| Data                             | Strona debetowa/kredytowa | Kwoty               | Konto księgi głównej (KG)    | Typ transakcji             | Typ księgowania       | Strona kredytowa | Korekta |
|----------------------------------|--------------|-----------------------|--------------------------------|------------------------------|--------------------|--------|------------|
|3 stycznia 2013 (= data płatności) | Strona debetowa        | 0 CAD/2000 USD       | rozrachunki z odbiorcami                             | Odbiorca                     | Zysk z tytułu dodatnich różnic kursowych |        |            |
3 stycznia 2013 (= data płatności) | Strona kredytowa       | 0 CAD/2000 USD       | Zrealizowana dodatnia różnica kursowa   | Odbiorca                     | Zysk z tytułu dodatnich różnic kursowych | X      |            |


### <a name="revaluation--standard-method-date--december-31-2012"></a>Przeszacowanie (metoda Standardowo; data = 31 grudnia 2012)
W tym przykładzie przeszacowania zauważ, że wpis z 3 stycznia 2013 r., jest bezpośrednim cofnięciem wpisu z 31 grudnia 2012 r. Nawet konta KG i typy księgowania są takie same. Ponadto zauważ, że została ustawiona flaga **Korekta**.

| Data                             | Strona debetowa/kredytowa | Kwoty               | Konto księgi głównej (KG)    | Typ transakcji             | Typ księgowania       | Strona kredytowa | Korekta |
|----------------------------------|--------------|-----------------------|--------------------------------|------------------------------|--------------------|--------|------------|
| 31-gru-12           | Strona debetowa        | 0 CAD/5000 USD       | rozrachunki z odbiorcami                             | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych |        |            |
| 31-gru-12           | Strona kredytowa       | 0 CAD/5000 USD       | Niezrealizowana dodatnia różnica kursowa | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych | X      |            |
| 3-sty-13            | Strona debetowa        | 0 CAD/5000 USD       | rozrachunki z odbiorcami                             | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych |        | X          |
 3-sty-13            | Strona kredytowa       | 0 CAD/5000 USD       | Niezrealizowana dodatnia różnica kursowa | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych | X      | X          |


### <a name="revaluation-invoice-date-method-date--january-1-2013"></a>Przeszacowanie (metoda Data faktury; data = 1 stycznia 2013)
W tym przeszacowaniu zauważ, że wpis z 1 stycznia 2013 r., jest bezpośrednim cofnięciem wpisu z 3 stycznia 2013 r. Nawet konta KG i typy księgowania są takie same. Ponadto zauważ, że została ustawiona flaga **Korekta**.

| Data   | Strona debetowa/kredytowa | Kwoty | Konto księgi głównej (KG)| Typ transakcji| Typ księgowania| Strona kredytowa | Korekta |
|--------|--------------|---------|----------------------------|----------------|--------|------------|--------------|
|1-sty-13 | Strona debetowa  | 0 CAD/5000 USD | rozrachunki z odbiorcami                             | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych |   | X |
|1-sty-13 | Strona kredytowa | 0 CAD/5000 USD | Niezrealizowana dodatnia różnica kursowa | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych | X | X |
|3-sty-13 | Strona debetowa  | 0 CAD/5000 USD | rozrachunki z odbiorcami                             | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych |   |   |
|3-sty-13 | Strona kredytowa | 0 CAD/5000 USD | Niezrealizowana dodatnia różnica kursowa | Przeszacowanie w walucie obcej | Zysk z tytułu dodatnich różnic kursowych | X |   |

Zachowanie systemu jest takie same, niezależnie od tego, czy w opcji **Korekta** w sekcji **Wycofanie transakcji** na stronie **Parametry księgi głównej** ustawiono wartość **Tak**, czy **Nie**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]