---
title: Terminologia z dziedziny rachunku kosztów
description: W tym temacie opisano kluczowe pojęcia używane w rachunku kosztów.
author: ShylaThompson
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedger
audience: Application User
ms.reviewer: roschlom
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f61ae7a6657eaad3510833c17f342b7266be247aec2a9bfe80b97172f662ae0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774384"
---
# <a name="cost-accounting-terminology"></a>Terminologia z dziedziny rachunku kosztów

[!include [banner](../includes/banner.md)]

W tym temacie opisano kluczowe pojęcia używane w rachunku kosztów.

**Podstawa alokacji**

Podstawą alokacji służy do mierzenia i kwantyfikowania działań, takich jak liczba roboczogodzin, zużywana liczba kilowatogodzin lub zajmowana powierzchnia (w stopach lub metrach kwadratowych). Służy jako podstawa alokowania kosztów do jednego lub więcej obiektów kosztów

**Rachunek kosztów**

Moduł Rachunek kosztów pozwala zbierać dane z różnych źródeł, takich jak księga główna, księgi podrzędne, budżety i zasoby informacji statystycznych. Następnie można analizować, sumować i oceniać dane kosztów, dzięki czemu kierownictwo może podejmować najlepsze decyzje w kwestii aktualizacji cen, budżetów, kontroli kosztów i tak dalej. Dane źródłowe używane do analizy kosztów są traktowane niezależnie w rachunku kosztów. Dlatego aktualizacje w rachunku kosztów nie mają wpływu na dane źródłowe. Jednak podczas zbierania danych o kosztach z różnych źródeł, a zwłaszcza w przypadku importowania kont głównych z Księgi głównej jako składników kosztów, istnieje redundancja danych, ponieważ te same dane znajduje się w Księdze głównej i module Rachunek kosztów. Ta nadmiarowość jest wymagana, ponieważ zarządzanie finansowe jest używane do sprawozdawczości zewnętrznej, a rachunek kosztów do sprawozdawczości wewnętrznej.

**Księga rachunku kosztów**

Zdefiniowana przez kalendarz, walutę i wymiar elementu kosztu, kontroluje procesy i zasady pomiaru kosztów. 

**Wpis kosztu**

Wpisy kosztów to wynik przesyłania za pośrednictwem łączników danych z zapisów księgi głównej, alokacji kosztów i zaksięgowanych wpisów kosztów w arkuszach kosztów.

**Obiekt kosztów**

Dowolny typ obiektu wybrany do kontroli kosztów. Koszty lub przychody są księgowane bezpośrednio w obiektach kosztów lub do nich przydzielane. Typowe obiekty kosztów są następujące:

-  Produkty
-  Projekty
-  Działy
-  Centra kosztów

Kierownictwo używa obiektów kosztów do mierzenia kosztów, ale także do analizy rentowności.

**Składnik kosztu**

Służy jako funkcja do śledzenia i kategoryzowania kosztów. Istnieją dwa typy składników kosztów: podstawowe i dodatkowe.

Podstawowe składniki kosztów reprezentują przepływów kosztów z księgowości finansowej do rachunku kosztów. Struktura zwykle odpowiada strukturze konta wynikowego w księdze głównej, gdzie składnik kosztu może odpowiadać kontu głównemu. Nie wszystkie konta główne muszą być reprezentowane jako składniki kosztów. Zależy to od potrzeb biznesowych. 

Dodatkowe składniki kosztów reprezentują wewnętrzny przepływ kosztów, ponieważ koszty te są wykorzystywane tylko w rachunku kosztów. Są używane w zasadach akumulacji kosztów w celu agregacji kosztów na jednoznaczne przedziały używane przez obliczanie narzutu. 

**Klasyfikacja kosztu**

Klasyfikacja kosztów grupuje koszty według ich cech wspólnych. Na przykład koszty można grupować według składników, identyfikowalności i zachowania.

-   **Według składników** — Materiały, robocizna i wydatki.
-   **Według identyfikowalności** — Koszty bezpośrednie i pośrednie. Koszty bezpośrednie są przypisywane bezpośrednio do obiektów kosztów. Koszty pośrednie nie są bezpośrednio powiązane z obiektami kosztów. Koszty pośrednie są przydzielane do obiektów kosztów.
-   **Według zachowania** — Stałe, zmienne i półzmienne.

**Zachowanie kosztów**

Zachowanie kosztów klasyfikuje koszty zgodnie z ich zachowaniem w odniesieniu do zmian w kluczowych działaniach biznesowych. Aby skutecznie kontrolować koszty, kierownictwo musi rozumieć ich zachowanie. Istnieją trzy typy wzorców zachowań kosztów: stałe, zmienne i półzmienne.

- **Koszt stały** — Koszt stały to koszt, które nie zmienia się w krótkim okresie, bez względu na zmiany w poziomie aktywności. Na przykład kosztem stałym może być podstawowy wydatek operacyjny przedsiębiorstwa, taki jak czynsz, która nie ulegnie zmianie, nawet jeśli poziom aktywności zwiększy się lub zmniejszy.

- **Koszt zmienny** — Koszt zmienny zmienia się zgodnie ze zmianami poziomu aktywności. Na przykład określony koszt bezpośredni materiałów jest skojarzony z każdym sprzedawanym produktem. Im więcej produktów jest sprzedawanych, tym są wyższe bezpośrednie koszty materiałów.

- **Koszt półzmienny** — Koszty półzmienne to koszty częściowo stałe, a częściowo zmienne. Na przykład opłata za dostęp do Internetu zawiera standardową miesięczną opłatę za dostęp oraz opłatę za łączność szerokopasmową. Standardowa miesięczna opłata za dostęp jest kosztem stałym, a opłata za łączność szerokopasmową jest kosztem zmiennym.

**Jednostka kontroli kosztów**

Jednostka kontroli kosztów reprezentuje strukturę kosztów. Struktura określa sposób przepływu kosztów w zamówieniu hierarchicznym między wymiarami obiektów kosztów, a odpowiadającymi i m obiektami kosztów. 

**Dystrybucja kosztów**

Służy do rozdzielenia kosztów od jednego obiektu kosztów do jednego lub więcej innych obiektów kosztów poprzez zastosowanie odpowiedniej podstawy alokacji. Dystrybucja kosztów i alokacja kosztów różnią się tym, że dystrybucja kosztów zawsze jest wykonywana na poziomie podstawowego składnika kosztów pierwotnego kosztu a nie wzajemnego przetwarzania.

**Alokacja kosztu**

Jest używana w celu alokowania salda obiektu kosztów do innych obiektów kosztów poprzez zastosowanie podstawy alokacji. Aplikacja Finance obsługuje metody wzajemnej alokacji. W metodzie alokacji wzajemnej są w pełni wykazywane wzajemne usługi, jakie między sobą wymieniają pomocnicze obiekty kosztów. System automatycznie ustala prawidłową kolejność, w jakiej ma zostać wykonana alokacja i iteracja. Saldo obiektu kosztów jest alokowane przy użyciu jednej podstawy alokacji. Są obsługiwane alokacje między wymiarami obiektu kosztów i ich elementami członkowskimi. Kolejność alokacji jest kontrolowana przez jednostkę kontroli kosztów.

**Zasada alokacji kosztów**

Zasada alokacji kosztów określa kwoty i ilości, które muszą być przydzielone. Do reguł alokacji należą reguły źródła alokacji, które określają przydzielane koszty, oraz reguły celów alokacji, które określają, dokąd koszty są przydzielane. Na przykład wszystkie koszty za usługi w zakładzie są źródłem alokacji, które można przydzielić do różnych działów w organizacji (tzn. do celów alokacji).

**Akumulacja kosztów**

Celem zasad akumulacji kosztów jest agregacja kosztów w jednoznaczne przedziały. Poziom agregacji jest zdefiniowany przez użytkownika i obejmuje przydział podrzędnego składnika kosztu. Jeżeli akumulacja kosztów nie jest używana, każdy pojedynczy składnik kosztu jest przydzielany od jednego obiektu kosztów do drugiego.

**Zasada stawek kosztów**

Stawka kosztu jest używana do obliczania ceny dla obiektu kosztu. Aby znać składniki ceny, definiuje się zasady stawek kosztów. Istnieją dwa typy stawek kosztów: historyczna i planowana. Historyczna stawka kosztu to stawka obliczana, która jest używana jako mnożnik podstawy alokacji dla obiektu kosztów. Stawka jest obliczana na podstawie alokacji kosztów w poprzednim okresie. Stawka planowana jest definiowana przez użytkownika.

**Hierarchia wymiarów**

Istnieją dwie hierarchie wymiarów: hierarchia kategoryzacji i hierarchia klasyfikacji. Typ hierarchii kategoryzacji wymiarów jest używany na potrzeby sprawozdawczości. Obsługuje tylko wymiary składników kosztów. Typ hierarchii klasyfikacji wymiarów jest używany do definiowania zasad i na potrzeby sprawozdawczości. Obsługuje wszystkie wymiary, takie jak obiekty kosztów, składniki kosztów i wymiary statystyczne. 

**Łącznik danych**

Rachunek kosztów obsługuje integrację danych z systemów źródłowych za pomocą zestawu łączników danych. Dostępne są następujące łączniki danych:

-  Zaimportowane transakcje (wstępnie skonfigurowane)
-  Dynamics 365 Finance (wstępnie skonfigurowane)
-  Dynamics AX (wymagana konfiguracja)

**Uwaga:** Łącznik danych Zaimportowane transakcje jest oparty na jednostkach danych.

**Dostawca danych**

Większość systemów źródłowych może udostępnić dane zgodne z co najmniej jednym źródłem danych w rachunku kosztów. Aby dopasować dane z systemów źródłowych do źródła danych w rachunku kosztów, należy skonfigurować dostawcę danych. Poniższa tabel zawiera listę dostępności dostawców danych według łącznika danych i źródła danych.

|  **Źródła danych** |  **Łącznik danych zaimportowanych transakcji** | **Łącznik danych rozwiązania Dynamics 365 Finance**  | **Łącznik danych Dynamics AX**  |
|---|---|---|---|
| Elementy członkowskie wymiaru składnika kosztu  |  Tak | Tak  | Tak  |
|  Elementy członkowskie wymiaru obiektu kosztów |  Tak | Tak  | Tak  |
|  Elementy członkowskie wymiaru statystycznego | Tak  | Nr  | Nr  |
|  Księga główna | Tak  | Tak  | Tak  |
|  Wpisy budżetu  | Tak  | Tak  | Tak  |
|  Miary statystyczne | Tak  | Tak  | Tak  |

**Wzór**

Podstawy alokacji formuły umożliwiają definiowanie zaawansowanych formuł w celu osiągnięcia poprawnej podstawy alokacji. Można ręcznie tworzyć podstawy alokacji formuły. Następujące operatory służą do definiowania formuły.

|  **Symbole** | **Tekst**  |
|---|---|
|  ( ) | Nawiasy  |
|  < |  Mniejsze niż |
|  > |  Większe niż |
|  + |  Dodanie |
|  – |  Odejmowanie |
| *  | Mnożenie  |

Tradycyjne instrukcje IF nie są obsługiwane. Można jednak tworzyć instrukcje i sprawdzać, czy określone w nich warunki są spełnione.

|  **Weryfikacja wyciągu** | **Wynik**  |
|---|---|
|  a > b| Prawda  |
|  a > b |  Fałsz |

**Koszt narzutów**

Koszty ogólne odnoszą się do bieżących wydatków związanych z prowadzeniem przedsiębiorstwa. Nie można ich połączyć bezpośrednio z konkretnymi działaniami biznesowymi. Oto kilka przykładów kosztów ogólnych:

-   Koszty księgowości
-   Amortyzacja
-   Ubezpieczenie
-   Zainteresowania
-   Opłaty za obsługę prawną
-   Podatki
-   Koszty mediów

**Stawka narzutu**

Stawki są definiowane według obiektu kosztu i składnika kosztu. Dostępne są dwa typy stawki: okres obrachunkowy i określona przez użytkownika. Stawki okresu obrachunkowego są obliczane przez obliczenie narzutów. Stawka specyficzna dla użytkownika jest zdefiniowana przez użytkownika i można jej użyć do przydzielenia kosztów między obiektami kosztów z wcześniej określoną stawką w obliczaniu narzutów.

**Opublikowana**

Jeśli w tym polu zostanie ustawiona wartość Tak, użytkownik, któremu przypisano jedną z następujących ról, może wyświetlać raport w obszarze roboczym Kontrola kosztów.

-  Menedżer rachunku kosztów
-  Księgowy kosztów
-  Księgowy rachunku kosztów
-  Kontroler obiektów kosztów

Jeśli w tym polu zostanie ustawiona wartość Nie, tylko użytkownicy, którym przypisano jedną z następujących ról, mogą wyświetlać raport w obszarze roboczym Kontrola kosztów:

-  Menedżer rachunku kosztów
-  Księgowy kosztów
-  Księgowy rachunku kosztów

**Wymiar statystyczny**

Wymiar statystyczny i jego elementy członkowskie są używane do rejestrowania i kontrolowania wpisów niepieniężnych w rachunku kosztów. Elementy członkowskie wymiaru statystycznego mogą służyć do dwóch celów:

-  Jako podstawa alokacji w zasadach, na przykład dystrybucji kosztów lub alokacji kosztów.
-  Do raportowania zużycia niepieniężnego.

Wymiar statystyczny to wyrażenie liczby lub sumy działania, które może służyć jako podstawa dla alokacji lub obliczeń stawek. Tworzy się je ręcznie lub importuje z systemów źródłowych. Przykładami wymiarów statystycznych są liczba pracowników, liczba licencjonowanych programów na każdym urządzeniu, zużycie energii przez każdą maszynę lub powierzchnia centrum kosztu w metrach kwadratowych.

**Wyciąg**

Zestawienia to widoki dla menedżerów odpowiedzialnych za kontrolowanie kosztów. Zestawienia są definiowane przez kontrolera kosztów i zapewniają szybki podgląd kosztów rzeczywistych i budżetowych, a nawet odchyleń. W razie potrzeby menedżer może przejść do kolejnego poziomu szczegółów. Aby zapewnić, że menedżerowie widzą tylko dane, za które odpowiadają, dane wyświetlane w zestawieniach podlegają regułom dostępu.

**Wersja**

Wersje są używane do symulowania, wyświetlania i porównywania różnych wyników. Domyślnie wszystkie koszty rzeczywiste są wyświetlane w jednej wersji podstawowej określanej jako *rzeczywista*. Dla budżetów i obliczeń można pracować z tyloma wersjami, ile jest potrzebnych. Można na przykład zaimportować dane budżetu do oryginalnej wersji, a następnie skorygować budżet w nowej wersji. Dla obliczeń można tworzyć wiele wersji. W tych różnych wersjach można wówczas tworzyć obliczenia przy użyciu różnych reguł obliczeniowych, które będą stosowane dla alokacji kosztów.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]