---
title: Typy księgowania wynajmu
description: W tym temacie opisano typy księgowania używane w transakcjach wynajmu składników majątku.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddc229f3ab8e048390f27503e2c6c26bd1a6f24f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841148"
---
# <a name="lease-posting-types"></a>Typy księgowania wynajmu

[!include [banner](../includes/banner.md)]

W tym temacie opisano typy księgowania używane w transakcjach wynajmu składników majątku.

## <a name="lease-asset"></a>Składnik majątku wynajmu

Konto jest skojarzone ze składnikiem majątku z prawem do użytkowania (PDU). To konto jest obciążane, gdy wynajem jest początkowo ujmowany zgodnie z nowymi standardami księgowania wynajmu — Accounting Standards Codification Topic 842 (ASC 842) i Międzynarodowy Standard Sprawozdawczości Finansowej nr 16 (MSSF 16). W zmodyfikowanym wynajmie to konto może być obciążane lub uznawane w zależności od tego, czy modyfikacja powoduje zwiększenie, czy zmniejszenie zobowiązania z tytułu wynajmu.

**Przykładowe wpisy w arkuszu:** Początkowe ujęcie<br>
**Strona Winien:** Należność z tytułu wynajmu XXX<br>
**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX

## <a name="lease-liability"></a>Zobowiązanie z tytułu wynajmu

Konto jest skojarzone ze zobowiązaniem z tytułu wynajmu, które występuje, gdy płatności są dyskontowane w ramach nowych standardów MSSF 16 i ASC 842. Konto jest uznawane, gdy wynajem jest początkowo ujmowany według nowych standardów. Jest obciążane opłatami z tytułu wynajmu, a uznawane naliczonymi odsetkami.

**Przykładowe wpisy w arkuszu:** Początkowe ujęcie<br>
**Strona Winien:** Należność z tytułu wynajmu XXX<br>
**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX

**Przykładowe wpisy w arkuszu:** Naliczanie odsetek<br>
**Strona Winien:** Koszt odsetek XXX<br>
**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX

**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu<br>
**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX<br>
**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX

## <a name="short-term-lease-liability"></a>Krótkoterminowe zobowiązanie z tytułu wynajmu

Konto jest łączone z krótkoterminowym zobowiązaniem z tytułu wynajmu, gdy jest księgowany wpis w arkuszu dotyczący przeklasyfikowania krótkoterminowego zobowiązania z tytułu wynajmu. Konto jest uznawane krótkoterminowym zobowiązaniem według harmonogramu amortyzacji w ostatnim dniu miesiąca. Jednak ta sama kwota jest księgowana po stronie debetowej pierwszego dnia następnego miesiąca.

**Przykładowe wpisy w arkuszu:** Przeklasyfikowanie krótkoterminowego zobowiązania z tytułu wynajmu<br>
**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX<br>
**Strona Ma:** Krótkoterminowe zobowiązanie z tytułu wynajmu XXX<br>
**Strona Winien:** Krótkoterminowe zobowiązanie z tytułu wynajmu XXX<br>
**Strona Ma:** Zobowiązanie z tytułu wynajmu XXX

## <a name="depreciation-expense"></a>Wydatek amortyzacji

Konto jest łączone z wydatkiem związanym z amortyzacją składnika majątku z PDU zgodnie z MSSF 16, ASC 842 i zasadami leasingu finansowego określonymi w MSR 17 i ASC 840. Konto jest obciążane, gdy składnik majątku z PDU jest amortyzowany w każdym miesiącu.

**Przykładowe wpisy w arkuszu:** Naliczanie amortyzacji<br>
**Strona Winien:** Wydatek amortyzacji XXX<br>
**Strona Ma:** Umorzenie XXX

## <a name="gainloss-on-lease-modification"></a>Zysk/strata z modyfikacji wynajmu

Konto jest łączone ze wszystkimi zyskami lub stratami powstającymi w wyniku modyfikacji wynajmu. Zysk może powstać podczas modyfikacji wynajmu, jeśli modyfikacja zmniejsza zobowiązanie z tytułu wynajmu o kwotę przekraczającą wartość bilansową składnika majątku z PDU.

Na przykład wynajmowany składnik ma bieżącą wartość bilansową zobowiązania z tytułu wynajmu wynoszącą 150 000 zł i wartość bilansową składnika majątku z PDU wynoszącą 100 000 zł. Wynajem jest modyfikowany, a modyfikacja powoduje utworzenie nowej wartości bieżącej przyszłych opłat z tytułu wynajmu (PVFMLP) wynoszącej 40 000 zł. Z tego względu zobowiązanie z tytułu wynajmu zostanie zaksięgowane po stronie debetowej na kwotę 110 000 zł (150 000 zł – 40 000 zł). Ponieważ składnik majątku z PDU ma wartość tylko 100 000 zł, spadek o 110 000 zł zmniejszy wartość składnika majątku poniżej 0 (zera). Dlatego też wytyczne dotyczące księgowania stanowią, że reszta powinna zostać zaksięgowana na koncie zysków. W tym przypadku ostatecznym wpisem w arkuszu będzie obciążenie zobowiązaniem z tytułu wynajmu na kwotę 110 000 zł, uznanie należnością z tytułu wynajmu na kwotę 100 000 zł oraz uznanie konta zysków na kwotę 10 000 zł.

**Przykładowe wpisy w arkuszu:** Modyfikacja wynajmu<br>
**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX<br>
**Strona Ma:** Należność z tytułu wynajmu XXX<br>
**Strona Ma:** Zysk XXX

## <a name="accumulated-depreciation"></a>Umorzenie

Konto jest łączone z kontem przeciwstawnym składnika majątku z PDU. Konto jest uznawane podczas księgowania wydatku amortyzacji.

**Przykładowe wpisy w arkuszu:** Naliczanie amortyzacji<br>
**Strona Winien:** Wydatek amortyzacji XXX<br>
**Strona Ma:** Umorzenie XXX

## <a name="variable-payment"></a>Zmienna płatność

Konto jest łączone ze zmiennymi opłatami z tytułu wynajmu, które są generowane poprzez przeszacowanie indeksu w leasingu według standardów ASC 842, ASC 840 i MSR 17. W harmonogramie opłat z tytułu wynajmu zmienne płatności są uwzględniane w kolumnie **Opłaty zmienne**. Konto jest obciążane podczas tworzenia faktury dla wiersza harmonogramu płatności zawierającego zmienną opłatę.

**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu<br>
**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX<br>
**Strona Winien:** Opłata zmienna XXX<br>
**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX

## <a name="deferred-rent-asset-liability"></a>Odroczony czynsz składnika majątku (zobowiązanie)

Konto jest łączone z należnością lub zobowiązaniem z tytułu odroczonego czynszu powstającego w wynajmie z odroczonym czynszem. Konto jest obciążane podczas księgowania faktury za wynajem z odroczonym czynszem, jeśli kwota opłaty z tytułu wynajmu jest wyższa niż koszt wynajmu liczony metodą liniową za ten okres. Jest uznawane, gdy opłata z tytułu wynajmu jest niższa niż koszt wynajmu liczony metodą liniową za ten okres.

**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu (wynajem z odroczonym czynszem)<br>
**Strona Winien:** Wydatek z tytułu wynajmu XXX<br>
**Strona Ma:** Zobowiązanie z tytułu odroczonego czynszu XXX<br>
**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX

## <a name="lease-expense"></a>Wydatek z tytułu wynajmu

Konto jest łączone z wydatkiem z tytułu wynajmu, jeśli wynajem jest klasyfikowany jako wynajem z odroczonym czynszem. Konto jest obciążane podczas księgowania faktury za wynajem z odroczonym czynszem.

**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu (wynajem z odroczonym czynszem)<br>
**Strona Winien:** Wydatek z tytułu wynajmu XXX<br>
**Strona Ma:** Zobowiązanie z tytułu odroczonego czynszu XXX<br>
**Strona Ma:** Zobowiązanie wobec dostawcy/opłata z tytułu wynajmu XXX

## <a name="impairment-expense"></a>Wydatek utraty wartości

Spadek wartości wynajmowanego składnika powoduje odpowiednie księgowanie na koncie. Konto jest obciążane, natomiast konto składnika majątku z PDU jest bezpośrednio uznawane.

**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu<br>
**Strona Winien:** Wydatek utraty wartości XXX<br>
**Strona Ma:** Składnik majątku z PDU XXX

## <a name="lease-payment"></a>Opłata z tytułu wynajmu

Na koncie następuje księgowanie, gdy parametr **Płatność dla dostawcy** jest wyłączony. Kiedy parametr jest wyłączony, jest uznawane to konto, a nie konto zobowiązań wobec dostawcy.

**Przykładowe wpisy w arkuszu:** Opłata z tytułu wynajmu<br>
**Strona Winien:** Zobowiązanie z tytułu wynajmu XXX<br>
**Strona Ma:** Opłata z tytułu wynajmu XXX

## <a name="expense-type-postings"></a>Księgowania typów wydatków

Konto wybrane dla każdego typu wydatków jest obciążane po wygenerowaniu płatności dla danego typu wydatków. Na przykład konto określone dla typu wydatków **Ubezpieczenia** jest obciążane, ilekroć jest tworzona faktura lub wpis w arkuszu płatności na podstawie harmonogramu kosztów wykonawczych dla wydatków ubezpieczeniowych.

**Przykładowe wpisy w arkuszu:** Płatność z tytułu ubezpieczenia<br>
**Strona Winien:** Konto wydatków ubezpieczeniowych XXX<br>
**Strona Ma:** Konto przeciwstawne XXX

> [!NOTE]
> Konto przeciwstawne jest wybierane na poziomie wynajmu w wierszach harmonogramu płatności kosztów wykonawczych. Konto przeciwstawne może być powiązane z dostawcą lub z kontem księgowym.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
