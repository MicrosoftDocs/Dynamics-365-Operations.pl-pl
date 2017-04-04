---
title: "Stawki podatku na podstawie Podstawa i metody obliczeń"
description: "W tym artykule wyjaśniono, jak wartości w polach Podstawa limitu i Metoda obliczania ustalają stawki podatków w transakcji sprzedaży i zakupu."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ad731401fe553cdc50665cc87aaac64dc48813f2
ms.lasthandoff: 03/31/2017


---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a>Stawki podatku na podstawie Podstawa i metody obliczeń

W tym artykule wyjaśniono, jak wartości w polach Podstawa limitu i Metoda obliczania ustalają stawki podatków w transakcji sprzedaży i zakupu.

Podstawa limitu na karcie skróconej Obliczenia na stronie Podatek określają, która kwota służy do pobierania odpowiedniej stawki podatkowej z kursów na stronie Wartości kodu podatku. Typ kwoty w polu Podstawa limitu w połączeniu z metodą w polu Metoda obliczania określa logikę znajdowania odpowiednich stawek podatku dla transakcji. 

Rozmaite kombinacje wartości w tych polach generują całkowicie odmienne obliczenia podatku, jak pokazano na poniższych przykładach. W przykładach użyto tych samych wartości interwału podatku, które konfiguruje się na stronie Wartość kodu podatku. Aby otworzyć tę stronę, kliknij przycisk Kod podatku &gt;wartości na stronie kodów podatku.

> [!Important]                                                                                                                  
> Jeśli podstawa limitu w co najmniej jednym kodzie podatku jest oparta na kwotach lub jednostkach wiersza, pole Metoda obliczania na stronie Parametry księgi głównej musi mieć wartość Wiersz. |

## <a name="net-amount-per-line"></a>Kwota netto na wiersz
Wybierz tę opcję, aby określić stawki podatku na podstawie kwot netto dla wierszy faktury, z wykluczeniem wszelkich innych podatków.

### <a name="example"></a>Przykład

Stawki podatku są skonfigurowane przy użyciu następujących interwałów.

| Interwał kwoty    | Stawka podatkowa |
|--------------------|----------|
| 0–50             | 30%      |
| 50–100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

> [!NOTE]                                                                                                             
> Górny limit zero (0) w ostatnim interwale oznacza, że wszystkie kwoty powyżej 100 są uwzględniane w tym interwale.

Podstawa: **kwota netto na wiersz** 

Metoda obliczeń: **interwału** 

Kupujesz 8 lamp po 25,00 każda. 

Kwota netto dla wiersza faktury wynosi 200,00. 

Podatek jest obliczany w następujący sposób: 

Suma podatku = 50 x 30% + 50 × 20% + 100 x 10% = 15 + 10 + 10 = 35,00 

Łączna kwota faktury = 200,00 + 35,00 = 235,00 

**Variation** 

Jeśli faktura ma dwie linie o czterech elementach w każdym wierszu, kwota netto w każdym wierszu jest 100,00 i podatek jest obliczany w następujący sposób: 

Podatek od sprzedaży wiersz 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25,00 

Wiersz podatku, 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25,00 

Suma podatku = 25,00 + 25,00 = 50,00 

Łączna kwota faktury = 200,00 + 50,00 = 250,00

## <a name="net-amount-per-unit"></a> Kwota netto na jednostkę
Wybierz tę opcję, aby określić stawki podatku na podstawie wartości poszczególnych jednostek, z wykluczeniem wszelkich innych podatków. Jeśli wybrana jest Podstawa limitu oparta na jednostce, wówczas dla Kodu podatku wystarczy określić tylko Jednostkę.

### <a name="example"></a>Przykład

Stawki podatku są skonfigurowane przy użyciu następujących interwałów.

| Ilość             | Stawka podatkowa |
|--------------------|----------|
| 0–50             | 30%      |
| 50–100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Podstawa: **kwota netto na jednostkę** 

Metoda obliczeń: **cała kwota** 

Kupujesz 8 lamp po 25,00 każda. 

Kwota netto dla wiersza faktury wynosi 200,00. 

Podatek jest obliczany w następujący sposób: Podatek na jednostkę = 25,00 x 30% = 7,50 Suma podatku = 7,50 x 8 jednostek = 60,00 Łączna kwota faktury = 200,00 + 60,00 = 260,00

## <a name="net-amount-of-invoice-balance"></a> Kwota netto faktury

Wybierz tę opcję, aby określić stawki podatku na podstawie łącznej wartości dla faktury, z wykluczeniem wszelkich innych podatków.

### <a name="example"></a>Przykład

Stawki podatku są skonfigurowane przy użyciu następujących interwałów.

| Ilość            | Stawka podatkowa |
|-------------------|----------|
| 0–50            | 30%      |
| 50–100          | 20%      |
| 100 -0 (&gt; 100) | 10%      |

Podstawa: **kwotę netto saldo faktury** 

Metoda obliczeń: **interwał** faktury sprzedaży ma 2 linie z 4 lampy na każdej linii dla 25,00. Kwota netto salda faktury wynosi 4 x 25,00 + 4 x 25,00 = 200,00. Podatek jest obliczany w następujący sposób: Suma podatku = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Łączna kwota faktury = 200,00 + 35,00 = 235,00

## <a name="gross-amount-per-line"></a> Kwota brutto na wiersz

Wybierz tę opcję, aby określić stawki podatku na podstawie wartości wiersza z uwzględnieniem wszystkich podatków dla tego wiersza.

> [!NOTE]
> Grupa podatków może zawierać tylko jeden kod podatku z tą wartością wybraną w polu Podstawa limitu.

### <a name="example"></a>Przykład

Stawki podatku są skonfigurowane przy użyciu następujących interwałów.

| Ilość             | Stawka podatkowa |
|--------------------|----------|
| 0–50             | 30%      |
| 50–100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Podstawa limitu: **Kwota brutto na wiersz** Metoda obliczania: **Zakres** Dodatkowo jest obliczany jest inny kod podatku dla specjalnego cła w wysokości 5,00 za każdą lampę. Kwota cła jest dodawana do kwoty netto przed obliczeniem podatku. Kupujesz 8 lamp po 25,00 każda. Kwota netto dla wiersza faktury wynosi 200,00. Kwota brutto dla wiersza faktury wynosi 8 x 25,00 + 8 x 5,00 = 240,00. Podatek jest obliczany w następujący sposób: Suma podatku = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 ogółem cła = 5,00 x 8 = 40,00 łączna kwota faktury = 200,00 + 39,00 + 40,00 = 279.00

**Variation** 

Jeśli faktura jest tworzona przy użyciu 2 wiersze faktury z 4 elementy w każdym wierszu, kwota netto na wiersz faktury jest 100,00. Kwota brutto (z uwzględnieniem cła 4 x 5,00) na wiersz faktury wynosi 120,00, a podatek jest obliczany w następujący sposób: Wiersz 1 podatku na fakturze = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Wiersz 2 podatku na fakturze = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Suma podatku = 27,00 + 27,00 = 54,00 Łączne cło = 5,00 x 8 = 40,00 Łączna kwota faktury = 200,00 + 54,00 + 40,00 = 294,00.

## <a name="gross-amount-per-unit"></a> Kwota brutto na jednostkę

Wybierz tę opcję, aby określić stawki podatku na podstawie wartości poszczególnych jednostek, z uwzględnieniem wszelkich innych podatków.

> [!NOTE]
> Grupa podatków może zawierać tylko jeden kod podatku z tą wartością wybraną w polu Podstawa limitu.

### <a name="example"></a>Przykład

Stawki podatku są skonfigurowane przy użyciu następujących interwałów.

| Ilość             | Stawka podatkowa |
|--------------------|----------|
| 0–50             | 30%      |
| 50–100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Podstawa limitu: **Kwota brutto na jednostkę** jest specjalnym cłem, które wynosi 5,00 za każdą lampę. Kwota cła jest dodawana do kwoty netto przed obliczeniem podatku. Kupujesz 8 lamp po 25,00 każda. Kwota brutto na jednostkę wynosi 30,00. Podatek jest obliczany w następujący sposób: Podatek na jednostkę = 30 x 30% = 9,00 Łączny podatek = 9,00 x 8 = 72,00 Łączne cło = 5,00 x 8 = 40,00 Łączna kwota faktury = 200,00 + 72,00 + 40,00 = 312,00

## <a name="invoice-total-incl-other-sales-tax-amounts"></a> Kwota faktury z innymi podatkami

Wybierz tę opcję, aby określić stawki podatku na podstawie łącznej wartości dla faktury, z uwzględnieniem wszelkich innych podatków.
> [!NOTE]
> W grupie podatków może masz tylko jeden kod podatku z dokonanym wyborem w polu podstawowym marginalny

### <a name="example"></a>Przykład

Stawki podatku są skonfigurowane przy użyciu następujących interwałów.

| Ilość             | Stawka podatkowa |
|--------------------|----------|
| 0–50             | 30%      |
| 50–100           | 20%      |
| 100 - 0 (&gt; 100) | 10%      |

Podstawa: **faktury razem z innymi podatkami** metoda obliczeń: **interwału**   
Istnieje specjalny obowiązek 5,00 na każdego światła. Kwota cła jest dodawana do kwoty netto przed obliczeniem podatku. Kupujesz 8 lamp po 25,00 każda. Kwota netto dla faktury wynosi 200,00. Kwota brutto dla faktury wynosi 200,00 + (8 x 5,00) = 240,00. Podatek jest obliczany w następujący sposób: Łączny podatek = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Łączne cło = 5,00 x 8 = 40,00 Łączna kwota faktury = 200,00 + 39,00 + 40,00 = 279,00

Aby uzyskać więcej informacji, zobacz [całej kwoty i opcje obliczania interwału dla kodów podatku](whole-amount-interval-options-sales-tax-codes.md) i [metody obliczeń podatków w polu podstawy](sales-tax-calculation-methods-origin-field.md).


