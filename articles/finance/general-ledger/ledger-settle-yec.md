---
title: Świadomość funkcji rozliczenia między księgami przed zamknięciem roku
description: W tym artykule wyjaśniono, jak używać funkcji Świadomości między księgami przed przeprowadzeniem procesu zamknięcia roku przez księgę główną.
author: kweekley
ms.date: 12/02/2022
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
ms.openlocfilehash: c79b6f50296560e1534be0621bb2aa8eaa2c1dc8
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832169"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close"></a>Świadomość funkcji rozliczenia między księgami przed zamknięciem roku

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-before-year-end-close"></a>Przygotowanie do rozliczenia księgi głównej Świadomość przed zamknięciem roku

Jedną z głównych zmian w funkcji **Uwaga między rozliczeniem księgi a zamknięciem roku** (funkcja **Świadomość**) jest to, że rozliczenie księgi nie może być dokonywane w różnych latach podatkowych. To międzyroczne ograniczenie dotyczy tylko rozliczenia księgi, a nie rozliczenia należności czy zobowiązań.

Przed włączeniem funkcji **Świadomości** rok podatkowy, który będzie podlegał zamknięciu roku, nie może mieć żadnych transakcji w księdze rachunkowej, które są rozliczane w innych latach podatkowych. W szczególności wszelkie transakcje, które zostały zaksięgowane w roku podatkowym, dla którego przeprowadzasz zamknięcie roku, muszą być nierozliczone z transakcjami, które zostały zaksięgowane w innym roku podatkowym. Transakcje te mogą być następnie rozliczone z transakcjami w tym samym roku podatkowym.

W tym artykule opisano kroki wymagane do zidentyfikowania, nierozliczenia i ponownego rozliczenia transakcji w księdze, które są rozliczane w ciągu roku podatkowego. W podanym przykładzie zamknięto rok podatkowy 2021, a Ty przygotowujesz się do zamknięcia roku podatkowego 2022.

## <a name="example-setup"></a>Przykład konfiguracji

Poniższa ilustracja przedstawia transakcje, które zostały zaksięgowane na koncie głównym 110190. Transakcje księgi w kolorze zielonym są rozliczane w tym samym roku podatkowym i nie muszą być zmieniane. Transakcje zaznaczone na czerwono zostały rozliczone w księgach rachunkowych, ale mają daty transakcji w różnych latach podatkowych. Transakcje te muszą zostać zidentyfikowane, a rozliczenie księgi może wymagać cofnięcia.

![Transakcje księgi.](./media/YEC1.png)

## <a name="example"></a>Przykład

Wykonaj poniższe kroki, jeśli Twoja organizacja chce skorzystać z funkcji **Świadomości** przed zamknięciem roku podatkowego 2022.

> [!NOTE]
> Zamknięcie roku 2021 i wcześniejszych lat podatkowych musi być powtórzone tylko wtedy, gdy nowe transakcje zostaną zaksięgowane w roku podatkowym 2021 lub wcześniejszym. Gdy wykonasz poniższą procedurę, żadne nowe transakcje nie zostaną zaksięgowane w 2021 roku. Dzięki temu nie trzeba ponownie przeprowadzać zamknięcia roku.
>
> Transakcje w księdze, które są rozliczane w różnych latach podatkowych, mogą pozostać rozliczone w księdze, jeśli nie są rozliczane z transakcją, która została zaksięgowana w roku 2022 lub później. Na przykład, jeśli rozliczyłeś transakcje w latach 2019 i 2020, mogą one pozostać rozliczone.

1. Opcjonalnie: tymczasowo włącz funkcję **Świadomość**.

    - Jeśli zdecydujesz się włączyć tę funkcję, będziesz musiał ją wyłączyć w kolejnych krokach. Włączenie tej funkcji już teraz zapobiega tymczasowemu rozliczaniu przez użytkowników transakcji księgowych, które zostały zaksięgowane w różnych latach podatkowych.
    - Jeśli nie zdecydujesz się na włączenie tej funkcji, zalecamy, abyś poprosił swój zespół o nierozliczanie transakcji w latach podatkowych. Jeśli rozliczenie międzyroczne zostanie wykonane po ukończeniu poniższych kroków, trzeba powtórzyć kroki w celu zidentyfikowania i rozliczenia transakcji księgi.

2. Na stronie **Rozliczenie księgi** określ sumę wszystkich transakcji rozliczanych w latach obrachunkowych 2021 i 2022.

    1. Określ zakres dat dla całego roku podatkowego 2021. Na przykład wprowadź okres od 1 stycznia 2021 roku do 31 grudnia 2021 roku, jeśli jako rok podatkowy używasz roku kalendarzowego.

        Jeśli funkcja **Świadomość** jest włączona, wyświetlane jest ostrzeżenie, że transakcji nie można rozliczyć ani nierozliczonych dla zamkniętego roku obrachunkowego. Ostrzeżenie nie jest istotne, ponieważ w tym kroku nie jest już rozliczeniu ani co najmniej rozliczeniu.

    2. W polu **Stan** wybierz opcję **Rozliczono**.
    3. Filtrowanie na jednym koncie księgi w tym samym czasie.

        - Te czynności będziesz musiał powtórzyć dla każdego konta księgi, które jest rozliczane.
        - Jeśli inne konta księgi nie są już ustawione do rozliczenia księgi, może być konieczne tymczasowe dodanie ich z powrotem do konfiguracji rozliczenia księgi. Następnie wykonaj te kroki, jeśli na tych kontach księgi znajdują się transakcje z 2022 roku, które są rozliczane z transakcjami z innego roku podatkowego.

    4. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kolumnę **Stan**, a następnie wybierz opcję grupowania według tej kolumny.
    5. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kolumnę **Wartość w walucie transakcji**, a następnie wybierz opcję sumowania tej kolumny.

        - Jeśli rozliczyłeś transakcje tylko w 2021 roku, suma będzie wynosiła 0 (zero).
        - Jeśli masz transakcje, które zostały rozliczone w różnych latach podatkowych, suma nie będzie równa 0 (zero).

        Na poniższej ilustracji saldo wynosi 525,00 dolarów. Saldo to jest sumą transakcji, które zostały rozliczone z transakcjami w innym roku podatkowym. Twoja suma może zawierać transakcje rozliczone w latach 2021–2022 oraz transakcje rozliczone w latach 2022–2023.

        ![Transakcje księgi w latach 2021–2022.](./media/YEC2.png)

    6. Określ, które transakcje rozliczono w okresie od 2020 do 2021, filtrując wartość **Daty rozliczenia**. Określ filtr zakresu dat od 1 stycznia 2021 do 31 grudnia 2021. Nie wykazano żadnych transakcji, ponieważ żadne transakcje z roku 2020 nie zostały rozliczone z transakcjami, które zostały zaksięgowane w roku 2021.
    7. Określ, które transakcje rozliczono w okresie od 2021 do 2022, filtrując wartość **Daty rozliczenia**. Określ filtr zakresu dat od 1 stycznia 2022 do 31 grudnia 2022. Transakcje są wyświetlane ponownie, a ich suma wynosi 525,00 dolarów, ponieważ wszystkie transakcje zostały rozliczone w latach 2021–2022.

3. Na stronie **Rozliczenie księgi** określ sumę wszystkich transakcji rozliczanych w latach obrachunkowych 2021 i 2022.

    1. Określ zakres dat dla całego roku podatkowego 2022. Na przykład określ okres od 1 stycznia 2022 roku do 31 grudnia 2022 roku, jeśli jako rok podatkowy używasz roku kalendarzowego.
    2. W polu **Stan** wybierz opcję **Rozliczono**.
    3. Filtrowanie na jednym koncie księgi w tym samym czasie.
    4. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kolumnę **Stan**, a następnie wybierz opcję grupowania według tej kolumny.
    5. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kolumnę **Wartość w walucie transakcji**, a następnie wybierz opcję sumowania tej kolumny.

        ![Sumy transakcji w księdze.](./media/YEC3.png)

    6. Dodaj dodatkowy filtr do wartości **Daty rozliczenia**. Określ filtr zakresu dat od 1 stycznia 2022 do 31 grudnia 2022. Widoczna jest ta sama suma 525,00 dolarów. Wynik ten potwierdza, że całkowita kwota transakcji rozliczanych w latach 2021 i 2022 wynosi 525,00 dolarów.

        ![Transakcje księgi dla dat rozliczenia w 2022 i 2023 roku.](./media/YEC4.png)

    7. Zmień dodatkowy filtr do wartości **Daty rozliczenia**. Określ filtr zakresu dat od 1 stycznia 2023 do 31 grudnia 2023. Pojawia się nowa suma 700 $. Suma ta to łączna kwota transakcji, które zostały rozliczone w latach 2022 i 2023.
 
4. Powtórz krok 3 dla roku obrachunkowego 2023. Suma powinna odpowiadać kwocie 700 dolarów z roku 2022, ponieważ żadna transakcja z roku 2023 nie została rozliczona z transakcjami z roku 2024.
5. Jeśli w kroku 1 włączono funkcję **Świadomość**, wyłącz ją przed przejściem do kroku 6. W kolejnych krokach odwrócisz rozliczenie księgi, która przekroczyła rok fiskalny. Jeśli funkcja **Świadomość** jest włączona, nie można wycofać rozliczenia księgi dla roku obrachunkowego 2021. Dlatego przed kontynuacją musisz wyłączyć tę funkcję.
6. Po wyłączeniu funkcji **Świadomość** użyj tych samych filtrów na stronie **Rozliczenie księgi**, aby wycofać rozliczenie księgi dla transakcji szczegółowych.

    1. Wróć na stronę **Rozliczenie księgi** i odfiltruj daty transakcji dla 2021 roku. Dodaj dodatkowy filtr do wartości **Daty rozliczenia**. Określ filtr zakresu dat od 1 stycznia 2022 do 31 grudnia 2022. Następnie znajdź szczegółowe transakcje, które składają się na sumę 525 dolarów. Filtrowanie tych informacji może nie być łatwe. Być może będziesz musiał wysłać dane do programu Microsoft Excel, aby je ocenić.
    2. Po wybraniu listy transakcji wybierz transakcje księgi na stronie **Rozliczenie księgi** i wybierz opcję **Zaznacz wybór**. Nie musisz widzieć obu stron księgi rozliczonych transakcji. Jeśli zaznaczysz debet lub kredyt, wszystko, co ma taką samą wartość **Identyfikator rozliczenia**, zostanie odwrócone, nawet jeśli **Zaznaczona kwota** nie jest **0** (zero).
    3. Wybierz opcję **Wycofaj zaznaczone transakcje**, aby cofnąć rozliczenie.

    ![Wycofaj oznaczone transakcje.](./media/YEC5.png)

7. Powtórz krok 6, aby odwrócić rozliczenie dla transakcji, które zostały rozliczone w latach 2022 i 2023.

    ![Transakcje księgi odwróconej.](./media/YEC6.png)

8. Zamieść ogólny dziennik korygujący, aby podzielić bilans otwarcia na rok 2022 na dwie kwoty: część rozliczaną z transakcją z roku podatkowego 2021 oraz część nierozliczaną w roku 2022.

    - **Część bilansu otwarcia, która została rozliczona w poprzednim roku:** Pierwsza kwota wynosi 525 dolarów i jest oparta na sumach, które zostały rozliczone w latach 2021 i 2022.
    - **Część bilansu otwarcia, która nie została rozliczona w poprzednim roku:** Druga kwota to różnica między bilansem otwarcia a rozliczoną kwotą 525 dolarów. Pozostała kwota to 1025 $ - 525 $ = 500 $.

    W ten sposób możesz rozliczyć transakcje z 2022 roku z kwoty 525 dolarów, która została pierwotnie rozliczona z transakcji z 2021 roku. Ten krok jest wymagany, ponieważ rozliczenie w księdze głównej nie pozwala na częściowe rozliczenie.

    1. Przejdź do dziennika ogólnego i wpisz korektę. Twoja organizacja będzie musiała zdecydować, jaką datę transakcji zastosować w zależności od otwartych okresów. Transakcje te mogły zostać rozliczone z datą rozliczenia przypadającą na styczeń lub luty 2022 roku, ale może się okazać, że korekta zostanie zaksięgowana w grudniu, jeśli jest to jedyny otwarty okres.
    2. Być może będziesz musiał tymczasowo wyłączyć parametr **Nie zezwalaj na ręczne wprowadzanie** na stronie **Konto główne**. To dostosowanie nie zostanie uwzględnione, jeśli konto główne nie pozwala na ręczne wprowadzanie danych.

    ![Nie można księgować korekt.](./media/YEC7.png)

9. Możesz teraz ponownie rozliczyć nierozliczone transakcje. Wróć do strony **Rozliczenie księgi głównej** i ogranicz zakres dat do 1 stycznia 2022 r. - 31 grudnia 2022 roku. Poniższa ilustracja przedstawia nierozliczone transakcje, które obecnie istnieją.

    ![Nierozliczone transakcje](./media/YEC8.png)

    - Bilans otwarcia w wysokości 1 025 USD może zostać rozliczony z korektą o wartości – 1 025 USD.
    - Szczegółowe transakcje, które nie zostały rozliczone na kwoty -400 $, -50 $ i -75 $, mogą zostać rozliczone z korektą o 525,00 $.

    ![Szczegóły transakcji.](./media/YEC9.png)

10. Włącz funkcję **Świadomość**. Jesteś teraz gotowy do przeprowadzenia zamknięcia roku.

    - Zanim przeprowadzisz zamknięcie roku, rozważ wybranie opcji **Zachowaj szczegóły** dla wszystkich kont bilansowych w ustawieniach rozliczenia księgi. Aby uzyskać więcej informacji o zaletach wykonania tego kroku, zobacz dokument Świadomość.
    - Gdy rozpoczniesz zamykanie roku 2022, jeśli nadal będziesz miał do czynienia z transakcjami, które zostaną rozliczone w innych latach podatkowych, proces zamykania roku natychmiast Cię o tym powiadomi.
    - Jeśli transakcje z lat 2021 i 2022 są nadal rozliczone, będziesz musiał ponownie wyłączyć funkcję **Świadomości**, a następnie powtórzyć poprzednie kroki, aby wyłączyć te transakcje. Takie podejście jest konieczne, ponieważ rok 2021 jest zamknięty, a w zamkniętym roku podatkowym nie można rozliczać transakcji.
    - Jeśli transakcje 2022 i 2023 są nadal rozliczane, **nie musisz** wyłączać funkcji **Świadomości**. Ponieważ ani rok 2022, ani 2023 nie są zamknięte, możesz skorzystać z poprzednich kroków, aby rozliczyć te transakcje.

Po pomyślnym przeprowadzeniu zamknięcia roku 2022 możesz pozostawić włączoną funkcję **Świadomości**.
