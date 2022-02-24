---
title: Amortyzacja za pozostały liniowy okres użytkowania
description: Ten artykuł zawiera omówienie metody amortyzacji Liniowy pozostały okres użytkowania.
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
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d2414ea97fefbec1e975498e171496e33057541c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969011"
---
# <a name="straight-line-life-remaining-depreciation"></a>Amortyzacja za pozostały liniowy okres użytkowania

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie metody amortyzacji Liniowy pozostały okres użytkowania.

Po skonfigurowaniu profilu amortyzacji środków trwałych i wybraniu opcji **Liniowy pozostały okresu użytkowania** w polu **Metoda** na stronie **Profile amortyzacji amortyzacja środków trwałych**, które są przypisane do tego profilu amortyzacji, będzie obliczana na podstawie pozostałego okresu użytkowania środków. Kwota amortyzacji jest generalnie taka sama w każdym okresie amortyzacji. Aby skonfigurować pozostały liniowy okres użytkowania, trzeba również wybrać opcje w polach **Rok amortyzacji** i **Częstotliwość okresu** na stronie **Profile amortyzacji**. Opcje dostępne w polu **Częstotliwość okresu** różnią się w zależności od wartości wybranej w polu **Rok amortyzacji**.

## <a name="select-a-depreciation-year"></a>Wybór roku amortyzacji
Można wybrać **Kalendarzowy** lub **Obrachunkowy** w polu **Rok amortyzacji** na stronie **Profile amortyzacji**. Domyślna wartość to **Kalendarzowy**. Wybór określa opcje dostępne w polu **Częstotliwość okresu**. W polu będą dostępne cztery opcje definiujące daty księgowania oraz kwoty naliczeń amortyzacyjnych w roku kalendarzowym.

### <a name="calendar"></a>Kalendarz

W przypadku wybrania opcji **Kalendarz** w polu **_Rok amortyzacji_*_ przyjmowany jest rok od 1 stycznia do 31 grudnia, nawet jeśli kalendarz obrachunkowy został zdefiniowany inaczej. Opcja _* Kalendarz** powoduje aktualizację podstawy amortyzacji 1 stycznia każdego roku. Podstawą amortyzacji jest zazwyczaj wartość księgową netto minus wartość odzyskana. W poniższym przykładzie podstawa amortyzacji stanowi kolejny numer w pierwszym wyrażeniu w obliczeniach w kolumnie Obliczenia. W przypadku wybrania opcji **Kalendarzowy** jako rok amortyzacji, dostępne są następujące opcje są dostępne w polu **Częstotliwość okresu**:

-   **Roczne** — księgowanie kwoty 31 grudnia.
-   **Miesięczne** — służy do księgowania miesięcznej kwoty pod koniec każdego miesiąca kalendarzowego.
-   **Kwartalne** — księgowanie kwoty kwartalnej na koniec każdego kwartału kalendarzowego (31 marca, 30 czerwca, 30 września i 31 grudnia).
-   **Półroczne** — służy do księgowania półrocznej kwoty na koniec każdego półrocza kalendarzowego (30 czerwca i 31 grudnia).
-   **Dzienne** — służy do księgowania kwoty amortyzacji na potrzeby metody amortyzacji dziennej przy użyciu jednej transakcji dziennie.

Na przykład jeśli wybierzesz opcję **Roczne**, roczna amortyzacja jest księgowana tylko raz, 31 grudnia każdego roku. Jeśli wybierzesz opcję **Miesięczne**, miesięczna amortyzacja jest księgowana każdego miesiąca jako 1/12 kwoty amortyzacji.

### <a name="fiscal"></a>Fiskalny

Jeśli zostanie wybrana opcja **Obrachunkowy** w polu **Rok amortyzacji**, będzie używana amortyzacja za pozostały liniowy okres użytkowania. Amortyzacja jest obliczana na podstawie pozostałych lat obrachunkowych. Na przykład dla roku obrachunkowego od 1 lipca 2015 r. do 30 czerwca 2016 r. obliczanie amortyzacji rozpoczyna się w dniu 1 lipca 2016 r. Rok obrachunkowy może być dłuższy lub krótszy niż 12 miesięcy. Amortyzacja jest korygowana dla każdego okresu obrachunkowego. Długość kolejnego roku obrachunkowego jest określana na podstawie okresów obrachunkowych skonfigurowanych na stronie **Kalendarze obrachunkowe**. W przypadku wybrania opcji **Fiskalny** jako rok amortyzacji, w polu **Częstotliwość okresu** dostępne są następujące opcje:

-   **Roczne** — służy do księgowania sumy amortyzacji obliczonej dla roku obrachunkowego jako jednej kwoty ostatniego dnia roku obrachunkowego.
-   **Okres obrachunkowy** oblicza łączną kwotę amortyzacji w roku obrachunkowym. Ta kwota jest następnie naliczana w okresach obrachunkowych określonych na stronie **Kalendarze obrachunkowe** dla kalendarza obrachunkowego, który został określony dla księgi.

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Przykład amortyzacji liniowej środków trwałych, które nie uległy zmianie
Środek trwały ma następujące właściwości.

|                     |        |
|---------------------|--------|
| Koszt nabycia    | 11 000 |
| Wartość odzyskana       | 1 000  |
| Podstawa amortyzacji   | 10000 |
| Okres użytkowania (lata)  | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych      |
| Amortyzacja roczna | 2 000  |

Kwota amortyzacji jest taka sama co roku: (koszt nabycia - wartość odzyskana) / lata okresu użytkowania

| Okres | Obliczenie kwoty rocznej amortyzacji | Wartość księgowa netto pod koniec roku |
|--------|-----------------------------------------------|---------------------------------------|
| Rok 1 | (11 000 – 1000) ÷ 5 = 2000                  | 9000                                 |
| Rok 2 | (9000 – 1000) ÷ 4 = 2000                   | 7000                                 |
| Rok 3 | (7000 – 1000) ÷ 3 = 2000                   | 5000                                 |
| Rok 4 | (5000 – 1000) ÷ 2 = 2000                   | 3000                                 |
| Rok 5 | (3000 – 1000) ÷ 1 = 2000                   | 1 000                                 |





