---
title: Okresy podziału w arkuszach okresowych
description: Ten temat zawiera informacje o funkcji okresów podziału w arkuszach okresowych i arkuszach cyklicznych dla firm w Czechach, Estonii, na Węgrzech, na Łotwie, na Litwie, w Polsce i w Rosji.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 261354
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 91ae972203c7dab6df06a02a3024336a5b8f54376448005ea4fe033bb2159f2d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778847"
---
# <a name="split-periods-in-periodic-journals"></a>Okresy podziału w arkuszach okresowych

[!include [banner](../includes/banner.md)]

Arkusze okresowe są czasami nazywane arkuszami cyklicznymi, ponieważ kwota, tekst i inne informacje są powtarzane zawsze podczas księgowania arkusza. Podczas tworzenia arkusza należy określić interwał czasowy dla cyklu, taki jak dni lub miesiące. Można także określić liczbę okresów, dla których arkusz będzie księgowany.

Aby wielokrotnie pobierać i księgować wiersze transakcji, można użyć strony **Arkusze okresowe**. Dla firm w Czechach, Estonii, na Węgrzech, Łotwie, Litwie, w Polsce i Rosji strona **Arkusze okresowe** została rozszerzona o funkcjonalność podziału na okresy. Aby uzyskać więcej informacji, zobacz [Księgowanie arkuszy okresowych](../general-ledger/tasks/post-periodic-journals.md)

### <a name="example-split-for-periods-in-periodic-journals"></a>Przykład: Podział na okresy w arkuszach okresowych

Firma ubezpieczeniowa oferuje organizacji rabat na przedpłatę polisy ubezpieczeniowej na cały rok. Płatność jest zaksięgowana na koncie aktywów, takich jak przedpłaty na ubezpieczenia. Następnie miesięczny koszt ubezpieczenia jest amortyzowany w ciągu roku przez utworzenie arkusza okresowego, który zawiera kredyt na koncie przedpłat na ubezpieczenia i debet na koncie kosztów ubezpieczenia. W takim przypadku można użyć funkcji podziału na okresy. Kliknij przycisk **Podziel na okresy** znajdujący się w okienku akcji na stronie **Wiersze arkusza** **okresowego**, a następnie wypełnij następujące pola.


| Pole            | Opis                                                                                                                                                                                             |
|-----------------------|---------------------------------------------------------------|
| **Data rozpoczęcia**        | Wybierz datę dla pierwszego wiersza arkusza okresowego.                                                                                                                                                        |
| **Liczba okresów** | Wprowadź liczbę okresów, na które zostanie podzielony wiersz dziennika. Ta wartość określa liczbę nowych transakcji, które zostaną wygenerowane. Kwota transakcji jest równo dzielona między nowymi transakcjami. |
| **Jednostka**              | Wybierz jednostkę miary okresu.                                                                                                                                                                  |
| **Zakres czasowy**   | Określ interwał (odstęp czasu) między okresami księgowania.                                                                                                                                                              |

Na przykład aby wygenerować kwartalne księgowania, wprowadź **4** w polu **Liczba okresów**, zaznacz opcję **Miesiące** w polu **Jednostka** i wprowadź **3** w polu **Zakres czasowy**. System generuje cztery wiersze arkusza, każdy dla jednej czwartej wprowadzonej kwoty wiersza arkusza, w 3-miesięcznych interwałach. Podobna funkcjonalność jest również dostępna dla arkusza finansowego. Podczas wyświetlania wierszy arkusza finansowego wybierz kolejno opcje **Arkusz okresowy** &gt; **Zapisz arkusz**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]