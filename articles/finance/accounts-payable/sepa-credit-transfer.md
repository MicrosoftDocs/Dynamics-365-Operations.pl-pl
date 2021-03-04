---
title: Przegląd przeniesienia kredytu SEPA
description: Ten artykuł zawiera ogólne informacje o poleceniach przelewu ISO 20022, co obejmuje polecenia przelewu Jednolitego Obszaru Płatniczego w Euro (SEPA) oraz wszelkie inne elektroniczne płatności dla dostawców. Polecenie przelewu SEPA jest szczególną formą płatności (w euro) realizowanej przez jedną firmę lub osobę na rzecz innej firmy lub osoby. W temacie wyjaśniono również, jak ustawić i przesłać plik płatności poleceniem przelewu.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0fc01508bd206f750a4101521cd9dff7b647656
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446748"
---
# <a name="sepa-credit-transfer-overview"></a>Przegląd przeniesienia kredytu SEPA

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera ogólne informacje o poleceniach przelewu ISO 20022, co obejmuje polecenia przelewu Jednolitego Obszaru Płatniczego w Euro (SEPA) oraz wszelkie inne elektroniczne płatności dla dostawców. Polecenie przelewu SEPA jest szczególną formą płatności (w euro) realizowanej przez jedną firmę lub osobę na rzecz innej firmy lub osoby. W temacie wyjaśniono również, jak ustawić i przesłać plik płatności poleceniem przelewu.

## <a name="what-is-a-credit-transfer-message"></a>Co to jest komunikat polecenia przelewu?
Komunikat polecenia przelewu to żądanie wysyłane przez stronę inicjującą (Twoją firmę) nakazujące przelania funduszy z jej własnego konta do wierzyciela. Istnieje wiele implementacji komunikatów polecenia przelewu specyficznych dla krajów/regionów i banków. Niektóre z nich są używane wewnątrz jednego kraju/regionu, a niektóre stają się standardami. Jednym z ugruntowanych globalnych standardów jest ISO 20022 i jego komunikaty inicjujące, takie jak polecenie przelewu. Poniższa ilustracja przedstawia powiązania i zasięg wybranych komunikatów poleceń przelewu. 
![Polecenie przelewu](./media/credit-transfer.jpg) Komunikaty poleceń przelewu 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Co to są płatności ISO 20022 i SEPA?
Jednolity Obszar Płatniczy w Euro (SEPA) został ustanowiony przez Komisję Europejską i decyduje o tym, że wszystkie płatności elektroniczne są uważane za krajowe, niezależnie od kraju/regionu, w którym znajdują się osoby, przedsiębiorstwa, organizacje oraz właściwy bank. Nie istnieje różnica między płatnościami krajowymi i międzynarodowymi. SEPA obejmuje 28 państw członkowskich Unii Europejskiej (UE), plus Islandię, Liechtenstein, Norwegię, Szwajcarię, Monako i San Marino. SEPA tworzy jeden rynek dla transakcji płatności w ramach europejskiego obszaru gospodarczego (EOG). Ostatecznie SEPA umożliwia zmniejszenie liczby formatów płatności, którymi operują banki, firmy i osoby prywatne. Komisja Europejska określiła podstawę prawną dla płatności SEPA w postaci dyrektywy w sprawie usług płatniczych (PSD). Europejska Rada ds. Płatności (EPC) wspiera SEPA za pomocą następujących działań:

-   Wyznacza normy dla płatności elektronicznych SEPA zgodnie z uniwersalnym formatem XML ISO 20022 dla schematów wiadomości w branży finansowej.
-   Ustala zasady i wskazówki dotyczące obsługi płatności w euro.

EPC, w której skład wchodzą europejskie banki, opracowuje ramy handlowe i techniczne dla instrumentów płatności SEPA. Używane są trzy rodzaje płatności SEPA:

-   Polecenia przelewu
-   Polecenie zapłaty
-   Karty

## <a name="what-is-a-sepa-credit-transfer"></a>Co to jest polecenie przelewu SEPA?
Polecenie przelewu SEPA jest formą płatności realizowanej przez jedną firmę lub osobę na rzecz innej firmy lub osoby. Płatności muszą być w euro i muszą zawierać międzynarodowy numer konta bankowego (IBAN) oraz kod identyfikatora banku (BIC) dla obu stron. (Kod BIC jest również znany pod nazwą Society for Worldwide Interbank Financial Telecommunications \[SWIFT\]). Ponadto koszty transakcji muszą być dzielone między stronami. Polecenia przelewów realizowane między stronami powinny używać plików XML zgodnych z normami przetwarzania płatności ISO 20022 oraz formatem XML według wytycznych EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Jak jest implementowane polecenie przelewu?
Format płatności polecenia przelewu dla krajów europejskich jest implementowany przy użyciu modułu Raportowanie elektroniczne (ER) i funkcji Metody płatności w Microsoft Dynamics 365 Finance. Kilka formatów polecenia przelewu stosowanych w innych regionach nadal wykorzystuje starszą architekturę przelewu płatności. Wśród wielu innych formatów jest dwanaście formatów plików polecenia przelewu ISO 20022, które nadal funkcjonują. Te formaty eksportu są zgodne z normą XML ISO 20022 dla płatności SEPA. Służą do generowania przelewów płatności w walutach innych niż euro w krajach/regionach, gdzie takie waluty są używane, oraz płatności w euro zgodnie z treścią wersji 8.2 Zestawu Zasad Systemu Polecenia Przelewu SEPA publikowanego przez EPC. Zanim będzie można zaimplementować polecenia przelewu, należy skontaktować się z bankiem, by uzyskać oprogramowanie, które jest wymagane do przekazywania plików bankowości elektronicznej. Oprogramowanie to służy to przesyłania plików XML zawierających polecenia zapłaty dla banku.

## <a name="what-credit-transfer-formats-are-currently-supported"></a>Które polecenia przelewu są obecnie obsługiwane?
Należy zawsze przejść do biblioteki zasobów wspólnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) i wyświetlić najbardziej aktualną listę dostępnych plików, które mają typ składnika aktywów **Konfiguracja GER**. Następna sekcja — „Co trzeba skonfigurować?” — zawiera łącze do tematu, który wyjaśnia sposób tworzenia repozytorium usługi LCS na potrzeby przeglądania dostępnych konfiguracji i importowania wybranych konfiguracji.

## <a name="what-do-i-have-to-set-up"></a>Co trzeba skonfigurować?
-   Zanim będzie można tworzyć pliki poleceń przelewu, należy zaimportować co najmniej jedną aktywną konfigurację polecenia przelewu do konfiguracji raportowania elektronicznego. Instrukcje znajdują się w temacie [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
-   W przypadku konfigurowania metod płatności do rozrachunków z dostawcami należy zaznaczyć pole wyboru **Ogólne raportowanie elektroniczne** i wybrać odpowiedni format polecenia przelewu ISO (np. **Polecenie przelewu ISO 20022 (AT)**) jako konfigurację formatu eksportu.
-   Należy także skonfigurować informacje firmy i konta bankowego.
-   Do tworzenia prawidłowych płatności poleceniami przelewu są potrzebne numery kont bankowych, numery IBAN i czasami kody SWIFT (BIC) lub inne identyfikatory. W związku z tym należy je skonfigurować dla konta bankowego dostawcy i konta bankowego organizacji wnioskującej o przelew.
-   Mogą być też wymagane dodatkowe informacje, takie jak numery płatnika podatku od wartości dodanej (VAT) dla stron wymienionych w komunikacie polecenia przelewu. Informacje te muszą zostać wprowadzone dla dostawców i firmy, kiedy jest to wymagane.
-   Niektóre metody płatności w rozrachunkach z dostawcami, głównie oparte na standardzie ISO 20022, mogą wymagać dodatkowych ustawień w obszarze **Zestawy kodów formatów płatności**, np. **Typ usługi** = **SLEV**. Te kody są używane jako dodatkowe znakowanie transakcji płatniczych w trakcie przetwarzania płatności. Domyślne wartości kodów płatności, takie jak **Cel kategorii**, **Płatnik opłaty**, **Instrument lokalny** i **Poziom usług**, można konfigurować w dwóch miejscach. Pierwszym miejscem jest **nagłówek arkusza płatności w rozrachunkach z dostawcami**, a drugim **metody płatności w rozrachunkach z dostawcami**. Gdy utworzysz wiersze arkusza płatności, wartości kodów płatności ustawione w nagłówku arkusza płatności są przenoszone do wiersza arkusza, a jeśli nie zostały ustawione, system używa wartości z metod płatności.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Które parametry są dostępna do generowania płatności za pomocą polecenia przelewu?
Lista konkretnych parametrów zależy od formatu polecenia przelewu. Poniższa tabela zawiera listę parametrów, które są dostępne podczas generowania pliku płatności poleceniem przelewu ISO 20022 dla Niemiec w arkuszu płatności dostawcy. Korzystając z opcji dostępnych na karcie **Uruchom w tle**, można generować płatności w trybie wsadowym.

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
<li><strong>Strd</strong> — wybierz tę opcję, aby użyć formatu uporządkowanego, gdy jeden wiersz płatności jest rozliczany dla jednej faktury. Ta opcja jest niedostępna dla formatów eksportu właściwych dla Francji, Niemiec i Holandii.</li>
<li><strong>Ustrd</strong> — wybierz tę opcję, aby użyć formatu niestrukturalnego, gdy płatność jest rozliczana dla wielu faktur. Numery faktur dla rozliczonych faktur są łączone i używane jako informacje o przekazie. Zgodnie z wytycznymi ISO 20022 nieuporządkowane informacje o przekazach są ograniczone do 140 znaków.</li>
</ul></td>
</tr>
<tr class="even">
<td>Liczba faktur</td>
<td>Umożliwia wprowadzenie liczby faktur, z których jest drukowany raport <strong>Zawiadomienie o płatności</strong>.</td>
</tr>
<tr class="odd">
<td>Numer sekwencyjny</td>
<td>Umożliwia wprowadzenie numeru sekwencji identyfikującej plik. Numer kolejny jest widoczny na raporcie <strong>Notatka towarzysząca</strong>.</td>
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
Międzynarodowy numer konta bankowego (IBAN) i kod identyfikacyjny banku (SWIFT) są używane do identyfikowania każdego konta w wielu krajach/regionach na świecie. Obejmuje to również 34 kraje/regiony SEPA. Wprowadź kod identyfikacyjny banku (BIC) w polu **Kod SWIFT**, a numer IBAN w polu **IBAN**. Zarówno dla konta bankowego wierzyciela, jak i dla konta bankowego odbiorcy te pola znajdują się na skróconej karcie **Dodatkowa identyfikacja** na karcie **Konto bankowe** na stronie **Konta bankowe**. Stosowanie kodu BIC w płatnościach SEPA nie jest już wymuszane.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Jak przekazać plik płatności do banku?
Podczas generowania płatności zostanie wygenerowany plik płatności, a użytkownik jest proszony o zapisanie go w przeglądarce sieci web w dowolnej dostępnej lokalizacji. Następnym krokiem jest wysłanie pliku XML do banku. Ten proces różni się w zależności od banku. Postępuj zgodnie z instrukcjami otrzymanymi z banku, aby przesłać pliki do banku do przetworzenia.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]