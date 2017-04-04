---
title: "Terminologia rachunku kosztów"
description: "W tym temacie opisano kluczowe pojęcia używane w rachunku kosztów."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 87c13e268ab8825e06095d24e03694cf0f271a63
ms.openlocfilehash: 1ae6b43bdc1812ca822a1abe2a0e823cb797a511
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-terminology"></a>Terminologia rachunku kosztów

W tym temacie opisano kluczowe pojęcia używane w rachunku kosztów.

**Cost accounting**

Moduł Rachunek kosztów pozwala zbierać dane z różnych źródeł, takich jak księga główna, księgi podrzędne, budżety i zasoby informacji statystycznych. Następnie można analizować, sumować i oceniać dane kosztów, dzięki czemu kierownictwo może podejmować najlepsze decyzje w kwestii aktualizacji cen, budżetów, kontroli kosztów i tak dalej. Dane źródłowe używane do analizy kosztów są traktowane niezależnie w rachunku kosztów. Dlatego aktualizacje w rachunku kosztów nie mają wpływu na dane źródłowe. Jednak podczas zbierania danych o kosztach z różnych źródeł, a zwłaszcza w przypadku importowania kont głównych z księgi głównej w programie Microsoft Dynamics 365 for Operations jako składników kosztów, istnieje redundancja danych, ponieważ te same dane znajduje się w księdze głównej i module Rachunek kosztów. Ta nadmiarowość jest wymagana, ponieważ zarządzanie finansowe jest używane do sprawozdawczości zewnętrznej, a rachunek kosztów do sprawozdawczości wewnętrznej.

**Cost accounting ledger**

Księga rachunku kosztów to specjalistyczna struktura, która określa sposób wprowadzania i przedstawiania procesów, wartości i ilości dla konkretnego obszaru w rachunku kosztów. Księga rachunku kosztów definiuje procesy i reguły mierzenia kosztów w obiektach kosztów. Obsługuje transakcje kosztowe oraz zarządza dokumentami, które rejestrują zmiany wartości i ilości generowane przez transakcje kosztowe.

**Cost entry**

Wpisy kosztów to wynik przesyłania za pośrednictwem łączników danych z zapisów księgi głównej, alokacji kosztów i zaksięgowanych wpisów kosztów w arkuszach kosztów.

**Cost object**

Obiekty kosztów to obiekty dowolnego typu, do których są przydzielane koszty. Poniżej przedstawiono niektóre typowe obiekty kosztów:

-   Produkty
-   Projekty
-   Zasoby
-   Działy
-   MPK
-   Regiony geograficzne

Kierownictwo używa obiektów kosztów do mierzenia kosztów, ale także do analizy rentowności.

**Cost element**

Składniki kosztów są używane jako funkcja śledzenia i klasyfikowania obiektów docelowych przepływu kosztów. Istnieją dwa typy składników kosztów: koszty podstawowe i koszty dodatkowe. **Koszty podstawowe** elementy koszt podstawowy reprezentują przepływ kosztów z rachunkowości finansowej do rachunku kosztów. Struktura składników kosztów odpowiada strukturze konta wynikowego w księdze głównej, gdzie składnik kosztu może odpowiadać kontu głównemu. Nie wszystkie konta główne muszą być reprezentowane jako składniki kosztów. Zależy to od potrzeb biznesowych. Oto kilka przykładów podstawowych składników kosztów:

-   Koszt własny sprzedaży (COG)
-   Koszty pośrednie materiału
-   Koszty pracownicze
-   Koszty energii

**Secondary cost element** 

Podrzędne składniki kosztów reprezentują wewnętrzny przepływ kosztów, ponieważ koszty te są tworzone i wykorzystywane tylko w rachunku kosztów. Podrzędne składniki kosztów pomagają zagwarantować możliwość śledzenia źródła kosztów. Te składniki kosztów są używane w alokacji kosztów i obliczeniach kosztów ogólnych. Oto kilka przykładów podrzędnych składników kosztów:

-   Koszty produkcji
-   Koszty ogólne produkcji, materiałów i marketingu

**Cost control unit**

Jednostka kontroli kosztów reprezentuje strukturę kosztów. Musi być powiązana z wymiarami obiektu kosztów w księdze rachunku kosztów.

**Version**

Wersje są używane do symulowania, wyświetlania i porównywania różnych wyników. Domyślnie wszystkie koszty rzeczywiste są wyświetlane w jednej wersji podstawowej określanej jako *rzeczywista*. Dla budżetów i obliczeń można pracować z tyloma wersjami, ile jest potrzebnych. Można na przykład zaimportować dane budżetu do oryginalnej wersji, a następnie skorygować budżet w nowej wersji. Dla obliczeń można tworzyć wiele wersji. W tych różnych wersjach można wówczas tworzyć obliczenia przy użyciu różnych reguł obliczeniowych, które będą stosowane dla alokacji kosztów.

**Statement**

Zestawienia to widoki dla menedżerów odpowiedzialnych za kontrolowanie kosztów. Zestawienia są definiowane przez kontrolera kosztów i umożliwiają szybki podgląd na koszty rzeczywiste i budżetowe, a nawet na odchylenia i wersje obliczeń. Aby zagwarantować, że menedżerowie widzą tylko dane, za które odpowiadają, dane wyświetlane w zestawieniach podlegają regułom dostępu.

**Łącznik danych**

Dane można importować do rachunku kosztów z zewnętrznych systemów za pośrednictwem łączników danych. Na przykład można importować struktury kont, wymiary, zapisy księgi głównej i wpisy budżetu. Wstępnie skonfigurowanych łączników danych lub łączników niestandardowych można używać do importowania danych i tworzenia połączeń między danymi.

**Cost classification**

Klasyfikacja kosztów grupuje koszty według ich cech wspólnych. Na przykład koszty można grupować według składników, identyfikowalności i zachowania.

-   **Według składników** — Materiały, robocizna i wydatki.
-   **Według identyfikowalności** — Koszty bezpośrednie i pośrednie. Koszty bezpośrednie są przypisywane bezpośrednio do obiektów kosztów. Koszty pośrednie nie są bezpośrednio powiązane z obiektami kosztów. Koszty pośrednie są przydzielane do obiektów kosztów.
-   **Według zachowania** — Stałe, zmienne i półzmienne.

**Cost behavior**

Zachowanie kosztów klasyfikuje koszty zgodnie z ich zachowaniem w odniesieniu do zmian w kluczowych działaniach biznesowych. Aby skutecznie kontrolować koszty, kierownictwo musi rozumieć ich zachowanie. Istnieją trzy typy wzorców zachowań kosztów: stałe, zmienne i półzmienne.

- **Koszt stały** -koszt stały jest koszt, który nie zmienia się w krótkim okresie, bez względu na zmiany w poziomie działalności. Na przykład kosztem stałym może być podstawowy wydatek operacyjny przedsiębiorstwa, taki jak czynsz, która nie ulegnie zmianie, nawet jeśli poziom aktywności zwiększy się lub zmniejszy.

- **Koszt zmienny** -koszt zmienny zmienia się zgodnie ze zmianami w poziom aktywności. Na przykład określony koszt bezpośredni materiałów jest skojarzony z każdym sprzedawanym produktem. Im więcej produktów jest sprzedawanych, tym są wyższe bezpośrednie koszty materiałów.

- **Kosztów pół-zmiennych** -częściowo zmienne koszty są częściowo stałe i częściowo zmienne koszty. Na przykład opłata za dostęp do Internetu zawiera standardową miesięczną opłatę za dostęp oraz opłatę za łączność szerokopasmową. Standardowa miesięczna opłata za dostęp jest kosztem stałym, a opłata za łączność szerokopasmową jest kosztem zmiennym.

**Overhead cost**

Koszty ogólne odnoszą się do bieżących wydatków związanych z prowadzeniem przedsiębiorstwa. Nie można ich połączyć bezpośrednio z konkretnymi działaniami biznesowymi. Oto kilka przykładów kosztów ogólnych:

-   Koszty księgowości
-   Amortyzacja
-   Ubezpieczenie
-   Zainteresowania
-   Opłaty za obsługę prawną
-   Podatki
-   Koszty mediów

**Cost allocation**

Alokacja kosztów to proces przypisywania i przydzielania kosztów w oparciu o źródłowe przyczyny wspólnych kosztów. Można przydzielać kwoty kosztów i ilości z jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów. Na przykład wszystkie koszty usług w zakładzie są przydzielane do różnych działów korzystających ze wspólnego biurowca.

**Cost allocation policy**

Zasada alokacji kosztów określa kwoty i ilości, które muszą być przydzielone. Do reguł alokacji należą reguły źródła alokacji, które określają przydzielane koszty, oraz reguły celów alokacji, które określają, dokąd koszty są przydzielane. Na przykład wszystkie koszty za usługi w zakładzie są źródłem alokacji, które można przydzielić do różnych działów w organizacji (tzn. do celów alokacji).

**Allocation base**

Podstawa alokacji to podstawa, która może służyć do mierzenia i kwantyfikowania działań, takich jak wykorzystywane roboczogodziny, zużywane kilowatogodziny, wykonana robocizna bezpośrednia lub zajmowana powierzchnia. Umożliwia alokowanie kosztów do jednego lub więcej obiektów kosztów.

**Allocation principle**

Jedną z zasad alokacji jest przydzielanie kosztów według stawek kosztów. Można wybrać alokowanie kosztów według stawki w rzeczywistym okresie lub stawki historycznej. Alokacja wykorzystująca metodę wzajemną pomaga zagwarantować, że podstawa alokacji jest wyznaczana na podstawie szeregu jednoczesnych równań, zanim alokacja zostanie wykonana przy użyciu stawki w rzeczywistym okresie.

**Cost roll-up**

Celem akumulacji kosztów jest uwzględnienie wszystkich kosztów dla określonego obiektu kosztów. Poziom agregacji jest definiowany przez użytkownika. Za pomocą akumulacji kosztów można agregować składniki kosztów, które muszą zostać przydzielone od jednego obiektu kosztów do innego. Jeżeli akumulacja kosztów nie jest używana, każdy pojedynczy składnik kosztów jest przydzielany od jednego obiektu kosztów do drugiego.

**Stawka kosztu polityki**

Stawka kosztu jest używana do obliczania ceny dla obiektu kosztu. Aby znać składniki ceny, definiuje się zasady stawek kosztów. Istnieją dwa typy stawek kosztów: historyczna i planowana. Historyczna stawka kosztu to stawka obliczana, która jest używana jako mnożnik podstawy alokacji dla obiektu kosztów. Stawka jest obliczana na podstawie alokacji kosztów w poprzednim okresie. Stawka planowana jest definiowana przez użytkownika.

**Hierarchia wymiarów**

Hierarchie wymiarów są używane jako struktury sprawozdawcze podczas definiowania reguł alokacji, stawek kosztów i zestawień kosztów, wyświetlania zestawień lub danych w programie Microsoft Excel oraz określania praw dostępu do zagregowanych danych. Istnieją dwie hierarchie wymiarów: hierarchia kategoryzacji i hierarchia klasyfikacji. Hierarchia kategoryzacji jest definiowana na podstawie składników kosztów, podczas gdy hierarchia klasyfikacji jest definiowana na podstawie obiektów kosztów.

**Statistical dimension**

Wymiar statystyczny to wyrażenie liczby lub sumy obiektu, które może służyć jako podstawa dla alokacji lub obliczeń stawek kosztów. Tworzy się je ręcznie lub importuje z systemów źródłowych. Przykładami wymiarów statystycznych są liczba pracowników, liczba licencjonowanych programów na każdym urządzeniu, zużycie energii przez każdą maszynę lub powierzchnia centrum kosztu w metrach kwadratowych.

**Statistical entry**

Wpisy statystyczne przechowują zarejestrowaną wartość sumy lub liczby dla określonego wymiaru statystycznego. Zarejestrowana wartość sumy lub liczby również jest nazywana wartością.


