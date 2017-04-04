---
title: "Ustawienia domyślne zamówień dla wymiarów i wariantów produktu"
description: "Domyślne ustawienia zamówień definiują: oddział i magazyn, skąd towary będą pobierane lub gdzie będą przechowywane; ilości minimalne, maksymalne, wielokrotne i standardowe, które będą używane do handlu lub zarządzania zapasami; czasy realizacji; flagę blokady; metodę tworzenia zobowiązań zamówień. Domyślne ustawienia zamówień są stosowane przy tworzeniu zamówień zakupu, zamówień sprzedaży, zamówień przeniesienia i arkuszy magazynowych oraz w planowaniu głównym do generowania zamówień planowanych. Domyślne ustawienia zamówień mogą być specyficzne dla towaru, oddziału, wariantu produktu lub wymiaru produktu."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventItemOrderSetup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 60abaa69debd891b2fe2dd98184c0dab50b0bf9f
ms.lasthandoff: 03/29/2017


---

# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Ustawienia domyślne zamówień dla wymiarów i wariantów produktu

Domyślne ustawienia zamówień definiują: oddział i magazyn, skąd towary będą pobierane lub gdzie będą przechowywane; ilości minimalne, maksymalne, wielokrotne i standardowe, które będą używane do handlu lub zarządzania zapasami; czasy realizacji; flagę blokady; metodę tworzenia zobowiązań zamówień. Domyślne ustawienia zamówień są stosowane przy tworzeniu zamówień zakupu, zamówień sprzedaży, zamówień przeniesienia i arkuszy magazynowych oraz w planowaniu głównym do generowania zamówień planowanych. Domyślne ustawienia zamówień mogą być specyficzne dla towaru, oddziału, wariantu produktu lub wymiaru produktu.

Na stronie **Ustawienia domyślne zamówień** można wprowadzić domyślne parametry zamówień. Aby otworzyć tę stronę, przejdź do **zarządzanie informacjami o produktach**&gt;**produkty**&gt;**zwolnionych produktów**&gt; wybierz zwolnionego produktu &gt;na **Plan** lub *** zarządzanie zapasów *** w okienku akcji &gt;**zamówienia ustawienia**&gt;**ustawienia domyślne zamówień**.

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
Podczas tworzenia transakcji, należy określić pełną definicję zwolnionego produktu w wierszu, zanim spróbuje zidentyfikować ustawień domyślnych zamówienia 365 Dynamics dla operacji. Pełną definicję zwolnionego produktu oznacza, że kod towaru i wszystkie wymiary aktywnego produktu, takie jak konfiguracja, rozmiar, styl i kolor, są określone w odniesieniu do transakcji. Na przykład jeśli ręcznie tworzysz wiersz zamówienia zakupu dla zwolnionego produktu wariantu, należy określić wszystkie wymagane wymiary produktu, zanim oddział, magazyn, ilości i czas realizacji zostaną wyświetlone domyślnie w wierszu zamówienia. 

Nie wszystkie domyślne ustawienia zamówień są stosowane podczas tworzenia wierszy zamówień lub arkuszy. Ilości i czasy realizacji będą wyświetlane tylko domyślnie, gdy jest to właściwe. Na przykład gdy wiersz arkusza obliczania, tylko oddział i Magazyn wyświetli domyślnie podczas tworzenia wiersza. Oczywiście nie zalegających ilość lub kontroli na wielu i minimalne są wykonywane podczas tworzenia wiersza lub księgowania arkusza. 

System zawsze próbuje znaleźć domyślny oddział i magazyn podczas tworzenia wiersza zamówienia lub arkusza. Oddział nie zawsze jest wyświetlany domyślnie w ustawieniach zamówienia. Na przykład podczas tworzenia zamówienia sprzedaży lub zamówienia zakupu oddział z nagłówka zamówienia jest automatycznie używany w wierszach zamówienia. Podczas tworzenia wiersza BOM, używana jest witryna z nagłówka BOM-u. Po określeniu jest witryny, to będzie umożliwia znalezienie dowolnej witryny ustawienia określonego zamówienia, które może następnie służyć jako domyślny dla magazynu. 

Domyślny typ zamówienia zakupu i czasy realizacji zapasów mogą być zastąpione przez reguły zapotrzebowania na towar na **zapotrzebowanie na towar** strony. Chociaż domyślne ustawienia kolejności nie pozwalają na rozróżnienie między produkcją a czas realizacji transferu, umożliwić mu reguły zapotrzebowania na towar. Jednak konfiguracja zapotrzebowania na towary będzie używana przez system MRP tylko podczas tworzenia planowanych zleceń produkcyjnych i planowanych zamówień przeniesienia, a nie będzie stosowana w przypadku ręcznego tworzenia zleceń produkcyjnych i zamówień przeniesienia. 

## <a name="default-order-settings-rules"></a>Reguły domyślnych ustawień zamówień
Można zdefiniować ogólne domyślne ustawienia zamówień oraz dowolną liczbę reguł domyślnych ustawiań zamówień, które obowiązują tylko w pewnych warunkach, takich jak konkretny oddział, określone wymiary produktu lub kombinacja wymiarów produktu. Nie można zdefiniować ustawień zamówień właściwych dla magazynu.

### <a name="rank-in-default-order-settings"></a>Ranga w domyślnych ustawieniach zamówień

Reguły domyślnych ustawień zamówień mają rangi. Im wyższa ranga, tym bardziej istotna jest reguła, czyli ma wyższy priorytet i będzie używana przed regułami o niższych rangach. Ogólne domyślne ustawienia zamówień mają ranga zero i nie można jej zmienić. Może istnieć tylko jedna reguła z rangą 0. Reguły mogą mieć tę samą rangę, pod warunkiem, że wymiary, których dotyczą, są różne. Jest to przydatne do modelowania ustawień zamówień właściwych dla oddziałów. Podczas tworzenia nowej reguły domyślnych ustawień zamówień wartości liczbowe zamówień, flaga blokady itd. są dziedziczone z reguły o randze 0, ale można je zastąpić.

### <a name="default-order-settings-for-released-products"></a>Domyślne ustawienia zamówień dla zwolnionych produktów

Dla odrębnych zwolnionych produktów można zdefiniować ogólne ustawienia zamówień lub ustawienia zamówień właściwe dla oddziału. Ogólne ustawienia zamówień zawsze mają rangę 0. Jeśli konfigurujesz równocześnie nowe ustawienia dla zamówień sprzedaży, zakupu i zapasów, zalecamy użycie opcji **Widok szczegółów** dostępnej na stronie **Ustawienia domyślne zamówień**. Aby przełączyć się do widoku Szczegóły, przejdź do **opcje** w okienku akcji &gt;**Opcje strony**&gt;**zmienić widok**&gt;**widok szczegółów**.

### <a name="site-specific-order-settings"></a>Ustawienia zamówień właściwe dla oddziału

Aby utworzyć ustawienia zamówień właściwe dla oddziału, kliknij przycisk **Nowy**. W **widok szczegółów**, wypełnij witryny w **ustawienia właściwe dla**&gt;**witryny** pole. W oknie **Widok siatki** wpisz oddział w kolumnie **Oddział**. Nowa reguła automatycznie otrzyma nową wartość rangi wyższą niż 0. Można utworzyć dowolną potrzebną liczbę reguł właściwych dla oddziału, a wszystkim regułom właściwym dla oddziału można przypisać taką samą rangę, wskazując w ten sposób, że są one równie ważne. 

Jeśli znajdujesz się w oknie **Widok szczegółów**, nie można uzyskać podglądu reguł utworzonych dla towaru. Aby wyświetlić informacje przeglądowe, kliknij przycisk **Pokaż/ukryj listę**. Po utworzeniu wiersza zamówienia dowolnego typu i ma on nie witryna sieci Web, 365 Dynamics dla operacji wyszukiwania dla reguły z żadna z witryn podanych. Może to pomóc w określeniu domyślną witrynę w wierszu zamówienia. Znaleziony oddział jest następnie używany do wyszukiwania reguły właściwej dla oddziału, w której mógł zostać ustawiony domyślny magazyn. Ten magazyn jest stosowany do wiersza zamówienia.

### <a name="specific-order-settings-for-product-dimension"></a>Ustawienia zamówień właściwe dla wymiaru produktu

Można zdefiniować reguły ustawień zamówień dla każdego aktywnego wymiaru produktu lub kombinacji aktywnych wymiarów produktu. Jeśli pole wymiaru produktu zostanie pozostawione puste, ta reguła jest stosowana do wszystkich wartości wymiaru produktu. 

Rozważmy następujący przykładowy produkt.

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Product name**                                    | Czujnik fotoelektryczny                    |
| **Item number**                                     | XW56                                    |
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

W tym przykładzie pokazano potrzebę używania rangi. Jeśli zamówienie zakupu jest tworzone dla konfiguracji C1 i wersji R2, w przypadku braku rangi dwie reguły zdefiniowane dla wersji R2 i konfiguracji C1 byłyby niejednoznaczne. Aby rozwiązać niejednoznaczność, program Dynamics 365 for Operations przeszuka reguły w kolejności malejącej według rangi i zastosuje pierwszą pasującą regułę. W obecnym przykładzie podczas tworzenia wiersza zamówienia zakupu dla konfiguracji C1 i wersji R2 użytkownik otrzyma komunikat ostrzegawczy, że towar jest wstrzymamy i że jest to spowodowane wartością wersji. Jeśli reguła konfiguracji miałaby rangę wyższą niż 1 dla wersji, tworzenie wiersza zamówienia zakupu dla konfiguracji C1 i wersji R2 powiodłoby się, a użytkownikowi nie byłby wyświetlany żaden komunikat „Towar wstrzymany”. 

Rozważmy następujące reguły domyślnych ustawień zamówień.

| Stopień | Oddział | Konfiguracja | Styl | Oddział domyślny | Magazyn domyślny | Zakup — Zastąp domyślne wymiary magazynowania | Magazyn zakupu |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Tak                                            | 22                 |
| 10   |      | C1            |  R2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

System analizuje zestaw reguł dwa razy w celu ustalenia oddziału i magazynu. Podczas tworzenia wiersza zamówienia zakupu dla konfiguracji C1, styl R2, lokacja jest określana na podstawie reguły o randze 10. Następnie system wyszukuje dla reguły witryny 2 w celu ustalenia składu. Reguła 20 została znaleziona i ponieważ ma wyższą rangę, magazyn w wierszu zamówienia zakupu będzie miał wartość 22, a nie 21. 

Jako ogólną wskazówkę należy pamiętać, że specyficzne reguły oraz reguły dotyczące wymiarów ważniejszych niż inne wymiary uzyskują wyższe rangi, podczas gdy reguły standardowe otrzymują niższe rangi. 

Reguła o randze 0 jest używana w celach bezpieczeństwa. Jeśli nie zostaną znalezione inne reguły, wtedy są używane domyślne ustawienia zamówień z reguły 0. 

Ponieważ numer rangi jest tak ważny, w okienku akcji **Ustawienia domyślne zamówień** znajdują się funkcje umożliwiające przenoszenie reguł w górę i w dół oraz zmianę numeracji, tak aby ich numery zawsze zwiększały się o 10. 

Dla jednego zwolnionego produktu można utworzyć wiele reguł. Aby się lepiej zorientować, co zastępuje każda reguła i dlaczego jest potrzebna, zaleca się używanie opcji **Widok siatki** dostępnej na stronie **Ustawienia domyślne zamówień**. Można włączyć widok siatki, przechodząc do **opcje** w okienku akcji &gt;**Opcje strony**&gt;**zmienić widok**&gt;**widoku siatki**. Liczba kolumn wyświetlanych w siatce może być dość duża, zwłaszcza w przypadku kart sprzedaży i zapasów. Aby ograniczyć liczbę wyświetlanych kolumn w siatce, grupy kolumn mogą być ukryte lub wyświetlane za pomocą przycisków na **ustawienia domyślne zamówień**&gt;**wyświetlane kolumny** menu.

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


