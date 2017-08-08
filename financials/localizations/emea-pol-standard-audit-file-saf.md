---
title: Standardowy plik audytu (SAF) dla Polski
description: "Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten temat zawiera informacje o formatach dla Polski."
author: LizaGolub
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 274193
ms.assetid: b85c4019-f682-45bf-9a0d-c7549a2f1274
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 78b273b89e26073d4c979413786b3844dad17418
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---

# <a name="standard-audit-file-saf-for-poland"></a>Standardowy plik audytu (SAF) dla Polski

Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten temat zawiera informacje o formatach dla Polski. 

Użytkownicy w firmach w Polsce mogą generować standardowe plik audytu dla podatku (SAF-T) w formacie XML. Ten dokument zawiera informacje o formatach dla Polski. Niniejszy dokument odnosi się do funkcji, która nie została jeszcze wdrożona.

## <a name="set-up-the-standard-audit-file-for-tax-for-poland"></a>Konfigurowanie standardowego pliku audytu dla podatku dla Polski
Aby określić format raportowania elektronicznego (ER) dla każdego schematu SAF-T, kliknij przycisk kolejno opcje **Księga główna** &gt; **Ustawienia księgi** &gt; **Parametry księgi głównej**, a następnie na karcie **Standardowy plik audytu dla podatków (SAF-T)** skonfiguruj konkretne formaty dla każdego z następujących schematów:

-   Księgi księgowania SAF
-   Wyciągi bankowe SAF
-   Zapasy SAF
-   Rejestry SAF zakupów i sprzedaży objętych podatkiem VAT
-   Faktury VAT SAF

Każdy format raportowania elektronicznego powinien być wstępnie zdefiniowany i pozwalać na aktualizowanie w module Raportowanie elektroniczne.

## <a name="generate-a-saf-accounting-books-file"></a>Generowanie pliku ksiąg księgowania SAF
Aby wygenerować plik ksiąg księgowania SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Księgi księgowania SAF** i ustaw następujące parametry:

|                                                 |                                                                                                                                                            |
|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Parametr**                                   | **Opis**                                                                                                                                            |
| **Od dnia**                                   | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                                                                                                       |
| **Do dnia**                                     | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                                                                                                        |
| **Identyfikacja urzędu**                    | Określ identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.                                                                                     |
| **Warstwa księgowania**                               | Umożliwia wybranie warstwy księgowania, od której mają być uwzględniane transakcje. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.                                     |
| **Czy saldo otwarcia ma być pokazywane jako obroty?** | Jeśli ten parametr jest zaznaczony, transakcje otwarcia mają wpływ na obroty narastająco. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.                    |
| **Saldo rozwarte**                            | Ten parametr można włączać dla kont głównych, w których jest oznaczony odnośny parametr. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu.     |
| **Transakcje zamknięcia**                        | Jeśli ten parametr jest zaznaczony, transakcje zamknięcia będą uwzględnione w eksportowanych danych. Ten parametr dotyczy tylko sekcji ZOiS w pliku eksportu. |

Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.

## <a name="generate-a-saf-bank-statement-file"></a>Generowanie pliku wyciągu bankowego SAF
Aby wygenerować plik wyciągu bankowego SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Wyciąg bankowy SAF** i ustaw następujące parametry:

|                              |                                                                                    |
|------------------------------|------------------------------------------------------------------------------------|
| **Parametr**                | **Opis**                                                                    |
| **Od dnia**                | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                               |
| **Do dnia**                  | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                                |
| **Identyfikacja urzędu** | Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu. |
| **Konto bankowe**             | Umożliwia określenie rachunku bankowego, dla którego mają zostać wyeksportowane transakcje.                               |

 

## <a name="generate-a-saf-inventory-file"></a>Generowanie pliku zapasów SAF
Aby wygenerować plik zapasów SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Zapasy SAF** i ustaw następujące parametry:

|                              |                                                                                    |
|------------------------------|------------------------------------------------------------------------------------|
| **Parametr**                | **Opis**                                                                    |
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

Aby uzyskać ogólne informacje dotyczące sposobu konfigurowania urzędu skarbowego, zobacz [Konfigurowanie urzędów skarbowych (przewodnik po zadaniu)](/dynamics365/unified-operations/financials/general-ledger/tasks/set-up-sales-tax-authorities). Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT w wymaganym formacie dla odpowiedniego urzędu skarbowego, należy zdefiniować układ raportu dla urzędów skarbowych. Na stronie **Urzędy skarbowe** (**Podatek** &gt; **Podatki pośrednie** &gt; **Podatek** &gt; **Urzędy skarbowe**) w polu **Układ raportu** zaznacz wartość **Domyślnie**. Zaznacz ten sam urząd skarbowy dla okresu rozliczeniowego podatku, który będzie używany dla kodów podatków.

### <a name="set-up-sales-tax-codes-and-sales-tax-reporting-codes"></a>Konfigurowanie kodów podatków i kodów sprawozdawczości podatkowej

Kod raportowania jest liczbą całkowitą. Kody raportowania powinny być numerowane zgodnie z regułami obowiązującymi w firmie. Jednak zalecamy, aby różnicować kody według kierunku podatku. Na przykład zdefiniuj kod 5-cyfrowy i tak ustaw kody dla wszystkich transakcji wychodzących, które powinny być odzwierciedlane w pierwszej części schematu podatku VAT, aby były mniejsze lub równe 19999. Natomiast dla wszystkich transakcji przychodzących, które powinny być wykazywane w drugiej części systemu podatku VAT, ustaw kody tak, aby były większe lub równe 20000. W ten sposób uprościsz konfigurację raportów i eksportu danych, która opiera się na transakcjach podatkowych agregowanych według kodów raportowania. Oto przykład pokazujący użycie kodów sprawozdawczości podatkowej do generowania rejestru SAF sprzedaży i zakupów objętych podatkiem VAT. W tym przykładzie kody raportowania są w formacie *ABBCC*. Ten format składa się z następujących elementów:

-   **A** — Kierunek transakcji. Wartość wynosi **1** dla podatków wychodzących, **2** dla podatków przychodzących i **3** dla korekt.
-   **BB** — Kod podatku. Numeracja zachowuje kolejność wśród wszystkich kodów podatków.
-   **CC** — Numer typu transakcji wewnątrz kodu podatku. Parz tabela poniżej.

|                                       |                             |
|---------------------------------------|-----------------------------|
| **Typ transakcji**                  | **Numer typu transakcji** |
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

**Kod podatku**

**Kod raportowania podatku**

**Opis**

**Nazwa znacznika w podatku VAT SAF-T**

**Znak w podatku VAT SAF-T**

**ExportCust**

10101

Sprzedaż opodatkowana

K\_11

-

10102

Sprzedaż wolna od podatku

K\_11

-

10104

Opodatkowana faktura korygująca sprzedaży

K\_11

-

10105

Faktura korygująca sprzedaży zwolnionej z podatku

K\_11

-

**Art100**

10201

Sprzedaż opodatkowana

K\_12

-

10204

Opodatkowana faktura korygująca sprzedaży

K\_12

-

**VAT22\_23**

10301

Sprzedaż opodatkowana

K\_19

-

10302

Sprzedaż wolna od podatku

K\_10

-

10303

Podatek należny

K\_20

-

10304

Opodatkowana faktura korygująca sprzedaży

K\_19

-

10306

Podatek od faktury korygującej sprzedaży

K\_20

-

**VAT7\_8**

10401

Sprzedaż opodatkowana

K\_17

-

10402

Sprzedaż wolna od podatku

K\_10

-

10403

Podatek należny

K\_18

-

10404

Opodatkowana faktura korygująca sprzedaży

K\_17

-

10406

Podatek od faktury korygującej sprzedaży

K\_18

-

**VAT5**

10501

Sprzedaż opodatkowana

K\_15

-

10502

Sprzedaż wolna od podatku

K\_10

-

10503

Podatek należny

K\_16

-

10504

Opodatkowana faktura korygująca sprzedaży

K\_15

-

10506

Podatek od faktury korygującej sprzedaży

K\_16

-

**VAT0**

10601

Sprzedaż opodatkowana

K\_13

-

10602

Sprzedaż wolna od podatku

K\_10

-

10604

Opodatkowana faktura korygująca sprzedaży

K\_13

-

**ART129**

10701

Sprzedaż opodatkowana

K\_14

-

10702

Sprzedaż wolna od podatku

K\_14

-

10704

Opodatkowana faktura korygująca sprzedaży

K\_14

-

10705

Faktura korygująca sprzedaży zwolnionej z podatku

K\_14

-

**IntraEUGoods**

10801

Sprzedaż wolna od podatku

K\_21

-

10810

Import opodatkowany

K\_23

+

10812

Podatek nienaliczony

K\_24

+

**ExportOfGoods**

10901

Sprzedaż wolna od podatku

K\_22

-

10905

Faktura korygująca sprzedaży zwolnionej z podatku

K\_22

-

**ImportOfGoodsART33**

20207

Import opodatkowany

K\_45

+

11010

Przeciwstawna wartość importu podlegająca opodatkowaniu

K\_25

-

20209

Podatek nienaliczony

K\_46

+

11012

Konto przeciwstawne podatku nienaliczonego

K\_26

-

**ImportOfServices**

20207

Import opodatkowany

K\_45

+

11110

Przeciwstawna wartość importu podlegająca opodatkowaniu

K\_27

-

20209

Podatek nienaliczony

K\_46

+

11112

Konto przeciwstawne podatku nienaliczonego

K\_28

-

**ImportART28**

20207

Import opodatkowany

K\_45

+

11210

Przeciwstawna wartość importu podlegająca opodatkowaniu

K\_29

-

20209

Podatek nienaliczony

K\_46

+

11212

Konto przeciwstawne podatku nienaliczonego

K\_30

-

**ReverseCharge**

11301

Sprzedaż opodatkowana

K\_31

-

11302

Podatek należny

K\_35

-

11304

Opodatkowana faktura korygująca sprzedaży

K\_31

-

11306

Podatek od faktury korygującej sprzedaży

K\_35

-

**FixedAssetPurch**

20107

Zakup podlegający opodatkowaniu

K\_43

+

20109

Podatek naliczony

K\_44

+

20115

Opodatkowana faktura korygująca zakupu

K\_43

+

20116

Podatek od faktury korygującej zakupu

K\_47

+

**GoodServPurch**

20207

Zakup podlegający opodatkowaniu

K\_45

+

20209

Podatek naliczony

K\_46

+

20215

Opodatkowana faktura korygująca zakupu

K\_45

+

20216

Podatek od faktury korygującej zakupu

K\_48

+

**CorrATR89b1**

30101

Podatek należny

K\_49

+

30109

Podatek naliczony

K\_49

+

**CorrATR89b4**

30201

Podatek należny

K\_50

+

30209

Podatek naliczony

K\_50

+

### <a name="configure-the-er-model-and-format-for-the-report"></a>Konfigurowanie modelu i formatu raportowania elektronicznego dla raportu

Aby przejrzeć lub zmodyfikować konfigurację rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** na liście modeli zaznacz model **Standardowy plik audytu (SAF-T)**. Następnie kliknij przycisk **Projektant** i przejrzyj lub zmodyfikuj model. Aby przejrzeć lub zmodyfikować format rejestru SAF sprzedaży i zakupów objętych podatkiem VAT, na stronie **Konfiguracje raportowania** w obszarze **Standardowy plik audytu (SAF-T)** zaznacz opcję **Rejestr VAT (PL)** i kliknij przycisk **Projektant**. Aby uzyskać więcej informacji o raportowaniu elektronicznym, zobacz następujące tematy:

-   [Omówienie Raportowania elektroniczne](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting)
-   [Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)
-   [Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego](/dynamics365/unified-operations/dev-itpro/analytics/electronic-reporting-configuration)

Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej. Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji. W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**. Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**. Utworzony format jest kopią formatu nadrzędnego. Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania. Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane). Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**. Model danych zawiera wszystkie pola wszystkich raportów SAF-T. Format rejestru VAT jest mapowany głównie do węzła **TaxTransaction**. Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł. Wszystkie transakcje podatkowe są podzielone na dwie grupy: według znacznika **SprzedazWiersz** i według znacznika **ZakupWiersz**. Oraz zatytułowane odpowiednio **$SalesList** i **$PurchaseList**. Są to listy rekordów obliczane (filtrowane) według formuł. Formuły można przeglądać i modyfikować w redaktorze formuł. W tym celu należy zaznaczyć pole obliczeniowe lub listę rekordów (w tym konkretnym przypadku), a następnie w menu drzewa kliknąć przycisk **Edytuj**. Zmodyfikuj formuły dla grup **$SalesList** i **$PurchaseList** zgodnie z kodami raportowania używanymi w firmie, a następnie je zapisz. Okno projektanta formuł po lewej stronie zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować. (Więcej informacji o projektancie formatów — [Projektant formuł w raportowaniu elektronicznym](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting-formula-designer)). Po podzieleniu transakcji podatkowych na dwie grupy należy wewnątrz każdej grupy pogrupować transakcje dla każdego znacznika zgodnie z kodami raportowania używanymi w firmie. Znajdź pola obliczeniowe „list\_K” w grupach **$SalesList** i **$PurchaseList** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł. Po zaktualizowaniu formuł wszystkich węzłów „list\_K” odszukaj i zmodyfikuj elementy **SalasCtrl** i **PurchCtrl** odpowiednio w grupach **$SalesList** i **$PurchaseList**. Te węzły są używane odpowiednio przez znaczniki **SprzedazCtrl** i **ZakupCtrl**. Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie. Zapisz format. Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.

### <a name="generate-a-saf-vat-sales-and-purchase-register"></a>Generowanie rejestru SAF sprzedaży i zakupów objętych podatkiem VAT

Aby wygenerować rejestr SAF sprzedaży i zakupów objętych podatkiem VAT, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Rejestr SAF sprzedaży i zakupów objętych podatkiem VAT** i ustaw następujące parametry:

|                              |                                                                                    |
|------------------------------|------------------------------------------------------------------------------------|
| **Parametr**                | **Opis**                                                                    |
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

-   [Omówienie Raportowania elektroniczne](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting)
-   [Pobieranie konfiguracji Raportowania elektronicznego z usługi Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs)
-   [Wymagania dotyczące tłumaczenia — Tworzenie konfiguracji raportowania elektronicznego](/dynamics365/unified-operations/dev-itpro/analytics/electronic-reporting-configuration)

Początkowo konfiguracja jest przykładem rejestru VAT opartego na kodach raportowania opisanego w tabeli powyżej. Jeśli trzeba zaadaptować konfigurację do innego zestawu kodów raportowania, należy utworzyć pochodny format konfiguracji. W tym celu zaznacz format w drzewie konfiguracji, a następnie w **menu głównym** kliknij przycisk **Utwórz konfigurację**. Zaznacz opcję **Pochodna od nazwy:**, wypełnij pola **Nazwa** i **Opis** dotyczące nowego formatu, a następnie kliknij przycisk **Utwórz konfigurację**. Utworzony format jest kopią formatu nadrzędnego. Zaznacz utworzony format i w **menu głównym** kliknij przycisk **Projektant**, aby otworzyć projektanta formatów i zaktualizować format o żądane kody raportowania. Okno projektanta formatów jest podzielone na dwie części: lewa strona zawiera strukturę formatu (w przypadku rejestru VAT jest to schemat XML), a prawa strona zawiera model danych (dane). Po prawej stronie naciśnij przycisk **Mapowanie**, a zostanie wyświetlone okienko **Model danych**. Model danych zawiera wszystkie pola wszystkich raportów SAF-T. Format **Faktury VAT** składa się z kilku sekcji z różnymi źródłami danych. Dane pod znacznikiem **Faktura** są mapowane głównie do węzła **Model &gt; SourceDocuments &gt; $Invoices**. Przewiń drzewo w dół i poszukaj oraz zaznacz ten węzeł. Znajdź pola obliczeniowe **list\_P\_** w węźle **$Invoices** i zaktualizuj ich formuły o swoje kody raportowania przy użyciu projektanta formuł. Okno projektanta formuł zawiera model danych, gdzie można wybrać pola lub listy rekordów, natomiast z prawej strony zawiera wszystkie funkcje, które można implementować. Aby uzyskać więcej informacji o projektancie formatów, zobacz [Projektant formuł w raportowaniu elektronicznym](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting-formula-designer). Wartości znaczników pod znacznikiem **StawkiPodatku** są stałe. Zaznacz węzeł wartości (ciąg) dla każdego znacznika pod znacznikiem **StawkiPodatku** i ustaw mu wartość w polu **Wartość** na karcie **Format** z prawej strony okna **Projektant**. Zasadniczo nie trzeba wprowadzać żadnych innych zmian w formacie. Zapisz format. Zamknij okno i dokończ konfigurowanie formatu za pomocą przycisku **Zmień stan** &gt; **Zakończ** umieszczonego w menu wersji na skróconej karcie **Wersji** w oknie **Konfiguracje**.

### <a name="generate-a-saf-vat-invoices"></a>Generowanie faktur VAT SAF

Aby wygenerować plik faktur VAT SAF, kliknij kolejno opcje **Księga główna** &gt; **Zapytania i raporty** &gt; **Standardowy plik audytu dla podatku (SAF-T)** &gt; **Faktury VAT SAF** i ustaw następujące parametry:

|                              |                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------|
| Parametr                    | opis                                                                            |
| **Od dnia**                | Umożliwia określenie pierwszego dnia zakresu eksportowania danych sprawozdawczych.                                   |
| **Do dnia**                  | Umożliwia określenie ostatniego dnia zakresu eksportowania danych sprawozdawczych.                                    |
| **Identyfikacja urzędu** | Na liście zaznacz identyfikator urzędu skarbowego, który ma być używany w pliku eksportu.     |
| **Identyfikator faktury Od/Do**     | Określ zakres identyfikatorów faktur, aby ograniczyć ilość faktur wybieranych dla eksportu danych. |

Dodatkowe parametry wyboru można określić za pomocą funkcji **Filtr** na karcie **Rekordy do uwzględnienia**.

## <a name="using-batch-jobs-for-saft"></a>Używanie zadań wsadowych dla raportów SAFT
Generowanie raportów SAF-T za długi okres, taki jak miesiąc lub kwartał, może powodować objęcie bardzo dużej ilości danych i zajmować dużo czasu. W takich przypadkach zaleca się używanie zadań wsadowych. W oknie dialogowym strona każdego raportu SAF-T zawiera kartę **Uruchom w tle**. Po otwarciu tej karty można skonfigurować generowanie raportu w trybie wsadowym. Zaznacz pole wyboru **Przetwarzanie wsadowe**. Aby uzyskać więcej informacji na temat przetwarzania wsadowego, zobacz temat [Omówienie przetwarzania wsadowego](/dynamics365/unified-operations/dev-itpro/sysadmin/batch-processing-overview). Aby przejrzeć zadania wsadowe lub znaleźć wygenerowany plik, otwórz okno **Administrowanie organizacją** &gt; **Raportowanie elektroniczne** &gt; **Zadania raportowania elektronicznego** i znajdź wiersz związany z zadaniem. W **menu głównym** kliknij przycisk **Pokaż dziennik**. Jeżeli nic nie jest wyświetlane, oznacza to, że podczas generowania pliku nie zostały utworzone żadne komunikaty. Aby zobaczyć plik, w **menu głównym** kliknij przycisk **Pokaż pliki**, znajdź żądany plik i w **menu głównym** kliknij przycisk **Otwórz**.  


