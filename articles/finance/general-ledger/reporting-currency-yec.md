---
title: Raportowanie waluty jest poza saldem podczas zamykania roku
description: Ten artykuł wyjaśnia, w jaki sposób waluta sprawozdawcza może zostać poza saldem podczas zamykania roku.
author: kweekley
ms.date: 12/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 31f79791330e076d4fbd7b604ba9f9c6cd9b9195
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850265"
---
# <a name="reporting-currency-out-of-balance-when-the-year-end-close-is-run"></a>Raportowanie waluty jest poza saldem podczas zamykania roku

Jeśli funkcja **Świadomość między rozliczeniem księgi a zamknięciem roku** (funkcja **Świadomość**) jest włączona, transakcje księgi, które zostały rozliczone, nie będą dłużej uwzględniane w saldzie otwarcia następnego roku obrachunkowego podczas zamknięcia roku księgi głównej. Wyłączenie transakcji z księgi, które są rozliczane, może stanowić wyzwanie dla klientów na zamknięcie roku, jeśli w księdze zdefiniowana jest waluta sprawozdawcza.

Rozliczenie księgi odbywa się tylko dla waluty księgowej. Podczas rozliczania transakcji w księdze rachunkowej zatwierdzenie potwierdza jedynie, że obciążenia w walucie księgowej są równe uznaniom w walucie księgowej. Kwoty w walucie sprawozdawczej dla tych transakcji w księdze nie są zatwierdzane, więc obciążenia mogą nie być równe uznaniom. Ponadto rozliczenie księgi nie umożliwia automatycznego obliczania i księgowania zysków/strat w walucie raportowania.

Ze względu na te ograniczenia, w momencie rozliczania księgi, transakcja zysku/straty musi być zawarta w walucie sprawozdawczej. Jeśli w rozliczeniu księgi nie uwzględniono zysków/strat, podczas zamykania roku pojawi się komunikat o braku bilansu.

Poniższy przykład pokazuje, jak rozwiązać ten problem przed zamknięciem roku.

## <a name="example-setup"></a>Przykład konfiguracji

Aby skonfigurować ten przykład, włącz funkcję **Świadomość** i skonfiguruj konta główne 110180 rozliczania księgi. Poniższa ilustracja przedstawia transakcje księgowe, które zostały zaksięgowane w encji prawnej DEMF. Walutą księgową DEMF jest dolar amerykański (USD), a walutą sprawozdawczą euro (EUR).

![Zaksięgowane transakcje księgi w walucie raportowania.](./media/reporting-currency-1.png)

Strona **Rozliczenia księgi** zawiera transakcje księgi dla konta głównego 110180. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w siatce, a następnie wybierz polecenie **Wstaw kolumny**. Dodaj kolumnę **Kwota w walucie raportowania**, aby zostały wyświetlone wszystkie kwoty waluty transakcji, waluty rozliczeniowej i waluty raportowania.

![Kwota w kolumnie waluty raportowania dodana do strony Rozliczenia księgi.](./media/Ledger-settlement2.png)

Pierwsze dwie transakcje księgowe na kwotę 100,00 EUR są rozliczane jako jedna grupa, a kolejne dwie transakcje księgowe na kwotę 200,00 EUR są rozliczane jako inna grupa. (Te dwie transakcje będą miały różne identyfikatory rozliczenia). To ustawienie pokazuje, że organizacje mogą mieć wiele grup transakcji w księdze głównej, które są rozliczane w różnym czasie i mają różne daty rozliczenia. Po zakończeniu rozliczania na stronie **Rozliczenia księgi** są wyświetlane następujące informacje przy filtrowaniu w celu pokazywania transakcji o stanie **Rozliczone**.

![Rozliczone transakcje na stronie rozliczeń księgi.](./media/Settled-trans-filtered3.png)

Na stronie **Rozliczenia księgi** wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kolumnę **Kwota**, a następnie wybierz **Podsumuj tę kolumnę**. Powtórz ten krok dla kolumn **Kwota w walucie sprawozdawczej**. Waluta księgowa musi mieć różnicę 0 (zero), aby można było dokonać rozliczenia. Nie ma jednak możliwości zatwierdzenia kwoty rozliczenia dla waluty sprawozdawczej. Poniższa ilustracja pokazuje różnicę -27,79 USD dla waluty sprawozdawczej.

![Różnica dla waluty sprawozdawczej.](./media/Difference4.png)

## <a name="year-end-close"></a>Zamknięcie roku

Jeśli zamknięcie roku zostanie teraz przeprowadzone dla roku 2022, proces ten zakończy się błędem braku równowagi. Ten błąd jest bezpośrednio spowodowany tym, że waluta sprawozdawcza nie ma kwoty rozliczenia w księdze, która ma wartość 0 (zero).

![Komunikat o błędzie, który wskazuje, że kwota rozliczenia księgi nie wynosi 0 (zero).](./media/YEC5.png)

## <a name="posting-reporting-currency-gainloss"></a>Księgowanie zysków/ strat z tytułu różnic kursowych

Aby zamknięcie roku przebiegło pomyślnie, różnica w kwocie w walucie sprawozdawczej musi zostać zaksięgowana, zazwyczaj jako zysk lub strata, i uwzględniona w rozliczeniu księgi. Zysk/strata z waluty sprawozdawczej może być zaksięgowany na wiele sposobów:

- Jeśli głównym kontem są zobowiązania lub należności, to rozliczenie AR/AP tych dokumentów wygeneruje wymagane zyski/straty. Ten zapis księgowy musi zostać uwzględniony w rozliczeniu księgi, gdy zostaną rozliczone odpowiadające mu transakcje z faktury, płatności, noty kredytowej itd.
- Jeśli konto główne jest jakimkolwiek innym kontem niż zobowiązania lub należności, zysk lub stratę należy wprowadzić ręcznie. Poziom szczegółowości zapisu księgowego podczas księgowania zależy od organizacji.
- Dla każdego konta głównego określ kwotę zysku/ straty w walucie sprawozdawczej, którą należy zaksięgować.

Jak opisano wcześniej, to księgowanie można wykonać na stronie **Rozliczenia księgi**.

1. Przefiltruj zakres dat, dla których chcesz zaksięgować zysk/ stratę. Jeśli planujesz zamieszczać informacje o zyskach/stratach w poszczególnych miesiącach, filtruj je dla każdego miesiąca. Jeśli planujesz wykazać zysk lub stratę w danym roku podatkowym, filtruj przez cały rok.
2. Filtruj według konta głównego.
3. Filtruj według stanu, tak aby zostały wyświetlone tylko **Rozliczone** transakcje.
4. Dodaj sumę w kolumnie **Kwota w walucie raportowania**.
5. Jeśli zysk/strata ma być księgowany na bardziej szczegółowym poziomie, można wykonać dodatkowe filtrowanie według identyfikatora rozliczenia, wymiarów finansowych itp Łączna kwota w kolumnie **Kwota w walucie raportowania** przedstawia kwotę, dla jakiej zostanie zaksięgowany zysk/strata.
6. Wybierz kolejno opcje **Księga główna \> Wpisy w arkuszu \> Arkusze korekty z tytułu waluty sprawozdawczej**.
7. Wprowadź transakcję zysku/straty. W tym arkuszu korekta zostanie wprowadzona tylko w walucie sprawozdawczej. Księgowane kwoty w walucie transakcji i walucie rozliczeniowej są zawsze zerowe. Jeśli ten arkusz nie był wcześniej używany, być może trzeba będzie utworzyć nazwę arkusza o typie **Korekta waluty sprawozdawczej** w **Księga główna \> Konfiguracja arkuszy \> Nazwy arkuszy**.
8. Jeśli konto główne nie pozwala na ręczne wprowadzanie danych, korekta ta nie zostanie zaksięgowana. Być może będzie trzeba tymczasowo wyłączyć parametr **Nie zezwalaj na ręczne wprowadzanie** na stronie **Konto główne**.

![Ręczne wprowadzanie danych na stronie Voycher w arkuszu.](./media/Manual-entry6.png)

Po zaksięgowaniu arkusza korekt wróć na stronę **Rozliczenia księgi** i wybierz konto główne, dla których zaksięgowano zysk/stratę. Korekta zysków i strat musi być uwzględniona w rozliczeniu księgi. Ponieważ kwota w walucie sprawozdawczej nie musi być równa 0 (zero), możesz wyłączyć z rozliczenia wszystkie poprzednie transakcje, a następnie rozliczyć je ponownie, tym razem uwzględniając zysk/ stratę. To, jak bardzo chcesz być precyzyjny przy księgowaniu zysków/strat i ich rozliczaniu w księgach rachunkowych, zależy od twojej organizacji.

Poniższa ilustracja pokazuje, że transakcje na kwotę 200 EUR zostały nierozliczone, a następnie ponownie oznaczone do rozliczenia. Tym razem będą uwzględniać korektę zysków i strat.

![Korekta zysków i strat na stronie rozliczeń księgi.](./media/gain-loss7.png)

Po rozliczonych transakcjach zmień filtr **Stan** , tak aby strona zawierała **Rozliczone** transakcje. Suma w kolumnie **Kwota w walucie raportowania** wynosi teraz 0 (zero). Teraz można pomyślnie przeprowadzić zamknięcie roku.

![Pomyślne zamknięcie roku.](./media/Zero-settled8.png)
