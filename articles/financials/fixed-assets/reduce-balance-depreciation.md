---
title: Amortyzacja degresywna
description: Ten artykuł zawiera omówienie metody amortyzacji Degresywna.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e36a7e1a5d83a95de53b70b8e3c3b667aae9c6c0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "321186"
---
# <a name="reduce-balance-depreciation"></a>Amortyzacja degresywna

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metody amortyzacji Degresywna.

Jeśli przy konfiguracji profilu amortyzacji środka stałego zostanie wybrana opcja Degresywna w polu Metoda na stronie Profile amortyzacji, wówczas środki trwałe, do których przypisany jest ten profil amortyzacji, będą amortyzowane o tę samą wartość procentową w każdym okresie amortyzacji.

Aby skonfigurować amortyzację degresywną, należy również zaznaczyć pola na skróconej karcie Ogólne na stronie Profile amortyzacji. Najpierw wybierz rok w polu Amortyzacja roczna. Opcje dostępne w polu Częstotliwość okresu są uzależnione od opcji wybranych w pierwszym polu, co zostało opisane w sekcjach poniżej. 

Należy również wprowadzić wartość w polu Procent dla profilu amortyzacji. Jeśli zostanie wybrana opcja Pełna amortyzacja, pozostała podstawa amortyzacji zostanie pobrana w ostatnim okresie amortyzacji i może to być duża kwota. W niektórych krajach/regionach nie używa się przełączania na metodę liniową. Zamiana następuje wtedy, gdy kwota metody alternatywnej jest większa niż kwota podstawowego profilu amortyzacji lub jest jej równa, zostanie pobrana kwota amortyzacji z metody alternatywnej. 

Ponieważ środek trwały nigdy nie zostanie w pełni zamortyzowany na podstawie obliczenia wartości procentowej, należy wybrać opcję Pełna amortyzacja, aby w pełni zamortyzować środek trwały.

## <a name="select-a-depreciation-year"></a>Wybór roku amortyzacji
Można wybrać Kalendarzowy lub Obrachunkowy w polu Rok amortyzacji na stronie Profile amortyzacji. Wybór określa opcje dostępne w polu Częstotliwość okresu. Opcją domyślną jest Kalendarz.

### <a name="calendar"></a>Kalendarz

Opcja Kalendarz aktualizuje podstawę amortyzacji (zwykle wartość księgowa netto pomniejszona o wartość likwidacji) 1. stycznia każdego roku. W przykładzie amortyzacji degresywnej, niżej w tym temacie, podstawą amortyzacji jest licznik pierwszego wyrażenia w obliczeniach kolumny Obliczenia. 

Po wybraniu opcji Kalendarz dostępne są następujące opcje w polu Częstotliwość okresu, które określa daty księgowania naliczenia amortyzacji oraz kwoty w całym roku kalendarzowym:

-   Roczne — służy do księgowania 31 grudnia.
-   Miesięczne — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.
-   Kwartalne — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).
-   Półroczne — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).
-   Dzienne — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.

Na przykład jeśli wybierzesz opcję Roczne, roczna amortyzacja jest księgowana tylko raz, 31 grudnia każdego roku. Jeśli wybierzesz opcję Miesięczne, miesięczna amortyzacja jest księgowana każdego miesiąca jako 1/12 kwoty amortyzacji.

### <a name="fiscal"></a>Fiskalny

Jeśli zostanie wybrana opcja Obrachunkowy w polu Rok amortyzacji, będzie używana liniowa metoda amortyzacji. Jest ona obliczana na podstawie roku obrachunkowego, który został ustawiony na stronie Kalendarze obrachunkowe dla kalendarza obrachunkowego wybranego na stronie Księga. Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca. Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy. Amortyzacja jest korygowana dla każdego okresu obrachunkowego. Długość następnego roku obrachunkowego opiera się na okresach obrachunkowych, które konfiguruje się podczas tworzenia nowego roku obrachunkowego na stronie Kalendarze obrachunkowe.


W przypadku wybrania opcji Fiskalny w polu Częstotliwość okresu dostępne są następujące opcje:

-   Roczne — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako jednej kwoty ostatniego dnia roku obrachunkowego.
-   Okres obrachunkowy służy do księgowania łącznej kwoty amortyzacji obliczonej dla roku obrachunkowego, która jest naliczana w okresach obrachunkowych zdefiniowanych dla kalendarza obrachunkowego wybranego na stronie Księga lub dla kalendarza obrachunkowego wybranego dla księgi zawierającej środek trwały.

## <a name="example-of-reducing-balance-depreciation"></a>Przykład amortyzacji degresywnej

Załóżmy, że cena nabycia środka trwałego wynosi 11,000, wartość likwidacji -1,000, a procentowy współczynnik amortyzacji -30. 

Jeśli używasz metody Degresywna, 30 procent podstawy amortyzacji (wartość księgowa netto minus wartość likwidacji) jest obliczane na koniec poprzedniego okresu amortyzacji. Amortyzacja dla pierwszych trzech lat została przedstawiona w tabeli poniżej.

| Okres | Obliczenie kwoty rocznej amortyzacji | Wartość księgowa netto pod koniec roku |
|--------|-------------------------------------------|---------------------------------------|
| Rok 1 | (11 000 - 1000) \* 30% = 3000           | (11 000 - 1000) - 3000 = 7000      |
| Rok 2 | (7000 - 1000) \* 30% = 1800            | (7000 -1800) = 5200                |
| Rok 3 | (5200 - 1000) \* 30% = 1260            | (5200 - 1260) = 3940               |


-





