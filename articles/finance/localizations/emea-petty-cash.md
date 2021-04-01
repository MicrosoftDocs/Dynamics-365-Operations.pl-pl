---
title: Zarządzanie gotówką podręczną dla Europy Wschodniej i Rosji
description: Ten temat zawiera informacje o funkcji gotówki podręcznej, która pozwala użytkownikom w Estonii, na Litwie, w Czechach, na Węgrzech, na Łotwie, w Polsce i w Rosji uwzględniać operacje gotówkowe w systemie.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCashBalance, RCashCountStatementForm, RCashPosting, RCashRemainLimit, RCashReportJour_PL, RCashTable, RCashTableBalance, RCashTableCredLimit, RCashTableLastRevaluation, RCashTableTransactions, RCashTrans
audience: Application User
ms.reviewer: kfend
ms.custom: 268504
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: d6eaeb48184d30450a9da68b4f8419b1f3c77f6f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231503"
---
# <a name="petty-cash-for-eastern-europe-and-russia"></a>Zarządzanie gotówką podręczną dla Europy Wschodniej i Rosji

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o funkcji gotówki podręcznej, która pozwala użytkownikom w Estonii, na Litwie, w Czechach, na Węgrzech, na Łotwie, w Polsce i w Rosji uwzględniać operacje gotówkowe w systemie.

Funkcja gotówki podręcznej umożliwia automatyzację operacji przychodów i rozchodów gotówkowych, tworzenie dokumentów podstawowych i drukowanie powiązanych raportów. Funkcjonalność gotówki podręcznej umożliwia wykonywanie następujących operacji:

-   Rozliczanie przychodów i rozchodów dostępnych aktywów gotówkowych.
-   Generowanie typowych formularzy obrotu gotówkowego: dokumentów KP, dokumentów KW oraz arkusza rejestracji dokumentów kasowych.
-   Kontrolowanie maksymalnej kwoty środków pieniężnych dozwolonej w operacjach z odbiorcami, dostawcami itd.
-   Uwzględnianie operacji gotówkowych w różnych walutach w systemie.
-   Konwertowanie kwot operacji gotówkowych w walutach obcych na walutę domyślną na potrzeby sprawozdawczości księgowej.
-   Generowanie raportu **Księga kasowa** i raportu kasjera.

## <a name="prerequisites"></a>Wymagania wstępne
Aby można było używać funkcji gotówki podręcznej, należy wykonać następujące czynności wstępne:

-   Skonfigurowanie kont kasowych.
-   Skonfigurowanie profili księgowania kasy.
-   Skonfigurowanie numeracji dokumentów kasowych.
-   Skonfigurowanie domyślnych wartości modułu Zarządzanie gotówką i bankami.
-   Skonfigurowanie nazw arkuszy kasowych w księdze głównej.

### <a name="set-up-cash-accounts"></a>Konfigurowanie kont kasowych

Aby skonfigurować konto kasowe, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Konta bankowe** &gt; **Konta kasowe** i wprowadź następujące informacje:

| Pole                 | opis                                                                                                          |
|-----------------------|----------------------------------------------------------------------------------------------------------------------|
| Kasa                  | Wprowadź kod identyfikujący konto kasowe (obrót gotówką).                                                                    |
| Nazwisko                  | Wprowadź opis konta kasowego.                                                                             |
| Waluta              | Wybierz domyślny kod waluty dla transakcji kasowych.                                                              |
| Grupa sekwencji numerów | Jeśli numeracja dokumentów kasowych musi się różnić od numeracji określonej w parametrach, wprowadź odpowiedni kod. |
| Wiele walut       | Zaznacz to pole wyboru, aby umożliwić księgowanie walut różniących się od waluty rozliczeniowej.                     |
| Ujemne saldo kasowe         | Zaznacz to pole wyboru, aby zezwolić na ujemne salda kasowe w dowolnej walucie.                                               |

Aby skonfigurować reguły kontroli salda kasowego dla konta kasowego, wybierz konto kasowe, a następnie w okienku akcji na karcie **Konto kasowe** w grupie **Limit salda** kliknij opcję **Limit salda**. Wpisz następujące informacje.

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
<td>Typ waluty</td>
<td>Wybierz typ waluty:
<ul>
<li><strong>Waluta rozliczeniowa</strong> — użyj kodu waluty podstawowej firmy.</li>
<li><strong>Wskazana waluta</strong> — użyj kod waluty różniącego się od kodu waluty podstawowej firmy.</li>
</ul></td>
</tr>
<tr class="even">
<td>Waluta</td>
<td>Jeśli w polu <strong>Typ waluty</strong> zaznaczysz opcję <strong>Wskazana waluta</strong>, wybierz kod waluty. To pole nie jest dostępne, jeśli w polu <strong>Typ waluty</strong> wybrano opcję <strong>Waluta rozliczeniowa</strong>.</td>
</tr>
<tr class="odd">
<td>Typ ograniczenia salda</td>
<td>Wybierz jedną z dostępnych wartości:
<ul>
<li><strong>Maksimum</strong> — saldo kasowe nie powinno być wyższe, niż kwota w polu <strong>Limit salda</strong> dla konta kasowego (górna granica).</li>
<li><strong>Minimum</strong> — saldo kasowe nie powinno być niższe, niż kwota w polu <strong>Limit salda</strong> dla konta kasowego (dolna granica).</li>
</ul></td>
</tr>
<tr class="even">
<td>Sprawdź limit salda</td>
<td>Wybierz, co ma się dziać w procesie zatwierdzania dokumentów kasowych, jeśli kwota <strong>Limit salda</strong> dla konta kasowego zostanie przekroczona:
<ul>
<li><strong>Akceptuj</strong> — limit może zostać przekroczony.</li>
<li><strong>Ostrzeżenie</strong> — limit może zostać przekroczony, ale użytkownik otrzyma komunikat ostrzegawczy. Dokument kasowy jest potwierdzany lub zatwierdzany.</li>
<li><strong>Błąd</strong> — limit nie może zostać przekroczony. Użytkownik otrzymuje komunikat o błędzie, a dokument kasowy nie jest potwierdzany ani zatwierdzany.</li>
</ul>
Aby uzyskać więcej informacji na temat procesu zatwierdzania dokumentów kasowych, zobacz sekcję &quot;Zatwierdzanie i księgowanie transakcji kasowych&quot; w dalszej części tego tematu.</td>
</tr>
<tr class="odd">
<td>Limit salda</td>
<td>Wprowadź dopuszczalny limit salda konta kasowego. Kwota powinna być w ustawionej przez Ciebie walucie.</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-posting-profiles"></a>Konfigurowanie profili księgowania kasy

Profile księgowania kasy definiują sposób księgowania w księdze głównej. Aby skonfigurować profil księgowania kasy, wybierz kolejno opcje **Zarządzanie** **gotówką i bankami** &gt; **Ustawienia** &gt; **Profile księgowania kasy** i wybierz lub utwórz profil księgowania. Wpisz następujące informacje.

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
<td>Ważny dla</td>
<td>Określ, czy profil księgowania dotyczy określonego konta kasowego czy wszystkich kont kasowych:
<ul>
<li><strong>Tabela</strong> — jeśli dla konta kasowego istnieje wiersz profilu księgowania, ten wiersz jest używany do księgowania transakcji kasowych.</li>
<li><strong>Wszystko</strong> — nie istnieje żaden wiersz profilu księgowania dla konta kasowego.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kasa</td>
<td>Jeśli w polu <strong>Ważny dla</strong> wybrano opcję <strong>Tabela</strong>, określ konto kasowe. To pole pozostaje puste, jeśli w polu <strong>Ważne dla</strong> wybrano opcję <strong>Wszystko</strong>.</td>
</tr>
<tr class="odd">
<td>Konto księgowe</td>
<td>Wprowadź numer konta księgowego, które ma być używane jako konto rozrachunkowe dla konta kasowego.</td>
</tr>
</tbody>
</table>

### <a name="set-up-number-sequences-for-cash-documents"></a>Konfigurowanie numeracji dla dokumentów kasowych

Aby skonfigurować numerację dokumentów kasowych, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami**. Na karcie **Sekwencja numerów** określ kody numeracji dla dokumentów **Dokumenty KP**, **Dokumenty KW**, **Załącznik korekty kasowej** i **Różnica kursowa** oraz dla parametru **Numer raportu kasowego**.

### <a name="set-up-default-values-for-cash-and-bank-management-parameters"></a>Konfigurowanie domyślnych wartości modułu Zarządzanie gotówką i bankami

Aby skonfigurować domyślne wartości modułu Zarządzanie gotówką i bankami dla funkcji gotówki podręcznej, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami**. Na karcie **Kasa** wprowadź następujące informacje:

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
<td>Kasa</td>
<td>Wybierz domyślne konto kasowe, które będzie używane w arkuszach.</td>
</tr>
<tr class="even">
<td>Księgowanie kasy</td>
<td>Wprowadź domyślny profil księgowania kasy, który będzie używany, jeśli nie został określony profil księgowania.</td>
</tr>
<tr class="odd">
<td>Sprawdzanie użytego numeru załącznika</td>
<td>Wybierz, co się dzieje w razie znalezienia zduplikowanych numerów podczas sprawdzania numer dokumentu kasowego:
<ul>
<li>Odrzuć duplikaty</li>
<li>Odrzuć kopie w roku obrachunkowym</li>
<li>Dozwolone duplikaty</li>
<li>Ostrzegaj w przypadku duplikatów</li>
</ul></td>
</tr>
<tr class="even">
<td>Sprawdź limit operacji</td>
<td>Określ, co się dzieje po przekroczeniu limitu operacji z kontrahentami:
<ul>
<li><strong>Akceptuj</strong> — limit może zostać przekroczony.</li>
<li><strong>Ostrzeżenie</strong> — limit może zostać przekroczony, ale użytkownik otrzyma komunikat ostrzegawczy. Operacja jest księgowana.</li>
<li><strong>Błąd</strong> — limit nie może zostać przekroczony. Użytkownik otrzymuje komunikat o błędzie, a operacja nie jest księgowana.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Metoda weryfikacji</td>
<td>Wybierz metodę sprawdzania poprawności służącą do kontrolowania przekroczenia kwot limitów dla operacji:
<ul>
<li><strong>Operacja</strong> — sprawdzanie poprawności jest wykonywane dla każdej transakcji.</li>
<li><strong>Umowa</strong> — sprawdzanie poprawności jest wykonywane dla każdej transakcji mającej przypisaną umowę z kontrahentem.</li>
</ul></td>
</tr>
<tr class="even">
<td>Limit operacji</td>
<td>Wprowadź maksymalną dozwoloną kwotę transakcji kasowych z kontrahentami.</td>
</tr>
<tr class="odd">
<td>Księgowanie z wcześniejszą datą</td>
<td>Zaznacz to pole wyboru, aby umożliwić księgowanie transakcji kasowych z datą wcześniejszą niż data ostatniej transakcji kasowej.</td>
</tr>
<tr class="even">
<td>Wymiary</td>
<td>Wprowadź wymiary w polach <strong>Kod działu</strong>, <strong>Kod analityczny</strong> i <strong>Kod celu</strong>. Drukowana postać dokumentów kasowych będzie odzwierciedlała te informacje.</td>
</tr>
<tr class="odd">
<td>Użyj stanu potwierdzenia</td>
<td>Zaznacz to pole wyboru , aby korzystać z dodatkowego stanu <strong>Potwierdzone</strong> w procesie zatwierdzania dokumentów kasowych. (Aby uzyskać więcej informacji, zobacz sekcję &quot;Zatwierdzanie i księgowanie transakcji kasowych&quot;).</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-journal-names-in-general-ledger"></a>Konfigurowanie nazw arkuszy kasowych w księdze głównej

Aby utworzyć arkusz do księgowania transakcji kasowych, **Księga główna** &gt; **Konfiguracja arkusza** &gt; **Nazwy arkuszy** i utwórz nowy rekord. W polu **Typ arkusza** wybierz opcję **Kasa**. Zdefiniuj inne potrzebne domyślne parametry.

## <a name="daily-cash-operations-via-a-slip-journal"></a>Dokumentowanie codziennych operacje gotówkowych przy użyciu arkusza kasowego
Aby utworzyć dokument kasowy za pośrednictwem arkusza kasowego, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Transakcje kasowe** &gt; **Arkusz kasowy** i utwórz nowy arkusz. W okienku akcji kliknij pozycję **Wiersze**. Dodaj nowy wiersz i wprowadź następujące informacje:

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
<td>Data</td>
<td>Wprowadź datę transakcji.</td>
</tr>
<tr class="even">
<td>Konto</td>
<td>Wybierz konto kasowe. Domyślnie konto kasowe jest określone w oknie Parametry modułu Zarządzanie gotówką i bankami.</td>
</tr>
<tr class="odd">
<td>opis</td>
<td>Wprowadź tekst wyjaśniający o transakcji.</td>
</tr>
<tr class="even">
<td>Debet Kredyt</td>
<td>Wprowadź kwotę z dokumentu kasowego w jednym z następujących pól:
<ul>
<li><strong>Debet</strong> — to pole służy do rejestracji przychodów gotówkowych i dokumentu KP.</li>
<li><strong>Kredyt</strong> — to pole służy do rejestracji rozchodów gotówkowych i dokumentu KW.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Typ konta przeciwstawnego Konto przeciwstawne</td>
<td>Wybierz typ i numer konta przeciwstawnego.</td>
</tr>
<tr class="even">
<td>Waluta</td>
<td>Wybierz kod waluty transakcji.</td>
</tr>
<tr class="odd">
<td>Załącznik</td>
<td>To pole jest wypełniane automatycznie na podstawie ustawień arkusza.</td>
</tr>
<tr class="even">
<td>Numer zamówienia</td>
<td>Jeśli dla konta kasowego nie skonfigurowano innej numeracji, to pole jest wypełniane automatycznie na podstawie numeracji określonej w parametrach. W razie potrzeby można ręcznie wprowadzić numer zamówienia w tym polu. Aby zapobiec niespójnościom w numeracji dokumentów kasowych, stosuje się następującą kontrolę: numer dokumentu kasowego z wcześniejszą datą operacji nie może być wyższy niż numer dokumentu kasowego z późniejszą datą operacji. Jeśli nie potrzebujesz tej kontroli, zaznacz pole wyboru <strong>Księgowanie z wcześniejszą datą</strong> w oknie Parametry modułu Zarządzanie gotówką i bankami.</td>
</tr>
<tr class="odd">
<td>Stan zatwierdzenia</td>
<td>Pierwszym stanem transakcji jest <strong>Brak</strong>. Szczegółowe informacje o tym, jak ustawić stan transakcji, zawiera sekcja &quot;Zatwierdzanie i księgowanie transakcji kasowych&quot;.</td>
</tr>
<tr class="even">
<td>Typ dokumentu</td>
<td>To pole na karcie <strong>Zamówienie gotówkowe</strong> jest wypełniane automatycznie na podstawie kwoty wprowadzonej w dokumencie kasowym:
<ul>
<li><strong>Dokument KP</strong> — ta wartość jest używana, jeśli wprowadzono wartość w polu <strong>Debet</strong> dla konta kasowego.</li>
<li><strong>Dokument KW</strong> — ta wartość jest używana, jeśli wprowadzono wartość w polu <strong>Kredyt</strong> dla konta kasowego.</li>
<li><strong>Korekta</strong> — wprowadzono kwotę ujemną w polu <strong>Debet</strong> lub <strong>Kredyt</strong> dla konta kasowego.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Grupa podatków</td>
<td>Określ grupę podatków, która ma być używana do obliczania podatków od operacji.</td>
</tr>
<tr class="even">
<td>Grupa podatków dla pozycji</td>
<td>Określ grupę podatków od towarów, która ma być używana do obliczania podatków od operacji.</td>
</tr>
<tr class="odd">
<td>Przyczyna</td>
<td>Na karcie <strong>Zamówienie gotówkowe</strong> wprowadź tekst opisujący przedmiot transakcji. Ten tekst będzie drukowany w formularzu sprawozdawczym dokumentu kasowego.</td>
</tr>
<tr class="even">
<td>Data dokumentu</td>
<td>Wprowadź opis, numer i datę dokumentu podstawowego będącego powodem transakcji (na przykład raport o zaliczkach, faktura lub zamówienie).</td>
</tr>
<tr class="odd">
<td>Typ przedstawiciela</td>
<td>To pole może przyjmować następujące wartości:
<ul>
<li><strong>Pracownik</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę pracowników, jeśli pole <strong>Konto przeciwstawne</strong> zawiera wartość <strong>Księga</strong> lub <strong>Bank</strong>, albo listę osób kontaktowych u kontrahenta, jeśli pole <strong>Konto przeciwstawne</strong> zawiera wartość <strong>Odbiorca</strong> lub <strong>Dostawca</strong>. Aby skonfigurować przedstawicieli, wybierz kolejno opcje <strong>Podstawowe</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Kontakty</strong> &gt; <strong>Osoba kontaktowa</strong>.</li>
<li><strong>Inne</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę innych klientów. Aby skonfigurować odbiorców, którzy nie figurują w tabeli <strong>Odbiorcy</strong> ani <strong>Dostawcy</strong>, wybierz kolejno opcje <strong>Księga główna</strong> &gt; <strong>Odbiorcy</strong>. Ten typ jest dostępny tylko w Hiszpanii. (Musi być włączony klucz konfiguracji <strong>CSELatvia</strong>).</li>
<li><strong>Dostawca</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę dostawców. Aby skonfigurować dostawców, wybierz kolejno opcje <strong>Rozrachunki z dostawcami</strong> &gt; <strong>Dostawcy</strong>.</li>
<li><strong>Odbiorca</strong> — Wyszukiwanie <strong>Przedstawiciel</strong> zawiera listę odbiorców. Aby skonfigurować odbiorców, wybierz kolejno opcje <strong>Rozrachunki z odbiorcami</strong> &gt; <strong>Odbiorcy</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Przedstawiciel</td>
<td>Wybierz przedstawiciela o typie określonym w polu <strong>Typ przedstawiciela</strong>.</td>
</tr>
<tr class="odd">
<td>Nazwisko pracownika</td>
<td>To pole jest wypełniane automatycznie na podstawie zawartości pól <strong>Konto przeciwstawne</strong> i <strong>Przedstawiciel</strong>. Drukowana postać dokumentów kasowych będzie odzwierciedlała te informacje.</td>
</tr>
<tr class="even">
<td>Dowód tożsamości</td>
<td>To pole jest wypełniane automatycznie na podstawie danych dowodu tożsamości osoby kontaktowej (przedstawiciela). Jeśli pole <strong>Typ konta przeciwstawnego</strong> jest ustawione na <strong>Posiadacz zaliczki</strong>, a pole <strong>Konto przeciwstawne</strong> na numer pracownika, można dokonywać przychodów i rozchodów gotówkowych do i od tego pracownika. W takim przypadku pole <strong>Dowód tożsamości</strong> jest wypełniane automatycznie przy użyciu danych dowodu tożsamości z tabeli <strong>Pracownik</strong> (<strong>Księgowanie personelu</strong> &gt; <strong>Tabela pracowników</strong>).</td>
</tr>
<tr class="odd">
<td>Cel</td>
<td>W tabeli <strong>Cel</strong> zdefiniuj jeden lub więcej kodów przeznaczenia kwoty transakcji. Wybierz kod przeznaczenia w polu <strong>Cel</strong> i wpisz wyjaśnienie w polu <strong>Tekst transakcji</strong>. W polu <strong>Kwota</strong> wpisz kwotę w walucie transakcji. Pole <strong>Procent</strong> pokazuje (w procentach) stosunek kwoty docelowej do łącznej kwoty transakcji.</td>
</tr>
<tr class="even">
<td>Upomnienie</td>
<td>Obliczana pozostała kwota. Należy zauważyć, że cała kwota transakcja musi być przypisana do kodów przeznaczenia.</td>
</tr>
<tr class="odd">
<td>Dane urzędowe</td>
<td>Na karcie <strong>Dane urzędowe</strong> podaj imiona, nazwiska i tytuły osób odpowiedzialnych: dyrektora, głównego księgowego i kasjera. Wartości pola <strong>Pozycja</strong> są określane przez konfigurację danych urzędowych na kartach <strong>Ogólne</strong> i <strong>Księga</strong> na stronie <strong>Dane urzędowe</strong> (<strong>Podstawowe</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Kontakty</strong> &gt; <strong>Dane urzędowe</strong>).</td>
</tr>
<tr class="even">
<td>Zaliczka</td>
<td>Należy zaznaczyć to pole wyboru, jeśli transakcja jest przedpłatą.</td>
</tr>
<tr class="odd">
<td>Profil księgowania</td>
<td>Wprowadź profil księgowania konta kasowego. Domyślnie jest używany profil księgowania określony w oknie Parametry modułu Zarządzanie gotówką i bankami.</td>
</tr>
<tr class="even">
<td>Profil księgowania przeciwstawnego</td>
<td>Wprowadź profil księgowania wybranego konta przeciwstawnego.</td>
</tr>
<tr class="odd">
<td>Suma</td>
<td>W grupie pól <strong>Suma</strong> u dołu strony pole <strong>Zwroty</strong> zawiera sumę obliczaną dla wszystkich dokumentów KP wprowadzonych w bieżącym arkuszu, a pole <strong>Rozch</strong> zawiera sumę ze wszystkich dokumentów KW.</td>
</tr>
</tbody>
</table>

Aby sprawdzić zapisy w arkuszu, w okienku akcji kliknij przycisk **Weryfikuj**.

## <a name="daily-cash-operations-via-a-general-journal"></a>Dokumentowanie codziennych operacje gotówkowych przy użyciu arkusza finansowego
Aby utworzyć transakcję kasową za pomocą arkusza finansowego, wybierz kolejno opcje **Księga główna** &gt; **Wpisy w arkuszu** &gt; **Arkusze finansowe** i utwórz nowy arkusz. W okienku akcji kliknij pozycję **Wiersze**. Dodaj nowy wiersz i wprowadź następujące informacje:

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
<td>Data</td>
<td>Wprowadź datę transakcji.</td>
</tr>
<tr class="even">
<td>Typ konta</td>
<td>Wybierz opcję <strong>Gotówka podręczna</strong>.</td>
</tr>
<tr class="odd">
<td>Konto</td>
<td>Wybierz numer konta kasowego.</td>
</tr>
<tr class="even">
<td>Tekst transakcji</td>
<td>Wprowadź tekst wyjaśniający o transakcji.</td>
</tr>
<tr class="odd">
<td>Debet Kredyt</td>
<td>Wprowadź kwotę z dokumentu kasowego w jednym z następujących pól:
<ul>
<li><strong>Debet</strong> — to pole służy do rejestracji przychodów gotówkowych i dokumentu KP.</li>
<li><strong>Kredyt</strong> — to pole służy do rejestracji rozchodów gotówkowych i dokumentu KW.</li>
</ul></td>
</tr>
<tr class="even">
<td>Typ konta przeciwstawnego Konto przeciwstawne</td>
<td>Wybierz typ i numer konta przeciwstawnego.</td>
</tr>
<tr class="odd">
<td>Waluta</td>
<td>Wybierz kod waluty transakcji.</td>
</tr>
</tbody>
</table>

Na karcie **Faktura** można określić profile księgowania dla wybranego konta i konta przeciwstawnego. Jeżeli zarejestrowana transakcja to przedpłata, zaznacz pole wyboru **Przedpłata** na karcie **Płatność**. W grupie pola **Przedstawiciel** uzupełnij pola tak jak w wierszach arkusza kasowego w celu wydrukowania w raporcie **Kasa**. Aby sprawdzić zapisy w arkuszu, w okienku akcji kliknij przycisk **Weryfikuj**.

## <a name="cash-transaction-approval-and-posting"></a>Zatwierdzanie i księgowanie transakcji kasowych
Do transakcji kasowych mogą być stosowane następujące stany: **Brak**, **Potwierdzone**, **Zatwierdzone** i **Odrzucone**. Parametr **Użyj stanu potwierdzenia** na skróconej karcie **Zatwierdzenie** dostępnej na karcie **Kasa** w oknie **Zarządzanie gotówką i bankami** &gt; **Ustawienia** &gt; **Parametry modułu Zarządzanie gotówką i bankami** pozwala włączyć dwa dodatkowe stany: **Potwierdzone** i **Odrzucone**. Potwierdzenie należy zastosować, gdy są wydawane dokumenty kasowe, a przychody i rozchody gotówkowe są realizowanie wspólne przez dwóch pracowników: księgowego i kasjera. Funkcja **Resetuj stan** zmienia bieżący stan transakcji. Stan **Zatwierdzone** staje się stanem **Potwierdzone**, a stan **Potwierdzone** zmienia się na **Brak**. Zapisy w arkuszu kasowym można edytować tylko wtedy, gdy stanem jest **Brak**. Transakcje kasowe można odrzucać tylko wtedy, gdy stanem transakcji jest **Potwierdzone**. Odrzucone dokumenty kasowe znajdują się w raporcie **Arkusz rejestracji dokumentów kasowych**, ale nie są uwzględniane w raporcie **Księga kasowa**. Aby potwierdzić transakcję, wybierz odpowiedni wiersz arkusza kasowego, a następnie kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Potwierdź**. Zostanie wygenerowany numer zamówienia na podstawie ustawionej numeracji. Stan transakcji zmieni się na **Potwierdzone** i nie będzie można już edytować wiersza arkusza. Salda konta kasowego pozostaje bez zmian. Aby odrzucić dokument kasowy, kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Odrzuć**. Ta opcja jest dostępna tylko dla dokumentów o stanie **Potwierdzone**. Aby zatwierdzić transakcję, wybierz odpowiedni wiersz arkusza kasowego, a następnie kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Zatwierdź**. Stan **Zatwierdzone** wskazuje, że środki pieniężne zostały otrzymane lub wydatkowane. Saldo kasowe się zmienia. Transakcję kasową można zaksięgować. Aby anulować stan **Zatwierdzone** i zresetować stan do wartości **Brak**, kliknij kolejno opcje **Zatwierdzenie dokumentów** &gt; **Resetuj stan**. Można zaksięgować tylko zatwierdzone transakcje kasowe. Aby zaksięgować arkusz, kliknij kolejno opcje **Księguj** &gt; **Księguj**.

## <a name="print-a-cash-order"></a>Drukowanie zamówienia gotówkowego
Aby wydrukować zamówienie gotówkowe, zaznacz wiersz arkusza kasowego, a następnie w okienku akcji kliknij kolejno opcje **Drukuj** &gt; **Raport zamówień gotówkowych**. System wygeneruje drukowalną postać dokumentu KP lub KW, w zależności od tego, czy dla wybranego wiersza wprowadzono kwotę w polu **Debet**, czy **Kredyt**:

-   Jeśli istnieje kwota w pola **Debet**: dokument KP
-   Jeśli istnieje kwota w pola **Kredyt**: dokument KW

Wiersze arkusza kasowego, które mają stan **Potwierdzone**, **Zatwierdzone** lub **Odrzucone**, mogą być drukowane. Dokumenty zamówień gotówkowych można również drukować z okna **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Zamówienie gotówkowe**.

## <a name="periodic-tasks"></a>Zadania okresowe
W oknie **Zarządzanie gotówką i bankami** &gt; **Zadania okresowe** można wykonywać następujące zadania:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zadanie okresowe</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Sprawdź limit salda</td>
<td>Sprawdzanie salda wybranego konta kasowego na określony dzień oraz pokazywanie wyniku w komunikacie informacyjnym. W obliczaniu salda mogą być uwzględniane tylko zatwierdzone transakcje. Transakcje oznaczone jako <strong>Dla listy płac</strong> nie są brane pod uwagę.</td>
</tr>
<tr class="even">
<td>Ponowne obliczanie salda kasowego</td>
<td>To zadanie pozwala upewnić się, że salda księgi dla kont kasowych pasują do salda kasowego.</td>
</tr>
<tr class="odd">
<td>Tworzenie raportu kasowego (tylko Polska)</td>
<td>Tworzenie raportu <strong>Kasa</strong>. Numer raportu <strong>Kasa</strong> jest generowany na podstawie numeracji ustawionej w obszarze <strong>Numer raportu</strong>. W oknie dialogowym zadania w polu <strong>Do dnia</strong> określ ostatni dzień, z którego transakcje kasowe powinny być uwzględniane w raporcie <strong>Kasa</strong>. Za pomocą funkcji <strong>Filtr</strong> dostępnej na karcie <strong>Rekordy do uwzględnienia</strong> określ dodatkowe kryteria ograniczające wybór transakcji kasowych. Kryteria te mogą obejmować numery kont kasowych i kody walut. W polu <strong>Autor</strong> wybierz użytkownika odpowiedzialnego za tworzenie raportów. Aby wyświetlić utworzony raport <strong>Kasa</strong>, użyj przycisku <strong>Raporty kasowe</strong> znajdującego się na stronie <strong>Konta kasowe</strong>.</td>
</tr>
<tr class="even">
<td>Kasa — korekta kursu wymiany (FIFO i LIFO) (tylko Polska)</td>
<td>Obliczanie różnic kursowych według polskich norm. Za pomocą funkcji <strong>Filtr</strong> dostępnej na karcie <strong>Rekordy do uwzględnienia</strong> określ konto kasowe, dla którego ma zostać wykonane zadanie. Zaznacz pole wyboru <strong>Ponowne obliczanie</strong>, aby wykonać pełne ponowne obliczanie różnic kursowych dla wszystkich otwartych okresów. Oto sposób obliczania różnic kursowych w przypadku używania metody FIFO (pierwsze na wejściu, pierwsze na wyjściu) i LIFO (ostatnie na wejściu, pierwsze na wyjściu):
<ul>
<li><strong>Metoda FIFO</strong> — System szuka transakcji wydatków mającej wcześniejszą datę transakcji (niższy numer zamówienia) i rozlicza ją względem transakcja przychodu mającej wcześniejszą datę transakcji (niższy numer zamówienia).</li>
<li><strong>Metoda LIFO</strong> — System szuka transakcji wydatków mającej późniejszą datę transakcji (wyższy numer zamówienia) i rozlicza ją względem transakcja przychodu mającej późniejszą datę transakcji (wyższy numer zamówienia).</li>
</ul>
Rozliczona kwota znajduje odzwierciedlenie w polu <strong>Rozliczona waluta</strong> na stronie <strong>Transakcja kasowa</strong>. W przypadku istnienia różnicy kursowej kwota jest odzwierciedlana w polu <strong>Kwota korekty kursu wymiany</strong>, a transakcja o typie dokumentu <strong>Różnice kursowe</strong> jest generowana w tabeli <strong>Transakcja kasowa</strong>. Konta księgowe transakcji wynikowych ustawia się w tabeli <strong>Waluta</strong> (w polach <strong>Zysk finansowy z tytułu dodatnich różnic kursowych</strong> i <strong>Strata finansowa z tytułu ujemnych różnic kursowych</strong>).</td>
</tr>
<tr class="odd">
<td>Przeszacowanie w walucie obcej — kasa</td>
<td>Za pomocą tego zadania można uzyskać odpowiednie saldo w walucie domyślnej na dzień sprawozdawczy, jeśli operacje są wprowadzane w walutach obcych. Za pomocą funkcji <strong>Filtr</strong> dostępnej na karcie <strong>Rekordy do uwzględnienia</strong> określ konto kasowe, dla którego ma zostać wykonane zadanie. W oknie dialogowym zadania użyj pól <strong>Z waluty</strong> i <strong>Na walutę</strong>, aby określić waluty transakcji. System porównuje kwotę w walucie, która została przeliczona przy użyciu kursu wymiany na określony dzień, z kwotą w walucie domyślnej. Różnica między tymi dwoma kwotami (z wyłączeniem poprzedniej różnicy kursowej) jest obliczoną różnicą kursową. To zadanie powoduje utworzenie zatwierdzonej transakcji kasowej o typie <strong>Różnica kursowa</strong>. Transakcja finansowa powstaje poprzez użycie konta księgowego dla gotówki oraz konta księgowego określonego w polu <strong>Niezrealizowana dodatnia różnica kursowa</strong> lub <strong>Niezrealizowana ujemna różnica kursowa</strong> w tabeli <strong>Waluta</strong>.</td>
</tr>
</tbody>
</table>

## <a name="inquiries-and-reports"></a>Zapytania i raporty

| Zapytanie lub raport                             | opis                                                                                                                                                                                                                     |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Widok transakcji kasowych                        | Dla wiersza arkusza kasowego przycisk **Zapytania** w okienku akcji pozwala wyświetlić transakcje kasowe, saldo kasowe i inne informacje.                                                                                  |
| Transakcja kasowa                              | Aby wyświetlić transakcje kasowe, wybierz kolejno opcje **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Transakcje kasowe**. Za pomocą funkcji **Filtr** określ dodatkowe kryteria ograniczające wybór transakcji kasowych. |
| Arkusz rejestracji (Estonia, Rosja) | Raport w oknie **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Arkusz rejestracji** pokazuje wszystkie wystawione dokumenty KP i KW.                                   |
| Księga kasowa (Łotwa, Litwa, Rosja)     | Raport w oknie **Zarządzanie gotówką i bankami** &gt; **Zapytania i raporty** &gt; **Raport księgi kasowej** pokazuje rzeczywiste przesunięcia środków pieniężnych (wpływy i wydatki).                                                            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]