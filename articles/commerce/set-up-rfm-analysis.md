---
title: Konfigurowanie analizy RFM (wg daty ostatniego zakupu, częstotliwości i wartości pieniężnej)
description: W tym temacie omówiono konfigurowanie analizy ostatniego zakupu, częstotliwości i wartości pieniężnej (RFM) dla odbiorców.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRRFMDefinition
audience: Application User
ms.reviewer: josaw
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7a216b237052e084e7efac2580bf5ff9846d3127
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985682"
---
# <a name="set-up-recency-frequency-and-monetary-rfm-analysis"></a>Konfigurowanie analizy RFM (wg daty ostatniego zakupu, częstotliwości i wartości pieniężnej)

[!include [banner](includes/banner.md)]

W tym temacie omówiono konfigurowanie analizy ostatniego zakupu, częstotliwości i wartości pieniężnej (RFM) dla odbiorców.

Analiza RFM (wg daty ostatniego zakupu, częstotliwości i wartości pieniężnej) to narzędzie marketingowe, które organizacja może używać do oceny danych generowanych przez zakupy. Po skonfigurowaniu analizy RFM, do odbiorców przypisywana jest obliczona punktacja RFM według wykonanych zakupów. Punktacja RFM może być trzycyfrową oceną lub sumę liczbową, zależnie od sposobu skonfigurowania analizy RFM przez organizację. Poniżej przedstawiono sposób działania ocen, jeżeli organizacja używa wyniku w postaci trzycyfrowej oceny:

- Pierwsza wartość to ocena odbiorcy według daty ostatniego zakupu.
- Druga wartość to ocena częstotliwości odbiorcy, czyli jak często odbiorca dokonuje zakupów od organizacji.
- Trzecia wartość to ocena wartości pieniężnej odbiorcy, czyli ile pieniędzy odbiorca wydaje, gdy kupuje towary w Twojej firmie.

Załóżmy, że w Twojej firmie używana jest skala ocen od 1 do 5, gdzie 5 oznacza najwyższą ocenę. W tym przypadku jeśli odbiorca otrzymał ocenę 535, można z tego wywnioskować następujące fakty:

- **Ocena daty ostatniego zakupu 5** — ostatni zakup dokonany przez odbiorcę miał miejsce niedawno.
- **Ocena częstotliwości 3** — odbiorca kupuje produkty od organizacji z średnią częstotliwością.
- **Ocena wartości pieniężnej 5** — gdy odbiorca dokonuje zakupu, wydaje znaczną kwotę pieniędzy.

Jeśli organizacja używa sum liczbowych do określania wyniku, poszczególne wyniki są sumowane. Jeśli weźmiemy jeszcze raz ten sam przykład, odbiorca otrzymuje ocenę 13 (5 + 3 + 5).

## <a name="set-up-rfm-analysis-for-the-customers-in-your-organization"></a>Konfigurowanie analizy RFM dla odbiorców w organizacji

1. Wybierz kolejno opcje **Biuro obsługi** \> **Okresowe** \> **Analiza RFM**.
2. Na stronie **Analiza RFM** wybierz opcję **Nowa**. W polu **Definicja RFM** wprowadź nazwę definicji RFM. Na przykład można nazwać definicję RFM-A.
3. Wprowadź datę początkową i końcową dla definicji RFM.
4. Na skróconej karcie **Ogólne** wykonaj poniższe czynności:

    - Jeśli każda sekcja punktacji RFM musi zawierać równe liczby odbiorców, zaznacz pole wyboru **Rozkład równomierny**.
    - Zaznacz pole wyboru **Dodaj punktacje**, aby otworzyć sumę trzech wyników. W ten sposób, przykładowo, odbiorca uzyska punktację RFM równą 13 zamiast 535.
    - Zaznacz pole wyboru **Zapisz historię**, aby wymagać od systemu zapisywanie danych statystycznych dla odbiorców, tak aby dane mogły służyć do obliczania punktacji RFM.

5. Na skróconej karcie **Recency** wykonaj poniższe czynności:

    - W polu **Oddziały** wprowadź numer dzielenia lub grup, które będą używane do obliczania punktacji recency dla odbiorców. Na przykład, jeśli masz 100 odbiorców, dzielenie 5 oznacza, że nie ma 20 odbiorców dla każdego wyniku. 20 odbiorców, którzy ostatnio dokonali zakupu ma punktację recency wynoszącą 5. Kolejnych 20 odbiorców ma punktację recency wynoszącą 4 itd. Jeśli masz 50 odbiorców, 10 odbiorców otrzyma punktację recency równą 5, 10 otrzyma punktację recency 4 i tak dalej.
    - W polu **Priorytet** wybierz, jaką wagę można przyznać dla parametru recency w stosunku do innych parametrów przy obliczaniu punktacji RFM dla odbiorcy. Na przykład użytkownikowi może zależeć bardziej na punktacji recency niż na punktacji wg wartości pieniężnej.
    - W polu **Mnożnik** wprowadź wartość, przez którą ma zostać pomnożona punktacja recency. Jeśli wartość nie zostanie wprowadzona, punktacja nie będzie mnożona.
    - W polu **Okres** wybierz przedział czasu, w których jest obliczana punktacja recency. Na przykład, według tygodnia lub miesiąca.

6. Na skróconej karcie **Częstotliwość** wykonaj poniższe czynności:

    - W polu **Oddziały** wprowadź numer dzielenia lub grup, które będą używane do obliczania punktacji częstotliwości dla odbiorców.
    - W polu **Priorytet** wybierz, jaką wagę można przyznać dla parametru częstotliwości w stosunku do innych parametrów przy obliczaniu punktacji RFM dla odbiorcy.
    - W polu **Mnożnik** wprowadź wartość, przez którą ma zostać pomnożona punktacja częstotliwości. Jeśli wartość nie zostanie wprowadzona, punktacja nie będzie mnożona.

7. Na skróconej karcie **Waluta** wykonaj poniższe czynności:

    - W polu **Oddziały** wprowadź numer dzielenia lub grup, które będą używane do obliczania punktacji wg wartości pieniężnej dla odbiorców.
    - W polu **Priorytet** wybierz, jaką wagę można przyznać dla parametru wartości pieniężnej w stosunku do innych parametrów przy obliczaniu punktacji RFM dla odbiorcy.
    - W polu **Mnożnik** wprowadź wartość, przez którą ma zostać pomnożona punktacja wg wartości pieniężnej. Jeśli wartość nie zostanie wprowadzona, punktacja nie będzie mnożona.
    - W polu **Brutto/netto** wybierz, czy przy obliczaniu punktacji wg wartości pieniężnej system powinien używać kwoty zafakturowanej brutto czy netto.
    - Jeśli kwoty zwrotu dla odbiorcy powinny zostać odjęte od łącznej kwoty faktury dla odbiorcy, zaznacz pole wyboru **Odejmij zwroty**.

## <a name="view-a-customers-rfm-score"></a>Wyświetlanie wyniku RFM klienta

Ta procedura umożliwia wyświetlenie wyniku RFM odbiorcy.

1. Wybierz kolejno opcje **Biuro obsługi** \> **Arkusze** \> **Obsługa klienta**.
2. Na stronie **Obsługa klienta**, w okienku **Obsługa klienta**, w polach wyszukiwania, wybierz typ słowa kluczowego do wyszukania i wprowadź wyszukiwany tekst.
3. Wybierz opcję **Wyszukaj**.
4. Na stronie **Wyszukiwanie odbiorcy** wybierz odpowiedni rekord odbiorcy, a następnie kliknij przycisk **Wybierz odbiorcę**.

Wynik RFM jest wyświetlany w grupie **Historia zamówienia** w prawej części strony **Obsługa klienta**.

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>Wyświetlanie lub czyszczenie historii rekordu analizy RFM

Należy użyć tej procedury w celu wyświetlenia lub wyczyszczenia historii rekordu analizy RFM.

1. Wybierz kolejno opcje **Biuro obsługi** \> **Okresowe** \> **Analiza RFM**.
2. Na stronie **Analiza RFM** wybierz rekord do wyświetlenia.
3. Aby wyświetlić historię rekordu, wybierz kartę skróconą **Historia**.
4. Aby wyczyścić historię rekordu, wybierz opcję **Wyczyść historię**.
