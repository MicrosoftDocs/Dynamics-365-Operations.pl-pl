---
title: Nierozliczony przychód
description: Ten artykuł wyjaśnia, jak skonfigurować pozycje i konta, aby korzystać z funkcji nierozliczonych przychodów w rozliczaniu subskrypcji.
author: JodiChristiansen
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: adf6f06ee454f368fa194315a87cfdec9e5e13da
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644176"
---
# <a name="unbilled-revenue"></a>Nierozliczony przychód

Ten artykuł opisuje funkcję nierozliczonych przychodów, która pozwala na uwzględnienie w bilansie kwot z całych harmonogramów rozliczeń. Kwoty te są uwzględnione na koncie przychodów nierozliczonych i koncie kompensacyjnym przychodów nierozliczonych, a umowa jest rozliczana w ratach.

## <a name="set-up-unbilled-revenue"></a>Konfiguracja nierozliczonego przychodu

Aby skonfigurować przychód nierozliczony, należy wykonać następujące czynności.

- Na stronie **Parametry rozliczania umów cyklicznych** ustaw pola w sekcji **Dochody nieobliczone**.
- Funkcja nierozliczonego przychodu może być używana dla pozycji, w których pole **Typ pozycji** jest ustawione na **Standard**. Można jej również używać dla elementów odroczonych. Aby używać nierozliczanych przychodów z funkcjonalnością krótkoterminową, skonfiguruj opcje krótkoterminowe na stronie **Parametry rozliczania umów cyklicznych**.

Aby skonfigurować elementy z przychodem nierozliczonym, należy wykonać następujące czynności.

1. Na stronie **Ustawianie przychodów nierozliczonych**, w zakładce **Przedmioty** wybierz **Dodaj**.
2. W nowym wierszu w opcji **Kod towaru** wybierz kod towaru.
3. W polu **Relacja produktu** wybierz numer relacji.
4. Powtórz te kroki, aby dodać więcej linii.
5. Wybierz opcję **Zapisz**.

Aby skonfigurować pozycje i konta nierozliczonych przychodów, wykonaj poniższe kroki.

1. Na stronie **Ustawianie przychodów nierozliczonych**, w zakładce **Konta** wybierz **Dodaj**.
2. W nowym wierszu w opcji **Kod towaru** wybierz kod towaru.
3. W polu **Relacja produktu** wybierz numer relacji.
4. Wybierz konta, na które będą naliczane przychody nierozliczone, rabaty niefakturowane i kompensaty nierozliczonych przychodów. Aby korzystać z kont krótkoterminowych, musisz ustawić pole **Metoda rozliczania krótkoterminowego** na **Okresy nieprzerwanej dostępności** lub **Stały rok** na stronie **Parametry rozliczania umów cyklicznych**.
5. Powtórz te kroki, aby dodać więcej linii.
6. Wybierz opcję **Zapisz**.

## <a name="use-unbilled-revenue"></a>Wykorzystanie nierozliczonych przychodów

1. Na stronie **Wszystkie harmonogramy fakturowania** utwórz harmonogram rozliczeniowy.
2. Jeśli pozycja nie jest jeszcze skonfigurowana do korzystania z niefakturowanych przychodów, zaznacz pole wyboru **Dochody nierozliczone** w linii harmonogramu rozliczeń.
3. W opcji **Przychody nierozliczone** zaznacz wartość **Tak**. Następnie przejrzyj i edytuj konta nierozliczonych przychodów, rabatów i kompensacji niefakturowanych przychodów, zgodnie z potrzebami.
4. Na planie rozliczeń w sekcji **Obsługa przychodów nierozliczonych** wybierz opcję **Utwórz wpis w arkuszu**, aby utworzyć początkowy wpis w arkuszu dla przychodów nierozliczonych. Ten krok musi zostać wykonany przed wystawieniem faktury za harmonogram rozliczeniowy.
5. Po utworzeniu pierwszego wpisu w arkuszu wybierz **Generuj faktury**, aby utworzyć zamówienia sprzedaży i zaksięgować faktury dla harmonogramów rozliczeń.
6. Po zaksięgowaniu faktur możesz przejrzeć informacje o audycie w zakładce **Przedłużenia** na stronie **Wszystkie harmonogramy rozliczeń**.

### <a name="milestone-billing"></a>Fakturowanie etapowe

Fakturowanie etapowe działa z nierozliczonymi przychodami pod następującymi warunkami:

- Jeśli pozycja nadrzędna fakturowania etapowego jest nierozliczona (pole wyboru **Przychody nierozliczone** jest zaznaczone), a pozycje podrzędne są rozliczone (pole wyboru **Przychody nierozliczone** jest odznaczone), należy określić datę początkową i końcową dla pozycji nadrzędnej. Daty te są wykorzystywane do utworzenia pierwszego wpisu w arkuszu.
- Jeśli pozycja nadrzędna fakturowania etapowego jest nierozliczona (pole wyboru **Przychody nierozliczone** nie jest zaznaczone), a pozycje podrzędne są rozliczone (pole wyboru **Przychody nierozliczone** jest zaznaczone), data końcowa musi być określona tylko dla tych pozycji podrzędnych, dla których chcesz utworzyć początkowy wpis w arkuszu.

Każdy element podrzędny etapu można przetwarzać osobno. Daty końcowe można określić po utworzeniu wstępnego wpisu w arkuszu.

> [!NOTE]
> Jeśli dla pozycji nadrzędnej lub podrzędnej etapu został już utworzony pierwotny wpis w arkuszu lub została utworzona faktura, daty rozpoczęcia i zakończenia nie mogą być edytowane.

### <a name="unbilled-revenue-with-straight-line-deferrals"></a>Przychody nierozliczone z odroczeniem liniowym

Aby wykorzystać nierozliczone przychody z liniowymi harmonogramami odroczeń, wykonaj poniższe kroki.

1. Na stronie **Wszystkie harmonogramy fakturowania** utwórz harmonogram rozliczeniowy.
2. Dodaj pozycję do wiersza harmonogramu rozliczeń.
3. Wybierz **Odroczenia** dla wiersza.
4. Na stronie **Odroczenia transakcji** wykonaj następujące kroki:

    1. Ustaw wartość opcji **Odroczenia** na **Tak**.
    2. W razie potrzeby zmień konta.
    3. W sekcji **Harmonogram** wybierz opcję **Linia** i w wymaganych wartościach dokonaj edycji.
    4. Kliknij przycisk **OK**.

5. Zaznacz pole **Nierozliczony przychód** dla wiersza, a następnie wykonaj następujące czynności:

    1. W opcji **Przychody nierozliczone** zaznacz wartość **Tak**.
    2. Wybierz konta, które mają być używane dla przychodów, rabatów i kompensat przychodów.

6. Na planie rozliczeń, w sekcji **Obsługa przychodów nierozliczonych** wybierz opcję **Utwórz wpis w arkuszu**. Alternatywnie możesz użyć strony **Obsługa masowa przychodów nierozliczonych**, aby utworzyć w arkuszu.
7. Harmonogram odroczeń zostaje utworzony. Szczegóły możesz przejrzeć na stronie **Wszystkie harmonogramy odroczeń**. Po utworzeniu harmonogramu odroczeń możesz edytować różne wartości dla pozycji harmonogramu rozliczeń. Na przykład możesz edytować cenę jednostkową, ilość lub daty.

### <a name="unbilled-revenue-with-event-based-deferrals"></a>Przychody nierozliczone z odroczeniami opartymi na zdarzeniach

Aby wykorzystać nierozliczone harmonogramy odroczeń z przychodów opartych na wydarzeniach, wykonaj poniższe kroki.

1. Na stronie **Wszystkie harmonogramy fakturowania** utwórz harmonogram rozliczeniowy.
2. Dodaj pozycję do wiersza harmonogramu rozliczeń.
3. Wybierz **Odroczenia** dla wiersza.
4. Na stronie **Odroczenia transakcji** wykonaj następujące kroki:

    1. Ustaw wartość opcji **Odroczenia** na **Tak**.
    2. W razie potrzeby zmień konta.
    3. W sekcji **Harmonogram** wybierz pozycję **Oparte na wydarzeniu**, **Szablon**, **Typ alokacji** i **Konto wygaśnięcia**.
    4. Kliknij przycisk **OK**.

5. Zaznacz pole **Nierozliczony przychód** dla wiersza, a następnie wykonaj następujące czynności:

    - W opcji **Przychody nierozliczone** zaznacz wartość **Tak**.
    - Wybierz konta, które mają być używane dla przychodów, rabatów i kompensat przychodów.

6. Na planie rozliczeń, w sekcji **Obsługa przychodów nierozliczonych** wybierz opcję **Utwórz wpis w arkuszu**. Alternatywnie możesz użyć strony **Obsługa masowa przychodów nierozliczonych**, aby utworzyć w arkuszu.
7. Harmonogram odroczeń zostaje utworzony. Szczegóły możesz przejrzeć na stronie **Wszystkie harmonogramy odroczeń**. Po utworzeniu harmonogramu odroczeń możesz edytować różne wartości dla pozycji harmonogramu rozliczeń. Na przykład możesz edytować cenę jednostkową, ilość lub daty. Harmonogram odroczeń jest ponownie obliczany na podstawie nowych wartości.

Rozkłady są przeliczane na podstawie wybranego typu alokacji (**Procent**, **Procentowe uzupełnienie** lub **Równe kwoty**). W przypadku typu alokacji **Kwoty zmienne** podział jest przeliczany na podstawie procentowego odpowiednika wartości początkowej zdarzenia. Na przykład, pierwotna cena jednostkowa wynosi 100,00 $, a procent wartości początkowej to 55,00 $ (55%). Jeśli cena jednostkowa zostanie zmieniona na 200,00 $, kwota zmienna wydarzenia wyniesie 110,00 $ (nadal 55%).

> [!NOTE]
> Jeśli linie harmonogramu odroczeń zostały rozpoznane, pozycja harmonogramu rozliczeń nie może być edytowana. Aby edytować pozycję liniową, musisz najpierw odwrócić rozpoznane linie. Następnie można zaktualizować linię harmonogramu rozliczeń.

### <a name="unbilled-revenue-and-top-billing"></a>Niewyliczone przychody i rozliczenia z góry

Harmonogram rozliczeń jest wprowadzany na trzy lata, a faktury są rozliczane co roku przez okres trzech lat. Cała kwota kontraktu jest zapisywana na koncie niefakturowanych przychodów, z którego co roku tworzone są faktury. Kontem przeciwstawnym jest konto przychodów lub konto przychodów przyszłych okresów.

Rozliczenia z góry i przychody nierozliczone nie działają razem, ponieważ w księdze głównej mogą pojawić się problemy z uzgodnieniem. Na przykład na stronie **Ustawianie grupy elementów** grupa elementów A jest ustawiona tak, że pole **Liczba górnych wierszy** jest ustawione na **2**. Na stronie **Harmonogramy rozliczeń** dodano trzy elementy. Wszystkie trzy pozycje należą do grupy pozycji A. Kiedy tworzony jest pierwszy wpis w arkuszu dla funkcji przychodów niefakturowanych, kwota dla wszystkich trzech pozycji jest przetwarzana na konto niefakturowane. Kiedy tworzona jest faktura dla harmonogramu rozliczeń, uwzględniane są tylko kwoty dla dwóch pierwszych pozycji. Dlatego kwota na fakturze nie zgadza się z kwotą, która została zaksięgowana na koncie nierozliczonych przychodów, a w księdze głównej pojawiają się problemy z uzgodnieniem.

Jeśli chcesz używać nierozliczonych przychodów, pozostaw stronę **Ustawienia grupy artykułów** pustą lub ustaw wszystkie grupy artykułów tak, by pole **Liczba górnych linii** było ustawione na **0** (zero). Jeśli chcesz korzystać z rozliczenia górnego, nie są dostępne żadne akcje związane z nierozliczonymi przychodami.

### <a name="examples"></a>Przykłady

Od wersji 10.0.29 do parametrów rozliczania umowy cyklicznej jest dodawany nowy parametr. Jeśli ustawiono wartość Tak, parametr **Użyj nierozliczonych kont przeciwstawnych** włącza dwa nowe konta w **Ustawieniach nierozliczonych przychodów**. Stają się dostępne Konta przeciwstawne nierozliczonego przychodu i Konta przeciwstawne nierozliczonego rabatu i najlepiej używać ich w przypadku tworzenia harmonogramów rozliczania w walucie innej niż waluta rozliczeniowa. Używanie kont przeciwstawnych zapewnia, że konta nierozliczonych przychodów i nierozliczonych rabatów zostały wycofane przy użyciu tych samych kursów wymiany co ich początkowe wpisy. Początkowy proces **Utwórz wpis w arkuszu** jest taki sam, jak w przypadku debetu dla nierozliczonego przychodu i kredytu do przychodu. W przypadku korzystania z rabatu początkowy wpis w arkuszu jest taki sam, jak w przypadku debetu do rabatu i kredytu dla nierozliczonego rabatu. 

Ten przykład pokazuje, jak wykorzystać nierozliczone przychody, aby całą kwotę kontraktu ująć w bilansie jako niezafakturowane przychody. Drugą stroną tego wpisu jest przychód lub odroczony przychód. Kiedy wystawiasz klientowi fakturę, przychody nierozliczone są odwrócone. Ujęcie przychodów nastąpi albo w momencie wystawienia faktury, albo zgodnie z ustalonym harmonogramem odroczenia.

#### <a name="assumptions"></a>Założenia

- 1 stycznia bieżącego roku klient podpisuje trzyletnią umowę na kwotę 390 dolarów.
- Umowa obejmuje dwie części: licencje i umowę serwisową.
- Cena sprzedaży licencji wynosi 300 dolarów, a klient otrzyma fakturę na 100 dolarów 1 stycznia każdego roku obowiązywania umowy. Opłata licencyjna w wysokości 300 dolarów zostanie ujęta jako przychód w momencie podpisania umowy.
- Cena sprzedaży opłaty za utrzymanie wynosi 90 dolarów, a klient otrzymuje fakturę na kwotę 30 dolarów 1 stycznia każdego roku obowiązywania umowy. Opłata eksploatacyjna w wysokości 90 dolarów zostanie odroczona, a 2,50 dolara będzie uznawane co miesiąc przez cały okres trwania umowy.
- Klient otrzyma fakturę na 130 dolarów na początku (1 stycznia) każdego z trzech lat trwania umowy.

#### <a name="steps"></a>Kroki

1. Ustaw dwie zwolnione pozycje jako pozycje nierozliczone. Użyj strony **Ustawienie przychodów nierozliczonych**, aby skonfigurować pozycje i konta, które korzystają z przychodów nierozliczonych.
2. W tym przykładzie opłata za utrzymanie jest odroczona. Ten element wymaga szablonu odroczenia, który jest ustawiany na stronie **Szablony odroczeń**. Szablon ma częstotliwość okresu **Miesięcznie** i długość okresu rozpoznania 36 miesięcy. Dlatego przychód miesięczny wynosi 2,50 $.
3. Na stronie **Przedmioty domyślnie odroczone** ustaw pole **Opłata za utrzymanie** na **Przedmioty odroczone**. Ten i następny krok spowodują, że pozycja opłaty za utrzymanie zostanie odroczona, gdy zostanie sprzedana lub włączona do harmonogramu rozliczeń.
4. Wybierz **Ustawienia domyślne odraczania** \> **Szablon** i dodaj pozycję dla opłaty za utrzymanie oraz szablon liniowy z kroku 2. Pozycja dotycząca opłaty za utrzymanie będzie powiązana z 36-miesięcznym harmonogramem odroczeń.
5. Utwórz harmonogram rozliczeń, który uwzględnia dwie nieobliczone pozycje. Harmonogram rozliczeń dla kontraktu zawiera następujące pozycje.

    | Pozycja | Data początkowa | Data końcowa | Ilość | Częstotliwość rozliczania | Element odroczony | Nierozliczony przychód | Opis |
    |---|---|---|---|---|---|---|---|
    | Licencja | 01 stycznia 2022 r. | 31 grudnia 2024 r. | 100,00 $ | Co rok | Nr | Tak | Każdego roku klient otrzyma fakturę na kwotę 100,00 dolarów. Suma 300,00 dolarów zostanie zaksięgowana z góry jako niefakturowany przychód w bilansie oraz jako przychód w rachunku zysków i strat. Każda faktura zmniejsza kwotę niezafakturowaną. |
    | Konserwacja | 01 stycznia 2022 r. | 31 grudnia 2024 r. | 30,00 $ | Co rok | Tak | Tak | Każdego roku klient otrzyma fakturę na kwotę 30,00 dolarów. Suma 90,00 dolarów zostanie z góry zaksięgowana w bilansie jako nierozliczone przychody i przychody przyszłych okresów. Każda faktura zmniejsza kwotę niezafakturowaną. Odroczony przychód będzie rozpoznawany co miesiąc przez 36 miesięcy. |

6. Na stronie **Wszystkie harmonogramy rozliczeń** użyj procesu **Utwórz wpis w arkuszu**, aby zaksięgować wartość kontraktu w bilansie jako nierozliczony przychód.

Tworzone są dwa wpisy do dziennika, po jednym dla każdej linii w harmonogramie rozliczeń.

| Konto | Kwota debetu | Kwota kredytu |
|---|---|---|
| Konto nierozliczonego przychodu | 300,00 $ | |
| Konto przychodów | | 300,00 $ |

| Konto | Kwota debetu | Kwota kredytu |
|---|---|---|
| Konto nierozliczonego przychodu | 90,00 $ | |
| Odroczony przychód | | 90,00 $ |

Umowa wymaga, by faktura dla klienta była tworzona na początku każdego roku. Aby utworzyć fakturę, użyj procesu **Generuj fakturę**. Po utworzeniu faktury, jest fakturowany następujący załącznik faktury.

| Konto| Kwota debetu | Kwota kredytu |
|---|---|---|
| Konto nierozliczonego przychodu | | 130,00 USD |
| Rozrachunki z odbiorcami | 130,00 USD | |

Ten sam wpis w arkuszu zostanie utworzony na podstawie faktur, które zostaną zaksięgowane na początku kolejnych dwóch lat. W trakcie procesu **Generuj fakturę** konto Przychody nierozliczone jest zmniejszane każdego roku. Konto przeciwstawne nierozliczone przychody służy do równoważenia konta przychodów nierozliczonych, gdy są używane różne kursy wymiany. 

W ostatnim kroku co miesiąc tworzony jest wpis w arkuszu ujmujący przychody z tytułu odroczonego przychodu z opłaty eksploatacyjnej. Wpis w arkuszu można utworzyć za pomocą strony **Opracowanie rozpoznania**. Alternatywnie można ją utworzyć, wybierając opcję **Rozpoznaj** dla linii na stronach **Rozkład odroczeń**.

| Konto główne | Kwota debetu | Kwota kredytu |
|---|---|---|
| Odroczony przychód | 2,50 $ | |
| Przychód | | 2,50 $ |

Ten wpis w arkuszu zostanie utworzony za każdym razem, gdy proces uznawania zostanie uruchomiony dla tej pozycji rozliczeń międzyokresowych (w sumie 36 razy).

#### <a name="short-term-fixed-year"></a>Krótkoterminowe: stały rok

Możesz używać niefakturowanego przychodu razem z funkcją krótkoterminową, ustawiając pole **Krótkoterminowy nierozliczony** na stronie **Parametry rozliczania umów cyklicznych**. Poniższy przykład pokazuje obliczenia, które są wykonywane, gdy przychody niefakturowane są używane razem z metodą **Stały rok** krótkoterminowych przychodów niefakturowanych.

Zostanie utworzony harmonogram rozliczeń spełniający następujące kryteria:

- **Data rozpoczęcia:** 1 czerwca 2020 r.
- **Data końcowa:** 31 grudnia 2021 r.
- **Cena jednostkowa:** 100 $
- **Częstotliwość:** Miesięczna

Na stronie **Wszystkie harmonogramy rozliczeń** początkowy wpis w arkuszu jest tworzony przez proces **Utwórz wpis w arkuszu**. Bieżące kwoty krótkoterminowe i długoterminowe są obliczane w następujący sposób:

- **Bieżąca nierozliczona kwota krótkoterminowa przychodu:** 700 $
- **Bieżąca długoterminowa nierozliczona kwota przychodu:** 1200 $

Faktura jest tworzona za okres rozliczeniowy od 1 czerwca 2020 roku do 30 listopada 2020 roku. Bieżące kwoty krótkoterminowe i długoterminowe są obliczane w następujący sposób:

- **Bieżąca nierozliczona kwota krótkoterminowa przychodu:** 100 $
- **Bieżąca długoterminowa nierozliczona kwota przychodu:** 1200 $

Faktura jest tworzona za okres rozliczeniowy od 1 grudnia 2020 roku do 31 grudnia 2020 roku. Bieżące kwoty krótkoterminowe i długoterminowe są obliczane w następujący sposób:

- **Bieżąca nierozliczona kwota krótkoterminowa przychodu:** 1,200 $
- **Bieżąca długoterminowa nierozliczona kwota przychodu:** 0 $

#### <a name="short-term-rolling-periods"></a>Krótkoterminowe: Okresy nieprzerwanej dostępności

Możesz używać niefakturowanego przychodu razem z funkcją krótkoterminową, ustawiając metodę Krótkoterminowy nierozliczony na stronie **Parametry rozliczania umów cyklicznych**. Poniższy przykład pokazuje obliczenia, które są wykonywane, gdy przychody niefakturowane są używane razem z metodą **Okresy nieprzerwanej dostępności** krótkoterminowych przychodów niefakturowanych.

Zostanie utworzony harmonogram rozliczeń spełniający następujące kryteria:

- **Data rozpoczęcia:** 1 czerwca 2020 r.
- **Data końcowa:** 31 grudnia 2021 r.
- **Cena jednostkowa:** 100 $
- **Częstotliwość:** Miesięczna

Na stronie **Wszystkie harmonogramy rozliczeń** początkowy wpis w arkuszu jest tworzony przez proces **Utwórz wpis w arkuszu**. Bieżące kwoty krótkoterminowe i długoterminowe są obliczane w następujący sposób:

- **Bieżąca nierozliczona kwota krótkoterminowa przychodu:** 1,200 $
- **Bieżąca długoterminowa nierozliczona kwota przychodu:** 700 $

Faktura jest tworzona za okres rozliczeniowy od 1 czerwca 2020 roku do 30 listopada 2020 roku. Bieżące kwoty krótkoterminowe i długoterminowe są obliczane w następujący sposób:

- **Bieżąca nierozliczona kwota krótkoterminowa przychodu:** 1,200 $
- **Bieżąca długoterminowa nierozliczona kwota przychodu:** 100 $

Faktura jest tworzona za okres rozliczeniowy od 1 grudnia 2020 roku do 31 grudnia 2020 roku. Bieżące kwoty krótkoterminowe i długoterminowe są obliczane w następujący sposób:

- **Bieżąca nierozliczona kwota krótkoterminowa przychodu:** 1,200 $
- **Bieżąca długoterminowa nierozliczona kwota przychodu:** 0 $

### <a name="items-with-revenue-allocation"></a>Pozycje z przypisanym dochodem

Dwie pozycje, które mają różną częstotliwość rozliczeń, są dodane do harmonogramu rozliczeń. Oba wykorzystują niefakturowane przychody i są pozycjami, które można odroczyć.

- **Artykuł nr 1000:** Surface Pro 128 GB

    - **Częstotliwość rozliczania:** Jednorazowo
    - **Cena jednostkowa:** 1500 $
    - **Autonomiczna cena sprzedaży:** 1600 $
    - **Przychód z umowy:** 1465,26 $

- **Przedmiot nr S0021:** Ubezpieczenie sprzedawane razem z przedmiotem nr 1000

    - **Częstotliwość fakturowania:** miesięcznie przez 12 miesięcy
    - **Cena na jednostkę:** 20 $ na miesiąc
    - **Autonomiczna cena sprzedaży:** 25 $
    - **Przychód z umowy:** 264,74 $

Ponieważ obie pozycje korzystają z niefakturowanych przychodów i alokacji przychodów, całkowita kwota kontraktu w linii odnowienia wynosi 0 (zero). Kolumna **Dochody z umowy** zostaje dodana i pokazuje kwotę dochodów z umowy.

Poniższa tabela przedstawia początkowy wpis w arkuszu dotyczący pozycji i faktury.

| Konto główne | Kwota debetu | Kwota kredytu |
|---|---|---|
| **Pozycja 1000 wpis w arkuszu** | | | 
| Konto nierozliczonego przychodu (401250) | 1465,26 $ | |
| Konto odroczonego przychodu (250600) | | 1465,26 $ |
| **Pozycja 0021 wpis w arkuszu** | | | 
| Konto nierozliczonego przychodu (401250) | 274,74 $ | |
| Konto odroczonego przychodu (250600) | | 274,74 $ |
| **Faktura VAT** | | |
| Konto nierozliczonego przychodu | | 1465,26 $ |
| Konto nierozliczonego przychodu | | 274,74 $ |
| Konto rzeczywistości rozszerzonej (130100) | 1488,16 $ | |

#### <a name="changes-to-the-billing-schedule-line-billing-detail-line-or-revenue-allocation"></a>Zmiany w linii harmonogramu rozliczeń, linii szczegółów rozliczeń lub alokacji dochodu

Kiedy cena jednostkowa lub ilość ulegają zmianie, należy zaktualizować kwotę przychodu z umowy dla każdej pozycji, która jest częścią podziału przychodu. Dlatego wpis w dzienniku jest przeliczany na nowo.

Na przykład cena jednostkowa elementu 1000 została zmieniona z 1500 na 1600 dolarów. W tym przypadku kwota przychodu z umowy zostanie automatycznie przeliczona na 1549,47 $. Przychód z umowy dla pozycji S0021 został przeliczony na 290,53 $.

Kiedy zmiana zostaje potwierdzona i zatwierdzona, początkowe zapisy w dzienniku dla obu pozycji zostają odwrócone i tworzone są nowe zapisy w dzienniku:

- **Pozycja 1000:** Pierwotny wpis w dzienniku w wysokości 1465,26 $ zostaje odwrócony. Tworzony jest nowy wpis w arkuszu na kwotę 1549,47 $.
- **Pozycja S0021:** Pierwotny wpis w dzienniku w wysokości 274,74 $ zostaje odwrócony. Tworzony jest nowy wpis w arkuszu na kwotę 290,53 $.

#### <a name="termination"></a>Przerwanie

Pozycja S0021 ma datę rozpoczęcia w styczniu 2020 roku i datę zakończenia w grudniu 2020 roku, ale kończy się w czerwcu 2020 roku. Kwota dochodu z umowy dla obu pozycji musi zostać ponownie obliczona:

- **Pozycja 1000:** Przychód z umowy dla pozycji został przeliczony na 1567,67 $.
- **Pozycja S0021:** Przychód z umowy dla pozycji został przeliczony na 124,00 $.

Dla linii, która została przerwana, tworzony jest wpis w arkuszu korekt. Wpis w arkuszu dla linii, która należy do tego samego numeru układu wielu elementów (MEA), jest odwracany i tworzony jest nowy wpis w arkuszu:

- **Pozycja 1000:** Pierwotny wpis w dzienniku w wysokości 1465,26 $ zostaje odwrócony. Tworzony jest wpis wpis w arkuszu korekty na kwotę 1549,47 $.
- **Pozycja S0021:** Pierwotny wpis w dzienniku w wysokości 274,74 $ zostaje odwrócony. Tworzony jest nowy wpis w arkuszu na kwotę 124,00 $.
