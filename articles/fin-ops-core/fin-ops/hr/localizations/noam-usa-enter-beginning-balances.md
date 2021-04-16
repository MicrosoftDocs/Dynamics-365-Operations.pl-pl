---
title: Wprowadzanie sald początkowych listy płac
description: W tym temacie opisano kroki wprowadzania sald początkowych dla kodów zarobków, potrąceń, świadczeń i podatków.
author: andreabichsel
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9272828fe5d6e0bf131ea66353a0d5c3c7b1c4bd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752157"
---
# <a name="enter-payroll-beginning-balances"></a>Wprowadzanie sald początkowych listy płac

[!include [banner](../../includes/banner.md)]

W tym temacie opisano kroki wprowadzania sald początkowych dla kodów zarobków, potrąceń, świadczeń i podatków. Informacje te są przydatne dla partnerów, którzy chcą przenieść dane do nowej implementacji modułu Lista płac z innego systemu. W ramach przygotowania do wprowadzenia sald początkowych listy płac weryfikujemy następujące informacje:

- Rekordy pracowników etatowych są wprowadzone i dostępne w systemie
- Następujące dane są skonfigurowane i przypisane do pracowników:

    - Cykle płac i okresy płac
    - Kody zarobków
    - Podatki
    - Świadczenia i potrącenia

- Firma powinna mieć wybraną datę, od kiedy można ustawiać salda początkowe listy płac.
- Ze starszych systemów zebrano informacje o wszystkich zarobkach, świadczeniach/potrąceniach, wpłatach składek na świadczenia, podatkach pracowników i podatkach pracodawców oraz ich kwotach od początku roku.

Planując wprowadzenie sald początkowych, należy wziąć pod uwagę wymagany stopień szczegółowości danych. Większość firm wprowadza pojedyncze, skonsolidowane wartości od początku roku. Jednak jeśli są potrzebne bardziej szczegółowe informacje, salda można wprowadzić w przyrostach kwartalnych. Decyzja o potrzebnym poziomie szczegółów określi, ile ręcznych sprawozdań o wynagrodzeniach należy utworzyć dla każdego pracownika. Dla jednej kwoty od początku roku jest wymagane tylko jedno ręczne sprawozdanie dla każdego pracownika. W tym celu należy użyć kwot od początku z końcowego sprawozdania o wynagrodzeniach z poprzedniego systemu jako kwoty wprowadzonej w nowym systemie listy płac.

W poniższym przykładzie pokazano, jak można wprowadzić salda początkowe listy płac pracowników, łącznie z kodami zarobków, świadczeniami/potrąceniami i podatkami. W warunkach realnych istniałaby osobna pozycja dla każdego kodu zarobków, potrącenia na świadczenie, wpłaty na świadczenie, podatku pracownika i podatku pracodawcy, gdzie wprowadzana kwota byłaby wartością od początku roku. Używając tej listy kodów i kwot, wykonaj kroki procedury tworzenia ręcznego sprawozdania zarobków i płac przy wyłączonej funkcji księgowania, dzięki czemu kwoty zostaną wprowadzone jako salda początkowe dla listy płac. Funkcję księgowania wyłączasz, ponieważ nie chcesz księgować tego salda początkowego ze sprawozdania o wynagrodzeniach do księgi głównej. To zostało zrobione w poprzednim systemie i zostanie przeniesione do nowego systemu podczas ustawiania sald początkowych w księdze głównej.

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a>A. Konfigurowanie używania kodów zarobków w saldach początkowych listy płac

Podczas wprowadzania sald początkowych listy płac upewnij się, że kody zarobków, których będziesz używać, są skonfigurowane z włączoną opcją „Zezwalaj na edytowanie stawek w sprawozdaniu o zarobkach”. Dzięki temu będzie można ręcznie wprowadzać kwoty ze starszych systemów. 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a>B. Tworzenie sprawozdania o zarobkach dla pracownika w celu uzyskania salda początkowego

W tym kroku jest ręcznie tworzone sprawozdanie o zarobkach dla każdego pracownika za ostatni okres płac ze starszego systemu, co powoduje utworzenie wierszy sprawozdania o zarobkach w nowym systemie listy płac. Wprowadź jeden wiersz dla każdego kodu zarobków oraz sumę od początku roku i godziny. Oto przykładowe czynności:

1. Otwórz stronę **Wszystkie sprawozdania o zarobkach** i kliknij przycisk **Nowy**.

    Wpisz następujące dane: 

    | Pole      | Wartość                 |
    |------------|-----------------------|
    | Pracownik     | Michael Redmond       |
    | Cykl płac  | sm                    |
    | Okres płac | 16.06.2017 - 30.06.2017 |

2. Na karcie **Wiersz sprawozdania o zarobkach** wprowadź następujące informacje:

    Wiersz 1: karta **Wiersz sprawozdania o zarobkach**

    | Pole            | Wartość       |
    |------------------|-------------|
    | Kod zarobków    | Zwykła wypłata |
    | Ilość         | 1.00        |
    | Kurs             | 30,000      |
    | karta Szczegóły wiersza |             |
    | Ręczny           | (zaznaczone)    |

    Wiersz 2: karta **Wiersz sprawozdania o zarobkach**

    | Pole            | Wartość    |
    |------------------|----------|
    | Kod zarobków    | Premia    |
    | Ilość         | 1.0000   |
    | Kurs             | 4250.00  |
    | karta Szczegóły wiersza |          |
    | Ręcznie           | (zaznaczone) |

    Wiersz 3: karta **Wiersz sprawozdania o zarobkach**

    | Pole           | Wartość      |
    |-----------------|------------|
    | Kod zarobków   | Prowizja |
    | Ilość        | 1.0000     |
    | Kurs            | !,299,00   |
    | Kurs            | 1,299.00   |
    | karta Szczegóły wiersza |            |
    | Ręcznie          | (zaznaczone)   |

    > [!NOTE]
    > Ustawienie suwaka **Ręcznie** w pozycji **Tak** na karcie **Szczegóły wiersza** dla każdego wiersza sprawozdania o zarobkach jest niezbędne, aby dla poszczególnych pracowników zostały wprowadzone salda początkowe listy płac.

3. W okienku **Akcja** kliknij pozycję **Zwolnij sprawozdanie o zarobkach** USA-FED-ER-FICA.
4. W okienku **Akcja** kliknij opcję **Sprawozdanie o wynagrodzeniach**, aby otworzyć stronę **Generuj sprawozdania o wynagrodzeniach** i skonfigurować następujące opcje:

    | Pole              | Wartość     |
    |--------------------|-----------|
    | Data płatności       | 6/30/2017 |
    | Typ przebiegu płatności   | Ręcznie    |
    | Wyłącz księgowanie |   Tak     |

    > [!NOTE] 
    > Te opcje są dostępne tylko wtedy, gdy pole Typ przebiegu płatności ma wartość Ręcznie, tzn. użytkownik wyłączy księgowanie w sesji kalkulacji płac.

    Kliknij przycisk **OK** i zamknij okno **Dziennik informacyjny**.

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a>Dlaczego podczas generowania sprawozdań o wynagrodzeniach suwak Wyłącz księgowanie musi być przesunięty w położenie Tak?

Ustawienie suwaka na pozycji **Tak** zapobiega rozdzielaniu wierszy w sprawozdaniu o wynagrodzeniach do księgi głównej. Kwoty księgi głównej zostały zaktualizowane wcześniej, podczas wprowadzenia sald kont ze starszego systemu. Wprowadzenie sald początkowych dla listy płac umożliwia generowanie raportów zawierających informacje z poprzednich lat, a także identyfikowanie limitów dla celów ustalania świadczeń i podatków.

### <a name="c-create-pay-statements-for-employees"></a>C. Tworzenie sprawozdań o wynagrodzeniach dla pracowników

Po wygenerowaniu sprawozdań o wynagrodzeniach mających salda początkowe należy zweryfikować, czy sprawozdania o wynagrodzeniach dokładnie odzwierciedlają dane listy płac. Należy także ręcznie zaktualizować dane świadczeń i podatków, aby były one zgodne z wartościami w poprzednim systemie listy płac. Po upewnieniu się, że kwoty z poprzedniego systemu listy płac są zgodne z kwotami w bieżących sprawozdaniach o wynagrodzeniach, należy sfinalizować sprawozdania o wynagrodzeniach.

1. Otwórz stronę **Wszystkie sprawozdania o wynagrodzeniach**.
2. Wyróżnianie ostatniego wygenerowanego sprawozdania o wynagrodzeniach dla Michaela Redmonda
3. Kliknij przycisk **Edytuj**, a zostanie otwarta strona **Sprawozdanie o wynagrodzeniach**.
4. Otwórz kartę **Potrącenia dot. świadczenia** i wprowadź następujące informacje:

    | Pole             | Wartość            |
    |-------------------|------------------|
    | Świadczenie           | Kwota potrącenia |
    | 401K              | Uczestnictwo      |
    | Stomatologia            | SubSp            |
    | Wydatki na opiekę szpitalną | Uczestnictwo      |
    | Okulistyka            | SupSp            |

5. Na karcie **Udziały w świadczeniu** i wprowadź następujące informacje:

    | Pole   | Wartość               |
    |---------|---------------------|
    | Świadczenie | Kwota udziału |
    | 401K    | Uczestnictwo         |
    | Stomatologia  | SubSp               |
    | Okulistyka  | SubSp               |

6. Na karcie **Potrącenia podatku** wprowadź następujące informacje:

    | Pole           | Wartość            |
    |-----------------|------------------|
    | Kod podatku        | Kwota potrącenia |
    | USA-FED-ER-FICA | 1600.00          |
    | USA-FED-ER-MEDI | 825.75           |

7. Na karcie **Udziały w podatku** wprowadź następujące informacje:
8. Kliknij przycisk **Oblicz**.

    > [!IMPORTANT] 
    > Sprawdź, czy sumy w sprawozdaniu o wynagrodzeniach dla pracownika są zgodne z wartościami od początku roku w starszym systemie. Warto się wstrzymać z finalizowaniem w następnym kroku i przeprowadzić ogólne całościowe sprawdzanie poprawności wszystkich sprawozdań o wynagrodzeniach. Po zakończeniu sprawdzania poprawności przejdź przez wszystkie sprawozdania o wynagrodzeniach i je sfinalizuj.

W razie potrzeby ten sam proces można wykonać w przyrostach kwartalnych dla wszystkich poprzednich kwartałów w każdym roku. Jest to potrzebne tylko wtedy, gdy odbiorca chce widzieć dane z podziałem na kwartały bez wracania do starego systemu.

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a>W razie popełnienia błędu przy wprowadzaniu sald początkowych dla pracownika

Istnieje możliwość wycofywania i ponownego wprowadzania transakcji. Aby wystornować transakcję, wystarczy tylko wykonać następujące czynności na stronie **Wszystkie sprawozdania o wynagrodzeniach**.

1. Kliknij przycisk **Wycofaj**.
2. Kliknij przycisk **Tak**, gdy zostanie wyświetlony komunikat „Wycofanie tego sprawozdania o wynagrodzeniach spowoduje utworzenie wycofującego sprawozdania o wynagrodzeniach, które będzie do niego przeciwstawne. Żadnego z tych sprawozdań o wynagrodzeniach nie można edytować. Czy chcesz wycofać to sprawozdanie o wynagrodzeniach?” . 

Po wycofaniu sprawozdania o wynagrodzeniach można wygenerować nowe sprawozdanie o wynagrodzeniach dla pracownika ze sprawozdania o zarobkach, które utworzono wcześniej. Pamiętaj, aby przed wygenerowaniem nowego sprawozdania o wynagrodzeniach poprawić wszelkie nieprawidłowe wiersze w sprawozdaniu o zarobkach, a następnie wygenerować nowe sprawozdania o wynagrodzeniach z właściwymi kwotami. 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]