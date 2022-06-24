---
title: Księgowanie kosztów pośrednich
description: Ten artykuł wyjaśnia, jak księgować koszty pośrednie, tworzyć grupy kosztów i dodawać węzły do arkusza kalkulacji kosztów dla kosztów pośrednich.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostSheetDesigner, BOMCostGroup, ProjCategory, CostingVersion, CostSheetCalculationFactor
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 04af10760ec50d60cbbc31c233109dffb786933c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868439"
---
# <a name="indirect-cost-posting"></a>Księgowanie kosztów pośrednich

Koszty pośrednie to koszty, które nie są bezpośrednio związane z żadnym pojedynczym działaniem w procesie produkcji. Przykładem są koszty administracyjne, takie jak pensje pracowników, koszty działu księgowości oraz koszty ogólne, takie jak czynsz, media i koszty maszyn.

## <a name="calculating-indirect-costs"></a>Obliczanie kosztów pośrednich

Microsoft Dynamics 365 Finance nie ma zautomatyzowanego sposobu obliczania stawki dla kosztów pośrednich. Musisz określić swoje koszty pośrednie, stworzyć kody kosztów pośrednich i utrzymać stawkę dla każdego kosztu pośredniego w arkuszu kalkulacyjnym.

Dokładny proces, który jest używany do obliczania kosztów pośrednich, może się nieco różnić w zależności od firmy. Jednak ogólnie rzecz biorąc, proces składa się z następujących podstawowych kroków:

1. Stwórz listę kosztów pośrednich do rozpoznania w produkcji. Lista ta może zawierać czynsz, wydatki administracyjne, opłaty księgowe i prawne. Nie powinna ona zawierać kosztów surowców ani kosztów pracy, które są rozpoznawane w trasach produkcyjnych.
2. Zsumuj wszystkie koszty pośrednie. Możesz grupować podobne rodzaje kosztów pośrednich lub oddzielać je od siebie. Każdy skonfigurowany koszt pośredni może mieć różne konta główne, które są używane do księgowania w księdze głównej.
3. Porównaj koszty pośrednie ze współczynnikiem, który jest też nazywany podstawą absorpcji. Czynnikiem może być wszystko, co wybierzesz. Oto kilka często występujących przykładów:

    - Przychód
    - Całkowita wyprodukowana ilość
    - Czas przezbrajania
    - Czas procesu

    Możesz wybrać okres, dla którego chcesz obliczać koszty pośrednie, np. miesięczny, kwartalny lub roczny. Suma twoich kosztów pośrednich i suma twojego czynnika powinny dotyczyć tej samej ilości czasu. Do obliczenia stawki kosztów pośrednich używa się następującego wzoru:

    *Stawka kosztów pośrednich* = *całkowite koszty pośrednie* &divide; *Całkowity współczynnik*

4. Utwórz grupy kosztów pośrednich.
5. Skonfiguruj arkusz kalkulacji kosztów z twoimi stawkami.
6. Utrzymuj koszty pośrednie w wersji kalkulacji kosztów.

> [!NOTE]
> Możesz użyć modułu **Księgowanie kosztów** do gromadzenia kosztów i określania kosztów ogólnych z różnych źródeł, takich jak produkcja, projekty i księga główna. Aby uzyskać więcej informacji, zobacz [Rachunek kosztów](/cost-accounting/cost-accounting-home-page.md).

> [!IMPORTANT]
> Różne instytucje regulacyjne opublikowały wytyczne dotyczące rodzajów kosztów, które mogą być włączone jako koszty pośrednie lub koszty ogólne do kosztu twoich wyrobów gotowych. Zanim zaczniesz konfigurować koszty pośrednie, radzimy, byś skonsultował się ze swoim księgowym oraz z lokalnymi przepisami, by upewnić się, że działasz zgodnie z nimi.

## <a name="create-cost-groups-for-indirect-costs"></a>Utwórz grupy kosztów dla kosztów pośrednich

Musisz utworzyć co najmniej jedną grupę kosztów, która będzie używana dla kosztów pośrednich. Nie ma ograniczeń co do liczby grup kosztów, których możesz używać. Zastanów się, jak obliczasz swoje koszty i czy istnieją różne stawki dla różnych rodzajów kosztów. Na przykład Twoja organizacja produkuje artykuły spożywcze. Niektóre surowce i wyroby gotowe są towarami suchymi i mają jeden koszt pośredni za magazynowanie. Inne surowce i wyroby gotowe są chłodzone i mają wyższy koszt pośredni. W tym przypadku możesz chcieć utworzyć dwie grupy kosztów: **Koszty ogólne materiałów suchych** i **Koszty ogólne materiałów chłodzonych**.

Aby utworzyć grupę kosztów dla kosztów pośrednich, wykonaj poniższe kroki.

1. Wybierz kolejno opcje **Kontrola produkcji &gt; Ustawienia &gt; Marszruty &gt; Grupy marszrut**.
2. Wybierz **Nowy**, aby utworzyć grupę.
3. W polu **Grupa kosztowa** wprowadź unikalną nazwę dla grupy kosztów, np. **MATOVH**.
4. W polu **Nazwa** wprowadź opis grupy kosztów, np. **Koszty ogólne materiałów**.
5. W polu **Typ kodu strony** wybierz opcję **Niebezpośredni**.
6. Opcjonalnie: W polu **Zachowanie** wybierz **Koszt stały** lub **Koszt zmienny**.

## <a name="configure-the-costing-sheet-for-indirect-costs"></a>Skonfiguruj arkusz kalkulacji kosztów dla kosztów pośrednich

Po utworzeniu jednej lub kilku grup kosztów możesz skonfigurować arkusz kalkulacyjny z kosztami pośrednimi i określić sposób ich wyliczania. Możesz chcieć pogrupować koszty pośrednie w arkuszu kalkulacji kosztów. Aby pogrupować koszty pośrednie, możesz utworzyć opcjonalny nagłówek w arkuszu kalkulacji kosztów. Musisz utworzyć co najmniej jeden węzeł dla każdej grupy kosztów w arkuszu kalkulacji kosztów. Dla każdej grupy kosztów dla kosztów pośrednich możesz dodać jeszcze jedną kalkulację kosztów pośrednich.

### <a name="indirect-cost-node-types"></a>Typy węzłów kosztów pośrednich

Ta sekcja opisuje różne typy węzłów kosztów pośrednich.

#### <a name="surcharge"></a>Dopłata

**Dopłata** to jeden z najczęstszych rodzajów kosztów pośrednich. Oblicza procent kosztów na podstawie absorpcji kosztów na zleceniu produkcyjnym. Definiujesz podstawę absorpcji, wybierając grupy kosztów, które są powiązane z komponentami materiałowymi lub czasowymi w arkuszu kalkulacji kosztów.

Na przykład 3-procentowy narzut może być doliczony do kosztu produkcji dla wszystkich surowców w zamówieniu produkcyjnym.

#### <a name="rate"></a>Stawka

Koszt pośredni typu **Sstawka** jest używany do dodania stałej kwoty kosztu do zlecenia produkcyjnego z podstawy absorpcji kosztów na zleceniu produkcyjnym. Wskaźnik może być oparty na jednym z trzech podtypów:

- **Proces** – Stawka jest zależna od czasu biegu na trasie.
- **Konfiguracja** – Stawka jest zależna od czasu ustawienia na trasie.
- **Ilość** – stawka jest oparta na wyprodukowanej ilości.

Definiujesz podstawę absorpcji, wybierając grupy kosztów, które są powiązane z komponentami materiałowymi lub czasowymi w arkuszu kalkulacji kosztów.

Na przykład stała kwota 2,00 dolarów amerykańskich (USD) jest dodawana do każdego zlecenia produkcyjnego na podstawie czasu przebiegu w trasie dla grupy kosztów pracy w twoim arkuszu kalkulacji kosztów.

#### <a name="output-unit-based"></a>Jednostkowy koszt na wyjściu

Koszt pośredni typu **Jednostka wyjściowa** jest obliczany przez pomnożenie kwoty, która jest określona na skróconej karcie **Stawka** arkusza kalkulacji kosztów, przez wybrany podtyp. Jako mnożnik kosztu pośredniego możesz wybrać ilość, wagę lub objętość gotowego wyrobu.

Na przykład, wykorzystujesz tę ilość do obliczenia 1,50 USD amortyzacji maszyny dla każdej wyprodukowanej ilości. Inny przykład: używasz objętości do obliczenia 2,00 USD kosztów chłodzenia za objętość przestrzeni, którą zajmują gotowe produkty w twoich urządzeniach chłodniczych.

#### <a name="input-unit-based"></a>Jednostkowy koszt na wejściu

Koszt pośredni typu **Na podstawie jednostki wejściowej** jest obliczany poprzez pomnożenie ilości surowców zużytych na zlecenie produkcyjne przez pewną kwotę. Do obliczenia sumy możesz wykorzystać wagę lub objętość składników zlecenia produkcyjnego. Możesz ograniczyć kalkulację do podzbioru materiałów, wybierając jedną lub więcej grup kosztów w zakładce **Podstawa absorpcji** w arkuszu kalkulacji kosztów.

Na przykład, aby dodać 1,00 USD do zlecenia produkcyjnego, używasz wielkości nakładów dla określonej grupy kosztów, która jest powiązana z produktami chłodzonymi.

### <a name="create-a-total-node-for-indirect-costs-in-the-costing-sheet"></a>Utwórz węzeł sumy dla kosztów pośrednich w arkuszu kalkulacji kosztów

Aby utworzyć węzeł sumy dla kosztów pośrednich w arkuszu kalkulacji kosztów, wykonaj poniższe kroki.

1. Przejdź do pozycji **Zarządzanie kosztami &gt; Rachunek kosztów pośrednich &gt; Arkusz kalkulacyjny**.
2. W drzewie wybierz węzeł, który reprezentuje koszt wyprodukowanych dóbr.
3. Wybierz **Nowy**, aby utworzyć węzeł.
4. W polu **Wybierz typ węzła** zaznacz opcję **Łącznie**.
5. W polu **Kod** wpisz unikalny identyfikator węzła, na przykład **Koszty Produkcji**.
6. Zaznacz pole wyboru **Nagłówek**.
7. Zaznacz pole wyboru **Łącznie**.
8. Kliknij przycisk **OK**.

### <a name="create-an-indirect-cost-group-node-in-the-costing-sheet"></a>Utwórz węzeł grupy kosztów pośrednich w arkuszu kalkulacji kosztów

Aby utworzyć węzeł grupy kosztów pośrednich w arkuszu kalkulacji kosztów, wykonaj poniższe kroki.

1. Przejdź do pozycji **Zarządzanie kosztami &gt; Rachunek kosztów pośrednich &gt; Arkusz kalkulacyjny**.
2. W drzewie wybierz węzeł, pod którym chcesz utworzyć koszt pośredni. Na przykład wybierz węzeł całkowity dla **Kosztów produkcji**.
3. Wybierz **Nowy**, aby utworzyć węzeł.
4. W polu **Wybierz typ węzła** wybierz opcję **Grupa kosztowa**.
5. W polu **Kod** wpisz unikalny identyfikator węzła, na przykład **TRANSP**.
6. W polu **Opis** wpisz krótki opis, na przykład **Nadwyżka transportowa**.
7. Kliknij przycisk **OK**.
8. W polu **Grupa kosztów** wybierz grupę kosztów, na przykład **OVH1: koszty ogólne transportu**.

### <a name="create-a-surcharge-indirect-cost"></a>Utwórz koszt pośredni dopłaty

Aby utworzyć koszt pośredni dopłaty w swoim arkuszu kalkulacji kosztów, wykonaj poniższe kroki.

1. Przejdź do pozycji **Zarządzanie kosztami &gt; Rachunek kosztów pośrednich &gt; Arkusz kalkulacyjny**.
2. W drzewie wybierz węzeł grupy kosztów pośrednich, pod którym chcesz utworzyć koszt pośredni. Na przykład wybierz węzeł całkowity dla **TRANSP - Koszty ogólne transportu**.
3. Wybierz **Nowy**, aby utworzyć węzeł.
4. W polu **Wybierz typ węzła** zaznacz opcję **Dopłata**.
5. W polu **Kod** wpisz unikalny identyfikator węzła, na przykład **Dopłata transportowa**.
6. Kliknij przycisk **OK**.
7. W polu **Podtyp** wybierz **Ogółem**.
8. Na skróconej karcie **Podstawa absorpcji** wybierz **Nowe**, aby utworzyć kod kosztu.
9. W polu **Kod** wybierz grupę kosztów, która będzie używana do obliczania dopłat.
10. Opcjonalnie: Powtórz kroki od 8 do 9 dla każdej dodatkowej grupy kosztów, którą chcesz wykorzystać do kalkulacji.
11. Na skróconej karcie **Dopłata** wybierz **Nowe**, aby utworzyć stawkę.
12. W polu **Wersja** wybierz wersję kosztorysu, do której chcesz dodać dopłatę.
13. Opcjonalnie: w polu **Lokacja** wprowadź miejsce, do których mają być stosowane dopłaty.
14. W polu **Procent** wpisz wartość procentową, która ma być obliczana dla zleceń produkcyjnych na podstawie grup kosztów zdefiniowanych na karcie **Podstawie absorpcji**.
15. Na skróconej karcie **Księgi rachunkowe** wybierz konto główne, które ma być używane w polach **Oszacowany koszt pośredni pochłonięty**, **Oszacowany koszt pośredni zużyty, WIP**, **Koszt pośredni pochłonięty** i **Koszt pośredni zużyty, WIP**.
16. Opcjonalnie: Na skróconej karcie **Wymiary finansowe** określ wymiary finansowe, które mają być domyślnie wprowadzane do transakcji podczas księgowania ich w księdze głównej.

Powyższa procedura pokazuje, jak utworzyć koszt pośredni typu **Dopłata**. Podobne kroki stosuje się przy tworzeniu innych rodzajów kosztów pośrednich. Poniższe sekcje opisują różnice pomiędzy poszczególnymi typami.

#### <a name="rate"></a>Stawka

- W kroku 4 wybierz **Stawka** zamiast **Dopłata**.
- W kroku 7 wybierz **Proces**, **Ustawienie** lub **Ilość** zamiast **Ogółem**.
- W kroku 11 użyj skróconej karty **Stawka** zamiast **Dopłata**.
- W kroku 14 wpisz kwotę w polu **Kwota** zamiast wartości procentowej w polu **Procent**.

#### <a name="output-unit-based"></a>Jednostkowy koszt na wyjściu

- W kroku 4 wybierz **Jednostkę wydajności** zamiast **Dopłaty**.
- W kroku 7 wybierz **Ilość**, **Waga** lub **Objętość** zamiast **Ogółem**.
- Omiń kroki od 8 do 10.
- W kroku 11 użyj skróconej karty **Stawka** zamiast **Dopłata**.

#### <a name="input-unit-based"></a>Jednostkowy koszt na wejściu

- W kroku 4 wybierz **Na podstawie jednostki wejściowej** zamiast **Dopłaty**.
- W kroku 7 wybierz **Waga** lub **Objętość** zamiast **Ogółem**.
- W kroku 11 użyj skróconej karty **Stawka** zamiast **Dopłata**.
