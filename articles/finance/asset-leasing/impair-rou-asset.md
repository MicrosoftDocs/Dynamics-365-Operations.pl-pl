---
title: Utrata wartości składników majątku z prawem do użytkowania
description: W tym temacie opisano funkcję, która rejestruje utratę wartości i dostosowuje harmonogram amortyzacji składnika majątku w leasingu operacyjnym realizowanym według przepisów Accounting Standards Codification Topic 842 (ASC 842).
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7a017cdbcbfa01d4dba383f2b6b7c742e54014e4
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447009"
---
# <a name="impair-right-of-use-assets"></a>Utrata wartości składników majątku z prawem do użytkowania

[!include [banner](../includes/banner.md)]

Jeśli wartość bilansowa składnika majątku z prawem do użytkowania (PDU) jest nie do odzyskania, może być konieczne sprawdzenie, czy składnik majątku utracił wartość. W przypadku stwierdzenia, że składnik majątku utracił wartość, moduł Wynajem składnika majątku może zarejestrować tę utratę i odpowiednio skorygować harmonogram amortyzacji. W tym temacie opisano funkcję, która rejestruje utratę wartości i dostosowuje harmonogram amortyzacji w leasingu operacyjnym realizowanym według przepisów Accounting Standards Codification Topic 842 (ASC 842). Tę samą metodę stosuje się również do wynajmu zgodnego Międzynarodowym Standardem Sprawozdawczości Finansowej nr 16 (MSSF 16).

Pozostałe saldo składnika majątku z PDU będzie amortyzowane liniowo przez pozostałą liczbę okresów, niezależnie od tego, czy wynajem został zaklasyfikowany jako leasing finansowy według MSSF 16, czy jako leasing operacyjny według ASC 842.

## <a name="impair-an-rou-asset"></a>Utrata wartości składnika majątku z PDU

1. Przejdź do wynajmu z utratą wartości i wybierz opcję **Księgi**.
2. W okienku akcji wybierz **Utrata wartości**.
3. W wyświetlonym oknie dialogowym w polu **Kwota utraty wartości** wprowadź kwotę, o jaką składnik majątku utracił wartość. Aby zmniejszyć wartość składnika majątku z PDU, należy wprowadzić wartość dodatnią.
4. W polu **Data transakcji** wprowadź dzień, kiedy ma zostać księgowany wpis utraty wartości.
5. W polu **Pozostałe okresy** wprowadź pozostałą liczbę miesięcy amortyzowania.
6. Włącz parametr **Księguj**, jeśli system ma automatycznie księgować wpis w arkuszu dotyczący wydatku utraty wartości. Jeśli pozostawisz ten parametr wyłączony, system utworzy wpis, ale go nie zaksięguje. Następnie można zaksięgować ten wpis ze strony **Arkusze wynajmu składnika majątku**.
7. Ustawienie w opcji **Wyświetl podgląd przed zaksięgowaniem** wartości **Tak** spowoduje wyświetlenie proponowanego wpisu przed jego utworzeniem lub zaksięgowaniem.
8. Ustawienie opcji **Zamknij księgę** na wartość **Tak** spowoduje zamknięcie książki wynajmu. Nie możesz cofnąć tej czynności. Wpisów nie można księgować dla zamkniętych wynajmów, a zamknięte wynajmy nie mogą być korygowane.
9. Wybierz przycisk **OK**, aby utworzyć lub zaksięgować wpis utraty wartości.
10. Aby wyświetlić harmonogram amortyzacji składnika majątku z utraconą wartością, otwórz harmonogram amortyzacji składników majątku dla tej księgi wynajmu. Składnik majątku będzie teraz amortyzowany liniowo przez liczbę miesięcy wprowadzoną w polu **Pozostałe okresy**.
11. Aby wyświetlić wpis w arkuszu dotyczący wydatku utraty wartości, wybierz opcję **Arkusz wynajmu składnika majątku** w okienku akcji księgi wynajmu z utratą wartości. System tworzy wpis w arkuszu obciążający konto księgowania wydatku utraty wartości, a uznający konto księgowania należności z tytułu wynajmu.
12. Aby wyświetlić nową wartość bilansową składnika majątku z PDU, zaznacz opcję **Transakcje składnika majątku** w okienku akcji księgi wynajmu.

## <a name="example-of-rou-asset-impairment"></a>Przykład utraty wartości składnika majątku z PDU

W tym przykładzie przedmiotem wynajmu jest niespecjalistyczny składnik majątku, który nie powoduje przeniesienia prawa własności ani przyznania najemcy opcji zakupu.

### <a name="setup"></a>Konfiguracja

W poniższych tabelach przedstawiono wartości ustawione na kartach **Ogólne** i **Wiersze harmonogramu płatności** dla wynajmu używanego w tym przykładzie.

**Karta Ogólne**

| Pole                      | Wartość            |
|----------------------------|------------------|
| Wartość godziwa składnika majątku    | 600,000          |
| Krańcowa stopa procentowa | 7%               |
| Interwał łączenia       | Co rok         |
| Okres użyteczności składnika majątku (w miesiącach) | 600              |
| Typ annuity               | Zwykła annuita |
| Data rozpoczęcia          | 01.01.2019       |

**Karta Wiersze harmonogramu płatności**

| Pole             | Wartość      |
|-------------------|------------|
| Rozpoczęcie        | 1.1.2019   |
| Zakres czasowy   | Miesięczne    |
| Okresy           | 120        |
| Data końcowa          | 31.12.2028 |
| Częstość płatności | Co rok   |
| Kwota płatności    | 10,000     |

### <a name="steps"></a>Kroki

1. Po utworzeniu wynajmu zgodnie z opisem wcześniej w tym temacie należy przejść do książki wynajmu i potwierdzić harmonogram płatności. Następnie należy zaksięgować wpis w arkuszu dotyczący początkowego ujęcia. Początkowa wartość składnika majątku z PDU i zobowiązania z tytułu wynajmu powinna wynosić 70 235,81 zł. W tym przykładzie wynajem został zaklasyfikowany jako leasing operacyjny według ASC 842.
2. Uruchom trzy razy proces arkusza przetwarzania wsadowego, aby zasymulować upływ trzech lat dla opłat z tytułu wynajmu, kosztów odsetek i wydatków amortyzacji.
3. Po zakończeniu wykonywania wszystkich trzech zadań wsadowych wróć do księgi wynajmu, a w nich otwórz tabele transakcji na pasywach i aktywach, aby wyświetlić bieżącą wartość bilansową składnika majątku z PDU i zobowiązania z tytułu wynajmu. Po trzech latach wartość zobowiązania powinna wynosić w przybliżeniu -53 893,00 zł, a wartość składnika majątku powinna wynosić w przybliżeniu 53 893,00 zł. 

    Po trzech latach firma wykonuje testy utraty wartości i stwierdza, że składnik majątku z PDU ma utratę wartości wynoszącą 35 000 zł. Należy teraz odnotować tę utratę wartości.
    
4. Przejdź do księgi wynajmu, a następnie w okienku akcji wybierz opcję **Utrata wartości**.
5. Na stronie **Parametry utraty wartości** wprowadź następujące szczegóły.

    | Pole                  | Wartość    |
    |------------------------|----------|
    | Kwota utraty wartości      | 35,000   |
    | Data transakcji       | 1.1.2022 |
    | Pozostałe okresy      | 84       |
    | Księguj                   | Tak      |
    | Wyświetl podgląd przed zaksięgowaniem | Nr       |
    | Zamknij rezerwację             | Nr       |

6. Wpis w arkuszu dotyczący wydatku utraty wartości został utworzony i zaksięgowany. Aby go wyświetlić, przejdź do arkusza wynajmu składnika majątku w księdze wynajmu. Zauważ, że kwota utraty wartości została zaksięgowana po stronie debetowej konta księgowania wydatku utraty wartości oraz po stronie kredytowej konta księgowania składnika majątku z PDU.
7. Aby wyświetlić efekt netto utraty wartości, przejdź do tabeli transakcji na pasywach i aktywach. Zauważ, że wydatek utraty wartości zmniejszył wartość składnika majątku z PDU, ale wartość bilansowa zobowiązania z tytułu wynajmu nie uległa zmianie.

Utrata wartości ma jeszcze jeden efekt, który należy wziąć pod uwagę. Ponieważ wartość składnika majątku z PDU jest teraz znacznie mniejsza od wartości zobowiązania z tytułu wynajmu, musi być amortyzowana inaczej niż wcześniej. Dokładniej rzecz biorąc składnik majątku jest teraz amortyzowany liniowo przez pozostałe 84 miesiące wynajmu, licząc od daty transakcji.
