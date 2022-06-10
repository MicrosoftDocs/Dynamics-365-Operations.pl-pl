---
title: Księgowanie zleceń produkcyjnych
description: Ten temat zawiera informacje o różnych typach księgowania zleceń produkcyjnych.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, ProjCategory, CostSheetDesigner
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: cd1b6c49e59f9480fd831ad5ff143033ca09792c
ms.sourcegitcommit: 5b55f2913e736d12e40c227bf3ce3a9abec815bd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/24/2022
ms.locfileid: "8803020"
---
# <a name="production-postings"></a>Postowanie produkcji

Ten temat zawiera informacje o różnych typach księgowania w procesie zlecenia produkcyjnego.


## <a name="material-consumption"></a>Zużycie materiału

Materiały są rejestrowane jako zużyte w trakcie produkcji, gdy księgowany jest arkusz listy pobrania produkcji. W ten sposób powstają transakcje, które odejmują stan zapasów na stanie. W **parametrach produkcji** można określić, czy wartość surowców będących w toku (Praca w toku WIP) ma być księgowane w księdze.

Wartość surowców w toku (WIP) jest księgowana na kontach **Szacunkowy koszt zużytych materiałów** i **Szacunkowy koszt zużytych materiałów, WIP**. Proces tworzenia listy kompletacyjnej dla zlecenia produkcyjnego jest fizyczną aktualizacją transakcji inwentaryzacyjnych związanych ze zleceniem produkcyjnym. Kiedy zlecenie produkcyjne zostaje zarejestrowane jako zakończone, transakcje fizyczne są odwracane, a powiązane z nimi transakcje inwentaryzacyjne są aktualizowane finansowo. Kiedy księgowany jest arkusz zamknięcia, używane są typy księgowania **Koszt zużytych materiałów** oraz **Koszt zużytych materiałów, WIP**.

Zakładka **Produkcja** na stronie **Profilów księgowania zapasów** kontroluje sposób księgowania zleceń produkcyjnych w księdze głównej. Jest ono używane, gdy pole **Księga zaksięgowań** jest ustawione na **Element i zasób** lub **Element i kategoria** na stronie **Parametry kontroli produkcji**. 

Aby arkusz listy pobrań został zaksięgowany w księdze głównej dla zlecenia produkcyjnego, muszą być spełnione następujące warunki:

-   Pole wyboru **Postaw listę kompletacji w księdze** musi być zaznaczone na stronie **Parametry kontroli produkcji**. To ustawienie może zostać zmienione dla konkretnej strony na stronie **Parametry kontroli produkcji według stron**.
-   Pole wyboru **Sporządzenie inwentaryzacji zapasów fizycznych** musi być zaznaczone na stronie **Grupy modeli przedmiotów** dla pozycji wybranej w linii zamówienia zakupu.
-   Konta główne muszą być określone na stronie na stronie **Profil księgowania zapasów** dla następujących typów księgowania:
    -   **Koszty szacowane zużytych materiałów**
    -   **Koszty szacowane zużytych materiałów, PWT**

## <a name="time-consumption"></a>Zużycie czasu

Czas, jaki pracownicy poświęcają na realizację zadań związanych z produkcją, jest rejestrowany w arkuszu **Karta marszruty** lub **Karta zadań**. Te arkusze są księgowane na specjalnym koncie dla zasobów będących w toku (PWT). Takie księgowanie pokazuje czas realizacji zlecenia produkcyjnego. Po zarejestrowaniu zlecenia produkcyjnego jako zakończonego konta PWT są rozliczane.

Istnieją trzy możliwe sposoby księgowania zużycia czasu w zależności od opcji wybranej w polu **Księgowanie** na stronie **Parametry kontroli produkcji**.

## <a name="reporting-finished-goods-and-error-quantities"></a>Zgłaszanie gotowych wyrobów i ilości błędów

Kiedy zlecenie produkcyjne jest **Raportowane jako zakończone**, wyroby gotowe, które zostały ukończone, są aktualizowane w inwentarzu poprzez arkusz **Raportowane jako zakończone**. Jeśli stosujesz księgowanie WIP, arkusz księgi jest księgowany w celu zmniejszenia kont WIP i zwiększenia stanu zapasów wyrobów gotowych. arkusz używa kosztu standardowego, który został zdefiniowany dla danego produktu. Jeśli na stronie **Parametry kontroli produkcji** zaznaczona jest opcja **Użyj szacunkowej ceny**, zostanie użyty szacunkowy koszt ze zlecenia produkcyjnego.

Wartość surowców w toku (WIP) jest księgowana na kontach **Oszacowany koszt wytworzenia** i **Oszacowany koszt wytworzenia, WIP**. Proces **Zgłoś jako zakończone** dla zlecenia produkcyjnego jest fizyczną aktualizacją transakcji inwentaryzacyjnych związanych ze zleceniem produkcyjnym. Kiedy zlecenie produkcyjne zostaje zakończone, transakcje fizyczne są odwracane, a powiązane z nimi transakcje inwentaryzacyjne są aktualizowane finansowo. Kiedy księgowany jest arkusz zamknięcia, używane są typy księgowania **Koszt wytworzenia** oraz **Koszt wytworzenia, WI**.

Karta **Produkcja** na stronie **Profile księgowania**, która służy do kontrolowania, w jaki sposób zlecenia produkcyjne będą księgowane w księdze głównej. Jest ono używane, gdy pole **Księga zaksięgowań** jest ustawione na **Element i zasób** lub **Element i kategoria** na stronie **Parametry kontroli produkcji**. Szybka zakładka **Przedmioty księgi głównej** na stronie **Grupy produkcyjne** może być także używana do kontrolowania księgowania zleceń produkcyjnych, gdy pole jest ustawione na **Grupy produkcyjne**.

Aby arkusz **Raportuj jako zakończone** został zaksięgowany w księdze głównej dla zlecenia produkcyjnego, muszą być spełnione następujące warunki:
-   Pole wyboru **Księguj raport jako gotowy w księdze** musi być zaznaczone na stronie **Parametry kontroli produkcji**. To ustawienie może zostać zmienione dla konkretnej strony na stronie **Parametry kontroli produkcji według stron**.
-   Pole wyboru **Sporządzenie inwentaryzacji zapasów fizycznych** musi być zaznaczone na stronie **Grupy modeli przedmiotów** dla pozycji wybranej w linii zamówienia zakupu.
-   Konta główne muszą być określone na stronie na stronie **Profil księgowania zapasów** dla następujących typów księgowania:
    -   **Szacowany koszt wyprodukowanych towarów**
    -   **Szacowany koszt wyprodukowanych towarów, PWT**

## <a name="ending-the-production-order"></a>Kończenie zlecenia produkcyjnego

Zanim zlecenie produkcyjne zostanie zakończone, dla wyprodukowanej ilości obliczane są koszty rzeczywiste. Wszystkie szacowane koszty materiałów, robocizny i narzutów zostają wycofane i zastąpione kosztami rzeczywistymi. Całkowity koszt gotowego produktu obciąża konto **Koszt wytworzenia** i uznaje konto **Koszt wytworzenia, WIP**. Materiały, które zostały zużyte podczas realizacji zlecenia produkcyjnego, są dopisywane do konta **Koszt zużytych materiałów** i obciążają konto **Koszt materiałów, WIP**.

Jeśli w momencie uruchamiania obliczenia kosztów jest zaznaczone pole wyboru **Zakończ zadanie**, stan zlecenia produkcyjnego zmienia się na **Zakończone**. Ten stan zapobiega przypadkowemu zaksięgowaniu dodatkowych kosztów dla ukończonego zlecenia produkcyjnego. Możesz określić, że wartość ilości błędów, które są zgłaszane jako zakończone, powinna być przypisana do ilości towaru, które są zgłaszane jako zakończone. Można też określić, że ilość błędów powinna być księgowana na specjalnym koncie odpadków. 

Aby określić konkretne konto odpadków, wykonaj poniższe kroki:
1.  Wybierz kolejno opcje **Kontrola produkcji** > **Ustawienia** > **Parametry kontroli produkcji**.
2.  Wybierz zakładkę **Standardowa aktualizacja**.
3.  W polu **Metoda odpadków** wybierz opcję **Alokacja**.
4.  W polu **Konto odpadków** wybierz konto główne, na którym ma być zaksięgowany złom dla ilości błędu po zakończeniu zlecenia produkcyjnego. Na przykład wybierz konto Wydatków, takie jak 510380: Odpadki produkcyjne.

Aby arkusz końcowy zaksięgował się w księdze głównej dla zlecenia produkcyjnego, muszą być spełnione następujące warunki:
-   Konta główne muszą być określone na stronie **Profilu księgowania zapasów** lub **Grupy produkcyjnej** dla następujących typów księgowań:
    -   **Koszt zużytych materiałów**
    -   **Koszt zużytych materiałów, PWT**
    -   **Koszt wyprodukowanych**
    -   **Koszt wyprodukowanych, PWT**
-   Konta główne muszą być określone na stronie **Kategorii kosztów**, **Zasobów** lub **Grup zasobów** dla następujących typów:
    -   **Zaabsorbowany koszt wytworzenia**
    -   **Wykorzystany koszt produkcji, PWT**

## <a name="indirect-costs-for-production-orders"></a>Koszty pośrednie dla zleceń produkcyjnych

Kiedy przetwarzasz transakcje dla zlecenia produkcyjnego, możesz skonfigurować koszty pośrednie, aby uchwycić koszty ogólne lub dodatkowe opłaty w księdze głównej. Transakcje fizyczne dotyczące kosztów pośrednich są ujmowane w inwentarzu, gdy tworzysz arkusz kompletacji lub arkusz raportów jako zakończone. Transakcje finansowe dotyczące kosztów pośrednich są ujmowane w zapasach w momencie księgowania arkusza końcowego.

Możesz rozpoznać koszty pośrednie na podstawie zużycia czasu związanego z arkuszami **Karty trasy** lub **Karty pracy**. Transakcje te są odwracane i księgowane na kontach finansowych, gdy kończysz zlecenie produkcyjne. Aby uzyskać więcej informacji, przejdź do działu [Arkusze kalkulacyjne](/supply-chain/cost-management/costing-sheets.md).

## <a name="controlling-the-level-of-ledger-posting"></a>Kontrolowanie poziomu księgowania w księdze

W **Parametrach kontroli produkcji** można użyć pola **Księgowanie w księdze**, aby ustawić poziom księgowania w księdze dla procesów produkcyjnych. 

Dostępne są następujące pola:

### <a name="item-and-resource"></a>Pozycja i zasób

Jeśli w polu **Księga rachunkowa** wybierzesz opcję **Element i zasób**, konta księgowania będą pochodziły z zasobu lub grupy zasobów w operacji na danej trasie. Konta na konkretnym zasobie będą pierwszą opcją księgowania. Jeśli konto nie zostanie podane, zostaną użyte konta określone dla grupy zasobów. Każdy wiersz operacji na trasie może mieć jeden zasób określony jako **Zasób kosztowy**. Ten zasób służy do określania konta, które ma być używane. Ta opcja jest powszechnie używana, gdy organizacja przypisuje koszty operacyjne do zasobów. Koszty są często wyższe w przypadku zasobów i są wykorzystywane do podejmowania decyzji typu "zrobić czy kupić". Jest to najbardziej szczegółowa konfiguracja postów, która umożliwia najbardziej szczegółową kontrolę nad nimi oraz bardzo szczegółową analizę procesu produkcji.

### <a name="item-and-category"></a>Pozycja i kategoria

Gdy wybierzesz opcję **Element i kategoria** w polu **Księga rachunkowa**, konta księgowe będą pochodziły ze strony **Kategorii kosztów** związanej z każdą linią w trasie. Każda linia operacyjna na trasie może mieć trzy kategorie kosztów: **czas przygotowania**, **czas wykonania** oraz **ilość**. Ta opcja jest często używana, gdy organizacja koncentruje się głównie na wydajności procesów i czasie trwania działań. Ta opcja jest bardziej podsumowującym sposobem księgowania, ale nadal pozwala na grupowanie kosztów w kategorie.

### <a name="production-group"></a>Grupa produkcji

Gdy w polu **Księga rachunkowa** wybierzesz opcję **Grupy produkcyjne**, konta do księgowania pochodzą ze strony **Grupy produkcyjne**. **Grupy produkcyjne** są zwykle używane, gdy więcej niż jedna linia produkcyjna wytwarza podobne produkty lub ma podobne wyposażenie. Możesz użyć tej opcji, by porównać koszty dwóch różnych grup produkcyjnych.  
  
> [!NOTE]
> Jeśli zastosowana zostanie standardowa metoda obliczania kosztu gotowej rzeczy, odzwierciedlą to końcowe transakcje. Jeśli koszty rzeczywiste i koszty obliczone metodą standardową różnią się, różnice są księgowane na konto, które wykazuje zysk lub stratę.

### <a name="route-groups-and-ledger-posting"></a>Grupy tras i księgowanie w księgach rachunkowych

Każda linia operacyjna w trasie ma określoną **grupę trasy**. Pola **Czas przygotowania**, **Czas realizacji** i **Ilość** w **Grupie trasy** w grupie **Oszacowanie i kalkulacja kosztów** służą do kontrolowania, czy czas zostanie wykorzystany do kalkulacji kosztów podczas księgowania **Karty zlecenia** lub **arkusza karty trasy** na zleceniu produkcyjnym. Jeśli te opcje są wyłączone, w księdze głównej nie zostanie utworzony bon na zużycie czasu.

Aby **Karta trasy** lub **arkusz karty pracy** został zaksięgowany w księdze głównej dla zlecenia produkcyjnego, muszą być spełnione następujące warunki:

-   Pole **Czas przygotowania**, **Czas realizacji** lub **Ilość** musi być wybrane w grupie **Oszacowanie i kalkulacja kosztów** na stronie **Grupa tras**.
-   Konta główne muszą być określone na stronie **Kategorii kosztów**, **Rutyny**, **Grupy tras** lub **Grupy produkcyjne** dla następujących typów księgowań:
    -   Szacowany zaabsorbowany koszt produkcji
    -   Koszty szacowane towarów zużytych w produkcji, PWT

Poniższy diagram pokazuje związek grupy tras z obliczaniem kosztu całkowitego dla każdej operacji (linii trasy) na danej trasie. Każda linia tras ma jedną grupę tras. Grupa tras kontroluje parametry czasu przygotowania, czasu pracy i ilości. Zakładka **Kategoria kosztów** zawiera trzy opcje **Ustawienie**, **Rozpoczęcie** i **Ilość**, które są włączane w zależności od ustawienia grup tras. Skrócona karta **Czas** ma trzy pola, które zależą od grupy tras.

Formuła, która jest używana, zależy od tego, czy opcja jest włączona w grupie tras. Koszt z wybranej kategorii kosztów jest mnożony przez ilość wprowadzoną w harmonogramie, aby obliczyć koszt całkowity.

:::image type="complex" source="media/RouteGroupRelationship.png" alt-text="Związek grup tras z całkowitym obliczonym kosztem.":::
Związek grup tras z całkowitym obliczonym kosztem. Każda linia tras ma jedną grupę tras. Grupa tras kontroluje parametry czasu przygotowania, czasu pracy i ilości. Zakładka Kategoria kosztów zawiera trzy opcje Ustawienie, Rozpoczęcie i Ilość, które są włączane w zależności od ustawienia grup tras. Zakładka Szybkie czasy ma trzy pola, które są aktywne i rozliczane na podstawie grupy tras. Formuła, która jest używana, zależy od tego, czy opcja jest włączona w grupie tras. Koszt z wybranej kategorii kosztów jest mnożony przez ilość wprowadzoną w harmonogramie, aby obliczyć koszt całkowity.
:::image-end:::

## <a name="sample-posting-profile-configuration"></a>Przykładowa konfiguracja profilu księgowania

Poniższa tabela pokazuje przykłady domyślnych typów księgowań wraz z przykładowymi kontami głównymi i opisami. 

 - Kolumna **Debet/Kredyt** wskazuje, czy transakcja zazwyczaj ma być księgowana po stronie debetowej lub kredytowej, czy w niektórych przypadkach po stronie obydwu. 
 - Kolumna **Konto rozliczeniowe** wskazuje typ księgowania jako konto rozliczeniowe. Kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji. 
 - Kolumna **P/F** wskazuje **P** dla księgowania fizycznego i **F** dla księgowania finansowego. 
 - Kolumna **Wykonaj** wskazuje, czy konto główne określonego typu księgowania jest zazwyczaj takie samo jak inny typ księgowania. Wartość w kolumnie wskazuje typ księgowania, który jest zazwyczaj stosowany.

> [!NOTE]
> Sugerowane konta główne i nazwy kont głównych są propozycjami. Zaleca się, aby współpracować z księgowym, aby ustalić najlepszą konfigurację dla potrzeb firmy.


| Typ księgowania  | Przykład konta głównego | Przykład nazwy konta głównego| Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | Fizyczne czy Finansowe | Śledzenie | Opis |
|---------------|----------------------|--------------------------|--------------|----------------|------------------|-----------------------|--------|------------|
| Koszty szacowane zużytych materiałów      | 140100               | Zapasy materiałów        | Element zawartości        | Środki         | Y                | P                     | Koszt zużytych materiałów                | To konto jest używane, gdy publikujesz arkusz listy pobrań dla zlecenia produkcyjnego. Kompensatą dla tego konta jest Szacowany koszt materiałów, WIP. Kwota na tym koncie jest automatycznie odwracana po zakończeniu zlecenia produkcyjnego. To konto reprezentuje konto zapasów w bilansie.       |
| Koszty szacowane zużytych materiałów, PWT | 150150               | WIP produkcji - materiały | Element zawartości        | Uznanie          | Y                | P                     | Szacowany koszt wyprodukowanych towarów, PWT          | To konto jest używane, gdy publikujesz arkusz listy pobrań dla zlecenia produkcyjnego. Kompensatą dla tego konta jest Szacowany koszt materiałów, zużyte. Kwota na tym koncie jest automatycznie odwracana po zakończeniu zlecenia produkcyjnego. To konto reprezentuje WIP w twoim bilansie.                  |
| Szacowany koszt wyprodukowanych towarów               | 140200               | Zapasy wyrobów gotowych   | Element zawartości        | Uznanie          | Y                | P                     | Koszt wyprodukowanych                         | To konto jest używane, gdy publikujesz raport jako gotowy arkusz dla zlecenia produkcyjnego. Kompensatą dla tego konta jest Szacowany koszt wytworzenia, WIP. Kwota na tym koncie jest automatycznie odwracana po zakończeniu zlecenia produkcyjnego. To konto reprezentuje konto zapasów w bilansie. |
| Szacowany koszt wyprodukowanych towarów, PWT          | 150150               | WIP produkcji - materiały | Element zawartości        | Środki         | Y                | P                     | Koszt wyprodukowanych, PWT                    | To konto jest używane, gdy publikujesz raport jako gotowy arkusz dla zlecenia produkcyjnego. Kompensatą dla tego konta jest Szacowany koszt wytworzenia. Kwota na tym koncie jest automatycznie odwracana po zakończeniu zlecenia produkcyjnego. To konto reprezentuje WIP w twoim bilansie.                     |
| Koszt zużytych materiałów                | 140100               | Zapasy materiałów        | Element zawartości        | Środki         | N                 | P                     | Koszty szacowane zużytych materiałów      | Konto to służy do ujmowania materiałów, które zostały zużyte w zleceniu produkcyjnym podczas procesu kończącego produkcję. Kompensatą dla tego konta jest konto Koszt zużytych materiałów, WIP.                                                                                                    |
| Koszt zużytych materiałów, PWT           | 150150               | WIP produkcji - materiały | Element zawartości        | Uznanie          | N                 | P                     | Koszty szacowane zużytych materiałów, PWT | Konto to służy do ujmowania w WIP materiałów, które są zużywane w zleceniu produkcyjnym podczas procesu kończącego produkcję. Kompensatą dla tego konta jest konto Koszt zużytych materiałów.                                                |
| Koszt wyprodukowanych                         | 140200               | Zapasy wyrobów gotowych   | Element zawartości        | Uznanie          | N                 | P                     | Szacowany koszt wyprodukowanych towarów               | Konto to służy do ujęcia kosztu wyrobów gotowych wyprodukowanych w ramach zlecenia produkcyjnego w momencie zakończenia zlecenia produkcyjnego. Kompensatą dla tego konta jest konto Koszt wytworzenia, WIP.                                                                  |
| Koszt wyprodukowanych, PWT                    | 150150               | WIP produkcji - materiały | Element zawartości        | Środki         | N                 | P                     | Szacowany koszt wyprodukowanych towarów, PWT          | Konto to służy do ujęcia kosztu wyrobów gotowych w WIP, które zostały wyprodukowane w ramach zlecenia produkcyjnego, gdy kończysz zlecenie produkcyjne. Kompensatą dla tego konta jest konto Koszt wytworzenia.                                     |

> [!NOTE]
> **Odbiór WIP** i **Konto rozliczeniowe WIP** są używane z wyceną wsteczną dla lean manufacturing. Aby uzyskać więcej informacji, przejdź do działu [Wycena wsteczna](/supply-chain/cost-management/backflush-costing.md).

