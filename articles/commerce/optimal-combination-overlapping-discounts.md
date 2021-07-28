---
title: Określenia optymalnej kombinacji rabatów nakładających się
description: Gdy rabaty się nakładają, należy określić taką kombinację nakładających się rabatów, która wygeneruje najniższą sumę transakcji lub najwyższy rabat końcowy. Gdy kwota rabatu różni się zależności od cen kupowanych produktów, taki jak w popularnym rabacie detalicznym „Kup 1, drugi dostaniesz X procent taniej” (BOGO), ten proces staje się zagadnieniem optymalizacji kombinatorycznej.
author: kfend
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount,
audience: Application User, IT Pro
ms.reviewer: josaw
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 51526c8409e0a04cf35e2dbd63cb4a3bd7d121e0
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352969"
---
# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a>Określenia optymalnej kombinacji rabatów nakładających się

[!include [banner](includes/banner.md)]

Gdy rabaty się nakładają, należy określić taką kombinację nakładających się rabatów, która wygeneruje najniższą sumę transakcji lub najwyższy rabat końcowy. Gdy kwota rabatu różni się zależności od cen kupowanych produktów, taki jak w popularnym rabacie detalicznym „Kup 1, drugi dostaniesz X procent taniej” (BOGO), ten proces staje się zagadnieniem optymalizacji kombinatorycznej.

Ten artykuł dotyczy Microsoft Dynamics AX 2012 R3 z bazy wiedzy KB 3105973 (wersja z 2 listopada 2015 r.) lub nowszej, oraz Dynamics 365 Commerce. Aby umożliwić bezzwłoczne stosowanie kombinacji nakładających się rabatów, wprowadziliśmy metodę stosowania nakładających się rabatów. Nazywamy tę nową metodę **rankingiem wartości krańcowej**. Ranking wartości krańcowej jest stosowany w przypadku, gdy czas potrzebny do ocenienia możliwych kombinacji nakładających się rabatów przekracza próg skonfigurowany na stronie **Parametry komercyjne**. W metodzie rankingu wartości krańcowej wartość jest obliczana dla każdego nakładającego się rabatu poprzez użycie wartość rabatu ze wspólnych produktów. Nakładające się rabaty są następnie stosowane w porządku od najwyższej wartości względnej do najniższej wartości względnej. Szczegółowe informacje na temat nowej metody zawiera sekcja „Wartość krańcowa” w dalszej części tego artykułu. Ranking wartości krańcowej nie jest używany, gdy kwoty rabatów na produkt są całkowicie niezależne od innych produktów w transakcji. Na przykład ta metoda nie jest używana dla dwóch rabatów prostych ani dla rabatu prostego i rabatu ilościowego na jeden produkt.

## <a name="discount-examples"></a>Przykłady rabatów

Można utworzyć nieograniczoną liczbę rabatów dla wspólnego zestawu produktów. Jednakże ponieważ nie ma żadnego limitu, mogą wystąpić problemy z działaniem systemu podczas próby obliczania rabatów, które powinny być używane do różnych produktów. Poniższe przykłady ilustrują ten problem bardziej szczegółowo. W przykładzie 1 zaczynamy od dwóch produktów i dwóch nakładających się rabatów. Następnie w przykładzie 2 pokażemy, jak problem się rozwija wraz z dodawaniem kolejnych produktów.

### <a name="example-1-two-products-and-two-discounts"></a>Przykład 1: Dwa produkty i dwa rabaty

W tym przykładzie są niezbędne dwa produkty, aby uzyskać każdy rabat, a rabaty nie mogą być łączone. Rabaty w tym przykładzie są typu **Najlepsza cena**. Oba produkty kwalifikują się do obu rabatów. Poniżej przedstawiono oba rabaty.

![Przykład dwóch rabatów z najlepszą ceną.](./media/overlapping-discount-combo-01.jpg)

Dla dowolnych dwóch produktów to, który rabat jest lepszy, zależy od cen tych produktów. Jeżeli cena obu produktów jest równa bądź prawie równa, lepszy jest rabat 1. Gdy cena jednego produktu jest znacznie niższa od ceny drugiego produktu, lepszy jest rabat 2. Oto matematyczna reguła oceniania tych dwóch rabatów względem siebie.

![Reguła szacowania rabatów.](./media/overlapping-discount-combo-02.jpg)

> [!NOTE]
> Gdy cena produktu 1 jest równa dwóm trzecim ceny produktu 2, rabaty są równe. W tym przykładzie efektywny procent rabatu 1 waha się od kilku procent (gdy ceny obu produktów są bardzo różne) do maksymalnie 25 procent (gdy dwa produkty mają taką samą cenę). Efektywny procent rabatu 2 jest stały. Zawsze wynosi 20 procent. Ponieważ efektywny procent rabatu 1 ma zakres, którego wartości mogą być wyższe lub niższe niż rabat 2, najlepszy rabat zależy od cen dwóch produktów, dla których ma zostać obliczony rabat. W tym przykładzie obliczanie kończy się szybko, ponieważ są stosowane tylko dwa rabaty tylko do dwóch produktów. Istnieją tylko dwie możliwe kombinacje: jedno zastosowanie rabatu 1 lub jedno zastosowanie rabatu 2. Nie ma permutacji do obliczenia. Wartość każdego rabatu jest obliczana przy użyciu obu produktów i jest stosowany najlepszych rabat.

### <a name="example-2-four-products-and-two-discounts"></a>Przykład 2: Cztery produkty i dwa rabaty

Następnie użyjemy czterech produktów i tych samych dwóch rabatów. Wszystkie cztery produkty kwalifikują się do obu rabatów. Istnieje dwanaście możliwych kombinacji. Na koniec do transakcji zostaną zastosowane dwa rabaty w jednej z trzech kombinacjach: dwa zastosowania rabatu 1, dwa zastosowania rabatu 2 lub jedno zastosowanie rabatu 1 i jedno zastosowanie rabatu 2. Aby zilustrować możliwe kombinacje, przyjrzymy się dwóm różnym zestawom czterech produktów o różnych cenach:

- Wszystkie cztery produkty mają taką samą cenę 15,00 USD. W takim przypadku najlepszą kombinacją rabatu są dwa zastosowania rabatu 1. Dwa produkty będą miały pełną cenę, a dwa cenę z rabatem 50 procent. Suma transakcji po rabacie wynosi 45 USD (15 + 15 + 7,50 + 7.50), czyli 15 USD (25 procent) mniej niż suma bez rabatu wynosząca 60 USD. Rabat 2 wynosi tylko 12 USD (20 procent).
- Dwa produkty kosztują 20 USD każdy, jeden kosztuje 15 USD, a jeden 5 USD. W takim przypadku najlepszą kombinacją rabatów jest jedno zastosowanie rabatu 2 i jedno zastosowanie rabatu 1. Poniższe tabele ilustrują rabaty.

Do odczytu tabel używaj jednego produktu z wiersza i jednego produktu z kolumny. Na przykład w tabeli rabatu 1 w przypadku połączenia dwóch produktów kosztujących 20 USD otrzymasz rabat 10 USD. W tabeli rabatu 2 w przypadku połączenia produktów kosztujących 15 USD i 5 USD otrzymasz rabat 4 USD.

![Przykład użycia czterech produktów dla tych samych dwóch rabatów.](./media/overlapping-discount-combo-03.jpg)

Najpierw znajdziemy największy rabat dostępny dla dowolnych dwóch produktów przy użyciu dowolnego rabatu. W dwóch tabelach przedstawiono kwotę rabatu dla wszystkich kombinacji dwóch produktów. Zacieniowane fragmenty tabel reprezentują przypadki, gdy produkt jest sparowany z samym sobą, czego nie można zrobić, lub odwrotne sparowanie dwóch produktów, które daje taką samą kwotę rabatu i może zostać zignorowane. Patrząc na tabele, można zobaczyć, że rabat 1 na dwa towary za 20 USD jest największym rabatem dostępnym wśród obu typów rabatu dla wszystkich czterech produktów. (Ten rabat jest wyróżniony na zielono w pierwszej tabeli). To pozostawia tylko produkty za 15 USD i 5 USD. Patrząc na dwie tabele ponownie, można zobaczyć, że dla tych dwóch produktów rabat 1 daje kwotę rabatu 2,50 USD, podczas gdy rabat 2 daje kwotę rabatu 4 USD. W związku z tym wybieramy rabat 2. Rabat końcowy wynosi 14 USD. Aby ułatwić wizualizację tej dyskusji, zamieszczamy dwie dodatkowe tabele, które pokazują efektywny procent rabatu dla wszystkich możliwych kombinacji dwóch produktów dla rabatów typu 1 i 2. Pokazujemy tylko połowę listy kombinacji, ponieważ kolejność stosowania obu rabatów do tych dwóch produktów nie ma znaczenia. Najwyższy efektywny rabat (25 procent) jest wyróżniony na zielono, a najniższy efektywny rabat (10 procent) jest wyróżniony kolorem czerwonym.

![Efektywna wartość procentowa rabatu dla wszystkich kombinacji dwóch produktów z tytułu obu rabatów.](./media/overlapping-discount-combo-04.jpg)

> [!NOTE]
> Gdy ceny się różnią, a dwa lub więcej rabatów konkurują ze sobą, jedynym sposobem zagwarantowania sobie najlepszej kombinacji rabatów jest ocena obu rabatów i ich porównanie.

## <a name="total-possible-combinations"></a>Łączna liczba możliwych kombinacji

W tej sekcji kontynuujemy przykład z poprzedniej sekcji. Dodamy więcej produktów i kolejny rabat i zobaczymy, ile kombinacji trzeba obliczyć i porównać. Poniższa tabela pokazuje liczbę możliwych kombinacji rabatów wraz ze wzrostem liczby produktów. W tabeli przedstawiono, co się dzieje, gdy istnieją dwa nakładające się rabaty, jak w poprzednim przykładzie, i gdy istnieją trzy nakładające się rabaty. Liczba możliwych kombinacji rabatów, które muszą zostać ocenione, wkrótce przekracza zdolności szybkiego komputera do obliczenia i porównania w tempie akceptowanym w transakcjach detalicznych.

![Liczba możliwych kombinacji rabatów wraz ze wzrostem liczby produktów.](./media/overlapping-discount-combo-05.jpg)

W przypadku jeszcze większej liczby produktów i nakładających się rabatów całkowita liczba możliwych kombinacji rabatów szybko sięga milionów i czas niezbędny do oceny i wybrania najlepszej kombinacji szybko staje się zauważalny. Dlatego w aparacie ustalania cen wprowadzono pewne optymalizacje, które zmniejszają łączną liczbę kombinacji wymagających oceny. Jednak ponieważ liczba nakładających się rabatów i ilości produktów w transakcjach są nieograniczone, zawsze trzeba oceniać dużą liczbę kombinacji, gdy tylko istnieją nakładające się rabaty. W celu rozwiązania tego problemu wprowadzono metodę rankingu wartości krańcowej.

## <a name="marginal-value-method"></a>Metoda wartości krańcowej

Aby rozwiązać problem lawinowo wzrastającej liczby kombinacji wymagających oceny, wprowadzono optymalizację, która oblicza wartość dla każdego wspólnego produktu w każdym rabacie w zbiorze produktów, do którego można zastosować dwa lub więcej rabatów. Nazywamy tę wartość **wartością krańcową** rabatu na wspólne produkty. Wartość krańcowa jest średnim wzrostem łącznej kwoty rabatu na każdy produkt, gdy w każdym rabacie występują wspólne produkty. Wartość krańcowa jest obliczana następująco: od łącznej kwoty rabatu (DTotal) jest odejmowana kwota rabatu bez wspólnych produktów (DMinus\\ Shared), a uzyskana różnica jest dzielona przez liczbę wspólnych produktów (ProductsShared).

![Formuła obliczania wartości krańcowej.](./media/overlapping-discount-combo-06.jpg)

Po obliczeniu wartości krańcowej każdego rabatu dla zbioru wspólnych produktów rabaty są stosowane do wspólnych produktów kolejno od najwyższej wartości krańcowej do najniższej wartości krańcowej. W przypadku tej metody wszystkie pozostałe możliwości rabatów nie są porównywane przy każdym stosowaniu jednego wystąpienia rabatu. Zamiast tego nakładające się rabaty są porównywane jeden raz, a następnie stosowane kolejno. Nie są wykonywane żadne inne porównania. Na stronie **Parametry sprzedaży** na karcie **Rabat** można skonfigurować próg przełączania na metodę wartości krańcowej. Dopuszczalny czas na obliczenie rabatu końcowego różni się w poszczególnych branżach wykorzystujących sprzedaż detaliczną. Jednakże zasadniczo wynosi on od kilkudziesięciu milisekund do jednej sekundy.


[!INCLUDE[footer-include](../includes/footer-banner.md)]