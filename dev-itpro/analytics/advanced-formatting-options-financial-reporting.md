---
title: Zaawansowane opcje formatowania w raportowaniu finansowym
description: "Podczas tworzenia raportu w module raportowania finansowego są dostępne dodatkowe funkcje formatowania, włącznie z filtrami wymiarów, ograniczeniami kolumn i jednostek sprawozdawczych, wierszami niedrukowanymi i instrukcjami IF/THEN/ELSE w obliczeniach."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 631fec1dc135565e6d38e7faf193a7a898b508cb
ms.lasthandoff: 03/29/2017


---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Zaawansowane opcje formatowania w raportowaniu finansowym

Podczas tworzenia raportu w module raportowania finansowego są dostępne dodatkowe funkcje formatowania, włącznie z filtrami wymiarów, ograniczeniami kolumn i jednostek sprawozdawczych, wierszami niedrukowanymi i instrukcjami IF/THEN/ELSE w obliczeniach. 

W poniższej tabeli opisano zaawansowane funkcje formatowania, które są dostępne podczas projektowania raportów.

| Funkcja                   | Opis                                                                                                                                                                                                                                                                                                                     |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Filtr wymiarów           | Aby uzyskać dostęp do określonego zestawu danych, można użyć wymiarów w definicji wiersza i w definicji kolumny. Wiele raportów używa segmentu naturalnego w formacie wiersza. Jednak wiersze można modyfikować, aby zawierały wartości wymiarów. Filtry wymiarów w definicji kolumny umożliwiają dostęp do określonych wartości wymiaru. |
| Ograniczenie jednostki raportowania | Wiersz raportu można skonfigurować tak, aby pokazywane były tylko dane połączone z określoną jednostką raportowania.                                                                                                                                                                                                                      |
| Wiersze niedrukowane (NP)     | Wiersze niedrukowane są przydatne w wielu raportach. Jeśli do uzyskania jakiejś wartości trzeba wykonać kilka obliczeń, w drukowanym raporcie te obliczenia mogą być ukryte. Wiersze niedrukowane są również przydatne do rozwiązywania problemów z projektami raportów i do zaawansowanego rozmieszczania komórek.                                                    |
| Ograniczenie kolumny         | Ograniczenie kolumny w definicji wiersza jest przydatne do ukrywania wartości, które są istotne tylko w przypadku niektórych wierszy raportu. Podczas obliczania wartości procentowej dla wiersza, ograniczenie kolumny uniemożliwia drukowanie kolumn sum lub innych kolumn, gdy te wartości nie mają zastosowania.                              |
| Podział kolumny               | Można dodać podziały kolumn w definicji wiersza, aby wyświetlić dane raportu obok siebie. W jednej definicji wiersza można dodać wiele podziałów kolumn, a nagłówki kolumn są powtarzane na górze każdej kolumny po jej podziale. Komentarze dotyczące raportu są wyświetlane między podziałami kolumn.                              |
| Instrukcja IF/THEN/ELSE     | Można zmodyfikować obliczenia w definicji wiersza lub definicji kolumny.                                                                                                                                                                                                                                                         |

## <a name="advanced-cell-placement"></a>Zaawansowane rozmieszczanie komórek
Zaawansowane rozmieszczenie komórek (*wymuszenie*) polega na wstawianiu określonych wartości do określonych komórek. Na przykład wymuszenie jest często używane do przenoszenia poprawnego salda w zestawieniu przepływów pieniężnych. Można używać wymuszenia do następujących celów:

-   Przenoszenie wartości z programu Microsoft Excel do określonych komórek.
-   Kodowanie na stałe określonych wartości w raporcie.
-   Modyfikowanie znaków przez kopiowanie wartości z poprzedniej komórki i mnożenie tej wartości -1.

**Uwaga:** w wielu przypadkach należy skonfigurować definicję raportu tak, aby obliczenia kolumny były wykonywane przed obliczeniami wiersza. Aby przeprowadzić tę konfigurację, należy wykonać następujące czynności.

1.  W Projektancie raportów otwórz definicję raportu.
2.  Na karcie **Ustawienia** w obszarze **Priorytet obliczeń** wybierz opcję **Najpierw wykonaj obliczenia kolumny, a następnie wierszy**.

## <a name="designing-the-report"></a>Projektowanie raportu
Podczas projektowania raportu należy najpierw utworzyć wszystkie wiersze szczegółów, aby mieć pewność, że wartości są pobierane zgodnie z oczekiwaniami. Następnie należy dodać zastąpienia formatu **NP** (niedrukowane), aby pomijać szczegół zawierający wartości końcowe. **Ważne:** gdy używasz kodu formatu **CAL** w definicji wiersza, możesz wyświetlić bardziej szczegółowe dane na poziomie transakcji. Do wymuszania, formuły, użyj następującego formatu: &lt;kolumny docelowej&gt;=&lt;pochodzący z kolumny&gt;. &lt;wierszy kodu&gt; oddzielić wszelkich dodatkowych miejsc docelowych dla wiersza przecinkiem i spacją. Oto przykład: D=C.190,E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Przykłady zaawansowanych opcji formatowania
Następujące przykłady przedstawiają sposób formatowania definicji wiersza i definicji kolumny w celu wymuszania podstawowego raportu przepływów pieniężnych (przykład 1) i raportu statystycznego (przykład 2).

### <a name="example-1-basic-forcing"></a>Przykład 1: Wymuszenie podstawowe

Poniższa tabela przedstawia przykład definicji wiersza, która używa wymuszenie podstawowego.

| Kod wiersza | Opis                      | Kod formatu | Powiązane formuły/wiersze/jednostki | Zmiana formatu | Saldo zwykłe | Sterowanie wydrukiem | Ograniczenie kolumny | Modyfikator wiersza               | Łącze do wymiarów finansowych |
|----------|----------------------------------|-------------|-----------------------------|-----------------|----------------|---------------|--------------------|----------------------------|------------------------------|
| 100      | Gotówka na początku okresu (NP) |             |                             |                 |                |               |                    | Konto modyfikator = \[/BB\] | + Segment2 = \[1100\]         |
| 130      | Gotówka na początku okresu      | CAL         | C=C.100,F=D.100             |                 |                |               |                    |                            |                              |
| 160      |                                  |             |                             |                 |                |               |                    |                            |                              |
| 190      |                                  |             |                             |                 |                |               |                    |                            |                              |

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

| Kod wiersza | Opis               | Kod formatu | Powiązane formuły/wiersze/jednostki     | Zmiana formatu      | Saldo zwykłe | Sterowanie wydrukiem | Ograniczenie kolumny | Modyfikator wiersza | Łącze do wymiarów finansowych               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|---------------|--------------------|--------------|--------------------------------------------|
| 50       | Informacje statystyczne   | REM         |                                 |                      |                |               |                    |              |                                            |
| 100      | Liczba pracowników — Stany Zjednoczone            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 115      | Liczba pracowników — międzynarodowa | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 130      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 190      | Sprzedaż w Stanach Zjednoczonych                  |             |                                 |                      | C              |               |                    |              | + Segment2 = \[41\*\], Segment3 = \[00\]    |
| 220      | Międzynarodowa sprzedaż       |             |                                 |                      | C              |               |                    |              | + Segment2 = \[41\*\], Segment3 = \[01:99\] |
| 250      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 280      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 310      | Sprzedaż w Stanach Zjednoczonych                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |               |                    |              |                                            |
| 340      | Międzynarodowa sprzedaż       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |               |                    |              |                                            |

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
Po wiersz raportu jest ograniczony do określonej jednostki sprawozdawczej, ten wiersz pokazuje połączone dane tylko dla jednostki raportowania o określonej nazwie i ignoruje dane dla innych jednostek raportowania w drzewie raportowania. Na przykład można utworzyć wiersz, który zawiera szczegóły wszystkich wydatków operacyjnych dla określonego działu. Raport może zawierać zduplikowane dane, jeśli raport zawiera zarówno drzewo raportowania, jak i definicję wiersza, która ma nie tylko konto naturalne. Na przykład drzewo raportowania zawiera sześć działów w organizacji i oprócz tego w definicji wiersza jest określona kombinacja konta i działu w wierszu. Podczas generowania raportu określona kombinacja konta i działu jest drukowana na każdym poziomie drzewa raportowania, nawet jeśli ten dział może nie odpowiadać temu, co znajduje się w drzewie. To zachowanie występuje z powodu zastąpienia przez wiersz tego, co jest zwykle odfiltrowywane przez definicję raportu. Jednym ze sposobów uniknięcia duplikowania danych jest ograniczenie wiersza do określonej jednostki raportowania. **Uwaga:** jeśli wiersz zawiera wymiary i zostanie ograniczony do podrzędnej jednostki raportowania, kwota wiersza jest uwzględniona dla tej jednostki podrzędnej dla jej jednostek nadrzędnych, ale dane się nie duplikują.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Ograniczanie wiersza do jednostki raportowania

1.  W Projektancie raportów kliknij **Definicje wiersza**, a następnie wybierz wiersz do zmodyfikowania.
2.  Kliknij dwukrotnie odpowiednią komórkę **Powiązane formuły/wiersze/jednostki**.
3.  W oknie dialogowym **Raportowanie wyboru jednostki** w polu **Drzewo raportowania** wybierz drzewo, które jest przypisane w definicji raportu.
4.  Wybierz jednostkę raportowania, a następnie kliknij przycisk **OK**. Ograniczenie jest wyświetlane w komórce definicji wiersza.
5.  Kliknij dwukrotnie komórkę w kolumnie **Łącze do wymiarów finansowych** ograniczonego wiersza, a następnie wprowadź łącze do systemu danych finansowych.

## <a name="selecting-print-control-in-a-row-definition"></a>Wybieranie sterowania wydrukiem w definicji wiersza
Kody sterowania wydrukiem można określić dla każdej kolumny za pomocą komórki **Sterowanie wydrukiem**.

### <a name="add-print-control-codes-to-a-report-row"></a>Dodawanie kodów sterowania wydrukiem do wiersza raportu

1.  W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Sterowanie wydrukiem**.
3.  W oknie dialogowym **Sterowanie wydrukiem** wybierz kod sterowania wydrukiem lub naciśnij i przytrzymaj klawisz Ctrl, aby zaznaczyć wiele kodów. Można również wprowadzić kody sterowania wydrukiem bezpośrednio w komórce **Sterowanie wydrukiem**. Kolejne kody sterowania wydrukiem należy oddzielić przecinkami.
4.  Wybierz wszelkie warunkowe opcje wydruku.
5.  Kliknij przycisk **OK**

### <a name="regular-print-control-codes"></a>Zwykłe kody sterowania wydrukiem

W poniższej tabeli opisano kody zwykłego sterowania wydrukiem dla definicji wiersza.

| Kod sterowania wydrukiem | Interpretacja kodu sterowania wydrukiem         | Opis                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Wiersz niedrukowany                                 | Uniemożliwia drukowanie kwot w wierszu w raporcie i wyklucza wszelkie kwoty z obliczeń. Aby uwzględnić kolumnie niedrukowaną, należy odwołać się do niej bezpośrednio w formule obliczania. Na przykład wiersz niedrukowany 240 jest uwzględniony w obliczeniu: **230+240+250**. Jednak wiersz niedrukowany 240 nie jest już uwzględniany w obliczeniu: **230:250**. |
| CS                 | Symbol waluty; użyj formatu waluty w tym wierszu | Dołącz symbol waluty we wszystkich kwotach nieprocentowych. Wartości procentowe nigdy otrzymują symbolu waluty.                                                                                                                                                                                                                                                                                                |
| XD                 | Pomijanie wiersza w raporcie szczegółów konta            | Wyłącz wyświetlanie konta w raportach szczegółów konta i raportach szczegółów transakcji. Ta opcja sterowania wydrukiem jest przydatna, gdy wiersz zawiera wiele kont, które nie powinny być widoczne w raporcie szczegółów ani raporcie szczegółów transakcji.                                                                                                                                                           |
| X0                 | Pomijanie wiersza, jeśli wszystkie wartości są zerowe                        | Wyklucz wiersz z raportu, jeśli wszystkie komórki w tym wierszu są puste lub zawierają zera. Ta opcja sterowania wydrukiem ma znaczenie tylko wtedy, gdy opcja pomijania salda zerowego nie jest wybrana w definicji raportu.                                                                                                                                                                                            |
| B0                 | Zostawianie pustych kolumn o wartościach zerowych                         | Zostaw kolumny w wierszu niewypełnione, jeśli kwoty wynoszą zero.                                                                                                                                                                                                                                                                                                                                                      |
| XR                 | Pomijanie akumulacji                                  | Pomijaj akumulację. Jeśli raport używa trzeba raportowania, kwoty w tym wierszu nie są akumulowane w następnych węzłach nadrzędnych.                                                                                                                                                                                                                                                                               |
| SR                 | Pomijanie zaokrąglania                                | Zapobiegaj zaokrąglaniu kwoty w tym wierszu.                                                                                                                                                                                                                                                                                                                                                          |
| XT                 | Pomijanie wiersza w raporcie szczegółów transakcji        | Wyłącz wyświetlanie transakcji w raportach szczegółów transakcji. Ta opcja sterowania wydrukiem jest przydatna, gdy wiersz zawiera wiele kont, które nie powinny być widoczne w raporcie szczegółów transakcji.                                                                                                                                                                                                             |

### <a name="conditional-print-control-codes"></a>Kody warunkowego sterowania wydrukiem

W poniższej tabeli opisano kody warunkowego sterowania wydrukiem dla definicji wiersza.

| Kod sterowania wydrukiem | Opis                                  |
|--------------------|----------------------------------------------|
| (brak)             | Usuwanie zaznaczenia warunkowego wydruku.       |
| UW                 | Drukuj tylko salda debetowe dla tego wiersza.  |
| CR                 | Drukuj tylko salda kredytowe dla tego wiersza. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Komórka Ograniczenie kolumny w definicji wiersza
Komórka **Ograniczenie kolumny** w definicji wiersza ma wiele zastosowań. W zależności od typu wiersza możesz użyć komórki **Ograniczenia kolumny** do określenia jednej z następujących funkcji:

-   Komórka może ograniczać drukowanie kwot wiersza do określonej kolumny. Ta funkcja jest przydatna, jeśli tworzysz bilans tabelaryczny.
-   Komórka może określać kolumnę kwot do sortowania.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Używanie formuły obliczania w definicji wiersza
Formuła kalkulacji w definicji wiersza może zawierać **+**, **-**, **\***, i **/**podmiotów gospodarczych, a także **ELSE-IF/THEN** instrukcji. Oprócz tego obliczenie może obejmować pojedyncze komórki oraz kwoty bezwzględne (wartości rzeczywiste zawarte w formule). Kod może zawierać maksymalnie 1024 znaki. Obliczenia nie mogą być stosowane do wierszy zawierających komórki typu **Łącze do wymiarów finansowych** (FD). Można jednak dołączać obliczenia w kolejnych wierszach, wyłączać drukowanie tych wierszy, a następnie sumować wiersze obliczeń.

### <a name="operators-in-a-calculation-formula"></a>Operatory w formule obliczania

Formuła obliczania używa bardziej złożonych operatorów niż formuła sumy wiersza. Jednak można użyć **\***i **/**operatorów wraz z innych operatorów, które należy pomnożyć (\*) i dzielenia (/) kwoty. Aby użyć zakresu lub sumy w formule obliczeń, trzeba umieścić znak @ przed kodem wiersza, chyba że używasz kolumny w definicji wiersza. Na przykład, aby dodać kwota rzędu 100 do kwoty w wierszu 330, można użyć formuły ogólnej wiersza **100 + 330** lub formuła kalkulacji **@100+@330**. **Uwaga:** należy użyć znaku @ przed każdym wierszem kodu, który jest używany w formule obliczania. W przeciwnym razie liczba jest odczytywana jako kwota bezwzględna. Na przykład formuła **@100330** dodaje USD 330 do kwoty 100 wierszy. W przypadku odwołania do kolumny w formule obliczania znak @ nie jest konieczny.

### <a name="create-a-calculation-formula"></a>Tworzenie formuły obliczeń

1.  W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Kod formatu**, a następnie wybierz opcję **CAL**.
3.  W komórce **Powiązane formuły/wiersze/jednostki** wpisz formułę obliczania.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Przykład formuły obliczania dla wybranych wierszy

W tym przykładzie formuła kalkulacji **@100+@330** oznacza, że kwota rzędu 100 zostanie dodana do kwoty w wierszu 330. Wiersz formuły ogólnej **340 + 370** dodanie ilości w wierszu 340 do kwoty w wierszu 370. (Ilość w wierszu 370 jest kwota formuły obliczania).

| Kod wiersza | Opis                 | Kod formatu | Powiązane formuły/wiersze/jednostka | Sterowanie wydrukiem | Modyfikator wiersza | Łącze do wymiarów finansowych |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Gotówka na początku okresu |             |                            | NP            | BB           | + Konto =\[1100:1110\]       |
| 370      | Gotówka na początku roku   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Gotówka na początku okresu | TOT         | 340+370                    |               |              |                              |

Jeśli wiersz w definicji wiersza ma format kodu **CAL**, i wprowadzisz matematyczne obliczenie w komórce **Powiązane formuły/wiersze/jednostki**, należy również wprowadzić literę skojarzonej kolumny i wiersza w raporcie. Na przykład wpisz **A.120** do reprezentowania A kolumna, wiersz 120. Alternatywnie, można użyć znaku (@), aby wskazać wszystkie kolumny. Na przykład wpisz **@120**do reprezentowania wszystkich kolumn w wierszu 120. Obliczeń matematycznych, która nie ma literę kolumny lub znak (@) zakłada się liczbą rzeczywistą. **Uwaga:** Jeśli używasz kodu wiersz etykiet Aby odwołać wiersz, należy użyć kropki (.) jako separatora między literę kolumny i etykiety (na przykład **A.GROSS\_MARGIN/A.SALES**). Jeśli używasz znaku (@), separatora nie jest wymagana (na przykład **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Przykład formuły obliczania dla wybranych kolumn

W tym przykładzie formuła obliczeń **E=C.340** oznacza, że obliczenia w komórce w kolumnie C, wiersz 340, są wykonywane tylko w kolumnie E **Uwaga:** jeśli do kolumny odwołuje się formuła obliczania, znak @ nie jest wymagany.

| Kod wiersza | Opis                 | Kod formatu | Powiązane formuły/wiersze/jednostka | Sterowanie wydrukiem | Modyfikator wiersza | Łącze do wymiarów finansowych |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Gotówka na początku okresu |             |                            | NP            | BB           | + Konto =\[1100:1110\]       |
| 370      | Gotówka na początku roku   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Gotówka na początku okresu | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Modyfikowanie liczb w wybranych kolumn

Jeśli modyfikujesz liczbę lub obliczenie w jednej kolumnie określonego wiersza, ale nie chcesz zmieniać innych kolumn w raporcie, możesz określić opcję **CAL** (obliczenie) w kolumnie **Kod formatu** dla definicji wiersza.

-   Aby wykonać obliczenie we wszystkich kolumnach raportu (**FD**), nie wpisuj przypisania kolumny.
-   Aby ograniczyć formuły do określonych kolumn, wpisz literę kolumny, znak równości (**=**), a następnie formułę.
-   Możesz określić wiele kolumn. Kiedy używasz znaku @ dla danego położenia kolumny, znak @ jest powiązany z wierszem.
-   Możesz wprowadzić wiele formuł kolumn w jednym wierszu. Formuły należy oddzielić przecinkami.

### <a name="calculation-examples"></a>Przykłady obliczeń

| Obliczenie            | Tworzone działanie                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Dla każdej kolumny wartość w wierszu 130 jest mnożona przez 0,75. Wynik jest następnie umieszczany w bieżącym wierszu każdej kolumny. |
| B=@130\*.75            | To samo obliczenie jest wykonywane tylko w kolumnie B.                                                                      |
| A, B,C=(@100/@130)\*.75 | A=(A.100/A.130)\*.75 B=(B.100/B.130)\*.75 C=(C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>Instrukcje IF/THEN/ELSE w definicji wiersza

Instrukcje **IF/THEN/ELSE** można dodawać do wszystkich prawidłowych obliczeń i używane z formatem **CAL**. Formuły obliczeń **IF/THEN/ELSE** wpisuje się w komórce w kolumnie **Powiązane formuły/wiersze/jednostki**. **ELSE-IF/THEN** obliczenia formuły, użyj następującego formatu: IF &lt;instrukcji PRAWDA/FAŁSZ&gt; następnie &lt;formuła&gt; ELSE &lt;formuła&gt;**ELSE &lt;formuła&gt;** część instrukcji jest opcjonalne.

#### <a name="if-statements"></a>Instrukcje IF

Instrukcja, która występuje po instrukcji **IF**, może być dowolną instrukcją, która może zostać oceniona jako prawda (true) lub fałsz (false). Instrukcja, która występuje po instrukcji **IF**, może zawierać prostą ocenę lub może być złożoną instrukcją zawierającą wiele wyrażeń. Oto kilka przykładów:

-   **Jeśli A.200&gt;0** (ocena prosty)
-   **Jeśli A.200&gt;0 i A.200&lt;10 000** (oświadczenie złożone)
-   **Jeśli A.200&gt;10000 lub ((A.340/B.1200)\*2 &lt;1200)** (złożonych instrukcji, która zawiera wiele wyrażeń)

Wyrażenie **Okresy** w instrukcji **IF** określa liczbę okresów dla raportu. Ten termin jest zwykle używany do obliczania średniej od początku roku. Na przykład po uruchomieniu raportu za okres 7 od początku roku instrukcja **B.150/Okresy** oznacza, że wartość w wierszu 150 kolumny B jest dzielona przez 7.

#### <a name="then-and-else-formulas"></a>Formuły THEN i ELSE

Formuły **THEN** i **ELSE** mogą być dowolnym prawidłowym obliczeniem od bardzo prostych przypisań wartości do złożonych formuł. Na przykład, instrukcja **IF A.200&gt;0, a następnie A=B.200** oznacza "Jeśli"wartość w komórce w kolumnie A 200 wierszy jest więcej niż 0 (zero), umieścić wartość z komórki w kolumnie B rzędu 200 komórek w kolumnie A bieżącego wiersza. Instrukcja **IF/THEN**, która występuje przed nią, wstawia wartość w jednej kolumnie bieżącego wiersza. Można jednak również użyć znaku @ w ocenie prawda/fałsz lub w formule, aby określić wszystkie kolumny. Oto kilka innych przykładów, które są opisane w następujących sekcjach:

-   **Jeśli A.200 &gt;0, a następnie B.200**: Jeżeli wartość w komórce A.200 jest dodatnia, wartość z komórki B.200 jest umieszczana w każdej kolumny bieżącego wiersza.
-   **Jeśli A.200 &gt;następnie 0 @200**: Jeżeli wartość w komórce A.200 jest dodatnia, wartość z każdej kolumny w wierszu 200 jest umieszczana w odpowiedniej kolumny w bieżącym wierszu.
-   **Jeśli @200&gt;następnie 0 @200**: Jeżeli wartość rzędu 200 bieżącej kolumny jest dodatnia, wartość rzędu 200 jest umieszczana w tej samej kolumnie w bieżącym wierszu.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Ograniczanie obliczenia do jednostki raportowania w definicji wiersza

Aby ograniczyć obliczeń do pojedynczej jednostki raportowania w drzewie raportowania, tak, że wynikająca stąd kwota nie jest rzutowany jednostce wyższego poziomu, można użyć **@Unit**kod w **powiązane formuły/wiersze/jednostki** komórki w definicji wiersza. **@Unit**Kod znajduje się w kolumnie B raportowania drzewo **nazwa jednostki**. Użycie **@Unit**kod, wartości nie są rzutowane, ale obliczenia jest sprawdzane na każdym poziomie drzewa raportowania. **Uwaga:** do korzystania z tej funkcji raportowania drzewo muszą być skojarzone z definicją wiersza. Wiersz obliczania może odnosić się do wiersza obliczania lub wiersza danych finansowych. Obliczenie jest rejestrowane w komórce **Powiązane formuły/wiersze/jednostki** definicji wiersza i ograniczeniu typu danych finansowych. Obliczeń należy użyć warunkowych obliczeń, który zaczyna się od **IF @Unit**konstrukcji. Oto przykład: IF @Unit(sprzedaży) następnie @100ELSE 0 to obliczenie obejmuje kwoty z wiersza 100 w każdej kolumnie raportu, ale tylko dla jednostki sprzedaży. Jeśli wiele jednostek ma nazwę SPRZEDAŻ, kwota pojawia się w każdej z tych jednostek. Ponadto wiersz 100 może być wierszem danych finansowych i może być zdefiniowany jako niedrukowany. W takim przypadku kwota nie pojawia się we wszystkich jednostkach drzewa. Można też ograniczyć kwotę do jednej kolumny raportu, np. kolumny H, korzystając z ograniczenia kolumny, aby drukować tylko wartość widoczną w tej kolumnie raportu. Można uwzględnić kombinacje **OR** w instrukcji **IF**. Oto przykład: IF @Unit(sprzedaż) lub @Unit(SALESWEST), następnie 5 ELSE @100ograniczenie typu kalkulacji można określić jednostkę w jednym z następujących sposobów:

-   Wprowadź nazwę jednostki, aby uwzględnić jednostki, które spełniają kryteria. Na przykład **IF @Unit(sprzedaż)** umożliwia obliczanie dla każdej jednostki o nazwie Sprzedaż, nawet jeśli istnieje kilka jednostek sprzedaży w drzewie raportowania.
-   Wpisz nazwę firmy i jednostki, aby ograniczyć obliczenia do określonych jednostek w wybranej firmie. Na przykład wpisz **IF @Unit(ACME: sprzedaż**) do ograniczenia obliczeń do jednostek sprzedaży w firmie xyz.
-   Wpisz pełny kod hierarchii z drzewa raportowania, aby ograniczyć obliczanie do określonej jednostki. Na przykład wpisz **IF @Unit(podsumowanie ^ ACME ^ zachodniego wybrzeża ^ sprzedaży)**. **Uwaga:** Aby znaleźć pełen kod hierarchii, kliknij prawym przyciskiem w definicji drzewa raportowania, a następnie wybierz **Kopiuj identyfikator jednostki raportowania (kod H)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Ograniczanie obliczenia do jednostki raportowania

1.  W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2.  Kliknij dwukrotnie komórkę **Kod formatu**, a następnie wybierz opcję **CAL**.
3.  Kliknij **powiązane formuły/wiersze/jednostki** komórki, a następnie wprowadź warunkowych obliczeń, który zaczyna się od **IF @Unit**konstrukcji.

### <a name="ifthenelse-statements-in-a-column-definition"></a>Instrukcje IF/THEN/ELSE w definicji kolumny

Instrukcja **IF/THEN/ELSE** pozwala uzależnić każde obliczenie od wyników z dowolnej innej kolumny. Można się odwoływać do innych kolumn, ale nie można odwołać się do komórki raportu w instrukcji **IF**. Każde obliczenie musi być stosowane do całej kolumny. Na przykład, instrukcja **IF B&gt;100, a następnie B C innego\*1,25** oznacza, "kwotę podaną w kolumnie B jest większa niż 100, umieścić wartość z kolumny B w **CALC** kolumny. Jeśli wartość w kolumnie B nie jest większa niż 100, pomnóż wartość w kolumnie C przez 1,25 i umieścić wynik w kolumnie **CALC**”. Po instrukcji **IF** musi zawsze występować instrukcja logiczna, która może być oceniona jako prawdziwa lub fałszywa. Formuły używane do instrukcji **THEN** i **ELSE** mogą zawierać odwołania do dowolnej liczby kolumn i te formuły mogą być dowolnie złożone. **Uwaga:** nie można umieszczać wyników obliczeń w dowolnej innej kolumnie. Wyniki muszą być w kolumnie zawierające formułę.


