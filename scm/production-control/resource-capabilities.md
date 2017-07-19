---
title: "Możliwości zasobu"
description: "Ten artykuł zawiera informacje o organizowaniu możliwościach zasobów. Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania. Wyjaśniono, jak możliwości i związane z nimi funkcje, takie jak poziom biegłości i priorytet, służą do wybierania zasobów odpowiednich dla działań."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability, WrkCtrTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f6b4ccf4d7f9727819831b07221d859e3c5cdd39
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="resource-capabilities"></a>Możliwości zasobu

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o organizowaniu możliwościach zasobów. Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania. Wyjaśniono, jak możliwości i związane z nimi funkcje, takie jak poziom biegłości i priorytet, służą do wybierania zasobów odpowiednich dla działań.

Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania. Zasób operacyjny może mieć więcej niż jedną przypisaną możliwość, a możliwości można przypisywać do więcej niż jednego zasobu. Można tymczasowo przypisać możliwości do zasobów operacyjnych, wybierając daty rozpoczęcia i zakończenia w przypisaniu możliwości. Kiedy wygasa możliwość zasobu, zasób nie może zostać uwzględniony w harmonogramie projektu lub produkcji. Wygasłe możliwości można odnowić. Można usunąć możliwości, pod warunkiem że nie znajdują się one w relacji marszruty ani w marszrucie produkcji aktywnego zlecenia produkcyjnego. Ogólnie należy zachować ostrożność w przypadku usuwania możliwości. Zamiast tego należy rozważyć korektę daty ważności zasobów posiadających określone możliwości. Możliwości można przypisać do wszystkich typów zasobów: Narzędzie, Dostawca, Maszyna, Zasoby ludzkie, Lokalizacja, lub Zakład.

## <a name="level"></a>Poziom
Wiele zasobów często ma te same funkcjonalne możliwości, ale inny poziom biegłości (np. siła, szybkość przetwarzania lub dokładność). Dlatego po przypisaniu możliwości do zasobu, można określić wartość **poziomu**. Poziom jest prostą wartością liczbową. Jeśli określisz, że możliwości jest wymaganiem źródłowym dla marszruty produkcji, możesz również określić wartość **Minimalny wymagany poziom** dla danej możliwości. Aparat planowania wybiera potem tylko te zasoby, które mają wymagane możliwości na poziomie równym lub przewyższającym poziom określony w wymaganiu źródłowym.

## <a name="priority"></a>Priorytet
Zasobom operacyjnym o jednakowych możliwościach można przypisać priorytet. Następnie jeśli wiele zasobów ma możliwości spełniające wymagania planowania na żądanym poziomie i posiada wolne zdolności produkcyjne, aparat planowania może wybierać spośród tych zasobów. Jeśli zostanie wybrana wartość **Priorytet** w polu **Wybór zasobu głównego** na stronie **Parametry planowania**, to zasób, który ma najwyższy priorytet (najniższą wartość liczbową w polu **Priorytet**), zostanie wskazany jako pierwszy podczas planowania.

## <a name="resource-requirements"></a>Zapotrzebowanie na zasoby
Po zdefiniowaniu wymagań źródłowych dla marszruty produkcji można określić jedną lub więcej możliwości jako wymagania. Podczas planowania produkcji możliwości zdefiniowane w wymaganiach źródłowych dla operacji marszruty zostaną dopasowane do możliwości określonych dla zasobów. Zostaną wybrane zasoby posiadające możliwości spełniające wymagania. Jeśli wiele zasobów ma taką samą funkcjonalną możliwość, ale inne poziomy biegłości (np. siła szybkość przetwarzania lub dokładność), można zdefiniować wiele możliwości lub użyć poziomu do określenia możliwości zasobu. Oto przykład:

-   W marszrucie proces wiercenia jest ustawiony jako 10 jednostek na godzinę, ale samo wymaganie jest zdefiniowane jako Wiercenie.
-   Są dwa urządzenia wiertnicze: M1 i M2.
-   Możliwość Wiercenie jest przypisana do obu zasobów: do urządzenia M1 i urządzenia M2.
-   Urządzenie M1 może wiercić dwie jednostki na godzinę, a urządzenie M2 może wiercić 11 jednostek na godzinę.

W tym przykładzie oba urządzenia mogą zostać wybrane przez aparat planowania, bo obie spełniają podstawowe wymaganie możliwości (Wiercenie). Ale urządzenie M1 może wiercić tylko dwie jednostki na godzinę. Ze względu na to, że ten współczynnik jest znacznie niższy od 10 jednostek na godzinę określonych w marszrucie, urządzenie M1 spowoduje problemy na etapie produkcji, jeśli zostanie wybrane. Istnieją dwa sposoby rozwiązania tego problemu i upewnienia się, że zostanie wybrane urządzenie M2:

-   Utwórz dwie osobne możliwości: Wolne wiercenie i Szybkie wiercenie. Zdefiniuj Wolne wiercenie jako wiercenie o czasie procesu od 1 do 9 jednostek na godzinę. Zdefiniuj Szybkie wiercenie jako wiercenie o czasie procesu od 10 do 19 jednostek na godzinę. Następnie przypisz urządzeniu M1 możliwość Wolne wiercenie, a urządzeniu M2 — Szybkie wiercenie. Na końcu zmień wymaganie możliwości zasobu w marszrucie na Szybkie wiercenie. Dzięki temu aparat planowania wybierze prawidłowe urządzenie (M2).
-   Użyj poziomu możliwości do określenia możliwości Wiercenie przypisanej do urządzeń wiertniczych. Określ, że urządzenie M1 ma możliwość Wiercenie na poziomie 2.0, a urządzenie M2 ma możliwość Wiercenie na poziomie 11.0. Następnie określ, że 10.0 jest minimalnym poziomem wymaganym dla możliwości Wiercenie w danej marszrucie. Aparat planowania określi, że tylko urządzenie M2 spełnia wymagania źródłowe.

## <a name="competencies-for-human-resources"></a>Kwalifikacje dla zasobów ludzkich
Jeśli korzystasz z zasobów operacyjnych typu **zasoby ludzkie** połączonych z pracownikami w module Zasoby ludzkie, możesz także korzystać z kwalifikacji pracowników podczas definiowania wymagań źródłowych dla marszruty produkcji. Innymi słowy, można także określić wymagania dotyczące określonych umiejętności, kursów, certyfikatów i tytułów. Aparat planowania może wybrać zasoby, które są połączone z pracownikami, a wybór będzie opierać się na kompetencjach tych pracowników. Kwalifikacje ustawia się w module zasobów ludzkich, nie na stronie **możliwości zasobu**. Podczas definiowania umiejętności, kursów, certyfikatów i tytułów jako wymagania źródłowego należy użyć funkcji zasobów ludzkich i połączyć każdy zasób typu **Zasoby ludzkie** z odpowiednim pracownikiem. Jeśli nie używasz funkcji zasobów ludzkich, możesz określić możliwości na stronie **Możliwości zasobu**, na której znajdują się podobne lub takie same kompetencje, co w module Zasoby ludzkie. Jednakże strona **możliwości zasobu** nie zawiera funkcji koniecznych do obsługi kwalifikacji, kursów, certyfikatów lub tytułów.




