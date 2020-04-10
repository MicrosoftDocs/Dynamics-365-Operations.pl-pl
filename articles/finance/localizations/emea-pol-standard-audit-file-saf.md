---
title: Standardowy plik audytu (SAF) dla Polski
description: Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten temat zawiera informacje o formatach dla Polski.
author: LizaGolub
manager: AnnBe
ms.date: 03/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 274193
ms.assetid: b85c4019-f682-45bf-9a0d-c7549a2f1274
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 6a543258219b461f1eaaad0e2c18c86e4a5793c7
ms.sourcegitcommit: 4445977b68d61003ea3b9cb0a002ccf5843e4a64
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/27/2020
ms.locfileid: "3170316"
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
| **Warstwa księgowania**                               | Umożliwia wybranie jednej lub więcej warstwy księgowania, od której mają być uwzględniane transakcje. Ten parametr ma wpływ na wszystkie części raportu. |
| **Czy saldo otwarcia ma być pokazywane jako obroty?** | Jeśli ten parametr jest zaznaczony, narastające obroty mają wpływ na saldo otwarcia. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu. |
| **Saldo rozwarte**                            | Ten parametr można włączać dla kont głównych, w których jest oznaczony odnośny parametr. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.     |
| **Transakcje zamknięcia**                        | Jeśli ten parametr jest zaznaczony, transakcje zamknięcia będą uwzględnione w eksportowanych danych. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu. |

Sprawozdanie to musi być dostarczone na żądanie i zawiera dane księgowania dla okresu sprawozdawczego. Obejmuje ono dane księgowania w wybranych warstwach księgowania dla wszystkich kont głównych, które w okresie sprawozdawczym mają niezerowe łączne obroty lub transakcje.

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

Aby uzyskać więcej informacji o ustawieniach deklaracji VAT, zobacz [Raportowanie podatku VAT w Europie](emea-vat-reporting.md).

### <a name="set-up-sales-tax-authorities"></a>Konfigurowanie urzędów skarbowych

Aby uzyskać ogólne informacje dotyczące sposobu konfigurowania urzędu skarbowego, zobacz [Konfigurowanie urzędów skarbowych](../general-ledger/tasks/set-up-sales-tax-authorities.md). Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT w wymaganym formacie dla odpowiedniego urzędu skarbowego, należy zdefiniować układ raportu dla urzędów skarbowych. Na stronie **Urzędy skarbowe** (**Podatek > Podatki pośrednie > Podatek > Urzędy skarbowe**) w polu **Układ raportu** zaznacz wartość **Domyślnie**. Zaznacz ten sam urząd skarbowy dla okresu rozliczeniowego podatku, który będzie używany dla kodów podatków.

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
<td rowspan="4"><strong>IntraEUGoods</strong></td>
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
<td>10811</td>
<td>Sprzedaż opodatkowana (opłata zwrotna)</td>
<td>K_23</td>
<td>-</td>
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

W przypadku faktur, które nie zostały opłacone w ciągu 150 dni, można zastosować zadanie okresowe **Zaległa kwota podatku VAT stanowiąca zadłużenie**. W takim przypadku można użyć tych samych kodów raportowania, które są używane dla **K_44** i/lub **K_46**. System automatycznie interpretuje transakcje do raportowania w **K_49** (Zaległa faktura) i **K_50** (Opłacona zaległa faktura). 

### <a name="configure-the-er-model-and-format-for-the-report"></a>Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu

Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**. Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model. Aby przejrzeć lub zmodyfikować format rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Rejestr VAT (PL)** i kliknij przycisk **Projektant**. Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:

-   [Omówienie Raportowania elektroniczne](../../dev-itpro/analytics/general-electronic-reporting.md)
-   [Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   [Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego](../../dev-itpro/analytics/electronic-reporting-configuration.md)

Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej. Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji. W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**. Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**. Utworzony format jest kopią formatu nadrzędnego. Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania. Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane). Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**. Model danych zawiera wszystkie pola wszystkich raportów SAF-T. Format rejestru VAT jest mapowany głównie do węzła **TaxTransaction**. Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł. Wszystkie transakcje podatkowe są podzielone na dwie grupy: według znacznika **SprzedazWiersz** i według znacznika **ZakupWiersz**. Oraz zatytułowane odpowiednio **$SalesList** i **$PurchaseList**. Są to listy rekordów obliczane (filtrowane) według formuł. Formuły można przeglądać i modyfikować w redaktorze formuł. W tym celu należy zaznaczyć pole obliczeniowe lub listę rekordów (w tym konkretnym przypadku), a następnie w menu drzewa kliknąć przycisk **Edytuj**. Zmodyfikuj formuły dla grup **$SalesList** i **$PurchaseList** zgodnie z kodami raportowania używanymi w firmie, a następnie je zapisz. Okno projektanta formuł po lewej stronie zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować. (Więcej informacji o projektancie formatów — [Projektant formuł w raportowaniu elektronicznym](../../dev-itpro/analytics/general-electronic-reporting-formula-designer.md)). Po podzieleniu transakcji podatkowych na dwie grupy należy wewnątrz każdej grupy pogrupować transakcje dla każdego znacznika zgodnie z kodami raportowania używanymi w firmie. Znajdź pola obliczeniowe „list\_K” w grupach **$SalesList** i **$PurchaseList** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł. Po zaktualizowaniu formuł wszystkich węzłów „list\_K” odszukaj i zmodyfikuj elementy **SalasCtrl** i **PurchCtrl** odpowiednio w grupach **$SalesList** i **$PurchaseList**. Te węzły są używane odpowiednio przez znaczniki **SprzedazCtrl** i **ZakupCtrl**. Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie. Zapisz format. Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.

### <a name="generate-a-saf-vat-sales-and-purchase-register"></a>Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT

Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT, kliknij kolejno opcje **Księga główna > Zapytania i raporty > Standardowy plik audytu dla podatku (SAF-T) > Rejestr SAF sprzedaży i zakupów objętych podatkiem VAT** i ustaw następujące parametry:

|   Parametr                  |   opis                                                                      |
|------------------------------|------------------------------------------------------------------------------------|
| **Od dnia**                | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                               |
| **Do dnia**                  | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                               |
| **Identyfikacja urzędu** | Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu. |

Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.

## <a name="generate-a-saf-vat-invoices-file"></a>Generowanie pliku faktur VAT SAF

Aby można było wygenerować plik faktur VAT SAF, należy wykonać następujące dodatkowe czynności konfiguracyjne:

-   Skonfiguruj urzędy skarbowe.
-   Kody podatków dla raportowania podatku VAT.
-   Ustawianie kodów podatków.
-   Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu.

To konfigurowanie przypomina dodatkowe konfigurowanie wykonane dla rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, z wyjątkiem czynności **Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu**.

Aby poprawnie raportować niektóre z ważnych znaczników w raporcie, należy zdefiniować parametry właściwe dla aplikacji (dla wersji formatu **Faktur VAT (PL)**, począwszy od 48.36.58). 

1. Otwórz **Konfiguracje** \> **Parametry specyficzne dla aplikacji** w okienku akcji wybierz opcję **Konfiguracja**.
2. Wybierz wersję formatu, który ma być używany (na przykład **48.36.58**), a następnie ustaw wartości dla każdego wyszukiwania na liście po prawej stronie.

    | Imię i nazwisko            | Krótki opis (Angielski) | Krótki opis (Polski) | Opis (Angielski) | Opis (Polski) |
    |-----------------|-----------------------|-----------------------|-----------------|-----------------|
    | **TaxFree_LOOKUP** | Wolne od podatku | Wolne od podatku | Transakcje niepodlegające opodatkowaniu do dostarczenia towarów i usług poza krajem, zwolnione z opodatkowania. | Niepodlegające opodatkowaniu — transakcje dostawy towarów oraz świadczenia usług poza terytorium kraju; zwolnione z opodatkowania. |
    | **TaxExemptReason_LOOKUP** | Przyczyna zwolnienia z podatku | Przyczyna lub podstawa zwolnienia z podatku lub jego zmniejszenia | W przypadku dostawy towarów lub świadczenia usług, które są zwolnione z podatku zgodnie z artykułem 43 ustęp 1; Artykuł 113 sekcja 1 i 9; lub przepisy wydawane na podstawie artykułu 82, ust. 3. | W przypadku dostawy towarów lub świadczenia usług zwolnionych od podatku na podstawie art. 43 ust. 1, art. 113 ust. 1 I 9 albo przepisów wydanych na podstawie art. 82 ust. 3. |
    | **ItemType_LOOKUP** | Typ towaru | Rodzaj przedmiotu | Dostarczenie towarów używanych, dzieł sztuki, pozycji kolekcjonerskich i antyków, dla których podstawa podatkowa jest utworzona zgodnie z artykułem 120, ustęp czwarty, przypis 5. Nowe środki transportu są przedmiotem dostaw wewnątrz wspólnoty. | Dostawy towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich I antyków, dla których podstawę opodatkowania stanowi zgodnie z art. 120 ust. 4 I 5 marża; W przypadku, gdy przedmiotem wewnątrzwspólnotowej dostawy są nowe środki transportu. |

### <a name="taxfree_lookup"></a>TaxFree_LOOKUP

W JPK_FA v. 2 wartość pola **P_12** może raportować następujące wartości oprócz stawki podatkowej i **zw** (opłata zwrotna): 

- **oo** — umożliwia wycofywanie opłat w ramach transakcji krajowych
- **np** — dla transakcji związanych z dostawą towarów i świadczenia usług poza krajem

Należy skonfigurować i używać określonych kodów zwolnienia (**Podatek \> Konfiguracja \> Podatek \> Kody zwolnienia z podatku**) dla kodów podatków, które są ustawione jako zwolnione w grupach podatków (**Podatek \> Podatki pośrednie \> Podatek \> Kody zwolnienia z podatku**), aby rozróżnić transakcje podatkowe według tych kodów zwolnienia w raporcie. W celu utworzenia raportu należy zdefiniować, które kody zwolnienia muszą być raportowane przy użyciu podanych wartości znacznika **P_12**. Wybierz format **Faktury VAT (PL)**, otwórz **Konfiguracja** \> **Parametry specyficzne dla aplikacji** w okienku akcji wybierz opcję **Konfiguracja**. Aby uzyskać najnowszą wersję konfiguracji, na skróconej karcie **Wyszukiwania** wybierz opcję **TaxFree_LOOKUP**. Następnie, na **Warunkach** na skróconej karcie, zdefiniuj warunki dla następujących wyników wyszukiwania.

| Wynik wyszukiwania               | Kody zwolnienia |
|-----------------------------|--------------|
| **np**                      | Umożliwia wybór kodów zwolnienia, które są używane dla transakcji podatkowych związanych z dostawą towarów i świadczeniem usług poza krajem. Jeśli istnieje więcej niż jeden kod zwolnienia tego typu, należy dodać wiersz dla każdego dodatkowego kodu zwolnienia używanego do transakcji dostawy towarów i świadczenia usług poza krajem. |
| **zw**                      | Wybierz opcję **Nie pusty**. Wszystkie inne transakcje, które są zwolnione, ale w przypadku, gdy powód nie jest brany pod uwagę, będą raportowane jako opłaty dodatkowe w ramach transakcji krajowych. Ten wiersz musi być ostatnim wierszem na liście. Można sprawdzić, czy jest to ostatni wiersz, przeglądając wartość w kolumnie **Wiersz**. |

> [!NOTE]
> Transakcje podatkowe oznaczone jako **Opłata zwrotna** będą raportowane jako **oo**. Nie jest wymagana żadna dodatkowa konfiguracja.

Po zakończeniu konfigurowania pola wyszukiwania **TaxFree_LOOKUP** i przygotowaniu do skonfigurowania następnego pola wyszukiwania wybierz opcję **Zapisz**.

### <a name="taxexemptreason_lookup"></a>TaxExemptReason_LOOKUP

Warunki **TaxExemptReason_LOOKUP** są kodami zwolnienia z podatku zdefiniowanymi w Finance (**Podatek** \> **konfiguracja** \> **Podatek** \> **Kody zwolnienia z podatku**) i używane w grupach podatków podczas księgowania transakcji podatkowych. Jeśli na fakturze nie ma żadnych wierszy zwolnienia z podatku, w polu **P_19** będzie raportowana wartość **fałsz**, a znaczniki **P_19A**, **P_19B** i **P_19C** zostaną pominięte.

- **P_19A** wskazuje, że dany akt został wystawiony, na podstawie którego podatnik stosuje zwolnienie z podatku.
- **P_19B** wskazuje przepis dyrektywy 2006/112/WE, który zwalnia dostawę towarów lub takich usług z takiego podatku.
- **P_19C** wskazuje inną podstawę prawną, która wskazuje, że dostawa towarów lub usług przynosi korzyści z wyłączenia.

Po zakończeniu konfigurowania pola wyszukiwania **TaxExemptReason_LOOKUP** i przygotowaniu do skonfigurowania następnego pola wyszukiwania wybierz opcję **Zapisz**.

### <a name="itemtype_lookup"></a>ItemType_LOOKUP

Pole wyszukiwania **ItemType_LOOKUP** zostało wprowadzone w wersji 48.36.58 (bieżąca KB) formatu **faktury VAT (PL)**.

Dostępne do konfiguracji są następujące wartości:

| Imię i nazwisko | Opis (Angielski) | Opis (Polski) | Konfiguracja |
|------|------------------|------------------|-------|
| **SecondHandGoods** | Dostawy towarów używanych, dla których podstawę opodatkowania stanowi art. 120 ust. 4, przypis piąty | Dostawy towarów używanych dla których podstawę opodatkowania stanowi zgodnie z art. 120 ust. 4 i 5 marża | Umożliwia określenie kodów podatków używanych w transakcjach powiązanych z towarami używanymi w danym magazynie. Po zakończeniu tego ustawienia faktura zawierająca transakcje podatkowe, w której używany jest określony **procedura marży — towary używane** kod podatku będzie raportowana w **P_106E_3A**. |
| **ArtWorks** | Dostawy dzieł sztuki, dla których podstawę opodatkowania stanowi art. 120 ust. 4, przypis piąty | Dostawy dzieł sztuk dla których podstawę opodatkowania stanowi zgodnie z art. 120 ust. 4 i 5 marża | Umożliwia określenie kodów podatków używanych w transakcjach powiązanych z dziełami sztuki. Po zakończeniu tego ustawienia faktura zawierająca transakcje podatkowe, w której używany jest określony **procedura marży — dzieła sztuki** kod podatku będzie raportowana w **P_106E_3A**. |
| **CollectorAntiques** | Dostawy przedmiotów kolekcjonerskich i antyków, dla których podstawę opodatkowania stanowi zgodnie z art. 120, ustęp czwarty, przypis piąty | Dostawy przedmiotów kolekcjonerskich i antyków, dla których podstawę opodatkowania stanowi zgodnie z art. 120 ust. 4 i 5 marża | Umożliwia określenie kodów podatków używanych w transakcjach powiązanych z przedmiotami kolekcjonerskimi i antykami. Po zakończeniu tego ustawienia faktura zawierająca transakcje podatkowe, w której używany jest określony **procedura marży — przedmioty kolekcjonerskie i antyki** kod podatku będzie raportowana w **P_106E_3A**. |
| **Transport** | Wewnątrzwspólnotowe dostarczanie nowych środków transportu | Wewnątrzwspólnotowa dostawa nowych środków transportu | Umożliwia określenie kodów podatków używanych w transakcjach powiązanych z wewnątrzwspólnotowym dostawą nowych środków transportu. Po zakończeniu tego ustawienia faktura zawierająca transakcje podatkowe, w której używany jest określony kod podatku **P_22** będzie raportowany z wartością **Prawda**. |
| **Inna** | Inna | Inne | Należy określać wartość **Nie puste** w polu **Kod zwolnienia z podatku**. Ta wartość musi być ostatnią na liście wartości. Ta wartość musi być obowiązkowa dla tego wyszukiwania. |

Po zakończeniu konfigurowania wartości pól wyszukiwania określ pole **Stan** jako **Zakończone**, a następniezapisz zmiany i zamknij stronę. Jeśli dowolne pole wyszukiwania nie zawiera co najmniej jednej wartości **Nie puste**, podczas uruchamiania raportu zostanie wygenerowany błąd. Komunikat o błędzie będzie zawierać informację o braku parametrów specyficznych dla aplikacji.

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

### <a name="implementation-details"></a>Szczegóły implementacji

W wersji 3 raportu **JPK_FA** faktury z różnymi walutami dokumentów mogą być raportowane w tym samym pliku. W tym celu parametr **Waluty** w oknie dialogowym dla raportu **SAF faktury VAT (Polska)** jest opcjonalny. W przypadku określenia waluty raport będzie zawierał tylko faktury o tej samej walucie. Jeśli waluta nie zostanie określona, raport będzie generowany dla wszystkich faktur.

#### <a name="p_14x-tags"></a>Znaczniki <P_14x>

Zgodnie z wymaganiami wersji 3 raportu **JPK_FA**, gdy faktura jest księgowana w walucie innej niż **PLN**, znaczniki **<P_13x>**, **<P_14x>** i **<P_15>** muszą reprezentować kwoty w walucie faktury, a nowe znaczniki **<P_14xW>** muszą reprezentować kwoty powiązane w walucie **PLN**. Przyjmuje się, że wartość **PLN** jest definiowana jako waluta dla kodów podatków używanych w transakcjach, które zostaną uwzględnione w raporcie **JPK_FA**. Na podstawie tego założenia dla faktur, dla których waluta dokumentu różni się od waluty ustawionej w kodach podatków używanych w transakcjach podatkowych tego dokumentu, system zgłasza dodatkowe znaczniki **<P_14xW>** z kwotą w walucie kodu podatku (ponieważ zakłada się, że waluta jest wyrażona w **PLN**).

#### <a name="p_18a-tag"></a>Znacznik <P_18A>

KB #4339927 („Specjalna aktualizacja kraju dla Polski o podzielonej płatności w aplikacjach Dynamics 365 for Finance and Operations”) wprowadza ustawienia metod płatności jako podzielone płatności w module **Rozrachunki z odbiorcami**.

Zgodnie z wymaganiami wersji 3 raportu **JPK_FA**, znacznik **<P_18A>** dla faktury musi być raportowany jako **Prawda**, jeśli dla tej faktury jest stosowany mechanizm podziału płatności. Aby określić, czy mechanizm podziału płatności został zastosowany dla faktury, system sprawdza parametr **Podziału płatności**, który został użyty podczas księgowania faktury i jest widoczny w odpowiedniej transakcji odbiorcy w tabeli CustTrans. Ważne jest, aby zachować konfigurację parametru **Podziału płatności** dla metod płatności stabilnych w celu zapewnienia prawidłowego raportowania.

#### <a name="p_22-tag"></a>Znacznik <P_22>

Znacznik **<P_22>** będzie raportowany z wartością **Prawda** zgodnie z konfiguracją kodów podatków w **ItemType_LOOKUP**, gdzie **Result** = **Transport** w parametrach określonych dla aplikacji w formacie **faktur VAT (PL)**.

#### <a name="p_106e_3-and-p_106e_3a-tags"></a>Znaczniki <P_106E_3> i <P_106E_3A>

Zgodnie z wymogami raportu **JPK_FA** znacznik **<P_106E_3>** musi raportować wartość **Prawda** w przypadku dostawy towarów używanych, dzieł sztuki, przedmiotów kolekcjonerskich i antyków, dla których podstawa opodatkowania jest zgodna z art. 120 ust. 5 ust. Gdy zostanie zaraportowany znacznik **<P_106E_3>** o wartości **Prawda**, znacznik **<P_106E_3A>** musi reprezentować powiązane wartości.

| Wartość znacznika <P_106E_3A> | Opis (Polski) | Opis (Angielski) | Sposób, w jaki Finance odróżnia znacznik |
|--------|--------------------|------------------|-------|
| **procedura marży — towary używane** | Dostawy towarów używanych dla których podstawę opodatkowania stanowi zgodnie z art. 120 ust. 4 i 5 marża | Dostawy towarów używanych, dla których podstawę opodatkowania stanowi art. 120 ust. 4, przypis piąty | Zgodnie z konfiguracją kodów podatków w **ItemType_LOOKUP**, gdzie **Result** = **SecondHandGoods** w parametrach właściwych dla danej aplikacji w formacie **faktur VAT (PL)** | 
| **procedura marży - dzieła sztuki** | Dostawy dzieł sztuki, przedmiotów kolekcjonerskich i antyków, dla których podstawę opodatkowania stanowi zgodnie z art. 120 ust. 4 i 5 marża | Dostawy dzieł sztuki, dla których podstawę opodatkowania stanowi art. 120 ust. 4, przypis piąty | Zgodnie z konfiguracją kodów podatków w **ItemType_LOOKUP**, gdzie **Result** = **ArtWorks** w parametrach właściwych dla danej aplikacji w formacie **faktur VAT (PL)** |
| **procedura marży - przedmioty kolekcjonerskie i antyki** | Dostawy przedmiotów kolekcjonerskich i antyków, dla których podstawę opodatkowania stanowi zgodnie z art. 120 ust. 4 i 5 marża | Dostawy przedmiotów kolekcjonerskich i antyków, dla których podstawę opodatkowania stanowi zgodnie z art. 120, ustęp czwarty, przypis piąty | Zgodnie z konfiguracją kodów podatków w **ItemType_LOOKUP**, gdzie **Result** = **CollectorAntiques** w parametrach właściwych dla danej aplikacji w formacie **faktur VAT (PL)** |

#### <a name="zamowienie-and-zamowieniectrl-nodes"></a>Węzły zamowienie i ZamowienieCtrl

Zgodnie z wymaganiami wersji 3 raportu **JPK_FA**, węzeł **Zamowienie** musi reprezentować zamówienia lub umowy określone w artykule 106f, ustęp 1, pozycja 4 aktu (dla faktur zaliczkowych) w walucie, w której wystawiono fakturę zaliczkową (zamówienia lub umowy, o których mowa w art.) 106f ust. 1 pkt 4 ustawy (dla faktur zaliczkowych) w walucie, w której wystawiono fakturę zaliczkową).

Aby wykonać to wymaganie, system gromadzi informacje z bazy danych dla wierszy zamówień sprzedaży i faktur niezależnych, które są połączone z fakturami zaliczkowymi uwzględnionymi w raporcie, oraz dostarcza z nich następujących informacji.

| Nazwa znacznika | Opis (Polski) | Opis (Angielski) | Sposób zbierania informacji przez Finance |
|--------|--------------------|------------------|-------|
| **P_7Z** | Nazwa (rodzaj) towaru lub usługi | Nazwa (rodzaj) towaru lub usługi | Wartość przechowywana w wierszu zamówienia sprzedaży lub faktury niezależnej w bazie danych Finance |
| **P_8AZ** | Miara zamówionego towaru lub zakres usługi | Jednostka miary zamówionego towaru lub zakresu usługi | Wartość jednostka miary przechowywana w wierszu zamówienia sprzedaży lub faktury niezależnej w bazie danych Finance (Jeśli pole jest puste, zostanie użyta opcja „usługa”). |
| **P_8BZ** | Ilość zamówionego towaru lub zakres usługi | Ilość zamówionych towarów lub zakres usługi | Wartość ilości w wierszu zamówienia sprzedaży lub faktury niezależnej w bazie danych Finance |
| **P_9AZ** | Cena jednostkowa netto | Cena jednostkowa netto | Wartość ceny w wierszu zamówienia sprzedaży lub faktury niezależnej w bazie danych Finance |
| **P_11NettoZ** | Wartość zamówionego towaru lub usługi bez kwoty podatku | Wartość zamówionych towarów lub usług bez kwoty podatku | Wartość kwoty podstawy podatku, która jest obliczana dla wiersza zamówienia sprzedaży lub faktury niezależnej, na podstawie ilości przechowywanej w wierszu (**P_8BZ)**. |
| **P_11VatZ** | Kwota podatku od zamówionego towaru lub usługi | Kwota podatku od zamówionego towaru lub usługi | Wartość kwoty podatku, która jest obliczana dla wiersza zamówienia sprzedaży lub faktury niezależnej, na podstawie ilości przechowywanej w wierszu (**P_8BZ)**. |
| **P_12Z** | Stawka podatku | Stawka podatkowa | Obliczona wartość stawki podatku na podstawie konfiguracji podatku w wierszu zamówienia sprzedaży lub faktury niezależnej (Grupa podatków i Grupa podatków dla towaru). |

W odniesieniu do wartości raportowanych dla wierszy zamówień sprzedaży lub faktur niezależnych wartość w znaczniku **WartoscZamowienia** węzła **Zamowienie** jest obliczana jako suma wartości obliczonych dla kwoty podstawy podatku oraz kwoty podatku (**P_11NettoZ** + **P_11VatZ**) dla wszystkich wierszy dokumentu.

Wartość znacznika **WartoscZamowien** węzła **ZamowienieCtrl** jest obliczana jako suma wartości znacznika **WartoscZamowienia** dla wszystkich dokumentów raportowanych w węźle **Zamowienie**.

## <a name="using-batch-jobs-for-saft"></a>Używanie zadań wsadowych dla raportów SAFT

Generowanie raportów SAF-T za długi okres, taki jak miesiąc lub kwartał, może powodować objęcie bardzo dużej ilości danych i zajmować dużo czasu. W takich przypadkach zaleca się używanie zadań wsadowych. Okno dialogowe dla każdego raportu SAF-T zawiera kartę **Uruchom w tle**. Otwórz tę kartę, aby ustawić generowanie raportu w trybie wsadowym. Zaznacz pole wyboru **Przetwarzanie wsadowe**. Aby uzyskać więcej informacji na temat przetwarzania wsadowego, zobacz temat [Omówienie przetwarzania wsadowego](../../dev-itpro/sysadmin/batch-processing-overview.md). Aby przejrzeć zadania wsadowe lub znaleźć wygenerowany plik, otwórz okno **Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Zadania raportowania elektronicznego** i znajdź wiersz związany z zadaniem. W **menu głównym** kliknij przycisk **Pokaż dziennik**. Jeżeli nic nie jest wyświetlane, oznacza to, że podczas generowania pliku nie zostały utworzone żadne komunikaty. Aby zobaczyć plik, w **menu głównym** kliknij przycisk **Pokaż pliki**, znajdź żądany plik i w **menu głównym** kliknij przycisk **Otwórz**.  

