---
title: Raporty wartości zapasów
description: W tym temacie wyjaśniono, jak konfigurować, generować i używać raportów wartości zapasów. Te raporty zawierają szczegółowe informacje dotyczące ilości i kwot fizycznych oraz finansowych zapasów.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3da92c384d3074335067433120eccc97d11b6b81
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103947"
---
# <a name="inventory-value-reports"></a>Raporty wartości zapasów

[!include [banner](../includes/banner.md)]

Raporty wartości zapasów zawierają szczegółowe informacje dotyczące ilości i kwot fizycznych oraz finansowych zapasów. Raporty można przeglądać na wiele sposobów. Można na przykład wyświetlać sumy lub transakcje albo filtrować według towarów lub przedziału czasu. Można wyświetlać koszt własny sprzedaży (KSZ) lub praca w toku (PWT) i ustawiać inne opcje.

Raporty wartości zapasów pozwalają wykonać następujące zadania:

- Czy uzgadniać między księgą główną a zapasami.
- Skonsultuj się z dostępnymi zapasami i wartościami dla określonego okresu.
- Umożliwia tworzenie konfiguracji raportów dostosowanych do określonego celu.
- Zapisz konfiguracje raportów, aby można było ich używać wielokrotnie.
- Umożliwia dodawanie zakresów do filtru danych po uruchomieniu raportu.

## <a name="types-of-inventory-value-report"></a>Rodzaje raportu o wartości zapasów

Istnieją dwa typy raportów o wartości zapasów: **Wartość zapasów** (raport standardowy) i **Magazyn raportu wartości zapasów**.

### <a name="standard-inventory-value-report"></a>Standardowy raport wartości zapasów

Standardowy raport **wartości zapasów** to prosty raport, który umożliwia wybór uwzględnionych informacji, a następnie wyświetlanie tych informacji na ekranie. Wyniki nie zostaną zapisze. Nie dostarcza także interakcyjnych funkcji filtrowania, przechodzenia do dół, przeglądania lub eksportowania. Z tych powodów zaleca się w większości przypadków korzystanie z **raportu magazynowego Raport wartości zapasów**.

### <a name="inventory-value-report-storage-report"></a>Raport dotyczący przechowywania raportu wartości zapasów

Raport **Przechowywanie raportów wartości zapasów** zapewnia dane wyjściowe jako interaktywna strona w Microsoft Dynamics 365 Supply Chain Management lub jako wyeksportowany dokument w jednym z kilku formatów

Podczas wyświetlania raportu w przeglądarce kolumny i salda zagregowane są dynamicznie dostosowywane w zależności od skonfigurowanego układu. Można posortować wyniki, przefiltrować je, przejść do kolejnych danych i wykonać inne zadania.

Wyniki raportu są przechowywane w jednostce danych **Wartości zapasów**. Można więc filtrować i eksportować wyniki do formatu, takiego jak wartości rozdzielane przecinkami (CSV) lub Microsoft Excel.

Raport **Przechowywanie raportu wartości zapasów** jest przydatny, gdy dane wyjściowe zawierają wiele wierszy. Na przykład pozycje 50 000 i 300 sklepów zostały utworzone jako magazyny. W takim przypadku, jeśli salda końcowe zapasów są żądane według towarów, oddziału i magazynu, produkcja będzie zawierała wiele wierszy.

> [!NOTE]
> Raport **Przechowywanie raportów wartości zapasów** nie zawiera sum częściowych zdefiniowanych w układzie raportu. Nie obejmuje również sald księgi głównej, nawet jeśli te salda są zdefiniowane w układzie raportu. Uzgodnienia księgi głównej należy wykonać przy użyciu bilansów próbnych. Jednak standardowy raport **wartości zapasów** zawiera te podsumy i salda.

## <a name="turn-the-inventory-value-report-storage-feature-on-or-off"></a>Włącz lub wyłącz funkcję przechowywania raportu o wartości zapasów

Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Przechowywanie raportu wartości zapasów* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="define-inventory-value-report-configurations"></a><a name="report-configuration"></a>Zdefiniuj konfiguracje raportu wartości zapasów

Strona **Raporty wartości zapasów** zawiera informacje o zawartości zawartej w raporcie o różnych typach wartości zapasów. Można zdefiniować dowolną liczbę typów raportów. Po każdym wygenerowaniu raportu wartości zapasów wybierany jest typ raportu.

1. Przejdź do pozycji **Zarządzanie kosztami \> Ustawienia zasad księgowania zapasów \> Raporty o wartości zapasów**.
1. Wykonaj jeden z następujących kroków:

    - Aby edytować istniejący raport, wybierz go w okienku listy, a następnie wybierz **Edytuj** w okienku akcji.
    - Aby utworzyć nowy raport, wybierz w okienku akcji wybierz opcję **Nowe**.

1. W nagłówku nowego lub wybranego raportu ustaw następujące pola:

    - **Identyfikator** – Umożliwia wprowadzenie identyfikatora wiersza raportu. Ta wartość musi być unikatowa wśród wszystkich konfiguracji raportu wartości zapasów. Nie można go edytować po zapisaniu nowej konfiguracji.
    - **Nazwa** — Wprowadzić nazwę opisową dla raportu.

1. Jeśli tworzysz nową konfigurację raportu, wybierz przycisk **Zapisz** w okienku akcji, aby udostępnić pozostałe pola.
1. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - **Interwał dat** — umożliwia wybór wstępnie zdefiniowanego interwału dat Po uruchomieniu raportu ten interwał dat można zastąpić.
    - **Zakres** — umożliwia wybranie *daty księgowania* lub *czasu transakcji* w zależności od daty i czasu, która powinna być używana podczas pobierania rekordów dla raportu.
    - **Zestaw wymiarów** — umożliwia wybór zestawu wymiarów, dla których mają być uruchamiane dane (Wymiary są zdefiniowane w księdze głównej) Na przykład można uruchomić dane dla *konta głównego* lub *konta głównego + jednostka biznesowa*. Wybierany zestaw wymiarów nie może mieć więcej niż dwóch wymiarów. Aby uzyskać więcej informacji, zobacz [Zestawy wymiarów finansowych](../../finance/general-ledger/financial-dimension-sets.md).

1. Na skróconej karcie **Kolumny** ustaw następujące pola. Pola te kontrolują kolumny, które zawierają raport, oraz typy danych zawarte w tych kolumnach.

    - **Zapasy** — tę opcję należy ustawić na wartość *Tak*, aby wyświetlić wartości zapasów Następnie te wartości można uzgodnić z saldami konta księgi głównej.
    - **PWT** — tę opcję należy ustawić na wartość *Tak*, aby wyświetlić wartości PWT. Następnie można uzgodnić te wartości z saldami kont PWT w księdze głównej. W przypadku ustawienia tej opcji na wartość *Tak*, raport będzie wyświetlał tylko ilości i ilości fizyczne zapasów o stanie PWT Zlecenia produkcyjne o stanie PWT zostały odebrane lub zgłoszone jako zakończone, ale nie zostały zakończone.
    - **Odroczony COGS** – Ustaw dla tej opcji wartość *Tak*, aby wyświetlić kolumnę, która pokazuje fizyczne ilości i ilości zapasów dla odroczonego COGS. Odroczony KWS jest pokazywany przy użyciu fizycznych ilości i kwot, ponieważ jest przeciwstawny do ilości i kwot dokumentów dostawy.
    - **Odroczony KWS** – Ustaw dla tej opcji wartość *Tak*, aby wyświetlić kolumnę, która pokazuje finansowe ilości i ilości zapasów dla odroczonego KWS. KWS jest pokazywana przy użyciu ilości i kwot finansowych, ponieważ kompensuje ilości i kwoty faktury.
    - **Zysk i strata** — ustaw tę opcję na *Tak*, aby wyświetlić kolumnę zawierającą kwotę finansową, która została zaksięgowana na kontach zysków i strat dla zapasów.
    - **Drukuj skumulowane wartości konta dla porównania** — ustaw tę opcję na wartość *Tak*, aby wyświetlić kolumnę, która pokazuje saldo konta księgi głównej. W ten sposób nie będzie trzeba sprawdzać salda końcowego. Ta opcja działa tylko w przypadku standardowego raportu **Wartości zapasów**, a nie raportu **magazynowego raportu Wartości zapasów**. Po ustawieniu tej opcji na wartość *Tak*, należy użyć następujących pól w celu określenia każdego konta księgi głównej, które ma być uwzględnione w liście, w zależności od włączonych opcji **sytuacji finansowych**.

        > [!NOTE]
        > W przypadku wybrania konta *sum* dla dowolnego z tych pól zostanie wyświetlone zarówno kwota z każdego konta magazynowego uwzględnionego w koncie sum, jak i kwota konta sum.

        - **Konto magazynowe** — umożliwia określenie konta księgi głównej, dla których mają być wyświetlane informacje o zapasach (Obie strony: **Opcja Zapasy** i Opcja **Drukuj skumulowane wartości kont do porównania** muszą mieć wartość *Tak*.)
        - **Konto PWT** — umożliwia określenie konta księgi głównej, dla których mają być wyświetlane informacje o PWT. (Obie strony: **Opcja PWT** i Opcja **Drukuj skumulowane wartości kont do porównania** muszą mieć wartość *Tak*.)
        - **Odroczone konto KWS** — umożliwia określenie konta księgi głównej, dla których mają być wyświetlane informacje o KWS. (Obie strony: **Odroczone COGS** i Opcja **Drukuj skumulowane wartości kont do porównania** muszą mieć wartość *Tak*.)
        - **Konto KWS** — umożliwia określenie konta księgi głównej, dla których mają być wyświetlane informacje o KWS. (Obie strony: **Opcja KWS** i Opcja **Drukuj skumulowane wartości kont do porównania** muszą mieć wartość *Tak*.)

    - **Zsumuj wartości fizyczne i finansowe** — dla tej opcji ustaw wartość *Tak*, aby wyświetlić kolumnę zawierającą całkowitą ilość zapasów i kwotę zapasów (podsumowanie wartości fizycznych i finansowych zapasów). Jeśli ta opcja ma wartość *Nie*, raport będzie zawierał wartości zarówno fizyczne, jak i finansowe zapasów.
    - **Uwzględnij nie zaksięgowane w księdze**. Ta opcja ma wartość *Tak*, aby wyświetlić kolumnę zawierającą transakcje, które nigdy nie zostały zaksięgowane w księdze głównej. W księdze głównej mogą nie być księgowane transakcje następujących typów towarów:

        - Towary odebrane, ale jeszcze nie zafakturowane, jeśli opcja **Księguj magazyn fizyczny** jest wyczyszczana dla odpowiedniej grupy modeli pozycji.
        - Pozycje otrzymane i jeszcze nie zafakturowane, gdy opcja **Prześlij paragon produktu w księdze** jest wyczyszczona na **Pokwitowaniu produktu** Skróconej karcie na karcie **Ogólne** w **Parametry dotyczące kont z dostawcami** (**Rachunki z dostawcami \> Ustawienia \> Parametry kont z dostawcami**).

    - **Oblicz średni koszt jednostkowy** – Ustaw dla tej opcji wartość *Tak*, aby wyświetlić kolumnę zawierającą średni koszt jednostkowy. Średni koszt jednostkowy to łączna ilość podzielona przez łączną kwotę.
    - **Całkowita ilość i wartość** — Ustaw tę opcję na *Tak*, aby wyświetlić kolumny, które pokazują łączną ilość inwentarza z natury (i ilości finansowe) oraz łączną ilość inwentarza z natury (i kwoty finansowe). Tę opcję można ustawiać na *Tak* tylko wtedy, gdy wartość opcji **Podsumuj wartości fizyczne i finansowe** jest ustawiona na *Nie*.
    - **Wymiary magazynowe** — w tej siatce zaznacz pole wyboru **Widok** dla każdego wymiaru, który ma być pokazywany w raporcie. Wartości w raporcie będą wyświetlane tylko dla wymiarów, dla których jest włączona opcja **Magazyn finansowy**. W innych wymiarach będą wyświetlane tylko puste kolumny. Dla wymiarów wybranych do pokazania można zaznaczyć pole wyboru **Suma**, aby uwzględnić także sumy.
    - **Identyfikator zasobu** – w opcji **Widok** ustaw wartość *Tak*, aby wyświetlić kolumnę identyfikującą pozycję dla każdego wiersza. Ustaw dla **opcji Suma** wartość *Tak*, aby również uwzględnić sumy. W zależności od typu towaru wymienionego w każdym wierszu kolumna zawiera jeden z następujących typów informacji:

        - **Materiał** — kolumna zawiera wartość pola `ItemID` odpowiedniego rekordu materiału.
        - **Praca** — kolumna zawiera wartość pola `WorkCenterID` odpowiedniego rekordu pracy.
        - **Koszt pośredni** — kolumna zawiera wartość pola `CodeID` odpowiedniego rekordu kosztu pośredniego.

        Jeśli opcja **Widok** jest ustawiona wartość na *Nie* w polu **Identyfikator zasobu** i **Grupa zasobów**, jest dostępna tylko łączna wartość zapasów oparta na wybranych wymiarach magazynowych.

    - **Grupa zasobu** – w opcji **Widok** ustaw wartość *Tak*, aby wyświetlić kolumnę identyfikującą grupy zasobu dla każdego wiersza. Ustaw dla **opcji Suma** wartość *Tak*, aby również uwzględnić sumy. W zależności od typu towaru wymienionego w każdym wierszu kolumna zawiera jeden z następujących typów informacji:

        - **Materiał** — kolumna zawiera wartość pola `ItemGroup` odpowiedniego rekordu materiału.
        - **Praca** — kolumna zawiera wartość pola `WorkcenterGroup` odpowiedniego rekordu pracy.
        - **Koszt pośredni** — kolumna zawiera wartość pola `CostGroup` odpowiedniego rekordu kosztu pośredniego. (Wartość `CostGroupType` musi wynosić *Pośrednie*.)

        Jeśli opcja **Widok** jest ustawiona wartość na *Nie* w polu **Identyfikator zasobu** i **Grupa zasobów**, jest dostępna tylko łączna wartość zapasów oparta na wybranych wymiarach magazynowych.

1. Na skróconej karcie **Wiersze** ustaw następujące pola. Pola te umożliwiają dodawanie do raportu lub usuwanie odpowiednich podsekcji związanych z PWT.

    - **Materiał** — tę opcję należy ustawić na wartość *Tak*, aby wyświetlić informacje o materiałach. *Materiał* jest domyślnym typem zasobów, ponieważ materiały muszą być uwzględnione we wszystkich konfiguracjach raportów, aby zapewnić pewne wyjście.
    - **Robocizna** – Ustaw tę opcję na Wartość *Tak*, aby pokazać koszty robocizny dla PWT.
    - **Koszt pośredni** – Ustaw tę opcję na Wartość *Tak*, aby pokazać koszty pośredni dla PWT.
    - **Outsourcing bezpośredni** – Ustaw tę opcję na Wartość *Tak*, aby pokazać bezpośrednie koszty outsourcingu PWT. Informacje te są przydatne w przypadku podwykonawstwa.
    - **Poziom szczegółowości** — umożliwia wybór opcji wyświetlania raportu:

        - *Transakcje* — umożliwia wyświetlanie wszystkich odpowiednich transakcji w raporcie. Należy zauważyć, że mogą wystąpić problemy z wydajnością podczas wyświetlania raportów, które obejmują dużą liczbę transakcji. Dlatego, aby użyć tej opcji widoku, zaleca się użycie **raportu magazynowego o wartości zapasów**.
        - *Sumy* — umożliwia wyświetlenie sumy wyników.

    - **Uwzględnij saldo rozpoczęcia** – Ustaw dla tej opcji wartość *Tak*, aby wyświetlić saldo rozpoczęcia. Ta opcja jest dostępna tylko wtedy, gdy pole **Poziom szczegółów** jest ustawione na *Transakcje*.

## <a name="generate-an-inventory-value-report-storage-report"></a>Wygeneruj raport przechowywania raportu wartości zapasów

Wykonaj poniższe kroki, aby wygenerować i zapisać raport **Przechowywanie raportu wartości zapasów**:

1. Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Magazyn raportów wartości zapasów**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W oknie dialogowym **Wartość zapasów** na skróconej karcie **Parametry** ustaw następujące pola:

    - **Nazwa** — Wpisz unikalną nazwę raportu.
    - **Identyfikator** — umożliwia wybór [konfiguracji raportu wartości zapasów](#report-configuration), która będzie dla tego raportu. Konfiguracja ustala opcje dla kolumn i wierszy, które będą uwzględniane w raporcie.
    - **Interwał dat** — pola w tej sekcji określają, które rekordy będą uwzględniane w raporcie. Aby zdefiniować interwał dat, można wybrać wstępnie zdefiniowany zakres (w odniesieniu do daty generowania raportu) w polu **Kod zakresu dat** lub wybrać określone daty w polach **Od dnia** i **Do dnia**.

1. Na skróconej karcie **Rekordy do uwzględnienia** należy skonfigurować filtry i ograniczenia w celu zdefiniowania danych uwzględnionych w raporcie. Wybierz **Filtruj**, aby otworzyć standardowe okno dialogowe edytora zapytań, w którym możesz zdefiniować kryteria wyboru, kryteria sortowania i łączenia. Pola działają w ten sam sposób, jak działają w przypadku innych typów zapytań w module Supply Chain Management. Wszystkie te filtry będą stosowane do transakcji magazynowych, ale nie do salda księgi głównej. Podczas skonfigurowania filtrów należy pamiętać o tym zachowaniu. W przeciwnym razie może wystąpić rozbieżność między zapasami a księgą główną.
1. Na skróconej karcie **Uruchom w tle** określ sposób, kiedy i jak często generowany jest raport. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.

    > [!NOTE]
    > Ten raport jest zawsze wykonywany w ramach zadania wsadowego.

1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko dialogowe.

Po zakończeniu zadania wsadowego raport będzie wyświetlany na stronie **Magazyn raportów wartości zapasów**. W celu wyświetlenia zaktualizowanego raportu może być konieczne odświeżenie strony.

> [!IMPORTANT]
> W wybranej konfiguracji raportu wartości zapasów można uzyskać nieprawidłowe saldo rozpoczęcia, jeśli zostanie wybrana ta sama data w polu **Od dnia** i **Do dnia**, a także w przypadku ustawienia opcji **Uwzględnij saldo rozpoczęcia** na wartość *Tak*.

## <a name="explore-an-inventory-value-report-storage-report"></a>Zapoznaj się z raportem dotyczącym przechowywania raportu wartości zapasów

Po wygenerowaniu raportu można go przeglądać i eksplorować w dowolnym momencie wykonując następujące kroki:

1. Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Magazyn raportów wartości zapasów**.
1. Na liście wybierz raport. Na stronie pokazano szczegóły konfiguracji raportu [wartości zapasów](#report-configuration), która została użyta do wygenerowania wybranego raportu.
1. W okienku akcji wybierz opcję **Wyświetl szczegóły**, aby wyświetlić zawartość raportu.
1. Przeglądaj raport, wykonując następujące kroki:

    - Podobnie jak w przypadku większości standardowych formularzy w Supply Chain Management możesz wybrać niemal dowolny nagłówek kolumny, aby posortować lub przefiltrować siatkę według wartości w tej kolumnie.
    - Pole **Filtr** umożliwia filtrowanie raportu według dowolnej wartości w dowolnej z kilku dostępnych kolumn.
    - Aby zapisać i załadować Ulubione kombinacje opcji sortowania i filtrowania, należy skorzystać z menu Widok (powyżej pola **Filtr**).

## <a name="export-an-inventory-value-report-storage-report"></a>Eksportuj raport przechowywania raportu wartości zapasów

Każdy generowany raport jest przechowywany w jednostce danych **Wartości zapasów**. Za pomocą standardowych funkcji Supply Chain Management można eksportować dane z tej jednostki do dowolnego obsługiwanego formatu danych, w tym także do pliku CSV lub programu Excel.

W poniższym przykładzie przedstawiono sposób eksportowania raportu dotyczącego **Przechowywanie raportu wartości zapasów**.

1. Wybierz kolejno opcje **Administrowanie systemem \> Obszary robocze \> Zarządzanie danymi**.
1. W sekcji **Import/eksport** wybierz kafelek **Eksportuj**.
1. Na wyświetlonej stronie **Eksportuj**, zostanie skonfigurowane zadanie eksportowania. Najpierw wprowadź nazwę grupy dla zadania.
1. W sekcji **Wybrane jednostki** wybierz pozycję **Dodaj jednostkę**.
1. W wyświetlonym oknie dialogowym można ustawić następujące pola:

    - **Nazwa jednostki** — umożliwia wybór *Wartości zapasów*.
    - **Docelowy format danych** — umożliwia wybór formatu, do którego mają zostać wyeksportowane dane.

1. Wybierz przycisk **Dodaj**, aby dodać nowy wiersz, a następnie kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.
1. Zazwyczaj w danym momencie można eksportować jeden raport. Aby wyeksportować jeden raport, należy skonfigurować filtr dla wiersza dodanego właśnie do okna dialogowego **Zapytanie**. W ten sposób można określić, który Raport z jednostki **Wartość zapasów** będzie uwzględniony w eksporcie. Wykonaj następujące kroki, aby skonfigurować następujące opcje filtrowania i wyeksportować pojedynczy raport:

    1. Na karcie **Zakres** wybierz opcję **Dodaj**, aby dodać wiersz.
    2. W polu **Tabela** ustaw wartość *Wartość zapasów*.
    3. W polu **Tabela pochodna** ustaw wartość *Wartość zapasów*.
    4. Ustaw pole **Pole**, według którego ma być wykonywane filtrowanie. Zazwyczaj używane jest pole **Nazwa wykonania** i/lub pole **Czas wykonania**.
    5. W polu **Kryterium** należy określić wartość, która ma być wyszukiwana w wybranym polu. (Jeśli w poprzednim kroku zaznaczono pole **Nazwa wykonania**, ta wartość będzie nazwą raportu. Jeśli zaznaczono pole **Czas wykonania**, będzie to godzina wygenerowania raportu.)
    6. Dodaj wiersze na karcie **Zakres** w razie potrzeby, dopóki szukany raport nie zostanie jednoznacznie zidentyfikowany.

1. Wybierz przycisk **OK**, aby zapisać ustawienia i zamknąć okienko dialogowe.
1. Wybierz **Zapisz**, by zapisać ustawienia eksportu.
1. Otwórz kartę **Opcje eksportu** i wybierz pozycję **Eksportuj teraz**, aby wygenerować plik eksportu.
1. Zostanie otwarta strona **podsumowanie wykonania**, na której możesz zobaczyć stan zadania eksportowania oraz listę wyeksportowanych jednostek. W obszarze **Stan przetwarzania jednostki** wybierz jednostkę **Wartość zapasów** z listy, a następnie wybierz opcję **Pobierz plik**, aby pobrać dane wyeksportowane z tej jednostki.

Aby uzyskać więcej informacji o używaniu funkcji zarządzania danymi do eksportowania danych, patrze [omówienie importowania i eksportowania danych](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

## <a name="generate-a-standard-inventory-value-report"></a>Wygeneruj standardowy raport o wartości zapasów

Aby wygenerować standardowy raport **wartości zapasów**, należy skorzystać z następującej procedury.

1. Przejdź do **Zarządzanie kosztami \> Zapytania i raporty \> Księgowanie zapasów - raporty o stanie \> Wartość zapasów**.
1. W oknie dialogowym **Raport wartości zapasów** na skróconej karcie **Parametry** ustaw następujące pola:

    - **Nazwa** — Wpisz unikalną nazwę raportu.
    - **Identyfikator** — umożliwia wybór [konfiguracji raportu wartości zapasów](#report-configuration), która będzie dla tego raportu. Konfiguracja ustala opcje dla kolumn i wierszy, które będą uwzględniane w raporcie.
    - **Interwał dat** — pola w tej sekcji określają, które rekordy będą uwzględniane w raporcie. Aby zdefiniować interwał dat, można wybrać wstępnie zdefiniowany zakres (w odniesieniu do daty generowania raportu) w polu **Kod zakresu dat** lub wybrać określone daty w polach **Od dnia** i **Do dnia**.

1. Na skróconej karcie **Rekordy do uwzględnienia** należy skonfigurować filtry i ograniczenia w celu zdefiniowania danych uwzględnionych w raporcie. Wybierz **Filtruj**, aby otworzyć standardowe okno dialogowe edytora zapytań, w którym możesz zdefiniować kryteria wyboru, kryteria sortowania i łączenia. Pola działają w ten sam sposób, jak działają w przypadku innych typów zapytań w module Supply Chain Management.
1. Na skróconej karcie **Uruchom w tle** określ sposób, kiedy i jak często generowany jest raport. Pola działają w ten sam sposób, jak działają w przypadku innych typów [zadań w tle](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) w module Supply Chain Management.
1. Wybierz przycisk **OK**, aby zastosować ustawienia i zamknąć okienko dialogowe. Pojawi się raport.

## <a name="reading-inventory-value-reports"></a>Czytanie raportów o wartości zapasów

Ta sekcja zawiera wskazówki dotyczące odczytywania i odczytywania raportu o wartości zapasów.

Supply Chain Management obsługuje następujące dwie ważne pojęcia związane ze stanem zapasów:

- **Aktualizacja finansowa** — ta koncepcja wskazuje, że transakcje magazynowe są już zafakturowane. W przypadku zleceń produkcyjnych wskazuje on zakończenie zlecenia produkcyjnego.
- **Fizyczna aktualizacja** — ta koncepcja wskazuje, że transakcje magazynowe nie zostały jeszcze zafakturowane, ale zostały odebrane lub wysłane. W przypadku zleceń produkcyjnych wskazuje, że materiał został pobrany lub zlecenie produkcyjne zostało zgłoszone jako gotowe.

Podczas zrozumienia tych dwóch pojęć powinno się ułatwić zrozumienie następujących kolumn w wynikach raportu:

- **Inwentarz: Ilość finansowa** — ilość, która została zaktualizowana finansowo.
- **Zapasy: Kwota finansowa** — Kwota wartości zapasów, która została zaktualizowana finansowo.
- **Zapasy: Zaksięgowana ilość fizyczna** — Ilość, która została fizycznie zaktualizowana.
- **Zapasy: Zaksięgowana kwota fizyczna** — Wartość ilości zapasów, która została fizycznie zaktualizowana.
- **Zapasy: Ilość fizyczna nie zaksięgowana** — ilość z transakcjami magazynowymi, które nie zostały zaksięgowane w księdze głównej Na przykład w grupie modeli towaru, w której wyczyszczane są opcje **Księguj magazyn fizyczny** i **Księguj magazyn finansowy**, a z grupą jest połączony towar. Następnie tworzysz zamówienie zakupu, otrzymujesz je i wystawiasz fakturę. Na tym etapie podczas przeglądania raportu wartości zapasów dla towaru można zobaczyć, że ilość i wartość na zamówieniu zakupu są wyświetlane w kolumnach **Zapasy: Ilość fizyczna nie zaksięgowana** i **Zapasy: Kwota fizyczna nie zaksięgowana**.
- **Zapasy: niezaksięgoowana kwota fizyczna** — raporty można tak skonfigurować, aby pokazywały niezaksięgowane kwoty. Jeśli jednak raport jest raportem uzgadniania zapasów, nie należy używać tej wartości. W przeciwnym razie kwota nie zostanie zaksięgowana w księdze głównej.
- **Zapasy: ilość** — łączna ilość we wszystkich kolumnach ilości w raporcie
- **Zapasy: kwota** — łączna ilość we wszystkich kolumnach kwoty w raporcie Podczas uzgadniania zapasów nie należy używać tej kolumny, jeśli raport zawiera kolumnę **Zapasy: kwota fizyczna nie zaksięgowana**. W tym przypadku musisz wykluczyć wartość **Zapasy: kwota fizyczna nie zaksięgowana** z łącznej kwoty.
- **Średni koszt jednostkowy** — łączna kwota podzielona przez całkowitą ilość.

Z reguły do wyświetlania wartości zapasów i ilości używany jest raport wartości zapasów. Czasami jednak w raporcie nie są wyświetlane wszystkie odpowiednie wymiary magazynowe. Jeśli spodziewane wymiary nie są widać, sprawdź poprawność następujących ustawień:

- Przejrzyj grupy wymiarów przechowywania i śledzenia towarów. W raporcie mogą być wyświetlane tylko dla wymiarów, dla których jest włączona opcja **Magazyn finansowy**.
- Przejdź do **Zarządzanie kosztami \> Ustawienia zasad księgowania zapasów \> Raporty wartości zapasów**, wybierz konfigurację raportu używaną do wygenerowania raportu i upewnij się, że w kolumnie **Widok** zostały wybrane wymagane wymiary magazynowe.

Na przykład w przypadku towaru o numerze *A0001*. W grupie wymiarów magazynowania tylko dla magazynu finansowego jest włączony tylko ten zespół. Dla zapasów fizycznych włączono zarówno miejsce, jak i magazyn. W grupie wymiarów śledzenia numer partii jest włączony dla magazynu fizycznego, ale nie dla magazynu finansowego. Następnie można użyć konfiguracji raportu, w której są wybrane wszystkie elementy lokalizacji, magazynu i numeru partii. Podczas wyświetlania raportu jest wyświetlana wartość tylko dla witryny. Kolumny dotyczące magazynu i numeru partii są puste. Jak pokazano w tym przykładzie, w raportach wartości zapasów mogą być wyświetlane tylko wymiary magazynowe włączone dla magazynu finansowego.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
