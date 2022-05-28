---
title: Przychody i odroczenia wydatków w ramach fakturowania subskrypcji
description: W tym temacie wyjaśniono, jak skonfigurować odroczenia przychodów i kosztów w rozliczaniu subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2021
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
ms.openlocfilehash: 9a12cf52d904db0396aa9914b8e324060289710f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690956"
---
# <a name="revenue-and-expense-deferrals-in-subscription-billing"></a>Przychody i odroczenia wydatków w ramach fakturowania subskrypcji

W tym temacie wyjaśniono, jak skonfigurować i używać odroczeń przychodów i kosztów w rozliczeniach Subskrypcji. Harmonogramy odroczeń są zawsze oparte na dokumencie źródłowym lub harmonogramie fakturowania i na nich zależą. Ponieważ są tworzone na podstawie wartości domyślnych, nie można ich wprowadzać ani tworzyć osobno.

Proces konfigurowania i używania odroczeń przychodów i wydatków odbywa się na wielu stronach:

- Na stronie Parametry **kosztów i przychodów odroczeń** można zdefiniować preferencje firmy.
- Na stronie **Ustawienia domyślne** odroczeń można skonfigurować domyślne konta i szablony używane dla harmonogramów odroczeń.
- Na stronach **szablonów odroczeń** i **szablonów odroczeń opartych na zdarzeniach** można definiować szablony używane dla harmonogramów odroczeń.
- Na stronie **Wszystkie harmonogramy odroczeń** można wyświetlać i edytować harmonogram odroczeń.

Odroczenia przychodów i wydatków mogą być używane razem z cyklicznym fakturowaniem umowy.

## <a name="revenue-and-expense-deferral-parameters"></a>Parametry odroczenia przychodów i wydatków

Strona **Parametry przychodów i odroczeń wydatków** zawiera następujące pola.

| Pole | Opis |
|---|---| 
| Karta **harmonogramu** | |
| Równe dla okresu | <p>Służy do określania, czy liczba dni w okresie jest używana podczas obliczania kwoty na okres dla harmonogramu odroczeń:</p><ul><li>**Tak** — kwota dla każdego okresu jest taka sama, niezależnie od liczby dni okresu. Okresy częściowe (takie jak okresy na początku lub na końcu harmonogramu odroczeń) będą proporcjonalnie.</li><li>**Nie** – Kwota ta jest obliczana na podstawie liczby dni w każdym okresie.</li></ul><p>To ustawienie można zastąpić na poziomie transakcji.</p> |
| Opcja odroczenia rabatu sprzedaży | <p>Umożliwia określenie, czy dla kwot rabatu i zamówienia sprzedaży są tworzone osobne harmonogramy odroczeń:</p><ul><li>**Oddzielny harmonogram dla rabatu** — kwota rabatu jest przechowywana oddzielnie od kwoty przychodu.<p>W takim przypadku podczas tworzenia i zaksięgowania zamówienia sprzedaży są tworzone dwa harmonogramy odroczeń. Kwoty rabatu i przychodu będą księgowane na różnych kontach odroczeń.</p></li><li>**Scal rabat z przychodem** — kwota rabatu jest łączona z kwotą przychodu. Tworzony jest jeden harmonogram odroczeń, a kwota rabatu i kwota przychodu są księgowane na tym samym koncie odroczeń.<p>W tym przypadku jeden harmonogram odroczeń jest tworzony w momencie utworzenia, a następnie zaksięgowania zamówienia sprzedaży. Kwota rabatu i kwota przychodu są księgowane na tym samym koncie odroczeń.</p></li></ul><p>**Uwaga:** Aby zastosować rabaty do towarów, które korzystają z funkcji nieskomplifikowanych przychodów, wybierz opcję **Oddziel harmonogram dla rabatu**. Rabaty można stosować do wszystkich towarów, niezależnie od tego, czy jest używana funkcja nieskomplifikowanych przychodów. Jeśli jest zaznaczona opcja **Scal rabat z przychodem**, nie można stosować rabatów do towarów, dla których jest stosowana funkcja Niebilonowany przychód.</p> |
| Opcja odroczenia rabatu zakupu | <p>Wybierz, czy dla kwot rabatu i zamówienia zakupu mają być tworzone osobne harmonogramy odroczeń:</p><ul><li>**Oddzielny harmonogram dla rabatu** — Kwota rabatu jest przechowywana oddzielnie od kwoty wydatków.<p>W tym przypadku podczas tworzenia, a następnie księgowania zamówienia zakupu tworzone są dwa harmonogramy odroczeń. Kwoty rabatu i kosztów są księgowane na różnych kontach odroczeń.</p></li><li>**Scal rabat z przychodem** — Kwota rabatu jest łączona z kwotą wydatków. Tworzony jest jeden harmonogram odroczeń, a zarówno kwota rabatu, jak i kwota wydatku są księgowane na tym samym koncie odroczeń.<p>W tym przypadku jeden harmonogram odroczeń jest tworzony w momencie utworzenia, a następnie zaksięgowania zamówienia zakupu. Zarówno kwota rabatu, jak i kwota wydatku są księgowane na tym samym koncie odroczeń.</p></li></ul> |
| Konsoliduj poprzednie okresy | <p>Określ, czy wiersze harmonogramu odroczeń dla poprzednich okresów mają być konsolidowane:</p><ul><li>**Tak** — jeśli data rozpoczęcia odroczenia znajduje się w okresie przed datą transakcji, wszystkie kwoty w okresie daty transakcji są łączone w jednym wierszu harmonogramu odroczeń.</li><li>**Nie** — Kwoty ze wszystkich okresów są przechowywane w oddzielnych wierszach harmonogramu odroczeń.<p>Jeśli data rozpoczęcia odroczenia należy do tego samego okresu lub późniejsza niż data transakcji, ta opcja nie ma wpływu.</p></li></ul><p>Ustawienie to można aktualizować na poziomie transakcji.</p> |
| Domyślna data początkowa odroczenia | <p>Umożliwia wybór reguły używanej do określania daty rozpoczęcia harmonogramu odroczeń:</p><ul><li>**Data transakcji** – Jako daty początkowej należy użyć daty transakcji.</li><li>**Początek bieżącego miesiąca** — jako daty rozpoczęcia należy użyć pierwszego z bieżącego miesiąca. Jeśli data transakcji jest pierwszym miesiącem, datą rozpoczęcia jest pierwszy z bieżącego miesiąca.</li><li>**Początek następnego miesiąca** — jako daty rozpoczęcia należy użyć pierwszego następnego miesiąca. Jeśli data transakcji znajduje się na pierwszym miejscu, używana jest data transakcji. W przeciwnym razie zostanie użyty pierwszy dzień następnego miesiąca.</li><li>**Reguła 15** — jeśli data transakcji należy do okresu od pierwszego do piętnastego, jako daty rozpoczęcia należy użyć pierwszego dnia bieżącego miesiąca. Jeśli data transakcji jest szesnastego dnia lub późniejsza, jako datę początkową należy przyjąć pierwszy dzień następnego miesiąca.</li></ul><p>Ustawienie to można aktualizować na poziomie transakcji.</p> |
| Metoda odroczeń krótkoterminowych | <p>Wybierz metodę odroczenia krótkoterminowego: **Brak**, **Okresy do zakańczania** lub **Stały rok**</p><p>|
| Metoda księgowania odroczenia | <p>Wybierz metodę, która jest używana do tworzenia transakcji odroczenia:</p><ul><li>**Bilans** — do tworzenia transakcji odroczeń należy użyć metody księgowania bilansowego.</li><li>**Wynikowe** – Do tworzenia transakcji z odroczonym terminem płatności należy stosować metodę księgowania zysków i strat. Podczas zaksięgowania transakcji można przejrzeć załącznik faktury, aby zobaczyć dodatkowe wpisy, które bilansują początkowe rozpoznawanie i rozpoznawanie kwot przeciwstawnych.</li></ul> |
| Wycofaj zysk i stratę z kredytu | <p>**Uwaga:** Pole to jest dostępne tylko wtedy, gdy pole **Metoda księgowania odroczeń** jest ustawione na **Zyski i straty**.</p><p>Umożliwia określenie, czy kwoty zysków i strat mają być wycofywne w przypadku zastosowania wycofania, zakończenia lub zwrotu do harmonogramu fakturowania lub zamówienia sprzedaży:</p><ul><li>**Tak** — należy wycofać kwoty zysków i strat i zastosować kwotę korekty kredytu do harmonogramu odroczeń.<p>Jeśli cofnięcie ma miejsce w połowie okresu fakturowania, kwoty są proporcjonalnie.</p></li><li>**Nie** – Transakcja odwrócenia nie jest tworzona w rachunku zysków i strat, gdy odwrócenie, rozwiązanie lub zwrot są stosowane do harmonogramu rozliczeń lub zamówienia sprzedaży.</li></ul> |
| Karta **Rozpoznanie** | |
| Automatycznie księguj arkusze ogólne | <p>Umożliwia określenie, czy wpisy w arkuszu utworzone przez przychody i odroczenia wydatków mają być księgowane automatycznie:</p><ul><li>**Tak** – Automatyczne księgowanie wpisów do dziennika, które są tworzone przez odroczenia przychodów i kosztów.<p>**Porada:** wybranie opcji **Tak** pomaga zapobiec niespójnościom księgowania spowodowanym ręcznymi zmianami załączników.</p></li><li>**Nie** – Wpisy w dzienniku tworzone przez odroczenia przychodów i kosztów nie są automatycznie księgowane. Należy ręcznie zaksięgować żadnych arkuszy.</li></ul> |
| Podsumuj arkusz rozpoznania | <p>Umożliwia określenie, czy załączniki rozpoznawania mają być domyślnie konsolidowane:</p><ul><li>**Tak** — umożliwia utworzenie jednego załącznika dla wszystkich wierszy rozpoznawania o tej samej dacie. Wszystkie wiersze w załączniku, które mają to samo konto, są konsolidowane w jednym wierszu.</li><li>**Nie** — umożliwia utworzenie załącznika dla każdego wiersza rozpoznawania.</li></ul><p>To ustawienie można zaktualizować na stronie **Przetwarzanie rozpoznawania**.</p> |
| Domyślna nazwa arkusza | Umożliwia wybór nazwy arkusza dla arkuszy tworzona na podstawie procesów przychodów i wydatków związanych z odroczeniami, takich jak przetwarzanie rozpoznawania. |
| Opis wiersza arkusza rozpoznania | <p>Umożliwia wybór opisu wyświetlanego w opisie wiersza załącznika arkusza:</p><ul><li>**Zaplanuj daty wierszy** — w opisie wiersza arkusza są wyświetlane daty wierszy harmonogramu.</li><li>**Szczegóły transakcji pochodzącej** — w opisie wiersza arkusza są wyświetlane informacje o transakcji pochodzącej z transakcji.<p>**Przykład:** USMF-0001, CIV-00839, Przychód z oprogramowania</p></li></ul> |
| Karta **Sekwencje numerów** | Ta karta służy do ustawienia wartości domyślnych sekwencji numerów dzierżawy. Kreator generowania sekwencji numerów służy do automatycznego generowania i przypisywania sekwencji numerów. Nie trzeba zmieniać sekwencji numerów, jeśli trzeba ręcznie zmieniać wygenerowane sekwencje numerów. |
| Numer harmonogramu | Numer, który jest kolejno używany w harmonogramach odroczeń. |

## <a name="deferral-templates"></a>Szablony odroczenia

Strona **Szablony odroczeń umożliwia** definiowanie szablonów liniowych używanych do harmonogramów odroczeń.

Poniżej podano niektóre zalety używania szablonu:

* Długość odroczenia jest obliczana automatycznie.
* Można zezwalać na harmonogramy odroczeń, których okresy są pomijane.
* Odroczenia można automatyzować, przypisując szablon do produktu, grupy produktów, kategorii produktów, odbiorców lub grupy odbiorców. Przypisanie szablonu jest wykonywane ze strony **ustawień domyślnych odroczeń**.

Dla szablonów dostępnych jest kilka częstotliwości okresu: dzienne, miesięczne lub obrachunkowe.

Wiersze szablonu składają się z typu (**Rozpoznany** lub **Pominięty**) oraz długości okresu. Pominięte wiersze mają kwotę 0 (zero) w wierszach harmonogramu odroczeń. Takie działanie może być przydatne, jeśli użytkownik nie chce rozpoznawać przychodu we wszystkich okresach.

### <a name="create-a-deferral-template"></a>Utwórz szablon odroczenia

Aby utworzyć nowy szablon odroczenia, należy wykonać poniższe kroki.

1. Na stronie **Szablony odroczenia** wybierz opcję **Nowe**.
2. W polu **Szablon** wpisz nazwę.
3. W polu **Opis wprowadź** opis.
4. W polu **Częstotliwość okresu** wybierz częstotliwość okresu.
5. Wybierz **opcję Dodaj**, aby dodać wiersz u góry listy wierszy, lub wybierz opcję **Dołącz**, aby dodać wiersz u dołu listy.
6. W polu **Typ** wybierz typ okresu.
7. W polu **Długość okresu** podaj długość okresu.
8. Powtórz kroki od 5 do 7 dla każdej wymaganego dodatkowego wiersza.
9. Wybierz opcję **Zapisz**.

## <a name="deferral-defaults"></a>Ustawienia domyślne odroczenia

Strona **Ustawienia domyślne odroczeń** zawiera informacje o ustawianiu domyślnych kont odroczeń dla towarów i przypisywaniu szablonów domyślnych do towarów odroczonych. Można również skonfigurować konta odroczeń dla opłat i przypisać szablony do opłat odroczonych.

**Odrocz według pozycji**

W przypadku transakcji z towarami (na przykład zamówień sprzedaży) można przypisywać konta i szablony do określonych towarów i odbiorców. Te ustawienia będą używane jako wartości domyślne w przypadku odroczenia transakcji. Aby domyślnie odroczyć transakcję, trzeba skonfigurować towary na stronie **Towary do odroczeń**.

**Odrocz wedłuh konta**

W przypadku transakcji, które nie mają towarów (na przykład arkuszy finansowych), można określić konta odroczeń. Gdy te konta są używane w wierszu transakcji, transakcja jest automatycznie oznaczana jako odroczona. Odpowiedni szablon i konto rozpoznawania zostaną przypisane do wiersza transakcji.

**Wszystkie typy transakcji (na przykład na kartach Zamówienia sprzedaży, Zakupy i Arkusz ogólny)**

Konta na tej stronie są kontami głównymi, które nie mają wymiarów finansowych. Wymiary finansowe konta rozpoznawania są od odbiorcy lub towaru, w zależności od organizacji.

Każdy wiersz szablonu musi mieć szablon liniowy lub szablon oparty na zdarzeniach. Nie można mieć obu tych jednocześnie.

### <a name="for-sales-orders"></a>Zamówienia sprzedaży

Aby określić wartości domyślne odroczeń dla zamówień sprzedaży, należy wykonać następujące kroki.

1. Na karcie **Zamówienie sprzedaży** wybierz typ odroczenia.
2. Wybierz pozycję **Dodaj**, aby dodać drugi wiersz.
3. W polu **Kod pozycji** wybierz kod towaru. Kod towaru określa sposób stosowania wartości domyślnych odroczeń.
4. Umożliwia określenie sposobu stosowania kodu towaru:

    * Jeśli w polu **Kod elementu** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja elementu** należy wybrać relację elementu.
    * Jeśli w **polu Kod pozycji** zostanie ustawiona wartość **Kategoria**, wybierz relację kategorii w polu **Relacja kategorii**.
    * Jeśli w **polu Kod** towaru zostanie ustawiona wartość **Wszystkie**, wartości domyślne będą dotyczyć wszystkich odpowiednich rekordów.

5. Określenie sposobu stosowania kodu konta:

    * Jeśli w polu **Kod konta** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja konta** należy wybrać relację konta.
    * Jeśli w **polu Kod** konta zostanie ustawiona wartość **Wszystkie**, konta będą dotyczyć wszystkich odpowiednich rekordów.

6. W polu **Konto główne** wybierz konto główne dla odroczenia.
7. Jeśli w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowe**, należy wybrać początkowe konto przychodów w polu **Konto przychodów początkowych** oraz konto przeciwstawne przychodu w polu **Konto przeciwstawne przychodu**.
8. Jeśli w polu **Metoda odroczenia krótkoterminowego** jest ustawiona wartość **Okresy zawierania** lub **Stały rok**, w polu Konto odroczeń krótkoterminowych należy wybrać **konto odroczeń krótkoterminowych**.
9. W szablonie możesz wybrać opcję **Dodaj,** aby dodać wiersz.
10. W polu **Kod pozycji** wybierz kod towaru.
11. Umożliwia określenie sposobu stosowania kodu towaru:

    * Jeśli w polu **Kod elementu** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja elementu** należy wybrać relację elementu.
    * Jeśli w **polu Kod pozycji** zostanie ustawiona wartość **Kategoria**, wybierz relację kategorii w polu **Relacja kategorii**.
    * Jeśli w **polu Kod** towaru zostanie ustawiona wartość **Wszystkie**, wartości domyślne będą dotyczyć wszystkich odpowiednich rekordów.

12. Określenie sposobu stosowania kodu konta:

    * Jeśli w polu **Kod konta** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja konta** należy wybrać relację konta.
    * Jeśli w **polu Kod** konta zostanie ustawiona wartość **Wszystkie**, konta będą dotyczyć wszystkich odpowiednich rekordów.
    * Wybierz szablon liniowy w polu **Szablon liniowy** lub szablon oparty na zdarzeniach w polu **szablonu opartego na zdarzeniu**.

13. Wybierz opcję **Zapisz**.

### <a name="for-purchase-orders"></a>Zamówienia zakupu

Aby określić wartości domyślne odroczeń dla zamówień zakupu, należy wykonać następujące kroki.

1. Na karcie **Zamówienie zakupu** wybierz typ odroczenia.
2. Wybierz pozycję **Dodaj**, aby dodać drugi wiersz.
3. W polu **Kod pozycji** wybierz kod towaru.
4. Umożliwia określenie sposobu stosowania kodu towaru:

    * Jeśli w polu **Kod elementu** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja elementu** należy wybrać relację elementu.
    * Jeśli w **polu Kod pozycji** zostanie ustawiona wartość **Kategoria**, wybierz relację kategorii w polu **Relacja kategorii**.
    * Jeśli w **polu Kod** towaru zostanie ustawiona wartość **Wszystkie**, wartości domyślne będą dotyczyć wszystkich odpowiednich rekordów.

5. Określenie sposobu stosowania kodu konta:

    * Jeśli w polu **Kod konta** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja konta** należy wybrać relację konta.
    * Jeśli w **polu Kod** konta zostanie ustawiona wartość **Wszystkie**, konta będą dotyczyć wszystkich odpowiednich rekordów.

6. W polu **Konto główne** wybierz konto główne dla odroczenia.
7. Jeśli w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowe**, należy wybrać początkowe konto przychodów w polu **Konto przychodów początkowych** oraz konto przeciwstawne przychodu w polu **Konto przeciwstawne przychodu**.
8. Jeśli w polu **Metoda odroczenia krótkoterminowego** jest ustawiona wartość **Okresy zawierania** lub **Stały rok**, w polu Konto odroczeń krótkoterminowych należy wybrać **konto odroczeń krótkoterminowych**.
9. W szablonie możesz wybrać opcję **Dodaj,** aby dodać wiersz. 
10. W polu **Kod pozycji** wybierz kod towaru.
11. Umożliwia określenie sposobu stosowania kodu towaru:

    * Jeśli w polu **Kod elementu** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja elementu** należy wybrać relację elementu.
    * Jeśli w **polu Kod pozycji** zostanie ustawiona wartość **Kategoria**, wybierz relację kategorii w polu **Relacja kategorii**.
    * Jeśli w **polu Kod** towaru zostanie ustawiona wartość **Wszystkie**, wartości domyślne będą dotyczyć wszystkich odpowiednich rekordów.

12. Określenie sposobu stosowania kodu konta:

    * Jeśli w polu **Kod konta** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja konta** należy wybrać relację konta.
    * Jeśli w **polu Kod** konta zostanie ustawiona wartość **Wszystkie**, konta będą dotyczyć wszystkich odpowiednich rekordów.
    * Wybierz szablon liniowy w polu **Szablon liniowy** lub szablon oparty na zdarzeniach w polu **szablonu opartego na zdarzeniu**.

13. Wybierz opcję **Zapisz**.

### <a name="for-general-journals"></a>Dla arkuszy finansowych

Aby określić domyślne wartości odroczenia dla ogólnych zapisów dziennika, należy wykonać poniższe czynności.

1. Kliknij kartę **Arkusze finansowe**.
2. Dla odroczenia możesz wybrać opcję **Dodaj,** aby dodać wiersz.
3. Jeśli w polu **Metoda odroczenia krótkoterminowego** jest ustawiona wartość **Okresy zawierania** lub **Stały rok**, w polu Konto odroczeń krótkoterminowych należy wybrać **konto odroczeń krótkoterminowych**.
4. W polu **Konto odroczenia** wybierz konto odroczenia.
5. W polu **Konto rozpoznania** wybierz konto rozpoznania.
6. Jeśli w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowe**, należy wybrać początkowe konto przychodów w polu **Konto przychodów początkowych** oraz konto przeciwstawne przychodu w polu **Konto przeciwstawne przychodu**.
7. Wybierz szablon liniowy w polu **Szablon liniowy** lub szablon oparty na zdarzeniach w polu **szablonu opartego na zdarzeniu**.
8. Wybierz opcję **Zapisz**.

### <a name="for-free-text-invoices"></a>Faktury niezależne

Aby określić domyślne wartości odroczenia dla faktur niezależnych, wykonaj poniższe kroki.

1. Wybierz **Faktura niezależna**.
2. Dla odroczenia możesz wybrać opcję **Dodaj,** aby dodać wiersz.
3. Określenie sposobu stosowania kodu konta:

    * Jeśli w polu **Kod konta** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja konta** należy wybrać relację konta.
    * Jeśli w **polu Kod** konta zostanie ustawiona wartość **Wszystkie**, kody konta będą dotyczyć wszystkich odpowiednich rekordów.

4. W polu **Konto odroczenia** wybierz konto odroczenia.
5. Jeśli w polu **Metoda odroczenia krótkoterminowego** jest ustawiona wartość **Okresy zawierania** lub **Stały rok**, w polu Konto odroczeń krótkoterminowych należy wybrać **konto odroczeń krótkoterminowych**.
6. W polu **Konto rozpoznania** wybierz konto rozpoznania.
7. Jeśli w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowe**, należy wybrać początkowe konto przychodów w polu **Konto przychodów początkowych** oraz konto przeciwstawne przychodu w polu **Konto przeciwstawne przychodu**.
8. Wybierz szablon liniowy w polu **Szablon liniowy** lub szablon oparty na zdarzeniach w polu **szablonu opartego na zdarzeniu**.
9. Wybierz opcję **Zapisz**.

### <a name="for-invoice-journals"></a>Arkusze faktur dostawcy

Aby określić domyślne wartości odroczenia dla zapisów dziennika faktur, wykonaj poniższe kroki.

1. Kliknij kartę **Arkusz faktur**.
2. Dla odroczenia możesz wybrać opcję **Dodaj,** aby dodać wiersz.
3. Określenie sposobu stosowania kodu konta:

    * Jeśli w polu **Kod konta** ustawiono wartość **Tabela** lub **Grupa**, w polu **Relacja konta** należy wybrać relację konta.
    * Jeśli w **polu Kod** konta zostanie ustawiona wartość **Wszystkie**, kody konta będą dotyczyć wszystkich odpowiednich rekordów.

4. W polu **Konto odroczenia** wybierz konto odroczenia.
5. Jeśli w polu **Metoda odroczenia krótkoterminowego** jest ustawiona wartość **Okresy zawierania** lub **Stały rok**, w polu Konto odroczeń krótkoterminowych należy wybrać **konto odroczeń krótkoterminowych**.
6. W polu **Konto rozpoznania** wybierz konto rozpoznania.
7. Jeśli w polu **Metoda księgowania odroczeń** ustawiono wartość **Wynikowe**, należy wybrać początkowe konto przychodów w polu **Konto przychodów początkowych** oraz konto przeciwstawne przychodu w polu **Konto przeciwstawne przychodu**.
8. Wybierz szablon liniowy w polu **Szablon liniowy** lub szablon oparty na zdarzeniach w polu **szablonu opartego na zdarzeniu**.
9. Wybierz opcję **Zapisz**.

### <a name="items-that-are-deferred-by-default"></a>Pozycje odroczone domyślnie

Strona Towary **odroczone domyślnie służy** do definiowania, które towary są domyślnie odroczone. Można skonfigurować typy transakcji, dla których towary będą odroczone. Można określić, czy jeden towar jest odroczony, czy cała grupa lub kategoria towaru.

Po skonfigurowaniu towarów jako odroczonych wybierz domyślne konta i szablony na **stronie Ustawienia domyślne odroczeń**. Jeśli konta i szablony nie zostaną wybrane, wiersze transakcji, w których wprowadzone zostaną te towary, nie będą odroczone.

Dla towarów, które są odroczone na podstawie kategorii sprzedaży lub zakupu, z która jest skojarzona, ustawienia odroczeń są oparte na tej kategorii. Jeśli jednak kategoria nie została wybrana w polu **Relacja kategorii**, używane są ustawienia odroczeń kategorii wyższa w rangi. Na przykład można dodać kategorię sprzedaży **wideo domowe**, ale nie kategorię sprzedaży **telewizji**. Podczas dodawania towaru odroczenia skojarzonego z kategorią **Telewizja** są dla tego towaru używane ustawienia odroczenia **wideo domowe**.

### <a name="set-up-deferred-items"></a>Konfigurowanie pozycji odroczonych

Aby skonfigurować towary, które są domyślnie odroczone, należy wykonać następujące czynności.

1. Na stronie **Towary odroczone domyślnie** wybierz kartę: **Zamówienie** sprzedaży lub **Zakupy**.
2. Wybierz pozycję **Dodaj**, aby dodać drugi wiersz.
3. W polu **Kod pozycji** wybierz kod towaru.
4. Umożliwia określenie sposobu stosowania kodu towaru:

    * Jeśli w polu **Kod elementu** ustawiono wartość **Grupa** lub **Tabela**, w polu **Relacja elementu** należy wybrać relację elementu.
    * Jeśli w **polu Kod pozycji** zostanie ustawiona wartość **Kategoria**, wybierz relację kategorii w polu **Relacja kategorii**.

5. Powtórz kroki od 2 do 4 dla każdej wymaganego dodatkowego wiersza.
6. Wybierz opcję **Zapisz**.

## <a name="deferred-charges"></a>Odroczone opłaty

Strona **Opłaty odroczeń umożliwia** określenie, które opłaty są domyślnie odroczone.

> [!NOTE]
> * Obecnie opłaty odroczone są dostępne tylko dla zamówień sprzedaży.
> * Obciążenia mogą być odraczane tylko na poziomie linii. Aby odroczyć opłatę na poziomie nagłówka zamówienia sprzedaży, można skonfigurować opłatę jako odroczony towar w osobnym wierszu zamówienia sprzedaży.
> * Aby odroczyć opłatę za fakturę niezależnej, należy wprowadzić opłatę jako osobny wiersz odroczonej faktury.
> * Ta funkcja nie jest dostępna dla opłat pomocy technicznej i funkcji podziału przychodów.

### <a name="set-up-deferred-charges"></a>Utworzenie rozliczeń międzyokresowych czynnych

Aby skonfigurować odroczone opłaty, wykonaj następujące czynności.

1. Na stronie **Opłaty odroczenia** wybierz pozycję **Dodaj**, aby dodać wiersz.
2. W polu **Kod opłat** wybierz kod opłaty.
3. W polu **Relacja opłaty** wybierz numer opłaty.
4. Powtórz kroki od 1 do 3 dla każdej wymaganego dodatkowego wiersza.
5. Wybierz opcję **Zapisz**.

## <a name="event-based-deferral-templates"></a>Szablony odroczeń oparte na zdarzeniach

Strona Szablony **odroczeń opartych** na zdarzeniach umożliwia definiowanie szablonów **odroczeń opartych na zdarzeniach, które można używać w transakcjach odroczeń i przypisywać na stronie Domyślne wartości odroczeń**.

### <a name="create-an-event-based-template"></a>Utwórz szablon oparty na zdarzeniach

Aby utworzyć szablon odroczenia oparty na zdarzeniach, wykonaj poniższe kroki.

1. Na stronie **Szablony odroczeń oparte na zdarzeniach** wybierz opcję **Nowe**.
2. W polu **Szablon** wpisz unikatową nazwę grupy szablonów.
3. W polu **Opis wprowadź** opis.
4. W polu **Typ alokacji** wybierz typ alokacji.

    * **Kwota zmienna** — przydziela określoną kwotę do każdego wprowadzanego wiersza.
    * **Kwota równa** — Dla każdego wprowadzonego wiersza należy przydzielić taką samą kwotę. 
    * **Procent** — alokacja kwoty na podstawie wartości procentowej wprowadzonej dla każdego wiersza.
    * **Procent ukończenia** — Dla każdego wprowadzonego wiersza należy przydzielić skumulowaną wartość zakończenia.
    * **Ilość zmienna** — Przydzielenie określonej ilości dla każdego wprowadzonego wiersza.

5. Ustaw opcję **Utwórz osobne zdarzenia na jednostkę** na wartość **Tak**, jeśli każdy wiersz zdarzenia ma być podzielony równomiernie przez liczbę jednostek w transakcji faktury. Ustaw wartość **Nie**, jeśli nie chcesz dzielić wierszy zdarzeń.
6. W polu **Konto wygaśnięcia** wybierz konto wygaśnięcia.
7. Wybierz **opcję Dodaj**, aby dodać wiersz u góry listy wierszy, lub wybierz opcję **Dołącz**, aby dodać wiersz u dołu listy.
8. W polu **Opis** wprowadź opis wydarzenia.
9. Jeśli w polu **Typ alokacji** wybrano wartość **Procent**, należy określić procent alokacji w polu **Procent alokacji**. Wartość procentowa musi należeć do zakresu od 0 (zero) do 100. Jeśli pole Procent alokacji **jest** puste, wartość procentowa jest traktowana jako 0. Suma wszystkich wartości procentowych jest wyświetlana w polu **Całkowita wartość procentowa** u dołu strony i musi być równa 100.
10. W polu **Miesiące do wygaśnięcia** określ liczbę miesięcy ważności zdarzenia. Na podstawie tej wartości automatycznie wprowadzana jest data ważności odroczenia transakcji.
11. Zaznacz pole **wyboru Rozpoznaj po zaksięgowaniu**, aby automatycznie rozpoznawał przychód po zaksięgowaniu transakcji. Jeśli to pole wyboru nie zostanie zaznaczone, przychód musi zostać rozpoznany ręcznie.
12. W polu **Konto rozpoznawania** wybierz konto rozpoznawania dla zdarzenia, jeśli dla zdarzenia jest używane konto inne niż całe harmonogram odroczeń. To pole jest używane razem z polem wyboru **Rozpoznaj po zaksięgowaniu**.
13. Powtórz kroki od 7 do 12 dla każdej wymaganego dodatkowego wiersza.
14. Wybierz opcję **Zapisz**.
