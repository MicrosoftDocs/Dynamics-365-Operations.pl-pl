---
title: Sprawozdania podatkowe dla Polski
description: Ten artykuł zawiera informacje o sprawozdawczości podatku VAT w Polsce oraz podaje informacje, które są wymagane przez prawo w rejestrach podatku VAT w Polsce.
author: mrolecki
ms.date: 12/06/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 274063
ms.search.region: Poland
ms.author: roschlom
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.openlocfilehash: 5ab3555c22dae02e41cc62adc2786aea8e93d93b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875927"
---
# <a name="sales-tax-reports-for-poland"></a>Sprawozdania podatkowe dla Polski
[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o sprawozdawczości podatku od towarów i usług (VAT) w Polsce oraz podaje informacje, które są wymagane przez prawo w rejestrach podatku VAT w Polsce.

## <a name="vat-report-date-codes"></a>Kody dat raportu VAT

Zgodnie z polską ustawą o rachunkowości, która weszła w życie dnia 29 września 1994 r., podatek VAT dla sprzedaży, zakupów i produktów importowanych musi być przetwarzany oddzielnie. Dla każdej zaksięgowanej transakcji sprzedaży lub zakupu, która ma ustawione pole **Data rejestru VAT** lub **Kod daty rejestru VAT**, podatek jest wykazywany w odpowiednich rejestrach podatku VAT. Pole **Kod daty rejestru VAT** znajduje się na kilku stronach transakcji. Podczas aktualizowania lub księgowania transakcji informacje o kodzie daty raportu VAT są księgowane w tabelach podatku. Następnie będą drukowane w polskim rejestrze podatku VAT.

Aby skonfigurować kody dat raportu VAT, ustaw podane pola na stronie **Kody dat raportu VAT** (**Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Kody dat raportu VAT**).

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Pole</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Kod daty rejestru  VAT</td>
<td>Wprowadź kod daty raportu VAT.</td>
</tr>
<tr class="even">
<td>opis</td>
<td>Wprowadź opis kodu daty raportu VAT.</td>
</tr>
<tr class="odd">
<td>Uwzględnij w raporcie podatku VAT</td>
<td>Umożliwia wybranie jednej z następujących opcji:
<ul>
<li><strong>Z datą raportu VAT </strong> — raport pokazuje całą kwotę faktury, jeśli obliczona data w polu <strong>Data rejestru VAT</strong> na stronie <strong>Księgowanie faktury</strong> mieści się w przedziale dat objętym raportem.</li>
<li><strong>Z datą raportu VAT nie później niż</strong> — raport pokazuje całą kwotę faktury, jeśli data w polu <strong>Data rejestru VAT</strong> mieści się w przedziale dat objętym raportem. Data jest obliczana na podstawie informacji w polach <strong>Liczone od</strong> i <strong>Liczba dni</strong>.</li>
<li><strong>Z datą fizycznej płatności</strong> — w przypadku zaznaczenia pola wyboru <strong>Rozliczenia częściowe</strong> raport pokazuje rozliczoną część kwoty faktury, jeśli interwał raportowania obejmuje daty płatności. Jeśli pole wyboru <strong>Rozliczenia częściowe</strong> jest wyczyszczone, raport nie pokazuje kwoty faktury, dopóki faktura nie zostanie całkowicie rozliczona.</li>
<li><strong>Z datą fizycznej płatności nie później niż</strong> — w przypadku zaznaczenia pola wyboru <strong>Rozliczenia częściowe</strong> raport pokazuje rozliczenia dokonane w przedziale dat objętym raportem. Jeśli obliczona wartość w polu <strong>Data rejestru VAT</strong> znajduje się w zakresie dat raportu, raport pokazuje łączną kwotę faktury, z wyjątkiem rozliczonych kwot poprzedniego okresu. Jeśli pole wyboru <strong>Rozliczenie częściowe</strong> jest wyczyszczone, wybierz opcję <strong>Data transakcji</strong> lub <strong>Data VAT</strong> w polu <strong>Liczone od</strong>, aby określić kryterium używane do obliczania daty rejestru VAT.</li>
</ul></td>
</tr>
<tr class="even">
<td>Liczba dni</td>
<td>Umożliwia wprowadzanie liczby dni po dacie zarejestrowania podatku VAT. To pole jest dostępne tylko wtedy, gdy pole <strong>Uwzględnij w raporcie podatku VAT</strong> jest ustawione na wartość <strong>Z datą raportu VAT nie później niż</strong> lub <strong>Z datą fizycznej płatności nie później niż</strong>.</td>
</tr>
<tr class="odd">
<td>Liczone od</td>
<td>Umożliwia wybranie jednej z następujących opcji:
<ul>
<li>Data transakcji</li>
<li>Data VAT</li>
</ul></td>
</tr>
<tr class="even">
<td>Rozliczenia częściowe</td>
<td>Zaznacz to pole wyboru, aby rozliczać płatności częściowo. To pole wyboru jest dostępne tylko wtedy, gdy pole <strong>Uwzględnij w raporcie podatku VAT</strong> jest ustawione na wartość <strong>Z datą fizycznej płatności</strong> lub <strong>Z datą fizycznej płatności nie później niż</strong>.</td>
</tr>
<tr class="odd">
<td>Data podatku VAT jest datą płatności</td>
<td>Zaznaczenie tego pola wyboru spowoduje wyświetlanie kodu daty raportu VAT tylko wtedy, gdy data płatności podatku VAT jest taka sama, jak data w rejestrze VAT.</td>
</tr>
</tbody>
</table>

Następujące strony zawierają kod daty raportu VAT.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Strona</th>
<th>Więcej informacji</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Parametry modułu rozrachunków z dostawcami
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Parametry modułu rozrachunków z dostawcami</strong>.</li>
</ul></td>
<td>Na karcie <strong>Ogólne</strong> na skróconej karcie <strong>Dostawca</strong> wprowadź kod daty raportu VAT, który powinien być używany jako domyślny kod dla nowych dostawców.</td>
</tr>
<tr class="even">
<td>Parametry modułu rozrachunków z odbiorcami
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Parametry modułu rozrachunków z odbiorcami</strong>.</li>
</ul></td>
<td>Na karcie <strong>Ogólne</strong> na skróconej karcie <strong>Odbiorca</strong> wprowadź kod daty raportu VAT, który powinien być używany jako domyślny kod dla nowych zamówień zakupu.</td>
</tr>
<tr class="odd">
<td>Obsługa przedpłat
<ol>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Szczegóły dostawcy</strong> &gt; <strong>Transakcje</strong>.<br>
– lub –<br>
Wybierz kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Szczegóły odbiorcy</strong> &gt; <strong>Transakcje</strong>.</li>
<li>Zaznacz transakcję przedpłaty, a następnie wybierz opcję <strong>Obsługa przedpłat</strong>.</li>
</ol></td>
<td>Pole <strong>Kod daty rejestru VAT</strong> jest widoczne, jeśli wybrano opcję <strong>Zaawansowane</strong> w polu <strong>Obsługa przedpłat</strong> na stronie <strong>Parametry modułu rozrachunków z dostawcami</strong> lub <strong>Parametry modułu rozrachunków z odbiorcami</strong>.</td>
</tr>
<tr class="even">
<td>Zatwierdzenie faktury od dostawcy
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Arkusz zatwierdzania faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Pula faktur
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Pula faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Rejestr faktur od dostawców
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Rejestr faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Arkusz faktur od dostawców
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Arkusz faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Wszystkie zamówienia zakupu
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Zamówienia zakupu</strong> &gt; <strong>Wszystkie zamówienia zakupu</strong>.</li>
</ul></td>
<td>Kod daty raportu VAT jest wyświetlany w nagłówku.</td>
</tr>
<tr class="odd">
<td>Specyfikacja
<ol>
<li>Wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Dostawcy</strong> &gt; <strong>Wszyscy dostawcy</strong>.</li>
<li>Na karcie <strong>Faktura</strong> w grupie <strong>Rozlicz</strong> wybierz opcję <strong>Rozlicz transakcje</strong>.</li>
<li>Wybierz kolejno opcje <strong>Informacje</strong> &gt; <strong>Specyfikacje</strong>, a następnie na karcie <strong>Ustawienia</strong> w polu <strong>Widok</strong> zaznacz opcję <strong>Zakup</strong>.</li>
</ol>
<p>– lub –</p>
<ol>
<li>Wybierz kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Odbiorcy</strong> &gt; <strong>Wszyscy odbiorcy</strong>.</li>
<li>Na karcie <strong>Windykacja</strong> w grupie <strong>Rozlicz</strong> wybierz opcję <strong>Rozlicz transakcje</strong>.</li>
<li>Wybierz kolejno opcje <strong>Informacje</strong> &gt; <strong>Specyfikacje</strong>, a następnie na karcie <strong>Ustawienia</strong> w polu <strong>Widok</strong> zaznacz opcję <strong>Zamówienie sprzedaży</strong>.</li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td>Załącznik arkusza
<ul>
<li>Na stronie arkusza finansowego, arkusza okresowego, arkusza kasowego lub arkusza wydatków wybierz opcję <strong>Wiersze</strong>.</li>
</ul></td>
<td>Przejrzyj zawartość karty <strong>Faktury</strong> lub <strong>Płatność</strong>.<blockquote>[!NOTE]<br>W przypadku arkusza wydatków pole <strong>Typ konta przeciwstawnego</strong> powinno być ustawione na <strong>Dostawca</strong>.</blockquote></td>
</tr>
<tr class="odd">
<td>Zamówienie sprzedaży
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Zamówienia</strong> &gt; <strong>Wszystkie zamówienia sprzedaży</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Faktura niezależna
<ul>
<li>Wybierz kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Faktury niezależne</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Zaksięgowany podatek
<ul>
<li>Wybierz kolejno opcje <strong>Podatek</strong> &gt; <strong>Zapytania i raporty</strong> &gt; <strong>Zapytania o podatki</strong> &gt; <strong>Zaksięgowany podatek</strong>.</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="name-of-services-for-vat-reporting"></a>Nazwa usług przeznaczonych do raportowania podatku VAT

Numery taryf usługowych są wymagane podczas raportowania informacji o podatku VAT związanych z transakcją ze stroną, która nie znajduje się w Polsce. Numery taryf usługowych ustawia się na stronie **Numery taryf usługowych**. Aby skonfigurować numery taryf usługowych, wybierz kolejno opcje **Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Numer taryfy usługowej** i ustaw następujące pola:

| Pole                      | opis                                                                          |
|----------------------------|--------------------------------------------------------------------------------------|
| Numer taryfy usługowej      | Wprowadź numer taryfy usługowej, który został przypisany do strony przez organ administracji państwowej. |
| Opis taryfy usługowej | Umożliwia wprowadzanie opisu numeru taryfy usługowej.                                    |

Można również ustawić, aby numer taryfy usługowej był obowiązkowy. Wybierz kolejno opcje **Podatek** &gt; **Podatek** &gt; **Grupa podatków**, a następnie na skróconej karcie **Ogólne** ustaw pole **Obowiązkowy numer taryfy usługowej**. Parametr **Obowiązkowy numer taryfy usługowej** parametr ma wpływ na następujące strony:

- Nagłówki i wiersze na stronie **Wszystkie zamówienia sprzedaży** (wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Zamówienia** &gt; **Wszystkie zamówienia sprzedaży**).
- Nagłówek i wiersze na stronie **Wszystkie faktury niezależne** (wybierz kolejno opcje **Rozrachunki z odbiorcami** &gt; **Faktury**&gt; **Wszystkie faktury niezależne**).
- Strona **Unieważnione zamówienia sprzedaży** (wybierz kolejno opcje **Sprzedaż i marketing** &gt; **Zapytania i raporty** &gt; **Historia** &gt; **Unieważnione zamówienia sprzedaży**, a następnie opcję **Pokaż**).

Następujące wspólne funkcje działają na wszystkich powyższych stronach:

- Podczas tworzenia wiersza numer taryfy usługowej jest kopiowany z nagłówka do wiersza.
- Jeśli parametr **Obowiązkowy numer taryfy usługowej** jest włączony w grupie podatków, faktura zostanie zatrzymana i pojawi się komunikat o błędzie.
- Podczas księgowania faktury transakcje podatku są dzielone według numerów taryf usługowych. Grupa podatków i grupa podatków dla towaru są takie same.
- Podczas tworzenia faktury korygującej dla dowolnej zaksięgowanej faktury, której wiersze mają wartość w polu **Numer taryfy usługowej**, numer taryfy usługowej jest kopiowany do wierszy faktury korygującej z oryginalnego dokumentu, a nie z nagłówka faktury korygującej. Numer taryfy usługowej może być edytowany w wierszu korekty.

## <a name="base-amount-for-vat"></a>Kwota podstawy podatku VAT

Pole **Kwota podstawy podatku VAT** jest aktywne po wprowadzeniu transakcji podatkowej w następujących arkuszach. (Transakcje podatkowe są to takie transakcje, w których pole **Kod podatku** w wierszach arkusza ma wartość).

- Arkusz faktur (wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Arkusze** &gt; **Faktury** &gt; **Arkusz faktur**, wybierz opcję **Wiersze**, a następnie wybierz kartę **Ogólne**).
- Arkusz finansowy (wybierz kolejno opcje **Księga główna** &gt; **Arkusze** &gt; **Arkusz finansowy**, wybierz opcję **Wiersze**, a następnie wybierz kartę **Ogólne**).
- Arkusz kasowy (wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Transakcje kasowe** &gt; **Arkusz kasowy**, wybierz opcję **Wiersze**, a następnie wybierz kartę **Ogólne**).

W polu **Kwota podstawy podatku VAT** należy ręcznie wprowadzić kwotę podstawy podatku. Po zaksięgowaniu arkusza wartość z pola **Kwota podstawy podatku VAT** jest przenoszona do pola **Podstawa opodatkowania** w transakcjach podatkowych.

## <a name="sales-tax-vat-reporting"></a>Raportowanie podatku od towarów i usług (VAT)

Funkcja podatku od towarów i usług (raportowania podatku VAT) jest używana w arkuszach księgi, gdzie wiele wierszy ma ten sam załącznik. Gdy poniższe pola w jednym wierszu ulegają zmianie, pojawia się okno komunikatu umożliwiające zaktualizowanie pól w innych wierszach mających ten sam załącznik:

- Faktura VAT
- Data dokumentu
- Adres
- NIP
- Odbiorca/dostawca
- Data rejestru VAT
- Kod daty rejestru  VAT

> [!NOTE]
> Okno komunikatu pojawia się tylko wtedy, gdy pola zostaną zmodyfikowane dla wiersza, w którym skonfigurowano grupę podatków, grupę podatków dla towaru i kod podatku. Pole komunikatu jest wywoływane na następujących stronach arkusza:
>
> - Arkusz finansowy (wybierz kolejno opcje **Księga główna** &gt; **Arkusze** &gt; **Arkusz finansowy**, a następnie wybierz opcję **Wiersze**)
> - Arkusz faktur (wybierz kolejno opcje **Rozrachunki z dostawcami** &gt; **Arkusze** &gt; **Faktury** &gt; **Arkusz faktur**, a następnie wybierz opcję **Wiersze**)

## <a name="tax-direction-for-the-line"></a>Kierunek podatku dla wiersza

Funkcja kierunku podatku dotyczy księgowań realizowanych za pośrednictwem arkusza finansowego, który obejmuje transakcje podatkowe. W zależności od typu konta użytego do księgowania system automatycznie ustala kierunek podatku, który powinien być przypisywany do tworzonych transakcji podatkowych. Ta funkcja pomaga zagwarantować poprawne ustalenie kont głównych i poprawne przypisanie kierunku podatku dla wierszy arkusza finansowego w tym samym załączniku. Wiersze muszą spełniać jeden z następujących warunków:

- Konto jest typu **Odbiorca**, **Dostawca** lub **Gotówka podręczna**, a typem konta przeciwstawnego jest **Księga**. Konto przeciwstawne musi być określone.
- Konto jest typu **Księga**, a typem konta przeciwstawnego jest **Odbiorca**, **Dostawca** lub **Gotówka podręczna**. Konto przeciwstawne musi być określone.

Dla wierszy arkusza finansowego spełniających powyższe warunki system przypisuje osobny kierunek podatku:

- **Podatek należny** dla typ konta **Odbiorca**
- **Podatek naliczony** dla typ konta **Dostawca**
- **Podatek należny** dla typ konta **Gotówka podręczna**

### <a name="example"></a>Przykład

Tworzysz następujące wiersze arkusza finansowego:

| Typ konta | Numer konta | Strona debetowa | Strona kredytowa | Typ konta przeciwstawnego | Numer konta przeciwstawnego | Grupa księgowania podatków | Grupa księgowania podatków dla towarów |
|--------------|----------------|-------|--------|---------------------|-----------------------|-------------------------|------------------------------|
| Odbiorca     | 1101           |       | 800    | Księga              | 0101                  | AR-DOM                  | PEŁNE                         |
| Dostawca       | 1001           |       | 800    | Księga              | 0101                  | AR-DOM                  | PEŁNE                         |
| Księga       | 0102           | 700   |        |                     |                       | AR-DOM                  | PEŁNE                         |
| Księga       | 0103           |       | 700    |                     |                       | AR-DOM                  | PEŁNE                         |

Poniżej przedstawiono wyniki księgowania:

- Wiersz 1 zawiera transakcję podatkową z kierunkiem podatku **Podatek należny**.
- Wiersz 2 zawiera transakcję podatkową z kierunkiem podatku **Podatek naliczony**.
- Wiersz 3 zawiera transakcję podatkową z kierunkiem podatku **Podatek naliczony**.
- Wiersz 4 zawiera transakcję podatkową z kierunkiem podatku **Podatek należny**.

## <a name="ssrs-vat-register-report"></a>Raport rejestru VAT dla usług SSRS

Raport **Rejestr VAT** jest raportem dotyczącym usług Microsoft SQL Server Reporting Services (SSRS) uznawanym za główny podsumowujący dokument podatkowy. Jest to podstawowy dokument używany w polskiej rachunkowości do raportowania podatków urzędowi skarbowemu. Jest to również główny dokument kontrolny w sprawozdawczości podatkowej w każdej polskiej firmie. Podatek VAT dla sprzedaży, zakupów i produktów importowanych musi być przetwarzany oddzielnie. Na raporcie **Rejestr VAT** opiera się deklaracja VAT. 

Ustawodawstwo określa także kilka oficjalnych raportów podatku VAT oraz warunki transakcji, które muszą zostać uwzględnione w raportach.

Rejestry VAT są drukowane regularnie według okresów sprawozdawczych. (Zazwyczaj są one drukowane co miesiąc). Raporty muszą być wydrukowane na papierze i podpisane przez co najmniej jedną uprawnioną osobę, taką jak główny księgowy lub dyrektor finansowy. Raporty te są używane jako podstawa miesięcznej deklaracji podatkowej VAT-7. Dostęp do raportów **Rejestr VAT** można uzyskać z kilku miejsc:

- **Podatek** &gt; **Zapytania i raporty** &gt; **Raporty podatków** &gt; **Sumaryczny rejestr podatku VAT (UE)**
- **Podatek** &gt; **Zapytania i raporty** &gt; **Raporty podatków** &gt; **Rejestr VAT zakupów**
- **Podatek** &gt; **Zapytania i raporty** &gt; **Raporty podatków** &gt; **Rejestr VAT sprzedaży**

## <a name="allowance-for-bad-debts"></a>Odpis na pokrycie prawdopodobnie nieściągalnych długów

Polskie przepisy prawa dotyczące podatku VAT regulują sytuacje, w których występują niezapłacone faktury i wymagana jest korekta VAT.

- Po stronie wierzyciela należny podatek VAT od niezapłaconych faktur (należności) można skorygować pod następującymi warunkami:

    - Towary lub usługi zostały dostarczone do czynnego płatnika podatku VAT.
    - Na dzień przed złożeniem deklaracji VAT, w której uwzględniony będzie odpis na pokrycie prawdopodobnie nieściągalnego długu, dłużnik jest czynnym płatnikiem podatku VAT i nie został postawiony w stanu upadłości ani likwidacji.
    - Należność nie jest zaległa o więcej niż dwa lata.

- Należny podatek VAT można skorygować za okres, w którym potwierdzono niemożność odzyskania należności. Innymi słowy, faktura nie została zapłacona w ciągu 150 dni od początkowej daty płatności. (Należność nie została sprzedana, a faktura nie została zapłacona).
- Po stronie dłużnika dłużnik jest zobowiązany skorygować naliczony podatek VAT od niezapłaconych należności, gdy od początkowej daty płatności faktury zakupu minie 150 dni. Ten wymóg jest bezwarunkowy. Dlatego korektę należy zrobić, nawet jeśli dłużnik nie skorzysta z odpisu na pokrycie prawdopodobnie nieściągalnych długów.
- Jeśli faktura zostanie zapłacona (lub wierzyciel sprzeda należność) po skorzystaniu z odpisu na pokrycie prawdopodobnie nieściągalnych długów, taki odpis należy wycofać w deklaracji VAT za okres, w którym faktura została zapłacona (lub w którym wierzyciel sprzedał należność). Jeśli płatność była płatnością częściową, wycofanie również powinno być częściowe i proporcjonalne do początkowej kwoty faktury.
- Księgowy pracujący w module Rozrachunki z dostawcami lub Rozrachunki z odbiorcami musi okresowo wskazywać prawdopodobnie nieściągalne długi. Długi traktuje się jako prawdopodobnie nieściągalne, gdy faktury pozostają niezapłacone przez ponad 150 dni, ale nie więcej niż dwa lata, od zaplanowanej daty płatności.
- Naliczony oraz należny podatek VAT można i należy skorygować (wycofać) dla wskazanych długów. Jednak za podjęcie ostatecznej decyzji odpowiada księgowy. W związku z tym księgowy ręcznie wyłączyć niektóre faktury, które zostały zidentyfikowane automatycznie.
- Jeśli długi zostaną spłacone w kolejnym okresie obrachunkowym, podatek VAT należy wycofać proporcjonalnie do kwoty płatności.
- Procedura okresowa pozwala wskazać prawdopodobnie nieściągalne długi na podstawie otwartych transakcji dostawcy oraz rozliczeń dostawcy lub klienta z jednej strony oraz harmonogramu płatności z drugiej strony.
- Podatek VAT w kwocie zidentyfikowanego długu jest przydzielany między kodami VAT w wierszach wycofywanej faktury.
- Kwoty rozliczonych płatności również są przydzielane w ten sam sposób do kodów VAT w wierszach wycofywanej faktury.
- Jeśli wystąpi błąd, arkusze można anulować, począwszy od ostatniego arkusza. Transakcje zostaną wycofane.
- Kwoty podatku VAT są przydzielane poprzez księgowanie.
- Należy skonfigurować główne konta księgowe do księgowania korekt podatku VAT oraz okresy dla prawdopodobnie nieściągalnych długów.

Aby skonfigurować funkcję odpisów na pokrycie prawdopodobnie nieściągalnych długów, należy najpierw skonfigurować system. Wykonaj następujące kroki.

1. Wybierz kolejno opcje **Księga główna** &gt; **Ustawienia arkusza** &gt; **Obliczanie arkusza zaległości**, aby skonfigurować obliczenia dla arkusza zaległości.
2. Wybierz typ arkusza:

    - Arkusz dotyczący transakcji VAT klienta
    - Arkusz dotyczący transakcji VAT dostawcy

3. Dla każdego arkusza ustaw następujące pola:

   - **Minimalna liczba dni:** wprowadź minimalny okres, po którym faktura zostanie uznana za zaległą. Minimalny okres wynosi zazwyczaj 150 dni.
   - **Maksymalna liczba dni:** wprowadź maksymalny okres, przez który faktura nie będzie uznawana za zaległą. Maksymalny okres wynosi zazwyczaj dwa lata lub 720 dni.
   - **Typ obliczania:** umożliwia wybranie typu daty dla każdej zaległej faktury do obliczenia. Dostępne wartości to **Termin** i **Data faktury**.
   - **Sprawdzanie poprawności:** zaznaczenie tego pola wyboru spowoduje sprawdzanie, czy salda transakcji nie uległy zmianie na dzień ostatnio zaksięgowanego arkusza.

     > [!NOTE]
     > Pola **Warunek** i **Terminy płatności** pozostaw puste.

4. Na stronach **Parametry rozrachunków z odbiorcami** i **Parametry rozrachunków z dostawcami** ustaw następujące odwołania sekwencji numerów:

    - Numer arkusza do zaległej kwoty podatku VAT stanowiącej zadłużenie
    - Arkusz podatku VAT dotyczącego zaległego zadłużenia

5. Wybierz kolejno opcje **Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Grupa księgowania w księdze** i wybierz główne konta księgowe dla opcji **Konto przeciwstawne stornowania zapisu podatku przychodzącego** i **Konto przeciwstawne stornowania zapisu podatku wychodzącego**.

Po skonfigurowaniu systemu można zarządzać zaległymi długami za pomocą funkcji okresowej **Zaległości VAT** dostępnej w sekcjach Rozrachunki z dostawcami i Rozrachunki z odbiorcami. Na stronie można wykonać następujące akcje:

- **Utwórz arkusz** — pozwala ustawić datę obliczenia kwoty zadłużenia. Interwał dat jest obliczany automatycznie na podstawie ustawień obliczania arkusza zaległości.

    > [!NOTE]
    > Podczas tworzenia arkusza wszystkie zaległe niezapłacone faktury dla okresów arkusza zostaną uwzględnione automatycznie. Arkusz zawiera także faktury, dla których w tym okresie przetworzono płatności. Informacje są dostępne w polach **Kwota zapłacona** i **Zapłacona kwota podatku**.
    
    Można wybrać numer arkusza, aby wyświetlić szczegóły arkusza i przejrzeć karty:

    - **Nagłówek arkusza podatku VAT dotyczącego zaległego zadłużenia** — można przełączać między widokiem **Wiersze** a widokiem **Nagłówek**.
    - **Wiersze arkusza podatku VAT dotyczącego zaległego zadłużenia** — wiersze zawierają informacje o fakturach odbiorcy lub dostawcy sklasyfikowanych jako posiadający prawdopodobnie nieściągalne długi w okresie sprawozdawczym. Można zaznaczyć pole wyboru **Wyklucz**, aby wykluczyć z arkusza wszelkie faktury, których nie chce się przetwarzać. Nie można wykluczyć faktury, jeśli jakakolwiek jej część została już przetworzona (tzn. jeśli zakończono zwrot podatku VAT). Sumy kwot w kolumnach są odzwierciedlane w nagłówku. Po zastosowaniu filtra do wierszy kwoty są obliczane ponownie.
    - **Szczegóły wiersza** — informacje zawierają szczegóły dotyczące konta odbiorcy lub dostawcy, transakcji i kwoty zaległości.

- **Księgowanie arkusza** — pozwala utworzyć transakcję wycofania podatku VAT dla faktur uwzględnionych w arkuszu. Po zaksięgowaniu arkusza można anulować tę akcję.
- **Anuluj zaksięgowany arkusz** — funkcja anulowania jest dostępna tylko dla ostatniego arkusza. Podczas anulowania, można wybrać typ korekty transakcji (korektę lub wycofanie), zaznaczając pole wyboru **Korekta** w oknie dialogowym.
- **Sprawdź załączniki** — umożliwia wyświetlanie transakcji załączników utworzonych podczas księgowania lub anulowania.
- **Sprawdź podatek zaksięgowany** — pozwala wyświetlić zaksięgowane transakcje podatkowe przydzielone do kodów podatku z faktur.
- **Otwórz zliczanie** — umożliwia wyświetlanie informacji podsumowujących dla odbiorcy lub dostawców i faktury dla odbiorców lub dostawców uwzględnionych w arkuszu.

Okienko pola informacji zawiera kwoty dla wszystkich faktur, które dotyczą prawdopodobnie nieściągalnych długów i nie zostały zapłacone na koniec okresu sprawozdawczego. Wyświetlana jest również zaległa kwota oraz zaległa kwota podatku.

## <a name="remove-costs-from-overdue-invoices"></a>Usuwanie kosztów z zaległych faktur

Zasady opodatkowania w Polsce wymagają, aby firmy nie miały zaległych płatności na rzecz zleceniobiorców. Firmy są również karane, jeśli nie płacą w terminie. Kara polega na tym, że nie można potraktować kosztów wynikających z zaległych faktur jako kosztów do odliczenia od podatku dochodowego od osób fizycznych (PIT) / podatku dochodowego od osób prawnych (CIT).

Faktur nie można uwzględnić w odliczeniach od podatku, jeśli wystąpi jedna z następujących sytuacji:

- Termin płatności przy początkowej dacie płatności jest krótszy niż 60 dni, a faktura nie została zapłacona w ciągu 30 dni od początkowej daty płatności.
- Termin płatności przy początkowej dacie płatności jest dłuższy niż 60 dni, a faktura nie została zapłacona w ciągu 90 dni od daty uwzględnionej w kosztach podatkowych (na przykład daty lub okresu księgowania).

Ze względu na przepisy dotyczące podatku PIT/CIT korektę kosztów należy wykonać w miesiącu, w którym zostały one wykluczone z kosztów podatkowych, a wycofać korektę należy w miesiącu, w którym faktura została w końcu zapłacona. Jeśli faktura została zapłacona częściowo, można również wykonać częściową korektę lub wycofanie.

Korektę kosztów stosuje się, jeśli faktura jest kosztem bezpośrednim (na przykład czynszem za wynajem biura) lub gdy nie jest zaksięgowana bezpośrednio na konta kosztów. Jeśli na przykład faktura jest związana z zakupem środka trwałego, amortyzacja środka trwałego nie jest kosztem, który można odliczyć od podatku. Ewentualnie faktura jest związana z zakupem towarów do odsprzedaży, a kosztu sprzedanych towarów nie można odliczyć od podatku.

> [!NOTE]
> Tę funkcję opisano w tym miejscu tylko w celu umożliwienia użytkownikowi stwierdzenia, czy jakiekolwiek faktury wymagają korekty. Do obowiązków użytkownika należy zastosowanie wymaganych korekt przy księgowaniu.

Aby skorzystać z ten funkcji należy odpowiednio skonfigurować system. Wykonaj następujące kroki.

1. Wybierz kolejno opcje **Księga główna** &gt; **Ustawienia arkusza** &gt; **Obliczanie arkusza zaległości**, aby skonfigurować interwały zaległości.

    Oto przykład typowej konfiguracji interwałów.

    - **Okres 1:** utwórz nowy wpis, wybierz typ arkusza **CIT i PIT dostawcy**, a następnie ustaw następujące pola:

        - **Minimalna liczba dni:** umożliwia określenie minimalnej liczby dni. Minimalna liczba dni wynosi zazwyczaj 30.
        - **Maksymalna liczba dni:** umożliwia określenie maksymalnej liczby dni. Maksymalna liczba dni wynosi zazwyczaj 360.
        - **Typ obliczania:** to pole służy do definiowania daty dla każdej zaległej faktury do obliczenia. Wybierz opcję **Termin**.
        - **Warunek:** określ **<**.
        - **Terminy płatności:** umożliwia określenie liczby dni po terminie. Liczba dni wynosi zazwyczaj 60.
        - **Sprawdzanie poprawności:** ustaw w tym polu wartość **Prawda**, jeśli wymagane jest sprawdzanie poprawności wprowadzanych i rozliczanych faktur.

    - **Okres 2:** utwórz nowy wpis, wybierz typ arkusza **CIT i PIT dostawcy**, a następnie ustaw następujące pola:

        - **Minimalna liczba dni:** umożliwia określenie minimalnej liczby dni. Minimalna liczba dni wynosi zazwyczaj 90.
        - **Maksymalna liczba dni:** umożliwia określenie maksymalnej liczby dni. Maksymalna liczba dni wynosi zazwyczaj 360.
        - **Typ obliczania:** to pole służy do definiowania daty dla każdej zaległej faktury do obliczenia. Wybierz opcję **Data faktury**. (W takim przypadku uwzględnia się datę wysyłki).
        - **Warunek:** określ **>=**.
        - **Terminy płatności:** umożliwia określenie liczby dni po terminie. Liczba dni wynosi zazwyczaj 60.
        - **Sprawdzanie poprawności**: ustaw w tym polu wartość **Prawda**, aby dla transakcji fakturowanych sprawdzano, czy całkowita kwota zaległości pozostaje taka sama, jak na dzień ostatniego arkusza zaległości.

2. Na stronie **Parametry rozrachunków z dostawcami** ustaw następujące pola:

    - **Wymiar do obliczenia korekty CIT i PIT:** umożliwia określenie wymiaru służącego do przydzielania prawdopodobnie nieściągalnych długów. (Aby uzyskać dostęp do tego pola, wybierz opcję **Księga i podatek**, a następnie wybierz kartę **CIT (podatek dochodowy od osób prawnych) i PIT (podatek dochodowy od osób fizycznych)**).
    - **Sekwencja numerów:** pozwala skonfigurować odwołanie do **arkusza CIT i PIT zaległości podatkowej**.

Po skonfigurowaniu kosztów niepodlegających odliczeniu na stronie **Arkusze CIT i PIT zaległości podatkowej dostawcy** można skonfigurować następujące zadania:

- **Utwórz arkusz** — w polu **Data** ustaw ostatni dzień okresu raportowania arkusza jako datę raportowania. Dokumenty są wybierane na podstawie dwóch ustawionych wcześniej warunków. Po utworzeniu arkusza suma zadłużenia zostanie przydzielona proporcjonalnie do wymiarów finansowych przypisanych w wierszach faktury.

    > [!NOTE]
    > Przycisk **Nowy** jest dostępny tylko wówczas, gdy strona jest pusta lub ostatni arkusz został zatwierdzony.

    Można wybrać numer arkusza, aby wyświetlić szczegóły arkusza i przejrzeć karty:

    - **Nagłówek arkusza podatku CIT i PIT dotyczącego zaległego zadłużenia** — można przełączać między widokiem **Wiersze** a widokiem **Nagłówek**.
    - **Wiersze arkusza CIT i PIT zaległości podatkowej** — pozwala uwzględnić informacje na temat faktur dostawców wybranych zgodnie z kryteriami skonfigurowanymi dla okresu. Za pomocą pola wyboru **Wyklucz** można wykluczyć z arkusza dowolną fakturę.
    - **Szczegóły wiersza**

- **Zatwierdzanie arkusza**
- **Anuluj zatwierdzenie arkusza** — funkcja anulowania jest dostępna tylko dla ostatniego zatwierdzonego arkusza.
- **Wyświetl dystrybucje** — pozwala wyświetlić rozkład kwoty zadłużenia według wymiaru finansowego.
- **Drukowanie raportu**

Okienko pola informacji zawiera sumy w arkuszu oraz łączną kwotę zaległości.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]