---
title: "Raporty podatków dla Polski (konfigurowanie informacji podatkowych i innych funkcji)"
description: "Ten temat zawiera informacje o sprawozdawczości podatku VAT w Polsce oraz podaje informacje, które są wymagane przez prawo w rejestrach podatku VAT w Polsce."
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 274063
ms.search.region: Poland
ms.author: shylaw
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4f256733cc2afa6c81c88ccc3435b28e1c4570e1
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-reports-for-poland-setting-up-tax-information-and-other-features"></a>Raporty podatków dla Polski (konfigurowanie informacji podatkowych i innych funkcji)
[!include[banner](../includes/banner.md)]

Ten temat zawiera informacje o sprawozdawczości podatku VAT w Polsce oraz podaje informacje, które są wymagane przez prawo w rejestrach podatku VAT w Polsce. 

## <a name="poland---vat-report-date-codes"></a>Polska — Kody dat raportu VAT

Zgodnie z polską ustawą o rachunkowości, która weszła w życie dnia 29 września 1994 r., podatek od towarów i usług (VAT) dla sprzedaży, zakupów i produktów importowanych musi być przetwarzany oddzielnie. Dla każdej zaksięgowanej transakcji sprzedaży lub zakupu, która ma ustawione pole **Data rejestru VAT** lub **Kod daty rejestru VAT**, podatek będzie wykazywany w odpowiednich rejestrach podatku VAT. Pole **Kod daty rejestru VAT** znajduje się na kilku stronach transakcji. Podczas aktualizowania lub księgowania transakcji informacje o kodzie daty raportu VAT są księgowane w tabelach podatku. Następnie będą drukowane w polskim rejestrze podatku VAT. Aby skonfigurować kody dat raportu VAT, otwórz stronę **Kody dat raportu VAT** (**Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Kody dat raportu VAT**) i ustaw następujące pola:

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
<td>Kod daty rejestru VAT</td>
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
<li><strong>Z datą raportu VAT</strong> - Raport pokazuje całą kwotę faktury, jeśli obliczona data w polu <strong>Data rejestru VAT</strong> na stronie <strong>Księgowanie faktury</strong> mieści się w przedziale dat objętym raportem.</li>
<li><strong>Z datą raportu VAT nie później niż</strong>  Raport pokazuje całą kwotę faktury, jeśli data w polu <strong>Data rejestru VAT</strong> mieści się w przedziale dat objętym raportem. Data jest obliczana na podstawie informacji w polach <strong>Liczone od</strong> i <strong>Liczba dni</strong>.</li>
<li><strong>Z datą fizycznej płatności</strong> - W przypadku zaznaczenia pola wyboru <strong>Rozliczenia częściowe</strong> raport pokazuje rozliczoną część kwoty faktury, jeśli interwał raportowania obejmuje daty płatności. Jeśli pole wyboru <strong>Rozliczenia częściowe</strong> jest wyczyszczone, raport nie pokazuje kwoty faktury, dopóki faktura nie zostanie całkowicie rozliczona.</li>
<li><strong>Z datą fizycznej płatności nie później niż</strong> - W przypadku zaznaczenia pola wyboru <strong>Rozliczenia częściowe</strong> raport pokazuje rozliczenia, dokonane w przedziale dat objętym raportem. Jeśli obliczona wartość w polu <strong>Data rejestru VAT</strong> znajduje się w zakresie dat raportu, raport pokazuje łączną kwotę faktury, z wyjątkiem rozliczonych kwot poprzedniego okresu. Jeśli pole wyboru <strong>Rozliczenie częściowe</strong> jest wyczyszczone, wybierz opcję <strong>Data transakcji</strong> lub <strong>Data VAT</strong> w polu <strong>Liczone od</strong>, aby określić kryterium używane do obliczania daty rejestru VAT.</li>
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
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Parametry</strong> <strong>modułu</strong> <strong>rozrachunków z dostawcami</strong>.</li>
</ul></td>
<td>Na karcie <strong>Ogólne</strong> na skróconej karcie <strong>Dostawca</strong> wprowadź kod daty raportu VAT, który powinien być używany jako domyślny kod dla nowych dostawców.</td>
</tr>
<tr class="even">
<td>Parametry modułu rozrachunków z odbiorcami
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki</strong> <strong>z dostawcami</strong> &gt; <strong>Konfiguracja</strong> &gt; <strong>Parametry</strong> <strong>modułu</strong> <strong>rozrachunków z odbiorcami</strong>.</li>
</ul></td>
<td>Na karcie <strong>Ogólne</strong> na skróconej karcie <strong>Odbiorca</strong> wprowadź kod daty raportu VAT, który powinien być używany jako domyślny kod dla nowych zamówień zakupu.</td>
</tr>
<tr class="odd">
<td>Obsługa przedpłat
<ol>
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Szczegóły</strong> <strong>dostawcy</strong> &gt; <strong>Transakcje</strong>. -lub- Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Szczegóły</strong> <strong>odbiorcy</strong> &gt; <strong>Transakcje</strong>.</li>
<li>Zaznacz transakcję przedpłaty, a następnie kliknij przycisk <strong>Obsługa przedpłat</strong>.</li>
</ol></td>
<td>Pole <strong>Kod daty rejestru VAT</strong> jest widoczne, jeśli wybrano opcję <strong>Zaawansowane</strong> w polu <strong>Obsługa przedpłat</strong> na stronie <strong>Parametry modułu rozrachunków z dostawcami</strong> lub <strong>Parametry modułu rozrachunków z odbiorcami</strong>.</td>
</tr>
<tr class="even">
<td>Zatwierdzenie faktury od dostawcy
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Arkusz zatwierdzania faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Pula faktur
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Pula faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Rejestr faktur od dostawców
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Rejestr faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Arkusz faktur od dostawców
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Arkusz faktur</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Wszystkie zamówienia zakupu
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Zamówienia zakupu</strong> &gt; <strong>Wszystkie zamówienia zakupu</strong>.</li>
</ul></td>
<td>Kod daty raportu VAT jest wyświetlany w nagłówku.</td>
</tr>
<tr class="odd">
<td>Specyfikacja
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Dostawcy</strong> &gt; <strong>Wszyscy dostawcy</strong>. Na karcie <strong>Faktura</strong> w grupie <strong>Rozlicz</strong> kliknij opcję <strong>Rozlicz transakcje</strong>. Kliknij kolejno opcje <strong>Informacje</strong> &gt; <strong>Specyfikacje</strong>. Następnie na karcie <strong>Ustawienia</strong> w polu <strong>Widok</strong> zaznacz opcję <strong>Zakup</strong>. -lub- Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Odbiorcy</strong> &gt; <strong>Wszyscy odbiorcy</strong>. Na karcie <strong>Windykacja</strong> w grupie <strong>Rozlicz</strong> kliknij opcję <strong>Rozlicz transakcje</strong>. Kliknij kolejno opcje <strong>Informacje</strong> &gt; <strong>Specyfikacje</strong>. Następnie na karcie <strong>Ustawienia</strong> w polu <strong>Widok</strong> zaznacz opcję <strong>Zamówienie sprzedaży</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Załącznik arkusza
<ul>
<li>Na stronie arkusza finansowego, arkusza okresowego, arkusza kasowego lub arkusza wydatków kliknij opcję <strong>Wiersze</strong>.</li>
</ul></td>
<td>Zapoznaj się z kartą <strong>Faktura</strong> lub kartą <strong>Płatność</strong>. <strong>Uwaga:</strong> Dla arkusza wydatków pole <strong>Typ konta przeciwstawnego</strong> należy ustawić na <strong>Dostawca</strong>.</td>
</tr>
<tr class="odd">
<td>Zamówienie sprzedaży
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Zamówienia</strong> &gt; <strong>Wszystkie zamówienia sprzedaży</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Faktura niezależna
<ul>
<li>Kliknij kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Faktury</strong> &gt; <strong>Faktury niezależne</strong>.</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Zaksięgowany podatek
<ul>
<li>Kliknij kolejno opcje <strong>Podatek</strong> &gt; <strong>Zapytania i raporty</strong> &gt; <strong>Zapytania o podatki</strong> &gt; <strong>Zaksięgowany podatek</strong>.</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="poland---name-of-services-for-vat-reporting"></a>Polska — Nazwy usług raportowania podatku VAT
Numery taryf usługowych są wymagane podczas raportowania informacji o podatku VAT związanych z transakcją ze stroną, która nie znajduje się w Polsce. Numery taryf usługowych ustawia się na stronie **Numery taryf usługowych**. Aby skonfigurować numery taryf usługowych, kliknij kolejno opcje **Podatek** &gt; **Ustawienia** &gt; **Podatek** &gt; **Numer taryfy usługowej** i ustaw następujące pola:

| Pole                      | opis                                                                          |
|----------------------------|--------------------------------------------------------------------------------------|
| Numer taryfy usługowej      | Wprowadź numer taryfy usługowej, który został przypisany do strony przez organ administracji państwowej. |
| Opis taryfy usługowej | Umożliwia wprowadzanie opisu numeru taryfy usługowej.                                    |

Można również ustawić parametr obowiązkowości numeru taryfy usługowej. Kliknij kolejno opcje **Podatek** &gt; **Podatek** &gt; **Grupa podatków**, a następnie na skróconej karcie **Ogólne** ustaw pole **Obowiązkowy numer taryfy usługowej**. Parametr **Obowiązkowy numer taryfy usługowej** parametr ma wpływ na następujące strony:

-   **Wszystkie zamówienia sprzedaży** (kliknij kolejno opcje **Rozrachunki z odbiorcami** &gt; **Zamówienia** &gt; **Wszystkie zamówienia sprzedaży**) (nagłówek i wiersze)
-   **Wszystkie faktury niezależne** (kliknij kolejno opcje **Rozrachunki z odbiorcami** &gt; **Faktury**&gt; **Wszystkie faktury niezależne**) (nagłówek i wiersze)
-   **Unieważnione zamówienia sprzedaży** (kliknij kolejno opcje **Sprzedaż i marketing** &gt; **Zapytania i raporty** &gt; **Historia** &gt; **Unieważnione zamówienia sprzedaży**, a następnie opcję **Pokaż**)

Następujące wspólne funkcje działają na wszystkich powyższych stronach:

-   Podczas tworzenia nowego wiersza numer taryfy usługowej jest kopiowany z nagłówka do wiersza.
-   Jeśli parametr **Obowiązkowy numer taryfy usługowej** jest włączony w grupie podatków, faktura zostanie zatrzymana i pojawi się komunikat o błędzie.
-   Podczas księgowania faktury transakcje podatku są dzielone według numerów taryf usługowych. Nawet grupa podatków i grupa podatków dla towaru są takie same.
-   Podczas tworzenia faktury korygującej dla dowolnej zaksięgowanej faktury, której wiersze mają wartość w polu **Numer taryfy usługowej**, numer taryfy usługowej jest kopiowany do wierszy faktury korygującej z oryginalnego dokumentu, a nie z nagłówka faktury korygującej. Numer taryfy usługowej może być edytowany dla wiersza korekty.

## <a name="poland---base-amount-for-vat"></a>Polska — Kwota podstawy podatku VAT
Pole **Kwota podstawy podatku VAT** jest włączone podczas wprowadzania transakcji podatku (pole **Kod podatku** ma wartość w wierszach arkusza) w następujących arkuszach:

-   Arkusz faktur (kliknij kolejno opcje **Rozrachunki z dostawcami** &gt; **Arkusze** &gt; **Faktury** &gt; **Arkusz faktur**, kliknij opcję **Wiersze**, a następnie kliknij kartę **Ogólne**)
-   Arkusz finansowy (kliknij kolejno opcje **Księga główna** &gt; **Arkusze** &gt; **Arkusz finansowy**, kliknij opcję **Wiersze**, a następnie kliknij kartę **Ogólne**)
-   Arkusz kasowy (kliknij kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Transakcje kasowe** &gt; **Arkusz kasowy**, kliknij opcję **Wiersze**, a następnie kliknij kartę **Ogólne**)

W polu **Kwota podstawy podatku VAT** należy ręcznie wprowadzić kwotę podstawy podatku. Po zaksięgowaniu arkusza wartość z pola **Kwota podstawy podatku VAT** jest przenoszona do pola **Podstawa opodatkowania** w transakcjach podatkowych.

## <a name="poland---sales-tax-vat-reporting"></a>Polska — Raportowanie podatku (VAT)
Ta funkcja jest używana w arkuszach księgi, gdzie wiele wierszy ma ten sam załącznik. Gdy poniższe pola w jednym wierszu ulegają zmianie, pojawia się okno komunikatu umożliwiające zaktualizowanie pól w innych wierszach mających ten sam załącznik:

-   Faktura VAT
-   Data dokumentu
-   Adres
-   NIP
-   Odbiorca/dostawca
-   Data rejestru VAT
-   Kod daty rejestru VAT

> [!NOTE]
> Okno komunikatu pojawia się tylko wtedy, gdy pola zostały zmodyfikowane dla wiersza, w którym skonfigurowano grupę podatków, grupę podatków dla towaru i kod podatku. Komunikat jest wywoływany na następujących stronach arkusza:

-   Arkusz finansowy (kliknij kolejno opcje **Księga główna** &gt; **Arkusze** &gt; **Arkusz finansowy**, a następnie kliknij opcję **Wiersze**)
-   Arkusz faktur (kliknij kolejno opcje **Rozrachunki z dostawcami** &gt; **Arkusze** &gt; **Faktury** &gt; **Arkusz faktur**, a następnie kliknij opcję **Wiersze**)

## <a name="poland---tax-direction-for-the-line"></a>Polska — Kierunek podatku dla wiersza
Ta funkcja dotyczy księgowań za pośrednictwem arkusza finansowego, który obejmuje transakcje podatkowe. System automatycznie ustala kierunek podatku, który powinien być przypisywany do tworzonych transakcji podatkowych, w oparciu o typ konta użyty do księgowania. Ta funkcja umożliwia poprawne ustalenie kont głównych i poprawne przypisanie kierunku podatku dla wierszy arkusza finansowego w tym samym załączniku. Wiersze muszą spełniać jeden z następujących warunków:

-   Konto jest typu **Odbiorca**, **Dostawca** lub **Gotówka podręczna**, a typem konta przeciwstawnego jest **Księga**. Konto przeciwstawne musi być określone.
-   Konto jest typu **Księga**, a typem konta przeciwstawnego jest **Odbiorca**, **Dostawca** lub **Gotówka podręczna**. Konto przeciwstawne musi być określone.

Dla wierszy arkusza finansowego spełniających powyższe warunki system przypisuje osobny kierunek podatku w następujący sposób:

-   **Podatek należny** dla typ konta **Odbiorca**
-   **Podatek naliczony** dla typ konta **Dostawca**
-   **Podatek należny** dla typ konta **Gotówka podręczna**

### <a name="example"></a>Przykład

Tworzysz następujące wiersze arkusza finansowego:

| Typ konta | Numer konta | Strona debetowa | Strona kredytowa | Typ konta przeciwstawnego | Numer konta przeciwstawnego | Grupa księgowania podatków | Grupa księgowania podatków dla towarów |
|--------------|----------------|-------|--------|---------------------|-----------------------|-------------------------|------------------------------|
| Odbiorca     | 1101           |       | 800    | Księga              | 0101                  | AR-DOM                  | PEŁNE                         |
| Dostawca       | 1001           |       | 800    | Księga              | 0101                  | AR-DOM                  | PEŁNE                         |
| Księga       | 0102           | 700   |        |                     |                       | AR-DOM                  | PEŁNE                         |
| Księga       | 0103           |       | 700    |                     |                       | AR-DOM                  | PEŁNE                         |

Poniżej przedstawiono wyniki księgowania:

-   Wiersz 1 zawiera transakcję podatkową z kierunkiem podatku **Podatek należny**.
-   Wiersz 2 zawiera transakcję podatkową z kierunkiem podatku **Podatek naliczony**.
-   Wiersz 3 zawiera transakcję podatkową z kierunkiem podatku **Podatek naliczony**.
-   Wiersz 4 zawiera transakcję podatkową z kierunkiem podatku **Podatek należny**.

## <a name="poland---ssrs-vat-register-report"></a>Polska — Raport rejestru podatku VAT usług SSRS
Raport **Rejestr VAT** jest traktowany jako główny dokument podsumowania podatku. Na tym raporcie jest oparta deklaracja VAT. Jest to główny dokument kontrolny w sprawozdawczości podatkowej w każdej polskiej firmie. Podatek VAT dla sprzedaży, zakupów i produktów importowanych musi być przetwarzany oddzielnie. Ustawodawstwo określa także kilka oficjalnych sprawozdań podatku VAT oraz warunki transakcji, które muszą zostać uwzględnione w sprawozdaniach. Raport **Rejestr VAT** jest podstawowym dokumentem używanym w polskiej rachunkowości do raportowania podatków urzędowi skarbowemu. Rejestry VAT są drukowane regularnie według okresów sprawozdawczych. (Zazwyczaj są drukowane co miesiąc). Raporty muszą być wydrukowane na papierze i podpisane przez jedną lub więcej uprawnionych osób, takich jak główny księgowy lub dyrektor finansowy. Raporty te są używane jako podstawa miesięcznej deklaracji podatkowej VAT-7. Dostęp do raportów **Rejestr VAT** można uzyskać z kilku miejsc:

-   Podatek &gt; Zapytania i raporty &gt; Raporty podatków &gt; Sumaryczny rejestr podatku VAT (UE)
-   Podatek &gt; Zapytania i raporty &gt; Raporty podatków &gt; Rejestr VAT zakupów
-   Podatek &gt; Zapytania i raporty &gt; Raporty podatków &gt; Rejestr VAT sprzedaży




