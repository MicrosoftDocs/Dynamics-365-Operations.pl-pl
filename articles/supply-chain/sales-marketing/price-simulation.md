---
title: Symulacja ceny
description: Ten artykuł zawiera informacje o symulacjach cen dla ofert. Symulacja ceny pomaga ocenić wpływ obniżek na przyszłą cenę sprzedaży w trakcie procesu sporządzania oferty, zanim określona cena zostanie potwierdzona.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationPriceSimulation, SalesQuotationsTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a14e485d1e02247159e1d9eb1c5d81be37626216
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580511"
---
# <a name="price-simulation"></a>Symulacja ceny

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o symulacjach cen dla ofert. Symulacja ceny pomaga ocenić wpływ obniżek na przyszłą cenę sprzedaży w trakcie procesu sporządzania oferty, zanim określona cena zostanie potwierdzona.

Symulacja ceny oferty zawiera nową łączną kwotą, opartą na proponowanej nowej cenie. Symulacja ceny można również wyświetlać nową wartość dla określonego wiersza utworzonego w istniejącej ofercie. Można wpisać symulację ceny i zastosować ją później. Ewentualnie można użyć oryginalnej oferty bez symulacji ceny i wprowadzać dodatkowe zmiany w trakcie pracy poprzez proces sprzedaży z klientem.  

Symulacja ceny nie powoduje zmiany ceny w ofercie. Symulacja ceny jest stosowana do całej oferty, jest traktowana jako specjalny rabat w nagłówku oferty. Symulacja ceny jest stosowana do określonych towarów, jest traktowana jako specjalny rabat w wierszach oferty. Cena jednostkowa sprzedaży w utworzonym wierszu sprzedaży nie ulega zmianie po wprowadzeniu symulacji cen. Zamiast tego jest wprowadzany rabat o określonej procentowo wartości, odpowiadający obniżce ceny w wierszu oferty. Po przeprowadzeniu symulacji cen, jednostkowe ceny sprzedaży i rabaty procentowe są transferowane do wiersza oferty lub nagłówka oferty.  

>[Uwaga] Podczas wykonywania symulacji cen pod uwagę jest brana tylko bieżąca waluta sprzedaży. Natomiast podczas przeglądania wartości ofert jest widoczna zarówno waluta sprzedaży, jak i waluta podstawowa dla w firmy.  

Dodatkowe towary, które powinny zostać dodane do wierszy oferty mogą uruchamiać rabaty wiersza lub rabaty wspólne. Mogą wywoływać rabat końcowy, co skutkuje zmianą marży pokrycia i współczynników marży dla wierszy oferty i rabatem całościowym.  

Można wykonywać wielokrotne symulacje cen, aby prześledzić wpływ zmiany cen na końcowy kształt oferty. Wykonywanie takich symulacji umożliwia dopasowanie w ofercie całkowitej ceny oferty albo ceny jednego bądź kilku wierszy wierszy, a następnie przeprowadzenie takiej symulacji cen, która daje największe szanse zawarcia transakcji.  

Podczas tworzenia oferty można skonfigurować alarm. Oto kilka zastosowań alarmów:

-   Mogą one powiadamiać o statusie ofert w organizacji.
-   Mogą wywołać przegląd określonej oferty lub informować o przekroczeniu limitu rabatu.

## <a name="price-simulation-and-discounts"></a>Symulacja cen i rabaty
Aby zagwarantować, że rabaty i ceny są obliczane prawidłowo, należy zachować ostrożność przy uruchamianiu symulacji cen dla ofert z rabatami. Ponieważ wszystkie symulacje cen są traktowane jako specjalne rabaty dotyczące aktywnego wiersza oferty lub całej oferty, istotne znaczenie ma uwzględnianie różnic w rabatach.

### <a name="types-of-discounts-in-trade-agreements"></a>Typy rabatów w umowach handlowych

W umowach handlowych w Supply Chain Management są możliwe cztery typy rabatów. Rabaty te można konfigurować dla różnych towarów, odbiorców lub grup cenowych i można je ograniczać terminem. Aby uniknąć błędów w obliczeniach, podczas wykonywania symulacji ceny należy wziąć pod uwagę umowy handlowe. Oto cztery typy rabatów w umowach handlowych:

-   **Cena sprzedaży** – można określić osobne ceny sprzedaży towarów. Podczas tworzenia wierszy zapytania ofertowego, program wyszukuje poprawnych cen sprzedaży dla towaru i przenosi je do wierszy zamówienia sprzedaży. Z tego względu umowa handlowa zawierająca ten rodzaj rabatu nie wpływa na symulację ceny. Cena sprzedaży, która jest używana w wierszu oferty, odzwierciedla zapisy umowy handlowej.
-   **Rabat wiersza** — specjalne rabaty określone dla towarów, w zależności od zamówionej ilości. Kwoty wierszy są zwykle pomniejszane o rabat wiersza przed uruchomieniem symulacji ceny. Z tego względu umowa handlowa zawierająca ten rodzaj rabatu wpływa na symulację ceny.
-   **Rabaty wspólne** – jeśli połączone ilości przekraczają określony limit, wstępnie określone kombinacje zamówionych towarów wymuszają zastosowanie rabatu do całego zamówienia. Kwoty wierszy są zwykle pomniejszane o rabat wiersza przed uruchomieniem symulacji ceny. Z tego względu umowa handlowa zawierająca ten rodzaj rabatu wpływa na symulację ceny.
-   **Rabat końcowy** – jeśli połączone kwoty przekraczają określony limit, wstępnie określone zamówione towary wymuszają zastosowanie rabatu do całego zamówienia. Rabat końcowy jest generowany przez wiersze oferty. Jednak ponieważ rabat końcowy jest stosowany do sumy oferty jako rabat, zmniejsza łączna kwota oferty. Z tego względu umowa handlowa zawierająca ten rodzaj rabatu wpływa na symulację ceny.

### <a name="quotation-lines-and-trade-agreements"></a>Wiersze oferty a umowy handlowe

Podczas tworzenia lub poprawiania wierszy oferty, rabaty wiersza są obliczane automatycznie. Odnajdowana jest odpowiednia cena sprzedaży dla towarów, w zależności od umowy handlowej.

## <a name="price-simulation-examples"></a>Przykłady symulacji ceny
W poniższych przykładach symulacja cen jest stosowana do nagłówków ofert i pojedynczych towarów.

### <a name="price-simulation-for-quotation-headers"></a>Symulacja ceny dla nagłówków oferty

Utworzono ofertę z następującymi wierszami:

-   10 sztuk towaru BR-12 (koszt własny na sztukę: 9,52 USD, cena sprzedaży sztuki towaru: 15,32 USD).
-   12 sztuk towaru BR-14 (koszt własny na sztukę: 7,48 USD, cena sprzedaży sztuki towaru: 13,75 USD).

Poniższa tabela przedstawia wiersze oferty.

|    &nbsp;                  | Obliczanie                          | Wynik   |
|----------------------------|--------------------------------------|----------|
| Ilość sprzedaży             | 10 sztuk + 12 sztuk                  | 22 sztuki |
| Wartość sprzedaży w USD         | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Wartość kosztów w USD          | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Marża pokrycia w USD | 318,20 – 184,96                      | 133,24   |
| Współczynnik marży         | (\[318,20 – 184,96\] ÷ 318,20) × 100 | 41,87%   |

Uruchomiono symulację ceny i zastosowano 15 procent rabatu końcowego dla całej oferty lub nagłówka oferty. Poniższa tabela przedstawia nowe sumy oferty po uruchomieniu symulacji cen.

|     &nbsp;                                           | Obliczanie                               | Wynik   |
|------------------------------------------------------|-------------------------------------------|----------|
| Ilość sprzedaży                                       | 10 sztuk + 12 sztuk                       | 22 sztuki |
| Stara wartość sprzedaży w USD                               | (10 × 15,32) + (12 × 13,75)               | 318,20   |
| Stare wartość kosztów w USD                                | (10 × 9,52) + (12 × 7,48)                 | 184,96   |
| Stara marża pokrycia w USD                       | 318,20 – 184,96                           | 133,24   |
| Stary współczynnik marży                               | (\[318,20 – (10 × 9,52)\] ÷ 318,20) × 100 | 41,87%   |
| Symulacja ceny, 15% rabatu końcowego w USD | (15 × 318,2) ÷ 100                        | 47,73    |
| Nowa wartość sprzedaży w USD                               | 318,20 – 47,73                            | 270,47   |
| Nowa marża pokrycia w USD                       | 270,47 – 184,96                           | 85,51    |
| Nowy współczynnik udziału                               | \[(270,47 – 184,96) ÷ 270,47\] × 100      | 31,61%   |

### <a name="price-simulation-for-single-line-items"></a>Symulacja ceny dla pojedynczych towarów

Utworzono ofertę z następującymi wierszami:

-   10 sztuk towaru BR-12 (koszt własny na sztukę: 9,52 USD, cena sprzedaży sztuki towaru: 15,32 USD).
-   12 sztuk towaru BR-14 (koszt własny na sztukę: 7,48 USD, cena sprzedaży sztuki towaru: 13,75 USD).

Poniższa tabela przedstawia wiersze oferty.

|      &nbsp;                          | Obliczanie                          | Wynik   |
|--------------------------------------|--------------------------------------|----------|
| Ilość sprzedaży                       | 10 sztuk + 12 sztuk                  | 22 sztuki |
| Wartość sprzedaży w USD dla BR-12         | 10 × 15,32                           | 153,20   |
| Wartość sprzedaży w USD dla BR-14         | 12 × 13,75                           | 165,00   |
| Wartość kosztów w USD dla BR-12          | 10 × 9,52                            | 95,20    |
| Wartość kosztów w USD dla BR-14          | 12 × 7,48                            | 89,76    |
| Marża pokrycia w USD dla BR-12 | 153,20 – 95,20                       | 58,00    |
| Marża pokrycia w USD dla BR-14 | 165,00 – 89,76                       | 75,24    |
| Współczynnik marży w USD dla BR-12  | \[(153,20 – 95,20) ÷ 153,20\] × 100  | 37,86    |
| Współczynnik marży w USD dla BR-14  | \[(165,00 – 89,76) ÷ 165,00\] × 100  | 45,60    |
| Łączna wartość sprzedaży w USD             | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Łączna wartość kosztów w USD              | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Łączna marża pokrycia w USD     | 318,20 – 184,96                      | 133,24   |
| Łączny współczynnik marży             | \[(318,20 – 184,96) ÷ 318,20\] × 100 | 41,87%   |

Uruchomiono symulację cen i zastosowano 10 procent rabatu końcowego dla jednostek BR-12. Poniższa tabela przedstawia nowe sumy oferty po uruchomieniu symulacji cen dla pojedynczego towaru.

|    &nbsp;                                         | Obliczanie                             | Wynik   |
|---------------------------------------------------|-----------------------------------------|----------|
| Ilość sprzedaży                                    | 10 sztuk + 12 sztuk                     | 22 sztuki |
| Stara wartość sprzedaży w USD dla BR-12                  | 10 × 15,32                              | 153,20   |
| Symulacja ceny, 10% rabatu dla BR-12 | (10 × 153,2) ÷ 100                      | 15,32    |
| Nowa wartość sprzedaży w USD dla BR-12                  | (10 × 15,32) – 15,32                    | 137,88   |
| Wartość sprzedaży w USD dla BR-14                      | 12 × 13,75                              | 165,00   |
| Wartość kosztów w USD dla BR-12                       | 10 × 9,52                               | 95,20    |
| Wartość kosztów w USD dla BR-14                       | 12 × 7,48                               | 89,76    |
| Nowa marża pokrycia w USD dla BR-12          | 137,88 – 95,20                          | 42,68    |
| Marża pokrycia w USD dla BR-14              | 165,00 – 89,76                          | 75,24    |
| Nowy współczynnik marży w USD dla BR-12           | \[(137,88 – 95,20) ÷ 137,88\] × 100     | 30,95    |
| Współczynnik marży w USD dla BR-14               | \[(165,00 – 89,76) ÷ 165,00\] × 100     | 45,60    |
| Nowa łączna wartość sprzedaży w USD                      | \[(10 × 15,32) – 15,32\] + (12 × 13,75) | 302,88   |
| Łączna wartość kosztów w USD                           | (10 × 9,52) + (12 × 7,48)               | 184,96   |
| Nowa łączna marża pokrycia w USD              | 302,88 – 184,96                         | 117,92   |
| Nowy sumaryczny poziom marży                      | \[(302,88 – 184,96) ÷ 302,88\] × 100    | 38,93%   |

Symulacja ceny wpływa tylko na wiersz, do którego jest stosowana, powodując zmniejszenie sumy dla tego wiersza.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]