---
title: Propozycja wypowiedzenia wynajmu
description: W tym temacie wyjaśniono, jak zaproponować zakończenie wynajmu.
author: moaamer
manager: Ann Beebe
ms.date: 1/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetLease
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ff3795f26ab10ac19cc3a0dd00dca65095118f45
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207310"
---
# <a name="propose-a-lease-for-termination"></a>Proponowanie wynajmu do zakończenia

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W przypadku wcześniejszego zakończenia wynajmu, wynajem aktywów może rejestrować zapis w dzienniku wypowiedzenia, aby odpisać zobowiązanie z tytułu wynajmu, składnik aktywów z tytułu prawa do użytkowania (ROU) i skumulowaną amortyzację oraz zaksięgować zysk lub stratę. Proces wcześniejszego wypowiedzenia kończy umowę najmu i powiązane księgi wynajmu. Nie oznacza to zakończenia poszczególnych ksiąg wynajmu. W tym temacie opisano funkcję, która umożliwia zaproponowanie wynajmu do zakończenia i przetworzenie zapisu księgowego zakończenia wynajmu.

Jeśli wynajem nie jest klasyfikowany jako wynajmu z odroczonym czynszem najmu i nie jest powiązany ze środkiem trwałym, w ramach leasingu środków trwałych powstaje następujący wpis dziennika zakończenia.

| Transakcji                           | Debet (Dr.) | Kredyt (Cr.) |
|---------------------------------------|-------------|--------------|
| Zobowiązanie z tytułu wynajmu                   | X           |              |
| Dr. Umorzenie          | X           |              |
| Wynikajacy zysk (strata) z modyfikacji wynajmu | X           |              |
| Cr. Składnik majątku wynajmu                       |             | X            |
| Cr. Wynikajacy zysk (strata) z modyfikacji wynajmu |             | X            |

Jeżeli księga wynajmu jest klasyfikowana jako książka czynszów odroczonych, zapis odpisuje saldo odroczonego czynszu najmu przed wypowiedzeniem na rachunek zysków lub strat, jak pokazano tutaj.

| Transakcji                           | Debet (Dr.) | Kredyt (Cr.) | 
|---------------------------------------|-------------|--------------|
| Dr. Odroczony czynsz                     | X           |              |
| Cr. Wynikajacy zysk (strata) z modyfikacji wynajmu |             | X            |
| Cr. Odroczony czynsz                     |             | X            |
| Wynikajacy zysk (strata) z modyfikacji wynajmu | X           |              |

Jeżeli księga leasingu jest połączona ze środkiem trwałym, środek ROU jest rozliczany w środkach trwałych. To rozliczenie obejmuje rozliczanie przedterminowego rozwiązania umowy. Wynajem aktywów tworzy następujący zapis księgowy w celu odpisania zobowiązania z tytułu wynajmu.

| Transakcji                           | Debet (Dr.) | Kredyt (Cr.) |
|---------------------------------------|-------------|--------------|
| Zobowiązanie z tytułu wynajmu                   | X           |              |
| Cr. Wynikajacy zysk (strata) z modyfikacji wynajmu |             | X            |

Aby uzyskać informacje na temat poprawnego sposobu likwidacji środka trwałego typu ROU, zobacz temat [Likwidacja środka trwałego jako odpadków](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md).

## <a name="propose-a-lease-for-termination"></a>Proponowanie wynajmu do zakończenia

1. Przejdź do wynajmu, który ma być zakończony, a następnie w okienku akcji wybierz opcję **Propozycja rozwiązania umowy**.

    > [!NOTE]
    > Przycisk **Propozycja zerwania umowy** jest niedostępny, jeśli istnieją niezaksięgowane wpisy arkusza dotyczące żadnej księgi. Przed wypowiedzeniem dzierżawy należy zaksięgować lub usunąć wszelkie zapisy księgowe, które zostały utworzone w ramach dzierżawy.

2. W wyświetlonym oknie dialogowym należy ustawić pola **Data wprowadzenia** i **Data księgowania** dla wpisu w arkuszu zakończenia zatrudnienia.
3. Wybierz **Propozycję zakończenia zatrudnienia**, aby proponować wynajem za zakończenie zatrudnienia.
4. Wybierz opcję **Księguj zakończenie pozycje wynajmu**, aby automatycznie zak księgować wpis w arkuszu zakończenia wynajmu.
5. Na stronie **Zakończenie wynajmu** wybierz identyfikator wynajmu proponowany dla zakończenia, aby wyświetlić wiersze zakończenia wynajmu. Wiersze dotyczące wypowiedzenia przedstawiają wartości bilansowe aktywa ROU, zobowiązania z tytułu wynajmu, skumulowanej amortyzacji, odroczonego czynszu (jeśli dotyczy) oraz zysków lub strat, które należy ująć w momencie zakończenia wynajmu.

Wynajem jest teraz gotowy do zakończenia. Wartość pola **Stan zakończenia** zatrudnienia w księdze wynajmu zostanie zmieniona na **Gotowe do zakończenia**. Na tym etapie nie można już księgować wpisów arkusza z wynajmem ani korygować ani zawęzać ich. 

## <a name="process-leases-that-are-ready-for-termination"></a>Przetwarzanie wynajmów gotowych do zakończenia zatrudnienia

Aby przetworzyć wynajmy gotowe do zakończenia i zakłocować wpis w arkuszu zakończenia zatrudnienia, wykonaj następujące kroki.

1. Na stronie **Zakończenie wynajmu** wybierz wynajem do przetworzenia, a następnie wybierz opcję **Zwalnianie**.
2. W oknie dialogowym wybierz **Ok**.

System księguje wpis arkusza zakończenia zatrudnienia. Pole **Stan wynajmu** dla księgi dzierżawy ma wartość **Zakończono**, a pole **Stan propozycji zakończenia** ma wartość **Zakończono**.

## <a name="reverse-a-lease-termination"></a>Wycofanie zakończenia wynajmu

Aby wycofać wpis w arkuszu zakończenia wynajmu i otworzyć wynajm zakończony, wykonaj ten krok.

- Na stronie **Zakończenie wynajmu** wybierz wynajem do zakończenia, a następnie wybierz opcję **Odwrotne zakończenie**.

System księguje wpis arkusza odwrotnego zakończenie zatrudnienia. Pole **Stan wynajmu** dla księgi dzierżawy ma wartość **Otwarte**. Wynajm nie będzie już wyświetlany na stronie **Zakończenie wnajmu** i może zostać ponownie zaproponowana jako rozwiązanie umowy.

## <a name="example-of-a-lease-termination"></a>Przykład zakończenia wynajmu

W tym przykładzie leasing jest powiązany z niewyspecjalizowanym składnikiem aktywów i nie powoduje przeniesienia własności składnika aktywów ani nie daje leasingobiorcy opcji zakupu tego składnika.

### <a name="setup"></a>Konfiguracja

W poniższych tabelach przedstawiono wartości ustawione na kartach **Ogólne** i **Wiersze harmonogramu płatności** dla wynajmu używanego w tym przykładzie.

**Karta Ogólne**

| Pole                      | Wartość            |
|----------------------------|------------------|
| Wartość godziwa składnika majątku    | 600,000          |
| Waluta                   | USD              |
| Początkowe koszty bezpośrednie       | 1 000            |
| Krańcowa stopa procentowa | 7%               |
| Interwał łączenia       | Co rok         |
| Okres użyteczności składnika majątku (w miesiącach) | 600              |
| Typ annuity               | Zwykła annuita |
| Data rozpoczęcia          | 1.1.2019         |

**Karta Wiersze harmonogramu płatności**

| Pole             | Wartość      |
|-------------------|------------|
| Rozpoczęcie        | 1.1.2019   |
| Zakres czasowy   | Miesięczne    |
| Okresy           | 120        |
| Data końcowa          | 31.12.2028 |
| Częstość płatności | Co rok   |
| Kwota płatności    | 10,000     |

### <a name="steps-for-terminating-the-lease"></a>Kroki do końenia wynajmu

1. Po utworzeniu wynajmu zgodnie z opisem wcześniej w tym temacie należy przejść do książki wynajmu i potwierdzić harmonogram płatności. Następnie należy zaksięgować wpis w arkuszu dotyczący początkowego ujęcia. Początkowa wartość składnika majątku z PDU to $71 235,81 i zobowiązania z tytułu wynajmu powinna wynosić 70 235,81 zł. W tym przykładzie leasing został sklasyfikowany jako wynajm operacyjny zgodnie z kodyfikacją standardów rachunkowości, temat 842 (ASC 842).
2. Uruchom trzy razy proces arkusza przetwarzania wsadowego, aby zasymulować upływ trzech lat dla opłat z tytułu wynajmu, kosztów odsetek i wydatków amortyzacji.
3. Po zakończeniu wykonywania wszystkich trzech zadań wsadowych wróć do księgi wynajmu, a w nich otwórz tabele transakcji na pasywach i aktywach, aby wyświetlić bieżącą wartość bilansową składnika majątku z PDU i zobowiązania z tytułu wynajmu. Po trzech latach wartość zobowiązania powinna wynosić w przybliżeniu -53 893,00 $, a wartość składnika majątku powinna wynosić w przybliżeniu 53 893,00 $.

    Po upływie tych trzech lat firma i najmodawca uzgadniają się wzajemnie, aby zakończyć wynajm. W związku z tym musisz teraz zakończyć wynajmu.

4. Przejdź do wynajmu, który ma być zakończony, a następnie w okienku akcji wybierz opcję **Propozycja rozwiązania umowy**. 
5. W oknie dialogowym, które zostanie wyświetlone, w polu **Data wprowadzenia** i **Data księgowania** wprowadź datę **2021-01-01**.
6. Wybierz **Propozycję zakończenia zatrudnienia**, aby proponować wynajem za zakończenie zatrudnienia.

    Zostanie wyświetlona strona **Zakończenie wynajmu** i pokazuje wynajm, która zostanie przerwany.

7. Aby wyświetlić wiersze zakończenia, wybierz identyfikator dzierżawy, dla której zaproponowano zakończenie. Wiersze zakończenia wskazują wartości bilansowania dzierżawy. W poniższej tabeli przedstawiono wartości, które powinny być podane w tym przykładzie. 

    | Pole                                                 | Wartość      |
    |-------------------------------------------------------|------------|
    | Saldo bilansowe zobowiązań w walucie transakcji | 53 892,89$ |
    | Środek trwały z prawa do użycia w walucie transakcji            | 71,235.81$ |
    | Umorzenie w walucie transakcji      | 16 642,92$ |
    | Zysk (strata) w walucie transakcji                   | -700,00$   |

8. Aby zaksięgować zapis księgowy dotyczący zakończenia, wybierz dzierżawę na stronie **Zakończenie wynajmu** wybierz wynajem do zakończenia, a następnie wybierz opcję **Zakończ**.
9. W oknie dialogowym wybierz **Ok**.
10. Aby wyświetlić wpis w arkuszu zakończenia zatrudnienia, który został utworzony i zaksięgowany, przejdź do arkusza wynajmu środka trwałego w księdze wynajmu. Poniższa tabela pokazuje, jak ten wpis powinien wyglądać w tym przykładzie.

    | Transakcji                           | Debet (Dr.) | Kredyt (Cr.) |
    |---------------------------------------|-------------|--------------|
    | Zobowiązanie z tytułu wynajmu                   | 53,892.89   |              |
    | Dr. Umorzenie          | 16,642.92   |              |
    | Wynikajacy zysk (strata) z modyfikacji wynajmu | 700.00      |              |
    | Cr. Składnik majątku wynajmu                       |             | 71,235.81    |

11. Aby wyświetlić efekt netto rozwiązania umowy, w którym aktywa ROU i zobowiązania z tytułu leasingu będą równe 0 (zero), otwórz tabele transakcji zobowiązań i aktywów.

Stan wynajmu powinien teraz mieć stan **Przerwane**. Żadne dodatkowe wpisy w arkuszu nie będą księgowane dla tego wynajmu, chyba że zakończenie zostanie wycofane.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]