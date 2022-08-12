---
title: Omówienie rozliczeń w płatnościach scentralizowanych
description: W tym artykule opisano rozliczanie scentralizowanych płatności w Microsoft Dynamics 365 Finance.
author: angelad116
ms.date: 08/02/2018
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "222414"
- intro-internal
ms.assetid: 610f6858-0f37-4d0f-8c68-bab5a971ef4a
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef71520df5cdae192355e512238d03c1f21b901f
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151184"
---
# <a name="settlement-overview-for-centralized-payments"></a>Omówienie rozliczeń w płatnościach scentralizowanych

[!include [banner](../includes/banner.md)]

Organizacje obejmujące wiele firm mogą tworzyć i zarządzać płatnościami za pomocą firmy, która obsługuje wszystkie płatności. Eliminuje to konieczność wprowadzania tej samej transakcji w wielu firmach i zapewnia oszczędność czasu dzięki usprawnieniu procesów propozycji płatności i rozrachunku oraz edycji otwartych i zamkniętych transakcji w przypadku płatności scentralizowanych. 

Po wprowadzeniu płatności odbiorcy lub dostawcy w jednej firmie i po rozliczeniu jej na fakturze wprowadzonej w innej firmie dla każdej z tych firm są automatycznie generowane odpowiednie rozliczenie oraz transakcje „należne od” i „należne do”. Jest tworzony rekord rozliczenia dla każdej kombinacji faktury i płatności w transakcji. Każdemu rekordowi rozliczenia jest przypisywany nowy numer załącznika, który bazuje na numeracji załączników płatności określonej na stronie **Parametry modułu rozrachunków z odbiorcami** dla odbiorców i na stronie **Parametry modułu rozrachunków z dostawcami** dla dostawców. 

Jeśli są generowane dodatkowe rekordy rozliczenia dla rabatów gotówkowych, przeszacowań w walucie obcej, różnic groszowych, nadpłat i niedopłat, to jest im przypisywana późniejsza data transakcji faktury lub płatności. Jeśli rozliczenie następuje po zaksięgowaniu płatności, to w odniesieniu do rekordów rozliczenia jest używana data księgowania rozliczenia określona na stronie **Rozliczanie otwartych transakcji**.

## <a name="posting-types-transaction-types-and-default-descriptions"></a>Typy księgowania, typy transakcji i domyślne opisy

Transakcje w załączniku rozliczeń międzyfirmowych wykorzystują typ księgowania Rozliczenie międzyfirmowe, rozliczenie z odbiorcą międzyfirmowym oraz typy transakcji Rozliczenie z dostawcą międzyfirmowym. Na stronie **Opisy domyślne** można skonfigurować dane typu transakcji. 

Oto typy transakcji dostępne do użycia zarówno w wypadku rozliczeń w ramach jednej firmy, jak i rozliczeń międzyfirmowych:

-   Miejscowość
-   Rabat gotówkowy
-   Przeszacowania w walucie obcej (obejmuje zrealizowane i niezrealizowane przeszacowania w walucie obcej)
-   Różnice groszowe
-   Nadpłata/niedopłata

Można także zdefiniować domyślne opisy dla załączników rozliczeń międzyfirmowych.

## <a name="currency-exchange-gains-or-losses"></a>Zyski i straty związane z wymianą walut

Kurs wymiany stosowany w transakcjach odbiorcy lub dostawcy jest przechowywany razem z transakcją. Zrealizowane dodatnie lub ujemne różnice kursowe są księgowane w firmie wystawiającej fakturę lub firmie dokonującej płatności, w zależności od opcji wybranej w polu **Zaksięguj zyski lub straty związane z wymianą walut** na stronie **Księgowanie międzyfirmowe** dla firmy dokonującej płatności. W poniższych przykładach użyto następujących walut:
-   Waluta rozliczeniowa płatności: EUR
-   Waluta rozliczeniowa faktury: USD
-   Waluta transakcji płatności: DKK
-   Waluta transakcji fakturowania: CAD

### <a name="currency-calculations"></a>Obliczenia walutowe

W wypadku rozliczania faktury wprowadzonej w jednej firmie z płatnością wprowadzoną w drugiej firmie waluta transakcji płatności (DKK) jest konwertowana w trzech krokach:
1.  Konwersja na walutę rozliczeniową płatności (EUR) przy użyciu kursów wymiany firmy dokonującej płatności.
2.  Konwersja na walutę rozliczeniową faktury (USD).
3.  Konwersja na walutę transakcji właściwą dla faktury (CAD) przy użyciu kursów wymiany firmy wystawiającej fakturę.

W ramach konwersji są używane kursy wymiany aktualne w dniu płatności. Jeśli wynikowa kwota płatności w walucie transakcji faktury (CAD) jest równa kwocie faktury (CAD), to faktura jest uznawana za w pełni zapłaconą. 

W wypadku otwarcia strony **Rozliczanie otwartych transakcji** z arkusza płatności, w którym nie wprowadzono kwoty płatności, kwota do rozliczenia jest obliczana na podstawie faktur wybranych do rozliczenia na stronie **Rozliczanie otwartych transakcji**. Konwersja kwoty do rozliczenia jest wykonywana w trzech krokach:
1.  Konwersja na walutę rozliczeniową faktury (USD) przy użyciu kursów wymiany firmy wystawiającej fakturę aktualnych w dniu płatności.
2.  Konwersja na walutę rozliczeniową płatności (EUR) przy użyciu kursów wymiany firmy wystawiającej fakturę aktualnych w dniu płatności.
3.  Konwersja na walutę transakcji właściwą dla płatności (DKK).

Wynikowa kwota płatności jest przenoszona do wiersza arkusza płatności po zamknięciu strony **Rozliczanie otwartych transakcji**.

### <a name="posting-for-gain-or-loss-because-of-different-accounting-currencies"></a>Księgowanie zysków lub strat wynikających z różnych walut rozliczeniowych

Jeśli występuje zysk lub strata na różnicy kursowej, wartość ta jest księgowana w firmie określonej w polu **Zaksięguj zyski lub straty związane z wymianą walut** na stronie **Księgowanie międzyfirmowe** dla firmy dokonującej płatności. Kwota zysku lub straty jest konwertowana na walutę rozliczeniową firmy, w której zysk lub strata jest księgowana, przy użyciu kursu wymiany zdefiniowanego dla tej firmy.

## <a name="cash-discounts"></a>Rabaty gotówkowe

Rabaty gotówkowe generowane w trakcie procesu rozliczeń międzyfirmowych są księgowane w firmie wystawiającej fakturę lub firmie dokonującej płatności, w zależności od opcji wybranej w polu **Zaksięguj rabat gotówkowy** na stronie **Księgowanie międzyfirmowe** dla firmy dokonującej płatności. Odpowiednia transakcja rozliczająca jest generowana w firmie wystawiającej fakturę.

## <a name="overpayments-and-underpayments"></a>Nadpłaty i niedopłaty

Dopuszczalne rozbieżności różnic groszowych oraz nadpłaty i niedopłaty są uzależnione od firmy dokonującej płatności dla nadpłat i firmy wystawiającej fakturę dla niedopłat. Używane konto księgowania zależy od wartości w polu **Zarządzanie rabatami gotówkowymi** na stronie **Parametry modułu rozrachunków z odbiorcami** i w polu **Zarządzanie rabatami gotówkowymi** na stronie **Parametry modułu rozrachunków z dostawcami** dla dostawców.

-   Jeśli ustawienie zarządzania rabatami gotówkowymi ma wartość Określony albo ma wartość Nieokreślony, a odnośny rabat gotówkowy zaksięgowano w innej firmie niż nadpłatę, wówczas jest używane automatyczne konto rabatu gotówkowego odbiorcy, rabatu gotówkowego dostawcy lub różnic groszowych w walucie rozliczeniowej. Konta te można określić na stronie **Konta dla transakcji automatycznych**.
-   Jeśli ustawienie zarządzania rabatami gotówkowymi ma wartość Nieokreślony i rabat gotówkowy jest księgowany w tej samej firmie co nadpłata (firma dokonująca płatności jest także firmą wystawiającą fakturę), to jest korygowane konto tego rabatu. Na przykład, jeśli fakturę o wartości 100,00 z dostępnym rabatem gotówkowym 3,00 rozliczono z płatnością 98,00, to konto rabatu gotówkowego zostaje skorygowane o 1,00. Kwota rabatu netto wynosi 2,00.
-   Jeśli ustawienie zarządzania rabatami gotówkowymi ma wartość Nieokreślony, rabat gotówkowy jest księgowany w tej samej firmie co nadpłata, a nadpłata lub niedopłata jest rozliczana kilkoma fakturami z rabatami gotówkowymi, to jest korygowane konto rabatu gotówkowego ostatniej faktury.

Jeśli ustawienie zarządzania rabatami gotówkowymi ma wartość Nieokreślony, to zasady rozliczania nieokreślonych płatności obowiązują tylko w następujących sytuacjach:
-   istnieje nadpłata,
-   nadpłata jest rozliczana za pomocą faktury lub kilku faktur z rabatem gotówkowym,
-   rabat gotówkowy jest księgowany w tej samej firmie, co nadpłata.

We wszystkich innych sytuacjach nadpłaty i niedopłaty są księgowane na automatycznym koncie rabatu gotówkowego odbiorcy, rabatu gotówkowego dostawcy lub różnic groszowych w walucie rozliczeniowej.

## <a name="sales-tax"></a>Podatek
Transakcje podatkowe pozostają w firmie, w której zostały pierwotnie zaksięgowane. 

Jeśli podatek zaksięgowano w związku z przedpłatą, to rozliczenie międzyfirmowe wycofuje podatek z tytułu przedpłaty w firmie dokonującej przedpłaty. Podatki w firmie wystawiającej fakturę pozostają w tej firmie.

## <a name="financial-dimensions"></a>Wymiary finansowe
W wypadku płatności od odbiorców w transakcjach „należne do” i „należne od” w firmie dokonującej płatności są używane wymiary finansowe określone w rozliczanej płatności dla konta rozrachunków z odbiorcami. W firmie wystawiającej fakturę w transakcjach „należne do” i „należne od” są używane wymiary finansowe określone w rozliczanej fakturze dla konta rozrachunków z odbiorcami. 

W wypadku płatności do dostawców w transakcjach „należne do” i „należne od” w firmie otrzymującej płatność są używane wymiary finansowe określone w rozliczanej płatności dla konta rozrachunków z dostawcami. W firmie wystawiającej fakturę w transakcjach „należne do” i „należne od” są używane wymiary finansowe określone w rozliczanej fakturze dla konta rozrachunków z dostawcami.

## <a name="withholding-tax"></a>Potrącona zaliczka na podatek
Konto dostawcy skojarzone z fakturą służy do określania, czy powinna być obliczana zaliczka na podatek. Jeśli zaliczka na podatek ma zastosowanie, jest obliczana w firmie skojarzonej z fakturą. Jeśli firmy używają różnych walut, zostanie użyty kurs wymiany firmy skojarzonej z fakturą.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
