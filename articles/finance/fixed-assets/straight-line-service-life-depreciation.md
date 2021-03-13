---
title: Amortyzację za liniowy okres użytkowania
description: Ten artykuł zawiera omówienie metody amortyzacji Liniowy okres użytkowania.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a6848aaa679ae42d21b40fdc5f46596aa1f2e899
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009275"
---
# <a name="straight-line-service-life-depreciation"></a>Amortyzację za liniowy okres użytkowania

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metody amortyzacji Liniowy okres użytkowania.

Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu opcji Liniowy okres użytkowania w polu Metoda na stronie Profile amortyzacji amortyzacja środków trwałych z przypisanym profilem amortyzacji są amortyzowane będzie obliczana na podstawie całkowitego okresu użytkowania środków. Jest to zwykle taka sama kwota w każdym okresie amortyzacji. 

Różnica między kwotą amortyzacji obliczoną za liniowy pozostały okres użytkowania i liniowy okres użytkowania występuje w przypadku zaksięgowania korekty dla środków. 

Aby skonfigurować metodę amortyzacji liniowej, trzeba również wybrać opcje w polach Rok amortyzacji i Częstotliwość okresu na stronie Profile amortyzacji.

## <a name="select-a-depreciation-year"></a>Wybór roku amortyzacji
Można wybrać Kalendarzowy lub Obrachunkowy w polu Rok amortyzacji na stronie Profile amortyzacji. Wybór określa opcje dostępne w polu Częstotliwość okresu. Opcją domyślną jest Kalendarz.

### <a name="calendar"></a>Kalendarz

Jeśli zostanie wybrana opcja Kalendarz, przyjmowany jest rok od 1 stycznia do 31 grudnia, nawet jeżeli okresy w kalendarzu obrachunkowym są inne. 

Opcja Kalendarz aktualizuje podstawę amortyzacji (zwykle wartość księgowa netto pomniejszona o wartość odzyskana) 1. stycznia każdego roku. W poniższych przykładach podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia. 

Po wybraniu opcji Kalendarz dostępne są następujące opcje w polu Częstotliwość okresu, które określa daty księgowania naliczenia amortyzacji oraz kwoty w całym roku kalendarzowym:
-   Roczne — księgowanie kwoty 31 grudnia.
-   Miesięczne — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.
-   Kwartalne — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).
-   Półroczne — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).
-   Dzienne — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.

Na przykład jeśli wybierzesz opcję Roczne, roczna amortyzacja jest księgowana tylko raz, 31 grudnia każdego roku. Jeśli wybierzesz opcję Miesięczne, miesięczna amortyzacja jest księgowana każdego miesiąca jako 1/12 kwoty amortyzacji.

### <a name="fiscal"></a>Fiskalny

Jeśli zostanie wybrana opcja Obrachunkowy w polu Rok amortyzacji, będzie używana amortyzację za liniowy okres użytkowania. Jest ona obliczana na podstawie roku obrachunkowego zdefiniowanego przez kalendarz obrachunkowy określony dla księgi lub wybrany na stronie Księga. Kalendarze obrachunkowe konfiguruje się ustawia się na stronie Kalendarze obrachunkowe.

Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca. Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy. Amortyzacja jest korygowana automatycznie dla każdego okresu obrachunkowego. Długość następnego roku obrachunkowego opiera się na okresach obrachunkowych, które konfiguruje się podczas tworzenia nowego roku obrachunkowego w formularzu Kalendarze obrachunkowe. 

W przypadku wybrania opcji Fiskalny w polu Częstotliwość okresu dostępne są następujące opcje:
-   Roczne — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako jednej kwoty ostatniego dnia roku obrachunkowego.
-   Okres obrachunkowy — służy do obliczania dla roku obrachunkowego sumy amortyzacji, która jest naliczana w okresach obrachunkowych określonych w formularzu Kalendarze obrachunkowe dla kalendarza obrachunkowego.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Przykład: amortyzacja liniowa środków trwałych, które nie uległy zmianie
Załóżmy, że środki trwałe mają następujące właściwości.

|                     |        |
|---------------------|--------|
| Koszt nabycia    | 11 000 |
| Wartość odzyskana       | 1 000  |
| Podstawa amortyzacji   | 10000 |
| Okres użytkowania (lata)  | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych      |
| Amortyzacja roczna | 2 000  |

Każdego roku uzyskuje się taką samą kwotę amortyzacji. (Koszt nabycia - Wartość odzyskana) / Lata okresu użytkowania

| Okres | Obliczanie rocznej kwoty amortyzacji | Wartość księgowa netto na koniec roku |
|--------|-------------------------------------------|---------------------------------------|
| Rok 1 | (11 000 - 1000) / 5 = 2000              | 9000                                 |
| Rok 2 | (11 000 - 1000) / 5 = 2000              | 7000                                 |
| Rok 3 | (11 000 - 1000) / 5 = 2000              | 5000                                 |
| Rok 4 | (11 000 - 1000) / 5 = 2000              | 3000                                 |
| Rok 5 | (11 000 - 1000) / 5 = 2000              | 1 000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a> Przykład: amortyzacja liniowa środków trwałych, które uległy zmianie

Załóżmy, że do tych samych środków trwałych w roku 2. dodano korektę wartości początkowej w wysokości 4000. 

Okres użytkowania korekty wartości początkowej jest taki sam jak środków trwałych i rozpoczyna się od momentu dodania korekty. Wartość księgowa netto na końcu roku 5. odpowiada wartości księgowej netto korekty wartości początkowej. Amortyzacja za okres jest obliczana zgodnie z poniższą tabelą.

| Okres | Obliczenie kwoty rocznej amortyzacji | Wartość księgowa netto pod koniec roku |
|--------|-------------------------------------------|---------------------------------------|
| Rok 1 | 10 000 / 5 = 2000                        | 11 000 - 2000 = 9000                |
| Rok 2 | 4000 (korekta wartości początkowej)            | 9000 + 4000 =13 000                 |
| Rok 2 | 14 000 / 5 = 2800                        | 13 000 - 2800 = 10 200               |
| Rok 3 | 14 000 / 5 = 2800                        | 10 200 - 2800 = 7400                |
| Rok 4 | 14 000 / 5 = 2800                        | 7400 - 2800 = 4600                 |
| Rok 5 | 14 000 / 5 = 2800                        | 4600 - 2800 = 1800                 |
| Rok 6 | Pozostało 800\*                           | 1800 – 800 = 1000                   |

\*Ponieważ pozostała kwota jest niższa niż kwota amortyzacji, uwzględniana jest tylko kwota pozostała pomniejszona o wartość odzyskaną.





