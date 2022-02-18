---
title: Relacja między rozliczeniem księgi a zamknięciem roku
description: Ten temat zawiera informacje dotyczące ulepszeń, które mają wpływ na rozliczenia księgi oraz zamknięcie na koniec roku księgi głównej.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: acfbcf1467363262769884063efbc1a6d6e21eb1
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075576"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Relacja między rozliczeniem księgi a zamknięciem roku

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

W Microsoft Dynamics 365 Finance w wersji 10.0.25 funkcja **Wiadomość między rozliczeniem księgi a zamknięciem roku** jest dostępna w przestrzeni roboczej **Zarządzanie funkcjami**. Ta funkcja dodaje dwa podstawowe usprawnienia, które mają wpływ na rozliczenie księgi głównej i zamknięcie roczne księgi głównej.

Podczas zamykania księgi głównej na koniec roku transakcje księgi, które zostały rozliczone, nie będą już uwzględniane w bilansie otwarcia następnego roku podatkowego. To usprawnienie zapewnia, że tylko nierozliczone transakcje księgi są uwzględniane w bilansie otwarcia. Jest to ważne, gdy w księdze głównej dokonuje się przeszacowania walut obcych. Przeszacowanie waluty obcej jest przeprowadzane tylko dla transakcji księgi, które mają status **Nierozliczone**. Jednak zanim została udostępniona funkcja **Wiadomość między rozliczeniem księgi a zamknięciem roku**, bilans otwarcia podsumowywał zarówno transakcje o statusie **Rozliczone**, jak i te o statusie **Nierozliczone**, a status podsumowanej kwoty był ustawiony na **Nierozliczone**.

Drugie usprawnienie pozwala na księgowanie szczegółowych transakcji bilansu otwarcia podczas zamykania księgi głównej na koniec roku. Jeśli opcja **Zachowaj szczegóły podczas zamknięcia roku** jest ustawiona na **Tak**, to dla każdej transakcji księgi, która nie jest rozliczona, zostanie utworzony osobny bilans otwarcia. To ustawienie jest definiowane dla każdego konta głównego w ustawieniach rozliczania księgi. Zachowując szczegółowe transakcje dla bilansu otwarcia, znacznie zwiększasz możliwość rozliczenia nierozliczonych transakcji księgi w następnym roku podatkowym.

Aby wesprzeć nowe usprawnienia, wprowadzono zmiany w rozliczaniu ksiąg i zamykaniu roku.

### <a name="changes-to-ledger-settlement"></a>Zmiany w rozliczeniu księgi

- Rozliczenie księgi musi zostać wykonane w ciągu roku obrachunkowego.
- Rozliczenie księgi musi zostać wykonane dla transakcji na jednym koncie głównym. Konto główne jest teraz wymaganym filtrem na stronie **Rozliczenie księgi**.
- Rozliczenie księgi i odwrócenie rozliczenia księgi nie może być dokonane dla transakcji, które są księgowane w zamkniętym roku podatkowym (innymi słowy, zamknięcie roku zostało przeprowadzone).

### <a name="changes-to-year-end-close"></a>Zmiany w zamknięciu na koniec roku

- Nie można wycofać zamknięcia na koniec roku, jeśli jakieś transakcje otwarcia zostaną rozliczone w następnym roku obrachunkowym. Ta zmiana ma zastosowanie, gdy zamknięcie roku jest odwrócone lub gdy zamknięcie roku jest przeprowadzane ponownie, a opcja **Usuń istniejące wpisy na koniec roku przy ponownym zamknięciu roku** jest ustawiona na **Tak** w parametrach księgi głównej.
- Jeśli opcja **Zachowaj szczegóły podczas zamknięcia roku** jest ustawiona na **Tak** dla dowolnego konta bilansowego w rozliczeniu księgi, to dla tego konta głównego zostaną utworzone bardziej szczegółowe transakcje bilansu otwarcia.

## <a name="before-you-enable-the-feature"></a>Przed włączeniem funkcji

Ze względu na zmiany w funkcjonalności i modelu danych ważne jest, abyś rozważył następujące kwestie, zanim włączysz tę funkcję:

- Wszystkie transakcje, które zostały oznaczone do rozliczenia, ale nie zostały rozliczone, zostaną automatycznie odznaczone, gdy funkcja ta zostanie włączona. Aby uniknąć strat w pracy, zanim włączysz tę funkcję, rozlicz wszystkie zaznaczone transakcje.
- Niektóre organizacje uruchamiają zamknięcie na koniec roku wielokrotnie dla tego samego roku obrachunkowego. Nie włączaj tej funkcji, jeśli zamknięcie roku zostało już raz przeprowadzone i będzie przeprowadzone ponownie w tym samym roku podatkowym. Funkcja ta musi być włączona przed pierwszym zamknięciem roku lub po ostatnim zamknięciu roku podatkowego.

  Jeśli chcesz włączyć tę funkcję, ale zamknięcie roku zostało już raz przeprowadzone, musisz odwrócić zamknięcie roku, zanim będziesz mógł włączyć tę funkcję.

- Ponieważ rozliczenia między latami podatkowymi nie są już dozwolone, zalecamy, abyś włączył tę funkcję przed rozpoczęciem procesu zamknięcia roku. Następnie, aby upewnić się, że na bilans otwarcia następnego roku podatkowego nie mają wpływu poprzednie rozliczenia międzyfiskalne, transakcja bilansu otwarcia powinna być rozliczona dla zamykanego roku podatkowego.
- Ponieważ rozliczenia pomiędzy kontami głównymi nie są już dozwolone, dostosuj swój plan kont lub procesy tak, by zapewnić, że rozliczenia ksiąg będą mogły być dokonywane na tym samym koncie głównym.
- Funkcja ta nie może być włączona, jeśli w sektorze publicznym stosowany jest proces zamknięcia roku.

## <a name="set-up-ledger-settlement"></a>Tworzenie rozliczenia księgi głównej

Po włączeniu tej funkcji, a przed przeprowadzeniem kolejnego zamknięcia roku, każda organizacja musi określić, czy będzie przechowywać szczegóły transakcji podczas zamknięcia roku. Wybór ten nie ma wpływu na księgowania bilansu otwarcia z poprzednich procesów zamknięcia roku.

Opcja **Zachowaj szczegóły podczas zamknięcia roku** jest ustawiana dla każdego konta głównego na stronie **Konfiguracja rozliczenia księgi**.

1.  Wybierz kolejno opcje **Księga główna** > **Ustawienia księgi** > **Parametry księgi głównej**.
2.  W zakładce **Rozrachunki księgi** wybierz **Konta rozrachunkowe księgi**.

— lub —

1.  Wybierz kolejno opcje **Księga główna** > **Zadania okresowe** > **Rozliczenia księgi**.
2.  Wybierz **Konta rozliczeniowe księgi**.

Dwie kolumny zostały dodane do strony **Rozliczenia księgi**:
    
- **Typ konta głównego** – ta kolumna ma wyłącznie cel informacyjny. Pokazuje typ, który jest przypisany do konta głównego.
- **Zachowaj szczegóły podczas zamknięcia na koniec roku** – domyślnie jest ustawiona opcja **No** Wartość **Tak** może być ustawiona tylko wtedy, gdy wartością w kolumnie **typu konta głównego** jest **Arkusz bilansowy**, **Aktywa** lub **Pasywa**. Jeśli ustawiono opcję **Nie**, salda otwarcia będą księgowane w podsumowaniu, jak to jest typowe podczas zamknięcia na koniec roku. Jeśli jest ustawiona wartość **Tak**, salda otwarcia będą tworzone szczegółowo dla każdej transakcji księgi, która nie jest rozliczona dla konta głównego.

## <a name="year-end-close"></a>Zamknięcie roku

Kiedy przeprowadzasz zamknięcie roku, przechodząc do **Księgi Głównej** > **Zamknięcia okresu** > **Zamknięcia roku**, proces ten tworzy bilanse otwarcia dla kont głównych, które są zdefiniowane dla rozliczenia księgi. Salda otwarcia są tworzone w podsumowaniu lub w szczegółach, w zależności od konfiguracji rozliczania księgi. Proces ten wyklucza transakcje księgi, które są rozliczane, niezależnie od tego, czy księgujesz bilans otwarcia dla każdego konta głównego w podsumowaniu czy w szczegółach.

Na przykład wiele transakcji zostaje zaksięgowanych na koncie głównym 130100 w roku fiskalnym 2021.

| Numer arkusza | Załącznik  | Data       | Typ      | Konto finansowe | Nazwa konta        | Opis       | Waluta | Kwota w walucie transakcji | Kwota  | Kwota w walucie raportowania |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 3/12/2021  | Działanie | 130100-001-    | Rozrachunki z odbiorcami | Opłata za usługę       | USD      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 5/12/2021  | Działanie | 130100-002-    | Rozrachunki z odbiorcami | Media         | USD      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 16/12/2021 | Działanie | 130100-001-    | Rozrachunki z odbiorcami | Zwrot            | USD      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 20/12/2021 | Działanie | 130100-002-    | Rozrachunki z odbiorcami |                   | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Działanie | 130100-002-    | Rozrachunki z odbiorcami |                   | EUR      | -127,11                        | -174,12 | -174,12                      |
| 20856          | CMV-4010 | 21/12/2021 | Działanie | 130100-002-    | Rozrachunki z odbiorcami | Kredyt na konto | USD      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 28/12/2021 | Działanie | 130100-001-    | Rozrachunki z odbiorcami | Media         | USD      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 29/12/2021 | Działanie | 130100-002-    | Rozrachunki z odbiorcami | Usługa           | USD      | 300                            | 300     | 300                          |

Z tych transakcji trzy transakcje są rozliczane podczas rozliczania księgi.

Istnieje faktura na 175 dolarów (175 USD). Ta faktura została zapłacona za pomocą płatności w euro (EUR) i pozyskano rabat gotówkowy.

| Numer arkusza | Załącznik  | Data       | Typ      | Konto finansowe | Nazwa konta        | Opis | Waluta | Kwota w walucie transakcji | Kwota  | Kwota w walucie raportowania |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 5/12/2021  | Działanie | 130100-002-    | Rozrachunki z odbiorcami | Media   | USD      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 20/12/2021 | Działanie | 130100-002-    | Rozrachunki z odbiorcami |             | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Działanie | 130100-002-    | Rozrachunki z odbiorcami |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Wyniki operacji na koncie głównym 130100 zależą od tego, czy funkcja jest włączona przed uruchomieniem zamknięcia na koniec roku. Jeśli ta funkcja jest włączona, wynik zależy również od ustawienia opcji Zachowaj szczegóły podczas zamykania na koniec roku.

### <a name="the-feature-isnt-enabled"></a>Funkcja nie jest włączona
Zamknięcie na koniec roku powoduje utworzenie trzech transakcji salda otwarcia dla konta głównego 130100 2022. Suma transakcji w walucie księgowej wynosi 525 USD.

| Numer arkusza | Załącznik  | Data     | Typ    | Konto finansowe | Nazwa konta        | Opis | Waluta | Kwota w walucie transakcji | Kwota  | Kwota w walucie raportowania |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-002-    | Rozrachunki z odbiorcami |             | USD      | 299.12                         | 299.12  | 299.12                       |
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-001-    | Rozrachunki z odbiorcami |             | USD      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-002-    | Rozrachunki z odbiorcami |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Nawet jeśli transakcja płatności na kwotę -127,11 EUR została rozliczona w księdze głównej, to transakcja ta nadal pojawia się jako saldo początkowe.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>Funkcja jest włączona, a podczas zamknięcia na koniec roku zachowaj szczegóły = Nie

Zamknięcie na koniec roku powoduje utworzenie dwóch transakcji salda otwarcia dla konta głównego 130100 2022. Suma transakcji w walucie księgowej nadal wynosi 525 USD, ale transakcje rozliczane w księdze rachunkowej są wyłączone z bilansu otwarcia. Całkowita kwota na koncie 130100-002- wynosi 125 USD zamiast 299,12 USD, a transakcja za 127,11 EUR/ 174,12 USD jest całkowicie wykluczona.

| Numer arkusza | Załącznik  | Data     | Typ    | Konto finansowe | Nazwa konta        | Opis | Waluta | Kwota w walucie transakcji | Kwota | Kwota w walucie raportowania |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-002-    | Rozrachunki z odbiorcami |             | USD      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-001-    | Rozrachunki z odbiorcami |             | USD      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>Funkcja jest włączona, a podczas zamknięcia na koniec roku zachowaj szczegóły = Tak

Zamknięcie na koniec roku powoduje utworzenie pięciu transakcji salda otwarcia dla konta głównego 130100 2022. Dla każdej z tych pięciu transakcji, które nie zostały rozliczone, tworzona jest osobna transakcja bilansu otwarcia. Suma transakcji w walucie księgowej nadal wynosi 525 USD.

| Numer arkusza | Załącznik  | Data     | Typ    | Konto finansowe | Nazwa konta        | Opis       | Waluta | Kwota w walucie transakcji | Kwota | Kwota w walucie raportowania |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-001-    | Rozrachunki z odbiorcami | Opłata za usługę       | USD      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-001-    | Rozrachunki z odbiorcami | Zwrot            | USD      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-002-    | Rozrachunki z odbiorcami | Kredyt na konto | USD      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-001-    | Rozrachunki z odbiorcami | Media         | USD      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 1.1.2022 | Otwieranie | 130100-002-    | Rozrachunki z odbiorcami | Usługa           | USD      | 300                            | 300    | 300                          |

Gdy szczegóły transakcji są zachowywane, nie ma to wpływu na pierwotne, szczegółowe transakcje. Pozostają one zaksięgowane i nierozliczone w roku podatkowym, który jest zamykany. Kopia tych transakcji jest tworzona dla salda otwarcia. Następujące wartości z oryginalnych transakcji są kopiowane do transakcji bilansu otwarcia.

- Konto księgi (konto główne i wszystkie wymiary finansowe)
- Kwoty w walucie transakcyjnej, księgowej i sprawozdawczej
- Opis
- Warstwa księgowania
- Typ księgowania

   > [!NOTE]
   > Żadne inne transakcje bilansu otwarcia nie mają przypisanego typu księgowania. Dlatego typ księgowania może być użyty do rozróżnienia transakcji otwarcia, które zostały szczegółowo przeniesione.

Niektóre pola z oryginalnych transakcji muszą ulec zmianie w szczegółowych transakcjach bilansu otwarcia. Data transakcji salda otwarcia jest zawsze pierwszym dniem następnego roku obrachunkowego. Numer arkusza musi się zmienić, a numer załącznika zmienia się na wartość wprowadzona w oknie dialogowym zamknięcia na koniec roku.

Informacje z oryginalnych transakcji można znaleźć na stronie **Rozliczenie księgi**. Każda szczegółowa transakcja bilansu otwarcia ma w siatce kolumnę **Data pierwotnej transakcji**. Ta kolumna może pomóc Ci w dopasowaniu transakcji w nowym roku fiskalnym. Można wybrać polecenie **Wyświetl oryginalny załącznik,** aby przejść do pełnego oryginalnego załącznika.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Rozlicz transakcje
W celu rozliczenia transakcji księgi wykonaj następujące czynności.

1. Wybierz kolejno opcje **Księga główna** > **Zadania okresowe** > **Rozliczenia księgi**.
2.  Ustaw filtry w górnej części strony.

    1. Wybierz zakres dat. Alternatywnie wybierz kod zakresu dat, aby automatycznie uzupełnić zakres dat.

       - Zakres dat nie może przekraczać lat podatkowych. Jeśli zakres dat przekracza lata obrachunkowe, po wybraniu opcji **Wyświetl transakcje** nie będą wyświetlane żadne transakcje.
       - Jeśli zakres dat znajduje się w otwartym roku podatkowym, transakcje mogą zostać rozliczone, a rozliczenie może zostać cofnięte. Jeśli zakres dat znajduje się w zamkniętym roku podatkowym lub jeśli zamknięcie roku zostało zakończone, transakcje są pokazywane, ale nie mogą być ani rozliczone, ani nierozliczone. Możesz odznaczyć transakcje tylko w zamkniętym roku fiskalnym. Jeśli zakres dat znajduje się w zamkniętym roku fiskalnym, przyciski **Zaznacz zaznaczone**, **Rozlicz zaznaczone transakcje** oraz **Odwróć zaznaczone transakcje** są niedostępne.

    2. Wybierz konto główne, dla którego chcesz pokazać transakcje. To pole jest wymagane. Wyszukanie pokazuje tylko te konta główne, które są wybrane na stronie **Rozliczenie księgi** dla zakładowego planu kont.
    3. Wybierz warstwę księgowania. Nie możesz rozliczać transakcji, które znajdują się w różnych warstwach księgowania.
    4. Aby pokazać konto główne i wymiary w osobnych kolumnach, wybierz zestaw wymiarów finansowych.

3.  Wybierz opcję **Wyświetl transakcje**, aby wyświetlić wszystkie transakcje zgodne z ustawionymi filtrami. Jeśli zmodyfikujesz którykolwiek filtr lub zestaw wymiarów, należy ponownie kliknąć opcję **Wyświetl transakcje**.
4.  Wybierz wiersze do rozliczenia. Wartość w polu **Wybrana kwota** na górze strony zwiększa się lub zmniejsza, aby odzwierciedlić całkowitą kwotę w wybranych liniach.
5.  Po zakończeniu wybierania transakcji wybierz opcję **Oznacz wybrane**. Dla każdej wybranej transakcji w kolumnie **Oznaczone** pojawi się znacznik wyboru. Ponadto wartość pola **Oznaczona kwota** nad siatką zwiększy się lub zmniejszy o łączną kwotę w oznaczonych wierszach.
6.  Gdy wartość pola **Oznaczona kwota** ma wartość **0** (zero), wybierz opcję **Rozlicz oznaczone transakcje**.

    - Częściowe rozliczenie nie jest dozwolone. Na przykład, nie możesz rozliczyć transakcji debetowej o wartości 100 $ z transakcją kredytową o wartości 90 $. Pozostała transakcja kredytowa o wartości 10 dolarów również musi zostać zaznaczona do uwzględnienia w rozliczeniu.
    - Wprowadź datę rozliczenia. Data nie może być późniejsza niż najpóźniejsza data transakcji zaznaczonych do rozliczenia.

Stan oznaczonych transakcji zostanie zaktualizowany na **Rozliczone**.

> [!IMPORTANT]
> Wszystkie transakcje zaznaczone do rozliczenia dla aktywnej firmy i wybranego konta głównego zostaną rozliczone. Transakcje nie muszą pojawiać się na stronie. Zostaną one rozliczone, nawet jeśli są ukryte z powodu filtru.

Niektóre procesy, takie jak wycofanie transakcji, automatycznie rozliczają transakcje księgi. Na przykład płatność i faktura są rozliczane w rozrachunkach z odbiorcami, a rozliczenie generuje zrealizowaną zysk/stratę. Rozliczenie płatności i faktury nie rozlicza żadnych transakcji finansowych, takich jak transakcje na koncie księgowym rozrachunków z odbiorcami. Jeśli jednak płatność i faktura nie zostaną rozliczone w rozrachunkach z odbiorcami, wycofanie wpisu księgowego zaksięgowanego podczas wycofywania rozrachunku z odbiorcami spowoduje rozliczenie oryginalnych i wywłaszczonych zapisów księgowych w księdze głównej. Gdy jest włączona funkcja **Świadomość między rozliczeniem księgi a zamknięciem na koniec roku**, rozliczenie operacji wycofania nie jest automatycznie księgowane, jeśli data wycofania się znajduje się w innym roku obrachunkowym.

## <a name="use-excel-for-ledger-settlement"></a>Użyj programu Excel do rozliczania księgi

Transakcje pokazywane na stronie **Rozliczenie księgi** można eksportować do programu Excel. W programie Excel można dodatkowo filtrować transakcje, aby określić, które transakcje oznaczyć do rozliczenia.
Obie jednostki rozliczeniowe księgi eksportują transakcje księgi tylko dla konta głównego, które jest wybrane na stronie **Rozliczenie księgi**. Chociaż transakcje dla zamkniętych lat obrachunkowych mogą nadal być oznaczone lub odznaczone za pomocą programu Excel, nie można ich rozliczyć. Ponadto nie można wycofać rozliczonych transakcji dla tego roku obrachunkowego.

## <a name="make-transactions-easier-to-find"></a>Ułatwienie znajdowania transakcji

Strona **Rozliczenia księgi** zawiera funkcje, które ułatwiają zobaczenie transakcji wymaganych do rozliczenia.

•   Użyj filtra **Zaznaczone**, aby filtrować transakcje na podstawie tego, czy zaznaczone jest dla nich pole wyboru **Zaznaczone**.
•   Użyj filtru **Stan**, aby filtrować transakcje na podstawie ich stanu.
•   Wybierz opcję **Sortuj według kwoty bezwzględnej**, aby posortować kwoty według wartości bezwzględnej. W ten sposób możesz grupować obciążenia i uznania, które mają tę samą kwotę.

## <a name="reverse-a-settlement"></a>Wycofywanie rozliczenia

Można cofnąć rozliczenie, która nastąpiło przez pomyłkę.

1.  Wykonaj kroki od 1 do 3 w sekcji [Rozlicz transakcje](#settle-transactions), aby wyświetlić odpowiednie transakcje.
2.  W filtrze **Stan** wybierz wartość **Rozliczone**.
3.  Wybierz linie do odwrócenia.
4.  Wybierz **Odwróć zaznaczone transakcje**. Stan wszystkich transakcji o tym samym identyfikatorze rozliczenia zostanie zaktualizowany na **Nierozliczone**.

> [!IMPORTANT]
> Wszystkie transakcje, które mają ten sam identyfikator rozliczenia, zostaną odwrócone, nawet jeśli nie są oznaczone. Na przykład cztery wiersze zostały oznaczone i rozliczone. Wszystkie cztery wiersze mają ten sam identyfikator rozliczenia. Jeśli oznaczysz jeden z czterech wierszy i wybierzesz opcję **Odwróć zaznaczone transakcje**, wszystkie cztery wiersze zostaną wycofane.






