---
title: Zaawansowane opcje formatowania w raportowaniu finansowym
description: "Podczas tworzenia raportu w module raportowania finansowego są dostępne dodatkowe funkcje formatowania, włącznie z filtrami wymiarów, ograniczeniami kolumn i jednostek sprawozdawczych, wierszami niedrukowanymi i instrukcjami IF/THEN/ELSE w obliczeniach."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 8c95f3bfc33730fcf03bd65cd1e66ec104f1e236
ms.contentlocale: pl-pl
ms.lasthandoff: 08/13/2018

---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Zaawansowane opcje formatowania w raportowaniu finansowym

[!include [banner](../includes/banner.md)]

Podczas tworzenia raportu w module raportowania finansowego są dostępne dodatkowe funkcje formatowania, włącznie z filtrami wymiarów, ograniczeniami kolumn i jednostek sprawozdawczych, wierszami niedrukowanymi i instrukcjami IF/THEN/ELSE w obliczeniach. 

W poniższej tabeli opisano zaawansowane funkcje formatowania, które są dostępne podczas projektowania raportów.

| Funkcja                   | Opis |
|----------------------------|-------------|
| Filtr wymiarów           | Aby uzyskać dostęp do określonego zestawu danych, można użyć wymiarów w definicji wiersza i w definicji kolumny. Wiele raportów używa segmentu naturalnego w formacie wiersza. Jednak wiersze można modyfikować, aby zawierały wartości wymiarów. Filtry wymiarów w definicji kolumny umożliwiają dostęp do określonych wartości wymiaru. |
| Ograniczenie jednostki raportowania | Wiersz raportu można skonfigurować tak, aby pokazywane były tylko dane połączone z określoną jednostką raportowania. |
| Wiersze niedrukowane (NP)     | Wiersze niedrukowane są przydatne w wielu raportach. Jeśli do uzyskania jakiejś wartości trzeba wykonać kilka obliczeń, w drukowanym raporcie te obliczenia mogą być ukryte. Wiersze niedrukowane są również przydatne do rozwiązywania problemów z projektami raportów i do zaawansowanego rozmieszczania komórek. |
| Ograniczenie kolumny         | Ograniczenie kolumny w definicji wiersza jest przydatne do ukrywania wartości, które są istotne tylko w przypadku niektórych wierszy raportu. Podczas obliczania wartości procentowej dla wiersza, ograniczenie kolumny uniemożliwia drukowanie kolumn sum lub innych kolumn, gdy te wartości nie mają zastosowania. |
| Podział kolumny               | Można dodać podziały kolumn w definicji wiersza, aby wyświetlić dane raportu obok siebie. W jednej definicji wiersza można dodać wiele podziałów kolumn, a nagłówki kolumn są powtarzane na górze każdej kolumny po jej podziale. Komentarze dotyczące raportu są wyświetlane między podziałami kolumn. |
| Instrukcja IF/THEN/ELSE     | Można zmodyfikować obliczenia w definicji wiersza lub definicji kolumny. |

## <a name="advanced-cell-placement"></a>Zaawansowane rozmieszczanie komórek
Zaawansowane rozmieszczenie komórek (*wymuszenie*) polega na wstawianiu określonych wartości do określonych komórek. Na przykład wymuszenie jest często używane do przenoszenia poprawnego salda w zestawieniu przepływów pieniężnych. Można używać wymuszenia do następujących celów:

- Przenoszenie wartości z programu Microsoft Excel do określonych komórek.
- Kodowanie na stałe określonych wartości w raporcie.
- Modyfikowanie znaków przez kopiowanie wartości z poprzedniej komórki i mnożenie tej wartości -1.

> [!NOTE]
> W wielu przypadkach należy skonfigurować definicję raportu tak, aby obliczenia kolumny były wykonywane przed obliczeniami wiersza. Aby przeprowadzić tę konfigurację, należy wykonać następujące czynności.
> 
> 1. W Projektancie raportów otwórz definicję raportu.
> 2. Na karcie **Ustawienia** w obszarze **Priorytet obliczeń** wybierz opcję **Najpierw wykonaj obliczenia kolumny, a następnie wierszy**.

## <a name="designing-the-report"></a>Projektowanie raportu
Podczas projektowania raportu należy najpierw utworzyć wszystkie wiersze szczegółów, aby mieć pewność, że wartości są pobierane zgodnie z oczekiwaniami. Następnie należy dodać zastąpienia formatu **NP** (niedrukowane), aby pomijać szczegół zawierający wartości końcowe.

> [!IMPORTANT]
> Użycie w definicji wierszy kodu formatu **CAL** uniemożliwi przejście do szczegółów transakcji.

Przy wymuszaniu formuły używają następującego formatu: &lt;kolumna docelowa&gt;=&lt;kolumna źródłowa&gt;.&lt;kod wiersza&gt; Dodatkowe rozmieszczenia wiersza oddziela się przecinkami i spacjami. Oto przykład: D=C.190,E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Przykłady zaawansowanych opcji formatowania
Następujące przykłady przedstawiają sposób formatowania definicji wiersza i definicji kolumny w celu wymuszania podstawowego raportu przepływów pieniężnych (przykład 1) i raportu statystycznego (przykład 2).

### <a name="example-1-basic-forcing"></a>Przykład 1: Wymuszenie podstawowe

Poniższa tabela przedstawia przykład definicji wiersza, która używa wymuszenie podstawowego.

| Kod wiersza |           opis            | Kod formatu | Powiązane formuły/wiersze/jednostki |        Modyfikator wiersza        | Łącze do Wymiary finansowe |
|----------|----------------------------------|-------------|-----------------------------|----------------------------|------------------------------|
| 100      | Gotówka na początku okresu (NP) |             |                             | Modyfikator konta = \[/BB\] | +Segment2 = \[1100\]         |
| 130      | Środki pieniężne na początku okresu      | CAL         | C=C.100,F=D.100             |                            |                              |
| 160      |                                  |             |                             |                            |                              |
| 190      |                                  |             |                             |                            |                              |

> [!NOTE] 
> Puste kolumny zostały usunięte z poprzedniej tabeli dla celów prezentacji: kolumny Format zastępczy, Saldo zwykłe, Sterowanie wydrukiem, Ograniczenia kolumny nie są wyświetlane.

Poniższa tabela przedstawia przykład definicji kolumny, która używa wymuszenie podstawowego w wierszu.

|                              | I   | mld    | C        | D      | E      | P    |
|------------------------------|-----|------|----------|--------|--------|------|
| Nagłówek 1                     |     |      |          |        |        |      |
| Nagłówek 2                     | I   | mld    | C        | D      | E      | P    |
| Nagłówek 3                     |     |      |          |        |        |      |
| Typ kolumny                  | ROW | DESC | FD       | FD     | FD     | CALC |
| Kod księgi/Atrybut kategorii |     |      | ACTUAL   | ACTUAL | ACTUAL |      |
| Rok obrachunkowy                  |     |      | BASE     | BASE   | BASE   |      |
| Okres                       |     |      | BASE     | BASE   | BASE   |      |
| Objęte okresy              |     |      | PERIODIC | YTD/BB | YTD    |      |
| Wzór                      |     |      |          |        |        | E-D  |
| Szerokość kolumny                 | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>Przykład 2: Raporty statystyczne

Poniższa tabela przedstawia przykład definicji wiersza, która używa wymuszenie dla raportu statystycznego.

| Kod wiersza | Opis               | Kod formatu | Powiązane formuły/wiersze/jednostki     | Format zastępczy      | Saldo zwykłe | Łącze do Wymiary finansowe               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|--------------------------------------------|
| 50       | Informacje statystyczne   | REM         |                                 |                      |                |                                            |
| 100      | Liczba pracowników — Stany Zjednoczone            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |                                            |
| 115      | Liczba pracowników — międzynarodowa | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |                                            |
| 1.3.0      |                           |             |                                 |                      |                |                                            |
| 190      | Sprzedaż w Stanach Zjednoczonych                  |             |                                 |                      | C              | +Segment2 = \[41\*\], Segment3 = \[00\]    |
| 220      | Międzynarodowa sprzedaż       |             |                                 |                      | C              | +Segment2 = \[41\*\], Segment3 = \[01:99\] |
| 250      |                           |             |                                 |                      |                |                                            |
| 280      |                           |             |                                 |                      |                |                                            |
| 310      | Sprzedaż w Stanach Zjednoczonych                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |                                            |
| 340      | Międzynarodowa sprzedaż       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |                                            |

> [!NOTE] 
> Puste kolumny zostały usunięte z poprzedniej tabeli dla celów prezentacji: kolumny Sterowanie wydrukiem, Ograniczenia kolumny i Modyfikator wiersza nie są wyświetlane.

Poniższa tabela przedstawia przykład definicji kolumny, która używa wymuszenie dla raportu statystycznego.

|                              | A   | mld    | C      | D            | E     | P            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| Nagłówek 1                     | A   | mld    | C      | D            | E     | P            |
| Nagłówek 2                     | -   | -    | Od początku roku do chwili obecnej    | Sprzedaż w roku | Pracownicy | USD na osobę |
| Nagłówek 3                     |     |      |        |              |       |              |
| Typ kolumny                  | ROW | DESC | FD     | CALC         | CALC  | CALC         |
| Kod księgi/Atrybut kategorii |     |      | ACTUAL |              |       |              |
| Rok obrachunkowy                  |     |      | BASE   |              |       |              |
| Okres                       |     |      | BASE   |              |       |              |
| Objęte okresy              |     |      | YTD    |              |       |              |
| Wzór                      |     |      |        |              |       | E-D          |
| Szerokość kolumny                 | 5 przypada na składniki z tytułu ubezpieczeń majątkowych i osobowych   | 30   | 14     | 14           | 14    | 14           |

## <a name="restricting-a-row-to-a-specific-reporting-unit"></a>Ograniczanie wiersza do określonej jednostki raportowania
Po wiersz raportu jest ograniczony do określonej jednostki sprawozdawczej, ten wiersz pokazuje połączone dane tylko dla jednostki raportowania o określonej nazwie i ignoruje dane dla innych jednostek raportowania w drzewie raportowania. Na przykład można utworzyć wiersz, który zawiera szczegóły wszystkich wydatków operacyjnych dla określonego działu. Raport może zawierać zduplikowane dane, jeśli raport zawiera zarówno drzewo raportowania, jak i definicję wiersza, która ma nie tylko konto naturalne. Na przykład drzewo raportowania zawiera sześć działów w organizacji i oprócz tego w definicji wiersza jest określona kombinacja konta i działu w wierszu. Podczas generowania raportu określona kombinacja konta i działu jest drukowana na każdym poziomie drzewa raportowania, nawet jeśli ten dział może nie odpowiadać temu, co znajduje się w drzewie. To zachowanie występuje z powodu zastąpienia przez wiersz tego, co jest zwykle odfiltrowywane przez definicję raportu. Jednym ze sposobów uniknięcia duplikowania danych jest ograniczenie wiersza do określonej jednostki raportowania.

> [!NOTE]
> Jeśli wiersz zawiera wymiary i zostanie ograniczony do podrzędnej jednostki raportowania, kwota wiersza jest uwzględniona dla tej jednostki podrzędnej dla jej jednostek nadrzędnych, ale dane się nie duplikują.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Ograniczanie wiersza do jednostki raportowania

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie wybierz wiersz do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Powiązane formuły/wiersze/jednostki**.
3. W oknie dialogowym **Wybór jednostki raportowania** w polu **Drzewo raportowania** zaznacz drzewo przypisane w definicji raportu.
4. Wybierz jednostkę raportowania, a następnie kliknij przycisk **OK**. Ograniczenie jest wyświetlane w komórce definicji wiersza.
5. Kliknij dwukrotnie komórkę w kolumnie **Łącze do wymiarów finansowych** ograniczonego wiersza, a następnie wprowadź łącze do systemu danych finansowych.

## <a name="selecting-print-control-in-a-row-definition"></a>Wybieranie sterowania wydrukiem w definicji wiersza
Kody sterowania wydrukiem można określić dla każdej kolumny za pomocą komórki **Sterowanie wydrukiem**.

### <a name="add-print-control-codes-to-a-report-row"></a>Dodawanie kodów sterowania wydrukiem do wiersza raportu

1. W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Sterowanie wydrukiem**.
3. W oknie dialogowym **Sterowanie wydrukiem** wybierz kod sterowania wydrukiem lub naciśnij i przytrzymaj klawisz Ctrl, aby zaznaczyć wiele kodów. Można również wprowadzić kody sterowania wydrukiem bezpośrednio w komórce **Sterowanie wydrukiem**. Kolejne kody sterowania wydrukiem należy oddzielić przecinkami.
4. Wybierz wszelkie warunkowe opcje wydruku.
5. Kliknij przycisk **OK**

### <a name="regular-print-control-codes"></a>Zwykłe kody sterowania wydrukiem

W poniższej tabeli opisano kody zwykłego sterowania wydrukiem dla definicji wiersza.

| Kod sterowania wydrukiem | Interpretacja kodu sterowania wydrukiem         | Opis |
|--------------------|--------------------------------------------------|-------------|
| NP                 | Wiersz niedrukowany                                 | Uniemożliwia drukowanie kwot w wierszu w raporcie i wyklucza wszelkie kwoty z obliczeń. Aby uwzględnić kolumnie niedrukowaną, należy odwołać się do niej bezpośrednio w formule obliczania. Na przykład wiersz niedrukowany 240 jest uwzględniony w obliczeniu: **230+240+250**. Jednak wiersz niedrukowany 240 nie jest już uwzględniany w obliczeniu: **230:250**. |
| CS                 | Symbol waluty; użyj formatu waluty w tym wierszu | Dołącz symbol waluty we wszystkich kwotach nieprocentowych. Wartości procentowe nigdy otrzymują symbolu waluty. |
| XD                 | Pomijanie wiersza w raporcie szczegółów konta            | Wyłącz wyświetlanie konta w raportach szczegółów konta i raportach szczegółów transakcji. Ta opcja sterowania wydrukiem jest przydatna, gdy wiersz zawiera wiele kont, które nie powinny być widoczne w raporcie szczegółów ani raporcie szczegółów transakcji. |
| X0                 | Pomijanie wiersza, jeśli wszystkie wartości są zerowe                        | Wyklucz wiersz z raportu, jeśli wszystkie komórki w tym wierszu są puste lub zawierają zera. Ta opcja sterowania wydrukiem ma znaczenie tylko wtedy, gdy opcja pomijania salda zerowego nie jest wybrana w definicji raportu. |
| B0                 | Zostawianie pustych kolumn o wartościach zerowych                         | Zostaw kolumny w wierszu niewypełnione, jeśli kwoty wynoszą zero. |
| XR                 | Pomijanie akumulacji                                  | Pomijaj akumulację. Jeśli raport używa trzeba raportowania, kwoty w tym wierszu nie są akumulowane w następnych węzłach nadrzędnych. |
| SR                 | Pomijanie zaokrąglania                                | Zapobiegaj zaokrąglaniu kwoty w tym wierszu. |
| XT                 | Pomijanie wiersza w raporcie szczegółów transakcji        | Wyłącz wyświetlanie transakcji w raportach szczegółów transakcji. Ta opcja sterowania wydrukiem jest przydatna, gdy wiersz zawiera wiele kont, które nie powinny być widoczne w raporcie szczegółów transakcji. |

### <a name="conditional-print-control-codes"></a>Kody warunkowego sterowania wydrukiem

W poniższej tabeli opisano kody warunkowego sterowania wydrukiem dla definicji wiersza.

| Kod sterowania wydrukiem | Opis                                  |
|--------------------|----------------------------------------------|
| (brak)             | Usuwanie zaznaczenia warunkowego wydruku.       |
| UW                 | Drukuj tylko salda debetowe dla tego wiersza.  |
| CR                 | Drukuj tylko salda kredytowe dla tego wiersza. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Komórka Ograniczenie kolumny w definicji wiersza
Komórka **Ograniczenie kolumny** w definicji wiersza ma wiele zastosowań. W zależności od typu wiersza możesz użyć komórki **Ograniczenia kolumny** do określenia jednej z następujących funkcji:

- Komórka może ograniczać drukowanie kwot wiersza do określonej kolumny. Ta funkcja jest przydatna, jeśli tworzysz bilans tabelaryczny.
- Komórka może określać kolumnę kwot do sortowania.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Używanie formuły obliczania w definicji wiersza
Formuła obliczania w definicji wiersza może zawierać operatory **+**, **-**, **\*** i **/** oraz instrukcje **IF/THEN/ELSE**. Oprócz tego obliczenie może obejmować pojedyncze komórki oraz kwoty bezwzględne (wartości rzeczywiste zawarte w formule). Kod może zawierać maksymalnie 1024 znaki. Obliczenia nie mogą być stosowane do wierszy zawierających komórki typu **Łącze do wymiarów finansowych** (FD). Można jednak dołączać obliczenia w kolejnych wierszach, wyłączać drukowanie tych wierszy, a następnie sumować wiersze obliczeń.

### <a name="operators-in-a-calculation-formula"></a>Operatory w formule obliczania

Formuła obliczania używa bardziej złożonych operatorów niż formuła sumy wiersza. Może jednak używać operatorów **\*** i **/** wraz z dodatkowymi operatorami do mnożenia (\*) i dzielenia (/) kwot. Aby użyć zakresu lub sumy w formule obliczeń, trzeba umieścić znak @ przed kodem wiersza, chyba że używasz kolumny w definicji wiersza. Na przykład aby dodać kwotę w wierszu 100 do kwoty w wierszu 330, możesz użyć formuły sumy wiersza **100+330** lub formuły obliczeń **@100+@330**.

> [!NOTE]
> Należy użyć znaku @ przed każdym wierszem kodu, który jest używany w formule obliczania. W przeciwnym razie liczba jest odczytywana jako kwota bezwzględna. Na przykład formuła **@100+330** dodaje 330 USD do kwoty w wierszu 100. W przypadku odwołania do kolumny w formule obliczania znak @ nie jest konieczny.

### <a name="create-a-calculation-formula"></a>Tworzenie formuły obliczeń

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Kod formatu**, a następnie wybierz opcję **CAL**.
3. W komórce **Powiązane formuły/wiersze/jednostki** wpisz formułę obliczania.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Przykład formuły obliczania dla wybranych wierszy

W tym przykładzie formuła obliczania **@100+@330** oznacza, że kwota z wiersza 100 jest dodawana do kwoty w wierszu 330. Formuła sumy wiersza **340+370** dodaje kwotę z wiersza 340 do kwoty w wierszu 370. (Kwota w wierszu 370 jest kwotą z formuły obliczania).

| Kod wiersza | Opis                 | Kod formatu | Powiązane formuły/wiersze/jednostka | Sterowanie wydrukiem | Modyfikator wiersza | Łącze do wymiarów finansowych |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Gotówka na początku okresu |             |                            | NP            | BB           | +Konto=\[1100:1110\]       |
| 370      | Gotówka na początku roku   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Gotówka na początku okresu | TOT         | 340+370                    |               |              |                              |

Jeśli wiersz w definicji wiersza ma format kodu **CAL**, i wprowadzisz matematyczne obliczenie w komórce **Powiązane formuły/wiersze/jednostki**, należy również wprowadzić literę skojarzonej kolumny i wiersza w raporcie. Na przykład wpisz **A.120**, aby wskazać wiersz 120 w kolumnie A. Można również użyć znaku @, aby wskazać wszystkie kolumny. Na przykład wpisz **@120**, aby wskazać wszystkie kolumny dla wiersza 120. Wyniki wszelkich matematycznych obliczeń, które nie zawierają litery kolumny lub znaku @, są uznawane za liczby rzeczywiste.

> [!NOTE]
> Jeśli odwołanie do wiersza ma postać kodu wiersza etykiety, musisz użyć kropki (.) jako separatora między literą kolumny a etykietą (na przykład **A.MARŻABRUTTO\_A.SPRZEDAŻ**). Jeśli używasz znaku @, separator nie jest wymagany(na przykład **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Przykład formuły obliczania dla wybranych kolumn

W tym przykładzie formuła obliczania **E=C.340** oznacza, że obliczenia w komórce w kolumnie C, wiersz 340, są wykonywane tylko w kolumnie E.

> [!NOTE]
> W przypadku odwołania do kolumny w formule obliczania znak @ nie jest konieczny.

| Kod wiersza | Opis                 | Kod formatu | Powiązane formuły/wiersze/jednostka | Sterowanie wydrukiem | Modyfikator wiersza | Łącze do wymiarów finansowych |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Gotówka na początku okresu |             |                            | NP            | BB           | +Konto=\[1100:1110\]       |
| 370      | Gotówka na początku roku   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Gotówka na początku okresu | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Modyfikowanie liczb w wybranych kolumn

Jeśli modyfikujesz liczbę lub obliczenie w jednej kolumnie określonego wiersza, ale nie chcesz zmieniać innych kolumn w raporcie, możesz określić opcję **CAL** (obliczenie) w kolumnie **Kod formatu** dla definicji wiersza.

- Aby wykonać obliczenie we wszystkich kolumnach raportu (**FD**), nie wpisuj przypisania kolumny.
- Aby ograniczyć formułę do określonych kolumn, wpisz literę kolumny i znak równości (**=**), a następnie formułę.
- Możesz określić wiele kolumn. Kiedy używasz znaku @ dla danego położenia kolumny, znak @ jest powiązany z wierszem.
- Możesz wprowadzić wiele formuł kolumn w jednym wierszu. Formuły należy oddzielić przecinkami.

### <a name="calculation-examples"></a>Przykłady obliczeń

| Obliczenie            | Tworzone działanie                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Dla każdej kolumny wartość w wierszu 130 jest mnożona przez 0,75. Wynik jest następnie umieszczany w bieżącym wierszu każdej kolumny. |
| B=@130\*.75            | To samo obliczenie jest wykonywane tylko w kolumnie B.                                                                      |
| A,B,C=(@100/@130)\*.75 | A=(A.100/A.130)\*.75 B=(B.100/B.130)\*.75 C=(C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>Instrukcje IF/THEN/ELSE w definicji wiersza

Instrukcje **IF/THEN/ELSE** można dodawać do wszystkich prawidłowych obliczeń i używane z formatem **CAL**. Formuły obliczeń **IF/THEN/ELSE** wpisuje się w komórce w kolumnie **Powiązane formuły/wiersze/jednostki**. Formuły obliczeń **IF/THEN/ELSE** wykorzystują następujący format: IF &lt;instrukcja true/fale&gt; THEN &lt;formuła&gt; ELSE &lt;formuła&gt; Część **ELSE &lt;formuła&gt;** instrukcji jest opcjonalna.

#### <a name="if-statements"></a>Instrukcje IF

Instrukcja, która występuje po instrukcji **IF**, może być dowolną instrukcją, która może zostać oceniona jako prawda (true) lub fałsz (false). Instrukcja, która występuje po instrukcji **IF**, może zawierać prostą ocenę lub może być złożoną instrukcją zawierającą wiele wyrażeń. Oto kilka przykładów:

- **IF A.200&gt;0** (Ocena prosta)
- **IF A.200&gt;0 AND A.200&lt;10,000** (Instrukcja złożona)
- **IF A.200&gt;10000 OR ((A.340/B.1200)\*2 &lt;1200)** (Instrukcja złożona zawierająca wiele wyrażeń)

Wyrażenie **Okresy** w instrukcji **IF** określa liczbę okresów dla raportu. Ten termin jest zwykle używany do obliczania średniej od początku roku. Na przykład po uruchomieniu raportu za okres 7 od początku roku instrukcja **B.150/Okresy** oznacza, że wartość w wierszu 150 kolumny B jest dzielona przez 7.

#### <a name="then-and-else-formulas"></a>Formuły THEN i ELSE

Formuły **THEN** i **ELSE** mogą być dowolnym prawidłowym obliczeniem od bardzo prostych przypisań wartości do złożonych formuł. Na przykład instrukcja **IF A.200&gt;0 THEN A=B.200** oznacza: „jeśli wartość w komórce w kolumnie A wiersza 200 jest większa niż 0 (zero), należy wprowadzić wartość z komórki w kolumnie B wiersza 200 do komórki w kolumnie A bieżącego wiersza”. Instrukcja **IF/THEN**, która występuje przed nią, wstawia wartość w jednej kolumnie bieżącego wiersza. Można jednak również użyć znaku @ w ocenie prawda/fałsz lub w formule, aby określić wszystkie kolumny. Oto kilka innych przykładów, które są opisane w następujących sekcjach:

- **IF A.200 &gt;0 THEN B.200**: Jeśli wartość w komórce A.200 jest dodatnia, wartość z komórki B.200 jest umieszczana w każdej kolumnie bieżącego wiersza.
- **IF A.200 &gt;0 THEN @200**: Jeśli wartość w komórce A.200 jest dodatnia, wartość z każdej kolumny w wierszu 200 jest umieszczana w odpowiedniej kolumnie bieżącego wiersza.
- **IF @200 &gt;0 THEN @200**: Jeśli wartość w wierszu 200 bieżącej kolumny jest dodatnia, wartość z wiersza 200 jest umieszczana w tej samej kolumnie bieżącego wiersza.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Ograniczanie obliczenia do jednostki raportowania w definicji wiersza

Aby ograniczyć obliczenia do jednej jednostki raportowania w drzewie raportowania, tak aby kwota wyniku nie była akumulowana do jednostki wyższego poziomu, można użyć kodu **@Unit** w komórce **Powiązane formuły/wiersze/jednostki** w definicji wiersza. Kod **@Unit** znajduje się w kolumnie B drzewa raportowania **Nazwa jednostki**. Jeśli używany jest kod **@Unit**, wartości nie są akumulowane, ale obliczenia są oceniane na każdym poziomie drzewa raportowania.

> [!NOTE]
> Do korzystania z tej funkcji raportowania drzewo muszą być skojarzone z definicją wiersza.

Wiersz obliczania może odnosić się do wiersza obliczania lub wiersza danych finansowych. Obliczenie jest rejestrowane w komórce **Powiązane formuły/wiersze/jednostki** definicji wiersza i ograniczeniu typu danych finansowych. Obliczenie musi używać obliczenia warunkowego, które zaczyna się od konstrukcji **IF @Unit**. Oto przykład: IF @Unit(SPRZEDAŻ) THEN @100 ELSE 0 To obliczenie obejmuje kwoty z wiersza 100 w każdej kolumnie raportu, ale tylko dla jednostki SPRZEDAŻ. Jeśli wiele jednostek ma nazwę SPRZEDAŻ, kwota pojawia się w każdej z tych jednostek. Ponadto wiersz 100 może być wierszem danych finansowych i może być zdefiniowany jako niedrukowany. W takim przypadku kwota nie pojawia się we wszystkich jednostkach drzewa. Można też ograniczyć kwotę do jednej kolumny raportu, np. kolumny H, korzystając z ograniczenia kolumny, aby drukować tylko wartość widoczną w tej kolumnie raportu. Można uwzględnić kombinacje **OR** w instrukcji **IF**. Oto przykład: IF @Unit(SPRZEDAŻ) OR @Unit(SPRZEDAŻZACHÓD) THEN 5 ELSE @100 Można ograniczyć jednostkę w ograniczeniu typu obliczenia w jeden z następujących sposobów:

- Wprowadź nazwę jednostki, aby uwzględnić jednostki, które spełniają kryteria. Na przykład **IF @Unit(SPRZEDAŻ)** pozwala przeprowadzić obliczenie dla każdej jednostki o nazwie SPRZEDAŻ, nawet jeśli w drzewie raportowania jest kilka jednostek SPRZEDAŻ.
- Wpisz nazwę firmy i jednostki, aby ograniczyć obliczenia do określonych jednostek w wybranej firmie. Na przykład wpisz **IF @Unit(ACME:SPRZEDAŻ)**, aby ograniczyć obliczenie do jednostek SPRZEDAŻ w firmie ACME.
- Wprowadzenie pełnej hierarchii kodów z drzewa raportowania, tak aby kalkulacja była ograniczona tylko do konkretnej jednostki. Na przykład wpisz **IF @Unit(PODSUMOWANIE^ACME^ZACHODNIA WYBRZEŻE^SPRZEDAŻ)**.

> [!NOTE]
> W celu obejrzenia całej hierarchii kodów kliknij prawym przyciskiem myszy definicję drzewa raportowania i wybierz polecenie **Kopiuj identyfikator jednostki raportowania (kod H)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Ograniczanie obliczenia do jednostki raportowania

1. W Projektancie raportów kliknij pozycję **Definicje wierszy**, a następnie otwórz definicję wiersza, którą chcesz zmodyfikować.
2. Kliknij dwukrotnie komórkę **Kod formatu**, a następnie wybierz opcję **CAL**.
3. Kliknij komórkę **Powiązane formuły/wiersze/jednostki**, a następnie wprowadź warunkowe obliczanie, które rozpoczyna się od konstrukcji **IF @Unit**.

### <a name="ifthenelse-statements-in-a-column-definition"></a>Instrukcje IF/THEN/ELSE w definicji kolumny

Instrukcja **IF/THEN/ELSE** pozwala uzależnić każde obliczenie od wyników z dowolnej innej kolumny. Można się odwoływać do innych kolumn, ale nie można odwołać się do komórki raportu w instrukcji **IF**. Każde obliczenie musi być stosowane do całej kolumny. Na przykład instrukcja **IF B&gt;100 THEN B ELSE C\*1.25** oznacza: „jeśli kwota w kolumnie B jest większa niż 100, umieść wartość z kolumny B w kolumnie **CALC**. Jeśli wartość w kolumnie B nie jest większa niż 100, pomnóż wartość w kolumnie C przez 1,25 i umieścić wynik w kolumnie **CALC**”. Po instrukcji **IF** musi zawsze występować instrukcja logiczna, która może być oceniona jako prawdziwa lub fałszywa. Formuły używane do instrukcji **THEN** i **ELSE** mogą zawierać odwołania do dowolnej liczby kolumn i te formuły mogą być dowolnie złożone.

> [!NOTE]
> Nie można umieszczać wyników obliczeń w dowolnej innej kolumnie. Wyniki muszą być w kolumnie zawierające formułę.

