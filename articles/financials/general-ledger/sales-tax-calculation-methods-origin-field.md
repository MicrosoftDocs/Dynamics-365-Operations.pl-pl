---
title: "Wybieranie metody obliczeń podatków w polu podstawy"
description: "W tym artykule opisano opcje dostępne w polu Podstawy opodatkowania na stronie kodów podatków oraz sposób obliczania podatku na podstawie wybranej opcji kodu podatku."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1473eeb2950296f5ae6250d7a53794af3d9cba81
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>Wybieranie metody obliczeń podatków w polu podstawy

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

W tym artykule opisano opcje dostępne w polu Podstawy opodatkowania na stronie kodów podatków oraz sposób obliczania podatku na podstawie wybranej opcji kodu podatku.

Dla każdego kodu podatku utworzonego na stronie Kody podatku należy wybrać metodę obliczeń, która będzie stosowana w odniesieniu do kwoty podstawy podatku w polu Podstawa.

## <a name="percentage-of-net-amount"></a>Procent od kwoty netto
Metoda obliczania wartości procentowej kwoty netto jest wartością domyślną w polu Podstawa. Podatek jest obliczany jako procent kwoty zakupu lub kwoty sprzedaży niezawierających jakichkolwiek podatków.
### <a name="example"></a>Przykład

Stawka podatku = 25%. Wiersz faktury zawiera 10 sztuk towaru po 1,00 USD, a odbiorca ma rabat wiersza w wysokości 10%. Kwota netto: (10 x 1,00) -10% = 9,00 Podatek: 9,00 x 25% = 2,25 Łączna kwota: 9,00 + 2,25 = 11,25

## <a name="percentage-of-gross-amount"></a> Procent od kwoty brutto
Jeśli wybierzesz metodę Procent od kwoty brutto, podatek jest obliczany jako procent kwoty sprzedaży brutto. Kwota brutto to kwota netto wiersza plus wszystkie podatki i opłaty dla wiersza, z wyjątkiem podatku z podstawą = procent od kwoty brutto.
### <a name="example"></a>Przykład

Urząd skarbowy nałożył na dany towar specjalne cła. Kwoty ceł są dodawane do kwoty netto przed obliczeniem podatku. Kody podatków:
-   CŁO 1 = 10%, przy użyciu metody obliczeń Procent od kwoty netto
-   CŁO 2 = 20%, przy użyciu metody obliczeń Procent od kwoty netto
-   PODATEK = 25%, przy użyciu metody obliczeń Procent od kwoty brutto

Jeśli kwota netto = 10,00, wtedy cło 1 = 1,00 x 10.00%= 10 , a cło 2 = 2,00 x 10.00% = 20. Kwoty będą następujące: Kwota brutto: kwota netto + CŁO 1 + CŁO 2 (10,00 + 1,00 + 2,00) = 13,00 PODATEK = 13,00 x 25% = 3,25 CŁA I PODATEK łącznie: 1,00 + 2,00 + 3,25 = 6,25 Suma: 10,00 + 6,25 = 16,25

| **Uwaga**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tylko jeden kod z Podstawą = Procent od kwoty brutto może być użyty w transakcji. Jeśli więcej niż jeden taki kod podatku jest określony dla transakcji, zostanie wyświetlony błąd z informacją, że nie można obliczyć podatku. |


<a name="percentage-of-sales-tax"></a>Procent od podatku
-----------------------

Po wybraniu opcji Procent od sprzedaży w polu Podstawa, podatek jest obliczany jako procent podatku zaznaczonego w podatku w polu Podatek. Najpierw jest obliczany podatek wybrany w opcji podatek w polu Podatek. Na podstawie kwoty pierwszego podatku jest następnie obliczany drugi podatek.
### <a name="example"></a>Przykład

Kody podatków:
-   CŁO 1 = 10%, przy użyciu metody Procent od kwoty netto
-   CŁO 2 = 20% przy użyciu metody Procent podatku, z cło 1 w opcji podatek w polu Podatek
-   PODATEK = 25%, przy użyciu metody obliczeń Procent od kwoty brutto

Kwota netto: 10,00 cło 1: 10,00 x 10% = 1,00 cło 2: 1,00 x 20% = 0,20 kwota brutto: 10,00 + 1,00 + 0,20 = 11,20 podatek: 11,20 x 25% = 2.80 Suma ceł i podatek: 1,00 + 0,20 + 2,80 = 4,00 łączna kwota: 10,00 + 4,00 = 14,00

| **Uwaga**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nie można używać wielu poziomów podatku w obliczeniach podatku. Podatek nie może być obliczany na podstawie podatku, który już jest obliczony na podstawie innego podatku. Można obliczyć wiele jednopoziomowych podatków dla kodu podatku w transakcji. |

## <a name="amount-per-unit"></a> Kwota na jednostkę
Po wybraniu opcji Kwota na jednostkę w polu Podstawa, podatek jest obliczany jako stała kwota na jednostkę pomnożona przez ilość wpisana w wierszu dokumentu. Jednostka musi zostać określona polu Jednostka. Kwota na jednostkę jest określana na stronie Wartości kodu podatku.
### <a name="example"></a>Przykład

Kod podatku jest skonfigurowany jako: 1,20 USD na jednostkę = pole W wierszu faktury sprzedaży 25 opakowań towaru jest sprzedanych Podatek jest obliczany jako 25 x 1,20 = 30,00.

| **Uwaga**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jeśli transakcja zostanie wprowadzona w jednostce innej niż jednostka określona w kodzie podatku, jest ona automatycznie konwertowana w oparciu o konwersje jednostek ustawiane na stronie Konwersje jednostek. |

###  <a name="amount-per-unit-additional-option"></a> Kwota na jednostkę (opcja dodatkowa)

Na karcie Obliczanie, można wybrać, czy podatek obliczany na jednostkę jest obliczany przed innymi kodami podatków i dodawany do kwoty netto przed obliczeniem innych kodów podatków z Podstawą = Procent od kwoty netto.

### <a name="examples"></a>Przykłady

Załóżmy, że obliczamy 2 kody podatków dla transakcji:

-   CŁO: Podstawa = Kwota na jednostkę oraz podatek, wartość jest ustawiona na 5,00 na jednostkę = szt.
-   PODATEK: Źródło = jak pokazano w poniższych przykładach, wartość jest równa 25%

Sprzedajemy 1 sztukę towaru w cenie jednostkowej 10,00.
#### <a name="example-1"></a>Przykład 1

PODATEK: Źródło = metoda obliczeń Procent od kwoty brutto Opcja Oblicz przed naliczeniem podatku jest ignorowana, ponieważ PODATEK jest obliczany jako procent od kwoty brutto. CŁO: 1 x 5,00 = 5,00 Kwota brutto: 10,00 + 5,00 = 15,00 PODATEK: 15,00 x 25% = 3,75 Całkowity podatek: 5,00 + 3,75 = 8,75 Łączna kwota: 10,00 + 8,75 = 18,75

#### <a name="example-2"></a>Przykład 2

PODATEK: Źródło = Procent od kwoty netto Opcja Oblicz przed naliczeniem podatku nie jest zaznaczona dla obliczania CŁA. Kwota netto: 10,00 CŁO: 1 x 5,00 = 5,00 PODATEK: 10,00 x 25% = 2,50 Całkowity podatek: 5,00 + 2,50 = 7,50 Łączna kwota: 10,00 + 7,50 = 17,50

#### <a name="example-3"></a>Przykład 3

PODATEK: Źródło = Procent od kwoty netto Opcja Oblicz przed naliczeniem podatku jest zaznaczona dla obliczania CŁA. Kwota netto: 10,00 CŁO: 1 x 5,00 = 5,00 PODATEK: (10,00 + 5,00) x 25% = 3,75 Całkowity podatek: 5,00 + 3,75 = 8,75 Łączna kwota: 10,00 + 8,75 = 18,75

#### <a name="example-4"></a>Przykład 4

Wyniki z przykładów 3 i 1 są takie same, ponieważ nałożono tylko jedno cło. Załóżmy, że masz dwa CŁA, a tylko jedno z nich jest uwzględniane w kwocie netto do obliczania podatku: CŁO 1: 5,00, przy użyciu metody Kwota na jednostkę i opcja Oblicz przed naliczeniem podatku jest zaznaczona CŁO 2: 2,50, przy użyciu metody Kwota na jednostkę i opcja Oblicz przed naliczeniem podatku nie jest zaznaczona Podatek: 25%, przy użyciu metody Procent od kwoty netto Kwota netto: 10,00 CŁO 1: 1 x 5,00 CŁO 2: 1 x 2,50 = 2,50 Kwota netto do opodatkowani: 10,00 + 5,00 = 15,00 PODATEK: 15.00 x 25% = 3,75 Suma podatku uwzględniająca cła: 5.00 + 2,50 + 3,75 = 11,25 Łączna kwota: 10,00 + 11,25 = 21,25 25% PODATKU jest obliczane dla sumy kwoty netto (10,00) + CŁO 1 (5,00) = 15,00. CŁO 2 jest dodawane do kwoty podatku po obliczeniu podatku.

## <a name="calculated-percentage-of-net-amount"></a> Obliczony procent kwoty netto
Obliczony procent kwoty netto obsługuje obliczanie podatku inaczej w zależności od ustawienia parametru Kwoty zawierają podatek dla dokumentu lub arkusza.
### <a name="example-1"></a>Przykład 1

Dokument/arkusz jest ustawiony na Kwoty zawierają podatek = Tak Kwota wiersza transakcji: 10,00 Stawka podatku: 25% Podatek: Kwota wiersza transakcji x stawka podatku (10,00 x 25%) = 2,50 Kwota podstawy podatku (kwota źródła): Kwota wiersza transakcji - Podatek (10,00 - 2,50) = 7,50)

### <a name="example-2"></a>Przykład 2

Dokument/arkusz jest ustawiony na Kwoty zawierają podatek = Nie Kwota wiersza transakcji: 10,00 Stawka podatku: 25% Podatek: (Kwota wiersza transakcji x stawka podatku) / (100 - stawka podatku) (10,00 x 25%) / (100% - 25%) = 3,33 Kwota podstawy podatku (kwota źródła): Kwota wiersza transakcji = 10,00



<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Ustalanie stawki podatku na podstawie pól Podstawa limitu i Metoda obliczania](marginal-base-field.md)

[Opcje Cała kwota i Obliczanie interwału dla kodów podatku](whole-amount-interval-options-sales-tax-codes.md)




