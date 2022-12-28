---
title: Funkcja relacji między rozliczeniem księgi przed zamknięciem roku z użyciem strony zapytań
description: W tym artykule wyjaśniono, jak korzystać z funkcji Świadomość między rozliczeniami księgi głównej, używając nowej strony zapytania przed zamknięciem roku przez księgę główną.
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
ms.openlocfilehash: b138d2d5e88ff7f2ca2240cf256a4938f55a5606
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853161"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close-using-the-inquiry-page"></a>Funkcja relacji między rozliczeniem księgi przed zamknięciem roku z użyciem strony zapytań

Jedną z głównych zmian w funkcji **Uwaga między rozliczeniem księgi a zamknięciem roku** (funkcja **Świadomość**) jest to, że rozliczenie księgi nie może być dokonywane w różnych latach podatkowych. To międzyroczne ograniczenie dotyczy tylko rozliczenia księgi, a nie rozliczenia należności czy zobowiązań.

Przed włączeniem funkcji **Świadomości** rok podatkowy, który będzie podlegał zamknięciu roku, nie może mieć żadnych transakcji w księdze rachunkowej, które są rozliczane w innych latach podatkowych. W szczególności wszelkie transakcje, które zostały zaksięgowane w roku podatkowym, dla którego przeprowadzasz zamknięcie roku, muszą być nierozliczone z transakcjami, które zostały zaksięgowane w innym roku podatkowym. Transakcje te mogą być następnie rozliczone z transakcjami w tym samym roku podatkowym.

W tym artykule opisano kroki wymagane do zidentyfikowania, nierozliczenia i ponownego rozliczenia transakcji w księdze, które są rozliczane w ciągu roku podatkowego. W podanym przykładzie zamknięto rok podatkowy 2021, a Ty przygotowujesz się do zamknięcia roku podatkowego 2022.

Od wersji 10.0.29 Microsoft Dynamics 365 Finance można identyfikować, rozłączać i ponownie rozliczać transakcje księgi głównej za pomocą nowej strony zapytania. Jeśli nie masz jeszcze wersji programu Finance 10.0.29 lub nowszej, kroki związane z identyfikacją, rozrachunkiem i ponownym rozrachunkiem transakcji księgi głównej znajdziesz w poniższych artykułach:

- [Świadomość funkcji rozliczenia między księgami przed zamknięciem roku](ledger-settle-yec.md)
- [Świadomość funkcji rozliczenia między księgami po zamknięciu roku](ledger-settle-yec-after.md)

Aby uzyskać więcej informacji o nowym oknie zapytania, zobacz informacje [Rozliczenie księgi](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Przykład konfiguracji

Poniższa ilustracja przedstawia transakcje, które zostały zaksięgowane na koncie głównym 110200. Transakcje w kolorze zielonym zostały rozliczone w tym samym roku podatkowym i nie muszą być zmieniane. Transakcje zaznaczone na czerwono zostały rozliczone w księgach rachunkowych, ale mają daty transakcji w różnych latach podatkowych. Transakcje te muszą zostać zidentyfikowane, a rozliczenie księgi może wymagać cofnięcia.

![Zaksięgowanie transakcji w księdze.](./media/ledgersettlement.png)

## <a name="example"></a>Przykład

Wykonaj poniższe kroki, jeśli Twoja organizacja chce skorzystać z funkcji **Świadomości** przed zamknięciem roku podatkowego 2022.

> [!NOTE]
> Zamknięcie roku 2021 i wcześniejszych lat podatkowych musi być powtórzone tylko wtedy, gdy nowe transakcje zostaną zaksięgowane w roku podatkowym 2021 lub wcześniejszym. Gdy wykonasz poniższą procedurę, żadne nowe transakcje nie zostaną zaksięgowane w 2021 roku. Dzięki temu nie trzeba ponownie przeprowadzać zamknięcia roku.
>
> Transakcje w księdze, które są rozliczane w różnych latach podatkowych, mogą pozostać rozliczone w księdze, jeśli nie są rozliczane z transakcją, która została zaksięgowana w roku 2022 (rok, który jest zamykany) lub później. Na przykład, jeśli rozliczyłeś transakcje w latach 2019 i 2020, mogą one pozostać rozliczone.

1. **Nie** włączaj funkcji **Świadomości**.
2. Na stronie **Rozliczenia księgowe** wybierz **Przeglądaj rozliczenia międzyroczne**.
3. Zidentyfikuj wszystkie transakcje, które zostały zaksięgowane w innych latach podatkowych, ale rozliczone z transakcjami, które zostały zaksięgowane w 2022 roku.

    1. Wybierz rok fiskalny 2022, czyli ten, dla którego chcesz przeprowadzić proces zamknięcia roku.
    2. Wybierz wartość w polu **Zestaw wymiarów finansowych**, aby wyświetlić wymiary finansowe, które chcesz zobaczyć dla danego konta księgowego. Konto główne jest zawsze pokazywane, nawet jeśli wybrany zestaw wymiarów nie zawiera konta głównego.
    3. Wybierz **Pokaż transakcje**.

    Na stronie zapytania zostaną wyświetlone wszystkie transakcje, dla wszystkich kont księgi (nawet jeśli nie ma ich już w ustawieniach rozliczenia księgi), ze wszystkich innych lat podatkowych, które są rozliczane z transakcjami zaksięgowanymi w 2022 roku. Wyświetlane są trzy różne konta księgowe.

    ![2022 rozliczenia międzyroczne.](./media/review-cross-year.png)

3. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w siatce, a następnie wybierz polecenie **Eksportuj wszystkie wiersze**. W tych wierszach znajdują się wszystkie transakcje, które muszą być nierozliczone z transakcji w 2022 roku, aby można było przeprowadzić zamknięcie roku. Chcesz mieć szczegółową listę transakcji, aby później móc je prawidłowo rozliczyć.
4. Zwróć uwagę na lata podatkowe, w których zostały zaksięgowane transakcje. W tym przykładzie mamy do czynienia z transakcjami w latach 2021 i 2023.
5. Na stronie zapytania zmień rok podatkowy na 2021, czyli pierwszy rok podatkowy, który zawiera transakcje rozliczone z transakcjami z 2022 roku.
6. Filtruj kolumnę **Data transakcji**, aby uwzględnić tylko te transakcje, które zostały zaksięgowane w roku 2022. Są to szczegółowe transakcje z 2022 roku, które zostały rozliczone z transakcjami z 2021 roku.
7. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w siatce, a następnie wybierz polecenie **Eksportuj wszystkie wiersze**.

    > [!IMPORTANT]
    > W kolejnych krokach transakcje te zostaną nierozliczone, a następnie ponownie rozliczone z transakcjami w 2022 roku. Bardzo ważne jest, abyś przechowywał te informacje w programie Excel.

    ![2021 rozliczenia międzyroczne.](./media/review-cross-year.png)

8. Na stronie zapytania zmień rok podatkowy na 2023, czyli następny rok podatkowy, który zawiera transakcje rozliczone z transakcjami z 2022 roku. 
9. Filtruj kolumnę **Data transakcji**, aby uwzględnić tylko te transakcje, które zostały zaksięgowane w roku 2022. Są to szczegółowe transakcje z 2023 roku, które zostały rozliczone z transakcjami z 2022 roku. 
10. Wybierz i przytrzymaj (lub kliknij prawym przyciskiem myszy) w siatce, a następnie wybierz polecenie **Eksportuj wszystkie wiersze**.

    > [!IMPORTANT]
    > W kolejnych krokach transakcje te zostaną nierozliczone, a następnie ponownie rozliczone z transakcjami w 2022 roku. Bardzo ważne jest, abyś przechowywał te informacje w programie Excel.

    ![2023 rozliczenia międzyroczne.](./media/filter-transactions.png)

11. Powtórz poprzednie kroki dla każdego roku podatkowego, w którym występują transakcje rozliczane z transakcjami w 2022 roku. Zawsze eksportuj szczegółowe transakcje do programu Excel.

    Po wyeksportowaniu wszystkich szczegółowych transakcji z lat 2021 i 2023 do Excela, możesz je rozliczyć za pomocą nowej strony zapytania.

12. Zmień rok rozliczeniowy na 2022.
13. Zaznacz wszystkie rekordy w siatce, a następnie wybierz **Unieważnij zaznaczone rekordy**. Wszystkie wybrane transakcje w siatce zostaną nierozliczone.

    Pojawiają się dwa komunikaty ostrzegawcze, aby upewnić się, że szczegóły transakcji zostały wyeksportowane do programu Excel, zanim zostaną nierozliczone. Jeśli przypadkowo rozłączysz transakcje księgi przed wysłaniem szczegółów do Excela, nie ma możliwości cofnięcia rozłączeń.

    ![Rozliczanie transakcji krzyżowych.](./media/revert-unsettle.png)

14. Wykorzystaj dane z Excela, aby znaleźć łączną kwotę transakcji z lat 2021 i 2023, które zostały rozliczone z transakcjami z roku 2022. W tym przykładzie transakcje z 2021 roku wynoszą 525 dolarów, a z 2023 roku 700 dolarów.
15. Zamieść ogólny dziennik korygujący, aby podzielić bilans otwarcia na rok 2022 na dwie kwoty: część, która została rozliczona na rok podatkowy 2021 oraz część, która nie została jeszcze rozliczona na rok 2022.

    - **Część bilansu otwarcia, która została rozliczona w poprzednim roku:** Pierwsza kwota wynosi 525 dolarów i jest oparta na sumach, które zostały rozliczone w latach 2021 i 2022.
    - **Część bilansu otwarcia, która nie została rozliczona w poprzednim roku:** Druga kwota to różnica między bilansem otwarcia a rozliczoną kwotą 525 dolarów. Pozostała kwota to 1025 $ - 525 $ = 500 $.

    W ten sposób możesz rozliczyć transakcje z 2022 roku z kwoty 525 dolarów, która została pierwotnie rozliczona z transakcji z 2021 roku. Ten krok jest wymagany, ponieważ rozliczenie w księdze głównej nie pozwala na częściowe rozliczenie.

    1. Przejdź do dziennika ogólnego i wpisz korektę. Twoja organizacja będzie musiała zdecydować, jaką datę transakcji zastosować w zależności od otwartych okresów. Transakcje te mogły zostać rozliczone z datą rozliczenia przypadającą na styczeń lub luty 2022 roku, ale może się okazać, że korekta zostanie zaksięgowana w grudniu, jeśli jest to jedyny otwarty okres.
    2. Być może będziesz musiał tymczasowo wyłączyć parametr **Nie zezwalaj na ręczne wprowadzanie** dla konta 110200 na stronie **Konto główne**. To dostosowanie nie zostanie uwzględnione, jeśli konto główne nie pozwala na ręczne wprowadzanie danych.

    ![Księgowanie dziennika ogólnego korygującego.](./media/not-post.png)

16. Możesz teraz ponownie rozliczyć nierozliczone transakcje. Wróć do strony **Rozliczenia księgowe**, określ zakres dat od 1 stycznia do 31 grudnia 2022 roku i filtruj na koncie głównym 110200. Następnie użyj szczegółowych transakcji, które wyeksportowałeś do Excela, aby znaleźć konkretne transakcje, które muszą zostać ponownie rozliczone. Poniższa ilustracja przedstawia nierozliczone transakcje, które obecnie istnieją.

    ![Nierozliczone transakcje.](./media/updated-unsettled.png)

    - Bilans otwarcia w wysokości 1 025 USD może zostać rozliczony z korektą o wartości – 1 025 USD.
    - Szczegółowe transakcje, które nie zostały rozliczone na kwoty -400 $, -50 $ i -75 $, mogą zostać rozliczone z korektą o 25$.

17. Włącz funkcję **Świadomość**. Jesteś teraz gotowy do przeprowadzenia zamknięcia roku.

    - Zanim przeprowadzisz zamknięcie roku, rozważ wybranie opcji **Zachowaj szczegóły** dla wszystkich kont bilansowych w ustawieniach rozliczenia księgi. Aby uzyskać więcej informacji, zobacz temat [Relacja między rozliczeniem księgi a zamknięciem roku](awareness-between-ledger-settlement-year-end-close.md).
    - Gdy rozpoczniesz zamykanie roku 2022, jeśli nadal będziesz miał do czynienia z transakcjami, które zostały rozliczone w innych latach podatkowych, proces zamykania roku natychmiast Cię o tym powiadomi. Taka sytuacja może mieć miejsce, jeśli użytkownicy rozliczali transakcje w różnych latach podatkowych po wykonaniu poprzednich kroków.
    - Jeśli transakcje z lat 2021 i 2022 są nadal rozliczone, będziesz musiał ponownie wyłączyć funkcję **Świadomości**, a następnie powtórzyć poprzednie kroki, aby wyłączyć te transakcje. Takie podejście jest konieczne, ponieważ rok 2021 jest zamknięty, a w zamkniętym roku podatkowym nie można rozliczać transakcji.
    - Jeśli transakcje 2022 i 2023 są nadal rozliczane, nie musisz wyłączać funkcji **Świadomości**. Ponieważ ani rok 2022, ani 2023 nie są zamknięte, możesz skorzystać z poprzednich kroków, aby rozliczyć te transakcje.

18. Możesz rozliczyć transakcję o wartości 700 $ z roku 2023 z transakcjami szczegółowymi, które zostały przeniesione jako bilans otwarcia w roku 2023. Ta transakcja nie zostanie rozliczona z pierwotną transakcją w 2022 roku.

Po pomyślnym przeprowadzeniu zamknięcia roku 2022 możesz pozostawić włączoną funkcję **Świadomości**.
