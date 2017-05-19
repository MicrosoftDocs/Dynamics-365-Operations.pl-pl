---
title: "Raportowanie listy sprzedaży do UE"
description: "Ten artykuł zawiera informacje o raportowaniu listy sprzedaży do państw Unii Europejskiej (UE)."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12811
ms.assetid: 89ffb659-b4a1-450a-9485-d56dd72829bb
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 9308158482b2eda0bd27cee07697b4184fc62253
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="eu-sales-list-reporting"></a>Raportowanie listy sprzedaży do UE

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o raportowaniu listy sprzedaży do państw Unii Europejskiej (UE).

<a name="eu-sales-list-reporting"></a>Raportowanie listy sprzedaży do UE
-----------------------

Dostawca, który dostarcza towary lub usługi wewnątrz Wspólnoty firmom, które są zarejestrowane w Unii Europejskiej (UE), musi przesyłać deklarację sprzedaży do UE (Lista sprzedaży do UE lub ESL). Ogólnie dokument ESL musi zostać przesłany do urzędu skarbowego nie później niż ostatniego dnia miesiąca po zakończeniu okresu kalendarzowego, objętego przez ESL. Dostawca musi podać swój numer identyfikacyjny VAT na ESL i musi także podać, według odbiorcy, następujące informacje:

-   Numer identyfikacyjny VAT dla odbiorcy w UE
-   Łączna wartość wewnątrzwspólnotowych dostaw towarów i usług wykonywanych dla odbiorcy w UE w tym okresie. Dostawca musi także oddzielić ogólne dostawy towarów od dostaw w handlu trójstronnym. Handel trójstronny dotyczy bezpośrednich dostaw towarów od dostawcy dostawcy do odbiorcy, gdy obie strony są zarejestrowane w innych krajach UE.

Za pomocą ESL władze podatkowe każdego Państwa Członkowskiego UE mogą sprawdzić, czy został zapłacony podatek VAT dla każdej transakcji wewnątrzwspólnotowej. Połączenie list i zwrotów podatku VAT umożliwia państwom członkowskim UE wymianę informacji na temat przepływu towarów w całej Unii Europejskiej.

## <a name="overview-of-the-eu-sales-list-reporting-process"></a>Omówienie procedury raportowania ESL
Można wykonać następujące zadania dla raportowania ESL:

-   Zbieranie informacji dotyczących wewnątrzwspólnotowych transakcji handlowych. Wewnątrzwspólnotowa transakcja handlowa może być fakturą sprzedaży, fakturą niezależną, fakturą projektu lub faktura od dostawcy. Transakcja jest identyfikowana na podstawie kraju/regionu kontrahenta. Wewnątrzwspólnotowe transakcje handlowe różnego typu są gromadzone w tabeli Lista sprzedaży do UE, gdzie są przedstawiane we wspólnym formularzu. Każdy rekord w tabeli ESL odpowiada jednej transakcji i składa się z identyfikatora VAT kontrahenta i łącznej wartości towarów i usług, które zostały dostarczone.
-   (Opcjonalnie) Podgląd raportu **ESL**. Można wyświetlić podgląd i sprawdzić poprawność raportu **ESL** w danym okresie w postaci skoroszytu programu Microsoft Excel.
-   Generowanie raportu **ESL**. Raport **ESL** jest generowany w formie pliku elektronicznego w określonym formacie, który jest właściwy dla każdego państwa członkowskiego UE. Na ogół raport **ESL** zawiera podstawowe informacje dotyczące strony raportowania i wartości dostaw towarów i usług. Informacje są pogrupowane według kraju i identyfikatora VAT kontrahenta.
-   Zamykanie okresu raportowania ESL. Po wygenerowaniu raportu **ESL** i przesłaniu go do urzędu, można oznaczyć rekordy tabeli ESL jako **Zamknięte**. Te transakcje nie będą uwzględniane w dodatkowych raportach.

## <a name="prerequisites"></a>Wymagania wstępne
W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategoria</th>
<th>Wymaganie wstępne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Konfiguracja:</strong> Firma</td>
<td>Podstawowy adres firmy musi być w Unii Europejskiej. Na stronie <strong>Firmy</strong> (kliknij kolejno opcje <strong>Administrowanie organizacją</strong> &gt; <strong>Organizacje</strong> &gt; <strong>Firmy</strong>) wybierz swoją firmę. Na skróconej karcie <strong>Adresy</strong> utwórz adres, wybierz kraj/region i inne składniki adresu i oznacz adres jako <strong>Podstawowy</strong>. Na skróconej karcie <strong>Rejestracja podatkowa</strong> w polu <strong>Numer identyfikacji podatkowej</strong> określ numer NIP swojej firmy.</td>
</tr>
<tr class="even">
<td><strong>Konfiguracja:</strong> Parametry numeru identyfikacji podatkowej</td>
<td>Ustaw parametry identyfikacji podatkowej na stronie <strong>Parametry kraju/regionu</strong> (kliknij kolejno opcje <strong>Podatek</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Podatek</strong> &gt; <strong>Parametry kraju/regionu</strong>). Dla każdego kraju/regionu, w którym masz kontrahentów, utwórz rekord na stronie, a następnie określ następujące informacje:
<ul>
<li><strong>Kraj/region</strong> — wybierz kraj/region do powiązania z numerem identyfikacji podatkowej.</li>
<li><strong>Podatek</strong> — umożliwia wprowadzenie numeru identyfikacji podatkowej (czyli prefiksu numeru identyfikacji podatkowej) dla wybranego kraju/regionu.</li>
<li><strong>Sprawdź numer identyfikacji podatkowej</strong> — zaznaczenie tego pola wyboru pozwala sprawdzić poprawność numeru identyfikacji podatkowej dla wybranego kraju/regionu.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Konfiguracja:</strong> Numery identyfikacji podatkowej</td>
<td>Utwórz numery identyfikacji podatkowej na stronie <strong>Numery identyfikacji podatkowej</strong> (kliknij kolejno opcje <strong>Podatek</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Podatek</strong> &gt; <strong>Numery identyfikacji podatkowej</strong>). Dla każdego numeru identyfikacji podatkowej utwórz rekord na stronie, a następnie określ następujące informacje:
<ul>
<li><strong>Kraj/region </strong>— wybierz kraj/region identyfikacji podatkowej kontrahenta.</li>
<li><strong>Numer identyfikacji podatkowej</strong> — umożliwia wprowadzenie numeru identyfikacji podatkowej kontrahenta.</li>
<li><strong>Nazwa firmy</strong> – (Opcjonalnie) Wprowadź nazwę kontrahenta.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Konfiguracja:</strong> Rejestracja kontrahentów</td>
<td>Ustaw informacje o identyfikacji podatkowej na stronie <strong>Wszyscy odbiorcy</strong> (kliknij kolejno opcje <strong>Sprzedaż i marketing</strong> &gt; <strong>Odbiorcy</strong> &gt; <strong>Wszyscy odbiorcy</strong>, wybierz rekord odbiorcy, a następnie kliknij kolejno opcje <strong>Opcje</strong> &gt; <strong>Zmień widok</strong> &gt; <strong>Widok szczegółów</strong>) lub na stronie <strong>Dostawcy</strong> (kliknij kolejno opcje <strong>Zaopatrzenie i sourcing</strong> &gt; <strong>Dostawcy</strong> &gt; <strong>Dostawcy</strong>, wybierz rekord dostawcy, a następnie kliknij kolejno opcje <strong>Opcje</strong> &gt; <strong>Zmień widok</strong> &gt; <strong>Widok szczegółów</strong>). Na skróconej karcie <strong>Faktura i dostawa</strong> w polu <strong>Numer identyfikacji podatkowej</strong> wybierz numer identyfikacji podatkowej.</td>
</tr>
<tr class="odd">
<td><strong>Konfiguracja:</strong> Podatek</td>
<td>Ustaw kody podatków, które mają znaleźć się w raporcie <strong>Lista sprzedaży do UE</strong> na stronie <strong>Kody podatków</strong> (kliknij kolejno opcje <strong>Podatek</strong> &gt; <strong>Podatki pośrednie</strong> &gt; <strong>Podatek</strong> &gt; <strong>Kody podatków</strong>). Na skróconej karcie <strong>Konfiguracja raportu</strong> dla każdego kodu podatku, która powinna zostać uwzględniona w raporcie, wyczyść pole wyboru <strong>Wykluczone</strong>. Ustaw parametry podatku dla towarów na stronie <strong>Grupy podatków dla pozycji</strong> (kliknij kolejno opcje <strong>Podatek</strong> &gt; <strong>Podatki pośrednie</strong> &gt; <strong>Podatek</strong> &gt; <strong>Grupy podatków dla pozycji</strong>). Dla każdej grupy podatków towarów wybierz wartość w polu <strong>Typ raportowania</strong>. Wybrana wartość określa kwotę kolumny ESL, w której zostanie uwzględniona kwota wiersza.
<ul>
<li><strong>Puste</strong> — kwota wiersza jest uwzględniana w kolumnie <strong>Nieprzypisana wartość</strong>.</li>
<li><strong>Towar</strong> — kwota wiersza jest uwzględniana w kolumnie <strong>Wartość towarów</strong>.</li>
<li><strong>Usługa</strong> — kwota wiersza jest uwzględniana w kolumnie <strong>Wartość usług</strong>.</li>
<li><strong>Inwestycja</strong> — kwota wiersza jest uwzględniana w kolumnie <strong>Wartość inwestycji</strong>. Ta kolumna jest odpowiednia tylko dla Belgii.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Konfiguracja:</strong> konfiguracje raportowania ESL</td>
<td>Importowanie lub tworzenie konfiguracji raportowania elektronicznego dla ESL Aby uzyskać informacje dotyczące sposobu tworzenia i obsługi konfiguracji raportowania elektronicznego zobacz temat Dokumentacja raportowania elektronicznego.</td>
</tr>
<tr class="odd">
<td><strong>Konfiguracja: </strong>Parametry ogólne</td>
<td>Ustaw parametry raportowania ESL na stronie <strong>Parametry handlu zagranicznego</strong> (kliknij kolejno opcje <strong>Podatek</strong> &gt; <strong>Ustawienia</strong> &gt; <strong>Handel zagraniczny</strong> &gt; <strong>Parametry handlu zagranicznego</strong>). Określ następujące parametry:
<ul>
<li>Karta <strong>Lista sprzedaży do UE</strong>:
<ul>
<li><strong>Raport rabatu gotówkowego</strong> — zaznacz to pole wyboru, jeśli rabat gotówkowy ma być uwzględniany w wartości, gdy transakcja jest uwzględniana w ESL.</li>
<li><strong>Przenieś zakupy</strong> — zaznacz to pole wyboru, aby uwzględniać zakupy na ESL.</li>
<li><strong>Mapowanie formatu pliku</strong> – umożliwia wybranie formatu raportowania elektronicznego do użycia podczas generowania pliku dla ESL.</li>
<li><strong>Mapowanie formatu raportu</strong> – umożliwia wybranie formatu podglądu raportu do użycia podczas generowania pliku dla ESL.</li>
<li><strong>Reguła zaokrąglania</strong> — umożliwia określenie rzeczywistej liczny, która ma być używana do zaokrąglania. Kwoty ESL będą zaokrąglane do wielokrotności tej liczby.</li>
<li><strong>Metoda zaokrąglania</strong> — umożliwia wybranie metody zaokrąglania, która ma być używana przy zaokrąglaniu kwot ESL (<strong>Normalna</strong>, <strong>W dół</strong> lub <strong>W górę</strong>).</li>
<li><strong>Użyj wartości minimalnej</strong> — zaznacz to pole wyboru, jeżeli kwoty, które są mniejsze od liczby <strong>Reguły zaokrąglania</strong> ma być zaokrąglana do liczby <strong>Reguły zaokrąglania</strong>.</li>
<li><strong>Liczba cyfr dziesiętnych</strong> — służy do określania liczby miejsc po przecinku w kwotach ESL (zarówno w plikach elektronicznych, jak i w raportach <strong>podglądu ESL</strong>).</li>
</ul></li>
<li>Karta <strong>Parametry kraju/regionu</strong>: Identyfikowanie państw członkowskich UE. Dla każdego państwa członkowskiego UE utwórz rekord na stronie, a następnie określ następujące informacje:
<ul>
<li><strong>Kraj/region</strong> – wybierz kraj/region.</li>
<li><strong>Typ kraju/regionu</strong> – jeśli wartości <strong>Kraj/region</strong> jest krajem/regionem, w którym firma jest zarejestrowana, wybierz <strong>Krajowy</strong>. Jeśli wartość <strong>Kraj/region</strong> jest państwem członkowskim UE innym niż kraj/region, w którym firma jest zarejestrowana, wybierz <strong>UE</strong>. Jeśli wartość <strong>Kraj/region</strong> nie jest państwem członkowskim UE, wybierz <strong>Trzeci kraj/region</strong>.</li>
</ul></li>
<li>Karta <strong>Sekwencje identyfikatorów</strong>: w wierszu, w którym <strong>Odwołanie</strong> wybrano wartość <strong>Lista sprzedaży do UE</strong>, wybierz kod sekwencji numerów.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Powiązane transakcje</strong></td>
<td><ul>
<li>Rejestracja sprzedaży dla odbiorcy w innym państwie członkowskim UE.</li>
<li>Rejestracja faktury niezależnej dla odbiorcy w innym państwie członkowskim UE.</li>
<li>Rejestracja faktury projektu dla odbiorcy w innym państwie członkowskim UE.</li>
<li>Rejestracja faktury od dostawcy w innym państwie członkowskim UE.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="working-with-the-esl"></a>Praca z ESL
### <a name="collecting-information-about-intra-community-trade-transactions"></a>Zbieranie informacji dotyczących wewnątrzwspólnotowych transakcji handlowych

Transakcje następujących typów można uznać za transakcje handlu wewnątrzwspólnotowego:

-   Faktury sprzedaży
-   Faktury niezależne
-   Faktury projektu
-   Faktury dostawcy

Transakcja jest uznawana za transakcję handlu wewnątrzwspólnotowego, jeśli adres dostawy transakcji jest w państwie członkowskim UE. Dla tych krajów/regionów musi istnieć rekord na karcie **Parametry kraju/regionu** na stronie **Parametry handlu zagranicznego**, a **Typ kraju/regionu** powinien mieć wartość **UE**. Transakcje handlu wewnątrzwspólnotowego są oznaczane w polu **Kod listy**. Za pomocą tego pola, można także oddzielić ogólne transakcje handlu wewnątrzwspólnotowego od transakcji handlu trójstronnego. Można zbierać informacje o transakcjach handlu wewnątrzwspólnotowego na stronie **Lista sprzedaży do UE** (kliknij kolejno opcje **Podatek** &gt; **Deklaracje** &gt; **Handel zagraniczny** &gt; **Lista sprzedaży do UE**) za pomocą funkcji **Przenieś**. Ta funkcja pozwala na uwzględnianie transakcji zawierających kwoty o różnych typów raportowania (tzn., towary lub usługi) według grup podatku dla towarów określonych w wierszach transakcji. Można także zastosować inne filtry do określania transakcji, które mają być uwzględniane. Funkcja **Przenieś** tworzy rekord na stronie **Lista sprzedaży do UE** dla każdej uwzględnionej transakcji handlu wewnątrzwspólnotowego i umożliwia określenie numeru konta kontrahenta, kraju/regionu, numeru identyfikacji podatkowej, numeru faktury oraz daty i sumy wierszy według typu raportowania. Kopiuje ona także wartość **Kod listy** z transakcji. Kod listy transakcji można ręcznie zmienić na stronie **Lista sprzedaży do UE**. Funkcja **Przenieś** tworzy rekordy, w których wartość **Stan raportowania** jest ustawiona na **Uwzględnione**. Można sprawdzić poprawność informacji, które są gromadzone na stronie **Lista sprzedaży do UE** za pomocą **Sprawdzanie poprawności**.

### <a name="generating-the-eu-sales-list-report"></a>Generowanie raportu ESL.

Można wygenerować raport **Lista sprzedaży do UE** za pomocą funkcji **Raportowanie** na stronie **Lista sprzedaży do UE**. Funkcja umożliwia wybranie okresu raportowania i zastosowanie filtrów w celu zdefiniowania rekordów ESL, które mają być uwzględnione. Ponadto można określić inne parametry właściwe dla każdego kraju/regionu. Można także generować podgląd raportu, pliku elektronicznego lub jednego i drugiego. Funkcja **Raportowanie** wykorzystuje ustawienia formatu raportu i pliku, które są określone na stronie **Parametry handlu zagranicznego**. Ogólnie raport **Lista sprzedaży do UE** składa się z oddzielnych wierszy zawierających listę sum dostaw dla kraju/regionu kontrahenta, numer identyfikacji podatkowej oraz typ raportowania (transakcje handlu trójstronnego są uwzględniane). Po wygenerowaniu raportu **Lista sprzedaży do UE** w danym okresie można oznaczyć rekordy ESL, które są uwzględniane w raporcie przez ustawienie **Stanu raportowania** na wartość **Zgłoszony**. Aby ustawić ten stan, użyj funkcji **Zaznacz jako zgłoszony** na stronie **Lista sprzedaży do UE**.

### <a name="closing-the-eu-sales-list-reporting-period"></a>Zamykanie okresu raportowania ESL

Po zakończeniu procesu generowania raportów w danym okresie (na przykład, kiedy urząd skarbowy zaakceptował raport **Lista sprzedaży do UE**), można oznaczyć rekordy ESL znajdujące się w raporcie dla danego okresu, ustawiając **Stan raportowania** na **Zamknięty**. Aby ustawić ten stan, użyj funkcji **Zaznacz jako zamknięty** na stronie **Lista sprzedaży do UE**. W przypadku cofnięcia zamknięcia okresu można oznaczyć rekordy ESL, ustawiając **Stan raportowania** na **Uwzględniony**. Następnie można ponownie umieszczać te rekordy w raporcie **Lista sprzedaży do UE**. Aby ustawić ten stan, użyj funkcji **Zaznacz jako** **zgłoszony** na stronie **Lista sprzedaży do UE**.




