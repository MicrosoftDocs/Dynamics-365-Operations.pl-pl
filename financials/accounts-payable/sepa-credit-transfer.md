---
title: "Przegląd przeniesienia kredytu SEPA"
description: "Ten artykuł zawiera ogólne informacje o ISO 20022 przelewu, które obejmują przelewów bankowych jednolitego obszaru płatności Euro (SEPA) i innych elektronicznych płatności dla dostawców. Przelewy SEPA jest określonego typu płatności w euro z jednej firmy lub w indywidualnych do innej firmy lub indywidualnych. Opisano także sposób ustawiania i przekazuje kredytu transfer plików płatności."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 848df5e3898f37284d7746c59bff8b38d35ac883
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-credit-transfer-overview"></a>Przegląd przeniesienia kredytu SEPA

Ten artykuł zawiera ogólne informacje o ISO 20022 przelewu, które obejmują przelewów bankowych jednolitego obszaru płatności Euro (SEPA) i innych elektronicznych płatności dla dostawców. Przelewy SEPA jest określonego typu płatności w euro z jednej firmy lub w indywidualnych do innej firmy lub indywidualnych. Opisano także sposób ustawiania i przekazuje kredytu transfer plików płatności.

## <a name="what-is-a-credit-transfer-message"></a>Co to jest wiadomość przeniesienia kredytu?
Komunikat przeniesienia kredytu jest żądanie inicjująca Strona (firma) wysyła przenieść fundusze z jego własnego konta jest winny wierzycielowi. Istnieje wiele implementacji specyficznych dla kraju/regionu i specyficzne dla banku przelewu bankowego wiadomości. Niektóre z nich są używane w ramach jednego kraju/regionu, a niektóre stają się standardów. Jeden ugruntowanego globalny standard jest ISO 20022 i jego wszczęcie, takie jak wiadomości przelewu bankowego. Poniżej przedstawiono stosunków i zasięg dla wybranej faktury transferu wiadomości. 
![Kredyt przesyłanie zawartości](./media/credit-transfer.jpg) kredytu transferu wiadomości\[/caption\] 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Jakie są ISO 20022 i SEPA płatności?
Jednolity Obszar Płatniczy w Euro (SEPA) został ustanowiony przez Komisję Europejską i decyduje o tym, że wszystkie płatności elektroniczne są uważane za krajowe, niezależnie od kraju/regionu, w którym znajdują się osoby, przedsiębiorstwa, organizacje oraz właściwy bank. Nie ma żadnej różnicy między płatności krajowych i transgranicznych. SEPA obejmuje 28 Państw Unii Europejskiej (UE) i również Islandia, Liechtenstein, Norwegia, Szwajcaria, Monako i San Marino. SEPA tworzy jeden rynek dla transakcji płatności w ramach europejskiego obszaru gospodarczego (EOG). Ostatecznie SEPA umożliwia zmniejszenie liczby formatów płatności, którymi operują banki, firmy i osoby prywatne. Komisja Europejska określiła podstawę prawną dla płatności SEPA w postaci dyrektywy w sprawie usług płatniczych (PSD). Europejska Rada ds. Płatności (EPC) wspiera SEPA za pomocą następujących działań:

-   Wyznacza normy dla płatności elektronicznych SEPA zgodnie z uniwersalnym formatem XML ISO 20022 dla schematów wiadomości w branży finansowej.
-   Ustala zasady i wskazówki dotyczące obsługi płatności w euro.

EPC, w której skład wchodzą europejskie banki, opracowuje ramy handlowe i techniczne dla instrumentów płatności SEPA. Używane są trzy rodzaje płatności SEPA:

-   Polecenia przelewu
-   Polecenie zapłaty
-   Karty

## <a name="what-is-a-sepa-credit-transfer"></a>Co to jest polecenie przelewu SEPA?
Polecenie przelewu SEPA jest formą płatności realizowanej przez jedną firmę lub osobę na rzecz innej firmy lub osoby. Płatności muszą być w euro i muszą zawierać międzynarodowy numer konta bankowego (IBAN) oraz kod identyfikatora banku (BIC) dla obu stron. (BIC jest również znany jako Society for Worldwide Interbank Financial Telecommunication \[SWIFT\] kod.) Ponadto koszty transakcji muszą być udostępnione między obiema stronami. Polecenia przelewów realizowane między stronami powinny używać plików XML zgodnych z normami przetwarzania płatności ISO 20022 oraz formatem XML według wytycznych EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Sposób implementacji przelewu bankowego?
Format płatności transferu kredytu dla krajów Europy jest implementowane za pomocą elektronicznego raportowania (ER) i metody funkcji płatności w usłudze Dynamics 365 dla operacji. Kilka formatów przeniesienia kredytu, które są używane w innych regionach nadal używać framework starszych płatności. Wiele innych formatów należą dwunastu ISO 20022 kredytu transfer formatów plików, które są dostępne. Te formaty eksportowania zgodne ze standardem SEPA ISO 20022 XML. Służą one do generowania przelewów spoza euro dla krajów/regionów, w których są one używane i płatności w euro jak określono w wersji 8.2 SEPA kredytu Transfer schemat zbioru przepisów wydawana EPC. Przed zaimplementowaniem przelewów bankowych, należy skontaktować się z Bankiem, aby uzyskać oprogramowanie, które jest wymagane w celu, aby przesłać bankowości elektronicznej. Używasz tego oprogramowania do przesyłania plików XML, które zawierają poleceń płatności do banku.

## <a name="what-credit-transfer-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Jakie formaty przeniesienia kredytu są aktualnie obsługiwane w usłudze Dynamics 365 dla operacji?
Należy zawsze przejdź do biblioteki zasobów współużytkowanych w usług Microsoft Dynamics cyklu (LCS) i wyświetlić aktualną listę dostępne pliki, które mają typ składnika aktywów **konfiguracji GUŁ**. Następnej sekcji, "Co mam skonfigurować?", zawiera łącze do tematu, który wyjaśnia, jak utworzyć repozytorium LCS Przejrzyj dostępne konfiguracje i zaimportować wybranych konfiguracji.

## <a name="what-do-i-have-to-set-up"></a>Co trzeba skonfigurować?
-   Przed utworzeniem przelewu bankowego plików, co najmniej jedną konfigurację transferu kredytowych działających należy zaimportować do konfiguracji encja-Relacja. Aby uzyskać instrukcje, zobacz [pobrać elektroniczne raportowanie konfiguracje z cyklem życia usług](https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   Po skonfigurowaniu konta płatne metod płatności, wybierz **ogólnego raportowania elektronicznego** pole wyboru i wybierz format transferu odpowiednich kredytu (na przykład **ISO 20022 przelewu (AT)**) jako Konfiguracja format eksportu.
-   Należy również skonfigurować informacje encji i konto bankowe prawne w usłudze Dynamics 365 dla operacji.
-   Numery kont bankowych, IBAN i czasami SWIFT kody (BIC) lub innych identyfikatorów są wymagane, aby utworzyć prawidłowe przelewu płatności. W związku z tym należy skonfigurować je dla konta bankowego dostawcy i dla konta bankowego dla organizacji, która żąda transferu.
-   Dodatkowe informacje mogą być wymagane, takie jak numery podatku od wartości dodanej (VAT) dla stron, które są określone w komunikacie przeniesienia kredytu. Informacje te przygotowana dla dostawców i dla podmiotu prawnego, kiedy jest wymagane.
-   Niektóre konta płatne metody płatności, metod płatności, głównie na podstawie ISO 20022 może wymagać dodatkowych ustawień dla **zestawów kodu formatu płatności**, takich jak **typ usługi** = **SLEV**. Te kody są używane jako dodatkowe etykietowanie dla transakcji płatności podczas przetwarzania płatności. Domyślne wartości kodów płatności, jak **celem kategorii**, **okaziciela opłaty**, **lokalnego instrument** i **poziom obsługi** można ustawić w dwóch miejscach. Pierwsze miejsce jest **nagłówek arkusza płatności rozrachunków z dostawcami konta**, a drugi jest **Rozrachunki z dostawcami metody płatności**. Po utworzeniu wierszy arkusza płatności płatności kod wartości ustawione w nagłówku arkusza płatności są przenoszone do wiersza dziennika, jeśli nie ustawiona, używane są wartości od metody płatności.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Jakie parametry są dostępne dla generowania płatności przelewem kredytu?
Lista określonych parametrów zależy od formatu transferu kredytu. W poniższej tabeli przedstawiono parametry, które są dostępne podczas generowania pliku ISO 20022 kredytu przeniesienia płatności dla Niemiec w arkuszach płatności dostawcy. Korzystając z opcji dostępnych na **w tle** kartę, generowanie płatności można uruchomić w trybie wsadowym.

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
<td>Księgowanie zbiorcze</td>
<td>Zaznaczenie tego pola wyboru powoduje umieszczenie znacznika rezerwacji wsadowej w pliku XML.</td>
</tr>
<tr class="even">
<td>Data przetwarzania</td>
<td>Umożliwia wprowadzenie daty, kiedy bank ma przetworzyć płatności.</td>
</tr>
<tr class="odd">
<td>Format</td>
<td>Umożliwia wybranie formatu informacji o przekazie, w zależności od potrzeb banku lub kraju/regionu:
<ul>
<li><strong>Strd</strong> — wybierz tę opcję, aby użyć formatu strukturalnego podczas jeden wiersz płatności jest rozliczona dla jednej faktury. Ta opcja nie jest dostępna dla formatów eksportu specyficzne dla kraju/regionu dla Francji, Niemczech i Holandii.</li>
<li><strong>Ustrd</strong> — wybierz tę opcję, aby użyć formatu niestrukturalnego, gdy płatność jest rozliczana dla wielu faktur. Numery faktur dla rozliczonych faktur są łączone i używane jako informacje o przekazie. Zgodnie z ISO 20022 wytycznych, informacje statystyczne o przekazach niestrukturalnych jest ograniczone do 140 znaków.</li>
</ul></td>
</tr>
<tr class="even">
<td>Liczba faktur</td>
<td>Wprowadź numer faktury tego <strong>zawiadomienie o płatności</strong> z drukowany jest raport.</td>
</tr>
<tr class="odd">
<td>Numer sekwencyjny</td>
<td>Umożliwia wprowadzenie numeru sekwencji identyfikującej plik. Numer sekwencyjny pojawia się na <strong>Notatka towarzysząca</strong> raportu.</td>
</tr>
<tr class="even">
<td>Drukuj notatkę towarzyszącą</td>
<td>Zaznacz to pole wyboru, aby wydrukować raport <strong>Notatka towarzysząca</strong>.</td>
</tr>
<tr class="odd">
<td>Drukuj raport kontroli</td>
<td>Zaznacz to pole wyboru, aby wydrukować raport zawierający informacje o płatności.</td>
</tr>
<tr class="even">
<td>Drukuj list przewodni</td>
<td>Zaznacz to pole wyboru, aby wydrukować raport <strong>Zawiadomienie o płatności</strong>.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>Co to są IBAN i BIC?
Międzynarodowy numer konta bankowego (IBAN) i kod identyfikator banku (BIC) są używane do identyfikowania dowolnego konta w wielu krajach na całym świecie. Należą do nich 34 SEPA krajów/regionów. Wprowadź kod BIC w **kod SWIFT** pola i IBAN w **IBAN** pole. Dla konta bankowego wierzyciela i konto bankowe nabywcy, pola te znajdują się na **dodatkowa identyfikacja** skróconej na **konta bankowego** na karcie **kont bankowych** strony. Stosowania BIC SEPA płatności nie są wymuszane.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Jak przekazać plik płatności do banku?
Podczas generowania płatności, generowany jest plik płatności, a użytkownik jest proszony o zapisać go w przeglądarce sieci web na każdej dostępnej lokalizacji. Następnym krokiem jest wysłać plik XML do swojego banku. Ten proces różni się w zależności od banku. Postępuj zgodnie z instrukcjami otrzymanymi z banku, aby przesłać pliki do banku do przetworzenia.


