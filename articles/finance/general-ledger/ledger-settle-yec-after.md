---
title: Świadomość funkcji rozliczenia między księgami po zamknięciu roku
description: W tym artykule wyjaśniono, jak używać funkcji Świadomości między księgami po przeprowadzeniu procesu zamknięcia roku przez księgę główną.
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
ms.openlocfilehash: 7efa9d652d74bd836f51b5b1c5f6bfaf8934ea40
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832172"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close"></a>Świadomość funkcji rozliczenia między księgami po zamknięciu roku

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-after-year-end-close"></a>Przygotowanie do rozliczenia księgi głównej Świadomość po zamknięciu roku

Jedną z głównych zmian w funkcji **Uwaga między rozliczeniem księgi a zamknięciem roku** (funkcja **Świadomość**) jest to, że rozliczenie księgi nie może być dokonywane w różnych latach podatkowych. To międzyroczne ograniczenie dotyczy tylko rozliczenia księgi, a nie rozliczenia należności czy zobowiązań.

Przed włączeniem funkcji **Świadomości** rok podatkowy, który będzie podlegał zamknięciu roku, nie może mieć żadnych transakcji w księdze rachunkowej, które są rozliczane w innych latach podatkowych. W szczególności wszelkie transakcje, które zostały zaksięgowane w roku podatkowym, dla którego przeprowadzasz zamknięcie roku, muszą być nierozliczone z transakcjami, które zostały zaksięgowane w innym roku podatkowym. Transakcje te mogą być następnie rozliczone z transakcjami w tym samym roku podatkowym.

W tym artykule opisano kroki wymagane do zidentyfikowania, nierozliczenia i ponownego rozliczenia transakcji w księdze, które są rozliczane w ciągu roku podatkowego. W podanym przykładzie rok podatkowy 2022 został zamknięty. Skupiamy się na przygotowaniu transakcji rozliczeniowych księgi głównej przed zamknięciem roku 2023.

## <a name="example-setup"></a>Przykład konfiguracji

Poniższa ilustracja przedstawia transakcje, które zostały zaksięgowane na koncie głównym 110190. Transakcje księgi w kolorze zielonym są rozliczane w tym samym roku podatkowym i nie muszą być zmieniane. Transakcje zaznaczone na czerwono zostały rozliczone w księgach rachunkowych, ale mają daty transakcji w różnych latach podatkowych. Transakcje te muszą zostać zidentyfikowane, a rozliczenie księgi może wymagać cofnięcia.

![Transakcje księgi.](./media/afterYEC1.png)

## <a name="example"></a>Przykład

Wykonaj poniższe kroki, jeśli Twoja organizacja chce skorzystać z funkcji **Świadomości** po zamknięciu roku podatkowego 2022.

> [!NOTE]
> Zamknięcie roku 2022 i wcześniejszych lat podatkowych musi być powtórzone tylko wtedy, gdy nowe transakcje zostaną zaksięgowane w roku podatkowym 2022 lub wcześniejszym. Gdy wykonasz poniższą procedurę, żadne nowe transakcje nie zostaną zaksięgowane w 2022 roku. Dzięki temu nie trzeba ponownie przeprowadzać zamknięcia roku.
>
> Transakcje w księdze, które są rozliczane w różnych latach podatkowych, mogą pozostać rozliczone w księdze, jeśli nie są rozliczane z transakcją, która została zaksięgowana w roku 2023 lub później. Na przykład, jeśli rozliczyłeś transakcje w latach 2019 i 2020, mogą one pozostać rozliczone.

1. Zakończ zamknięcie na koniec roku 2022 bez włączonej funkcji **Świadomość**.
2. Opcjonalnie: po zakończeniu zamknięcia roku 2022 włącz funkcję **Świadomość** . Zamknięcie na koniec roku jest traktowane jako ukończone, gdy wszystkie korekty są księgowane i proces zamknięcia na koniec roku nie zostanie uruchomiony ponownie.

    > [!IMPORTANT]
    > Funkcja **Świadomość** nie może być włączona, jeśli zamknięcie na koniec roku 2022 zostanie uruchomione ponownie. Włączenie tej funkcji już teraz zapobiega rozliczaniu przez użytkowników transakcji księgowych, które zostały zaksięgowane w różnych latach podatkowych.

    Jeśli zamknięcie na koniec roku nie zostało zakończone, nadal można wykonać następne kroki bez włączania funkcji **Świadomość** . Zgodnie z zaznaczoną funkcją zostanie włączyć tę funkcję w późniejszym kroku.

3. Na stronie **Rozliczenie księgi** określ sumę wszystkich transakcji rozliczanych w latach obrachunkowych 2022 i 2023. Zauważ, że transakcje z 2021 roku, które są rozliczane z transakcjami z 2022 roku, nie są istotne, ponieważ 2022 rok został już zamknięty. Te transakcje mogą pozostać rozliczone.

    1. Określ zakres dat dla całego roku podatkowego 2022. Na przykład określ okres od 1 stycznia 2022 roku do 31 grudnia 2022 roku, jeśli jako rok podatkowy używasz roku kalendarzowego.
    2. W polu **Stan** wybierz opcję **Rozliczono**.
    3. Filtrowanie na jednym koncie księgi w tym samym czasie.

        - Te czynności będziesz musiał powtórzyć dla każdego konta księgi, które jest rozliczane.
        - Jeśli inne konta księgi nie są już ustawione do rozliczenia księgi, może być konieczne tymczasowe dodanie ich z powrotem do konfiguracji rozliczenia księgi. Następnie wykonaj te kroki, jeśli na tych kontach księgi głównej znajdują się transakcje z 2023 roku, które są rozliczane z transakcjami z 2022 roku lub wcześniejszymi.

    4. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kolumnę **Stan**, a następnie wybierz opcję grupowania według tej kolumny.
    5. Zaznacz i przytrzymaj (lub kliknij prawym przyciskiem myszy) kolumnę **Wartość w walucie transakcji**, a następnie wybierz opcję sumowania tej kolumny.

        - Jeśli rozliczyłeś transakcje tylko w 2022 roku, suma będzie wynosiła 0 (zero).
        - Jeśli masz transakcje, które zostały rozliczone w różnych latach podatkowych, suma nie będzie równa 0 (zero).

    6. Określ, które transakcje rozliczono w okresie od 2022 do 2023, filtrując wartość **Daty rozliczenia**. Jeśli wyfiltrujesz datę rozliczenia od 1 stycznia 2023 roku do 31 grudnia 2023 roku, otrzymasz 700 dolarów, czyli sumę transakcji, które zostały rozliczone w księgach rachunkowych w latach 2022 i 2023.

    ![Suma 2022 transakcji księgi.](./media/afterYEC2.png)

4. Powtórz krok 3 dla roku obrachunkowego 2023. Suma powinna odpowiadać kwocie 700 dolarów z roku 2022, ponieważ żadna transakcja z roku 2023 nie została rozliczona z transakcjami z roku 2024.

    ![Suma 2023 transakcji księgi.](./media/afterYEC3.png)

5. Jeśli w kroku 2 włączono funkcję **Świadomość**, wyłącz ją przed przejściem do kroku 6. W kolejnych krokach odwrócisz rozliczenie księgi, która przekroczyła rok fiskalny. Jeśli funkcja **Świadomość** jest włączona, nie można wycofać rozliczenia księgi dla roku obrachunkowego 2022. Dlatego przed kontynuacją musisz wyłączyć tę funkcję.
6. Po wyłączeniu funkcji **Świadomość** użyj tych samych filtrów na stronie **Rozliczenie księgi**, aby wycofać rozliczenie księgi dla transakcji szczegółowych.

    1. Wróć na stronę **Rozliczenie księgi** i odfiltruj daty transakcji dla 2023 roku. Następnie znajdź szczegółowe transakcje, które składają się na sumę 700 dolarów. Filtrowanie tych informacji może nie być łatwe. Być może będziesz musiał wysłać dane do programu Microsoft Excel, aby je ocenić.
    2. Po wybraniu listy transakcji wybierz transakcje księgi na stronie **Rozliczenie księgi** i wybierz opcję **Zaznacz wybór**. Nie musisz widzieć obu stron księgi rozliczonych transakcji. Jeśli zaznaczysz debet lub kredyt, wszystko, co ma taką samą wartość **Identyfikator rozliczenia**, zostanie odwrócone, nawet jeśli **Zaznaczona kwota** nie jest **0** (zero).
    3. Wybierz opcję **Wycofaj zaznaczone transakcje**, aby cofnąć rozliczenie.

    ![Wycofaj transakcje.](./media/afterYEC4.png)

7. Zamieść ogólny dziennik korygujący, aby podzielić bilans otwarcia na rok 2023 na dwie kwoty: część rozliczaną z transakcją z roku podatkowego 2022 oraz część nierozliczaną w roku 2023.

    - **Część bilansu otwarcia, która została rozliczona w poprzednim roku:** Pierwsza kwota wynosi 700 dolarów i jest oparta na sumach, które zostaną rozliczone w latach 2022 i 2023.
    - **Część bilansu otwarcia, która nie została rozliczona w poprzednim roku:** Druga kwota to różnica między bilansem otwarcia a pierwszą kwotą 525 dolarów. Pozostała kwota to 1700 $ - 700 $ = 1000 $.

    W ten sposób możesz rozliczyć transakcje z 2023 roku z kwoty 700 dolarów, która została pierwotnie rozliczona z transakcji z 2022 roku. Ten krok jest wymagany, ponieważ rozliczenie w księdze głównej nie pozwala na częściowe rozliczenie.

    1. Przejdź do dziennika ogólnego i wpisz korektę. Twoja organizacja będzie musiała zdecydować, jaką datę transakcji zastosować w zależności od otwartych okresów w 2023 r.
    2. Być może będziesz musiał tymczasowo wyłączyć parametr **Nie zezwalaj na ręczne wprowadzanie** na stronie **Konto główne**. To dostosowanie nie zostanie uwzględnione, jeśli konto główne nie pozwala na ręczne wprowadzanie danych.

    ![Nie można księgować korekt.](./media/afterYEC5.png)

8. Możesz teraz ponownie rozliczyć nierozliczone transakcje. Wróć do strony **Rozliczenie księgi głównej** i ogranicz zakres dat do 1 stycznia 2022 r. - 31 grudnia 2022 roku. Poniższa ilustracja przedstawia nierozliczone transakcje, które obecnie istnieją.

    ![Nierozliczone transakcje](./media/afterYEC6.png)

    - Bilans otwarcia w wysokości 1700 USD może zostać rozliczony z korektą o wartości – 1700 USD.
    - Szczegółowe transakcje, które nie zostały rozliczone na kwotę -700 $, mogą zostać rozliczone z korektą na kwotę 700 $.

9. Włącz ponownie funkcję **Świadomość**.
10. Po tym, jak funkcja **Świadomość** jest włączona, rozliczenia w księgach rachunkowych nie mogą być dokonywane w różnych latach podatkowych. Być może będziesz musiał dalej dzielić pozostałe saldo 1000 dolarów na mniejsze kwoty, zanim będziesz mógł rozliczyć się z nowych transakcji w 2023 roku. Niektórzy klienci decydują się na zaksięgowanie tej informacji w kroku 8, w którym 1000 $ jest dalej dzielone na nierozliczone transakcje z 2022 roku. To podejście w zasadzie naśladuje działania funkcji **Świadomość** tylko w bieżącym roku. Następny rok zostanie automatycznie wykonane przy użyciu ustawienia **Zachowaj szczegóły** w konfiguracji rozliczania księgi.
