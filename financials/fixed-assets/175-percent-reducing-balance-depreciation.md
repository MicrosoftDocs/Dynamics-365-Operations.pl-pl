---
title: 175% amortyzacja degresywna
description: "Ten artykuł zawiera omówienie metody amortyzacji 175% amortyzacja degresywna."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 812fbb3cc3159783e9908e537c366ffc7f934092
ms.lasthandoff: 03/31/2017


---

# <a name="175-percent-reducing-balance-depreciation"></a>175% amortyzacja degresywna

Ten artykuł zawiera omówienie metody amortyzacji 175% amortyzacja degresywna.

Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu wartości **Degresywna 175%** w polu **Metoda** na stronie **Profile amortyzacji** amortyzacja środków trwałych, które są przypisane do tego profilu amortyzacji, ma taką samą wartość procentową dla każdego okresu amortyzacji. 

Aby skonfigurować amortyzację degresywną 175%, należy również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**. Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.

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

W przypadku wybrania opcji **Obrachunkowy** w polu **Rok amortyzacji** amortyzacja degresywna 175% jest obliczana na podstawie roku obrachunkowego z kalendarza obrachunkowego określonego dla księgi lub wybranego na stronie **Księga**. Kalendarze obrachunkowe ustawia się na stronie **Kalendarze obrachunkowe**. Aby uzyskać więcej informacji, zobacz [kalendarze obrachunkowe, lata finansowe i okresy.](\financials\budgeting\fiscal-calendars-fiscal-years-periods.md).

Na przykład dla roku obrachunkowego 1 lipca do 30 czerwca, obliczanie amortyzacji rozpoczyna się 1 lipca. Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy. Amortyzacja jest automatycznie korygowana dla każdego okresu obrachunkowego, a długość kolejnego roku obrachunkowego jest określona przez okresy obrachunkowe zdefiniowane na stronie **Kalendarze obrachunkowe**. 

W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:

-   **Rocznie** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako kwoty ostatniego dnia roku obrachunkowego.
-   **Okres obrachunkowy** oblicza łączną kwotę amortyzacji w roku obrachunkowym. Ta kwota jest naliczana w okresach obrachunkowych, które zostały zdefiniowane na stronie **Kalendarze obrachunkowe**.

## <a name="example-of-175-reducing-balance-depreciation"></a>Przykład amortyzacji degresywnej 175%
|                                |        |
|--------------------------------|--------|
| Koszt nabycia               | 11 000 |
| Wartość odzyskana                  | 1 000  |
| Podstawa amortyzacji              | 10000 |
| Okres użytkowania (lata)             | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych      |
| Roczna wartość procentowa amortyzacji | 35%    |

Metoda amortyzacji degresywnej 175% dzieli wartość 175% między lata okresu użytkowania. Wartość procentowa zostanie pomnożona przez wartość księgową netto środków trwałych w celu określenia kwoty amortyzacji za dany rok.

| Okres | Obliczenie kwoty rocznej amortyzacji | Wartość księgowa                  | Wartość księgowa netto pod koniec roku |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| Rok 1 | (11,000 – 1,000) × 35% = 3,500                | 11,000 – 3,500 = 7,500      | 11,000 – 1,000 – 3,500 = 6,500        |
| Rok 2 | 6,500 × 35% = 2,275                           | 7,500 – 2,275 = 5,225       | 6,500 – 2,275 = 4,225                 |
| Rok 3 | 4,225 × 35% = 1,478.75                        | 5,225 – 1,478.75 = 3,746.25 | 4,225 – 1,478.75 = 2,746.25           |

> [!NOTE] 
> Zazwyczaj, kiedy kwotę, która jest obliczana przy użyciu zmniejszenie metody amortyzacji degresywnej 175% stanie się niższa od kwoty, która może być obliczona za pomocą metody liniowej jest konwersja do metody liniowej za pozostały okres użytkowania.


