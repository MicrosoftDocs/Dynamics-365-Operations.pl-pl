---
title: Kasa dla Europy Wschodniej
description: "Ten temat zawiera informacje dotyczące funkcji kasy, która pozwala użytkownikom w Estonii, Litwy, Republika Czeska, Węgry, Łotwa, Polska i Rosja uwzględnienia operacji gotówkowych w systemie."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RCashBalance, RCashCountStatementForm, RCashPosting, RCashRemainLimit, RCashReportJour_PL, RCashTable, RCashTableBalance, RCashTableCredLimit, RCashTableLastRevaluation, RCashTableTransactions, RCashTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268504
ms.assetid: ff2ea7b0-8de2-48c5-8f9f-5d95d9924925
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: e843abff91f74ff8c2c577f499fa829821fc56ee
ms.lasthandoff: 03/31/2017


---

# <a name="petty-cash-for-eastern-europe"></a>Kasa dla Europy Wschodniej

Ten temat zawiera informacje dotyczące funkcji kasy, która pozwala użytkownikom w Estonii, Litwy, Republika Czeska, Węgry, Łotwa, Polska i Rosja uwzględnienia operacji gotówkowych w systemie.

Funkcja kasy automatyzacji operacji dla przychodów i rozchodów gotówkowych, utworzenie podstawowego dokumentów i drukowanie raportów związanych z. Funkcjonalność kasy umożliwia wykonywanie następujących operacji:

-   Konto przychodu i wydatków aktywów dostępnej gotówki.
-   Generowanie formularzy typowych środków pieniężnych: gotówka KP, dokumenty kW i arkusza rejestracji dokumentów.
-   Kontrolować kwota maksymalna środków pieniężnych, który jest dozwolony dla operacji z nabywcami, dostawcami i tak dalej.
-   Uwzględnienia operacji gotówkowych w różnych walut w systemie.
-   Konwertuj kwoty operacji gotówkowych w walucie obcej na walutę standardową, aby zapewnić zgłoszenie rachunkowości.
-   Generowanie **Księga kasowa** sprawozdanie oraz Raport kasjera.

## <a name="prerequisites"></a>Wymagania wstępne
Przed użyciem funkcji kasy, należy wykonać następujące wymagania wstępne:

-   Ustawianie kont kasowych.
-   Konfigurowanie profili księgowania kasowego.
-   Ustawienie sekwencji numerów dla numerowania środków pieniężnych dokumentu.
-   Ustawianie wartości domyślnych dla środków pieniężnych i bankowych parametry zarządzania.
-   Ustawianie nazw arkuszy środków pieniężnych w ogóle księgi.

### <a name="set-up-cash-accounts"></a>Ustawianie kont kasowych

Aby skonfigurować gotówki, otwórz **Zarządzanie gotówką i bankami**&gt;**kont bankowych**&gt;**środków pieniężnych konta**i wprowadź następujące informacje.

| Pole                 | opis                                                                                                          |
|-----------------------|----------------------------------------------------------------------------------------------------------------------|
| Kasa                  | Wprowadź kod identyfikujący konto kasowe (Gotówka).                                                                    |
| Nazwisko                  | Wprowadź opis konta kasowego.                                                                             |
| Waluta              | Wybierz domyślny kod waluty dla transakcji kasowych.                                                              |
| Grupa sekwencji numerów | Jeśli numeracja dokumentów kasowych musi się różnić od numeracji, który jest określony w parametrach, należy wprowadzić kod. |
| Wiele walut       | Zaznacz to pole wyboru, aby umożliwić walut, które różnią się od walutą rozliczeniową do zaksięgowania.                     |
| Ujemne saldo kasowe         | Zaznacz to pole wyboru, aby umożliwić salda ujemne saldo kasowe w dowolnej walucie.                                               |

Aby skonfigurować saldo gotówkowe kontroli zasady dla konta kasowego, wybierz konto kasowe, a następnie w okienku akcji na **konto kasowe** kartę w **limitu salda** grupy, kliknij przycisk **limitu salda**. Wpisz następujące informacje.

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
<td>Wybierz żądany rodzaj waluty:
<ul>
<li><strong>Waluta księgowania</strong> — Użyj kodu waluty firmy podstawowe.</li>
<li><strong>Wskazano waluty</strong> — Użyj kod waluty, która różni się od kodu waluty podstawowej firmy.</li>
</ul></td>
</tr>
<tr class="even">
<td>Waluta</td>
<td>W przypadku wybrania <strong>wskazano waluty</strong> w <strong>typu Waluta</strong> wybierz kod waluty. To pole nie jest dostępne, jeśli wybrano <strong>waluty rozliczeniowej</strong> w <strong>typu Waluta</strong> pole.</td>
</tr>
<tr class="odd">
<td>Typ ograniczenia salda</td>
<td>Wybierz jedną z dostępnych wartości:
<ul>
<li><strong>Maksymalne</strong> — saldo gotówkowe nie powinien przekraczać <strong>limitu salda</strong> kwoty dla konta kasowego (górna granica).</li>
<li><strong>Minimalna</strong> — saldo gotówkowe powinno być zabronione zejść poniżej <strong>limitu salda</strong> kwoty dla konta kasowego (na dole powiązane).</li>
</ul></td>
</tr>
<tr class="even">
<td>Sprawdź limit salda</td>
<td>Wybierz zdarzenia występujące w procesie zatwierdzania dla dokumentów kasowych Jeśli <strong>limitu salda</strong> kwoty dla konta kasowego zostanie przekroczony:
<ul>
<li><strong>Zaakceptuj</strong> — może zostać przekroczony limit.</li>
<li><strong>Ostrzeżenie</strong> -limit może zostać przekroczony, ale użytkownik otrzyma komunikat ostrzegawczy. Dokument kasowy jest potwierdzone lub zatwierdzone.</li>
<li><strong>Błąd</strong> — nie można przekroczyć limitu. Użytkownik odbiera komunikat o błędzie, a dokument kasowy nie jest potwierdzona lub zatwierdzone.</li>
</ul>
Aby uzyskać więcej informacji na temat procesu zatwierdzania dla dokumentów kasowych, zobacz &quot;pieniężnych zatwierdzenia transakcji i księgowania&quot; sekcji w dalszej części tego tematu.</td>
</tr>
<tr class="odd">
<td>Limit salda</td>
<td>Wprowadzenie limitu salda konta kasowego. Kwota powinna być w określonej walucie.</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-posting-profiles"></a>Konfigurowanie profili księgowania kasowego

Profili księgowania kasowego zdefiniować księgowań w księdze głównej. Aby skonfigurować profil księgowania środków pieniężnych, przejdź do **środków pieniężnych****i zarządzanie bankowym**&gt;**instalacji**&gt;**środki pieniężne profile księgowania**i wybierz lub Utwórz profil księgowania. Wpisz następujące informacje.

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
<td>Określ, czy profil księgowania dotyczy konta kasowego określonych lub wszystkich kont gotówkowych:
<ul>
<li><strong>Tabela</strong> — w przypadku linii profilu księgowania dla konta kasowego tego wiersza jest używany do księgowania transakcji środków pieniężnych.</li>
<li><strong>Wszystkie</strong> — istnieje żaden wiersz profilu księgowania dla konta kasowego.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kasa</td>
<td>W przypadku wybrania <strong>tabeli</strong> w <strong>ważny dla</strong> Określ konta kasowego. Pole to pozostanie puste, jeśli wybrano <strong>wszystkie</strong> w <strong>ważny dla</strong> pole.</td>
</tr>
<tr class="odd">
<td>Konto księgowe</td>
<td>Wprowadź numer konta księgowego do użycia jako konto rozrachunkowe dla konta kasowego.</td>
</tr>
</tbody>
</table>

### <a name="set-up-number-sequences-for-cash-documents"></a>Ustawienie sekwencji numerów dla dokumentów kasowych

Do ustawiania sekwencji numerów dla dokumentów kasowych, przejdź do **Zarządzanie gotówką i bankami**&gt;**instalacji**&gt;**parametry zarządzania gotówką i bankami**. Na **sekwencja numerów** tab, określ kodów sekwencji numerów dla **środki pieniężne KP**, **gotówka dokumentów KW**, **załącznik korekty kasowej**, i **różnica kursowa** dokumentów i dla **numer raport kasowy**.

### <a name="set-up-default-values-for-cash-and-bank-management-parameters"></a>Ustawianie wartości domyślnych dla środków pieniężnych i bankowych parametry zarządzania

Ustawianie wartości domyślnych dla środków pieniężnych i bankowych parametry zarządzania dla funkcji kasy, przejdź do **Zarządzanie gotówką i bankami**&gt;**instalacji**&gt;**parametry zarządzania gotówką i bankami**. Na **środków pieniężnych** wprowadź następujące informacje.

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
<td>Wybierz domyślne konto kasowe w arkuszach.</td>
</tr>
<tr class="even">
<td>Księgowanie kasy</td>
<td>Wprowadź Domyślna gotówka, który jest używany, jeśli nie profil księgowania jest określony profil księgowania.</td>
</tr>
<tr class="odd">
<td>Sprawdzanie użytego numeru załącznika</td>
<td>Wybierz, jakie występuje, jeśli zduplikowane numery zostaną znalezione podczas sprawdzania numer dokumentu kasowego:
<ul>
<li>Odrzuć duplikaty</li>
<li>Odrzuć duplikaty w ciągu roku obrachunkowego</li>
<li>Dozwolone duplikaty</li>
<li>Ostrzegaj w przypadku duplikatów</li>
</ul></td>
</tr>
<tr class="even">
<td>Sprawdź limit operacji</td>
<td>Określ, jaki występuje po przekroczeniu limitu dla operacji z kontrahentów:
<ul>
<li><strong>Zaakceptuj</strong> — może zostać przekroczony limit.</li>
<li><strong>Ostrzeżenie</strong> -limit może zostać przekroczony, ale użytkownik otrzyma komunikat ostrzegawczy. Operacja jest księgowana.</li>
<li><strong>Błąd</strong> — nie można przekroczyć limitu. Użytkownik odbiera komunikat o błędzie, a operacja nie jest zaksięgowany.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Metoda weryfikacji</td>
<td>Wybierz metodę sprawdzania poprawności, który jest używany do sterowania Przekroczono limit kwoty dla operacji:
<ul>
<li><strong>Operacja</strong> — jest sprawdzana na transakcję</li>
<li><strong>Porozumienie</strong> — sprawdzanie poprawności jest wykonywane według transakcji, która ma określonej umowy dotyczących kontrahenta.</li>
</ul></td>
</tr>
<tr class="even">
<td>Limit operacji</td>
<td>Wprowadź maksymalną kwotę, jaką jest dozwolone dla operacji z kontrahentów w gotówce.</td>
</tr>
<tr class="odd">
<td>Księgowanie z wcześniejszą datą</td>
<td>Zaznacz to pole wyboru, aby włączyć transakcje gotówkowe mają być księgowane przed datą ostatniej transakcji pieniężnych.</td>
</tr>
<tr class="even">
<td>Wymiary</td>
<td>Wprowadzanie wymiarów w <strong>kod wydziału</strong>, <strong>analityczne kod</strong>, i <strong>cel kod</strong> pól. Drukowanie formularza dla dokumentów kasowych będzie odzwierciedlał te informacje.</td>
</tr>
<tr class="odd">
<td>Użyj stanu potwierdzenia</td>
<td>Zaznacz to pole wyboru, aby użyć dodatkowy stan, <strong>potwierdzone</strong>, podczas procesu zatwierdzania dla dokumentów kasowych. (Aby uzyskać więcej informacji, zobacz &quot;pieniężnych zatwierdzenia transakcji i księgowania&quot; sekcji.)</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-journal-names-in-general-ledger"></a>Ustawianie nazw arkuszy środków pieniężnych w ogóle księgi

Aby utworzyć arkusz do księgowania transakcji pieniężnych, przejdź do **księgi głównej**&gt;**ustawienia dziennika**&gt;**nazwy arkuszy**i utworzyć nowy rekord. W **typu arkusza** określ **środków pieniężnych**. Inne domyślne parametry należy zdefiniować, ile jest potrzebnych.

## <a name="daily-cash-operations-via-a-slip-journal"></a>Codzienne operacje pieniężne za pośrednictwem arkusza dokumentu dostawy
Aby utworzyć dokument kasowy za pośrednictwem arkusza dokumentu dostawy, przejdź do **Zarządzanie gotówką i bankami**&gt;**środków pieniężnych transakcji**&gt;**arkusz kasowy**i utworzyć nowy arkusz. W okienku akcji kliknij polecenie **linii**. Dodać nowy wiersz i wprowadź następujące informacje.

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
<td>Wybierz konto kasowe. Domyślnie konto środków pieniężnych jest określony w parametrach Zarządzanie gotówką i bankami.</td>
</tr>
<tr class="odd">
<td>opis</td>
<td>Wprowadź tekst objaśnienia dla transakcji.</td>
</tr>
<tr class="even">
<td>Debet Kredyt</td>
<td>Wprowadź kwotę środków pieniężnych z dokumentu w jednym z tych pól:
<ul>
<li><strong>Debet</strong> — to pole służy do rejestracji blankietów kasowych i KP.</li>
<li><strong>Kredytu</strong> — to pole służy do rejestracji wydatków pieniężnych i dokumentu KW.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Typ konta przeciwstawnego konta przeciwstawne</td>
<td>Należy wybrać numer konta typu i przesunięcie konta przeciwstawnego.</td>
</tr>
<tr class="even">
<td>Waluta</td>
<td>Wybierz kod waluty transakcji.</td>
</tr>
<tr class="odd">
<td>Załącznik</td>
<td>To pole jest wypełniane automatycznie, na podstawie ustawień dziennika.</td>
</tr>
<tr class="even">
<td>Numer zamówienia</td>
<td>Jeśli inne sekwencja numerów jest ustawione dla konta kasowego, to pole jest wypełniane automatycznie, na podstawie sekwencji numerów, która jest określona w parametrach. Można ręcznie wprowadzić numer zamówienia w tej dziedzinie, ile jest potrzebnych. Aby zapobiec niespójność w numeracji dokumentów środków pieniężnych, stosuje się następujący formant: numer dokumentu środków pieniężnych, który ma datę wcześniejszą operacji nie może być wyższa niż numer dokumentu kasowego, który ma później operacji. Jeśli nie wymagają tego formantu, zaznacz <strong>Księgowanie z wcześniejszą datą</strong> pole wyboru w parametrach Zarządzanie gotówką i bankami.</td>
</tr>
<tr class="odd">
<td>Stan zatwierdzenia</td>
<td>Pierwszy stan transakcji jest <strong>Brak</strong>. Szczegółowe informacje o tym, jak ustawić stan transakcji &quot;pieniężnych zatwierdzenia transakcji i księgowania&quot; sekcji.</td>
</tr>
<tr class="even">
<td>Typ dokumentu </td>
<td>To pole na <strong>gotówkowa</strong> karta jest wypełniane automatycznie, na podstawie ilości wprowadzonej dla dokument kasowy:
<ul>
<li><strong>Gotówka KP</strong> -ta wartość jest używana, jeśli wprowadzono wartość w <strong>Debet</strong> pola dla konta kasowego.</li>
<li><strong>Gotówka dokumentu KW</strong> -ta wartość jest używana, jeśli wprowadzono wartość w <strong>kredytu</strong> dla konta kasowego pole</li>
<li><strong>Korekta</strong> — wprowadzona kwota ujemna w <strong>Debet</strong> pole lub <strong>kredytu</strong> pola dla konta kasowego.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Grupa podatków</td>
<td>Określ grupę podatku przy obliczaniu podatków na operację.</td>
</tr>
<tr class="even">
<td>Grupa podatków dla pozycji</td>
<td>Określ grupę podatków towaru do obliczania podatków od operacji.</td>
</tr>
<tr class="odd">
<td>Przyczyna</td>
<td>Na <strong>gotówkowa</strong> wprowadź tekst opisujący przedmiot transakcji. Ten tekst będzie drukowany na formularz sprawozdawczy dokumentu kasowego.</td>
</tr>
<tr class="even">
<td>Data dokumentu</td>
<td>Wprowadź opis, numer i Data dokumentu głównego, to jest powód, dla transakcji (na przykład raporty zaliczek, faktury lub zamówienia).</td>
</tr>
<tr class="odd">
<td>Typ przedstawiciela</td>
<td>To pole może mieć następujące wartości:
<ul>
<li><strong>Pracownik</strong> — <strong>reprezentatywnych</strong> odnośnika zawiera listę pracowników, jeśli <strong>konto przeciwstawne</strong> pole jest ustawione na <strong>księgi</strong> lub <strong>Bank</strong>, lub na liście kontrahenta, osób kontaktowych, jeśli <strong>konto przeciwstawne</strong> pole jest ustawione na <strong>klienta</strong> lub <strong>dostawcy</strong>. Aby skonfigurować przedstawicieli, przejdź do <strong>podstawowych</strong>&gt;<strong>instalacji</strong>&gt;<strong>kontakty</strong>&gt;<strong>osoba kontaktowa</strong>.</li>
<li><strong>Inne</strong> — <strong>przedstawiciel</strong> odnośnika zawiera listę innych klientów. Aby skonfigurować odbiorcy, którzy nie pojawiają się w <strong>klienci</strong> lub <strong>dostawców</strong> tabeli, przejdź do <strong>księgi głównej</strong>&gt;<strong>odbiorników</strong>. Ten typ jest dostępny tylko dla Łotwy. ( <strong>CSELatvia</strong> powinien być włączony klucz konfiguracji.)</li>
<li><strong>Dostawca</strong> — <strong>przedstawiciel</strong> odnośnika zawiera listę dostawców. Aby zdefiniować dostawców, przejdź do <strong>rozrachunków z dostawcami</strong>&gt;<strong>dostawców</strong>.</li>
<li><strong>Odbiorcy</strong> — <strong>przedstawiciel</strong> odnośnika zawiera listę klientów. Aby zdefiniować nabywców, przejdź do <strong>rozrachunków z odbiorcami</strong>&gt;<strong>klienci</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Przedstawiciel</td>
<td>Wybrać przedstawiciela typu określonego w <strong>typ przedstawiciela</strong> pole.</td>
</tr>
<tr class="odd">
<td>Nazwisko pracownika</td>
<td>To pole jest wypełniane automatycznie, na podstawie <strong>konto przeciwstawne</strong> i <strong>przedstawiciel</strong> pól. Do drukowania formularza dokumenty kasowe będzie odzwierciedlał te informacje.</td>
</tr>
<tr class="even">
<td>Dowód tożsamości</td>
<td>To pole jest wypełniane automatycznie, na podstawie dowodu tożsamości danych osoby kontaktowej (przedstawiciel). Jeśli <strong>typ konta przeciwstawnego</strong> pole jest ustawione na <strong>posiadacza zaliczki</strong>i <strong>konto przeciwstawne</strong> pole jest ustawione na numer pracownika, wpłat gotówkowych lub wydatków może odbywać się z lub do pracownika. W takim przypadku <strong>dowodu tożsamości</strong> pole jest wypełniane automatycznie przy użyciu danych dowodu tożsamości z <strong>pracownika</strong> tabeli (<strong>Księgowanie personelu</strong>&gt;<strong>tabeli pracowników</strong>).</td>
</tr>
<tr class="odd">
<td>Cel</td>
<td>W <strong>celu</strong> table, zdefiniować jeden lub więcej kodów przeznaczenia kwoty transakcji. Należy wybrać kod przeznaczenia w <strong>celu</strong> i wpisz wyjaśnienie w <strong>tekst transakcji</strong> pole. W <strong>kwoty</strong> wprowadź kwotę w walucie transakcji. <strong>%</strong> Pól pokazuje, w procentach, stosunek wielkości docelowej do łącznej kwoty transakcji.</td>
</tr>
<tr class="even">
<td>Upomnienie</td>
<td>Kwota pozostała jest obliczana. Należy zauważyć, że kwota cała transakcja musi być przypisany do kody miejsca przeznaczenia.</td>
</tr>
<tr class="odd">
<td>Dane urzędowe</td>
<td>Na <strong>urzędników</strong> tab, określanie nazw i tytułów dla osób odpowiedzialnych: dyrektora, głównego księgowego i kasjera. <strong>Pozycji</strong> wartości są określane przez ustawienia urzędników na <strong>ogólne</strong> i <strong>księgi</strong> karty <strong>urzędników</strong> stronę (<strong>podstawowych</strong>&gt;<strong>instalacji</strong>&gt;<strong>kontakty</strong>&gt;<strong>urzędników</strong>).</td>
</tr>
<tr class="even">
<td>Zaliczka</td>
<td>Zaznacz to pole wyboru, jeśli transakcja jest przedpłatą.</td>
</tr>
<tr class="odd">
<td>Profil księgowania</td>
<td>Wprowadź profil księgowania dla konta kasowego. Domyślnie używany jest profil księgowania, który jest określony w parametrach Zarządzanie gotówką i bankami.</td>
</tr>
<tr class="even">
<td>Profil księgowania przeciwstawnego</td>
<td>Wprowadź profil księgowania dla wybranego konta przeciwstawnego.</td>
</tr>
<tr class="odd">
<td>Suma</td>
<td>W <strong>suma</strong> grupy pól u dołu strony, <strong>Reimb</strong> pole zawiera sumę, która jest obliczana dla wszystkich środków pieniężnych, zwrot dokumentów, które są wprowadzane w bieżącym arkuszu i <strong>Disb</strong> pole zawiera sumę wszystkich dokumentów KW.</td>
</tr>
</tbody>
</table>

Aby sprawdzić zapisy księgowe, w okienku akcji kliknij przycisk **sprawdzania poprawności**.

## <a name="daily-cash-operations-via-a-general-journal"></a>Codzienne operacje pieniężne za pomocą dziennika głównego
Aby utworzyć transakcji kasowej za pomocą dziennika głównego, przejdź do **księgi głównej**&gt;**pozycji dziennika**&gt;**arkusze finansowe**i utworzyć nowy arkusz. W okienku akcji kliknij polecenie **linii**. Dodać nowy wiersz i wprowadź następujące informacje.

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
<td>Wybierz <strong>kasy</strong>.</td>
</tr>
<tr class="odd">
<td>Konto</td>
<td>Wybierz numer konta kasowego.</td>
</tr>
<tr class="even">
<td>Tekst transakcji</td>
<td>Wprowadź tekst objaśnienia dla transakcji.</td>
</tr>
<tr class="odd">
<td>Debet Kredyt</td>
<td>Wprowadź kwotę środków pieniężnych z dokumentu w jednym z tych pól:
<ul>
<li><strong>Debet</strong> — to pole służy do rejestracji blankietów kasowych i KP.</li>
<li><strong>Kredytu</strong> — to pole służy do rejestracji wydatków pieniężnych i dokumentu KW.</li>
</ul></td>
</tr>
<tr class="even">
<td>Typ konta przeciwstawnego konta przeciwstawne</td>
<td>Należy wybrać numer konta typu i przesunięcie konta przeciwstawnego.</td>
</tr>
<tr class="odd">
<td>Waluta</td>
<td>Wybierz kod waluty transakcji.</td>
</tr>
</tbody>
</table>

Na **faktury** kartę, można określić profilów księgowania dla wybranego konta oraz konto przeciwstawne. W przypadku zarejestrowanych transakcji przedpłaty zaznacz **przedpłaty** pole wyboru na **płatności** kartę. W **przedstawiciel** grupie pól, wypełnij pola, tak jak dla wierszy arkusza dokumentu dostawy do wydrukowania na **środków pieniężnych** raportu. Aby sprawdzić zapisy księgowe, w okienku akcji kliknij przycisk **sprawdzania poprawności**.

## <a name="cash-transaction-approval-and-posting"></a>Zatwierdzenia transakcji pieniężnych i księgowania
Dla transakcji pieniężnych, mogą być stosowane następujące stany: **Brak**, **potwierdzone**, **zatwierdzone**, i **odrzucone**. A **Użyj stanu potwierdzenia** parametru na **zatwierdzenia** skróconej **środków pieniężnych** tab na **Zarządzanie gotówką i bankami**&gt;**instalacji**&gt;**parametry zarządzania gotówką i bankami** umożliwia aktywację dwa dodatkowe stany: **potwierdzone** i **odrzucone**. Właściwe jest potwierdzenie, gdy są wydawane dokumentów kasowych i wpłat gotówkowych lub wydatków, które są wspólne dla dwóch pracowników: księgowego i kasjera. **Resetowanie stanu** funkcja zmienia bieżący stan transakcji. **Zatwierdzone** staje się **potwierdzone**, i **potwierdzone** staje się **Brak**. Zapisy księgowe środków pieniężnych można edytować tylko wtedy, gdy stan jest **Brak**. Transakcje kasowe, mogą zostać odrzucone tylko wtedy, gdy dla transakcji wskazywany jest **potwierdzone**. Odrzucone pieniężnych dokumenty znajdują się na **arkusza rejestracji dokumentów kasowych** raportu, ale nie są odzwierciedlane **Księga kasowa** raportu. Aby zatwierdzić transakcję, wybierz odpowiedni wiersz arkusza dokumentu dostawy, a następnie kliknij przycisk **dokumenty zatwierdzenia**&gt;**Potwierdź**. Numer zamówienia jest generowany na podstawie określonej sekwencji numerów. Stan transakcji jest zmieniany na **potwierdzone**, i nie będzie można edytować wiersz dziennika. Salda konta kasowego pozostaje bez zmian. Aby odrzucić dokument kasowy, kliknij przycisk **dokumenty zatwierdzenia**&gt;**Odrzuć**. Ta opcja jest dostępna tylko dla dokumentów, które mają **potwierdzone** stanu. Do zatwierdzania transakcji, wybierz odpowiedni wiersz arkusza dokumentu dostawy, a następnie kliknij przycisk **dokumenty zatwierdzenia**&gt;**Zatwierdź**. **Zatwierdzone** stan wskazuje, że środki pieniężne otrzymane lub wydatkowane. Saldo gotówkowe zostanie zmieniona. Transakcja kasowa mogą być księgowane. Aby anulować **zatwierdzone** stanu i zresetować do stanu **Brak**, kliknij przycisk **dokumenty zatwierdzenia**&gt;**Resetowanie stanu**. Tylko zatwierdzonych środków pieniężnych, które mogą być księgowane transakcje. Aby zaksięgować dziennik, kliknij przycisk **Post**&gt;**Post**.

## <a name="print-a-cash-order"></a>Drukuj zamówienie gotówkowe
Aby wydrukować zamówienie gotówkowe, zaznacz wiersz arkusza dokumentu dostawy, a następnie w okienku akcji kliknij **drukować**&gt;**raportu zamówienia gotówkowego**. System generuje drukowania formularza dla KP lub kW, w zależności od tego, czy wprowadzona zostanie kwota w **Debet** pole lub **kredytu** dla wybranego wiersza pole:

-   Jeśli istnieje kwota w **Debet** pola: gotówka KP
-   Jeśli istnieje kwota w **kredytu** pola: gotówka dokumentu KW

Zdjąć wierszy dziennika, które mają **potwierdzone**, **zatwierdzone**, lub **odrzucone** stanu mogą być drukowane. Można również wydrukować dokumenty zamówienia gotówkowego o **Zarządzanie gotówką i bankami**&gt;**otrzymywać i raporty**&gt;**gotówkowa**.

## <a name="periodic-tasks"></a>Zadania okresowe
Następujące zadania mogą być wykonywane w **Zarządzanie gotówką i bankami**&gt;**zadania okresowe**.

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
<td>Sprawdź saldo konta kasowego wybranego na określony dzień i pokazać wynik w komunikat informacyjny. Tylko zatwierdzone transakcje mogą być liczone obliczanie salda. Transakcje, które są oznaczone jako <strong>dla listy płac</strong> nie są uznawane za.</td>
</tr>
<tr class="even">
<td>Ponowne obliczanie salda kasowego</td>
<td>To zadanie służy do upewnij się, że mieszczą się saldo gotówkowe sald finansowych dotyczących kont kasowych.</td>
</tr>
<tr class="odd">
<td>Utwórz raport kasowy (tylko w Polsce)</td>
<td>Tworzenie <strong>środków pieniężnych</strong> raportu. <strong>Środków pieniężnych</strong> numer raport jest generowany na podstawie sekwencji numerów, która jest ustawiona dla <strong>numer sprawozdania z</strong>. W oknie dialogowym pole zadania, w <strong>do tej pory</strong>, wybranie ostatniej daty, dla których kasy transakcje powinny być liczone dla <strong>środków pieniężnych</strong> raportu. Użyj <strong>filtr</strong> działać na <strong>rekordy dołączane</strong> kartę, aby określić dodatkowe kryteria, aby ograniczyć wybór transakcji kasowych. Kryteria te mogą obejmować numery kont gotówkowych i kodów walut. W <strong>przez tworzenie</strong> wybierz użytkownika, który jest odpowiedzialny za tworzenie raportów. Aby wyświetlić <strong>środków pieniężnych</strong> raport, który został utworzony, użyj <strong>gotówka raporty</strong> znajdującego się na <strong>środków pieniężnych konta</strong> strony.</td>
</tr>
<tr class="even">
<td>Kasa — wymiany korekty FIFO i LIFO (tylko w Polsce)</td>
<td>Obliczyć różnice kursowe według norm polskich. Użyj <strong>filtr</strong> działać na <strong>rekordy dołączane</strong> kartę, aby określić do uruchomienia zadania dla konta kasowego. Wybierz <strong>ponownego obliczania</strong> pole wyboru, aby wykonać pełne ponowne obliczanie różnice korekty kursowe dla wszystkich otwartych okresów. Oto sposób obliczania różnice kursowe po pierwszym, najpierw FIFO i ostatnio w pierwszym LIFO metody są używane:
<ul>
<li><strong>Metoda FIFO</strong> – system wyszuka transakcję wydatków, który ma wcześniejszą datę transakcji (mniejszy numer zamówienia) i załatwiona transakcja przychodu, która ma wcześniejszą datę transakcji (mniejszy numer zamówienia).</li>
<li><strong>Metoda LIFO</strong> – system wyszuka transakcję wydatków, który ma nowszej daty transakcji (większy numer zamówienia) i załatwiona transakcja przychodu, która ma nowszej daty transakcji (większy numer zamówienia).</li>
</ul>
Rozliczona kwota znajduje odzwierciedlenie w <strong>rozliczona Waluta</strong> w <strong>środków pieniężnych transakcji</strong> strony. W przypadku korekty różnice kursowe, kwota jest odzwierciedlona w <strong>kwotę różnic kursowych</strong> pola i transakcji z <strong>różnicy kursowej</strong> typu dokumentu jest generowany w <strong>środków pieniężnych transakcji</strong> tabeli. Konta księgowe dla transakcji zysków/strat mieszczą się w <strong>waluty</strong> tabeli (<strong>Zysk finansowy kurs wymiany</strong> i <strong>Strata finansowa spowodowana kursami wymiany</strong>).</td>
</tr>
<tr class="odd">
<td>Przeszacowanie w walucie obcej — kasa</td>
<td>Za pomocą tego zadania odpowiedniej równowagi w walucie domyślnej na dzień bilansowy, kiedy działania są wprowadzane w walutach obcych. Użyj <strong>filtr</strong> działać na <strong>rekordy dołączane</strong> kartę, aby określić do uruchomienia zadania dla konta kasowego. W oknie dialogowym zadania, użyj <strong>z waluty</strong> i <strong>do waluty</strong> pola, aby określić waluty transakcji. System porównuje kwota w walucie, które było konwertowane przy użyciu kursu wymiany dla wybranej daty z kwotą w walucie domyślnej. Różnica między tymi dwiema kwotami (z wyjątkiem poprzedniego różnice kursowe) jest obliczoną różnice kursowe. To zadanie powoduje utworzenie transakcji zatwierdzonych środków pieniężnych, z <strong>różnica kursowa</strong> typu. Transakcja księgi powstaje przy użyciu konta księgowego dla środków pieniężnych i konta księgowego, które określono w <strong>niezrealizowany zysk</strong> lub <strong>Niezrealizowana ujemna różnica kursowa</strong> w <strong>waluty</strong> tabeli.</td>
</tr>
</tbody>
</table>

## <a name="inquiries-and-reports"></a>Zapytania i raporty
| Badanie lub raportu                             | opis                                                                                                                                                                                                                     |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Wyświetlanie transakcji kasowych                        | Dla wiersza arkusza dokumentu dostawy, użyj **zapytania** przycisku w okienku akcji do wyświetlania transakcji księgi, salda środków pieniężnych i inne informacje.                                                                                  |
| Transakcja kasowa                              | Przejdź do **Zarządzanie gotówką i bankami**&gt;**informacji i raportów**&gt;**środków pieniężnych transakcji** do wyświetlania transakcji kasowych. Użyj **filtr** funkcji, aby określić dodatkowe kryteria, aby ograniczyć wybór transakcji kasowych. |
| Arkusz rejestracji (dla Estonii, Rosja) | Raport o **Zarządzanie gotówką i bankami**&gt;**informacji i raportów**&gt;**Arkusz rejestracji** odzwierciedla wszystkie KP i dokumenty kW, które zostały wydane.                                   |
| Księga kasowa (dla Łotwy, Litwy, Rosji)     | Raport o **Zarządzanie gotówką i bankami**&gt;**informacji i raportów**&gt;**raport Księga** odzwierciedla rzeczywistą gotówkę Funduszu ruchy (wpływy gotówkowe i wydatki).                                                            |




