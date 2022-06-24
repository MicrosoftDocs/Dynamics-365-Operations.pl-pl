---
title: Funkcje harmonogramu rozliczania
description: W tym artykule omówiono funkcje harmonogramów rozliczeń, takie jak metody ustalania cen, eskalacje i rabaty, daty wyrównania, proraty, rozliczenia odwrotne oraz grupy elementów dzielonych.
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
ms.openlocfilehash: b6cfebc2bbfe06e118bfc96f9ae0df6323805e39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853591"
---
# <a name="billing-schedule-features"></a>Funkcje harmonogramu rozliczania

[!include [banner](../includes/banner.md)]

W tym artykule omówiono funkcje harmonogramów billingowych i linii harmonogramów billingowych. Opisano w nim różne metody stosowane do ustalania cen, sposoby korzystania z podwyżek i rabatów oraz sposoby odwracania okresu rozliczeniowego. Zawiera również przykłady obliczeń prorogacji i dzielenia grup pozycji.

## <a name="pricing-methods"></a>Metody wyceny

Aby obliczyć cenę jednostkową elementu, można użyć jednej z poniższych metod wyceny:

* Spłaszcz
* Standardowy
* Warstwa
* Warstwa równa

### <a name="flat-pricing"></a>Wycena ryczałtowa

Gdy stosowana jest metoda cen ryczałtowych, cenę jednostkową dla pozycji harmonogramu rozliczeniowego na stronie **Wszystkie harmonogramy rozliczeniowe** można edytować do dowolnej wartości. Wartość **Cena jednostkowa** wynosi zawsze **1**. W związku z tym wartości **Cena jednostkowa** i **Kwota netto** towaru są takie same.

### <a name="standard-pricing-without-a-trade-agreement"></a>Standardowa cena (bez umowy handlowej)

W przypadku stosowania standardowej metody ustalania cen bez umowy handlowej cenę jednostkową dla pozycji harmonogramu rozliczeniowego określa się, wybierając **Zarządzanie informacjami o produkcie** na stronie **Uwolnij szczegóły produktu**. Cena jednostkowa jest wyświetlana w sekcji **Podstawowa cena sprzedaży**. Jest obliczana jako *Cena* &divide; *Ilość dla ceny*.

### <a name="standard-pricing-with-a-trade-agreement"></a>Standardowa cena (z umową handlową)

W poniższych przykładach przedstawiono standardowe kalkulacje cenowe w przypadku istnienia umowy handlowej. Umowy handlowe można tworzyć za pomocą strony **Szczegóły produktu zwolnienia**.

W obu przykładach użyto artykułu, który ma następujące przedziały cenowe.

| Od ilości | Ilość do | U z M | Cena | Jednostka cenowa |
|---|---|---|---|---|
| 0 | 100 | Wszystkie | 1.50 | 1 |
| 100 | 200 | Wszystkie | 1.25 | 1 |
| 200 | 999999 | Wszystkie | 1,00 | 1 |

**Przykład 1**

Ilość na fakturze wynosi 250 sztuk i stosowana jest standardowa metoda ustalania cen. Ponieważ ilość należy do przedziału ilościowego 200–999 999, cena jednostkowa wynosi 1,00. 

Kwotę netto oblicza się w następujący sposób:

*Kwota netto* = (*Ilość* &times; *Price*) &divide; *Jednostka cenowa* = (250 &times; 1,00) &divide; 1 = 250

**Przykład 2**

Ilość na fakturze wynosi 100 sztuk i stosowana jest standardowa metoda ustalania cen. Ponieważ ilość na fakturze mieści się w przedziale ilościowym 0-100, cena jednostkowa wynosi 1,50.

> [!NOTE]
> Ilość na fakturze mieści się w przedziale 0-100, a nie 100-200, ponieważ w standardowym trybie dopasowywania ilości ilość jest dopasowywana, jeśli jest *większa lub równa* ilości "od" i *mniejsza niż* ilości "do".

Kwotę netto oblicza się w następujący sposób:

*Kwota netto* = (100 &times; 1,50) &divide; 1 = 150

### <a name="tier-pricing"></a>Ceny warstwowe

W poniższym przykładzie artykuł ma następujące przedziały cenowe.

| Od ilości | Ilość do | U z M | Cena | Jednostka cenowa |
|---|---|---|---|---|
| 0 | 100 | Wszystkie | 1.50 | 10 |
| 100 | 200 | Wszystkie | 1.25 | 10 |
| 200 | 999999 | Wszystkie | 1,00 | 10 |

Jeśli ilość na fakturze wynosi 250 i stosowana jest metoda cen warstwowych, ceny pozycji są obliczane w następujący sposób, na podstawie nawiasów cenowych:

- **Pierwsze 100 towarów:** 100 &times; 1,50 = 150,00
- **Drugie 100 pozycji:** 100 &times; 1,25 = 125,00
- **Pozostałe pozycje:** 50 &times; 1.00 = 50,00

Kwotę netto oblicza się w następujący sposób:

*Kwota netto* = (150,00 &divide; 10) + (125,00 &divide; 10) + (50,00 &divide; 10) = 15,00 + 12,50 + 5,00 = 32,50

Po obliczeniu kwoty netto, cena jednostkowa jest obliczana poprzez podzielenie kwoty netto przez ilość:

*Cena jednostkowa* = 32,50 &divide; 250 = 0,13

### <a name="flat-tier-pricing"></a>Płaskie ceny warstwowe

W poniższym przykładzie artykuł ma następujące przedziały cenowe.

| Od ilości | Ilość do | U z M | Kwota warstwy równej | Jednostka cenowa |
|---|---|---|---|---|
| 0 | 50 | Wszystkie | 100.00 | 50 |
| 50 | 200 | Wszystkie | 150.00 | 200 |

W poniższej tabeli przedstawiono faktury i ceny jednostkowe dla różnych zakupionych ilości. Najpierw obliczana jest kwota netto, a następnie cena jednostkowa.

| Faktura | Ilość zakupiona | Cena jednostkowa | Kwota netto |
|---|---|---|---|
| 1 | 25 | 2.00 &divide; 25 = 0,08 | 100 &divide; 50 = 2,00 |
| 2 | 20 | 2.00 &divide; 20 = 0,10 | 100 &divide; 50 = 2,00 |
| 3 | 50 | 2.00 &divide; 50 = 0,04 | 100 &divide; 50 = 2,00 |
| 4 | 60 | 0,75 &divide; 60 = 0,0125 = 0,01 | 150 &divide; 200 = 0,75 |

## <a name="escalations-and-discounts"></a>Eskalacje i rabaty

*Eskalacja* to wzrost ceny za przyszły okres fakturowania, dla którym nie utworzono jeszcze faktury. *Rabat* to obniżka ceny za przyszły okres rozliczeniowy, dla którego nie została jeszcze utworzona faktura.

W przypadku rozliczania subskrypcji nie można zastosować z mocą wsteczną eskalacji i rabatów do harmonogramu rozliczeniowego. Na przykład nie można zastosować eskalacji do harmonogramu rozliczeń sprzed trzech miesięcy i przetworzyć go. Innymi słowy, nie można zastosować podwyżki cen, która miała miejsce trzy miesiące temu.

Można zastosować eskalację lub rabat do harmonogramu rozliczeniowego lub linii harmonogramu rozliczeniowego w jednym z następujących miejsc:

- Strona **listy wszystkich/aktywnych harmonogramów** fakturowania
- Szczegółowy harmonogram rozliczeń
- Określony wiersz harmonogramu rozliczeń

### <a name="apply-an-escalation-or-discount"></a>Zastosuj eskalację lub rabat

Aby zastosować eskalację lub rabat do harmonogramu fakturowania, należy wykonać następujące kroki.

1. Wybierz harmonogram fakturowania lub wiersz harmonogramu fakturowania.
2. Wybierz **eskalację i rabat** na karcie **Eskalacja i rabat** albo w wierszu harmonogramu fakturowania.
3. Jeśli indeks cen dla odbiorców jest używany do obliczania eskalacji lub rabatu, wybierz wartość w polu **Obliczanie indeksu cen dla odbiorców**.
4. Wybierz pozycję **Nowy**, aby dodać wiersz eskalacji lub rabatu.
5. Aby uzyskać rabat, zaznacz pole wyboru **Rabat**. W przypadku eskalacji pozostaw wyczyszone pole wyboru **Rabat**.
6. Ustaw pola **Data rozpoczęcia** i **Częstotliwość**.
7. W przypadku towarów odroczonych, które korzystają z funkcji przychodu niepodbilonego, ustaw **pole Data zakończenia**.
8. Ustaw pole **Harmonogram indeksu** wartości procentowej, **kwoty** lub **ceny konsumpcyjnej**.
9. Ustaw pole **Data zakończenia**.
10. Kliknij przycisk **OK**.
11. Powtórz kroki od 4 do 10 dla każdej wymaganej dodatkowej eskalacji lub wiersza rabatu.

### <a name="fields-on-the-billing-schedule-lines-page"></a>Pola na stronie Wiersze harmonogramu rozliczeń

Strona **Linie harmonogramu rozliczeń** zawiera następujące pola.

| Pole | Opis |
|---|---|
| Numer towaru | Numer pozycji dla wiersza harmonogramu rozliczeń. To pole jest dostępne tylko wtedy, gdy strona jest otwierana z pozycji harmonogramu rozliczeniowego. |
| Obliczanie indeksu ceny konsumenta | <p>Wybierz metodę, która jest stosowana do obliczania wzrostu wskaźnika cen towarów i usług konsumpcyjnych:</p><ul><li>**Poprzedni indeks cen klientów** — użyj poprzedniej wartości indeksu cen dla odbiorców w obliczeniach eskalacji.</li><li>**Bazowy wskaźnik cen towarów i usług konsumpcyjnych** — Do obliczenia eskalacji należy użyć wartości bazowego wskaźnika cen towarów i usług konsumpcyjnych.</li></ul> |
| **Siatka** wiersza | |
| Rabat | <p>To pole wyboru należy ustawić, aby określić, czy zmiana kwoty jest eskalacją czy rabatem:</p><ul><li>**Zaznaczone** — zmiana powoduje zastosowanie rabatu do harmonogramu fakturowania lub wiersza harmonogramu fakturowania.</li><li>**Wyczyszone** — zmiana powoduje eskalację do harmonogramu fakturowania lub wiersza harmonogramu.</li></ul><p>Nie można zmienić ustawienia tego pola wyboru dla pozycji, które korzystają z funkcji nieskomplikowanych przychodów. Ponadto nie można stosować rabatów do towarów, dla których jest stosowany podział przychodów.</p> |
| Data początkowa | Wybierz datę rozpoczęcia eskalacji lub rabatu. |
| Częstotliwość | Wybierz częstotliwość eskalacji lub rabatu: **Brak**, **Miesięcznie**, **Kwartalne**, **Półroczne** lub **Rocznie**. |
| Wartość procentowa | Określ procentowy poziom eskalacji lub rabatu. |
| Ilość | Określ kwotę eskalacji lub rabatu. |
| Harmonogram indeksu ceny konsumenta | Wybierz schemat wskaźnika cen towarów i usług konsumpcyjnych, który jest używany do obliczeń. |
| Data końcowa | <p>Wybierz datę końcową eskalacji lub rabatu.</p><p>**Uwaga:** to pole jest wymagane w przypadku towarów, które korzystają z funkcji nieskomplikowanych przychodów.</p> |
| Numer harmonogramu odroczeń | <p>Numer harmonogramu odroczeń.</p><p>To pole jest dostępne tylko wtedy, gdy strona jest otwierana z harmonogramu rozliczeniowego.</p> |
| Arkusz z numerem partii | <p>Numer partii dziennika.</p><p>To pole jest dostępne tylko wtedy, gdy strona jest otwierana z harmonogramu rozliczeniowego.</p> |
| Łączna kwota rabatu | <p>Suma kwot rabatów dla wszystkich wierszy w siatce.</p><p>To pole jest dostępne tylko wtedy, gdy strona jest otwierana z harmonogramu rozliczeniowego.</p> |
| Bieżąca nierozliczona kwota krótkoterminowa przychodu | <p>Bieżąca kwota krótkoterminowych niezafakturowanych przychodów.</p><p>Kwota ta pojawia się po wybraniu metody odroczenia krótkoterminowego na stronie **Parametry rozliczania umów cyklicznych** i skonfigurowaniu kont dla tej pozycji na stronie **Ustawianie przychodów niefakturowanych**.</p> |
| Bieżąca długoterminowa nierozliczona kwota przychodu | <p>Bieżąca kwota długoterminowych niefakturowanych przychodów.</p><p>Kwota ta pojawia się po wybraniu metody odroczenia krótkoterminowego na stronie **Parametry rozliczania umów cyklicznych** i skonfigurowaniu kont dla tej pozycji na stronie **Ustawianie przychodów niefakturowanych**.</p> |

## <a name="proration-examples"></a>Przykłady proporcji

Obliczenia dotyczące pomniejszania mogą być oparte na liczbie dni lub miesięcy. Metoda używana do obliczania proration jest ustawiana na stronie **Parametry fakturowania umowy cyklicznej**. Metoda przetwarzania ma wpływ na sposób obliczania kwot dla harmonogramu fakturowania w następujących sytuacjach:

- Tworzenie wstępne
- Zastosowanie podwyżki lub obniżki
- Przerwanie
- Umieszczenie lub usunięcie wstrzymania
- Dodawanie pomocy technicznej lub odnowienia

Metoda przetwarzania ma także wpływ na obliczenia miesięcznego raportu cyklicznego przychodu (MRR).

### <a name="example-1"></a>Przykład 1

Roczna kwota harmonogramu fakturowania jest $5000. Data rozpoczęcia to 12 sierpnia 2019, a data końcowa to 22 grudnia 2019. Częstotliwość fakturowania jest roczna. Kwota proporcjonalna jest obliczana w następujący sposób, w zależności od tego, czy jest używana metoda obliczania dziennego czy miesięcznego:

- **Codziennie**

    - *Liczba dni* = *Data końcowa* – *Start rozpoczęcia* + 1 = 133 dni
    - *Liczba dni w roku* = 11 sierpnia 2020 – 12 sierpnia 2019 + 1 = 366 dni
    - *Kwota proporcjonalna* = 5000 &times; (133 &divide; 366) = 1816,94

- **Miesięczne**

    - *Część miesiąca rozpoczęcia* = (31 – 12 + 1) &divide; 31 = 20 &divide; 31
    - *Miesiące pośrednie* = 3
    - *Część miesiąca końcowego* = 22 &divide; 31
    - Kwota proporcjonalna = 5000 &divide; 12 &times; \[(20 &divide; 31) + 3 + (22 &divide; 31)\] = 1814,52

### <a name="example-2"></a>Przykład 2

Roczna kwota harmonogramu fakturowania jest $12,000. Data rozpoczęcia to 1 sierpnia 2019, a data końcowa to 31 grudnia 2019. Częstotliwość fakturowania jest roczna. Kwota proporcjonalna jest obliczana w następujący sposób, w zależności od tego, w zależności od metody obliczania:

- **Codziennie**

    - *Liczba dni* = *Data końcowa* – *Start rozpoczęcia* + 1 = 153 dni
    - *Liczba dni w roku* = 31 lipca 2020 – 1 sierpnia 2019 + 1 = 366 dni
    - *Kwota proporcjonalna* = 12,000 &times; (153 &divide; 366) = 5016,39

- **Miesięczne (Pełny miesiąc)**

    - *Liczba miesięcy* = 5
    - *Łączna liczba miesięcy* = 12
    - *Kwota proporcjonalna* = (12000 &times; 5) &divide; 12 = 5000

## <a name="reversing-a-period-billing"></a>Wywłaszanie fakturowania okresu

W tym przykładzie harmonogram fakturowania ma tylko jeden wiersz:

- Fakturowanie jest wykonywane co miesiąc przez 12 miesięcy od stycznia do grudnia.
- Faktury zostały utworzone dla wszystkich okresów do kwietnia.

Chcesz wycofać fakturę za kwietniowy okres rozliczeniowy.

Jeśli faktura sprzedaży nie została jeszcze utworzona dla kwietnia okresu fakturowania, można usunąć zamówienie sprzedaży. W tym przypadku stan **Rozliczone** rachunki dla szczegółów zostanie usunięty. Ponieważ jednak faktura została utworzona dla okresu fakturowania, nie można wyczyścić stanu **Rozliczone** dla szczegółów. W związku z tym, aby wycofać kwietniową fakturę, należy utworzyć przeciwstawną fakturę korygujące dla wiersza.

1. Na stronie **Wszystkie harmonogramy fakturowania** utwórz wiersz harmonogramu dla tej samej pozycji.
2. Zmień wartość **Ilość** dla pozycji na ujemną ilość oryginalną.
3. Ustaw w polu **Częstotliwość fakturowania** wartość **Jeden raz**.
4. Zaktualizuj daty rozpoczęcia i zakończenia tak, aby były zgodne z datami wiersza szczegółów fakturowania, dla którego chcesz utworzyć fakturę korygową. W tym przykładzie należy ustawić datę rozpoczęcia na 1 kwietnia 2019, a datę zakończenia na 30 kwietnia 2019.
5. Zapisz zmiany.
6. Otwórz stronę **Generowanie faktury** i utwórz zamówienie sprzedaży z fakturą korygową dla podanego okresu.
7. Opcjonalnie: Zaksięguj fakturę.

Podczas przeglądania wierszy harmonogramu fakturowania można zauważyć, że nowy wiersz ma łącze do faktury korygowej. Oryginalny wiersz będzie nadal mieć łącze do oryginalnej kwietniowej faktury.

## <a name="split-item-group-examples"></a>Przykłady podziału grupy elementów

W tym przykładzie obowiązuje następująca konfiguracja:

- Na stronie **Parametry fakturowania umowy cyklicznej** zaznaczono opcję **Podziel według grup towarów**, a w polu **Unikatowy typ harmonogramu** ustawiono wartość **Odbiorca**.
- Utworzono trzy grupy towarów: **PREFIKS**, **DATAHUB** i **SPP**.
- Grupa US-001 ma wiele harmonogramów fakturowania, w których grupa pozycji to PREFIX lub DATAHUB.
- Grupa US-002 ma wiele harmonogramów fakturowania, w których grupa pozycji to PREFIX lub SPP.

| Numer harmonogramu rozliczania | Odbiorca | Grupa pozycji |
|---|---|---|
| SCH001 | US-001 | PREFIX |
| SCH002 | US-001 | DATAHUB |
| SCH003 | US-002 | PREFIX |
| SCH004 | US-002 | SPP |

Odbiorca US-001 element odnowienia należący do grupy pozycji PREFIX. Ta transakcja jest nowym zamówieniem sprzedaży.

| Numer zamówienia sprzedaży | Odbiorca | Główna pozycja | Pozycja odnowienia | Grupa pozycji odnowienia | Numer harmonogramu rozliczania |
|---|---|---|---|---|---|
| SO0001 | US-001 | D0001 | D0002 | PREFIX | SCH001 |

Po zaksięgowaniu faktury dla zamówienia sprzedaży towar odnowienia jest dodawany do istniejącego harmonogramu fakturowania (SCH001) dla odbiorcy. W tym harmonogramie fakturowania jest używana grupa pozycji PREFIX. Wszystkie odnowienie towarów należących do tej samej grupy towarów jest umieszczane w tym samym harmonogramie fakturowania.

**Nagłówek**
 
| Numer harmonogramu rozliczania | Odbiorca | Grupa pozycji |
|---|---|---| 
| SCH001 | US-001 | PREFIX |

**Wiersz**

| Numer harmonogramu rozliczania | Odbiorca | Grupa pozycji |
|---|---|---|
| SCH001 | US-001 | D0002 |

Odbiorca US-001 element odnowienia należący do grupy pozycji SPP. Ta transakcja jest nowym zamówieniem sprzedaży.

| Numer zamówienia sprzedaży | Odbiorca | Główna pozycja | Pozycja odnowienia | Grupa pozycji odnowienia | Numer harmonogramu rozliczania |
|---|---|---|---|---|---|
| SO0002 | US-001 | D0003 | D0004 | SPP | |

Obecnie odbiorca US-001 nie ma harmonogramu rozliczeń, który wykorzystuje grupę pozycji SPP. W związku z tym jest tworzony nowy harmonogram fakturowania.

**Nagłówek**

| Numer harmonogramu rozliczania| Odbiorca | Grupa pozycji |
|---|---|---|
| SCH005 | US-001 | SPP |

**Wiersz**

| Numer harmonogramu rozliczania | Odbiorca | Grupa pozycji |
|---|---|---|
| SCH005 | US-001 | D0004 |

### <a name="multiple-billing-schedules-for-the-same-end-user-and-customer"></a>Wiele harmonogramów fakturowania dla tego samego użytkownika końcowego i odbiorcy

W tym przykładzie obowiązuje następująca konfiguracja:

- Na stronie **Parametry fakturowania umowy cyklicznej** zaznaczono opcję **Podziel według grup towarów**, a w polu **Unikatowy typ harmonogramu** ustawiono wartość **Użytkownik końcowy**.
- Na stronie **Użytkownicy końcowi** są ustawione następujące relacje odbiorcy i użytkownika końcowego.

    | Konto odbiorcy | Konto użytkownika końcowego |
    |---|---|
    | US-001 | US-221 |

Dla kombinacji klienta i użytkownika końcowego tworzonych jest wiele harmonogramów rozliczeniowych. Ponieważ na stronie **Parametry fakturowania** umowy cyklicznej jest wybrana opcja **Podziel według towarów**, można utworzyć wiele harmonogramów fakturowania dla tej samej relacji odbiorcy i użytkownika końcowego.

| Numer harmonogramu rozliczania | Odbiorca | Konto użytkownika końcowego | Grupa pozycji nagłówka |
|---|---|---|---|
| SCH005 | US-001 | US-221 | IG1 |
| SCH006 | US-001 | US-221 | IG2 |
| SCH007 | US-001 | US-221 | IG3 |

Na stronie **Konfiguracja towaru** tworzysz obsługę i odnowienie relacji elementów.

| Kod pozycji | Relacja produktu | Pozycja obsługi | Pozycja odnowienia | Grupa pozycji odnowienia |
|---|---|---|---|---|
| Tabela | D001 | ITEM27 | D007 | IG1 |
| Tabela | D002 | ITEM28 | D005 | IG2 |
| Tabela | D003 | ITEM29 | D006 | IG3 |

Tworzysz teraz zamówienie sprzedaży dla klienta US-001. To zamówienie sprzedaży zawiera towary ze strony **Ustawienia towaru**. Podczas tworzenia zamówienia sprzedaży otwórz **stronę procesu pomocy technicznej i odnowienia**, a następnie ustaw pole **Konto użytkownika końcowego** i wszelkie inne wymagane informacje dotyczące elementu odnowienia.

Po utworzeniu i zaksięgowaniu faktury dla transakcji tworzone są różne harmonogramy fakturowania dla kombinacji odbiorca/użytkownik końcowy i grupa towarów. Do tego samego harmonogramu fakturowania można przypisać więcej niż jeden wiersz w tym samym zamówieniu sprzedaży.

| Numer zamówienia sprzedaży | Odbiorca | Konto użytkownika końcowego | Główna pozycja | Pozycja obsługi | Pozycja odnowienia | Numer harmonogramu rozliczania |
|---|---|---|---|---|---|---|
| SO0001 | US-001 | US-221 | D001 | ITEM27 | D007 | SCH005 |
| SO0001 | US-001 | US-221 | D002 | ITEM28 | D005 | SCH006 |
| SO0001 | US-001 | US-221 | D003 | ITEM29 | D006 | SCH005 |
