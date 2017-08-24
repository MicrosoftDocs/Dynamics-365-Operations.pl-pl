---
title: Konfigurowanie stopy procentowej dla kodu odsetek
description: "Kody odsetek zawierają ustawienia określające, kiedy i jak i odsetki obciążają i jak są obliczane na kontach zaległych."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: Shiva.Pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b9595cf287f59ddb7543f36b2b541200f70a9c96
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="set-up-interest-rates-for-an-interest-code"></a>Konfigurowanie stopy procentowej dla kodu odsetek

[!include[banner](../includes/banner.md)]


Kody odsetek zawierają ustawienia określające, kiedy i jak i odsetki obciążają i jak są obliczane na kontach zaległych.

Można utworzyć jeden kod odsetek i zastosować do wielu profili księgowania odbiorców lub w określonych w wierszach faktury. Gdy szczegóły kodu odsetek zmieniają się, wszystkie funkcje używane do kodu powodują automatyczne wprowadzenie zmian w nowych transakcjach. Dla każdego kodu odsetek należy zdefiniować dwa rodzaje stawek:
-   Stawki zysku z odsetek — reprezentują one przychód obciążany odsetkami w przypadku faktur i not odsetkowych.
-   Stawki dla płatności odsetek — reprezentują one koszt, który ma być stosowany do naliczania odsetek na fakturach korygujących.

Oba te typy stawek mogą istnieć w tym samym czasie i w tym samym kodzie odsetek. Stopy procentowe mogą być oparte na trzech typach obliczeń:
-   Procent odsetek.
-   Kwota odsetek.
-   Odsetki według zakresu, które wynikają z oprocentowania lub kwoty.

Przy naliczaniu odsetek przy użyciu kodu odsetek jest tworzona oddzielna nota odsetkowa dla każdej stopy odsetkowej obowiązującej w okresie, w którym miała miejsce płatność dokonana już po terminie transakcji. Na karcie **Zarobki** na stronie **Kod odsetek** można skonfigurować stawki odsetek dla odsetek uzyskanych poprzez naliczanie odsetek. Na karcie **Płatności** można skonfigurować stopy odsetkowe dla odsetek, które będziesz płacić.

## <a name="interest-rates-based-on-a-percentage"></a>Stopy odsetkowe oparte na procencie
Istnieje możliwość konfigurowania stóp odsetek, które są obliczane według określonych odsetek.

-   Kwota odsetek ma zastosowanie do wszystkich walut.
-   Można wprowadzić opcjonalne limity kwot odsetek.
-   Opcja **Procent** jest wybrana** **w polu **Podstawa naliczania odsetek** na stronie **Skonfiguruj kody odsetek**.

Na przykład aby ustawić kod odsetek, który ma stosować oprocentowanie 5 co dwa miesiące, gdy transakcja płatności faktury przekroczy termin płatności, wprowadź 2 w polu **Obliczaj odsetki co** i wybierz opcję **Miesiąc**.

## <a name="interest-rates-based-on-amounts"></a>Stopy odsetek oparte na kwotach
Można skonfigurować stopy procentowe, które obliczają określoną kwotę w walucie.
-   Kwotę odsetek określa się dla każdej waluty w kodzie odsetek.
-   Można wprowadzić opcjonalne limity kwot odsetek.
-   Opcja **Kwota** jest wybrana w polu **Podstawa naliczania odsetek** na stronie **Skonfiguruj kody odsetek**.

Na przykład aby ustawić kod odsetek, który ma stosować oprocentowanie 25,00 co 20 dni, gdy transakcja płatności faktury przekroczy termin płatności, wprowadź 20 w polu **Obliczaj odsetki co** oraz wybierz opcję **Dzień**.

## <a name="interest-rates-based-on-ranges"></a>Stopy odsetek oparte na zakresach
Istnieje możliwość konfigurowania stóp odsetek w zależności od kwoty zaległości, od liczby dni, o ile płatność jest opóźniona lub liczby miesięcy, o które płatność jest spóźniona.
-   Na karcie **Dochody wg waluty**, aby zdefiniować określone ustawienia odsetek dla każdej waluty. Tu także definiuje się zakres.
-   Za pomocą przycisku **Zakresy** dodaje się wiersze będące zakresami, które mają zostać skonfigurowane.. Wartość **Z** odpowiada początkowi zakresu, a liczba **Wartość odsetek** określa procent lub kwotę, w zależności od wyboru dokonanego w polu **Podstawa naliczania odsetek** na stronie **Konfigurowanie kodów odsetek**.

## <a name="example-1-interest-by-range--amount"></a>Przykład 1: Odsetki według zakupu = ilość
Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co trzy miesiące, że płatności za fakturę transakcji przekraczają termin. Ma być podstawą obliczeń wartość procentową odsetek według interwałów stopniowanych kwot. Wartość odsetek jest równa 1 procent faktury dla kwoty maksymalnej 1.000,00, 2 procentu dla kwoty od 1.001,00 do 5.000,00 i 3 procentu dla dużych kwot powyżej niż 5.000,00. Utworzono kod odsetek wartości pól w następujący sposób.

| **Nazwa pola**                  | **Wartość pola** |
|---------------------------------|-----------------|
| **Kod odsetek**               | 3M%ByAmt        |
| **Obliczaj odsetki co**    | 3/miesiąc         |
| **Odsetki według zakresu**           | Kwota          |
| **Podstawa naliczania odsetek** | Wartość procentowa      |

Utworzono zakres informacji w następujący sposób.

| **Od wartości** | **Wartości odsetek** |
|----------------|--------------------|
| 0              | 1                  |
| 1,001          | 2                  |
| 5,001          | 3                  |

 
## <a name="example-2-interest-by-range--days"></a>Przykład 2: Odsetki według zakupu = dni
--------------------------------------------------

Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co 15 dni, że płatności za fakturę transakcji przekraczają termin. Podstawą obliczeń wartości procentowej odsetek mają być interwały dni. Wartość odsetek jest równa 10,00 przez 15 dni w okresie pierwszych 60 dni, 15,00 przez 15 dni w okresie 61 do 90 dni i 20,00 przez 15 dni od 91 dnia i później. Utworzono kod odsetek wartości pól w następujący sposób.

| **Nazwa pola**                  | **Wartość pola** |
|---------------------------------|-----------------|
| **Kod odsetek**               | 15DAmtXDay      |
| **Obliczaj odsetki co**    | 15/dzień          |
| **Odsetki według zakresu**           | Dni            |
| **Podstawa naliczania odsetek** | Kwota          |

Utworzono zakres informacji w następujący sposób.

| **Od wartości** | **Wartości odsetek** |
|----------------|--------------------|
| 0              | 10                 |
| 61             | 15                 |
| 91             | 20                 |

 
## <a name="example-3-interest-by-range--months"></a>Przykład 3: Odsetki według zakupu = miesiące
----------------------------------------------------

Konfigurowanie odpowiedniego kodu odsetek, który ocenia jeden raz co miesiąc, że płatności za fakturę transakcji przekraczają termin. Ma być podstawą obliczeń wartości procentowej odsetek według interwałów miesięcznych. Wartość odsetek jest równa 1,5 procent przez miesiąc dla pierwszych trzech zaległych miesięcy, 2,0 procent przez miesiąc dla kolejnych trzech miesięcy i 2,5 procent przez miesiąc dla każdego miesiąca powyżej okresu pierwszych sześciu miesięcy. Utworzono kod odsetek wartości pól w następujący sposób.

| **Nazwa pola**                  | **Wartość pola** |
|---------------------------------|-----------------|
| **Kod odsetek**               | 1M%ByMth        |
| **Obliczaj odsetki co**    | 1/miesiąc         |
| **Odsetki według zakresu**           | Miesiące          |
| **Podstawa naliczania odsetek** | Wartość procentowa      |

Utworzono zakres informacji w następujący sposób.

| **Od wartości** | **Wartości odsetek** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Nowe wersje
Kody odsetek są datą obowiązywania. Jeśli chcesz zmodyfikować stopę procentową, możesz utworzyć **nową wersję** obowiązującą od daty w przyszłości.

Aby wyświetlić różne wersje, można wybrać datę graniczną w menu **Na dzień**. Można też wybrać opcję **Wyświetlaj wszystkie rekordy**, aby wyświetlać wszystkie kody zainteresowania na stronie.




