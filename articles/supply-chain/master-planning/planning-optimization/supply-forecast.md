---
title: Planowanie główne z uwzględnieniem prognoz dostaw
description: W tym artykule opisano sposób, w jaki prognozy dostaw są traktowane podczas planowania głównego.
author: t-benebo
ms.date: 09/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-21
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2bac9355bb1ac00f697ec459f494a64553e0eacc
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740149"
---
# <a name="master-planning-with-supply-forecasts"></a>Planowanie główne z uwzględnieniem prognoz dostaw

[!include [banner](../../includes/banner.md)]

Prognozy dostaw pozwalają określić podaż, która może być potrzebna w pewnym przyszłym okresie. Zwykle oszacowanie bazuje na historii sprzedaży za ubiegły rok, a następnie na potrzeby budżetowania używana jest prognoza. Można również skonfigurować plany główne, aby uwzględnić prognozy podczas planowania.

## <a name="set-up-a-master-plan-to-consider-supply-forecasts"></a>Konfigurowanie planu głównego w celu uwzględnienia prognoz dostaw

Można określić, czy w każdym planie głównym mają być uwzględniane prognozy podczas jego działania. Aby ustawić opcje prognozowania dla każdego planu, należy skorzystać z następującej procedury.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz istniejący plan główny w okienku listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nowy.
1. Na skróconej karcie **Ogólne** ustaw następujące pola:

    - **Model prognozy** — umożliwia wybór modelu zawierającego prognozy dostaw i/lub popytu, które powinny być uwzględniane w planie głównym.
    - **Uwzględnij prognozę dostaw** — tę opcję należy ustawić na *Tak*, jeśli prognozy dostaw mają być uwzględniane w planie głównym.
    - **Uwzględnij prognozę popytu** — tę opcję należy ustawić na *Tak*, jeśli prognozy popytu mają być uwzględniane w planie głównym. Chociaż to ustawienie jest niezależne od ustawienia **Uwzględnij prognozę dostaw**, niektóre ustawienia na tej stronie dotyczą zarówno prognoz dostaw, jak i prognoz popytu. Aby uzyskać więcej informacji dotyczących planowania uwzględniającego prognozy popytu, zobacz [Planowanie główne z uwzględnieniem prognoz popytu](demand-forecast.md).
    - **Metoda używana do redukowania zapotrzebowań prognozowanych** — umożliwia wybór metody do użycia do zmniejszenia zapotrzebowania prognozowanego podczas planowania głównego:

        - *Brak* — prognozowane zapotrzebowanie nie będzie zmniejszane podczas planowania głównego.
        - *Procent — klucz redukcji* — prognozowane zapotrzebowanie będzie zmniejszane według wartości procentowych i przedziałów czasu, które są definiowane w kluczu redukcji.
        - *Transakcje — klucz redukcji* — prognozowane zapotrzebowanie będzie zmniejszane według transakcji dokonywanych w przedziałach czasu, które są definiowane w kluczu redukcji.
        - *Transakcje — okres dynamiczny* — prognozowane zapotrzebowanie będzie zmniejszane według transakcji zamówień dokonywanych w okresie dynamicznym. Okres dynamiczny obejmuje aktualne daty prognozy i kończy się po rozpoczęciu kolejnej prognozy. Metoda *Transakcje — okres dynamiczny* nie używa lub nie wymaga klucza redukcji. W przypadku jej użycia stosowane są następujące warunki:

            - Jeśli prognoza zostanie zmniejszona do zera, wymagania prognozy dla bieżącej prognozy przybierają wartość 0 (zero).
            - Jeśli nie ma żadnej przyszłej prognozy, wymagania prognozy z ostatnio wprowadzonej prognozy są redukowane.
            - Horyzonty czasowe są uwzględniane w obliczeniach redukcji prognozy.
            - Dni pasywne są uwzględniane w obliczeniach redukcji prognozy.
            - Jeśli transakcje rzeczywistego zamówienia przekraczają prognozowane zapotrzebowanie, pozostałe transakcje nie są przekazywane do następnego okresu prognozy.

        > [!NOTE]
        > Ustawienie **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** dotyczy także prognoz popytu, jeśli zostały one włączone w planie głównym, i wpływa na nie w podobny sposób. Aby uzyskać więcej informacji, zobacz [Planowanie główne z uwzględnieniem prognoz popytu](demand-forecast.md).

## <a name="set-reduction-options-for-coverage-groups"></a>Ustawianie opcji redukcji dla grup zapotrzebowania

Aby ustawić opcje, które sterują tym, w jaki sposób grupa zapotrzebowania zmniejsza prognozowane zapotrzebowanie dla planów głównych, w których jest używana redukcja oparta na transakcjach, należy wykonać następujące kroki.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Plany \> Grupy zapotrzebowania**.
1. Wybierz istniejącą grupę zapotrzebowania w okienku listy lub wybierz **Nowy** w okienku akcji, aby utworzyć nową.
1. Na skróconej karcie **Inne** w polu **Zmniejsz prognozę o** określ, jak prognozowane zapotrzebowanie powinno być zmniejszane dla pozycji w grupie zapotrzebowania dla planów głównych, w których pole **Metoda używana w celu zmniejszenia prognozowanych zapotrzebowań** zostało ustawione na *Transakcje — klucz redukcji* lub *Transakcje — okres dynamiczny*. Należy wybrać jedną z następujących opcji:

    - *Wszystkie transakcje* — wszystkie transakcje powinny zmniejszać prognozę.
    - *Zamówienia* — prognozy są redukowane tylko w przypadku zamówień sprzedaży tego samego typu.

    Na przykład domyślne ustawienia zamówienia pozycji wskazują, że powinna ona zostać wyprodukowana. Istnieje wiersz prognozy dostaw dla ilości 50 i istnieje zamówienie zakupu dla ilości 20. Jeśli w polu **Zmniejsz prognozę o** jest ustawiona wartość *Zamówienia*, zostanie utworzone planowane zlecenie produkcyjne z ilością 50. Jeśli jest ustawiona wartość *Wszystkie transakcje*, planowane zlecenie produkcyjne zostanie zmniejszona do ilości 30.

    To ustawienie dotyczy także redukcji prognozowania popytu. Aby uzyskać więcej informacji, zobacz [Planowanie główne z uwzględnieniem prognoz popytu](demand-forecast.md).

## <a name="enter-a-supply-forecast-for-a-product"></a>Wprowadzanie prognozy dostaw produktu

Aby wprowadzić prognozę dostaw, wykonaj poniższe kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Wybierz produkt, dla którego chcesz wprowadzić prognozę.
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Prognoza dostaw**.
1. Na stronie **Prognoza dostaw**, w okienku akcji wybierz opcję **Nowy**, aby dodać prognozę do siatki.
1. Wprowadź informacje w nowym wierszu zgodnie z potrzebami, aby określić prognozę.

## <a name="plan-for-an-item-with-supply-forecast-lines"></a>Planowanie pozycji z wierszami prognozy dostaw

Po uruchomieniu planu głównego, który zawiera pozycję, dla których istnieje prognoza dostaw, system utworzy zamówienie zakupu dla wprowadzonych wierszy dostaw. Domyślne ustawienia zamówienia dla pozycji są zachowywane. Jeśli te domyślne ustawienia zamówienia określają opcję **Domyślny typ zamówienia** jako *Zamówienie zakupu*, a w wierszu prognozy dostaw nie określono konta dostawcy, system użyje domyślnego dostawcy dla tej pozycji.

## <a name="check-whether-a-planned-order-is-a-supply-forecast-order"></a>Sprawdzanie, czy planowane zamówienie jest zamówieniem prognozy dostaw

Aby dowiedzieć się, czy w wyniku prognozy dostaw utworzono zamówienie planowane, należy skorzystać z następującej procedury.

1. Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Zamówienia planowane**.
1. Otwórz planowane zamówienie zakupu, które chcesz zbadać.
1. Na skróconej karcie **Ogólne** sprawdź wartość pola **Prognoza dostaw**. Jeśli zamówienie zostało utworzone w celu pokrycia prognozy dostaw, to pole będzie mieć wartość *Tak*.

## <a name="examples-of-master-planning-with-supply-forecasts"></a>Przykłady planowania głównego z uwzględnieniem prognoz dostaw

Ta sekcja zawiera kilka przykładów, które pokazują, w jaki sposób prognozowanie dostaw wpływa na planowanie główne.

### <a name="example-1-supply-forecast-for-an-item"></a>Przykład 1. Prognoza dostaw dla pozycji

Masz pozycję, której domyślnym typem zamówienia jest *Zamówienie zakupu*, a domyślnym dostawcą jest *US-002*. Zawiera ona następujący wiersz prognozy dostaw.

| Model    | Data     | Konto dostawcy | Grupa dostawców | Ilość | Jednostka | Witryna | Magazyn |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10.10.2022 |                |              | 35       | szt.   | 1    | 11        |

Podczas uruchamiania planowania głównego zostanie utworzone planowane zamówienie zakupu na *35 szt.* od dostawcy *US-002*.

### <a name="example-2-several-supply-forecast-lines-with-and-without-a-vendor"></a>Przykład 2. Kilka wierszy prognozy dostaw z dostawcą lub bez

Masz pozycję, której domyślnym typem zamówienia jest *Zamówienie zakupu*, a domyślnym dostawcą jest *US-002*. Zawiera ona następujące wiersze prognozy dostaw.

| Model    | Data     | Konto dostawcy | Grupa dostawców | Ilość | Jednostka | Witryna | Magazyn |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10.10.2022 |                |              | 35       | szt.   | 1    | 11        |
| CurrentF | 10.10.2022 | US-101         |              | 25       | szt.   | 1    | 11        |

W takim przypadku system traktuje wiersz, który nie określa dostawcy, jako prognozę ogólną, i zakłada, że wiersz, który określa dostawcę, powinien zostać odjęty od prognozy ogólnej. Dlatego planowanie główne utworzy następujące planowane zamówienia zakupu dla pozycji:

- Planowane zamówienie zakupu na ilość *25 szt.* od dostawcy *US-101* (używany jest dostawca i ilość określone w wierszu prognozy).
- Planowane zamówienie zakupu na ilość *10 szt.* od dostawcy *US-002* (ponieważ w drugim wierszu prognozy nie określono dostawcy, jest używany domyślny dostawca, a ilość z tego wiersza prognozy jest zmniejszana o ilość wiersza prognozy specyficznego dla dostawcy).

### <a name="example-3-plans-that-use-the-transactions---dynamic-period-reduction-method-in-a-single-forecast-period"></a>Przykład 3. Plany, w których stosowana jest metoda redukcji Transakcje — okres dynamiczny w pojedynczym okresie prognozy

W przypadku planów głównych, w których jest używana metoda redukcji *Transakcje — okres dynamiczny*, planowanie główne zmniejszy ilości prognoz, jeśli istnieją transakcje zgodne z tymi charakterystykami dostaw.

Na przykład masz pozycję z domyślnym typem zamówienia *Zamówienie zakupu*. Zawiera ona następujący wiersz prognozy dostaw.

| Model    | Data     | Konto dostawcy | Grupa dostawców | Ilość | Jednostka | Witryna | Magazyn |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10.10.2022 | US-101         |              | 25       | szt.   | 1    | 11        |

Ponieważ istnieje tylko jeden wiersz prognozy dostaw, jest tylko jeden okres prognozy.

Po uruchomieniu planu głównego skonfigurowanego do użycia metody redukcji *Transakcje — okres dynamiczny* może wystąpić jeden z następujących wyników:

- Jeśli istnieje zamówienie zakupu dla dostawcy *US-101* i ilości *10 szt.*, a pole **Prognoza dostaw** ma wartość *Tak*, planowanie główne tworzy nowe planowane zamówienie zakupu dla pozostałej ilości wynoszącej *10 szt*. Wiersz prognozy jest zmniejszany, ponieważ dostawca pasuje do istniejącego zamówienia zakupu.
- Jeśli istnieje zamówienie zakupu dla dostawcy *US-102*, lokacji *1*, magazynu *11* i ilości *10 szt.*, a pole **Prognoza dostaw** ma wartość *Tak*, planowanie główne tworzy nowe planowane zamówienie zakupu dla pełnej ilości wynoszącej *25 szt*. Nie można zmniejszyć wiersza prognozy, ponieważ ma on innego dostawcę niż istniejące zamówienie zakupu.

> [!NOTE]
> Taka sytuacja może wystąpić w przypadku planowanych zamówień zakupu, ponieważ dostawca jest z nimi skojarzony. Jednak w przypadku zamówień przeniesienia i zleceń produkcyjnych kwoty prognozy dostaw zawsze będą zmniejszane o istniejące zamówienia, ponieważ dla tego typu zamówień nie określono dostawcy.

### <a name="example-4-plans-that-use-the-transactions---dynamic-period-reduction-method-over-several-forecast-periods"></a>Przykład 4. Plany, w których stosowana jest metoda redukcji Transakcje — okres dynamiczny w wielu okresach prognozy

Masz pozycję z domyślnym typem zamówienia *Zamówienie zakupu*. Zawiera ona następujące wiersze prognozy dostaw.

| Model    | Data     | Konto dostawcy | Grupa dostawców | Ilość | Jednostka | Witryna | Magazyn |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10.10.2022 | US-101         |              | 25       | szt.   | 1    | 11        |
| CurrentF | 15.10.2022 | US-101         |              | 25       | szt.   | 1    | 11        |

W tym przykładzie istnieją dwa wiersze prognozy, z których każdy ma inną datę. W związku z tym daty ustalają granice okresów prognozy. Pierwszy okres to okres od 10 października do 14 października 2022 r. (10.10.2022–14.10.2022). Drugi okres to przedział do 15 października 2022 (15.10.2022).

Istnieje zamówienie zakupu dla dostawcy *US-101*, ilości *10 szt.* i daty *12.10.2022* (12 października 2022 r.). Po uruchomieniu planu głównego skonfigurowanego do użycia metody redukcji *Transakcje — okres dynamiczny* zostaną utworzone następujące zamówienia:

- Zamówienie planowane z ilością *15 szt.* i datą *10.10.2022* (ilość jest zmniejszana o istniejące zamówienie zakupu, które datowane jest w tym samym okresie prognozy).
- Zamówienie planowane z ilością *25 szt.* i datą *15.10.2022* (Ilość jest pełną ilością prognozy).

### <a name="example-5-plans-that-use-no-reduction"></a>Przykład 5. Plany bez redukcji

W przypadku uruchomienia planu, w którym metodą redukcji prognozy jest *Brak*, planowanie główne zawsze utworzy planowaną podaż dla wszystkich wierszy prognozy dostaw. Zatwierdzenie planowanej podaży spowoduje ograniczenie przyszłych zamówień planowanych. Jednak zamówienia zakupu nie zmniejszą wierszy prognozy dostaw.

Na przykład masz pozycję z domyślnym typem zamówienia *Zamówienie zakupu*. Zawiera ona następujący wiersz prognozy dostaw.

| Model    | Data     | Konto dostawcy | Grupa dostawców | Ilość | Jednostka | Witryna | Magazyn |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10.10.2022 | US-101         |              | 25       | szt.   | 1    | 11        |

Istnieje zamówienie zakupu dla dostawcy *US-101*, lokacji *1*, magazynu *11*, ilości *25 szt.* i daty *10.10.2022*. 

W przypadku uruchomienia planu głównego, który jest ustawiony do używania metody redukcji *Brak*, zostanie utworzone planowane zamówienie zakupu dla dostawcy *US-101*, lokacji *1*, magazynu *11*, ilości *25 szt.* i daty *10.10.2022*. Innymi słowy, istniejące zamówienie zakupu nie zostanie zmniejszone, ponieważ metodą redukcji prognozy jest *Brak*.

Edytujesz teraz planowane zamówienie zakupu, które zostało utworzone po ostatnim uruchomieniu planowania, i zmniejszasz ilość na *15 szt*. Następnie zatwierdzasz zamówienie zakupu. Następnym razem, gdy uruchomisz plan główny, zostanie utworzone planowane zamówienie zakupu dla dostawcy *US-101*, lokacji *1*, magazynu *11*, ilości *10 szt.* i daty *10.10.2022*. Tym razem ilość zostanie zmniejszona, aby odzwierciedlić ilość w istniejącym zatwierdzonym zamówieniu z poprzedniego przebiegu planowania.

## <a name="differences-between-planning-optimization-and-the-deprecated-master-planning-engine"></a>Różnice między optymalizacją planowania i przestarzałym aparatem planowania głównego

Prognozy dostaw działają nieco inaczej, w zależności od silnika planowania, którego używasz ( Optymalizacja planowania lub przestarzały silnik planowania głównego). W tej sekcji opisano różnice.

### <a name="vendor-groups"></a>Grupy dostawców

Podczas dodawania prognozowanego wiersza można określić dostawcę i grupę dostawców. W przestarzałym aparacie planowania głownego tworzone zamówienia planowane są grupowane według kombinacji wartości dostawców i grup dostawców. W optymalizacji planowania zamówienia planowane są grupowane według dostawcy.

W poniższej tabeli przedstawiono przykłady wierszy prognozy dostaw dla pozycji.

| Model    | Data     | Konto dostawcy | Grupa dostawców | Ilość | Jednostka | Witryna | Magazyn |
|----------|----------|----------------|--------------|----------|------|------|-----------|
| CurrentF | 10.10.2022 |                | VendorGroupA | 5        | szt.   | 1    | 11        |
| CurrentF | 10.10.2022 |                | VendorGroupA | 6        | szt.   | 1    | 11        |
| CurrentF | 10.10.2022 |                |              | 7        | szt.   | 1    | 11        |

Dostawca *VendorA* jest domyślnym dostawcą dla grupy dostawców *VendorGroupA*. Jest to również domyślny dostawca dla pozycji.

Przestarzały aparat planowania głównego utworzy następujące zamówienia:

- Planowane zamówienie zakupu dla dostawcy *VendorA*, grupy dostawców *VendorGroupA* i ilości *11*
- Planowane zamówienie zakupu dla dostawcy *VendorA* i ilości *7*

Optymalizacja planowania spowoduje utworzenie tylko jednego zamówienia:

- Planowane zamówienie zakupu dla dostawcy *VendorA*, grupy dostawców *VendorGroupA* i ilości *18*

### <a name="reduction-of-general-forecasts-by-more-specific-forecasts"></a>Zmniejszanie prognoz ogólnych o bardziej szczegółowe prognozy

We przestarzałym aparacie planowania głównego wynik jest nieprzewidywalny, jeśli niektóre prognozy mają dostawcę, a inne nie.

W przypadku optymalizacji planowania prognozy ogólne są zawsze zmniejszane o bardziej szczegółowe prognozy, jak pokazano w poniższym przykładzie.

W poniższej tabeli przedstawiono przykłady wierszy prognozy dostaw dla pozycji.

| Data       | Ilość | Dostawca   | Grupa dostawców  |
|------------|----------|----------|---------------|
| 11.02.2022 | 5.00     | Vendor-A | VendorGroup-A |
| 11.02.2022 | 6,00     | Vendor-A | VendorGroup-A |
| 11.02.2022 | 15.00    |          |               |

Prognoza ogólna (na 15,00 sztuk) jest redukowana o bardziej szczegółowe prognozy (dla 5,00 + 6,00 = 11,00 sztuk). Pozostała część jest przypisywana do domyślnego dostawcy. Poniższa tabela przedstawia planowane zamówienia.

| Data       | Ilość | Dostawca   | Grupa dostawców  |
|------------|----------|----------|---------------|
| 11.02.2022 | 11.00    | Vendor-A | VendorGroup-A |
| 11.02.2022 | 4.00     | Vendor-A | VendorGroup-A |

### <a name="respect-for-default-order-settings-when-planned-orders-are-generated"></a>Przestrzeganie domyślnych ustawień zamówienia podczas generowania zamówień planowanych

Każda pozycja może mieć ustawienia domyślne zamówienia, takie jak minimalna ilość zamówienia zakupu. Przestarzały aparat planowania głównego ignoruje te ustawienia, a w związku z tym przekłada prognozy na planowane zamówienia o takiej samej ilości. Optymalizacja planowania przestrzega tych ustawień, gdy na podstawie prognoz dostaw są generowane zamówienia planowane. 

### <a name="aggregation-of-planned-orders-as-a-result-of-reduction-by-approved-orders"></a>Agregacja zamówień planowanych w wyniku redukcji o zatwierdzone zamówienia

Przestarzały aparat planowania głównego zakłada, że tylko jedno zamówienie zmniejszy istniejącą prognozę dostaw. Jeśli więc kilka zamówień pasuje do wiersza prognozy dostaw, zmniejsza je tylko pierwsze zamówienie. W optymalizacji planowania wszystkie zamówienia, które pasują do wiersza prognozy dostaw, zmniejszą go.

### <a name="reduction-of-forecasts-by-matching-vendors-only"></a>Zmniejszanie prognoz tylko o pasujących dostawców

Gdy przestarzały aparat planowania głównego zmniejsza prognozę o istniejące zwolnione zamówienia zakupu, nie zapewnia, że dostawca na zamówieniu zakupu będzie taki sam jak dostawca z prognozy. Optymalizacja planowania zmniejsza prognozy tylko o zamówienia zakupu, które mają pasującą wartość w polu dostawcy.

W przypadku zamówień przeniesienia i zleceń produkcyjnych pole dostawcy jest zawsze ignorowane, ponieważ nie jest istotne dla tych typów zamówień.

### <a name="reduction-of-forecasts-by-transfer-orders"></a>Zmniejszanie prognoz o zamówienia przeniesienia

Jeśli domyślnym typem zamówienia dla pozycji jest *Przeniesienie*, prognozy mogą być zmniejszane tylko o istniejące planowane zamówienia przeniesienia. Jednak w przypadku zleceń produkcyjnych i zamówień zakupu tylko zwolnione zamówienia redukują prognozę dostaw.

Przestarzały aparat planowania zmniejsza ilość dla wszystkich stanów zamówienia przeniesienia, a optymalizacja planowania zmniejsza prognozy tylko o zamówienia przeniesienia, które są w stanie *Zwolnione*.
