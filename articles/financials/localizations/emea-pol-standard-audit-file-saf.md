---
title: Standardowy plik audytu (SAF) dla Polski
description: Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten temat zawiera informacje o formatach dla Polski.
author: LizaGolub
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274193
ms.assetid: b85c4019-f682-45bf-9a0d-c7549a2f1274
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 57d6924c7b1fde450a14a5083e84a77fc6549ead
ms.sourcegitcommit: bacec9ceb40bba604c86c8adbd0ccd0a6aa175a1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/27/2019
ms.locfileid: "769566"
---
# <a name="standard-audit-file-saf-for-poland"></a>Standardowy plik audytu (SAF) dla Polski

[!include [banner](../includes/banner.md)]

Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten temat zawiera informacje o formatach dla Polski. 

Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten dokument zawiera informacje o formatach dla Polski. Niniejszy dokument odnosi się do funkcji, która nie została jeszcze wdrożona.

## <a name="set-up-the-standard-audit-file-for-tax-for-poland"></a>Konfigurowanie standardowego pliku audytu dla podatku dla Polski
Aby określić format raportowania elektronicznego (ER) dla każdego schematu SAF-T, kliknij przycisk kolejno opcje **Księga główna > Ustawienia księgi > Parametry księgi głównej**, a następnie na karcie **Standardowy plik audytu dla podatków (SAF-T)** skonfiguruj konkretne formaty dla każdego z następujących schematów:

-   Księgi księgowania SAF
-   Wyciągi bankowe SAF
-   Zapasy SAF
-   Rejestry SAF zakupów i sprzedaży objętych podatkiem VAT
-   Faktury VAT SAF

Każdy format raportowania elektronicznego powinien być wstępnie zdefiniowany i pozwalać na aktualizowanie w module Raportowanie elektroniczne.

## <a name="generate-a-saf-accounting-books-file"></a>Generowanie pliku ksiąg księgowania SAF
Aby wygenerować plik ksiąg księgowania SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Księgi księgowania SAF** i ustaw następujące parametry:

|Parametr                                        |  opis            |
|-------------------------------------------------|-------------------------|
| **Od dnia**                                   | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych. |
| **Do dnia**                                     | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.  |
| **Identyfikacja urzędu**                    | Określ identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.|
| **Warstwa księgowania**                               | Umożliwia wybranie warstwy księgowania, od której mają być uwzględniane transakcje. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu. |
| **Czy saldo otwarcia ma być pokazywane jako obroty?** | Jeśli ten parametr jest zaznaczony, transakcje otwarcia mają wpływ na obroty narastająco. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu. |
| **Saldo rozwarte**                            | Ten parametr można włączać dla kont głównych, w których jest oznaczony odnośny parametr. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.     |
| **Transakcje zamknięcia**                        | Jeśli ten parametr jest zaznaczony, transakcje zamknięcia będą uwzględnione w eksportowanych danych. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu. |

Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.

## <a name="generate-a-saf-bank-statement-file"></a>Generowanie pliku wyciągu bankowego SAF
Aby wygenerować plik wyciągu bankowego SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Wyciąg bankowy SAF** i ustaw następujące parametry:

| Parametr                    | opis                                                                        |
|------------------------------|------------------------------------------------------------------------------------|
| **Od dnia**                | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                               |
| **Do dnia**                  | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                                |
| **Identyfikacja urzędu** | Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu. |
| **Konto bankowe**             | Umożliwia określenie rachunku bankowego, dla którego mają zostać wyeksportowane transakcje.                               |

 

## <a name="generate-a-saf-inventory-file"></a>Generowanie pliku zapasów SAF
Aby wygenerować plik zapasów SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Zapasy SAF** i ustaw następujące parametry:

| Parametr                    | opis                                                                        |
|------------------------------|------------------------------------------------------------------------------------|
| **Od dnia**                | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                               |
| **Do dnia**                  | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                                |
| **Identyfikacja urzędu** | Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu. |
| **Magazyn**                | Określ magazyn, dla którego mają zostać wyeksportowane transakcje.                                  |

### 

## <a name="generate-a-saf-vat-sales-and-purchase-register"></a>Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT
Zanim będzie można wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem od towarów i usług (VAT), należy wykonać następujące dodatkowe czynności konfiguracyjne:

-   Skonfiguruj urzędy skarbowe.
-   Konfigurowanie kodów podatków dla raportowania podatku VAT.
-   Ustawianie kodów podatków.
-   Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.

Aby uzyskać więcej informacji o ustawieniach deklaracji VAT, zobacz [Raportowanie podatku VAT (UE)](emea-vat-reporting.md).

### <a name="set-up-sales-tax-authorities"></a>Konfigurowanie urzędów skarbowych

Aby uzyskać ogólne informacje dotyczące sposobu konfigurowania urzędu skarbowego, zobacz [Konfigurowanie urzędów skarbowych (przewodnik po zadaniu)](../general-ledger/tasks/set-up-sales-tax-authorities.md). Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT w wymaganym formacie dla odpowiedniego urzędu skarbowego, należy zdefiniować układ raportu dla urzędów skarbowych. Na stronie **Urzędy skarbowe** (**Podatek > Podatki pośrednie > Podatek > Urzędy skarbowe**) w polu **Układ raportu** zaznacz wartość **Domyślnie**. Zaznacz ten sam urząd skarbowy dla okresu rozliczeniowego podatku, który będzie używany dla kodów podatków.

### <a name="set-up-sales-tax-codes-and-sales-tax-reporting-codes"></a>Konfigurowanie kodów podatków i kodów sprawozdawczości podatkowej

Kod raportowania jest liczbą całkowitą. Kody raportowania powinny być numerowane zgodnie z regułami obowiązującymi w firmie. Jednak zalecamy, aby różnicować kody według kierunku podatku. Na przykład zdefiniuj kod 5-cyfrowy i tak ustaw kody dla wszystkich transakcji wychodzących, które powinny być odzwierciedlane w pierwszej części schematu podatku VAT, aby były mniejsze lub równe 19999. Natomiast dla wszystkich transakcji przychodzących, które powinny być wykazywane w drugiej części systemu podatku VAT, ustaw kody tak, aby były większe lub równe 20000. W ten sposób uprościsz konfigurację raportów i eksportu danych, która opiera się na transakcjach podatkowych agregowanych według kodów raportowania. Oto przykład pokazujący użycie kodów sprawozdawczości podatkowej do generowania rejestru SAF sprzedaży i zakupów objętych podatkiem VAT. W tym przykładzie kody raportowania są w formacie *ABBCC*. Ten format składa się z następujących elementów:

-   **A** — Kierunek transakcji. Wartość wynosi **1** dla podatków wychodzących, **2** dla podatków przychodzących i **3** dla korekt.
-   **BB** — Kod podatku. Numeracja zachowuje kolejność wśród wszystkich kodów podatków.
-   **CC** — Numer typu transakcji wewnątrz kodu podatku. Parz tabela poniżej.

| Typ transakcji                      | Numer typu transakcji     |
|---------------------------------------|-----------------------------|
| **Sprzedaż opodatkowana**                     | 01                          |
| **Sprzedaż wolna od podatku**                    | 02                          |
| **Podatek należny**                 | 03                          |
| **Opodatkowana faktura korygująca sprzedaży**         | 04                          |
| **Faktura korygująca sprzedaży zwolnionej z podatku**      | 05                          |
| **Podatek od faktury korygującej sprzedaży**    | 6                          |
| **Zakup podlegający opodatkowaniu**                 | 07                          |
| **Zakup wolny od podatku**                 | 08                          |
| **Podatek naliczony**              | 09                          |
| **Import opodatkowany**                    | 10                          |
| **Przeciwstawna wartość importu podlegająca opodatkowaniu**             | 11                          |
| **Podatek nienaliczony**                           | 12                          |
| **Konto przeciwstawne podatku nienaliczonego**                    | 13                          |
| **Opodatkowana faktura korygująca zakupu**      | 14                          |
| **Faktura korygująca zakupu zwolnionego z podatku**   | 15                          |
| **Podatek od faktury korygującej zakupu** | 16                          |
| **Opodatkowana faktura korygująca importu**        | 17                          |
| **Faktura korygująca przeciwstawnej wartości importu podlegającej opodatkowaniu** | 18                          |

W poniższej tabeli przedstawiono kody podatków i kody sprawozdawczości podatkowej dla tego przykładu.

<table width="100%">
<tbody>
<tr>
<td><strong>Kod podatku</strong></td>
<td><strong>Kod raportowania podatku</strong></td>
<td><strong>Opis</strong></td>
<td><strong>Nazwa znacznika w podatku VAT SAF-T</strong></td>
<td><strong>Znak w podatku VAT SAF-T</strong></td>
</tr>
<tr>
<td rowspan="4"><strong>ExportCust</strong></td>
<td>10101</td>
<td>Sprzedaż opodatkowana</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td>10102</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td>10104</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td>10105</td>
<td>Faktura korygująca sprzedaży zwolnionej z podatku</td>
<td>K_11</td>
<td>-</td>
</tr>
<tr>
<td rowspan="2"><strong>Art100</strong></td>
<td>10201</td>
<td>Sprzedaż opodatkowana</td>
<td>K_12</td>
<td>-</td>
</tr>
<tr>
<td>10204</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_12</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><strong>VAT22_23</strong></td>
<td>10301</td>
<td>Sprzedaż opodatkowana</td>
<td>K_19</td>
<td>-</td>
</tr>
<tr>
<td>10302</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10303</td>
<td>Podatek należny</td>
<td>K_20</td>
<td>-</td>
</tr>
<tr>
<td>10304</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_19</td>
<td>-</td>
</tr>
<tr>
<td>10306</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_20</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><strong>VAT7_8</strong></td>
<td>10401</td>
<td>Sprzedaż opodatkowana</td>
<td>K_17</td>
<td>-</td>
</tr>
<tr>
<td>10402</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10403</td>
<td>Podatek należny</td>
<td>K_18</td>
<td>-</td>
</tr>
<tr>
<td>10404</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_17</td>
<td>-</td>
</tr>
<tr>
<td>10406</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_18</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><strong>VAT5</strong></td>
<td>10501</td>
<td>Sprzedaż opodatkowana</td>
<td>K_15</td>
<td>-</td>
</tr>
<tr>
<td>10502</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10503</td>
<td>Podatek należny</td>
<td>K_16</td>
<td>-</td>
</tr>
<tr>
<td>10504</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_15</td>
<td>-</td>
</tr>
<tr>
<td>10506</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_16</td>
<td>-</td>
</tr>
<tr>
<td rowspan="3"><strong>VAT0</strong></td>
<td>10601</td>
<td>Sprzedaż opodatkowana</td>
<td>K_13</td>
<td>-</td>
</tr>
<tr>
<td>10602</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_10</td>
<td>-</td>
</tr>
<tr>
<td>10604</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_13</td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><strong>ART129</strong></td>
<td>10701</td>
<td>Sprzedaż opodatkowana</td>
<td>K_14</td>
<td>-</td>
</tr>
<tr>
<td>10702</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_14</td>
<td>-</td>
</tr>
<tr>
<td>10704</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_14</td>
<td>-</td>
</tr>
<tr>
<td>10705</td>
<td>Faktura korygująca sprzedaży zwolnionej z podatku</td>
<td>K_14</td>
<td>-</td>
</tr>
<tr>
<td rowspan="3"><strong>IntraEUGoods</strong></td>
<td>10801</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_21</td>
<td>-</td>
</tr>
<tr>
<td>10810</td>
<td>Import opodatkowany</td>
<td>K_23</td>
<td>+</td>
</tr>
<tr>
<td>10812</td>
<td>Podatek nienaliczony</td>
<td>K_24</td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><strong>ExportOfGoods</strong></td>
<td>10901</td>
<td>Sprzedaż wolna od podatku</td>
<td>K_22</td>
<td>-</td>
</tr>
<tr>
<td>10905</td>
<td>Faktura korygująca sprzedaży zwolnionej z podatku</td>
<td>K_22</td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><strong>ImportOfGoodsART33</strong></td>
<td>20207</td>
<td>Import opodatkowany</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>11010</td>
<td>Przeciwstawna wartość importu podlegająca opodatkowaniu</td>
<td>K_25</td>
<td>-</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek nienaliczony</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>11012</td>
<td>Konto przeciwstawne podatku nienaliczonego</td>
<td>K_26</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><strong>ImportOfServices</strong></td>
<td>20207</td>
<td>Import opodatkowany</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>11110</td>
<td>Przeciwstawna wartość importu podlegająca opodatkowaniu</td>
<td>K_27</td>
<td>-</td>
</tr>
<tr>
<td>11117</td>
<td>Sprzedaż opodatkowana (opłata zwrotna)</td>
<td>K_27</td>
<td>+</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek nienaliczony</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>11112</td>
<td>Konto przeciwstawne podatku nienaliczonego</td>
<td>K_28</td>
<td>-</td>
</tr>
<tr>
<td rowspan="5"><strong>ImportART28</strong></td>
<td>20207</td>
<td>Import opodatkowany</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>11210</td>
<td>Przeciwstawna wartość importu podlegająca opodatkowaniu</td>
<td>K_29</td>
<td>-</td>
</tr>
<tr>
<td>111119</td>
<td>Sprzedaż opodatkowana (opłata zwrotna)</td>
<td>K_29</td>
<td>+</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek nienaliczony</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>11212</td>
<td>Konto przeciwstawne podatku nienaliczonego</td>
<td>K_30</td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><strong>ReverseCharge</strong></td>
<td>11301</td>
<td>Sprzedaż opodatkowana</td>
<td>K_34</td>
<td>-</td>
</tr>
<tr>
<td>11302</td>
<td>Podatek należny</td>
<td>K_35</td>
<td>-</td>
</tr>
<tr>
<td>11304</td>
<td>Opodatkowana faktura korygująca sprzedaży</td>
<td>K_34</td>
<td>-</td>
</tr>
<tr>
<td>11306</td>
<td>Podatek od faktury korygującej sprzedaży</td>
<td>K_35</td>
<td>-</td>
</tr>
<tr>
<td rowspan="4"><strong>FixedAssetPurch</strong></td>
<td>20107</td>
<td>Zakup podlegający opodatkowaniu</td>
<td>K_43</td>
<td>+</td>
</tr>
<tr>
<td>20109</td>
<td>Podatek naliczony</td>
<td>K_44</td>
<td>+</td>
</tr>
<tr>
<td>20115</td>
<td>Opodatkowana faktura korygująca zakupu</td>
<td>K_43</td>
<td>+</td>
</tr>
<tr>
<td>20116</td>
<td>Podatek od faktury korygującej zakupu</td>
<td>K_47</td>
<td>+</td>
</tr>
<tr>
<td rowspan="4"><strong>GoodServPurch</strong></td>
<td>20207</td>
<td>Zakup podlegający opodatkowaniu</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>20209</td>
<td>Podatek naliczony</td>
<td>K_46</td>
<td>+</td>
</tr>
<tr>
<td>20215</td>
<td>Opodatkowana faktura korygująca zakupu</td>
<td>K_45</td>
<td>+</td>
</tr>
<tr>
<td>20216</td>
<td>Podatek od faktury korygującej zakupu</td>
<td>K_48</td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><strong>CorrATR89b1</strong></td>
<td>30101</td>
<td>Podatek należny</td>
<td>K_49</td>
<td>+</td>
</tr>
<tr>
<td>30109</td>
<td>Podatek naliczony</td>
<td>K_49</td>
<td>+</td>
</tr>
<tr>
<td rowspan="2"><strong>CorrATR89b4</strong></td>
<td>30201</td>
<td>Podatek należny</td>
<td>K_50</td>
<td>+</td>
</tr>
<tr>
<td>30209</td>
<td>Podatek naliczony</td>
<td>K_50</td>
<td>+</td>
</tr>
</tbody>
</table>

### <a name="configure-the-er-model-and-format-for-the-report"></a>Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu

Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**. Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model. Aby przejrzeć lub zmodyfikować format rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Rejestr VAT (PL)** i kliknij przycisk **Projektant**. Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:

-   [Omówienie Raportowania elektroniczne](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego](../../dev-itpro/analytics/electronic-reporting-configuration.md)

Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej. Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji. W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**. Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**. Utworzony format jest kopią formatu nadrzędnego. Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania. Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane). Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**. Model danych zawiera wszystkie pola wszystkich raportów SAF-T. Format rejestru VAT jest mapowany głównie do węzła **TaxTransaction**. Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł. Wszystkie transakcje podatkowe są podzielone na dwie grupy: według znacznika **SprzedazWiersz** i według znacznika **ZakupWiersz**. Oraz zatytułowane odpowiednio **$SalesList** i **$PurchaseList**. Są to listy rekordów obliczane (filtrowane) według formuł. Formuły można przeglądać i modyfikować w redaktorze formuł. W tym celu należy zaznaczyć pole obliczeniowe lub listę rekordów (w tym konkretnym przypadku), a następnie w menu drzewa kliknąć przycisk **Edytuj**. Zmodyfikuj formuły dla grup **$SalesList** i **$PurchaseList** zgodnie z kodami raportowania używanymi w firmie, a następnie je zapisz. Okno projektanta formuł po lewej stronie zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować. (Więcej informacji o projektancie formatów — [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)). Po podzieleniu transakcji podatkowych na dwie grupy należy wewnątrz każdej grupy pogrupować transakcje dla każdego znacznika zgodnie z kodami raportowania używanymi w firmie. Znajdź pola obliczeniowe „list\_K” w grupach **$SalesList** i **$PurchaseList** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł. Po zaktualizowaniu formuł wszystkich węzłów „list\_K” odszukaj i zmodyfikuj elementy **SalasCtrl** i **PurchCtrl** odpowiednio w grupach **$SalesList** i **$PurchaseList**. Te węzły są używane odpowiednio przez znaczniki **SprzedazCtrl** i **ZakupCtrl** . Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie. Zapisz format. Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.

### <a name="generate-a-saf-vat-sales-and-purchase-register"></a>Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT

Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Rejestr SAF sprzedaży i zakupów objętych podatkiem VAT** i ustaw następujące parametry:

|   Parametr                  |   opis                                                                      |
|------------------------------|------------------------------------------------------------------------------------|
| **Od dnia**                | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                               |
| **Do dnia**                  | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                               |
| **Identyfikacja urzędu** | Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu. |

Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.

### <a name="generate-a-saf-vat-invoices-file"></a>Generowanie pliku faktur VAT SAF

Aby można było wygenerować plik faktur VAT SAF, należy wykonać następujące dodatkowe czynności konfiguracyjne:

-   Skonfiguruj urzędy skarbowe.
-   Kody podatków dla raportowania podatku VAT.
-   Ustawianie kodów podatków.
-   Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.

To konfigurowanie przypomina dodatkowe konfigurowanie wykonane dla rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, z wyjątkiem czynności **Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu**.

### <a name="configure-the-er-model-and-format-for-the-report"></a>Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu

Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**. Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model. Aby przejrzeć lub zmodyfikować faktury VAT SAF, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Faktury VAT (PL)** i kliknij przycisk **Projektant**. Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:

-   [Omówienie Raportowania elektroniczne](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego](../../dev-itpro/analytics/electronic-reporting-configuration.md)

Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej. Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji. W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**. Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**. Utworzony format jest kopią formatu nadrzędnego. Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania. Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane). Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**. Model danych zawiera wszystkie pola wszystkich raportów SAF-T. Format **Faktury VAT** składa się z kilku sekcji z różnymi źródłami danych. Dane pod znacznikiem **Faktura** są mapowane głównie do węzła **Model &gt; SourceDocuments &gt; $Invoices**. Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł. Znajdź pola obliczeniowe **list\_P\_** w węźle **$Invoices** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł. Okno projektanta formuł zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować. Aby uzyskać więcej informacji o projektancie formatów, zobacz [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md). Wartości znaczników pod znacznikiem **StawkiPodatku** są stałe. Zaznacz węzeł wartości (ciąg) dla każdego znacznika pod znacznikiem **StawkiPodatku** i ustaw mu wartość w polu **Wartość** na karcie **Format** z prawej strony okna **Projektant**. Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie. Zapisz format. Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.

### <a name="generate-a-saf-vat-invoices"></a>Generowanie faktur VAT SAF

Aby wygenerować plik faktur VAT SAF, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Faktury VAT SAF** i ustaw następujące parametry:

|  Parametr                   | opis                                                                            |
|------------------------------|----------------------------------------------------------------------------------------|
| **Od dnia**                | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                                   |
| **Do dnia**                  | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                                    |
| **Identyfikacja urzędu** | Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.     |
| **Identyfikator faktury Od/Do**     | Określ zakres identyfikatorów faktur, aby ograniczyć ilość faktur wybieranych dla eksportu danych. |

Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.

## <a name="using-batch-jobs-for-saft"></a>Używanie zadań wsadowych dla raportów SAFT
Generowanie raportów SAF-T za długi okres, taki jak miesiąc lub kwartał, może powodować objęcie bardzo dużej ilości danych i zajmować dużo czasu. W takich przypadkach zaleca się używanie zadań wsadowych. Okno dialogowe dla każdego raportu SAF-T zawiera kartę **Uruchom w tle**. Otwórz tę kartę, aby ustawić generowanie raportu w trybie wsadowym. Zaznacz pole wyboru **Przetwarzanie wsadowe**. Aby uzyskać więcej informacji na temat przetwarzania wsadowego, zobacz temat [Omówienie przetwarzania wsadowego](../../dev-itpro/sysadmin/batch-processing-overview.md). Aby przejrzeć zadania wsadowe lub znaleźć wygenerowany plik, otwórz okno **Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Zadania raportowania elektronicznego** i znajdź wiersz związany z zadaniem. W **menu głównym** kliknij przycisk **Pokaż dziennik**. Jeżeli nic nie jest wyświetlane, oznacza to, że podczas generowania pliku nie zostały utworzone żadne komunikaty. Aby zobaczyć plik, w **menu głównym** kliknij przycisk **Pokaż pliki**, znajdź żądany plik i w **menu głównym** kliknij przycisk **Otwórz**.  

