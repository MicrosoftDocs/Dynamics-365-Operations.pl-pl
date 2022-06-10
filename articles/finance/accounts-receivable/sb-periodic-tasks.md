---
title: Zadania okresowe w rozliczeniach kontraktów cyklicznych
description: Ten temat opisuje zadania okresowe, które są dostępne w cyklicznym rozliczaniu umów.
author: JodiChristiansen
ms.date: 04/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 80f65d82881bb000f626c4225b3eac7dd1a2a44a
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786974"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>Zadania okresowe w rozliczeniach kontraktów cyklicznych

Ten temat opisuje zadania okresowe, które są dostępne w cyklicznym rozliczaniu umów.

## <a name="generate-invoice"></a>Generuj fakturę

Użyj strony **Generuj fakturę**, aby utworzyć masowe comiesięczne faktury cykliczne na podstawie informacji, które skonfigurowałeś na stronach **Wszystkie harmonogramy rozliczeń** i **Sprawdź szczegóły rozliczeń**. Kiedy tworzona jest faktura, opis pozycji dla linii przetwarzania zlecenia sprzedaży jest uaktualniany o opis pozycji oraz daty rozpoczęcia i zakończenia fakturowania dla linii harmonogramu, która jest fakturowana.

## <a name="generate-invoice-batch-processing"></a>Generuj przetwarzanie partii faktury

Użyj strony **Generowanie faktur w procesie wsadowym**, aby utworzyć powtarzające się faktury za pomocą powtarzającego się procesu wsadowego. Dostępne parametry są takie same jak parametry na stronie **Generuj fakturę**, ale można je zapisać w procesie wsadowym, który może być uruchamiany wielokrotnie.

## <a name="price-update"></a>Aktualizacja ceny

Użyj narzędzia Aktualizacja cen, aby w jednym działaniu zaktualizować ceny kilku pozycji w wielu harmonogramach rozliczeniowych. Ceny mogą być aktualizowane w oparciu o określony procent lub określoną kwotę. Lista linii pokazuje tylko aktualne ceny jednostkowe przedmiotów. Nie pokazuje cen po aktualizacji cen.

Zwróć uwagę na następujące kwestie dotyczące narzędzia aktualizacji cen:

- Jeśli zamówienie sprzedaży na dany rok zostało już utworzone (tzn. pozycje zostały już rozliczone), nie ma to wpływu na cenę pozycji.
- Narzędzie do aktualizacji cen może być używane dla pozycji liniowych, które mają status **Aktywny** lub **Zatrzymany**. W przypadku pozycji, które są wstrzymane, opcja **Dostosuj harmonogram** musi być ustawiona na **Nie**, kiedy pozycja została wstrzymana.
- Narzędzie do aktualizacji cen nie może być używane dla pozycji, które są pozycjami użytkowymi, wykorzystują eskalację, rozliczenia milowe lub podział przychodów.

### <a name="price-update-example"></a>Przykład aktualizacji cen

Tworzony jest harmonogram rozliczeń i dodawana jest pozycja odnowienia. Cena jednostkowa wynosi 750 dolarów. Pierwszy rok obowiązywania pozycji jest płatny 15 grudnia 2021 roku. Harmonogram rozliczeń jest tworzony na okres od 1 stycznia do 31 grudnia 2022 roku.

W momencie odnowienia proces **Generuj fakturę** tworzy zlecenie sprzedaży na rok 2022. Po uruchomieniu narzędzia Aktualizacja cen cena zostaje zaktualizowana z 750 na 800 dolarów.

Nie ma to wpływu na zamówienie sprzedaży i harmonogram rozliczeń na rok 2022, a cena jednostkowa pozostaje na poziomie 750 dolarów, ponieważ harmonogram rozliczeń na rok 2022 został już rozliczony. Linia harmonogramu rozliczeń i szczegóły linii na rok 2023 są zaktualizowane do 800 dolarów, ponieważ harmonogram rozliczeń na rok 2023 nie został jeszcze rozliczony.

### <a name="update-prices--flat-pricing-method"></a>Aktualizacja cen - metoda cen płaskich

Kiedy aktualizujesz ceny elementów, które korzystają z metody cen płaskich, możesz określić procent lub kwotę, o jaką ma być zwiększona cena.

Aby uruchomić narzędzie do aktualizacji cen dla pozycji, które korzystają z metody cen płaskich, wykonaj poniższe kroki.

1. Na stronie narzędzia **Aktualizacja cen** wybierz **Równomierną** metodę ustalania cen.
2. W polu **Metoda podwyższania** wybierz metodę podwyższania, która będzie używana do aktualizacji cen artykułów.
3. W zależności od wybranej metody zwiększania, określ wartość procentową w polu **Procent** lub kwotę w polu **Kwota**.
4. Na skróconej karcie **Rekordy do uwzględnienia** użyj przycisku **Filtr**, aby dodać filtry danych.
5. Wybierz **opcję Wyświetl podgląd**, aby wyświetlić zakres rekordów.
6. Jeśli nie chcesz przetwarzać niektórych linii, zaznacz je, a następnie wybierz **Usuń**.
7. Kliknij przycisk **OK**.

### <a name="update-prices--standard-pricing-method"></a>Aktualizacja cen - Standardowa metoda ustalania cen

Jeśli cena elementu została zmieniona w rekordzie elementu, może zostać zaktualizowana dla wszystkich linii harmonogramu rozliczeniowego, jeśli element korzysta ze standardowej metody ustalania cen.

1. Na stronie narzędzia **Aktualizacja cen** wybierz **Standard** metodę ustalania cen.
2. Na skróconej karcie **Rekordy do uwzględnienia** użyj przycisku **Filtr**, aby dodać filtry danych.
3. Wybierz **opcję Wyświetl podgląd**, aby wyświetlić zakres rekordów.
4. Jeśli nie chcesz przetwarzać niektórych linii, zaznacz je, a następnie wybierz **Usuń**.
5. Kliknij przycisk **OK**.

## <a name="mass-hold-processing"></a>Masowe przetwarzanie wstrzymań

Użyj strony **Zatrzymanie masowe**, aby zastosować opcje wstrzymania do kilku harmonogramów rozliczeniowych jednocześnie.

Aby wstrzymać tylko jeden harmonogram billingowy lub jedną linię harmonogramu billingowego, otwórz stronę **Wszystkie harmonogramy billingowe** i wybierz **Zatrzymaj**. Aby usunąć wstrzymanie, użyj strony **Usuń wstrzymanie**.

### <a name="put-billing-schedules-on-hold"></a>Wstrzymaj harmonogramy rozliczeń

Aby wstrzymać kilka harmonogramów rozliczeniowych, wykonaj poniższe kroki.

1. Na stronie **Masowe wstrzymanie** ustaw w polu **Przetwarzanie opcji** wartość **Zastosuj wstrzymanie**.
2. Następnie w polu **Kod przyczyny** wybierz kod przyczyny.
3. Ustaw opcję **Dostosuj harmonogram**:

    - **Tak** - Jeśli ustawisz tę opcję na **Tak**, określ datę wstrzymania w polu **Data wstrzymania**. Wszystkie linie harmonogramu rozliczeniowego po dacie wstrzymania są usuwane.
    - **Nie** – wiersze harmonogramu rozliczeń nie ulegają zmianie. Zmienia się tylko status. Zaktualizowane na **Wstrzymano**.

4. Na skróconej karcie **Rekordy do uwzględnienia** użyj przycisku **Filtr**, aby dodać filtry danych.
5. Wybierz **opcję Wyświetl podgląd**, aby wyświetlić zakres rekordów.
6. Jeśli nie chcesz przetwarzać niektórych linii, zaznacz je, a następnie wybierz **Usuń**.
7. Kliknij przycisk **OK**.

Kiedy wrócisz do listy harmonogramów rozliczeń, powinieneś zobaczyć, że status harmonogramów rozliczeń został zmieniony na **Wstrzymane**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>Usuń wstrzymanie z kilku harmonogramów rozliczeniowych

1. Na stronie **Masowe wstrzymanie** ustaw w polu **Przetwarzanie opcji** wartość **Usuń wstrzymanie**.
2. Następnie w polu **Kod przyczyny** wprowadź kod przyczyny.
3. W polu **Data usunięcia** wybierz datę, kiedy wstrzymanie powinno zostać usunięte.
4. Ustaw pola **Data wznowienia** i **Data odroczenia** według własnych potrzeb. Data odroczenia jest dodawana do wszystkich linii, które podlegają odroczeniu.
5. Na skróconej karcie **Rekordy do uwzględnienia** użyj przycisku **Filtr**, aby dodać filtry danych.
6. Wybierz **opcję Wyświetl podgląd**, aby wyświetlić zakres rekordów.
7. Jeśli nie chcesz przetwarzać niektórych linii, zaznacz je, a następnie wybierz **Usuń**.
8. Kliknij przycisk **OK**.

> [!NOTE]
> Aby usunąć wstrzymanie, musisz ustawić wartość **Nadpisanie grupy użytkowników dla usunięcia wstrzymania** na stronie **Parametry rozliczania umów cyklicznych**.

Na przykład linia rozliczeniowa ma datę początkową 1 lutego 2022 roku i datę końcową 28 lutego 2022 roku. Kwota rozliczenia wynosi 200 dolarów. Pole **Data wstrzymania** jest ustawione na 10 lutego 2022. Dlatego okres lutowy jest korygowany tak, aby wykluczyć wszystkie daty po 10 lutego. Nowy okres trwa od 1 lutego do 9 lutego, a kwota wynosi 64,29 $ (poprzez dzienną prorację). Wszystkie linie harmonogramu rozliczeniowego powstałe 10 lutego lub później zostają usunięte.

Jeśli proces **Usuwania blokady** zostanie zakończony, a w polu **Data usunięcia** zostanie wpisana data 10 lutego 2022 roku, będą dwa okresy rozliczeniowe. Pierwszy okres rozliczeniowy trwa od 1 do 9 lutego, a kwota wynosi 64,29 $. Drugi okres rozliczeniowy trwa od 10 do 28 lutego, a kwota wynosi 135,71 $.

## <a name="mass-termination-processing"></a>Masowe przetwarzanie wypowiedzenia

Użyj strony **Zakończenie masowe**, aby zakończyć linie harmonogramu rozliczeniowego, które są aktualnie wyświetlane, określając datę zakończenia.

Jeśli używasz odroczeń przychodów i kosztów, do zwrotu kwalifikują się harmonogramy rozliczeń, w których pole **Data zakończenia** jest ustawione na **Dostosuj harmonogram** na stronie **Wszystkie harmonogramy rozliczeń**.

Harmonogramy rozliczeniowe, które korzystają z funkcji przydziału wielu elementów (MEA), nie pojawiają się na stronie **Masowe zakończenie kontraktu**. Nadal możesz zamknąć indywidualny harmonogram rozliczeniowy, korzystając z funkcji zamykania harmonogramu rozliczeniowego.

> [!NOTE]
> Linie harmonogramu rozliczeń, które są obecnie zawarte w partii **Generuj fakturę**, nie są dostępne dla tego procesu.

Aby uzyskać informacje na temat każdego pola i procesu, zobacz [Zakończ harmonogramy rozliczeń](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>Masowy proces archiwum

Użyj strony **Archiwum masowe**, aby zarchiwizować wiele harmonogramów rozliczeniowych. Archiwizowane mogą być tylko zakończone harmonogramy rozliczeń.

Po zarchiwizowaniu harmonogramu rozliczeniowego mają miejsce następujące zdarzenia:

- Status płatności zostanie zmieniony na **Zarchiwizowano**.
- Harmonogramy rozliczeń są zablokowane na stałe.
- Wiersze harmonogramu rozliczeń nie są już dostępne na stronach z zapytaniami.

> [!NOTE]
> Archiwizacja harmonogramu rozliczeniowego jest działaniem trwałym i nie może być cofnięta.

Aby zarchiwizować harmonogramy rozliczeń, wykonaj poniższe kroki.

1. Na stronie **Masowe archiwum**, w polu **Data zakończenia rozliczenia**, określ datę zakończenia rozliczenia. Aby wyświetlić wszystkie zakończone harmonogramy rozliczeń, pozostaw to pole puste.
2. Na skróconej karcie **Rekordy do uwzględnienia** użyj przycisku **Filtr**, aby ograniczyć wyświetlane rekordy.
3. Wybierz **Zobacz podgląd**.
4. Jeśli nie chcesz archiwizować niektórych rekordów, zaznacz je, a następnie wybierz **Usuń**.
5. Wybierz **OK**, aby zarchiwizować rekordy na stronie.

## <a name="mass-stubbing-process"></a>Masowy proces przycinania

Użyj strony **Masowe przycięcie**, aby oznaczyć wszystkie wybrane linie harmonogramu rozliczeniowego jako rozliczone (przycięcie) lub nieobliczone (odwrócone przycięcie). Najczęściej są one wykonywane na zaimportowanych wierszach harmonogramu fakturowania, które były wcześniej rozliczane w innym systemie. Zablokowane wiersze harmonogramu rozliczeń są wyświetlane jako zablokowane i nie tworzą faktury dla klienta.

### <a name="stub-records"></a>Przycięte rekordy

1. Na stronie **Masowe przycięcie**, w polu **Opcje procesu** wybierz **Przycięcie**.
2. W polu **Data graniczna** ustaw datę graniczną, aby określić wiersze, do których chcesz zastosować ten proces. Wyświetlone zostaną tylko rekordy, w których data rozpoczęcia rozliczenia jest równa lub wcześniejsza od podanej daty granicznej.
3. Wybierz opcję **Podgląd widoku**, aby wyświetlić wiersze, które chcesz przyciąć.
4. Aby wykluczyć wiersz z procesu, zaznacz go, a następnie wybierz polecenie **Usuń**.
5. Wybierz przycisk **Przetwórz**, aby przyciąć wiersze.

### <a name="reverse-stub-records"></a>Odwrotne przycinanie rekordów

1. Na stronie **Masowe przycięcie**, w polu **Opcje procesu** wybierz **Odwrotne przycięcie**.
2. W polu **Data graniczna** ustaw datę graniczną, aby określić wiersze, do których chcesz zastosować ten proces. Wyświetlone zostaną tylko rekordy, w których data rozpoczęcia rozliczenia jest równa lub wcześniejsza od podanej daty granicznej.
3. Wybierz opcję **Podgląd widoku**, aby wyświetlić wiersze, które chcesz odwrotnie przyciąć.
4. Aby wykluczyć wiersz z procesu, zaznacz go, a następnie wybierz polecenie **Usuń**.
5. Wybierz przycisk **Przetwórz**, aby odwrotnie przyciąć wiersze.

## <a name="update-completion-date-process"></a>Proces aktualizacji daty zakończenia

Użyj strony **Uaktualnij datę ukończenia**, aby zaktualizować datę ukończenia określonych pozycji kamieni milowych dla wielu harmonogramów rozliczeń lub użytkowników. Możesz także aktualizować procent ukończenia dla elementów na szablonach kamieni milowych, które używają metody **Procent ukończenia**.

1. Na stronie **Uaktualnij datę ukończenia** przejdź do zakładki **Przetwarzanie kamieni milowych** i wybierz **Uaktualnij procent ukończenia**.
2. W polu **Wartość procentowa** wprowadź łączną wartość procentową, która została ukończona.
3. Wybierz numer elementu, który jest związany z szablonem kamienia milowego.
4. Na skróconej karcie **Rekordy do uwzględnienia** wybierz **Filtr**, aby wybrać konkretne **konto użytkownika końcowego**, **numer harmonogramu rozliczeń** lub **numer pozycji** jako kryterium filtrowania.
5. Wybierz przycisk **OK**, aby przetworzyć zmianę. Gdy przetwarzanie zostanie zakończone, do alokacji kamieni milowych dodawany jest nowy wiersz. Ten wiersz reprezentuje wartość procentową, która została ukończona dla szablonu kamieni milowych.

## <a name="unbilled-revenue-mass-processing"></a>Masowe przetwarzanie nierozliczonego przychodu

Użyj strony **Przetwarzanie masowe dochodów niefakturowanych**, aby utworzyć wpis w dzienniku dochodów niefakturowanych lub zablokować wpis w dzienniku dla jednego lub kilku wybranych harmonogramów rozliczeń lub linii szczegółów rozliczeń.

- **Utwórz zapis w arkuszu** – tworzenie wpisów w arkuszu niepodliczonych przychodów dla wielu wierszy harmonogramu fakturowania. Użyj przycisku **Filtr** na szybkiej karcie **Rekordy do uwzględnienia**, aby wybrać zakres rekordów, które pojawią się na liście. Lista pokazuje tylko te linie harmonogramu rozliczeń, dla których nie zostały jeszcze utworzone wpisy w dzienniku niefakturowanych przychodów. Tworzone są pierwsze wpisy do arkusza. W przypadku towarów odroczonych tworzone są również harmonogramy odroczeń.
- **Przycięty wpis w arkuszu** - Zaznacz wiersze harmonogramu rozliczeń, dla których zostały już utworzone wpisy w dzienniku bez rozliczenia. Ta opcja jest używana, jeśli wpis w dzienniku niefakturowanym został już zaksięgowany w innym systemie. Oznacza arkusz niefakturowanych przychodów jako "przycięte" i nie księguje transakcji w księdze głównej.
- **Odwrotne przycięcie – wpis w dzienniku** wpisy w dzienniku dotyczące odwrotnego przycięcia, które zostały przetworzone. Jeśli podczas przetwarzania **Wpisu arkusza** popełniono błąd, ta opcja usunie zaznaczenie pola wyboru **Zatrzymany** dla linii harmonogramu rozliczeń.
- **Wiersz szczegółowy rozliczenia przycięcia** - Użyj tego procesu, gdy niefakturowane przychody zostały przetworzone w systemie zewnętrznym, a niektóre z linii fakturowania zostały już rozliczone. Ten proces zapewni, że na kontach niefakturowanych przychodów pojawi się właściwa kwota.
- **Odwróć szczegółową linię rozliczeniową** - Odwróć wszelkie działania związane z **odwróceniem szczegółowego wiersza rozliczeniowego**.

Pole **Nazwa arkusza** służy do umieszczenia **Utwórz wpis do arkusza** w księdze głównej.

> [!NOTE]
> Proces tworzenia odcinków nie księguje kwot do księgi głównej. Pole **Nazwa dziennika** nie jest dostępne dla wszystkich procesów typu przycięcia i odwrotnego przycięcia.

### <a name="unbilled-revenue-stub-example"></a>Przykład przycięcia niefakturowanych przychodów

Harmonogram rozliczeń jest ustalany na jeden rok, od października 2021 do września 2022. Przychody niefakturowane były już przetwarzane w systemie zewnętrznym. Rozliczono już dziewięć miesięcy z harmonogramu rozliczeń. Kwota za każdy okres rozliczeniowy wynosi 250 dolarów. Na początku roku całkowita kwota, która została zaksięgowana na poczet niefakturowanych przychodów, wynosi 3 000 dolarów. Po dziewięciu miesiącach zostało już naliczone 2250 dolarów, a pozostało 750 dolarów nienaliczonych przychodów.

Aby skonfigurować harmonogram rozliczeń, w którym pozostaną tylko trzymiesięczne niefakturowane przychody, wykonaj poniższe kroki.

1. Na stronie **Pokaż szczegóły rozliczeń** utwórz harmonogram rozliczeń na okres od października 2021 roku do września 2022 roku, numer pozycji S0001 i kwotę 250 dolarów miesięcznie.
2. Wybierz **Utwórz wpis do dziennika** dla harmonogramu rozliczeń. Kwota 3 000 $ jest księgowana w przychodach niefakturowanych.
3. Wybierz **Wiersz szczegółów rozliczenia** i określ datę transakcji na czerwiec 2022 roku (dziewięć miesięcy). Wiersze harmonogramu rozliczeń nie pojawią się w podglądzie. Wiersze, których to dotyczy, są oparte na dacie transakcji.
4. Kliknij przycisk **OK**.

Pierwsze dziewięć miesięcy, za które wystawiono rachunki, są przycięte.

[![Zobacz odcinek wierszy rozliczeniowych.](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

Kwota 3000 USD zostaje wycofana z przychodów niefakturowanych, a 750 USD, które pozostało, zostaje zaksięgowane. Aby zobaczyć księgowania niefakturowanych przychodów, wybierz **Audyt wpisu dziennika niefakturowanych przychodów** w zakładce **Odnowienia** na stronie szczegółów wiersza.

[![Inspekcja wpisu w arkuszu nierozliczonego przychodu.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> Wpis w dzienniku dotyczący niefakturowanych przychodów może być utworzony dla dowolnego okresu odnowienia, pod warunkiem, że wszystkie linie szczegółów rozliczenia z poprzedniego okresu zostały rozliczone. Na przykład linia harmonogramu rozliczeń ma miesięczną częstotliwość rozliczeń za okres 12 miesięcy, od stycznia do grudnia 2021 roku. Linia ma trzy terminy: termin początkowy, drugi termin (od stycznia do grudnia 2022 roku) i trzeci termin (od stycznia do grudnia 2023 roku). Po utworzeniu faktur dla wszystkich linii fakturowania z pierwszych 12 miesięcy w 2021 roku można utworzyć wpis w dzienniku dotyczący niefakturowanych przychodów za drugi okres.
>
> W przypadku pozycji odroczenia, które korzystają z funkcji niefakturowanych przychodów, przetwarzane są linie rozliczeniowe i rabatowe. Dla tych pozycji tworzony jest wpis w arkuszu niefakturowanych przychodów oraz harmonogram odroczeń dla wierszy rozliczeniowej i wiersza rabatowego.
>
> Wpisy w arkuszu tworzone dla pozycji nie podlegających odroczeniu i pozycji podlegających odroczeniu księgują uznanie na różnych kontach przychodów.
