---
title: Marszruty i operacje
description: Ten temat zawiera informacje o marszrutach i operacjach.
author: sorenva
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
ms.author: sorenand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 961cc6fe5bd1bfbb0f5c9116024415a5d53f569e
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1522204"
---
# <a name="routes-and-operations"></a>Marszruty i operacje

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o marszrutach i operacjach. Marszruta definiuje proces wytwarzania produktu lub wariantu produktu. Opisuje każdy krok (operację) w procesie produkcji oraz kolejność, w jakiej te kroki należy wykonać. Dla każdego kroku marszruta definiuje również wymagane zasoby operacyjne, wymagane czasy przezbrajania i wykonywania oraz sposób obliczania kosztów.

<a name="overview"></a>Przegląd
--------

Marszruta opisuje kolejność operacji niezbędnych w celu wytworzenia produktu lub wariantu produktu. Dla każdej operacji marszruta definiuje również wymagane zasoby operacyjne, czas potrzebny na przezbrojenie i wykonanie operacji oraz sposób obliczania kosztów. Można użyć tej samej marszruty do wytwarzania wielu produktów lub zdefiniować unikatową marszrutę dla każdego produktu lub wariantu produktu. Można nawet mieć wiele marszrut dla tego samego produktu. W takim przypadku używana marszruta zmienia się i zależy od czynników takich jak ilość, która musi zostać wyprodukowana. Definicja marszruty w programie Microsoft Dynamics 365 for Finance and Operations składa się z czterech oddzielnych elementów, które wspólnie opisują proces produkcji:

-   **Marszruta** — Marszruta definiuje strukturę procesu produkcji. Innymi słowy definiuje kolejność operacji.
-   **Operacja** — Operacja identyfikuje nazwany krok w marszrucie, taki jak **Montaż**. Ta sama operacja może wystąpić w wielu marszrutach i mieć różne numery operacji.
-   **Relacja operacji** — Relacja operacji definiuje właściwości operacyjnych operacji, takie jak czasy przezbrajania i wykonywania, kategorie kosztów, parametry zużycia i zapotrzebowanie na zasoby. Relacja operacji umożliwia różnicowanie właściwości operacyjnych operacji w zależności od marszruty, w której jest używana operacja, lub produktów, które są wytwarzane.
-   **Wersja marszruty** — Wersja marszruty określa marszrutę używaną do wytworzenia produktu lub wariantu produktu. Wersje marszrut umożliwiają wykorzystywanie marszrut do różnych produktów lub ich późniejszą zmianę. Umożliwiają również używanie różnych marszrut do wytwarzania tego samego produktu. W takim przypadku używana marszruta zależy od czynników takich jak lokalizacja lub ilość, która musi zostać wyprodukowana.

## <a name="routes"></a>Marszruty
Marszruta opisuje kolejność operacji niezbędnych do wytworzenia produktu lub wariantu produktu. Każdej operacji jest przypisywany numer operacji i operacja następująca. Kolejność operacji tworzy sieć marszrut, które mogą być reprezentowane przez ukierunkowany wykres mający jeden lub więcej punktów początkowych i jeden punkt końcowy. W programie Finance and Operations marszruty są rozróżniane na podstawie typu struktury. Istnieją dwa typy marszrut: proste i sieciowe. W oknie Parametry kontroli produkcji można określić, czy mogą być używane tylko marszruty proste czy też można używać bardziej złożonych marszrut sieciowych.

### <a name="simple-routes"></a>Marszruty proste

Marszruta prosta jest sekwencyjna i istnieje tylko jeden punkt początkowy marszruty.  

[![Marszruta prosta](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Jeśli w oknie Parametry kontroli produkcji zostanie włączona obsługa tylko prostych marszrut, program Finance and Operations będzie automatycznie generował numery operacji (10, 20, 30 i tak dalej) podczas definiowania marszruty.

### <a name="route-networks"></a>Marszruty sieciowe

Jeśli w oknie Parametry kontroli produkcji włączysz obsługę bardziej złożonych marszrut sieciowych, można definiować marszruty mające wiele punktów początkowych oraz operacje, które mogą być wykonywane równolegle.  

[![Marszruty sieciowe](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

> [!NOTE]
> -   Każda operacja może mieć tylko jedną operację następującą, a cała marszruta musi się kończyć w jednej operacji.
> -   Nie ma żadnej gwarancji, że wiele operacji mających tę samą operację następującą (na przykład operacje 30 i 40 na wcześniejszej ilustracji) będą rzeczywiście wykonywane równolegle. Dostępność i zdolności produkcyjne zasobów mogą nakładać ograniczenia na sposób planowania operacji.
> -   Nie można używać wartości 0 (zero) jako numeru operacji. Ten numer jest zarezerwowany i służy do określania, że ostatnia operacja w marszrucie ma żadnej operacji następującej.

### <a name="parallel-operations"></a>Operacje równoległe

Czasami w celu wykonania operacji jest wymagane połączenie wielu zasobów operacyjnych mających różne charakterystyki. Na przykład operacja montażu może wymagać maszyny, narzędzia oraz jednego pracownika nadzoru na każdą parę maszyn. Ten przykład można wymodelować przy użyciu operacji równoległych, gdzie jedna operacja jest wyznaczona jako główna, a pozostałe jako podrzędne.  

[![Marszruta zawierająca operacje główne i podrzędne](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Zazwyczaj operacja główna reprezentuje zasób w wąskim gardle i decyduje o czasie wykonywania operacji podrzędnych. Jednak podczas planowania obejmującego ograniczone zdolności produkcyjne zasoby, które są planowane zarówno dla operacji głównej, jak i operacji pomocniczych, muszą być dostępne i mieć wolne moce produkcyjne w tym samym czasie.  

Zarówno operacja główna, jak i operacje podrzędne muszą mieć ten sam numer operacji (30 na wcześniejszej ilustracji).  

W poprzednim przykładzie zapotrzebowaniem na zasób dla operacji głównej (30) jest maszyna, natomiast zapotrzebowaniami na zasoby dla operacji podrzędnych (30' i 30'') są narzędzie i pracownik. Pięćdziesięcioprocentowe obciążenie pracą pomaga zagwarantować, że zaplanowany pracownik może nadzorować dwie maszyny w tym samym czasie.

### <a name="approval-of-routes"></a>Zatwierdzenie marszrut

Marszruta musi zostać zatwierdzona, żeby można było jej użyć w procesie planowania lub produkcji. Zatwierdzenie wskazuje, że projektowanie marszruty zostało ukończone. Ten sam zwolniony produkt albo zwolniony wariant produktu może mieć wiele zatwierdzonych marszrut. Na ogół zatwierdzenie marszruty następuje, gdy zostanie zatwierdzona pierwsza wersja odnośnej marszruty. Jednak w niektórych scenariuszach biznesowych zatwierdzanie marszruty i wersji marszruty to oddzielne działania, które mogą obejmować różnych właścicieli procesów.  

Każdą marszrutę można z osobna zatwierdzać lub odmawiać zatwierdzenia. Należy zwrócić uwagę, że jeśli marszruta jest niezatwierdzona, wszystkie powiązane wersje marszruty są również niezatwierdzone. W oknie Parametry kontroli produkcji można określić, czy marszruty mogą być niezatwierdzone i czy zatwierdzone marszruty można edytować.  

Jeśli trzeba prowadzić dziennik przechowujący informacje o tym, kto zatwierdza każdą marszrutę, można wymagać podpisów elektronicznych dla zatwierdzania marszrut. Wtedy użytkownicy będą musieli potwierdzić swoją tożsamość za pomocą [podpisu elektronicznego](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

## <a name="operations"></a>Operations
Operacja jest etapem procesu produkcji. W programie Finance and Operations każda operacja ma identyfikator i prosty opis. Następujące tabele przedstawiają typowe przykłady operacji w warsztacie.

| Operacja  | opis        |
|------------|--------------------|
| PipeCut    | Cięcie rur       |
| TIGweld    | Spawanie metodą TIG        |
| JigAssy    | Mocowanie w przyrządzie obróbkowym       |
| Kontrola | Kontrola jakości |

Właściwości operacyjne operacji, takie jak czasy przezbrajania i wykonywania, zapotrzebowanie na zasoby, informacje o kosztach i obliczenia zużycia, określa się w relacji operacji. Więcej informacji o relacjach operacji znajdziesz w następnej części.

## <a name="operation-relations"></a>Relacje operacji
W relacji operacji są przechowywane następujące właściwości operacyjnych operacji:

-   Kategorie kosztu
-   Parametry zużycia
-   Czasy przetwarzania
-   Ilości przetwarzania
-   Zapotrzebowanie na zasoby
-   Uwagi i instrukcje

Dla jednej operacji można zdefiniować wiele relacji operacji. Jednak każda relacja operacji jest specyficzna dla jednej operacji i przechowuje właściwości specyficzne dla marszruty, zwolnionego produktu lub zbioru zwolnionych produktów, które są powiązane z grupą towarów. W związku z tym tej samej operacji można używać w wielu marszrutach mających różne właściwości operacyjne. Ponadto można łatwiej utrzymywać dane główne, jeśli używasz standardowych operacji mających takie same właściwości operacyjne bez względu na używaną marszrutę ani wytwarzany produkt. Zakres relacji operacji jest definiowany za pomocą właściwości **Kod pozycji**, **Relacja produktu**, **Kod marszruty** i **Relacja do marszruty**, jak pokazano w poniższej tabeli.

| Kod pozycji | Relacja produktu         | Kod marszruty | Relacja do marszruty   | Zakres relacji operacji                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabela     | &lt;Identyfikator towaru&gt;       | Marszruta      | &lt;Identyfikator marszruty&gt; | Właściwości operacyjne operacji używanej w marszrucie o atrybucie **Numer marszruty**=&lt;identyfikator marszruty&gt;, w celu wytworzenia zwolnionego produktu o atrybucie **Numer pozycji**=&lt;identyfikator towaru&gt;.                                                                                                                        |
| Tabela     | &lt;Identyfikator towaru&gt;       | Wszystko        |                  | Domyślne właściwości operacyjne operacji używanej w celu wytworzenia zwolnionego produktu o atrybucie **Numer pozycji**=&lt;identyfikator towaru&gt;. Innymi słowy te właściwości operacyjne mają zastosowanie, gdy zwolniony produkt nie ma żadnej relacji operacji specyficznej dla marszruty.                                     |
| Grupa     | &lt;Identyfikator grupy towarów&gt; | Marszruta      | &lt;Identyfikator marszruty&gt; | Właściwości operacyjne operacji używanej w marszrucie o atrybucie **Numer marszruty**=&lt;identyfikator marszruty&gt; w celu wytworzenia zwolnionych produktów skojarzonych z grupą towarów &lt;identyfikator grupy towarów&gt;, chyba że dla zwalnianego produktu istnieje operacja specyficzna dla relacji.                         |
| Grupa     | &lt;Identyfikator grupy towarów&gt; | Wszystko        |                  | Domyślne właściwości operacyjne operacji używanej do wytworzenia zwolnionych produktów skojarzonych z grupą towarów &lt;identyfikator grupy towarów&gt;, chyba że istnieje bardziej specyficzna relacja operacji.                                                                                                  |
| Wszystko       |                       | Marszruta      | &lt;Identyfikator marszruty&gt; | Domyślne właściwości operacyjne operacji używanej w marszrucie o atrybucie **Numer marszruty**=&lt;identyfikator marszruty&gt;. Innymi słowy te właściwości operacyjne mają zastosowanie, gdy marszruta nie ma żadnej relacji operacji specyficznej dla zwolnionego produktu ani skojarzonej z nim grupy towarów. |
| Wszystko       |                       | Wszystko        |                  | Domyślne właściwości operacyjne operacji. Te właściwości operacyjne mają zastosowanie, gdy nie istnieje bardziej specyficzna relacja operacji.                                                                                                                                                                |

Można również określić, że relacja operacji jest specyficzna dla oddziału. W ten sposób właściwości operacyjne operacji mogą się różnić w zależności od lokalizacji (oddziału), gdzie operacja jest wykonywana. W przypadku produktów skonfigurowanych można również określić różne właściwości operacyjne dla każdej konfiguracji produktu.  

Relacje operacji dają dużą elastyczność podczas definiowania marszrut. Ponadto możliwość definiowania właściwości domyślnych pomaga zmniejszyć ilość danych głównych, które należy przechowywać. Jednak ta elastyczność oznacza również, że trzeba mieć na uwadze kontekst, w którym jest modyfikowana relacja operacji.  

> [!NOTE]
> Uwaga: Ponieważ właściwości operacyjne są przechowywane w relacjach operacji dla poszczególnych operacji z podziałem na marszruty, wszystkie wystąpienia tej samej operacji (na przykład Montaż) mają taki sam czas przezbrajania, czasu wykonywania, zapotrzebowania na zasoby i tak dalej. W związku z tym jeśli dwa wystąpienia operacji muszą występować w tej samej marszrucie, ale mają różne czasy wykonywania, należy utworzyć dwie odrębne operacje, takie jak Montaż1 i Montaż2.

### <a name="modifying-product-specific-routes"></a>Modyfikowanie marszrut specyficznych dla produktów

Po otwarciu strony **Marszruta** ze strony **Szczegóły zwolnionego produktu** są wyświetlane wersje marszruty skojarzone z wybranym zwolnionym produktem. W tym kontekście dla każdej operacji program Finance and Operations pokazuje właściwości operacyjne z relacji operacji najlepiej pasującej do wersji marszruty. Można zauważyć, że lista operacji zawiera właściwości **Kod pozycji** i **Kod marszruty** z relacji operacji. W związku z tym można określić, która relacja operacji jest wyświetlana.  

Na stronie **Marszruta** można zmodyfikować właściwości operacyjnych operacji, takie jak czas wykonywania lub kategorie kosztów. Wprowadzone zmiany są przechowywane w relacji operacji specyficznej dla marszruty i zwolnionego produktu, do których odwołuje się bieżąca wersja marszruty. Jeśli wyświetlana relacja operacji nie jest specyficzna dla marszruty i zwolnionego produktu, przed zapisaniem zmian system tworzy kopię relacji operacji. Ta kopia *jest* specyficzna dla marszruty i zwolnionego produktu. W związku z tym wprowadzone zmiany nie mają wpływu na pozostałe marszruty ani zwolnione produkty. Aby sprawdzić, która relacja operacji jest modyfikowana na stronie **Marszruta**, spójrz w pola **Kod pozycji** i **Kod marszruty**.  

Można także ręcznie utworzyć operację specyficzną dla marszruty i zwolnionego produktu za pomocą funkcji **Kopiuj i edytuj relację**.  

> [!NOTE]
> Jeśli dodasz nową operację do marszruty na stronie **Marszruta**, relacja operacji zostanie utworzona tylko dla bieżącego zwolnionego produktu. Dlatego jeśli marszruta jest również używana do wytwarzania innych zwolnionych produktów, nie będzie istniała żadna relacja operacji mająca zastosowanie do tych zwolnionych produktów i marszruty nie będzie można już używać dla tych zwolnionych produktów.

### <a name="maintaining-operation-relations-per-route"></a>Obsługa relacji operacji w marszrucie

Po otwarciu strony **Szczegóły marszruty** ze strony listy **Marszruty** pojawi się lista wszystkich relacji operacji mających zastosowanie do wybranej marszruty. W związku z tym można łatwo sprawdzić, które właściwości operacyjne są używane do których produktów. Można zmodyfikować domyślne wartości właściwości oraz wartości właściwości specyficzne dla produktu.  

Po dodaniu nowej relacji operacji na stronie **Szczegółów marszruty** pole **Kod marszruty** jest automatycznie ustawiane na **Marszruta**, a pole **Relacja do marszruty** jest ustawiane na numer marszruty bieżącej marszruty.

### <a name="maintaining-operation-relations-per-operation"></a>Obsługa relacji operacji w operacji

Na stronie **Operacje** można otworzyć stronę **Relacje operacji**. Na tej stronie można zmodyfikować wszystkie relacje operacji dla określonej operacji. Można nawet modyfikować relacje operacji zawierające wartości domyślne.  

Jeśli firma używa standardowych operacji, a parametry operacyjne są takie same we wszystkich produktach i procesach, strona **Relacje operacji** oferuje wygodny sposób zarządzania domyślnymi właściwościami operacyjnymi tych operacji.

### <a name="applying-operation-relations"></a>Stosowanie relacji operacji

W niektórych przypadkach program Finance and Operations musi znaleźć właściwości operacyjne operacji. Na przykład podczas tworzenia zamówienia zakupu właściwości operacyjne każdej operacji muszą zostać skopiowane z relacji operacji do marszruty produkcji. W takich sytuacjach program Finance and Operations szuka odnośnych relacji operacji w porządku od najbardziej specyficznej kombinacji do najmniej specyficznej kombinacji.  

Kiedy program Finance and Operations szuka najbardziej odpowiedniej relacji operacji dla zwolnionego produktu, relacja operacji pasująca do identyfikatora towaru zwolnionego produktu jest preferowana wobec relacji operacji, która pasuje do identyfikator grupy towarów. Z kolei relacja operacji pasująca do identyfikatora grupy towarów jest preferowana wobec domyślnej relacji operacji. Wyszukiwanie odbywa się w następującej kolejności:

1.  **Kod pozycji**=**Tabela** i **Relacja produktu**=&lt;identyfikator towaru&gt;
2.  **Kod pozycji**=**Grupa** i **Relacja produktu**=&lt;identyfikator grupy towarów&gt;
3.  **Kod pozycji**=**Wszystko**
4.  **Kod marszruty**=**Marszruta** i **Relacja do marszruty**=&lt;identyfikator marszruty&gt;
5.  **Kod marszruty**=**Wszystko**
6.  **Konfiguracja**=&lt;identyfikator konfiguracji&gt;
7.  **Konfiguracja**=
8.  **Oddział**=&lt;identyfikator oddziału&gt;
9.  **Oddział**=

W związku z tym operacji należy użyć tylko jeden raz dla każdej marszruty. Jeśli operacja występuje wiele razy w tej samej marszrucie, wszystkie wystąpienia tej operacji będą miały tę samą relację operacji i nie będzie można zdefiniować różnych właściwości (na przykład czasów wykonywania) dla każdego wystąpienia.

## <a name="route-versions"></a>Wersje marszruty
Wersje marszruty pozwalają dostosować warianty wytwarzania produktów lub uzyskać lepszą kontrolę nad procesem produkcji. Określają, które marszruty powinny być używane podczas wytwarzania określonego zwolnionego produktu lub zwolnionego wariantu produktu. Można używać następujących ograniczeń do definiowania, która marszruta ma być używana dla zwolnionego produktu:

-   Wymiary produktów (rozmiar, kolor, styl lub konfiguracja)
-   Ilość produkcji
-   Oddział produkcji
-   Data produkcji

Gdy produkt jest wytwarzany w określonym oddziale, określonej ilości lub określonym okresie, można wyznaczyć określoną wersję marszruty jako domyślną wersję marszruty. Należy jednak zwrócić uwagę, że jest dozwolona tylko jedna aktywna marszruta dla danego zwolnionego produktu i danego zestawu ograniczeń.  

W oknie Parametry kontroli produkcji można określić wymóg, że zawsze ma być podawany okres ważności wersji marszruty.

### <a name="approval-of-route-versions"></a>Zatwierdzanie wersji marszrut

Aby można było używać wersji marszruty w procesie planowania lub produkcji, musi ona zostać zatwierdzona. Po zatwierdzeniu wersji marszruty można zatwierdzić również odnośną marszrutę. Należy zwrócić uwagę, że wersję marszruty można zatwierdzić tylko wtedy, jeśli zatwierdzono również powiązaną marszrutę.

### <a name="activating-the-default-route-version"></a>Aktywowanie domyślnej wersji marszruty

Podczas aktywacji wersji marszruty wyznaczasz ją jako domyślną wersję marszruty, która będzie używana w planowaniu głównym lub będzie służyła do tworzenia zleceń produkcyjnych. Można mieć tylko jedną aktywną wersję marszruty dla danego zestawu ograniczeń (na przykład okres, oddział lub ilość). Jeśli wersja, którą próbujesz uaktywnić, powoduje konflikt z wersją już aktywną, zostanie wyświetlony komunikat o błędzie. Aby uniknąć niejednoznacznej aktywacji, należy następnie zdezaktywować wersję powodującą konflikt lub zmodyfikować ograniczenia (zwykle okres) w wersji marszruty.

### <a name="electronic-signatures"></a>Podpisy elektroniczne

Jeśli trzeba prowadzić dziennik przechowujący informacje o tym, kto zatwierdza i aktywuje każdą wersję marszruty, można wymagać podpisów elektronicznych dla tych zadań. Wtedy użytkownicy, którzy zatwierdzają i aktywują wersje marszrut, będą musieli potwierdzić swoją tożsamość za pomocą [podpisu elektronicznego](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

### <a name="product-change-that-uses-case-management"></a>Zmiany w produkcie używającym funkcji zarządzania sprawami

Sprawa zmiany w produkcie do zatwierdzenia i uaktywnienia nowych lub zmienionych marszrut i wersji marszrut zapewnia prosty sposób przeglądania ograniczeń wersji marszrut. Można również zatwierdzić i aktywować wszystkie marszruty związane z określoną zmianą w jednej operacji oraz udokumentować wyniki w sprawie zmiany w produkcie.

## <a name="maintaining-routes"></a>Obsługa marszrut
W zależności od wymagań biznesowych może być możliwe zmniejszenie nakładu pracy wymaganego do zarządzania definicjami procesów.

### <a name="making-routes-independent-of-resources"></a>Uniezależnianie marszrut od zasobów

W wielu systemach w marszrucie należy określić zasób operacyjny lub grupę zasobów, które mają wykonać operację. Jednak w programie Finance and Operations można zdefiniować zestaw wymagań, które musi spełnić zasób operacyjny, aby mieć zastosowanie do operacji. W związku z tym konkretny zasób operacyjny lub grupa zasobów, które mają być używane, mogą zostać określone dopiero w trakcie faktycznego planowania operacji. Ta funkcja jest szczególnie przydatna, gdy masz wielu pracowników lub maszyn mogących wykonać tę samą operację.  

Na przykład określasz, że operacja wymaga zasobu operacyjnego typu **Maszyna** o możliwości **Tłoczenie** wynoszącej 20 ton. Aparat planowania następnie powiąże te wymagania z określonym zasobem operacyjnym lub grupą zasobów w trakcie planowania operacji. Ponieważ można po prostu określić te wymagania zamiast przypisywać operacje do określonej maszyny, masz znacznie większą elastyczność. Dodatkowo jest łatwiejsze zarządzanie w trakcie przenoszenia zasobów lub dodawania nowych zasobów.  

Aby uzyskać więcej informacji na temat różnych rodzajów zapotrzebowań na zasoby i sposobu ich używania, zobacz sekcje Zapotrzebowania na zasoby operacyjne i [Możliwości zasobu](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Udostępnianie marszrut między oddziałami

Jeśli wytwarzasz ten sam produkt w więcej niż jednym oddziale produkcji, a kroki wytwarzania produktu są takie same we wszystkich oddziałach, często można zaprojektować udostępnioną marszrutę, która będzie używana we wszystkich oddziałach produkcji. Aby utworzyć udostępnioną marszrutę, nie określaj oddziału w samej marszrucie. Jednakże nadal należy utworzyć wersję marszruty, która kojarzy udostępnioną marszrutę z produktem w każdym oddziale.  

Również należy się upewnić, że zapotrzebowania na zasoby dla każdej operacji w marszrucie nie określają konkretnych zasobów operacyjnych ani grup zasobów, ale zamiast tego są wyrażone w postaci charakterystyki wymaganych zasobów. Aparat planowania będzie wtedy w stanie przypisać odpowiednie zasoby operacyjne z oddziału, w którym zaplanowano produkcję. Na przykład jeśli istnieje niewielka różnica w czasie wykonywania albo czas przezbrajania w określonej operacji jest specyficzny dla oddziału, można podać te informacje poprzez dodanie kolejnej relacji operacji dla tego oddziału.  

Aby w pełni wykorzystać zalety marszrut udostępnionych, należy również użyć zużycia zasobów w odnośnej liście składowej (BOM). Gdy ustawisz flagę zużycia zasobu w wierszu BOM, magazyn i lokalizacja, z których powinny być zużywane surowce, są wnioskowane z zasobu operacyjnego zaplanowanego dla operacji. W związku z tym magazyn i lokalizacja mogą zostać określone dopiero w trakcie faktycznego planowania produkcji. W ten sposób zarówno BOM, jak i marszruta mogą być niezależne od fizycznej lokalizacji, w której jest wytwarzany produkt.

### <a name="standard-operation-relations"></a>Standardowe relacji operacji

Jeśli firma stosuje standardowe operacje w całej produkcji, a czasy przezbrajania, czasy wykonywania, obliczenia zużycia, obliczenia kosztów itd. różnią się niewiele lub w ogóle, być może warto utworzyć domyślne relacje operacji dla wszystkich operacji. W takim przypadku należy unikać tworzenia relacji operacji, które są specyficzne dla którejkolwiek trasy lub zwolnionego produktu.  

Jeśli również zapotrzebowania na zasoby są wyrażane w kategoriach umiejętności i możliwości, a marszruty są niezależne od oddziału, istnieje możliwość ograniczenia bieżącego zarządzania procesami biznesowymi do minimum.  

Kiedy używasz tej metody, strona **Relacje operacji** staje się głównym miejscem zarządzania czasami wykonywania i innymi właściwościami.

### <a name="resource-specific-process-times"></a>Czasy procesów specyficzne dla zasobów

Jeśli w ramach zapotrzebowania na zasoby dla operacji nie określisz zasobu operacyjnego ani grupy zasobów, odnośne zasoby mogą pracować z różnymi prędkościami. W związku z tym czas potrzebny na przetwarzanie operacji może się różnić. Aby rozwiązać ten problem, można użyć pola **Formuła** w relacji operacji, aby określić sposób obliczania czasu procesu. Dostępne są następujące opcje:

-   **Standardowy** — (Opcja domyślna) W obliczeniu są używane tylko pola z relacji operacji, a podany czas wykonywania jest mnożony przez ilość zamówienia.
-   **Zdolności produkcyjne** — Obliczanie obejmuje pole **Zdolności produkcyjne** z zasobu operacyjnego. W związku z tym czas jest zależny od zasobu. Wartość określona w zasobie operacyjnym jest zdolnościami produkcyjnymi na godzinę. Wartość ta jest mnożona przez ilość zamówienia i wartość **Współczynnik** z relacji operacji.
-   **Partia** — Wielkość partii jest obliczana przy użyciu informacji z relacji operacji. Liczbę partii, i w związku z tym czas procesu, można następnie obliczyć na podstawie ilości zamówienia.
-   **Partia zasobów** — Ta opcja zasadniczo działa tak samo, jak opcja **Partia**. Jednak obliczanie obejmuje pole **Wielkość partii** z zasobu operacyjnego. W związku z tym czas jest zależny od zasobu.

### <a name="set-up-route-groups"></a>Ustawianie grup marszrut

Można zdefiniować grupy marszrut i ustawienia dotyczące marszruty oraz typów zadań w obszarze **kontrola produkcji > Ustawienia > marszruty > grupy marszrut**. Dla każdego typu marszruty/zadania grupy marszruty można zaznaczyć lub wyczyścić następujące opcje:

- **Aktywacja** — Wybierz tę opcję, aby włączyć obliczenia i planowanie dla wybranego typu zadania i otrzymywać informacje zwrotne podczas uruchamiania planowania zadań. Należy wybrać tę opcję, aby włączyć typ zadania, a następnie trzeba wybrać pozostałe opcje dla tego typu zadania. Jeśli aktywacja nie jest zaznaczona, tego typu zadania nie zostaną włączone, bez względu na wybór innych opcji. 
- **Zarządzanie zadaniem** — Wybierz tę opcję, aby uwzględnić typ zadania w zarządzaniu zadaniami, gdy uruchamiasz planowanie zadań. 
- **Czas pracy** — Wybierz tę opcję, aby zaplanować typ zadania według kalendarza czasu pracy zdefiniowanego dla zasobu operacyjnego, w przeciwnym razie będzie używany kalendarz gregoriański. Czas pracy można planować według kalendarza gregoriańskiego lub zdefiniowanego kalendarza czasu pracy. Wybranie tej opcji sprawia, że planowanie jest oparte zdefiniowanym kalendarzu czasu pracy. Ponadto zadanie danego typu jest planowane od północy dnia zdefiniowanego jako data rozpoczęcia zadania.
- **Zdolności produkcyjne** — Wybierz tę opcję, aby zarezerwować zdolności produkcyjne dla typu zadania, gdy uruchamiasz planowanie zadań. Jeśli zostanie wybrana ta opcja, zdolności produkcyjne są rezerwowane po uruchomieniu planowania dla wybranego typu zadania. Dzięki temu można zobaczyć, które typy zadań w poszczególnych grupach marszruty używają zasobów operacyjnych. Na przykład w sytuacji, gdy zasoby suszące, są wąskimi gardłami, te zasoby muszą być określone jako wąskie gardła. Operacje suszenia, które są przypisane do zadań typu Czas oczekiwania będą rezerwowały zasoby suszące. 

Dla każdego typu zadania należy najpierw włączyć lub wyłączyć go. W przypadku wyłączenia żadne z pozostałych konfiguracji (zarządzania zadaniami, czasu pracy i zdolności produkcyjnych) nie będą brane pod uwagę, ponieważ typ zadania nie będzie aktywny. 

Wśród typów zadań można znaleźć Nakładanie. Nakładanie pozwala na wykonywanie różnych zadań w tym samym czasie. Gdy zadania nakładają się, zasoby mogą być używane, ale nie mogą być zarezerwowane dla określonych zadań.
Z tego względu po aktywacji Nakładania pozostałe ustawienia (zarządzanie zadaniem, czas pracy i zdolności produkcyjne) nie będą miały żadnego wpływu na grupę marszruty. 

> [!NOTE]
> Po uaktualnieniu wersji, może wystąpić następujący błąd: **Podczas wywoływania aparatu planowania wystąpił błąd środowiska CLR**. Jeśli wystąpi ten błąd, należy przejść na stronę **grupy marszruty** i dla wszystkich marszrut, dla których zostało aktywowane **Nakładanie**, należy usunąć zaznaczenie opcji **zarządzanie zadaniem**, **czas pracy** i **zdolności produkcyjne**. 

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Listy składowe (BOM) i formuły](bill-of-material-bom.md)

- [Kategorie kosztów używane podczas wyboru trasy produkcji](../cost-management/cost-categories-used-production-routings.md)

- [Możliwości zasobu](resource-capabilities.md)

- [Omówienie podpisów elektronicznych](../../fin-and-ops/organization-administration/electronic-signature-overview.md)



