---
title: Funkcja relacji między rozliczeniem księgi po zamknięciu roku z użyciem strony zapytań
description: W tym artykule wyjaśniono, jak korzystać z funkcji Świadomość między rozliczeniami księgi głównej, używając nowej strony zapytania po zamknięciu roku przez księgę główną.
author: kweekley
ms.date: 12/15/2022
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
ms.openlocfilehash: 921d2a17409ae10cd9c22eeca11557ba1248b9bc
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853154"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close-using-the-inquiry-page"></a>Funkcja relacji między rozliczeniem księgi po zamknięciu roku z użyciem strony zapytań

Jedną z głównych zmian w funkcji **Uwaga między rozliczeniem księgi a zamknięciem roku** (funkcja **Świadomość**) jest to, że rozliczenie księgi nie może być dokonywane w różnych latach podatkowych. To międzyroczne ograniczenie dotyczy tylko rozliczenia księgi, a nie rozliczenia należności czy zobowiązań.

Przed włączeniem funkcji **Świadomości** rok podatkowy, który będzie podlegał zamknięciu roku, nie może mieć żadnych transakcji w księdze rachunkowej, które są rozliczane w innych latach podatkowych. W szczególności wszelkie transakcje, które zostały zaksięgowane w roku podatkowym, dla którego przeprowadzasz zamknięcie roku, muszą być nierozliczone z transakcjami, które zostały zaksięgowane w innym roku podatkowym. Transakcje te mogą być następnie rozliczone z transakcjami w tym samym roku podatkowym.

W tym artykule opisano kroki wymagane do zidentyfikowania, nierozliczenia i ponownego rozliczenia transakcji w księdze, które są rozliczane w ciągu lat. W podanym przykładzie rok podatkowy 2022 został zamknięty. Skupiamy się na przygotowaniu transakcji rozliczeniowych księgi głównej przed zamknięciem roku 2023.

Od wersji 10.0.29 Microsoft Dynamics 365 Finance można identyfikować, rozłączać i ponownie rozliczać transakcje księgi głównej za pomocą nowej strony zapytania. Jeśli nie masz jeszcze wersji programu Microsoft Dynamics 365 Finance 10.0.29 lub nowszej, kroki związane z identyfikacją, rozrachunkiem i ponownym rozrachunkiem transakcji księgi głównej znajdziesz w poniższych artykułach:

- [Świadomość funkcji rozliczenia między księgami przed zamknięciem roku](ledger-settle-yec.md)
- [Świadomość funkcji rozliczenia między księgami po zamknięciu roku](ledger-settle-yec-after.md)

Aby uzyskać więcej informacji o nowym oknie zapytania, zobacz informacje [Rozliczenie księgi](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Przykład konfiguracji

Poniższa ilustracja przedstawia transakcje, które zostały zaksięgowane na koncie głównym 110200. Transakcje w kolorze zielonym zostały rozliczone w tym samym roku podatkowym i nie muszą być zmieniane. Transakcje zaznaczone na czerwono zostały rozliczone w księgach rachunkowych, ale mają daty transakcji w różnych latach podatkowych. Transakcje te muszą zostać zidentyfikowane, a rozliczenie księgi może wymagać cofnięcia.

![Zaksięgowanie transakcji w księdze.](./media/excel.png)

## <a name="example"></a>Przykład

Wykonaj poniższe kroki, jeśli Twoja organizacja chce skorzystać z funkcji **Świadomości** po zamknięciu roku podatkowego 2022.

> [!NOTE]
> Zamknięcie roku 2022 i wcześniejszych lat podatkowych musi być powtórzone tylko wtedy, gdy nowe transakcje zostaną zaksięgowane w roku podatkowym 2022 lub wcześniejszym. Gdy wykonasz poniższą procedurę, żadne nowe transakcje nie zostaną zaksięgowane w 2022 roku. Dzięki temu nie trzeba ponownie przeprowadzać zamknięcia roku.
>
> Transakcje w księdze, które są rozliczane w różnych latach podatkowych, mogą pozostać rozliczone w księdze, jeśli nie są rozliczane z transakcją, która została zaksięgowana w roku 2022 lub później. Na przykład, jeśli rozliczyłeś transakcje w latach 2019 i 2020, mogą one pozostać rozliczone.

1. Zakończ zamknięcie na koniec roku 2022 bez włączonej funkcji **Świadomość**.
2. Zidentyfikuj wszystkie transakcje, które zostały zaksięgowane w innych latach podatkowych, ale rozliczone z transakcjami, które zostały zaksięgowane w 2023 roku (następny rok podatkowy, który zostanie zamknięty).

    > [!NOTE]
    > Transakcje z 2021 roku, które zostały rozliczone z transakcjami z 2022 roku, nie są istotne, ponieważ rok 2022 został już zamknięty. Te transakcje mogą pozostać rozliczone.

    1. Na stronie **Rozliczenia księgowe** wybierz **Przeglądaj rozliczenia międzyroczne**.
    2. Wybierz rok fiskalny 2023, następny rok fiskalny, dla którego chcesz przeprowadzić proces zamknięcia roku.
    3. Wybierz wartość w polu **Zestaw wymiarów finansowych**, aby wyświetlić wymiary finansowe, które chcesz zobaczyć dla danego konta księgowego. Konto główne jest zawsze pokazywane, nawet jeśli wybrany zestaw wymiarów nie zawiera konta głównego.
    4. Wybierz **Pokaż transakcje**.

    Na stronie zapytania pojawią się wszystkie transakcje z innych lat podatkowych, które zostały rozliczone z transakcjami zaksięgowanymi w 2023 roku.

    ![2023 rozliczenia międzyroczne.](./media/2023-cross-settlement.png)

3. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w siatce, a następnie wybierz polecenie **Eksportuj wszystkie wiersze**. W tych wierszach znajdują się wszystkie transakcje, które muszą być nierozliczone z transakcji w 2022 roku, aby można było przeprowadzić zamknięcie roku następnego (2023). Chcesz mieć zapis tych transakcji.

    Po wyeksportowaniu wszystkich szczegółowych transakcji z roku 2022 do programu Excel, możesz je rozliczyć za pomocą strony zapytania.

4. Zaznacz wszystkie rekordy w siatce, a następnie wybierz **Unieważnij zaznaczone rekordy**. Wszystkie wybrane transakcje w siatce zostaną nierozliczone.

    Pojawiają się dwa komunikaty ostrzegawcze, aby upewnić się, że szczegóły transakcji zostały wyeksportowane do programu Excel, zanim zostaną nierozliczone. Jeśli przypadkowo rozłączysz transakcje księgi przed wysłaniem szczegółów do Excela, nie ma możliwości cofnięcia rozłączeń.

    ![Nierozliczone rozliczenia między latami.](./media/revert-settlement.png)

5. Korzystając z danych Excela, znajdź łączną kwotę transakcji z 2022 roku, które zostały rozliczone z transakcjami z 2023 roku. W tym przykładzie transakcje na rok 2023 wynoszą 700 dolarów.
6. Zamieść ogólny dziennik korygujący, aby podzielić bilans otwarcia na rok 2022 na dwie kwoty: część, która została rozliczona z transakcją na rok podatkowy 2022 oraz część, która nie została jeszcze rozliczona na rok 2023.

    - **Część bilansu otwarcia, która została rozliczona w poprzednim roku:** Pierwsza kwota wynosi 700 dolarów i jest oparta na sumach, które zostały rozliczone w latach 2021 i 2022.
    - **Część bilansu otwarcia, która nie została rozliczona w poprzednim roku:** Druga kwota to różnica między bilansem otwarcia a rozliczoną kwotą 700 dolarów. Pozostała kwota to 1700 $ - 700 $ = 1000 $.

    W ten sposób możesz rozliczyć transakcje z 2023 roku z kwoty 700 dolarów, która została pierwotnie rozliczona z transakcji z 2022 roku. Ten krok jest wymagany, ponieważ rozliczenie w księdze głównej nie pozwala na częściowe rozliczenie.

    1. Przejdź do dziennika ogólnego i wpisz korektę. Twoja organizacja będzie musiała zdecydować, jaką datę transakcji zastosować w zależności od otwartych okresów w 2023 r.
    2. Być może będziesz musiał tymczasowo wyłączyć parametr **Nie zezwalaj na ręczne wprowadzanie** na stronie **Konto główne**. To dostosowanie nie zostanie uwzględnione, jeśli konto główne nie pozwala na ręczne wprowadzanie danych.

    ![Księgowanie dziennika ogólnego korygującego.](./media/no-manual4.png)

7. Możesz teraz ponownie rozliczyć nierozliczone transakcje. Wróć do strony **Rozliczenia z księgą główną** i ogranicz zakres dat do 1 stycznia - 31 grudnia 2023 roku. Następnie użyj szczegółowych transakcji, które wyeksportowałeś do Excela, aby znaleźć konkretne transakcje, które muszą zostać ponownie rozliczone. Poniższa ilustracja przedstawia nierozliczone transakcje, które obecnie istnieją.

    ![Nierozliczone transakcje 2023 .](./media/2023-unsettled5.png)

    - Bilans otwarcia w wysokości 1700 USD może zostać rozliczony z korektą o wartości – 1700 USD.
    - Szczegółowe transakcje, które nie zostały rozliczone na kwotę -700 $, mogą zostać rozliczone z korektą na kwotę 700 $.

8. Włącz funkcję **Świadomość**. Jesteś teraz gotowy do przeprowadzenia zamknięcia roku.

    - Zanim przeprowadzisz zamknięcie roku 2023, rozważ wybranie opcji **Zachowaj szczegóły** dla wszystkich kont bilansowych w ustawieniach rozliczenia księgi. Aby uzyskać więcej informacji, zobacz temat [Relacja między rozliczeniem księgi a zamknięciem roku](awareness-between-ledger-settlement-year-end-close.md).
    - Gdy rozpoczniesz zamykanie roku 2023, jeśli nadal będziesz miał do czynienia z transakcjami, które zostały rozliczone w innych latach podatkowych, proces zamykania roku natychmiast Cię o tym powiadomi. Taka sytuacja może mieć miejsce, jeśli użytkownicy rozliczali transakcje w różnych latach podatkowych przed włączeniem funkcji **Świadomości**.
    - Jeśli transakcje z lat 2022 i 2023 są nadal rozliczone, będziesz musiał ponownie wyłączyć funkcję **Świadomości**, a następnie powtórzyć poprzednie kroki, aby wyłączyć te transakcje. Takie podejście jest konieczne, ponieważ rok 2022 jest zamknięty, a w zamkniętym roku podatkowym nie można rozliczać transakcji.

Po pomyślnym przeprowadzeniu zamknięcia roku 2022 możesz pozostawić włączoną funkcję **Świadomości**.
