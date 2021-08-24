---
title: Modyfikowanie komórek definicji wiersza
description: W tym temacie opisano informacje, które są wymagane dla każdej komórki w definicji wiersza w raporcie finansowym, oraz wyjaśniono, jak wprowadzić te informacje.
author: ShylaThompson
ms.date: 02/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e0bab0c9ecff1161612a6654209735b23a40aa6d085c6e83cdd44d3bf41e8b5e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734727"
---
# <a name="modify-row-definition-cells"></a>Modyfikowanie komórek definicji wiersza

[!include [banner](../includes/banner.md)]

W tym temacie opisano informacje, które są wymagane dla każdej komórki w definicji wiersza w raporcie finansowym, oraz wyjaśniono, jak wprowadzić te informacje.

## <a name="specify-a-row-code-in-a-row-definition"></a>Określanie kodu wiersza w definicji wiersza

W definicjach wierszy numery lub etykiety w komórce **Kod wiersza** identyfikują poszczególne wiersze w definicji wiersza. Kod wiersza można umieszczać w obliczeniach i sumach w roli odnośnika do danych.

### <a name="row-code-requirements"></a>Wymagania dotyczące kodu wiersza

Każdy wiersz musi mieć swój kod wiersza. W jednej definicji wiersza można łączyć ze sobą numeryczne, alfanumeryczne i nieustawione (puste) kody wiersza. Kod wiersza może być dowolną dodatnią liczbą całkowitą (mniejszą niż 100 000 000) lub etykietą opisową identyfikującą dany wiersz. Etykieta opisowa musi być zgodna z następującymi regułami:

- Etykieta musi zaczynać od litery (a-z lub A-Z) i może być dowolną kombinacją maksymalnie 16 cyfr i liter.

    > [!NOTE]
    > Etykieta może zawierać znaki podkreślenia (\_), ale inne znaki specjalne są niedozwolone.

- Etykieta nie może zawierać następujących słów zastrzeżonych: AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO i RPO.

Oto przykłady prawidłowych kodów wiersza:

- 320
- TL\_NET\_INCOME
- TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Zmienianie kodu wiersza w definicji wiersza

1. W Projektancie raportów kliknij **Definicje wierszy**, a następnie otwórz definicję wiersza, którą chcesz zmodyfikować.
2. W odpowiednim wierszu wpisz nową wartość w komórce w kolumnie **Kod wiersza**.

### <a name="reset-numeric-row-codes"></a>Resetowanie numerycznych kodów wiersza

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2. W menu **Edycja** kliknij **Zmień numerację wierszy**.
3. W oknie dialogowym **Zmiana numeracji wierszy** określ nowe wartości dla początkowego kodu wiersza i przyrostu kodu wiersza. Kody numeryczne wierszy można zresetować do równomiernie rozłożonych wartości. Projektant raportów zmienia numerację tylko dla kodów wierszy, które zaczynają się od numerów (np. 130 lub 246). Nie zmienia kodów wierszy numerycznych zaczynających się od liter (np. INCOME\_93 lub TP0693).

> [!NOTE]
> Podczas zmiany numeracji kodów wierszy projektant raportów automatycznie aktualizuje odwołania **TOT** i **CAL**. Na przykład jeśli **TOT** w wierszu odwołuje się do zakresu, który rozpoczyna się od kodu wiersza 100, i ponownie numeruje wiersze, począwszy od 90, początkowe odwołanie **TOT** zmienia się ze 100 na 90.

## <a name="add-a-description"></a>Dodawanie opisu
Komórka opisu zawiera opis danych finansowych w wierszu raportu, na przykład „Przychód” lub „Dochód netto”. Tekst w komórce **Opis** pojawia się w raporcie dokładnie tak, jak został wprowadzony w definicji wiersza.

> [!NOTE]
> Szerokość kolumny opisu w raporcie jest ustawiona w definicji kolumny. Jeśli tekst w kolumnie **Opis** w definicji wiersza jest długi, sprawdź szerokość kolumny **DESC**. Gdy okna dialogowego **Wstawianie wierszy z**, wartości w kolumnie **Opis** są wartościami segmentu lub wartościami wymiaru z danych finansowych. Można wstawić wiersze w celu dodania tekstu opisowego, np. nagłówka sekcji albo sumy sekcji, oraz dodać formatowanie, np. wiersz przed wierszem podsumowania. Jeśli raport zawiera drzewo raportowania, można dołączyć dodatkowy tekst, który jest zdefiniowany dla jednostek raportowania w drzewie raportowania. Istnieje również możliwość ograniczenia dodatkowego tekstu do określonej jednostki raportowania.

### <a name="add-the-description-for-a-line-on-a-report"></a>Dodawanie opisu dla wiersza w raporcie

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2. Wybierz komórkę **Opis**, a następnie wprowadź nazwę wiersza raportu.
3. Zastosuj formatowanie.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Dodawanie tekstu dodatkowego z drzewa raportowania w opisie

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2. Wprowadź kod dodatkowego tekstu i dowolny tekst w odpowiedniej komórce **Opis**.
3. Zastosuj formatowanie.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Ograniczanie dodatkowego tekstu do określonej jednostki raportowania

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2. Znajdź wiersz, gdzie dodatkowy tekst ma zostać utworzony, a następnie kliknij dwukrotnie komórkę w kolumnie **Powiązane formuły/wiersze/jednostki**.
3. W oknie dialogowym **Wybór jednostki raportowania** w polu **Drzewo raportowania** wybierz drzewo raportowania.
4. W polu **Wybieranie jednostki raportowania do ograniczenia** rozwiń lub zwiń drzewo raportowania, a następnie wybierz jednostkę raportowania.

## <a name="add-a-format-code"></a>Dodawanie kodu formatu
Komórka **Kod formatu** pozwala wybrać wstępnie sformatowane elementy zawartości tego wiersza. Jeśli komórka **Kod formatu** jest pusta, wiersz jest interpretowany jako wiersz szczegółów danych finansowych.

> [!NOTE]
> Jeśli raport zawiera wiersze z formatowaniem niekwotowym, które są powiązane z wierszami kwoty, które zostały pominięte (np. z powodu zerowych sald), można użyć kolumny **Powiązane formuły/wiersze/jednostki**, aby zapobiec drukowaniu wierszy tytułu i formatu.

### <a name="add-a-format-code-to-a-report-row"></a>Dodawanie kodu formatu do wiersza raportu

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie wybierz wiersz do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Kod formatu**.
3. Wybierz kod formatu z listy. Poniższa tabela opisuje kody formatów i związane z nimi akcje.

    | Kod formatu                   | Interpretacja kodu formatu | Akcja |
    |-------------------------------|-----------------------------------|--------|
    | (Brak)                        |                                   | Usuwa zawartość komórki **Kod formatu**. |
    | TOT                           | Suma                             | Określa wiersz używający operatorów matematycznych w kolumnie **Powiązane formuły/wiersze/jednostki**. Sumy zawierają proste operatory, takie jak **+** lub **-**. |
    | CAL                           | Obliczenie                       | Określa wiersz używający operatorów matematycznych w kolumnie **Powiązane formuły/wiersze/jednostki**. Obliczenia zawierają złożone operatory, takie jak **+**, **-**, **\**_, _*/**, oraz instrukcje **IF/THEN/ELSE**. |
    | DES                           | opis                       | Określa wiersz nagłówka lub pusty wiersz w raporcie. |
    | LFT RGT CEN                   | Lewo Prawo Środek                 | Wyrównuje tekst opisu wiersza na stronie raportu, niezależnie od miejsca tego tekstu w definicji kolumny. |
    | CBR                           | Zmiana wiersza podstawowego                   | Identyfikuje wiersz, który ustawia wiersz podstawowy w obliczeniach kolumny. |
    | COLUMN                        | Podział kolumny                      | Rozpoczyna nową kolumnę w raporcie. |
    | PAGE                          | Podział strony                        | Rozpoczyna nową stronę w raporcie. |
    | \---                          | Pojedyncze podkreślenie                  | Podkreśla wszystkie kolumny kwoty w raporcie pojedynczą linią. |
    | ===                           | Podwójne podkreślenie                  | Podkreśla wszystkie kolumny kwoty w raporcie podwójną linią. |
    | LINE1                         | Cienka linia                         | Rysuje pojedynczą cienką linię w poprzek strony. |
    | LINE2                         | Gruba linia                        | Rysuje pojedynczą grubą linię na stronie. |
    | LINE3                         | Linia kropkowana                       | Rysuje pojedynczą przerywaną linię w poprzek strony. |
    | LINE4                         | Pogrubiona linia i cienka linia          | Rysuje podwójną cienką linię w poprzek strony. Górna linia jest pogrubiona, a dolna linia jest cienka. |
    | LINE5                         | Cienka linia i pogrubiona linia          | Rysuje podwójną cienką linię w poprzek strony. Górna linia jest cienka, a dolna linia jest pogrubiona. |
    | BXB BXC                       | Wiersz obrysowany                         | Rysuje pole wokół wiersza raportu, które zaczyna się wierszem **BXB**, a kończy wierszem **BXC**. |
    | REM                           | Uwaga                            | Identyfikuje wiersz będący komentarzem, który nie powinien być drukowany w raporcie. Na przykład, w wierszu uwagi można opisać techniki formatowania. |
    | SORT ASORT SORTDESC ASORTDESC | Sortuj                              | Sortuje przychody lub wydatki, sortuje raport odchyleń rzeczywistych lub budżetowych według największej wartości lub sortuje opisy wierszy alfabetycznie. |

## <a name="specify-related-formulasrowsunits"></a>Określanie powiązanych formuł/wierszy/jednostek
Komórka **Powiązane formuły/wiersze/jednostki** ma wiele zastosowań. W zależności od typu wiersza komórka **Powiązane formuły/wiersze/jednostki** można wykonywać jedną z następujących funkcji:

- Określanie wierszy do uwzględnienia o obliczeniu, gdy używany jest kod formatu **TOT** lub **CAL**.
- Łączenie wiersza formatowania z wierszem kwoty, aby formatowanie było drukowane tylko wtedy, gdy jest drukowana powiązana kwota.
- Ograniczanie wiersza do określonej jednostki raportowania.
- Określanie wiersza podstawowego dla obliczeń, jeśli używany jest kod formatu **BASEROW**.
- Określanie wierszy do sortowania, gdy używany jest dowolny z kodów formatu sortowania.

### <a name="use-a-row-total-in-a-row-definition"></a>Używanie sumy wiersza w definicji wiersza

Formuła sumy wiersza pozwala dodawać lub odejmować kwoty w innych wierszach. Formuła tworzenia sumy wiersza może zawierać operatory + i -, umożliwiające łączenie pojedynczych kodów i zakresów wiersza. Zakresy są oznaczone dwukropkiem (:). Kod może zawierać maksymalnie 1024 znaki. Oto przykładowa standardowa formuła: 400+420+430+450+460ZOBOWIĄZANIA+KAPITAŁWŁASNY520:546520:546-ZOBOWIĄZANIA

### <a name="components-of-a-row-total-formula"></a>Składniki formuły sumy wierszy

Podczas tworzenia formuły sumy wierszy należy za pomocą kodów wierszy wskazać, które wiersze w bieżącej definicji wiersza mają być dodawane lub odejmowane, oraz za pomocą operatorów wskazać sposób połączenia wierszy. Wiersze sum i kwot mogą występować w dowolnych kombinacjach.

> [!NOTE]
> Operacja nie obejmuje żadnych wierszy sum należących do zakresu. Aby utworzyć sumę końcową, można określić wiele zakresów wierszy. Jeśli pierwszy wiersz zakresu jest wierszem sumy, ten wiersz jest uwzględniany w nowej sumie. Poniższa tabela opisuje sposób używania operatorów w formułach sumy wierszy.

| Operator | Przykładowa formuła | opis                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Dodaje kwotę w wierszu 100 do kwoty w wierszu 330.        |
| :        | 100:330         | Dodaje sumy wszystkich wierszy od wiersza 100 do wiersza 330.    |
| -        | 100-330         | Odejmuje kwotę w wierszu 100 od kwoty w wierszu 330. |

### <a name="create-a-row-total"></a>Tworzenie sumy wierszy

1. W Projektancie raportów kliknij pozycję **Definicje wierszy**, a następnie otwórz definicję wiersza, którą chcesz zmodyfikować.
2. Kliknij dwukrotnie komórkę **Kod formatu** w definicji wiersza, a następnie wybierz opcję **TOT**.
3. W komórce **Powiązane formuły/wiersze/jednostki** wpisz formułę sumy.

### <a name="relate-a-format-row-to-an-amount-row"></a>Wiązanie wiersza formatu z wierszem kwoty

W kolumnie **Kod formatu** w definicji wiersza kody formatu **DES**, **LFT**, **RGT**, **CEN**, **---** i **===** stosują formatowanie do wierszy niekwotowych. Aby to formatowanie nie było drukowane, gdy powiązane wiersze kwoty są pominięte (np. z powodu wartości zerowych w wierszach kwoty lub braku aktywności w okresie), trzeba powiązać wiersze formuły z odpowiednimi wierszami kwoty. Ta funkcja jest przydatna, jeśli chcesz zapobiec drukowaniu nagłówków lub formatowania sum częściowych, gdy dany okres nie zawiera informacji do wydrukowania.

> [!NOTE]
> Można również zapobiegać drukowaniu szczegółowych wierszy kwoty, usuwając zaznaczenie opcji wyświetlania wierszy bez kwot. Ta opcja znajduje się na karcie **Ustawienia** w definicji raportu. Domyślnie konta szczegółów transakcji, które mają zerowe saldo lub nie mają aktywności w okresie, są blokowane w raportach. Aby wyświetlić te konta szczegółów transakcji, zaznacz pole wyboru **Wyświetlaj wiersze bez kwot** na karcie **Ustawienia** w definicji raportu.

### <a name="relate-a-format-row-to-an-amount-row"></a>Wiązanie wiersza formatu z wierszem kwoty

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie wybierz wiersz do zmodyfikowania.
2. W wierszu formatowania w komórce **Powiązane formuły/wiersze/jednostki** wpisz kod wiersza kwoty, który ma być pomijany.

    > [!NOTE]
    > Aby pominąć wiersz kwoty, saldo wiersza musi mieć wartość 0 (zero). Wiersz kwoty z saldem nie jest pomijany.

3. W menu **Plik** kliknij **Zapisz**.

### <a name="example-of-preventing-printing-of-rows"></a>Przykład zapobiegania drukowaniu wierszy

W poniższym przykładzie użytkownik chce zapobiec drukowaniu nagłówków i podkreśleń w wierszu **Gotówka — razem**, ponieważ na żadnym z kont kasowych nie było aktywności. W związku z tym w wierszu 220 (który jest wierszem formatowania, na co wskazuje kod formatu **---**) w komórce **Powiązane formuły/wiersze/jednostki** użytkownik wprowadza wartość **250**, czyli numer kodu wiersza, który chce pomijać podczas drukowania.

[![RelatedRowsRowDefinition.](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Wybieranie wiersza podstawowego dla obliczeń kolumny
W raportach relacyjnych można przypisać jeden lub więcej wierszy podstawowych w definicji wiersza za pomocą kodu formatu **CBR** (zmień wiersz podstawowy). Do wiersza podstawowy odwołuje się następnie obliczenie w definicji kolumny. Oto kilka typowych przykładów obliczeń CBR:

- Procent całkowitych przychodów w odniesieniu do poszczególnych składników przychodów
- Procent całkowitych wydatków w odniesieniu do poszczególnych składników wydatków
- Procent marży brutto w odniesieniu do szczegółów oddziału lub działu.

W definicji wiersza określany jest co najmniej jeden wiersz podstawowy, a następnie definicja kolumny określa relację, według której wiersz podstawowy jest raportowany. Kod używany w formule kolumny to **BASEROW**. Z kodem **BASEROW** używane są następujące podstawowe działania matematyczne: dzielenie, mnożenie, dodawanie lub odejmowanie. Najczęściej używaną operacją jest dzielenie przez **BASEROW**, a jej wynik jest wyświetlany w postaci procentowej Obliczenia kolumny, które używają **BASEROW** w formule, używają definicji wiersza dla powiązanych kodów wiersza podstawowego. Wiersze **CBR** mają następującą charakterystykę:

- Wiersze **CBR** nie są drukowane na gotowym raporcie.
- Kod formatu **CBR** i kod powiązanego z nim wiersza są umieszczone powyżej wiersza lub sekcji, w których są wyświetlane powiązane obliczenia.

W definicji kolumn typ kolumny **CALC** wskazuje kolumnę określającą formułę w wierszu **Formuła**. Ta formuła działa tylko w odniesieniu do danych w tej kolumnie raportu i używa słowa kluczowego Baserow, aby oprzeć obliczenia na kodach formatu **CBR** w wierszu. W definicji wiersza kod formatu **CBR** definiuje podstawowy wiersz dla kolumn, które obliczają wartość procentową lub są mnożone przez wiersz podstawowy dla każdego wiersza w raporcie. W formacie wiersza może być wiele kodów formatu **CBR**, np. jeden dla sprzedaży netto, jeden dla sprzedaży brutto i jeden dla łącznych wydatków. Zazwyczaj kod formatu **CBR** służy do tworzenia wartości procentowej dla kont, które są porównywane z wierszem sumy. Wiersz podstawowy jest używany dla wszystkich obliczeń, dopóki nie zostanie zdefiniowany inny wiersz podstawowy. Należy określić początkowy kod formatu **CBR** i końcowy kod formatu **CBR**. Na przykład aby określić wydatki jako procent sprzedaży netto, można podzielić wartości w każdym wierszu wydatków przez wartość w wierszu sprzedaży netto. W takim przypadku wiersz sprzedaży netto jest wierszem podstawowym. Można określić definicję kolumny, która raportuje wyniki bieżące i od początku roku, razem z procentem podstawowym dla każdego wyniku, ja, pokazano w poniższym przykładzie. Zacznij od szczegółowego rachunku wyników.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Wybieranie wiersza podstawowego w definicji wiersza dla obliczenia kolumny

1. W Projektancie raportów kliknij **Definicje kolumn**, a następnie otwórz definicje kolumny dla rachunku wyników.
2. Dodaj nową kolumnę do definicji kolumny i ustaw typ kolumny na **CALC**.
3. W komórce **Formuła** dla nowej kolumny wpisz formułę **X/BASEROW**, gdzie **X** jest typem kolumny **FD**, której procent ma być widoczny.
4. Kliknij dwukrotnie komórkę **Zmiana formatu/waluty**.
5. W oknie dialogowym **Zmiana Format** na liście **Kategoria formatu** wybierz **Procent**, a następnie kliknij przycisk **OK**.
6. W menu **Plik** kliknij **Zapisz jako**, aby zapisać definicję kolumny pod nową nazwą. Dołącz **CBR** do bieżącej nazwy pliku (na przykład **CUR\_YTD\_CBR**). Ta definicja kolumny jest definicją kolumny wiersza podstawowego.
7. W Projektancie raportów kliknij przycisk **Definicje wierszy**, a następnie otwórz definicję wiersza do zmiany za pomocą obliczenia wiersza podstawowego.
8. Wstaw nowy wiersz powyżej wiersza, gdzie powinno rozpoczynać się obliczenie wiersza podstawowego.
9. Kliknij dwukrotnie komórkę **Kod formatu** w definicji wiersza, a następnie wybierz opcję **CBR**.
10. W komórce **Powiązane formuły/wiersze/jednostki** wpisz wprowadzić numer kodu wiersza dla wiersza podstawowego.

### <a name="example-of-base-row-calculation"></a>Przykład obliczania wiersza podstawowego

W poniższym przykładzie definicji wiersza wiersz 100 pokazuje, że wierszem podstawowym dla obliczeń jest wiersz 280.

[![Przykład obliczania wiersza podstawowego.](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png)

W poniższym przykładzie definicji kolumny w obliczeniach używany jest kod formatu **CBR**. Obliczenia w kolumnie C dzieli wartość w kolumnie B raportu według wartości określonej w wierszu 280 kolumny B. Zmiana formatu w kolumnie B drukuje wynik obliczenia jako wartość procentową. Podobnie każda kwota w kolumnie E jest kwotą w kolumnie D przedstawioną w postaci wartości procentowej sprzedaży netto.

[![Przykład definicji kolumny.](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png)

W poniższym przykładzie pokazano raport, który może zostać wygenerowany na podstawie poprzednich obliczeń.

[![Przykład raportu na podstawie poprzednich obliczeń przykładowych.](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Wybieranie kodu sortowania dla definicji wiersza
Kody sortowania sortują konta lub wartości, sortują raport odchyleń rzeczywistych lub budżetowych według największej wartości lub sortują opisy wierszy alfabetycznie. Dostępne są następujące kody sortowania:

- **SORT** – sortuje raport w kolejności rosnącej na podstawie wartości w określonej kolumnie.
- **ASORT** – sortuje raport w kolejności rosnącej na podstawie wartości bezwzględnej dla wartości w określonej kolumnie. To znaczy, że znak poszczególnych wartości jest ignorowany podczas sortowania wartości. Ten kod formatu ustawia wartości w sekwencji według wielkości odchylenia, niezależnie od tego, czy odchylenie jest dodatnie lub ujemne.
- **SORTDESC** – sortuje raport w kolejności malejącej na podstawie wartości w określonej kolumnie.
- **ASORTDESC** – sortuje raport w kolejności malejącej na podstawie wartości bezwzględnej dla wartości w określonej kolumnie.

### <a name="select-a-sorting-code"></a>Wybieranie kodu sortowania

1. W Projektancie raportów kliknij **Definicje wiersza**, a następnie otwórz definicje wiersza do zmodyfikowania.
2. Kliknij dwukrotnie komórkę **Kod formatu**, a następnie wybierz opcję kod sortowania.
3. W komórce **Powiązane formuły/wiersze/jednostki** należy określić zakres kodów wiersza do sortowania. Aby określić zakres, należy wprowadzić kod pierwszego wiersza, dwukropek (:) i kod ostatniego wiersza. Na przykład wpisz **160:490**, aby określić, że zakres obejmuje wiersze od 160 do 490.
4. W komórce **Ograniczenia kolumny** należy wprowadzić literę kolumny raportu, która ma być użyta do sortowania.

    > [!NOTE]
    > W obliczeniach sortowania należy uwzględniać tylko wiersze kwoty.

### <a name="examples-of-ascending-and-descending-column-values"></a>Przykłady wartości kolumn w porządku rosnącym i malejącym

W poniższym przykładzie wartości w kolumnie D raportu zostaną posortowane rosnąco dla wierszy od 160 do 490. Ponadto wartości bezwzględne w kolumnie G raportu zostaną posortowane w kolejności malejącej od wiersza 610 do 940.

| Kod wiersza | Opis                                         | Kod formatu | Powiązane formuły/wiersze/jednostki | Saldo zwykłe | Ograniczenie kolumny | Łącze do Wymiary finansowe |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Posortowane według miesięcznego odchylenia w kolejności rosnącej       | DES         |                             |                |                    |                              |
| 130      |                                                     | SORT        | 160:490                     |                | D                  |                              |
| 160      | Sprzedaż                                               |             |                             | C              |                    | 4100                         |
| 190      | Zwroty sprzedaży                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | Przychody z tytułu odsetek                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | Posortowane według odchylenia bezwzględnego od początku roku w kolejności malejącej | DES         |                             |                |                    |                              |
| 580      |                                                     | ASORTDESC   | 610:940                     |                | G                  |                              |
| 610      | Sprzedaż                                               |             |                             | F              |                    | 4 100                         |
| 640      | Zwroty sprzedaży                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | Dochód z odsetek                                     |             |                             | F              |                    | 7 000                         |


## <a name="specify-a-format-override-cell"></a>Określanie komórki Zmiana formatu
Komórka **Zmiana formatu** określa format, który jest używany dla wiersza podczas drukowania raportu. To formatowanie ma wyższy priorytet od formatowania określonego w definicji kolumny i definicji raportu. Domyślnie w tych definicjach określone jest formatowanie walutowe. Jeśli jeden wiersz raportu zawiera liczbę środków trwałych, np. liczbę budynków, a inny wiersz zawiera wartość pieniężną tych środków trwałych, można zastąpić formatowanie walutowe i wprowadzić formatowanie numeryczne dla wiersza, który określa liczbę budynków. Można określić te informacje w oknie dialogowym **Zmiana formatu**. Dostępne opcje zależą od wybranej kategorii format. Obszar **Próbka** okna dialogowego pokazuje przykładowe formaty. Dostępne są następujące formaty kategorii:

- Formatowanie walutowe
- Formatowanie liczbowe
- Formatowanie procentowe
- Formatowanie niestandardowe

### <a name="override-cell-formatting"></a>Zmiana formatu komórki

1. W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2. W wierszu, w którym ma być zmieniony format, kliknij dwukrotnie komórkę w kolumnie **Zmiana formatu**.
3. W oknie dialogowym **Zmiana formatu** wybierz opcje formatowania dla tego wiersza w raporcie.
4. Kliknij przycisk **OK**

### <a name="currency-formatting"></a>Formatowanie walutowe

Formatowanie walutowe ma zastosowanie do kwoty obrachunkowej i zawiera symbol waluty. Dostępne są następujące opcje:

- **Symbol waluty** — symbol waluty dla raportu. Ta wartość zastępuje ustawienie **Opcje regionalne** dla informacji o firmie.
- **Liczby ujemne** — liczby ujemne mają znak minus (-), mogą pojawiać się w nawiasach lub mogą być oznaczone trójkątem (∆).
- **Miejsca dziesiętne** — liczba wyświetlanych miejsc po przecinku.
- **Zastąp test z wartością zero** — tekst, który trzeba wstawić w raporcie, gdy kwota wynosi 0 (zero). Ten tekst jest widoczny w ostatnim wierszu w **Próbka**.

    > [!NOTE]
    > Jeśli drukowanie nie jest pomijane dla wartości zerowych lub braku aktywności w okresie, ten tekst jest pomijany.

### <a name="numeric-formatting"></a>Formatowanie liczbowe

Formatowanie numeryczne jest stosowane do dowolnej kwoty i nie zawiera symbolu waluty. Dostępne są następujące opcje:

- **Liczby ujemne** — liczby ujemne mają znak minus (-), mogą pojawiać się w nawiasach lub mogą być oznaczone trójkątem (∆).
- **Miejsca dziesiętne** — liczba wyświetlanych miejsc po przecinku.
- **Zastąp test z wartością zero** — tekst, który trzeba wstawić w raporcie, gdy kwota wynosi 0 (zero). Ten tekst jest widoczny w ostatnim wierszu w **Próbka**.

    > [!NOTE]
    > Jeśli drukowanie nie jest pomijane dla wartości zerowych lub braku aktywności w okresie, ten tekst jest pomijany.

### <a name="percentage-formatting"></a>Formatowanie procentowe

Formatowanie procentowe zawiera znak procentów (%). Dostępne są następujące opcje:

- **Liczby ujemne** — liczby ujemne mają znak minus (-), mogą pojawiać się w nawiasach lub mogą być oznaczone trójkątem (∆).
- **Miejsca dziesiętne** — liczba wyświetlanych miejsc po przecinku.
- **Zastąp test z wartością zero** — tekst, który trzeba wstawić w raporcie, gdy kwota wynosi 0 (zero). Ten tekst jest widoczny w ostatnim wierszu w **Próbka**.

    > [!NOTE]
    > Jeśli drukowanie nie jest pomijane dla wartości zerowych lub braku aktywności w okresie, ten tekst jest pomijany.

### <a name="custom-formatting"></a>Formatowanie niestandardowe

Za pomocą formatowania niestandardowego można tworzyć własne formaty nadrzędne. Dostępne są następujące opcje:

- **Typ** — format niestandardowy.
- **Zastąp test z wartością zero** — tekst, który trzeba wstawić w raporcie, gdy kwota wynosi 0 (zero). Ten tekst jest widoczny w ostatnim wierszu w **Próbka**.

    > [!NOTE]
    > Jeśli drukowanie nie jest pomijane dla wartości zerowych lub braku aktywności w okresie, ten tekst jest pomijany.

Typ powinien być przestawiać wartość dodatnią, a następnie wartość ujemną. Zazwyczaj wprowadza się podobny format, który odróżnia wartości dodatnie od ujemnych. Na przykład aby określić, że ujemne i dodatnie wartości mają dwa miejsca dziesiętne, ale wartości ujemne są wyświetlane w nawiasach, wprowadź **0,00;(0,00)**. W poniższej tabeli przedstawiono formaty niestandardowe, których można używać do kontroli formatów wartości. Wszystkie przykłady zaczynają się od wartości 1234,56.

| Format                         | Dodatnia   | Ujemne     | Zerowe    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);""       | 1 235      | (1 235)      | (Puste) |
| \#,\#\#0.00;(\#,\#\#0.00);zero | 1 234,56   | (1 234,56)   | zero    |
| 0,00%;(0,00%)                  | 123456,00% | (123456,00%) | 0,00%   |

## <a name="specify-a-normal-balance-cell"></a>Określanie komórki zwykłego salda
Komórka **Zwykłe saldo** w definicji wiersza określa znak kwoty w wierszu. Aby zmienić znak wiersza lub jeśli zwykłe saldo konta jest transakcją kredytową, wpisz **C** w komórce **Zwykłe saldo** tego wiersza. Projektant raportów odwraca znak dla wszystkich kont z saldami kredytowymi w tym wierszu. Gdy projektant raportów konwertuje te konta, usuwa cechę debet/kredyt ze wszystkich kwot, co upraszcza sumowanie. Na przykład aby obliczyć zysk netto, odejmuje się wydatki od przychodów. Zwykle sumowane i obliczone wiersze nie są uwzględnione w kodzie **C**. Jednak formant drukowania **XCR** w definicji kolumny odwraca znak każdego wiersza zawierającego **C** w kolumnie **Zwykłe saldo**. To formatowanie jest szczególnie ważne, jeśli chce się pokazać wszystkie niekorzystna odchylenia jako kwoty ujemne. Jeśli zsumowana lub obliczona liczba ma zły znak, wpisz **C** w komórce **Zwykłe saldo** dla wiersza, aby go odwrócić.

## <a name="specify-a-row-modifier-cell"></a>Określ komórkę Modyfikator wiersza
Zawartość komórki **Modyfikator wiersza** w definicji wiersza zastępuje lata obrachunkowe, okresy obrachunkowe i informacje określone w definicji kolumny dla tego wiersza. Wybrany modyfikator ma zastosowanie do każdego konta w wierszu. Każdy wiersz można zmodyfikować przy użyciu następujących typów modyfikacji:

- Modyfikatory konta
- Modyfikatory kody księgi
- Atrybuty konta i transakcji

### <a name="override-a-column-definition"></a>Zastępowanie definicji kolumny

1. W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2. W wierszu, w którym chcesz zastąpić definicję kolumny, kliknij dwukrotnie komórkę **Modyfikator wiersza**.
3. W oknie dialogowym **Modyfikator wiersza** wybierz opcję w polu **Modyfikator konta**. Opis opcji znajdziesz w sekcji „Modyfikatory konta”.
4. W polu **Modyfikator kodu księgi** wybierz kod księgi dla wiersza.
5. W obszarze **Atrybuty** wykonaj następujące kroki, aby dodać wpis dla każdego atrybutu, który powinien być uwzględniony w kodzie wiersza:

    1. Kliknij dwukrotnie komórkę **Atrybut** i wybierz nazwę atrybutu.

        > [!IMPORTANT]
        > Zastąp znak numeru (\#) wartością liczbową.

    2. Kliknij dwukrotnie komórkę **Z** i wpisz pierwszą wartość dla zakresu.
    3. Kliknij dwukrotnie komórkę **Do** i wpisz ostatnią wartość dla zakresu.

6. Kliknij przycisk **OK**

### <a name="account-modifiers"></a>Modyfikatory konta

Po wybraniu określonego konta projektant raportów zwykle łączy konta i lata obrachunkowe, okresy obrachunkowe i inne informacje określone w definicji kolumny. Można używać różnych informacji, takich jak różne okresy obrachunkowe, dla określonych wierszy. W poniższej tabeli przedstawiono dostępne modyfikatory kont. Zmień znak numeru (\#) na wartość, która jest równa lub mniejsza niż liczba okresów w roku obrachunkowym.

| Modyfikator konta | Co jest drukowane                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | Saldo początkowe dla konta.                                                     |
| /\#              | Saldo dla określonego okresu.                                                     |
| /-\#             | Saldo dla okresu, który jest \# okresów przed bieżącym okresem.                  |
| /+\#             | Saldo dla okresu, który jest \# okresów po bieżącym okresie.                   |
| /C               | Saldo dla bieżącego okresu.                                                       |
| /C-\#            | Saldo dla okresu, który jest \# okresów przed bieżącym okresem.                  |
| /C+\#            | Saldo dla okresu, który jest \# okresów po bieżącym okresie.                   |
| /Y               | Saldo od początku roku do bieżącego okresu.                                      |
| /Y-\#            | Saldo od początku roku do okresu, który jest \# okresów przed bieżącym okresem. |
| /Y+\#            | Saldo od początku roku do okresu, który jest \# okresów po bieżącym okresie.  |

### <a name="book-code-modifiers"></a>Modyfikatory kody księgi

Możesz ograniczyć wiersz do istniejącego kodu księgi. Definicja kolumny musi zawierać co najmniej jedną kolumnę **FD**, która ma kod księgi.

> [!NOTE]
> Ograniczenie kodu księgi dla wiersza zastępuje ograniczenia kodu księgi w definicji kolumny dla tego wiersza.

### <a name="account-and-transaction-attributes"></a>Atrybuty kont i transakcji

Niektóre systemy księgowe obsługują atrybuty konta i atrybuty transakcji w danych finansowych. Te atrybuty działają na zasadzie podobnie jak wirtualne segmenty kont i mogą zawierać dodatkowe informacje dotyczące konta lub transakcji. Te dodatkowe informacje mogą być identyfikatorami konta, identyfikatorami partii, kodami pocztowymi lub innymi atrybutami. Jeśli system księgowy obsługuje atrybuty, możesz używać atrybutów konta lub transakcji jako modyfikatorów wierszy w definicji wiersza. Aby uzyskać informacje dotyczące sposobu zastępowania informacji wiersza, zobacz sekcję „Zastępowanie definicji kolumny” we wcześniejszej części tego artykułu.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>Określanie łącza do komórki wymiarów finansowych
Komórka **Łącze do wymiarów finansowych** zawiera łącza do danych finansowych, które powinny znajdować się w każdym wierszu raportu. Ta komórka zawiera wartości wymiarów. Aby otworzyć okno dialogowe **Wymiary** kliknij dwukrotnie komórkę **Łącze do wymiarów finansowych**.

> [!NOTE]
> Projektant raportów nie można wybierać kont, wymiarów ani pól z systemu Microsoft Dynamics ERP, który zawiera jakiekolwiek z następujących znaków zarezerwowanych: &, \*, \[, \], { lub }. Aby określić informacje dla wiersza, który jest już wymieniony w definicji wierszy, należy dodać informacje w komórce **Łącze do Wymiary finansowe**. Aby dodać nowe wiersze połączone z danymi finansowymi, użyj okna dialogowego **Wstaw wiersze z**, aby utworzyć nowe wiersze w definicji raportu. Tytuł kolumny zmienia się w zależności od tego, jak kolumna jest skonfigurowana i wyświetlana w następującej tabeli.

| Typ łącza, które jest zaznaczone       | Opis kolumny Łącze zmienia się na ten tekst |
|----------------------------------|----------------------------------------------------|
| Wymiary finansowe             | Łącze do wymiarów finansowych                       |
| Arkusz raportu                 | Raport z raportowania finansowego                         |

### <a name="specify-a-dimension-or-range"></a>Określanie wymiaru lub zakresu

1. W Projektancie raportów otwórz definicję wierszy, którą chcesz zmodyfikować.
2. Kliknij dwukrotnie komórkę w kolumnie **Łącze do Wymiary finansowe**.
3. W oknie dialogowym **Wymiary** kliknij dwukrotnie komórkę pod nazwą wymiaru.
4. W oknie dialogowym wymiaru wybierz **Pojedynczy lub zakres**.
5. W polu **Od** wprowadź wymiar początkowy lub kliknij przycisk ![Przeglądaj.](media/browse.gif "Przeglądaj") aby wyszukać dostępne wymiary. Aby wprowadzić zakres wymiarów, należy wprowadzić wymiar końcowy w polu **Do**.
6. Kliknij **OK**, aby zamknąć okno dialogowe wymiaru. Okno dialogowe **Wymiary** wyświetla zaktualizowane wymiary lub zakresy.
7. Kliknij **OK**, aby zamknąć okno dialogowe **Wymiary**.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Wyświetlanie kont o saldzie zerowym w definicji wiersza
Domyślnie projektant raportów nie drukuje wierszy, które nie mają odnośnego salda w danych finansowych. W związku z tym można utworzyć jedną definicję wiersza, która obejmuje wszystkie wartości segmentu naturalnego lub wszystkie wartości wymiaru, a następnie użyć tej definicji wiersza dla działów w organizacji.

### <a name="modify-zero-balance-settings"></a>Modyfikowanie ustawień salda zerowego

1. W Projektancie raportu otwórz definicję raportu do zmodyfikowania.
2. Na karcie **Ustawienia** w obszarze **Inne formatowanie** wybierz opcję dla definicji wiersza, która jest używana w definicji raportu.
3. W menu **Plik** kliknij **Zapisz**, aby zapisać zmiany.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Używanie symboli wieloznacznych i zakresów w definicji wiersza
Po wprowadzeniu wartości segmentu naturalnego w oknie dialogowym **Wymiary** możesz wstawić symbol wieloznaczny (? lub \*) w dowolnym miejscu segmentu. Projektant raportów wyodrębnienia wszystkie wartości dla zdefiniowanych pozycji bez uwzględniania symboli wieloznacznych. Na przykład definicja wiersza zawiera tylko wartości naturalnych segmentów, a naturalne segmenty mają cztery znaki. Wprowadzając w wierszu wartość **6???**, tworzysz instrukcję dla projektanta raportów, aby uwzględniał wszystkie konta, które mają wartość naturalnego segmentu zaczynającą się od cyfry 6. Jeśli wprowadzisz **6\**_, zwracane są te same wyniki, ale obejmują one również wartości o różnej szerokości, takie jak _* 60** i **600000**. Projektant raportów zastępuje poszczególne symbole wieloznaczne (?) pełnym zakresem możliwych wartości, co obejmuje litery i znaki specjalne. Na przykład w zakresie od **12?0** do **12?4**, symbol wieloznaczny w kombinacji **12?0** jest zastępowany najniższą wartością w zestawie znaków, a symbol wieloznaczny w kombinacji **12? 4** jest zastępowany najwyższą wartością w zestawie znaków.

> [!NOTE]
> Należy unikać używania symboli wieloznacznych dla kont na początkach i końcach zakresów. Używanie symboli wieloznacznych w konta początkowych lub końcowych może dawać nieoczekiwane wyniki.

### <a name="single-segment-or-single-dimension-ranges"></a>Zakresy z jednym segmentem lub jednym wymiarem

Można określić zakres wartości segmentów lub wartości wymiarów. Zaletą określania zakresu jest to, że nie trzeba aktualizować definicji wiersza za każdym razem, gdy do danych finansowych dodawana jest nowa wartość segmentu lub wartość wymiaru. Na przykład zakres **+Konto=\[6100:6900\]** pobiera wartości z kont od 6100 do 6900 do kwoty wiersza. Gdy zakres zawiera symbol wieloznaczny (?), projektant raportów nie ocenia zakresu na zasadzie znak po znaku. Zamiast tego określane są niższe i wyższe krańce zakresu, a następnie uwzględniane są wartości krańcowe i wszystkie wartości między nimi.

> [!NOTE]
> Projektant raportów nie można wybierać kont, wymiarów ani pól z systemu Microsoft Dynamics ERP, który zawiera jakiekolwiek z następujących znaków zarezerwowanych: &, \*, \[, \], { lub }. Można dodać znak „&” tylko w przypadku automatycznego tworzenia definicji wierszy przy użyciu okna dialogowego **Wstawianie wierszy z wymiarów**.

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Zakresy z wieloma segmentami lub wieloma wymiarami

Jeśli wprowadzany jest zakres przy użyciu kombinacji wielu wartości wymiaru, porównanie zakresu jest wykonywane na ..\\wymiarach finansowych\\zasadzie wymiar po wymiarze. Porównanie zakresu nie może być wykonywane ani na zasadzie znak po znaku ani na podstawie segmentu częściowego. Na przykład zakres **+Konto=\[5000:6000\], Dział=\[1000:2000\], Centrum kosztu=\[00\]** zawiera tylko konta, które pasują do każdego segmentu. W tym scenariuszu pierwszy wymiar musi mieścić się w zakresie od 5000 do 6000, drugi wymiar musi mieścić się w zakresie od 1000 do 2000, a ostatni wymiar musi mieć wartość 00. Na przykład **+Konto=\[5100\], Dział=\[1100\], Centrum kosztu=\[01\]** nie jest uwzględniony w raporcie, ponieważ ostatni segment nie mieści się w określonym zakresie. Jeśli wartość segmentu zawiera spacje, należy umieścić tę wartość w nawiasach kwadratowych (\[ \]). Następujące wartości są prawidłowe dla segmentu złożonego z czterech znaków: **\[ 234\], \[123 \], \[1 34\]**. Wartości wymiarów powinny być ujęte w nawiasy kwadratowe (\[ \]), a projektant raportów dodaje te nawiasy samodzielnie. Jeśli zakres obejmujący wiele segmentów lub wiele wymiarów zawiera symbole wieloznaczne (? lub \*), określane są górne i dolne krańce całego zakresu złożonego z wielu segmentów lub wielu wymiarów, a następnie dodawane są wartości krańcowe i wszystkie wartości między nimi. Jeśli zakres jest duży, np. cały zakres kont od 40000 do 99999, należy określić prawidłowe konto początkowe i końcowe, jeśli jest to możliwe.

> [!NOTE] 
> Projektant raportów nie można wybierać kont, wymiarów ani pól z systemu Microsoft Dynamics ERP, który zawiera jakiekolwiek z następujących znaków zarezerwowanych: &, \*, \[, \], { lub }. Można dodać znak „&” tylko w przypadku automatycznego tworzenia definicji wierszy przy użyciu okna dialogowego **Wstawianie wierszy z wymiarów**.

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Dodawanie i odejmowanie z innych kont w definicji wiersza
Aby dodać lub odjąć kwoty pieniężne na jednym koncie z kwot pieniężnych na innym koncie, można użyć znaku plus (+) i znaku minus (-) w komórce **Łącze do wymiarów finansowych**. W poniższej tabeli przedstawiono dopuszczalne formaty dla dodawania i odejmowania łącz do danych finansowych.

| Operacja                                                                               | Użyj następującego formatu                                                                                              |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Dodaj dwa konta w pełni kwalifikowane.                                                       | +Oddział=\[000\], Konto=\[1205\], Dział=\[00\]+Oddział=\[100\], Konto=\[1205\], Dział=\[00\] |
| Dodaj dwie wartości segmentów.                                                                 | +Konto=\[1205\]+Konto=\[1210\]                                                                           |
| Dodaj wartości segmentów zawierające symbole wieloznaczne.                                    | +Konto=\[120?+Konto=\[11??\]                                                                             |
| Dodaj zakres kont w pełni kwalifikowanych.                                                | +Oddział=\[000:100\], Konto=\[1205\], Dział=\[00\]                                                   |
| Dodaj zakres wartości segmentów.                                                          | +Konto=\[1200:1205\]                                                                                       |
| Dodaj zakres wartości segmentów z symbolami wieloznacznymi.                         | +Konto=\[120?:130?\]                                                                                       |
| Odejmij jedno konto w pełni kwalifikowane od innego konta w pełni kwalifikowanego.              | +Oddział=\[000\], Konto=\[1205\], Dział=\[00\]-Oddział=\[100\], Konto=\[1205\], Dział=\[00\] |
| Odejmij wartość jednego segmentu od wartości innego segmentu.                                  | +Konto=\[1205\]-Konto=\[1210\]                                                                           |
| Odejmij wartość segmentu zawierającą symbol wieloznaczny od wartości innego segmentu. | +Konto=\[1200\]-Konto=\[11??\]                                                                           |
| Odejmij zakres kont w pełni kwalifikowanych.                                           | -Oddział=\[000:100\], Konto=\[1200:1205\], Dział=\[00:01\]                                           |
| Odejmij zakres wartości segmentów.                                                     | -Konto=\[1200:1205\]                                                                                       |
| Odejmij zakres wartości segmentów z symbolami wieloznacznymi.                    | -Konto=\[120?:130?\]                                                                                       |

Chociaż można modyfikować konta bezpośrednio, można również użyć okna dialogowego **Wymiary**, aby zastosować prawidłowe formatowanie do łącza danych finansowych. Każda z wartości może zawierać symbole wieloznaczne (? lub \*). Projektant raportów nie można jednak wybierać kont, wymiarów ani pól z systemu Microsoft Dynamics ERP, który zawiera jakiekolwiek z następujących znaków zarezerwowanych: &, \*, \[, \], { lub }.

> [!NOTE]
> W celu odjęcia wartości należy je umieścić w nawiasach. Na przykład jeśli wpiszesz operację **450?-(4509)**, będzie ona wyświetlana jako **+Konto=\[4509\]-Konto=\[450?\]**, a projektant otrzymuje instrukcję odejmowania kwoty dla segmentu konta 4509 od kwoty dla każdego segmentu konta, który rozpoczyna się od 450.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Dodawanie kont do innych kont i odejmowanie kont od innych kont

1. W Projektancie raportu otwórz definicję wiersza do zmodyfikowania.
2. W odpowiednim wierszu kliknij dwukrotnie komórkę w kolumnie **Łącze do wymiarów finansowych**.
3. W pierwszym wierszu okna dialogowego **Wymiary** wykonaj następujące kroki:

    1. W pierwszym polu wybierz wszystkie wymiary (domyślnie) lub kliknij, aby otworzyć okno dialogowe **Zarządzanie zestawami wymiarów**, w którym można utworzyć, zmodyfikować, skopiować lub usunąć zestaw.
    2. Kliknij dwukrotnie komórkę **Operator +/-** i wybierz operator plus (**+**) lub minus (**-**), który ma zastosowanie do jednej lub kilku wartości wymiarów lub zestawów w wierszu.
    3. W odpowiedniej kolumnie wartość wymiaru kliknij dwukrotnie komórkę, aby otworzyć okno dialogowe **Wymiary** i wybierz, czy dana wartość wymiaru dotyczy pojedynczej wartości lub zakresu, zestawu wartości wymiarów czy kont sumujących. Opisy pól dostępnych w oknie dialogowym **Wymiary** można znaleźć w sekcji „Opis okna dialogowego wymiaru”.
    4. Wpisz wartości segmentu w kolumnie **Od** i kolumnie **Do**.

4. Powtórz kroki od 2 do 3, aby dodać więcej operacji.

> [!NOTE]
> Operator ma zastosowanie do wszystkich wymiarów w wierszu.

## <a name="description-of-the-dimensions-dialog-box"></a>Opis okna dialogowego Wymiary
W poniższej tabeli opisano pola w tym oknie dialogowym **Wymiary**.

| Pozycja                | Opis |
|---------------------|-------------|
| Pojedynczy lub zakres | W polu **Z** wpisz nazwę konta lub kliknij przycisk **Przeglądaj** ![Przeglądaj](media/browse.gif "Przeglądaj") aby wyszukać konto. Aby wybrać zakres, wpisz lub przeglądaj, aby wybrać wartość w polu **Do**. |
| Zestaw wartości wymiarów | W polu **Nazwa** wprowadź nazwę zestawu wartości wymiarów. Aby utworzyć, zmodyfikować lub usunąć zestaw, kliknij **Zarządzaj zestawami wartości wymiarów**. Pole **Formuła** jest wypełniane przy użyciu formuły z komórki **Łącze do wymiarów finansowych** dla tego zestawu wartości wymiarów w definicji wiersza. |
| Konta sumujące   | W polu **Nazwa** wprowadź lub przeglądaj, aby wybrać wymiar kont sumujących. Pole **Formuła** jest wypełniane przy użyciu formuły w komórce **Łącze do wymiarów finansowych** dla tego konta sumującego w definicji raportowania. |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Dodawanie zestawów wartości wymiarów w definicji wiersza
Zestaw wartości wymiarów jest nazwaną grupą wartości wymiarów. Zestaw wartości wymiarów może zawierać wartości tylko w jednym wymiarze, ale można używać wartości wymiaru w wielu definicjach wierszy, kolumn, drzewa raportowania i definicjach raportów. Można również połączyć zestawy wartości wymiarów w definicji raportu. Jeśli modyfikacja danych finansowych wymaga zmiany zestawu wartości wymiarów, można zaktualizować definicję zestawu wartości wymiarów i ta aktualizacja ma zastosowanie do wszystkich obszarów, które używają zestawu wartości wymiarów. Na przykład jeśli często wskazujesz zakres wartości do połączenia z danymi finansowymi, np. wartości od 5100 do 5600, możesz przypisać ten zakres do zestawu kont o nazwie Sprzedaż. Po utworzeniu zestawu wartości wymiaru można wybrać ten zestaw jako łącze danych finansowych. Inny przykład: jeśli zakres wartości od 5100 do 5600 jest przypisany do wartości Sprzedaż, a wartość 4175 jest przypisana do wartości Rabaty, można wyznaczyć łączną wartość sprzedaży, odejmując wartość Rabaty od wartości Sprzedaż. Taka operacja jest wyrażana jako **(5100:5600)-4175**.

### <a name="create-a-set-of-dimension-values"></a>Tworzenie zestawu wartości wymiarów

1. W Projektancie raportów otwórz definicję wiersza, kolumny lub drzewa raportowania do zmodyfikowania.
2. W menu **Edycja** kliknij **Zarządzaj zestawami wartości wymiarów**.
3. W oknie dialogowym **Zarządzanie zestawami wartości wymiarów** w polu **Wymiar** wybierz typ zestawu wartości wymiarów do utworzenia, a następnie kliknij **Nowy**.
4. W oknie dialogowym **Nowy** wprowadź nazwę i opis dla zestawu.
5. W kolumnie **Z** kliknij dwukrotnie w komórce.
6. W oknie dialogowym **Konto** wybierz nazwę z listy lub wyszukaj wpisu w polu **Szukaj**. Następnie kliknij **OK**.
7. Powtórz kroki od 5 do 6 w kolumnie **Do**, aby zaprojektować formułę dla operatora.
8. Po zakończeniu formuły kliknij przycisk **OK**.
9. W oknie dialogowym **Zarządzaj zestawami wymiarów** kliknij przycisk **Zamknij**.

### <a name="update-a-set-of-dimension-values"></a>Aktualizowanie zestawu wartości wymiaru

1. W Projektancie raportów otwórz definicję wierszy, kolumn lub drzewa, którą chcesz zmodyfikować.
2. W menu **Edycja** kliknij **Zarządzaj zestawami wartości wymiarów**.
3. W oknie dialogowym **Zarządzanie zestawami wartości wymiarów** w polu **Wymiar** wybierz typ wymiaru.
4. Na liście wymierz zestaw wartości wymiarów do aktualizacji, a następnie kliknij **Modyfikuj**.
5. W oknie dialogowym **Modyfikowanie** modyfikuj wartości formuły, które mają znaleźć się w zestawie.

    > [!NOTE]
    > Jeśli dodajesz nowe konta lub wymiary, pamiętaj, aby zmodyfikować istniejące zestawy wartości wymiaru, tak aby uwzględniały zmiany.

6. Kliknij dwukrotnie komórkę, a następnie wybierz odpowiedni operator, konto **Z** i konto **Do**.
7. Kliknij **OK**, aby zamknąć okno dialogowe **Modyfikowanie** i zapisz zmiany.

### <a name="copy-a-dimension-set"></a>Kopiowanie zestawu wymiarów

1. W Projektancie raportów otwórz definicję wiersza, kolumny lub drzewa raportowania do zmodyfikowania.
2. W menu **Edycja** kliknij **Zarządzaj zestawami wartości wymiarów**.
3. W oknie dialogowym **Zarządzanie zestawami wartości wymiarów** w polu **Wymiar** wybierz typ wymiaru.
4. Z listy wybierz zestaw do skopiowania i kliknij **Zapisz jako**.
5. Wprowadź nową nazwę skopiowanego zestawu i kliknij **OK**.

### <a name="delete-a-dimension-set"></a>Usuwanie zestawu wymiarów

1. W Projektancie raportów otwórz definicję wierszy, kolumn lub drzewa, którą chcesz zmodyfikować.
2. W menu **Edycja** kliknij **Zarządzaj zestawami wartości wymiarów**.
3. W oknie dialogowym **Zarządzanie zestawami wartości wymiarów** w polu **Wymiar** wybierz typ wymiaru.
4. Wybierz zestaw, który chcesz usunąć, a następnie kliknij przycisk **Usuń**. Kliknij przycisk **Tak**, aby trwale usunąć zestaw wartości wymiaru.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie finansowe](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]