---
title: Ograniczenia wyrażenia i ograniczenia tabeli w modelach konfiguracji produktu.
description: W tym temacie opisano zastosowanie ograniczeń wyrażenia i ograniczeń tabeli. Ograniczenia służą do kontroli wartości atrybutów, które można wybrać podczas konfigurowania produktów dla zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego. Można użyć ograniczeń wyrażenia lub ograniczeń tabeli, w zależności od preferencji dotyczących tworzenia ograniczeń.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc07d5b915e0b878cc7b2ef1d5f3253de8776608
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007718"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>Ograniczenia wyrażenia i ograniczenia tabeli w modelach konfiguracji produktu.

[!include [banner](../includes/banner.md)]

W tym temacie opisano zastosowanie ograniczeń wyrażenia i ograniczeń tabeli. Ograniczenia służą do kontroli wartości atrybutów, które można wybrać podczas konfigurowania produktów dla zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego. Można użyć ograniczeń wyrażenia lub ograniczeń tabeli, w zależności od preferencji dotyczących tworzenia ograniczeń. 

Ograniczenia służą do kontroli wartości atrybutów, które można wybrać podczas konfigurowania produktów dla zamówienia sprzedaży, oferty sprzedaży, zamówienia zakupu lub zlecenia produkcyjnego. Można użyć ograniczeń wyrażenia lub ograniczeń tabeli, w zależności od preferencji dotyczących tworzenia ograniczeń.

## <a name="what-are-expression-constraints"></a>Czym są ograniczenia wyrażenia?
Ograniczenia wyrażenia charakteryzują się wyrażeniem zawierającym operatory logiczne i arytmetycznego oraz funkcje. Ograniczenie wyrażenia jest przeznaczone dla określonego składnika w modelu konfiguracji produktu. Nie można ponownie zastosować lub współużytkować go z innym składnikiem. Jednakże, ograniczenia wyrażenia dla składnika mogą odwoływać się do atrybutów składników podrzędnych dla składników.

## <a name="what-are-table-constraints"></a>Czym są ograniczenia tabeli?
Ograniczenia tabeli to listy kombinacji wartości, które są dozwolone dla atrybutów podczas konfigurowania produktu. Definicje ograniczeń tabeli mogą być używane ogólnie. Podczas tworzenia ograniczenia tabeli dla składnika w modelu konfiguracji produktu, należy wybrać definicję ograniczenia tabeli. Aby utworzyć kombinacje, które są dozwolone, należy dodać atrybuty określonych typów do składników. Każdy typ atrybutu ma określoną wartość.

### <a name="example-of-a-table-constraint"></a>Przykład ograniczenia tabeli

Ten przykład pokazuje, jak można ograniczyć konfigurację głośnika do określonych wykończeń i maskownic. Pierwsza tabela pokazuje wykończenia i maskownice powszechnie dostępnych dla konfiguracji. Wartości są zdefiniowane dla atrybutów typu **Wykończenia** i **Maskownica**.

| Typ atrybutu | Wartości                      |
|----------------|-----------------------------|
| Wykończenie | Czarny, Dąb, Rosewood, Biały |
| Maskownica    | Czarny, Metal, Biały         |

Następna tabela przedstawia kombinacje, które są definiowane przez ograniczenie tabeli **Kolor i wykończenie**. Za pomocą tego ograniczenia tabeli można skonfigurować głośnik w dębowym wykończeniem i czarną maskownicą, wykończeniem Rodewood i białą maskownicą itd.

| Zakończenie         | Maskownica                       |
|----------------|-----------------------------|
| Dąb            | Czarny                       |
| Rosewood       | Biały                       |
| Biały          | Czarny                       |
| Biały          | Biały                       |
| Czarny          | Czarny                       |
| Czarny          | Metal                       | 

Można tworzyć ograniczenia tabeli zdefiniowane przez użytkownika lub przez system. Aby uzyskać więcej informacji, zobacz [Ograniczenia tabeli zdefiniowane przez użytkownika lub przez system](system-defined-user-defined-table-constraints.md).

## <a name="what-syntax-should-be-used-to-write-constraints"></a>Jakiej składni należy używać w celu zapisywania ograniczeń?
Trzeba zapisać ograniczenia za pomocą składni Optimization Modeling Language (OML). System używa narzędzia Microsoft Solver Foundation do rozwiązywania ograniczeń.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>Z których ograniczeń należy korzystać: ograniczeń wyrażenia czy ograniczeń tabeli?
Można użyć albo ograniczeń wyrażenia, albo ograniczeń tabeli, w zależności od preferencji dotyczących ograniczeń. Ograniczenie tabeli jest tworzone jako macierz, podczas gdy ograniczenie wyrażenia to indywidualna instrukcja. Podczas konfigurowania produktu, nie ma znaczenia, jaki rodzaj ograniczenia jest używany. W poniższym przykładzie pokazano, jak te dwie metody się od siebie różnią.  

Jeśli konfigurujesz produkt za pomocą następujących ustawień ograniczenia, dozwolone są następujące kombinacje:

-   Produkt w kolorze Czarny i rozmiarze 30 lub 50
-   Produkt w kolorze Czerwony i rozmiarze 20

### <a name="table-constraint-setup"></a>Konfiguracja ograniczenia tabeli

| Kolor | Rozmiar |
|-------|------|
| Czarny | 30   |
| Czarny | 50   |
| Czerwony   | 20   |

### <a name="expression-constraint-setup"></a>Ustawienia ograniczenia wyrażenia

(Kolor == "Czarny" & (rozmiar == "30" | rozmiar == "50")) | (kolor == "Czerwony" & rozmiar = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>Czy używać operatorów czy notacji infix podczas zapisywania ograniczeń wyrażenia?
Możesz zapisać ograniczeń wyrażenia przy użyciu dostępnych operatorów prefiksu lub przy użyciu notacji infix. Dla operatorów **Min**, **Max** i **Abs** nie można użyć notacji infix. Operatory te są dołączane jako operacje standardowe w większości języków programowania.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>Jakich operatorów i notacji infix należy używać podczas zapisywania ograniczeń wyrażenia?
W poniższych tabelach znajdują się listy operatorów i notacji infix, których można używać podczas zapisywania ograniczenia wyrażenia dla składnika w modelu konfiguracji produktu. W przykładach w tym pierwszej tabeli zobacz jak zapisać wyrażenie przy użyciu notacji infix lub operatorów.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Operator</th>
<th>Opis</th>
<th>Składnia</th>
<th>Przykłady</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implies</td>
<td>Jest to wartość true, jeśli pierwszy warunek nie jest spełniony, drugi warunek jest prawdziwy, lub oba są.</td>
<td>Implies[a, b], infix: a -: b</td>
<td><ul>
<li><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</li>
<li><strong>Notacja Infix:</strong> x != 0 -: y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>i</td>
<td>Jest to możliwe tylko wtedy, gdy są spełnione wszystkie warunki. Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>True</strong>.</td>
<td>And[args], infix: a &amp; b &amp; ... &amp; z</td>
<td><ul>
<li><strong>Operator:</strong> And[x == 2, y &lt;= 2]</li>
<li><strong>Notacja Infix:</strong> x == 2 &amp; y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>lub</td>
<td>Wartość jest True, jeśli jest spełniony dowolny z warunków. Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>False</strong>.</td>
<td>Or[args], infix: a | b | ... | z</td>
<td><ul>
<li><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</li>
<li><strong>Notacja Infix:</strong> x == 2 | y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Plus</td>
<td>Sumuje warunki. Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>0</strong>.</td>
<td>Plus[args], infix: a + b + ... + z</td>
<td><ul>
<li><strong>Operator:</strong> Plus[x, y, 2] == z</li>
<li><strong>Notacja infix:</strong> x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Minus</td>
<td>Zmienia to znak argumentu. To musi mieć dokładnie jeden warunek.</td>
<td>Minus[expr], infix: -expr</td>
<td><ul>
<li><strong>Operator:</strong> Minus[x] == y</li>
<li><strong>Notacja infix:</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>Wartość bezwzględna dla warunku. To musi mieć dokładnie jeden warunek.</td>
<td>Abs[expr]</td>
<td><strong>Operator:</strong> Abs[x]</td>
</tr>
<tr class="odd">
<td>Czasy</td>
<td>Produkt jego warunków. Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>1</strong>.</td>
<td>Times[args], infix: a * b * ... * z</td>
<td><ul>
<li><strong>Operator:</strong> Times[x, y, 2] == z</li>
<li><strong>Notacja infix:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Potęga</td>
<td>Wartość wykładnicza. Potęgowanie od prawej do lewej. (Innymi słowy jest łączna z prawej). Dlatego <strong>Power[a, b, c]</strong> jest równoznaczne z <strong>Power[a, Power[b, c]]</strong>. Operatora <strong>Power</strong> można użyć tylko pod warunkiem, że wykładnik jest dodatnią wartością stałą.</td>
<td>Power[args], infix: a ^ b ^ ... ^ z</td>
<td><ul>
<li><strong>Operator:</strong> Power[x, 2] == y</li>
<li><strong>Notacja infix:</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>Maks.</td>
<td>Opcja zapewnia największy warunek. Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>Infinity</strong>.</td>
<td>Max[args]</td>
<td><strong>Operator:</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Min.</td>
<td>Opcja zapewnia najmniejszy warunek. Jeśli liczba warunków wynosi 0 (zero), wówczas wartość to <strong>Infinity</strong>.</td>
<td>Min[args]</td>
<td><strong>Operator:</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Nie</td>
<td>Daje logiczną odwrotność danego warunku. To musi mieć dokładnie jeden warunek.</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</li>
<li><strong>Notacja infix:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

W następnej tabeli przedstawiono przykłady jak zapisać notację infix.


|  Notacja infix:   |                                          opis                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     x + y + z     |                                           Dodanie                                            |
|    x \* y \* z    |                                        Mnożenie                                         |
|       x - y       | Odejmowanie binarne jest tłumaczona tak samo, jak binarnego dodawanie z zanegowaniem drugiego. |
|     x ^ y ^ z     |                          Potęgowanie z łącznością do prawej                          |
|        !x         |                                          Wartość logiczna not                                          |
|      x -: y       |                                      Logiczna implikacja                                      |
|         x         |                                               y                                               |
|     x & y & z     |                                          Wartość logiczna and                                          |
|    x == y == z    |                                           Równość                                            |
|    x != y != z    |                                           Określone                                            |
|  x &lt; y &lt; z  |                                           Mniejsze niż                                           |
|  x &gt; y &gt; z  |                                         Większe niż                                          |
| x &lt;= y &lt;= z |                                     Mniejsze lub równe                                     |
| x &gt;= y &gt;= z |                                   Większe lub równe                                    |
|        (x)        |                           Nawiasy zastępują domyślny priorytet.                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>Dlaczego moje ograniczenia wyrażeń nie przechodzą pomyślnie sprawdzania poprawności?
Nie można używać zarezerwowanych słów kluczowych jako nazwy zamiennej dla atrybutów, komponentów czy podskładniki w modelu konfiguracji produktu. Oto lista zastrzeżonych słów kluczowych, których nie można używać:

-   Pułap
-   Element
-   Taka sama
-   Podłoga
-   Jeśli
-   Mniejsze
-   Większe
-   Implies
-   Dziennik
-   Maksimum
-   Minimum
-   Minus
-   Plus
-   Moc
-   Czasy
-   Przedział
-   Model
-   Decyzja
-   Cel


<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Tworzenie ograniczenia wyrażenia](tasks/add-expression-constraint-product-configuration-model.md)

[Dodawanie obliczenia do modelu konfiguracji produktu](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]