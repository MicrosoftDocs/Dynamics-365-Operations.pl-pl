---
title: "Scalanie partii zapasów"
description: "Ten artykuł zawiera informacje o konsolidowaniu dwóch lub więcej partii zapasów w jedną partię scaloną."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventBatchJournalListPage, InventBatchJournalMerge
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 39782
ms.assetid: 07c5e98b-10fd-4f5c-b471-41d2150f47b0
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: aec97976ef6a2b4c66118289f7f76b14351456f8
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Scalanie partii zapasów
<a id="merge-inventory-batches" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o konsolidowaniu dwóch lub więcej partii zapasów w jedną partię scaloną. 

Przy scalaniu partii obliczenia mogą pomóc zoptymalizować cechy i atrybuty partii w scalonej partii. Po zaznaczeniu partii źródłowych można przejrzeć i zmodyfikować scaloną partię przed jej zaksięgowaniem. Możesz też przenieść scalenie partii do arkusza zapasów w celu zatwierdzenia. Zapasy można następnie rezerwować lub księgować bezpośrednio z tego arkusza magazynowego. Po zaksięgowaniu scalonej partii, ilość zapasów jest korygowana w celu uwzględnienia partii źródłowych i scalonej partii.

## Czy istnieją wymagania wstępne?
<a id="are-there-any-prerequisites" class="xliff"></a>
Tak, istnieją pewne elementy, które należy skonfigurować przed użyciem narzędzia scalenia partii. W poniższej tabeli opisano te wymagania wstępne.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Strona</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Nazwy arkuszy, Zapasy</td>
<td>Należy utworzyć nazwę arkusza, która będzie używana domyślnie podczas księgowania scaleń partii w arkuszach magazynowych. Opcjonalnie (zalecane): Można określić, że rezerwacje mają być dokonywane automatycznie, gdy scalenie partii jest przenoszone do arkusza magazynowego. W przeciwnym razie istnieje ryzyko, że wystąpią zmiany w dostępnych zapasach po skonfigurowaniu szczegółów scalenia partii i zaksięgowaniu w arkuszu. Aby włączyć automatyczne rezerwacje dla nazwy arkusza, w polu <strong><strong>Rezerwacja</strong> </strong>zaznacz opcję <strong>Automatycznie</strong>.</td>
</tr>
<tr class="even">
<td>Parametry modułu Zarządzanie zapasami i magazynem</td>
<td>Należy określić domyślną nazwę arkusza dla arkusza magazynowego.</td>
</tr>
<tr class="odd">
<td>Zwolnione produkty</td>
<td>Oto zalecane ustawienia towarów:
<ul>
<li>Aby automatycznie generować numery scalonych partii, należy przypisać zwolniony produkt do grupy numerów partii. Można również wprowadzić numer partii ręcznie, podczas tworzenia scalonej partii, lub wybrać istniejący numer partii. Jeśli wybierzesz istniejący numer partii, upewnij się, że wybrana partia nie została uwzględniona w żadnych transakcjach magazynowych.</li>
<li>Jeśli używasz okresów trwałości lub dat przydatności dla zwolnionego produktu, daty dla scalonej partii są obliczane na podstawie opcji wybranej w polu <strong>Obliczanie daty scalenia partii</strong>. Dostępne są następujące opcje:
<ul>
<li><strong>Najwcześniejsza</strong> — Obliczenie bazuje na najwcześniejszej dacie określonej dla partii źródłowej wybranej dla operacji scalania partii.</li>
<li><strong>Najpóźniejsza</strong> — Obliczenie bazuje na najpóźniejszej dacie określonej dla partii źródłowej wybranej dla operacji scalania partii.</li>
<li><strong>Ręczna</strong> — Nie są wykonywane żadne obliczenia. Jeśli data jest taka sama we wszystkich partiach źródłowych, zostanie ona zasugerowana. Można ją zmienić. Jeśli data nie jest taka sama we wszystkich partiach źródłowych, można ją wpisać ręcznie.</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td>Grupa numerów partii</td>
<td>Opcjonalnie: Aby wygenerować numer partii podczas scalenia partii, należy przypisać grupę numerów partii do zwolnionego produktu. W przeciwnym razie numer partii można wprowadzić ręcznie.</td>
</tr>
</tbody>
</table>

## Kiedy warto scalać partie zapasów?
<a id="when-might-i-want-to-merge-batches-of-inventory" class="xliff"></a>
Oto kilka przykładów scenariuszy, kiedy może być przydatne scalenie partii:

-   Podczas spaceru po magazynie Sammy zauważył, że istnieje kilka niewielkich partii tego samego towaru. Oczekuje otrzymania kilku nowych wysyłek i zdaje sobie sprawę, że poprzez scalenie małych ilości w jedną partię może zwolnić miejsce w magazynie.
-   Sammy przyjmuje zapasy i chce połączyć nową partię z już przyjętą partią, aby zoptymalizować wartość atrybutu istniejącej partii.

## Czy mogę scalać partię dla różnych oddziałów i firm?
<a id="can-i-merge-batches-across-sites-and-legal-entities" class="xliff"></a>
Nie, można scalić tylko partie w tym samym oddziale i o tych samych wymiarach magazynowania w granicach jednej firmy. Można jednak określić inną lokalizację i identyfikator palety dla scalonej partii.

## Czy można scalać częściowe ilości?
<a id="can-i-merge-partial-quantities" class="xliff"></a>
Nie, można scalić tylko pełne ilości partii. Funkcja scalania partii jest przewidziana jako funkcja zapasów, a nie funkcja produkcji.

## Co zrobić, jeśli partie mają różne wartości atrybutów partii?
<a id="what-if-the-batches-have-different-batch-attribute-values" class="xliff"></a>
Po wybraniu partii źródłowych do połączenia w partię scaloną program Finance and Operations sprawdza, czy wszystkie partie mają określone cechy lub wartości atrybutów. Gdy wartości danego atrybutu są takie same, system sugeruje wartość dla scalonej partii. Tę wartość można zmienić. Wartości atrybutów, które nie są takie same, są pozostawiane puste w scalonej partii i można je wprowadzić ręcznie. Jeśli typem atrybutu partii dla wartości atrybutu jest liczba całkowita lub ułamek, a wartości nie są takie same dla wszystkich partii źródłowych, taka wartość zostanie obliczona przy użyciu średniej ważonej. Obliczona wartość jest zaokrąglana w górę lub w dół, do najbliższej wartości przyrostu. Jeśli wartość jest pusta w partii źródłowej, wtedy partia i jej ilość nie są uwzględniane w obliczeniach. **Przykład** Poniższy przykład pokazuje sposób obliczania średniej ważonej dla scalonej partii. Dwie partie źródłowe mają wartość pustą dla typu atrybutu partii, która jest liczbą całkowitą. Następujący atrybut jest przypisany do partii źródłowych.

| Atrybut | Minimum | Przyrost | Maksimum |
|-----------|---------|-----------|---------|
| Kategoria     | 3       | 3         | 30      |

Partie źródłowe przyjmują następujące wartości atrybutu **Kategoria partii**.

| Zadanie wsadowe | Ilość | Atrybut | Wartość atrybutu |
|-------|----------|-----------|-----------------|
| B1    | 10       | Kategoria     | Puste           |
| B2    | 15       | Kategoria     | 15              |
| B3    | 20       | Kategoria     | 20              |
| B4    | 25       | Kategoria     | Puste           |
| B5    | 30       | Kategoria     | 25              |

W przypadku dodania tych partii jako partii źródłowych scalona partia otrzyma następujące wartości.

| Zadanie wsadowe | Ilość | Atrybut | Wartość atrybutu |
|-------|----------|-----------|-----------------|
| B6    | 100      | Kategoria     | 21              |

Wartości i ilości dla partii B1 i B4 nie są uwzględniane w obliczaniu średniej ważonej. Z tego względu wartość scalonej partii jest obliczana w następujący sposób.

| Wartość | Ilość (waga)                              | Względna waga | Względna waga × Wartość                                               |
|-------|------------------------------------------------|-----------------|-----------------------------------------------------------------------|
| 15    | 15                                             | 0.230769231     | 3.461538462                                                           |
| 20    | 20                                             | 0.307692308     | 6.153846154                                                           |
| 25    | 30                                             | 0.461538462     | 11.53846154                                                           |
|       | **Suma:** 65, czyli suma wag |                 | **Suma:** 21.5384615, zaokrąglona do 21 (najbliższej wartości przyrostu) |

## Co zrobić, jeśli partie mają różne daty atrybutów partii?
<a id="what-if-the-batches-have-different-batch-dates" class="xliff"></a>
Jeśli partie mają różne daty partii, niektóre daty są obliczane na podstawie wartości w grupie **Daty partii** na skróconej karcie **Scalona partia** na stronie **Scalanie partii**. System oblicza wartość pól w grupie **Daty partii**. Wartości te obejmują daty produkcji, ważności, zalecanego ponownego przetestowania i przydatności. Daty są obliczane na podstawie ustawień towaru w grupie pól **Dane pozycji** na stronie **Szczegóły zwolnionego produktu**. Wartości można zmienić lub wprowadzić ręcznie. Dla żadnych pozostałych dat obliczenia nie są wykonywane. Ta sama zasada jest używana dla wartości atrybutów partii. Jeśli data jest taka sama dla wszystkich partii źródłowych, będzie ona sugerowana dla scalonej partii. Jeśli data nie jest taka sama we wszystkich partiach źródłowych, pole daty zostanie puste w scalonej partii i można wypełnić je ręcznie.

## Co zrobić, jeśli wymiary różnią się w partiach, które chcę scalić?
<a id="what-if-the-dimensions-are-different-on-the-batches-that-i-want-to-merge" class="xliff"></a>
Wymiary produktu, śledzenia i magazynowania są obsługiwane w następujący sposób:

-   **Wymiary produktów** — Wszystkie wymiary produktu dla wybranego towaru muszą być takie same. Nie można scalić partii o różnych wymiarach produktów.
-   **Wymiary śledzenia** — Jeśli określono grupę numerów partii dla towaru, nowy numer partii jest generowany automatycznie. Jeśli grupa numerów partii nie jest przypisana do towaru, można wybrać istniejącą partię lub wprowadzić numer ręcznie. Numery seryjne są przenoszone z partii źródłowej do wierszy arkusza magazynowego dla scalonej partii.
-   **Wymiary magazynowania** — Wymiary magazynowania dla oddziału i magazynu muszą być takie same we wszystkich partiach źródłowych i scalonej partii. Można jednak określić nową lokalizację i identyfikator palety dla scalonej partii.

## Jak działa księgowanie?
<a id="how-does-posting-work" class="xliff"></a>
Księgowanie działa na dwa sposoby, w zależności od tego, czy jest używany proces zatwierdzania arkuszy. Można użyć akcji **Przenieś do arkusza** i **Księgowanie scalenia partii** w celu przeniesienia scalenia partii do arkusza, w którym scalenie zostanie zweryfikowane i zaksięgowane, lub też można bezpośrednio zaksięgować scalenie partii. Najważniejsza różnica między tymi dwoma operacjami polega na tym, że przeniesienie do arkusza nie powoduje zaksięgowania scalenia partii. Obie akcje tworzą nową partię (jeżeli nie zaznaczono istniejącej partii), aktualizują wszystkie szczegóły partii i wartości atrybutów oraz tworzą arkusz magazynowy.

-   **Przenieś do arkusza** — Przeniesienie szczegółów scalenia partii do nowego arkusza magazynowego. Jeśli skonfigurowano rezerwacje automatyczne, ilości w partiach źródłowych są rezerwowane. Nie można zmienić szczegółów scalenia partii. W celu zmodyfikowania scalenia partii należy usunąć arkusz. Arkusz może służyć jako zadanie do późniejszego wykonania przez innego pracownika. Rezerwacja ilości partii do wiersza arkusza jest zabezpieczona. Ta alokacja pozwala planiście jakości lub kierownikowi magazynu tworzyć zadania dla swoich pracowników.
-   **Księgowanie scalenia partii** — Księgowanie scalenia partii bezpośrednio. Tę czynność można wykonać po zakończeniu fizycznego scalenia.

Arkusz magazynowy scalenia partii można zatwierdzić ze strony listy **Wszystkie scalenia partii**. Kliknij kolejno opcje **Arkusz** &gt; **Księguj**. Po zaksięgowaniu arkusza nie można zmienić szczegółów w scalonej partii. Po przeniesieniu scalenia partii do arkusza magazynowego, szczegóły można zmienić tylko wtedy, jeśli arkusz zostanie usunięty.

## Dlaczego po scaleniu towaru w ilości efektywnej nie widać w arkuszu magazynowym informacji dotyczących ilości efektywnej?
<a id="after-i-merged-a-catchweight-item-why-cant-i-see-the-catchweight-information-in-the-inventory-journal" class="xliff"></a>
Można scalać partie towarów w ilości efektywnej tak samo, jak inne towary. Jednakże informacje o ilości efektywnej nie są wyświetlane w arkuszu magazynowym. Zaleca się sprawdzenie informacji o ilości efektywnej przed przeniesieniem scalenia partii do arkusza magazynowego.




