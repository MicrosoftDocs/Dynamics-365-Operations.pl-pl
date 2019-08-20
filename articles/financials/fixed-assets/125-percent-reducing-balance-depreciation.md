---
title: 125% amortyzacja degresywna
description: Ten artykuł zawiera omówienie metody amortyzacji 125% amortyzacja degresywna.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5af050fb6099b583be4e9c60ba56dacf38d31c08
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840872"
---
# <a name="125-percent-reducing-balance-depreciation"></a>125% amortyzacja degresywna

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metody amortyzacji 125% amortyzacja degresywna.

Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu wartości **Degresywna 125%** w polu **Metoda** na stronie **Profile amortyzacji** amortyzacja środków trwałych, które są przypisane do tego profilu amortyzacji, ma taką samą wartość procentową dla każdego okresu amortyzacji. Wartość procentowa jest obliczana na podstawie okresu użytkowania środków. Na przykład, jeżeli okres użytkowania środków wynosi pięć lat, wartość procentowa zostanie obliczona jako 25% (125%/5).

Aby skonfigurować amortyzację degresywną 125%, należy również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**. Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.

## <a name="select-a-depreciation-year"></a>Wybór roku amortyzacji
Można wybrać **Kalendarzowy** lub **Obrachunkowy** w polu **Rok amortyzacji** na stronie **Profile amortyzacji**. Domyślna wartość to **Kalendarzowy**. 

Wybór określa opcje dostępne w polu **Częstotliwość okresu**. W polu będą dostępne cztery opcje definiujące daty księgowania oraz kwoty naliczeń amortyzacyjnych w roku kalendarzowym.

### <a name="calendar"></a>Kalendarz

W polu **Rok amortyzacji** możesz zachować wartość domyślną — **Kalendarzowy** . 

Opcja **Kalendarzowy** aktualizuje podstawę amortyzacji w dniu 1 stycznia każdego roku. Podstawą amortyzacji jest zazwyczaj wartość księgową netto minus wartość likwidacji. W poniższych przykładach podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia. 

W przypadku wybrania opcji **Kalendarzowy** jako rok amortyzacji, dostępne są następujące opcje są dostępne w polu **Częstotliwość okresu**:

-   **Roczne** — księgowanie kwoty 31 grudnia.
-   **Miesięczne** — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.
-   **Kwartalne** — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).
-   **Półroczne** — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).
-   **Dzienne** — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.

### <a name="fiscal"></a>Fiskalny

W przypadku wybrania opcji **Obrachunkowy** w polu **Rok amortyzacji** amortyzacja degresywna 125% jest obliczana na podstawie roku obrachunkowego z kalendarza obrachunkowego określonego dla księgi lub wybranego na stronie **Księga**. Kalendarze obrachunkowe ustawia się na stronie **Kalendarze obrachunkowe**. 

Na przykład dla roku obrachunkowego od 1 lipca do 30 czerwca włącznie obliczanie amortyzacji rozpocznie się 1 lipca. Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy. Amortyzacja jest automatycznie korygowana dla każdego okresu obrachunkowego, a długość kolejnego roku obrachunkowego jest określona przez okresy obrachunkowe zdefiniowane na stronie **Kalendarze obrachunkowe**. 

W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:

-   **Roczne** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako jednej kwoty ostatniego dnia roku obrachunkowego.
-   **Okres obrachunkowy** księguje łączną kwotę amortyzacji w roku obrachunkowym. Ta kwota jest naliczana w okresach obrachunkowych, które zostały zdefiniowane na stronie **Kalendarze obrachunkowe**.

## <a name="example-of-125-reducing-balance-depreciation"></a>Przykład 125% amortyzacji degresywnej

|                                |        |
|--------------------------------|--------|
| Koszt nabycia               | 11 000 |
| Wartość odzyskana                  | 1 000  |
| Podstawa amortyzacji              | 10000 |
| Okres użytkowania (lata)             | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych      |
| Roczna wartość procentowa amortyzacji | 25%    |

Metoda amortyzacji degresywnej 125% dzieli wartość 125% między lata okresu użytkowania. Wartość procentowa zostanie pomnożona przez wartość księgową netto środków trwałych w celu określenia kwoty amortyzacji za dany rok.

| Okres | Obliczenie kwoty rocznej amortyzacji | Wartość księgowa                    | Wartość księgowa netto pod koniec roku |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| Rok 1 | (11 000 – 1000) × 25% = 2500                | (11 000 – 2500) = 8500      | (11 000 – 1000 – 2500) = 7500      |
| Rok 2 | 7500 × 25% = 1875                           | (8500 – 1875) = 6625       | (7500 – 1875) = 5625               |
| Rok 3 | 5625 × 25% = 1406,25                        | (6625 – 1406,25) = 5218,75 | (5625 – 1406,25) = 4218,75         |

> [!NOTE] 
> Zwykle kiedy kwota, która jest obliczana przy użyciu metody amortyzacji degresywnej 125%, stanie się niższa od kwoty, która może zostać obliczona za pomocą metody liniowej, następuje przejście do metody liniowej dla pozostałego okresu użytkowania.



