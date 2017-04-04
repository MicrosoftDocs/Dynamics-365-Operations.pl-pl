---
title: "Możliwości zasobu"
description: "Ten artykuł zawiera informacje o organizowaniu możliwościach zasobów. Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania. Wyjaśniono, jak możliwości i związane z nimi funkcje, takie jak poziom biegłości i priorytet, służą do wybierania zasobów odpowiednich dla działań."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WrkCtrCapability, WrkCtrTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4463ca8e11115eb83323716faa4ed6b38937a3e4
ms.lasthandoff: 03/31/2017


---

# <a name="resource-capabilities"></a>Możliwości zasobu

Ten artykuł zawiera informacje o organizowaniu możliwościach zasobów. Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania. Wyjaśniono, jak możliwości i związane z nimi funkcje, takie jak poziom biegłości i priorytet, służą do wybierania zasobów odpowiednich dla działań.

Możliwość to zdolność zasobu operacyjnego do wykonania określonego działania. Zasób operacyjny może mieć więcej niż jedną przypisaną możliwość, a możliwości można przypisywać do więcej niż jednego zasobu. Można tymczasowo przypisać możliwości do zasobów operacyjnych, wybierając daty rozpoczęcia i zakończenia w przypisaniu możliwości. Kiedy wygasa możliwość zasobu, zasób nie może zostać uwzględniony w harmonogramie projektu lub produkcji. Wygasłe możliwości można odnowić. Można usunąć możliwości, pod warunkiem że nie znajdują się one w relacji marszruty ani w marszrucie produkcji aktywnego zlecenia produkcyjnego. Ogólnie należy zachować ostrożność w przypadku usuwania możliwości. Zamiast tego należy rozważyć korektę daty ważności zasobów posiadających określone możliwości. Możliwości można przypisać do wszystkich typów zasobów: Narzędzie, Dostawca, Maszyna, Zasoby ludzkie, Lokalizacja, lub Zakład.

## <a name="level"></a>Poziom
Wiele zasobów często ma te same funkcjonalne możliwości, ale inny poziom biegłości (np. siła, szybkość przetwarzania lub dokładność). Dlatego po przypisaniu możliwości do zasobu, można określić wartość **poziomu**. Poziom jest prostą wartością liczbową. Jeśli określisz, że możliwości jest wymaganiem źródłowym dla marszruty produkcji, możesz również określić wartość **Minimalny wymagany poziom** dla danej możliwości. Aparat planowania wybiera potem tylko te zasoby, które mają wymagane możliwości na poziomie równym lub przewyższającym poziom określony w wymaganiu źródłowym.

## <a name="priority"></a>Priorytet
Zasobom operacyjnym o jednakowych możliwościach można przypisać priorytet. Następnie jeśli wiele zasobów mają możliwości, które spełniają wymogi planowania na wymaganym poziomie, a mają wolne moce, aparat planowania można wybrać spośród tych zasobów. Jeśli **priorytet** jest zaznaczone w **wybór zasobu głównego** w **parametry planowania** strony, zasób, który ma najwyższy priorytet (najniższej wartości liczbowe w **priorytet** pola) wybrano pierwszy podczas planowania.

## <a name="resource-requirements"></a>Zapotrzebowanie na zasoby
Po zdefiniowaniu wymagań źródłowych dla marszruty produkcji można określić jedną lub więcej możliwości jako wymagania. Podczas planowania produkcji możliwości zdefiniowane w wymaganiach źródłowych dla operacji marszruty zostaną dopasowane do możliwości określonych dla zasobów. Zostaną wybrane zasoby posiadające możliwości spełniające wymagania. Jeśli wiele zasobów ma taką samą funkcjonalną możliwość, ale inne poziomy biegłości (np. siła szybkość przetwarzania lub dokładność), można zdefiniować wiele możliwości lub użyć poziomu do określenia możliwości zasobu. Oto przykład:

-   W marszrucie proces wiercenia jest ustawiony jako 10 jednostek na godzinę, ale samo wymaganie jest zdefiniowane jako Wiercenie.
-   Są dwa urządzenia wiertnicze: M1 i M2.
-   Możliwość Wiercenie jest przypisana do obu zasobów: do urządzenia M1 i urządzenia M2.
-   Urządzenie M1 może wiercić dwie jednostki na godzinę, a urządzenie M2 może wiercić 11 jednostek na godzinę.

W tym przykładzie oba urządzenia mogą zostać wybrane przez aparat planowania, bo obie spełniają podstawowe wymaganie możliwości (Wiercenie). Ale urządzenie M1 może wiercić tylko dwie jednostki na godzinę. Ze względu na to, że ten współczynnik jest znacznie niższy od 10 jednostek na godzinę określonych w marszrucie, urządzenie M1 spowoduje problemy na etapie produkcji, jeśli zostanie wybrane. Istnieją dwa sposoby rozwiązania tego problemu i upewnienia się, że zostanie wybrane urządzenie M2:

-   Utwórz dwie osobne możliwości: Wolne wiercenie i Szybkie wiercenie. Zdefiniuj Wolne wiercenie jako wiercenie o czasie procesu od 1 do 9 jednostek na godzinę. Zdefiniuj Szybkie wiercenie jako wiercenie o czasie procesu od 10 do 19 jednostek na godzinę. Przypisywanie maszyny M1 możliwości wiercenia niskiej prędkości i przypisywanie maszyny M2 szybkich możliwości wiertnicze. Wreszcie zmienić wymagania dotyczące możliwości zasobu na trasie do wiercenia dużych prędkości. Dzięki temu aparat planowania wybierze prawidłowe urządzenie (M2).
-   Użyj poziomu możliwości do określenia możliwości Wiercenie przypisanej do urządzeń wiertniczych. Określ, że maszyna M1 ma możliwość wiertniczy na poziomie 2.0 i że maszyny M2 ma możliwość wiertniczy na poziomie 11.0. Następnie określ, że 10.0 jest poziomem minimalnym wymaganym do wymagania dotyczące możliwości wiertniczy w marszrucie. Aparat planowania określi, że tylko urządzenie M2 spełnia wymagania źródłowe.

## <a name="competencies-for-human-resources"></a>Kwalifikacje dla zasobów ludzkich
Jeśli korzystasz z zasobów operacyjnych typu **zasoby ludzkie** połączonych z pracownikami w module Zasoby ludzkie, możesz także korzystać z kwalifikacji pracowników podczas definiowania wymagań źródłowych dla marszruty produkcji. Innymi słowy, można także określić wymagania dotyczące określonych umiejętności, kursów, certyfikatów i tytułów. Aparat planowania może wybrać zasoby, które są połączone z pracownikami, a wybór będzie opierać się na kompetencjach tych pracowników. Kwalifikacje ustawia się w module zasobów ludzkich, nie na stronie **możliwości zasobu**. Podczas definiowania umiejętności, kursów, certyfikatów i tytułów jako wymagania dotyczące zasobów, należy użyć funkcji zasobów ludzkich i powiązać każdego zasobu z **zasoby ludzkie** typu do odpowiedniego pracownika. Jeśli nie używasz funkcji zasobów ludzkich, można zdefiniować możliwości na **możliwości zasobów** stronę, która przypominają lub powielanie kompetencje z działu kadr. Jednakże strona **możliwości zasobu** nie zawiera funkcji koniecznych do obsługi kwalifikacji, kursów, certyfikatów lub tytułów.


