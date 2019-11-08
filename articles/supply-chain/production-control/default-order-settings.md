---
title: Domyślne ustawienia zamówień dla wymiarów i wariantów produktów
description: 'Domyślne ustawienia zamówień definiują: oddział i magazyn, skąd towary będą pobierane lub gdzie będą przechowywane; ilości minimalne, maksymalne, wielokrotne i standardowe, które będą używane do handlu lub zarządzania zapasami; czasy realizacji; flagę blokady; metodę tworzenia zobowiązań zamówień.'
author: roxanadiaconu
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d13aabfb36e8af4a32de8bc8949e8b164075532a
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570709"
---
# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Domyślne ustawienia zamówienia dla wymiarów i wariantów produktu

[!include [banner](../includes/banner.md)]

Domyślne ustawienia zamówień w Dynamics 365 Supply Chain Management definiują: oddział i magazyn, skąd towary będą pobierane lub gdzie będą przechowywane; ilości minimalne, maksymalne, wielokrotne i standardowe, które będą używane do handlu lub zarządzania zapasami; czasy realizacji; flagę blokady; metodę tworzenia zobowiązań zamówień. Domyślne ustawienia zamówień są stosowane przy tworzeniu zamówień zakupu, zamówień sprzedaży, zamówień przeniesienia i arkuszy magazynowych oraz w planowaniu głównym do generowania zamówień planowanych. Domyślne ustawienia zamówień mogą być specyficzne dla towaru, oddziału, wariantu produktu lub wymiaru produktu.

Na stronie **Ustawienia domyślne zamówień** można wprowadzić domyślne parametry zamówień. Aby otworzyć tę stronę, wybierz kolejno opcje **Zarządzanie informacjami o produktach** &gt; **Produkty** &gt; **Zwolnione produkty** &gt; **Wybór zwalnianego produktu** &gt; w okienku akcji **Plan** lub **Zarządzanie zapasami** &gt; **Ustawienia zamówienia** &gt; **Ustawienia domyślne zamówień**.

## <a name="default-order-settings"></a>Ustawienia domyślne zamówień
Istnieją trzy typy domyślnych ustawień zamówień: dla zakupów, sprzedaży i zapasów. Domyślne ustawienia zamówień dla zakupów są używane podczas tworzenia następujących obiektów:

-   Wiersze zamówienia zakupu
-   Wiersze umowy zakupu
-   Wiersze zapytania ofertowego
-   Wiersze zapotrzebowania na zakup
-   Wiersze uzupełnienia zapasów konsygnacyjnych
-   Planowane zamówienia zakupu

Domyślne ustawienia zamówień dla sprzedaży są używane podczas tworzenia następujących obiektów:

-   Wiersze zamówienia sprzedaży
-   Wiersze umowy sprzedaży
-   Wiersze oferty sprzedaży
-   Wiersze zamówień zwrotu i wiersze wymiany towaru
-   Wiersze prognozy popytu

Domyślne ustawienia zamówień sprzedaży są również stosowane podczas tworzenia następujących obiektów:

-   Wymagania dotyczące pozycji projektu
-   Zapotrzebowanie na towary w zleceniu serwisowym

Domyślne ustawienia zamówień dla zapasów są używane podczas tworzenia następujących obiektów:

-   Arkusze magazynowe
-   Zamówienia przeniesienia
-   Planowane zamówienia przeniesienia

Domyślne ustawienia zamówień zapasów są również stosowane podczas tworzenia następujących obiektów:

-   Zlecenia kwarantanny
-   Zlecenia kontroli jakości
-   Zlecenia produkcyjne
-   Wiersze BOM
-   Planowane zlecenia produkcyjne

## <a name="full-definition-of-a-released-product"></a>Pełna definicja zwolnionego produktu
Podczas tworzenia transakcji należy określić pełną definicję zwolnionego produktu w wierszu, aby usługa Supply Chain Management podjęła próbę identyfikacji domyślnych ustawień zamówień. Pełna definicja zwolnionego produktu oznacza, że numer towaru i wszystkie aktywne wymiary produktu, takie jak konfiguracja, rozmiar, styl i kolor, są określone w transakcji. Na przykład jeśli ręcznie tworzysz wiersz zamówienia zakupu dla zwolnionego produktu wariantu, należy określić wszystkie wymagane wymiary produktu, zanim oddział, magazyn, ilości i czas realizacji zostaną wyświetlone domyślnie w wierszu zamówienia. 

Nie wszystkie domyślne ustawienia zamówień są stosowane podczas tworzenia wierszy zamówień lub arkuszy. Ilości i czasy realizacji będą wyświetlane domyślnie tylko wtedy, gdy jest to konieczne. Na przykład podczas inwentaryzacji wiersza arkusza będą domyślnie wyświetlane tylko oddział i magazyn dla utworzonego wiersza. Podczas tworzenia wiersza lub księgowania arkusza nie są domyślnie wprowadzane ilości ani sprawdzane wielokrotności i wartości minimalne. 

System zawsze próbuje znaleźć domyślny oddział i magazyn podczas tworzenia wiersza zamówienia lub arkusza. Oddział nie zawsze jest wyświetlany domyślnie w ustawieniach zamówienia. Na przykład podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu oddział z nagłówka zamówienia jest automatycznie używany w wierszach zamówienia. Podczas tworzenia wiersza BOM jest używany oddział z nagłówka BOM. Po określeniu oddziału będzie on używany do znajdowania wszelkich ustawień zamówień specyficznych dla oddziału. Następnie ustawienia te mogą być używane jako domyślne dla magazynu. 

Domyślny typ zamówienia oraz czasy realizacji zakupu i zapasów mogą być zastąpione przez reguły zapotrzebowania na towar na stronie **Zapotrzebowanie na towary**. Domyślne ustawienia zamówień nie pozwalają na rozróżnianie między czasami realizacji produkcji i przeniesień, ale pozwalają na to reguły zapotrzebowania na towary. Jednak konfiguracja zapotrzebowania na towary będzie używana przez system MRP tylko podczas tworzenia planowanych zleceń produkcyjnych i planowanych zamówień przeniesienia, a nie będzie stosowana w przypadku ręcznego tworzenia zleceń produkcyjnych i zamówień przeniesienia. 

## <a name="default-order-settings-rules"></a>Reguły domyślnych ustawień zamówień
Można zdefiniować ogólne domyślne ustawienia zamówień oraz dowolną liczbę reguł domyślnych ustawiań zamówień, które obowiązują tylko w pewnych warunkach, takich jak konkretny oddział, określone wymiary produktu lub kombinacja wymiarów produktu. Nie można zdefiniować ustawień zamówień właściwych dla magazynu.

### <a name="rank-in-default-order-settings"></a>Ranga w domyślnych ustawieniach zamówień

Reguły domyślnych ustawień zamówień mają rangi. Im wyższa ranga, tym bardziej istotna jest reguła, czyli ma wyższy priorytet i będzie używana przed regułami o niższych rangach. Ogólne domyślne ustawienia zamówień mają ranga zero i nie można jej zmienić. Może istnieć tylko jedna reguła z rangą 0. Reguły mogą mieć tę samą rangę, pod warunkiem, że wymiary, których dotyczą, są różne. Jest to przydatne do modelowania ustawień zamówień właściwych dla oddziałów. Podczas tworzenia nowej reguły domyślnych ustawień zamówień wartości liczbowe zamówień, flaga blokady itd. są dziedziczone z reguły o randze 0, ale można je zastąpić.

### <a name="default-order-settings-for-released-products"></a>Domyślne ustawienia zamówień dla zwolnionych produktów

Dla odrębnych zwolnionych produktów można zdefiniować ogólne ustawienia zamówień lub ustawienia zamówień właściwe dla oddziału. Ogólne ustawienia zamówień zawsze mają rangę 0. Jeśli konfigurujesz równocześnie nowe ustawienia dla zamówień sprzedaży, zakupu i zapasów, zalecamy użycie opcji **Widok szczegółów** dostępnej na stronie **Ustawienia domyślne zamówień**. Aby się przełączyć do widoku szczegółów, kliknij kolejno okienko akcji **Opcje** &gt; **Opcje strony** &gt; **Zmień widok** &gt; **Widok szczegółów**.

### <a name="site-specific-order-settings"></a>Ustawienia zamówień właściwe dla oddziału

Aby utworzyć ustawienia zamówień właściwe dla oddziału, kliknij przycisk **Nowy**. W oknie **Widok szczegółów** wpisz oddział w polu **Ustawienia dotyczące** &gt; **Oddział**. W oknie **Widok siatki** wpisz oddział w kolumnie **Oddział**. Nowa reguła automatycznie otrzyma nową wartość rangi wyższą niż 0. Można utworzyć dowolną potrzebną liczbę reguł właściwych dla oddziału, a wszystkim regułom właściwym dla oddziału można przypisać taką samą rangę, wskazując w ten sposób, że są one równie ważne. 

Jeśli znajdujesz się w oknie **Widok szczegółów**, nie można uzyskać podglądu reguł utworzonych dla towaru. Aby wyświetlić informacje przeglądowe, kliknij przycisk **Pokaż/ukryj listę**. Podczas tworzenia wiersza zamówienia dowolnego typu, gdy nie jest określony oddział, usługa Supply Chain Management wyszukuje reguły bez zdefiniowanego oddziału. Może to pomóc określić domyślny oddział w wierszu zamówienia. Znaleziony oddział jest następnie używany do wyszukiwania reguły właściwej dla oddziału, w której mógł zostać ustawiony domyślny magazyn. Ten magazyn jest stosowany do wiersza zamówienia.

### <a name="specific-order-settings-for-product-dimension"></a>Ustawienia zamówień właściwe dla wymiaru produktu

Można zdefiniować reguły ustawień zamówień dla każdego aktywnego wymiaru produktu lub kombinacji aktywnych wymiarów produktu. Jeśli pole wymiaru produktu zostanie pozostawione puste, ta reguła jest stosowana do wszystkich wartości wymiaru produktu. 

Rozważmy następujący przykładowy produkt.

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Nazwa produktu**                                    | Czujnik fotoelektryczny                    |
| **Numer pozycji**                                     | XW56                                    |
| **Konfiguracja** (służy do modelowania typu światła) | C1 - widzialne światło czerwone, C2 - światło podczerwone |
| **Styl** (służy do modelowania wersji technicznej)  | R1, R2, R3                              |

W tym przykładzie załóżmy, że produkt jest nabywany, a nie produkowany. Ponadto załóżmy, że konfiguracja C1 jest używana częściej, więc ma krótsze czasy realizacji. 

W celu wymodelowania tego scenariusza utwórz następujące domyślne ustawienia zamówień.

| Stopień | Oddział | Konfiguracja | Styl | Zakup — Zastąp ustawienia domyślne | Czas realizacji zakupu | Zakup — Zablokowane | Sprzedaż — Zastąp ustawienia domyślne | Sprzedaż — Zablokowane |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Tak                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Gdy jest tworzony wiersz zamówienia zakupu lub planowane zamówienie zakupu dla towaru XW56 w konfiguracji C1, to niezależnie od tego, w której wersji lub oddziale zostanie umieszczony wiersz, system przyjmie czas realizacji 2. Załóżmy, że wszystkie wersje oprócz R3 zostały zablokowane.

Można utworzyć następujące reguły domyślnych ustawień zamówień.

| Stopień | Oddział | Konfiguracja | Styl | Zakup — Zastąp ustawienia domyślne | Czas realizacji zakupu | Zakup — Zablokowane | Sprzedaż — Zastąp ustawienia domyślne | Sprzedaż — Zablokowane |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | R2    | Tak                                  |                    | Tak                | Tak                               | Tak             |
| 20   |      |               | R1    | Tak                                  |                    | Tak                | Tak                               | Tak             |
| 10   |      | C1            |       | Tak                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Dwie reguły blokowania starych wersji mają tę samą rangę, co oznacza, że są równie ważne. Obie mają wyższą rangę niż reguła dla konfiguracji C1, co oznacza, że mają pierwszeństwo nad regułą konfiguracji C1. 

W tym przykładzie pokazano potrzebę używania rangi. Jeśli zamówienie zakupu jest tworzone dla konfiguracji C1 i wersji R2, w przypadku braku rangi dwie reguły zdefiniowane dla wersji R2 i konfiguracji C1 byłyby niejednoznaczne. Aby rozwiązać niejednoznaczność, usługa Supply Chain Management przeszuka reguły w kolejności malejącej według rangi i zastosuje pierwszą pasującą regułę. W obecnym przykładzie podczas tworzenia wiersza zamówienia zakupu dla konfiguracji C1 i wersji R2 użytkownik otrzyma komunikat ostrzegawczy, że towar jest wstrzymamy i że jest to spowodowane wartością wersji. Jeśli reguła konfiguracji miałaby rangę wyższą niż 1 dla wersji, tworzenie wiersza zamówienia zakupu dla konfiguracji C1 i wersji R2 powiodłoby się, a użytkownikowi nie byłby wyświetlany żaden komunikat „Towar wstrzymany”. 

Rozważmy następujące reguły domyślnych ustawień zamówień.

| Stopień | Oddział | Konfiguracja | Styl | Oddział domyślny | Magazyn domyślny | Zakup — Zastąp domyślne wymiary magazynowania | Magazyn zakupu |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Tak                                            | 22                 |
| 10   |      | C1            |  R2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

System analizuje zestaw reguł dwa razy w celu ustalenia oddziału i magazynu. Podczas tworzenia wiersza zamówienia zakupu dla konfiguracji C1 o stylu R2 oddział jest ustalany zgodnie z regułą o randze 10. Następnie system szuka reguły dla oddziału 2 w celu określenia magazynu. Reguła 20 została znaleziona i ponieważ ma wyższą rangę, magazyn w wierszu zamówienia zakupu będzie miał wartość 22, a nie 21. 

Jako ogólną wskazówkę należy pamiętać, że specyficzne reguły oraz reguły dotyczące wymiarów ważniejszych niż inne wymiary uzyskują wyższe rangi, podczas gdy reguły standardowe otrzymują niższe rangi. 

Reguła o randze 0 jest używana w celach bezpieczeństwa. Jeśli nie zostaną znalezione inne reguły, wtedy są używane domyślne ustawienia zamówień z reguły 0. 

Ponieważ numer rangi jest tak ważny, w okienku akcji **Ustawienia domyślne zamówień** znajdują się funkcje umożliwiające przenoszenie reguł w górę i w dół oraz zmianę numeracji, tak aby ich numery zawsze zwiększały się o 10. 

Dla jednego zwolnionego produktu można utworzyć wiele reguł. Aby się lepiej zorientować, co zastępuje każda reguła i dlaczego jest potrzebna, zaleca się używanie opcji **Widok siatki** dostępnej na stronie **Ustawienia domyślne zamówień**. Widok siatki można włączyć, klikając kolejno okienko akcji **Opcje** &gt; **Opcje strony** &gt; **Zmień widok** &gt; **Widok siatki**. Liczba kolumn wyświetlanych w siatce może być dość duża, zwłaszcza w przypadku kart sprzedaży i zapasów. Aby ograniczyć liczbę kolumn pokazywanych w siatce, grupy kolumn można ukrywać albo wyświetlać przy użyciu przycisków w menu **Ustawienia domyślne zamówień** &gt; **Wyświetl kolumnę**.

### <a name="specific-order-settings-for-released-product-variant"></a>Ustawienia zamówień właściwe dla wymiaru zwolnionego produktu

Jeśli system reguł dla domyślnych ustawień zamówień jest zbyt skomplikowany, można po prostu określić domyślne ustawienia zamówień dla każdego wariantu produktu. Poniższy przykład przedstawia, jak to będzie wyglądało dla produktu i przypadków opisanych powyżej.

| Stopień | Oddział | Konfiguracja | Styl | Zakup — Zastąp ustawienia domyślne | Czas realizacji zakupu | Zakup — Zablokowane | Sprzedaż — Zastąp ustawienia domyślne | Sprzedaż — Zablokowane |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | R3    | Tak                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | R2    | Tak                                  | 5                  | Tak                | Tak                               | Tak             |
| 10   |      | C2            | R1    | Tak                                  | 5                  | Tak                | Tak                               | Tak             |
| 10   |      | C1            | R3    | Tak                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | R2    | Tak                                  | 2                  | Tak                | Tak                               | Tak             |
| 10   |      | C1            | R1    | Tak                                  | 2                  | Tak                | Tak                               | Tak             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

W tym przypadku ranga nie ma właściwie znaczenia, więc można ją ukryć. To rozwiązanie może potencjalnie wprowadzić utrudnienia przy konserwacji. Jednak warto wziąć pod uwagę używanie tej konfiguracji, jeśli rozważasz integrację z systemami zarządzania cyklem życia produktu (PLM).



