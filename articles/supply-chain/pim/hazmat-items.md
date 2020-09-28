---
title: Materiały niebezpieczne w produktach, zamówieniach, wysyłkach i ładunkach
description: W tym temacie opisano sposób ustawiania właściwości dot. niebezpiecznych materiałów dla wydawanych produktów, określania limitów magazynowych dotyczących towarów niebezpiecznych oraz sposobu uwzględniania materiałów niebezpiecznych w zamówieniu sprzedaży, wysyłce lub ładunku.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: d3573aa5f8f986fa4fbf1c9ea8b322a1256aee36
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803196"
---
# <a name="hazardous-materials-in-products-orders-shipments-and-loads"></a>Materiały niebezpieczne w produktach, zamówieniach, wysyłkach i ładunkach

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie opisano sposób ustawiania właściwości dot. niebezpiecznych materiałów dla wydawanych produktów, określania limitów magazynowych dotyczących towarów niebezpiecznych oraz sposobu uwzględniania materiałów niebezpiecznych w zamówieniu sprzedaży, wysyłce lub ładunku.

## <a name="set-hazardous-material-specifications-for-products"></a>Określanie specyfikacji materiałów niebezpiecznych dla produktów

Po określeniu odpowiednich przepisów dot. materiałów niebezpiecznych i skonfigurowaniu odpowiednich kodów odwołań zgodnie z opisem w temacie [Konfigurowanie materiałów niebezpiecznych](hazmat-setup.md) można powiązać te informacje z wydawanymi towarami. Tekst wysyłki dla dokumentów dostawy zostanie wystawiony na podstawie informacji o niebezpiecznych materiałach dot. zwolnionych towarów.

W ramach procesu przypisywania zwolnionego towaru statusu materiału niebezpiecznego, należy określić kod rozporządzenia i materiał. Różne kody regulacyjne mogą być przypisane do towaru, w zależności od typu transportu, a dla każdego towaru można skojarzyć wiele rozporządzeń i kodów materiałów.

Aby skonfigurować zwolniony produkt jako materiał niebezpieczny, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz lub utwórz produkt, aby otworzyć jego stronę **Szczegółów zwolnionego produktu**.
1. Na skróconej karcie **Zarządzania zapasami** ustaw opcje **Materiały niebezpieczne** na **Tak**. To ustawienie identyfikuje towar jako niebezpieczny i jest używane przy drukowaniu dokumentacji przewozowej.
1. W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Zgodność** wybierz **Produkt — materiał niebezpieczny**.
1. Wypełnij stronę **Produkt — materiał niebezpieczny** dla wybranego przedmiotu, korzystając z pól opisanych w poniższych podsekcjach.

### <a name="item-hazardous-materials-header"></a>Nagłówek materiałów niebezpiecznych dla pozycji

W poniższej tabeli opisano pola dostępne u góry strony **Produkt — materiały niebezpieczne**.

| Pole | opis |
|---|---|
| Identyfikator towaru | Zwolniony produkt, z którym pracuje użytkownik. |
| Kod przepisu | Umożliwia wybór rozporządzenia dotyczącego materiałów niebezpiecznych, które ma zastosowanie do danego produktu. Rozporządzenie określa sposób tworzenia drukowanego tekstu wysyłki dla towaru i skojarzonych z nim opcji dostawy. Po jego przypisaniu kod nie może być edytowany na tej stronie. Można jednak przypisać nowy kod rozporządzenia, wybierając opcję **Nowy**. |
| Kod materiałów | (Opcjonalnie) Umożliwia wybór kodu dotyczącego materiałów niebezpiecznych, które ma zastosowanie do danego produktu. Kod materiału zawiera szablon zawierający wartości domyślne dla wielu innych pól na tej stronie. Po wybraniu kodu wszystkie jego specyfikacje dotyczące materiałów niebezpiecznych zostaną skopiowane do bieżącego produktu. System najpierw prosi o potwierdzenie, że dane materiału towaru powinny być wypełnione na podstawie kodu materiału. |
| Kod grupy | (Opcjonalnie) Umożliwia wybór grupy klasyfikacji dotyczącej materiałów niebezpiecznych, która ma zastosowanie do danego produktu. Jeśli chodzi o pole **Kod materiału**, po wybraniu kodu wszystkie jego specyfikacje dotyczące materiałów niebezpiecznych zostaną skopiowane do bieżącego produktu. System najpierw prosi o potwierdzenie, że dane grupy klasy towaru powinny być wypełnione na podstawie kodu grupy. |

### <a name="descriptions-fasttab"></a><a name="hazmat-description"></a>Skrócona karta Opisy

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Opisy**.

| Pole | opis |
|---|---|
| Właściwa nazwa wysyłki | Wprowadź standardowy opis materiału, jak określono to w odpowiednim rozporządzeniu. Istnieje możliwość dostarczenia tłumaczeń dla tej wartości na skróconej karcie **Tłumaczenie tekstu dostawy przedmiotu**, tak jak opisano w następnej sekcji. |
| Nazwa techniczna | Wybierz nazwę pospolitą lub ogólną dla materiału. Ta nazwa może być ta sama nazwa, której firma używa wewnętrznie w odniesieniu do danego materiału. |
| Nieokreślone inaczej | To pole wyboru należy zaznaczyć, aby wskazać, że **Właściwa nazwa wysyłki** jest nazwą nieokreśloną inaczej dla tego towaru. Nieokreślone inaczej nazwy wysyłkowe są używane dla grup podobnych chemikaliów i materiałów, które mają określone zastosowania końcowe, ale mogą nie być wymienione na liście w tabeli materiałów niebezpiecznych w określonym rozporządzeniu. |

### <a name="item-ship-text-translation-fasttab"></a>Skrócona karta tłumaczenia tekstu opisu przedmiotu

Skrócona karta **Tłumaczenie tekstu opisu przedmiotu** zawiera siatkę, w której są wyświetlane tłumaczenia wartości **Właściwych nazw wysyłkowych**, które zostały zdefiniowane dla języka podstawowego na skróconej karcie **Opisy**. Te tłumaczenia mogą być używane podczas drukowania tekstu dla jednego lub kilku dodatkowych języków.

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Tłumaczenie tekstu opisu przedmiotu**.


| Pole | opis |
|---|---|
| Język | Kod języka używany w wierszu. Na przykład **pt-br** oznacza brazylijski portugalski. |
| Drukuj tekst wysyłki | Przetłumaczona wartość **Właściwej nazwy wysyłki** w języku, którego używa wiersz. |

Aby dodać lub edytować tłumaczenie, wybierz opcję **Tłumaczenia** powyżej siatki, aby otworzyć stronę **Tłumaczenia tekstu**. Następnie wykonaj jeden z następujących kroków:

- Aby dodać nowe tłumaczenie, w okienku akcji wybierz opcję **Dodaj**. Wybierz język, który ma zostać dodany, a następnie w polu **Przetłumaczony tekst** wprowadź przetłumaczony tekst.
- Aby edytować istniejące tłumaczenie, wybierz język docelowy w polu **Język** i wprowadź zmiany w polu **Przetłumaczony tekst**.

### <a name="material-management-fasttab"></a><a name="material-management"></a>Skrócona karta zarządzania materiałami

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Zarządzanie materiałami**.

| Pole | opis |
|---|---|
| Klasa | Umożliwia wybranie klasy materiałów niebezpiecznych, do której należy produkt, zgodnie z definicją podaną w rozporządzeniu, którego przestrzega system. Należy przypisać zarówno oddział, jak i klasę do każdego produktu zawierającego materiały niebezpieczne. |
| opis | Opis, który jest zdefiniowany dla klasy wybranej w polu **Klasa**. To pole jest przeznaczone tylko do odczytu. |
| Oddział | Umożliwia wybranie przedziału materiałów niebezpiecznych, do którego należy produkt, zgodnie z definicją podaną w rozporządzeniu, którego przestrzega system. Przedział jest podzestawem klasy. Należy przypisać zarówno oddział, jak i klasę do każdego produktu zawierającego materiały niebezpieczne. |
| Identyfikator | Wybierz kod identyfikacji materiałów niebezpiecznych. Zazwyczaj ten kod jest oparty na standardzie ONZ. |
| Grupa załadunkowa | Umożliwia wybór grupy załadunkowej stosowanej do bieżącego towaru. |
| opis | Opis, który jest zdefiniowany dla grupy wybranej w polu **Grupa pakowania**. To pole jest przeznaczone tylko do odczytu. |
| Opisy opakowań | Umożliwia wybór odpowiedniego kodu opisu dostawy. Ten kod odwołuje się do opisu, który wskazuje, w jaki sposób produkt musi zostać spakowany. |
| Materiały niebezpieczne — etykiety | Umożliwia wybranie kodu odwołującego się do odpowiedniej etykiety towarów niebezpiecznych, która powinna zostać zastosowana do produktu. |
| Ilość ograniczona | Ustawienie tej opcji na wartość **Tak** powoduje zgłaszanie łącznej wagi produktu zawartej w każdym ładunku i każdym wierszu ładunku. |
| Ilość | Służy do wprowadzania ilości niebezpiecznego materiału w danym produkcie, w określonej jednostce miary. Ta wartość będzie używana do obliczania całkowitej niebezpiecznego wyniku materiału dla ładunków i wysyłek zawierających produkt. |
| Mnożnik | Umożliwia wprowadzenie mnożnika stosowanego podczas obliczania wyniku niebezpiecznego materiału dla każdego wiersza ładunku zawierającego produkt. Wartość ta jest określana przez odpowiednie rozporządzenie, zgodnie z typem materiału niebezpiecznego, który jest zawarty w produkcie. |
| Jednostka | Umożliwia wybranie jednostki miary stosowanej do określenia ilości materiału niebezpiecznego w produkcie, określonego w polu **Ilość**. Ta wartość będzie używana do obliczania całkowitej niebezpiecznego wyniku materiału dla ładunków i wysyłek zawierających produkt. |

#### <a name="how-the-hazardous-material-score-is-calculated"></a>Sposób obliczania oceny materiały niebezpiecznego

Wartości określone na skróconej karcie **Zarządzania materiałami** dla danego produktu jest używane do obliczenia *oceny materiały niebezpiecznego* dla każdego wiersza ładunku zawierającego dany produkt. Rachunki są obliczane za pomocą następującego wzoru:

Ocena materiału niebezpiecznego = *&lt;IlośćLin&gt;* × *&lt;IlośćNieb&gt;* × *&lt;KonwersjaJednostki&gt;* × *&lt;Mnożnik&gt;*

Oto klucz formuły:

- *&lt;IlośćLIn&gt;* to ilość produktu w wierszu ładunku.
- *&lt;IlośćNieb&gt;* to ilość materiału niebezpiecznego, która została określona dla produktu w polu **Ilość** na skróconej karcie **Zarządzania materiałami**.
- *&lt;KonwersjaJednostki&gt;* jest współczynnikiem konwersji jednostki używanej dla ilości w wierszu ładunku i jednostki określonej dla produktu w polu **Jednostka** na skróconej karcie **Zarządzanie materiałami**.
- *&lt;Mnożnik&gt;* to mnożnik określony dla produktu w polu **Mnożnik** na skróconej karcie **Zarządzania materiałami**.

Ten wynik jest zgłaszany dla każdego wiersza ładunku zawierającego produkt, w którym te wartości są określone. Aby uzyskać więcej informacji, zajrzyj do tematu [Dostawy zawierające materiały niebezpieczne](#hazmat-shipments) oraz [Ładunki zawierające materiały niebezpieczne](#hazmat-loads), które znajdują się w dalszej części tego tematu.

#### <a name="how-the-hazardous-material-weight-is-calculated"></a>Sposób obliczania ciężaru materiały niebezpiecznego

Ładowanie i wiersze ładowania zawierające produkty, w których opcja **Ograniczona ilość** na skróconej karcie **Zarządzania materiałami** jest ustawiona na wartość **Tak**, spowoduje wyświetlenie całkowitej wagi materiału niebezpiecznego, zgodnie z opisem w sekcjach [Dostawy zawierające materiały niebezpieczne](#hazmat-shipments) oraz [Ładunki zawierające materiały niebezpieczne](#hazmat-loads), które znajdują się w dalszej części tego tematu. Waga materiału niebezpiecznego jest obliczana za pomocą następującego wzoru:

Waga materiału niebezpiecznego = *&lt;IlośćLin&gt;* × *&lt;WagaProd&gt;* × *&lt;JednostkaKonwersji&gt;*

Oto klucz formuły:

- *&lt;IlośćLIn&gt;* to ilość produktu w wierszu ładunku.
- *&lt;WagaProduktu&gt;* jest wagą netto określoną dla produktu w jednostce magazynowej określonej dla produktu.
- *&lt;JednostkaKonwersji&gt;* jest wskaźnikiem konwersji służącym do konwersji jednostki używanej dla ilości w wierszu ładunku i jednostki magazynowej używanej dla *&lt;WagiProduktu&gt;*.

### <a name="transport-information-fasttab"></a>Skrócona karta pt. Informacje o transporcie

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Informacje o transporcie**.

| Pole | opis |
|---|---|
| Kategoria transportu | Umożliwia wybór powiązanej kategorii transportu. |
| Kod tunelu | Umożliwia wybranie powiązanego kodu ograniczenia tunelu dla danego towaru. |
| Rozmieszczenie materiałów niebezpiecznych | Umożliwia wybranie kodu odwołania używanego do obsługi załadunkowego transportu morskiego, gdy towar jest w ramach transportu morskiego. |
| Typ samolotu | Umożliwia wybór ograniczenia dotyczącego materiału, który ma zastosowanie do materiału, gdy jest wysyłany w ramach frachtu lotniczego. |
| Pakowanie — tylko samolot transportowy | Na podstawie wartości wybranej w polu **Typ statku powietrznego** wybierz kod instrukcji pakowania, który ma zastosowanie w przypadku, gdy produkt może zostać wysłany tylko w ramach transportu lotniczego. |
| Pakowanie — samoloty pasażerskie i transportowe | Na podstawie wartości wybranej w polu **Typ statku powietrznego** wybierz kod instrukcji pakowania, który ma zastosowanie w przypadku, gdy produkt może zostać wysłany w ramach transportu lotniczego lub lotniczego transportu pasażerskiego. |
| Międzynarodowego Zrzeszenia Przewoźników Powietrznych i Star Alliance | Ustawienie tej opcji na wartość **Tak** wskazuje, że specyfikacje transportu lotniczego wprowadzone na tej skróconej karcie są związane regulacjami dotyczącymi towarów niebezpiecznych międzynarodowego zrzeszenia przewoźników powietrznych (IATA). To pole jest używane wyłącznie w celach informacyjnych. |
| Reakcja na sytuacje awaryjne | Wybierz kod, który odwołuje się do instrukcji obsługi materiału w nagłych przypadkach. |

### <a name="environmental-information-fasttab"></a>Skrócona karta informacji o środowisku

W poniższej tabeli przedstawiono pola dostępne na skróconej karcie **Informacje o środowisku**.

| Pole | opis |
|---|---|
| Niebezpieczne dla środowiska | Ustawienie tej opcji na wartość **Tak** oznacza, że produkt jest niebezpieczny dla środowiska. To pole służy do tworzenia własnych celów raportowania. |
| Substancja mogąca spowodować zanieczyszczenie morza | Ustawienie tej opcji na wartość **Tak** oznacza, że produkt może stanowić zanieczyszczenie dla zbiorników wodnych. To pole służy do tworzenia własnych celów raportowania. |

## <a name="set-stock-limits-for-hazardous-products"></a><a name="stock-limits"></a>Ustawienie limitów zapasów dla produktów niebezpiecznych

Ze względów bezpieczeństwa konieczne może być ograniczenie całkowitej ilości danego produktu, który może być składowany w jednym miejscu. Aby skonfigurować limity zapasów produktu, należy wykonać następujące czynności.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt, aby otworzyć jego stronę **Szczegółów zwolnionego produktu**.
1. W Okienku akcji na karcie **Zarządzaj zapasami** w grupie **Zgodność** wybierz **Szczegóły raportowania**.
1. W polach **Limit zapasów niebezpiecznych** i **Limit ostrzegawczy materiałów niebezpiecznych** należy określić odpowiednie wartości dla wybranego produktu.

Raport o **Limicie zapasów materiałów niebezpiecznych** umożliwia monitorowanie poziomów zapasów niebezpiecznych materiałów w lokalizacjach magazynowych w celu upewnienia się, że pozostaną one w ramach wyznaczonych limitów, które zostały tutaj określone. Aby uzyskać więcej informacji, zajrzyj do [Raportu dot. limitu zapasów materiałów niebezpiecznych](hazmat-reports.md#stock-limit-report).

## <a name="sales-order-transactions-that-include-hazardous-materials"></a>Transakcje zamówienia sprzedaży zawierające materiały niebezpieczne

Aby uwzględnić produkt, który jest zaklasyfikowany jako materiał niebezpieczny na zamówieniu sprzedaży, należy skojarzyć odpowiedniego przewoźnika z zamówieniem sprzedaży. Otwórz zamówienie sprzedaży, a następnie na skróconej karcie **Dostawy** ustaw pola **Przewoźnik transportowy** i **Usługa dostawy** zgodnie z wymaganiami.

Przewoźnik transportowy jest również skojarzony z trybem dostawy. Dlatego należy upewnić się, że te informacje są zgodne z przepisami dotyczącymi materiałów niebezpiecznych. Innymi słowy, metoda dostawy określona w rozporządzeniu dotyczącym materiałów niebezpiecznych musi być zgodna ze specyfikacją w nagłówku zamówienia sprzedaży. W ten sposób rozporządzenie, przewoźnik wysyłki i usługa są połączone z wierszami wysyłki używanymi w zamówieniu sprzedaży.

Po sfinalizowaniu i przygotowaniu zamówienia sprzedaży do wysłania można je zwolnić do magazynu w celu wskazania przeniesienia między operacjami sprzedaży i magazynowymi.

## <a name="shipments-that-include-hazardous-materials"></a><a name="hazmat-shipments"></a>Wysyłki, które zawierają materiały niebezpieczne

### <a name="view-hazardous-material-scores-for-each-shipment-line"></a>Wyświetl wyniki oceny materiałów niebezpiecznych dla każdego wiersza wysyłki

Na stronie **Szczegóły wysyłki** dla wysyłki wyświetlana jest całkowita waga materiału niebezpiecznego i wartości punktów, które zostały obliczone dla każdego wiersza ładunku, który jest uwzględniony w tej wysyłce. Aby wyświetlić wyniki i wagi, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Wybierz wysyłkę, aby otworzyć stronę **Szczegółów wysyłki**.
1. Na skróconej karcie **Wierszy ładunku** sprawdź wiersze. Dla każdego wiersza zostaną wyświetlone obliczenia materiałów niebezpiecznych w następujących polach:

    - **Punkty niebezpiecznego materiału** — w tym polu jest wyświetlana ocena materiału niebezpiecznego dla wiersza ładunku. Wartość jest obliczana zgodnie z regułami i wartościami określonymi dla odpowiedniego rozporządzenia i w konfiguracji zwolnionego produktu. Obliczenie pobiera ilość w wierszu ładunku i odwołuje się do mnożnika w [konfiguracji zarządzania materiałami](#material-management) dla zwolnionego produktu.
    - **Waga netto ograniczonej ilości** — dla produktów oznaczonych jako produkty z ograniczoną ilością ze względu na niebezpieczną zawartość materiału, w tym polu jest wyświetlana łączna waga netto zawartości niebezpiecznej, która jest uwzględniona w wierszu ładunku. Obliczenia są oparte na produktach oznaczonych jako materiały niebezpieczne w konfiguracji zwolnionego produktu. Jeśli towar jest oznaczony jako towar o ograniczonej ilości, obliczenie pobiera ilość w każdym wierszu ładunku i odwołuje się do wagi w [ustawieniach zarządzania materiałami](#material-management) dla zwolnionego produktu.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-shipment"></a>Sprawdzanie zgodności materiałów niebezpiecznych uwzględnionych w wysyłce

System może ocenić, czy wszystkie niebezpieczne materiały uwzględnione w wysyłce mogą być wysłane razem. Aby ocenić zgodność, system sprawdza grupę zgodności przypisaną do każdego produktu, który jest uwzględniony w wysyłce. Aby uzyskać więcej informacji, zajrzyj do [Grupy zgodności materiałów niebezpiecznych](hazmat-setup.md#compatibility-groups).

Aby uruchomić narzędzie do sprawdzenia zgodności, postępuj zgodnie z instrukcjami poniżej.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Wybierz wysyłkę, aby otworzyć stronę **Szczegółów wysyłki**.
1. W okienku akcji na karcie **Dostawy** w grupie **Działania** wybierz opcję **Sprawdzenie zgodności**.

Zostanie wyświetlony komunikat informujący o wynikach kontroli.

## <a name="loads-that-include-hazardous-materials"></a><a name="hazmat-loads"></a>Ładunki, które zawierają materiały niebezpieczne

### <a name="view-hazardous-material-scores-for-each-load-line"></a>Wyświetl wyniki oceny materiałów niebezpiecznych dla każdego wiersza ładunku

Na stronie **Szczegóły ładunku** dla ładunku wyświetlana jest całkowita waga materiału niebezpiecznego i wartości punktów, które zostały obliczone dla każdego wiersza ładunku i dla tego ładunku. Aby wyświetlić wyniki i wagi, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie ładunki**.
1. Wybierz ładunek, aby otworzyć stronę **Szczegółów ładunku**. (Możesz również otworzyć szczegóły ładunku, wybierając łącze z pokrewnej wysyłki.)
1. Na skróconej karcie **Ładunku** można przejrzeć całkowite wyniki oceny i wagi materiałów niebezpiecznych dla całego ładunku, sprawdzając następujące pola:

    - **Punkty niebezpiecznego materiału** — w tym polu jest wyświetlana ocena materiału niebezpiecznego dla ładunku. Wartość jest obliczana zgodnie z regułami i wartościami określonymi dla odpowiedniego rozporządzenia i w konfiguracji zwolnionego produktu. Obliczenie pobiera ilość w ładunku i odwołuje się do mnożnika w [konfiguracji zarządzania materiałami](#material-management) dla zwolnionego produktu.
    - **Waga netto ograniczonej ilości** — dla produktów oznaczonych jako produkty z ograniczoną ilością ze względu na niebezpieczną zawartość materiału, w tym polu jest wyświetlana łączna waga netto zawartości niebezpiecznej, która jest uwzględniona w ładunku. Obliczenia są oparte na produktach oznaczonych jako materiały niebezpieczne w konfiguracji zwolnionego produktu. Jeśli towar jest oznaczony jako towar o ograniczonej ilości, obliczenie pobiera ilość w każdym ładunku i odwołuje się do wagi w [ustawieniach zarządzania materiałami](#material-management) dla zwolnionego produktu.

1. Aby przejrzeć wyniki i wagi poszczególnych wierszy, wybierz skróconą kartę **Wiersze ładunku**. Wartości podane dla każdego wiersza są podobne do wartości podanych dla całego ładunku, zgodnie z opisem w poprzednim kroku.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-load"></a>Sprawdzanie zgodności materiałów niebezpiecznych uwzględnionych w ładunku

System może ocenić, czy wszystkie niebezpieczne materiały uwzględnione w ładunku mogą być wysłane razem. Aby ocenić zgodność, system sprawdza grupę zgodności przypisaną do każdego produktu, który jest uwzględniony w ładunku. Aby uzyskać więcej informacji, zajrzyj do [Grupy zgodności materiałów niebezpiecznych](hazmat-setup.md#compatibility-groups).

Aby uruchomić narzędzie do sprawdzenia zgodności, postępuj zgodnie z instrukcjami poniżej.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie ładunki**.
1. Wybierz wysyłkę, aby otworzyć stronę **Szczegółów ładunku**. (Możesz również otworzyć szczegóły ładunku, wybierając łącze z pokrewnej wysyłki.)
1. W okienku akcji na karcie **Ładunki** w grupie **Działania** wybierz opcję **Sprawdzenie zgodności**.

Zostanie wyświetlony komunikat informujący o wynikach kontroli.
