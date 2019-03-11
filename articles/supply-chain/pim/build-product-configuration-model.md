---
title: Budowanie modelu konfiguracji produktu
description: Konieczność konfigurowania produktów spełniających specjalne oczekiwania coraz częściej jest normą, a nie wyjątkiem, zarówno w relacjach między firmami, jak i między firmą a konsumentem.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 75083
ms.assetid: f08072b8-cb0b-43aa-9509-f5ec32caecd9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 60a901ce9e87571b2d199a49af2cddbd72fc5808
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "327465"
---
# <a name="build-a-product-configuration-model"></a>Budowanie modelu konfiguracji produktu

[!include [banner](../includes/banner.md)]

Konieczność konfigurowania produktów spełniających specjalne oczekiwania coraz częściej jest normą, a nie wyjątkiem, zarówno w relacjach między firmami, jak i między firmą a konsumentem.

Producent, który konfiguruje na zamówienie, może lepiej spełnić potrzeby klientów. Ponadto, składując półprodukty w formie ogólnych składników zamiast produktów gotowych, może ograniczyć koszty utrzymania zapasów.  

Pomyślne przejście z konfiguracji produkcji na magazyn do konfiguracji produkcji na zamówienie wymaga dokładnej analizy struktur produktów, identyfikacji rodzin produktów i modułowości. Aby zmniejszyć liczbę części i zminimalizować liczbę towarów wymaganych w procesie, bardzo ważne jest zapoznanie się z interfejsami produktu i projektowanie do ponownego użycia.  

Istnieje kilka zasad modelowania konfiguracji produktu: oparte na regułach, oparte na wymiarach i oparte na ograniczeniach. Badania pokazują, że metodologia oparta na ograniczeniu pozwala zmniejszyć liczbę wierszy kodu w modelach o około 50 procent w porównaniu z innymi zasadami modelowania. Z tego względu metoda ta pozwala zmniejszyć łączny koszt posiadania (TCO). Przechodząc z modelu opartego na regułach, którego podstawą jest kod języka X++, do modelu opartego na ograniczeniu, nie potrzebujesz już licencji programisty w celu utrzymania modeli produktu.

## <a name="product-configuration"></a>Konfiguracja produktu
Okres industrializacji doprowadził do wielkich osiągnięć w produkcji towarów o wysokiej jakości i bogatej funkcjonalności w przystępnych cenach. Ekonomia skali sprawiła, że większość ludzi w krajach rozwiniętych może kupować samochody, telewizory, sprzęt gospodarstwa domowego i inne dobra, które większość z nas uznaje za niezbędne w codziennym życiu.  

Ponieważ wiele produktów stało się towarami, pojawiła się konieczność ich odróżniania. Natychmiastową reakcją producentów na to wyzwanie było tworzenie wersji produktów, tak aby klienci mieli większy wybór. Ta strategia spowodowała wzrost problemów z prognozowaniem, a także wzrost kosztów utrzymania zapasów oraz niesprzedanych produktów, które stają się przestarzałe.  

Przyjmując filozofię konfiguracji na zamówienie, producent może zaspokoić zapotrzebowanie klientów na niepowtarzalne produkty przy jednoczesnym wyeliminowaniu lub ograniczeniu przestarzałych zapasów. Gdy filozofię produkcji na magazyn zastąpił model konfiguracji na zamówienie, powstał problem, jak krótki czas realizacji pogodzić z niskim stanem zapasów.  

Kluczem do sukcesu na tym polu jest dokładne analizowanie portfolio produktu i poszukiwanie wzorów w funkcjach produktu oraz procesach. Celem jest określenie ogólnych składników, które mogą być wytwarzane przez ten sam sprzęt i używane we wszystkich wariantach produktu.  

Nowa Funkcja konfiguracji produktu uwzględnia interfejs użytkownika, który zapewnia wizualny podgląd struktury modelu konfiguracji produktu oraz składnię ograniczeń deklaratywnych, która nie musi być skompilowana. Dzięki temu firmy, które chcą obsługiwać konfigurację, mogą zacząć o wiele łatwiej. Jak w poniższych sekcjach wyjaśniono, konstruktor produktów nie musi już korzystać z pomocy programisty do zbudowania modelu konfiguracji produktu, przetestowania go i zwolnienia do sprzedaży.

## <a name="building-a-product-configuration-model"></a>Budowanie modelu konfiguracji produktu
Istnieje kilka podejść, które można zastosować przy budowaniu modelu konfiguracji produktu. Jednym z nich jest działanie sekwencyjne polegające na utworzeniu najpierw danych referencyjnych, takich jak produkty główne, produkty odrębne i zasoby operacyjne, a następnie włączeniu ich jako składniki, wiersze list składowych (BOM), operacje marszruty i inne elementy do modelu konfiguracji produktu. Można też zastosować podejście bardziej iteratywne i najpierw utworzyć model, a potem w miarę potrzeb dodawać dane referencyjne.

### <a name="components"></a>Składniki

Model konfiguracji produktu składa się z jednego lub większej liczby składników powiązanych relacjami podskładnika. Składniki są definiowane jeden raz; następnie można ich używać wielokrotnie w jednym lub wielu modelach konfiguracji produktu. Składniki stanowią główne elementy składowe modelu konfiguracji produktu i prawie wszystkie informacje o modelu odnoszą się do nich.

### <a name="attributes"></a>Atrybuty

Każdy składnik ma jeden lub kilka atrybutów, które identyfikują jego właściwości. Atrybuty to elementy, które będą wybierane przez użytkowników w procesie konfiguracji. Atrybuty kontrolują zarówno i relacje między składnikami, jak i wewnątrz składników poprzez włączenie do ograniczeń lub obliczenia. Za pomocą warunków zastosowanych w wierszach BOM, atrybuty mogą określać, z jakich części fizycznych będzie się składał skonfigurowany produkt. Ponadto atrybut może kontrolować właściwość wiersza BOM poprzez mechanizm mapowania. Z podobnych funkcji można skorzystać w przypadku operacji marszruty w ustawieniach włączenia i właściwości.

### <a name="expression-constraints"></a>Ograniczenia wyrażenia

Korzystanie z modelu konfiguracji produktu opartej na ograniczeniu zakłada, że istnieją pewne ograniczenia, gdy użytkownik wybiera wartości różnych atrybutów. Takie ograniczenia mogą być implementowane jako ograniczenia wyrażenia za pomocą języka OML (Optimization Modeling Language). Można też zaimplementować ograniczenie w formie ograniczenia tabeli.

### <a name="table-constraints"></a>Powiązane tabele

Ograniczenia tabel mogą być definiowane przez użytkownika lub przez system.  

Ograniczenie definiowane przez użytkownika tworzy użytkownik. Użytkownik wybiera kombinację typów atrybutów reprezentujących kolumn tabeli, a następnie wprowadza wartości z domen typu wybranego atrybutu w celu utworzenia wierszy ograniczenia tabeli.  

Ograniczenia tabeli definiowane przez system definiuje się, wybierając tabelę programu Microsoft Dynamics 365 for Finance and Operations, która będzie używana jako odwołanie, a następnie wybierając pola z tej tabeli do utworzenia kolumn ograniczenia. Wiersze ograniczenia tabeli to wiersze tabeli programu Finance and Operations, która jest obecna w czasie konfigurowania.  

Ograniczenie tabeli jest uwzględnione w modelu konfiguracji produktu poprzez odwołanie do definicji ograniczenia tabeli i mapowanie odpowiednich atrybutów w modelu do kolumn ograniczenia tabeli.

### <a name="calculations"></a>Obliczenia

Obliczenia reprezentują mechanizm do wykonywania operacji arytmetycznych w modelu konfiguracji. Na przykład obliczenia mogą określić długość określonej części surowca lub czas przetwarzania dla operacji polerowania. Obliczenia są konieczne, a po uwzględnieniu wszystkich wartości atrybutu w wyrażeniu do obliczania można ustawić wartość atrybutu docelowego.

### <a name="subcomponents"></a>Składniki podrzędne

Podskładniki reprezentują węzły w strukturze modelu konfiguracji produktu. Dla każdej relacji podskładnika trzeba określić odwołanie do produktu głównego, który ma ustawioną technologię konfigurowania wariantów jako konfigurację opartą na ograniczeniach.

### <a name="user-requirements"></a>Wymagania użytkownika

Wymaganie użytkownika ma wszystkie elementy podskładnika. Jedyna różnica polega na tym, że wymaganie użytkownika nie jest związane z produktem głównym. W praktyce różnica ta polega na tym, że wszelkie wiersze BOM lub operacje marszruty zdefiniowane w kontekście wymagania użytkownika zostaną zwinięte do struktury BOM lub marszruty składnika nadrzędnego. To zachowanie przypomina zachowanie fantomowego BOM-u.

### <a name="bom-lines"></a>Wiersze BOM

Wiersze BOM są dołączone do identyfikowania BOM produkcji dla każdego składnika. Wiersz BOM musi odwoływać się do pozycji, a wszystkie właściwości pozycji można ustawić jako wartości stałe lub zmapowane do atrybutu.

### <a name="route-operations"></a>Operacje marszruty

Operacje marszruty są dołączone do identyfikowania marszruty produkcji. Operacja marszruty musi się odwoływać do zdefiniowanej operacji, a wszystkie właściwości operacji można ustawić jako wartości stałe. Wszystkie właściwości z wyjątkiem wymagań źródłowych można zmapować do atrybutu zamiast wartości.

## <a name="validating-and-testing-a-product-configuration-model"></a>Sprawdzanie poprawności i testowanie modelu konfiguracji produktu
Sprawdzanie poprawności modelu konfiguracji produktu można wykonać na różnych poziomach w modelu, i może ono obejmować różne zakresy. Najniższy poziom jest przeznaczony dla pojedynczego ograniczenia wyrażenia. W tym przypadku sprawdzanie poprawności jest zwykle wykonywane przez projektanta produktu w celu sprawdzenia poprawności składni wyrażenia.  

Podobnie, można osobno sprawdzić warunek dla wiersza BOM lub operacji marszruty.  

Ponadto można wykonać sprawdzania poprawności dla definicji ograniczenia tabeli zdefiniowanej przez użytkownika. W takim przypadku użytkownik może stwierdzić, że wartości, które są wprowadzane dla każdego pola znajdują się wewnątrz domeny odpowiednich typów atrybutu.  

Na koniec można wykonać sprawdzanie poprawności dla kompletnego modelu konfiguracji produktu, aby sprawdzić, czy kompletna składnia jest poprawna, a wszystkie konwencje nazewnictwa i modelowania są przestrzegane.

### <a name="testing"></a>Testowanie

Testowanie modelu jest podobne do uruchamiania sesji rzeczywistej konfiguracji. Użytkownik może przejrzeć strony konfiguracji i sprawdzić, czy struktura modelu obsługuje proces konfiguracji. Można sprawdzić, czy wartości atrybutów są poprawne, a opisy atrybutów prowadzą użytkownika do wybrania poprawnych wartości. Na koniec po zakończeniu sesji testowej, system próbuje utworzyć BOM i marszrutę odpowiadającą wartościom wybranego atrybutu, a jeśli cokolwiek się nie uda, wyświetli komunikat o błędzie.

### <a name="the-configuration-page"></a>Strona konfiguracji

Aby przechodzić między składnikami, kliknij przycisk **Dalej** lub kliknij składnik w drzewie modelu konfiguracji produktu, aby ustawić na nim fokus.

## <a name="finalizing-a-model-for-configuration"></a>Finalizowanie modelu do konfiguracji
Gdy model konfiguracji produktu jest gotowy do użycia w scenariuszach konfigurowania na zamówienie, należy utworzyć wersję. Istnieje jednak kilka opcji, które mogą ułatwić proces modelowania.

### <a name="user-interface"></a>Interfejs użytkownika

Interfejs użytkownika konfiguracji można zmodyfikować, wprowadzając grupy atrybutów do jednego lub kilku składników. Takie grupowanie może wyróżnić relacje między określonymi atrybutami i pomagać użytkownikowi konfiguracji w określeniu obszaru produktu, na którym jest aktualnie fokus.

### <a name="templates"></a>Szablony

Aby przyspieszyć proces konfiguracji można utworzyć jeden lub większą liczbę szablonów konfiguracji. Można też tworzyć szablony celu promowania kombinacji określonych atrybutów, np. gdy kampania sprzedażowa koncentruje się na konkretnym zestawie funkcji produktu.

### <a name="translations"></a>Tłumaczenia

Jeśli produkt będzie sprzedawany w różnych krajach/regionach, można utworzyć tłumaczenia całego tekstu, który będzie wyświetlany w interfejsie użytkownika konfiguracji. Ten tekst zawiera nie tylko pola nazwy i opisu, ale także wartości tekstowe atrybutu.

### <a name="versions"></a>Wersje

Ostatnim i najważniejszym etapem procesu finalizowania jest utworzenie wersji dla modelu konfiguracji produktu. Wersja reprezentuje relację między produktem głównym, który można wybrać dla konfiguracji zamówienia lub wiersza zapytania, a modelem konfiguracji produktu. Przed uruchomieniem i użyciem wersji w sesji konfiguracji należy zatwierdzić wersję.

## <a name="extending-a-product-configuration-model-through-the-api"></a>Rozszerzanie modelu konfiguracji produktu za pomocą interfejsu API
Został zaimplementowany dedykowany interfejs programowania aplikacji, więc partnerzy i inne osoby posiadające licencję programisty, mogą rozszerzać możliwości modelu konfiguracji produktu. Głównym celem było stworzenie mechanizmu umożliwiającego partnerom i klientom korzystającym z obecnego modułu Konstruktor produktów migrację kodu, który jest osadzony w modelach Konstruktora produktów, do interfejsu API. W ten sposób można przenosić modele z Konstruktora produktów do konfiguracji produktu. Ale nowi partnerzy i klienci mogą także używać interfejsu API do rozszerzania nowych modeli konfiguracji produktu.

### <a name="pcadaptor-class"></a>Klasa PCAdaptor

Interfejs API jest implementowany przy użyciu zestawu klas **PCAdaptor** udostępniających strukturę danych modeli konfiguracji produktu. Wystąpienia klasy **PCAdaptor** należy utworzyć dla każdego modelu, który zostanie rozszerzony. Po zakończeniu sesji konfiguracji, system sprawdza, czy jest wystąpienie tej klasy, i uruchamia je, jeśli je znajdzie.  

Na poniższym diagramie opisano ten proces.  

[![Diagram przepływu](./media/product_configuration_2.png)](./media/product_configuration_2.png)  

Diagram przepływu interfejsu API konfiguracji produktu

## <a name="product-configuration"></a>Konfiguracja produktu
Konfigurację produktu można wykonać z następujących miejsc:

-   Wiersz zamówienia sprzedaży
-   Wiersz oferty sprzedaży
-   Wiersz zamówienia zakupu
-   Wiersze zlecenia produkcyjnego
-   Wiersz zapotrzebowania na towary (projekt)

Celem konfiguracji jest utworzenie różnych wariantów produktu, które spełnią zapotrzebowanie odbiorcy. Dla każdej nowej konfiguracji jest tworzony unikatowy identyfikator. Ten identyfikator umożliwia śledzenie w magazynie.

### <a name="multiple-sites-and-intercompany"></a>Wiele witryn i międzyfirmowe

Jeśli konfiguracja zostanie wykonana w oddziale lub nawet w firmie, która różni się od oddziału lub firmy, w których będzie wykonywana produkcja, zostaną utworzone BOM i marszruta i umieszczone w zakładzie dostawcy w firmie zaopatrzeniowej. Wariant produktu zostanie zwolniony we wszystkich firmach, które uczestniczą w łańcuchu dostaw.



