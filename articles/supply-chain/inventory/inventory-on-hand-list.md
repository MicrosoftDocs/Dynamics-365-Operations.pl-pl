---
title: Listy dostępnych zapasów
description: W tym temacie opisano, jak używać strony Lista dostępnych do sprawdzenia szczegółów dostępnych zapasów. Pokazuje kilka sposobów, w jakie różne opcje filtrowania i sortowania współpracują ze sobą, oraz jak te opcje mogą czasami dawać nieoczekiwane rezultaty po ich połączeniu.
author: yufeihuang
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 9464240123ec2248e1b66f32dd3c9a2f974512b6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573928"
---
# <a name="inventory-on-hand-list"></a>Listy dostępnych zapasów

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak używać strony **Lista dostępnych** do sprawdzenia szczegółów dostępnych zapasów. Pokazuje kilka sposobów, w jakie różne opcje filtrowania i sortowania współpracują ze sobą, oraz jak te opcje mogą czasami dawać nieoczekiwane rezultaty po ich połączeniu.

## <a name="query-your-on-hand-inventory"></a>Przeszukaj swoje dostępne zapasy

Aby sprawdzić dostępność zapasów, przejdź do **Zarządzanie zapasami \> Zapytania i raporty \> Lista dostępnych**.

Strona **Lista dostępnych** jest aktualizowana automatycznie, gdy transakcje są dokonywane w magazynie. Transakcje te mogą być prognozami, transakcjami fizycznymi lub finansowymi.

Skorzystaj z poniższych narzędzi, aby znaleźć zbiór produktów, których szukasz:

- W okienku akcji wybierz opcję [**Wymiary**](#dimensions), aby otworzyć okno dialogowe, w którym można dodawać lub usuwać kolumny wyświetlane w siatce **Dostępnych**.
- W [okienku **Filtruj**](#filters-pane) wprowadź wartości dla określonych pól, aby wyświetlić tylko rekordy pasujące do tych wartości. Należy zauważyć, że filtry zdefiniowane w tym miejscu są stosowane do tabel źródłowych, które mogą być później agregowane, zgodnie z wymiarami wybranymi do pokazania. Aby uzyskać informacje o tym, jak to zachowanie może mieć wpływ na wyniki, należy zapoznać się z [przykładami](#examples) przedstawionymi dalej w tym temacie.
- W okienku **Filtruj** wybierz opcję **Zastosuj**, aby wygenerować listę dopasowanych dostępnych zapasów w siatce **Dostępne**.
- W siatce **Dostępne** wybierz dowolny nagłówek kolumny, który ma być sortowany lub przefiltrowany według wartości w tej kolumnie. Dodatkowe opcje filtrowania znajdują się w QuickFilter u góry siatki. Te filtry są stosowane do wyników, a nie do tabel źródłowych. Aby uzyskać informacje o tym, jak to zachowanie może mieć wpływ na wyniki, należy zapoznać się z [przykładami](#examples) przedstawionymi dalej w tym temacie.

Dla każdego dopasowanego towaru siatka **Dostępne** zawiera następujące kolumny informacji o zapasach.

| Kolumnowy | opis |
|---|---|
| Magazyn | Fizyczna ilość, która jest dostępna w zapasach. |
| Rezerwacja fizyczna | Całkowita ilość, która została fizycznie zarezerwowana. |
| Fizycznie dostępne | Dostępna (niezarezerwowana) ilość, która jest dostępna w spisie fizycznym.<p>**Dostępna fizyczna** jest polem obliczeniowym. Wartość jest równa wartości **Magazyn fizyczny** pomniejszonej o wartość **Fizyczną zarezerwowaną**.</p> |
| Fizyczna dostępna dla dodatkowych wymiarów | Dostępna ilość fizyczna dla wszystkich wymiarów pokazywanych w siatce. |
| Zamówione w sumie | Ilość całkowita uwzględniona w zamówieniach przychodzących lub mająca dodatnią ilość w różnych arkuszach magazynowych. |
| Zamówione | Ilość całkowita uwzględniona w zamówieniach wychodzących lub mająca ujemną ilość w różnych arkuszach magazynowych. |
| Zamówione i zarezerwowane | Całkowita ilość zarezerwowana na zamówionych paragonach. Wartość w tym polu reprezentuje łączną ilość towarów w transakcjach wychodzących, które mają stan _Zamówione zarezerwowane_. Towary zarezerwowane jako zamówione nie są fizycznie dostępne w magazynie. Dlatego nie można ich bezpośrednio pobrać i dostarczyć. |
| Dostępne do rezerwacji | Całkowita ilość dostępnych zapasów, jaka może zostać zarezerwowana.<p>**Uwaga:** Jeśli zaznaczono pole wyboru **Rezerwacja zamówionych pozycji** na stronie **Parametry modułu Zarządzanie zapasami i magazynem**, wartość w tym polu będzie zawierać oczekiwane przychody. Jeśli to pole wyboru jest wyczyszczone, wartość wyklucza oczekiwane przychody.</p> |
| Wszystkie dostępne | Łączna dostępna ilość.<p>**W sumie dostępne** jest polem obliczeniowym. Wartość jest równa **Dostępna fizyczna** powiększonej o wartość **Zamówione w sumie** pomniejszoną o wartość **W zamówieniu**.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>Stosowanie filtrów w celu znalezienia szukanych rekordów

Korzystając z okienka **Filtry**, można filtrować listę dostępnych zapasów, tak aby zawierała tylko rekordy, w których wartości pól odpowiadają kryteriom filtrowania. Aby zdefiniować filtr, należy wykonać następujące czynności.

1. W okienku **Filtry** znajdź pole, według którego chcesz filtrować.
2. W polu pod nazwą pola docelowego wybierz operator logiczny (na przykład, *zaczyna się od* , *jest równe* lub *większe niż*).
3. Wprowadź lub wybierz wartość do wyszukania.

> [!IMPORTANT]
> Strona **Lista dostępnych zapasów** jest składana z tabeli szczegółowych dostępnych zapasów, która zawiera wszystkie dostępne wymiary. Jednak lista na tej stronie jest podsumowaniem. Dlatego można łączyć wiersze z tabeli źródłowej, sumując wartości zgodnie z podanymi wymiarami.
>
> Filtry zdefiniowane w okienku **Filtrów** mają zastosowanie do tabeli źródłowej, a nie do listy agregowanej. Takie zachowanie może czasami dawać nieoczekiwane wyniki. Aby uzyskać informacje o tym, jak to zachowanie może mieć wpływ na wyniki, należy zapoznać się z [przykładami](#examples) przedstawionymi dalej w tym temacie.
> 
> Jednak [filtry dostarczone w siatce](#grid-filters) *są* stosowane do zagregowanej listy. Filtry te obejmują zarówno QuickFilter na górze siatki, jak i filtr dla każdego nagłówka kolumny.

Aby zmodyfikować zbiór filtrów dostępnych w okienku **Filtrów**, należy wykonać następujące kroki:

- Aby usunąć filtr z okienka, należy wybrać przycisk **Zamknij** (**X**).
- Aby dodać filtr, wybierz opcję **Dodaj** u góry okienka **Filtrów**. Wyświetlone zostanie okno dialogowe **Dodawania pól filtru**, w którym jest wyświetlana lista dostępnych pól. Pokazuje także informacje o typie danych i tabeli dla każdego pola. Nagłówki kolumn służą do filtrowania i sortowania listy zgodnie z potrzebami, a następnie zaznacz pole wyboru dla każdego pola, które chcesz dodać do okienka **Filtru**. Po zakończeniu wybierz opcję **Wstaw**, aby zastosować zmiany.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>Służy do wybierania wymiarów, które mają być pokazywane

Wymiary informują więcej o każdym towarze z listy dostępne zapasy i zapewniają więcej sposobów sortowania i filtrowania listy. Wymiary wybrane do pokazania wpływają również na sposób agregowania wierszy na stronie **Listy dostępnych**. Z kolei ta agregacja może mieć wpływ na sposób łączenia wierszy z tabel źródłowych w wynikach. Aby uzyskać informacje o tym, jak to zachowanie może mieć wpływ na wyniki, należy zapoznać się z [przykładami](#examples) przedstawionymi dalej w tym temacie.

Aby dostosować wybór widocznych wymiarów magazynowych, należy wykonać następujące kroki.

1. W Okienku akcji kliknij pozycję **Wymiary**.

    Wyświetlone zostanie okno dialogowe **Wyświetlanie wymiarów**, które pokazuje każdy wymiar.

2. Zaznacz pole wyboru przy każdym wymiarze, który chcesz dołączyć w siatce.
3. Jeśli wybór ma być używany domyślnie po kolejnym otwarciu strony **Lista dostępnych**, należy skonfigurować opcję **Zapisz ustawienia** na **Tak**. Jeśli zostanie wybrana opcja **Nie**, wybór będzie używany tylko podczas bieżącej sesji. Dlatego przy następnym otwarciu strony zostanie użyta bieżąca opcja domyślna.
4. Wybierz przycisk **OK**, aby zamknąć okienko dialogowe i zastosować zmiany.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>Filtr dla danych wyjściowych na liście dostępnych zapasów

Możesz wybrać dowolny nagłówek kolumny w siatce **Dostępne**, aby sortować lub filtrować według wartości w tej kolumnie. Dodatkowe opcje filtrowania znajdują się w QuickFilter u góry siatki. Te filtry są stosowane do wyników, a nie do tabel źródłowych. Aby uzyskać informacje o tym, jak to zachowanie może mieć wpływ na wyniki, należy zapoznać się z [przykładami](#examples) przedstawionymi dalej w tym temacie.

> [!NOTE]
> Nie można filtrować i sortować według wszystkich kolumn. Większość kolumn ilości nie zawiera formantów sortowania i filtrowania, ponieważ są to pola obliczeniowe. Kolumna **W zamówieniu** jest wyjątkiem.

## <a name="examples"></a><a name="examples"></a>Przykłady

System zawiera szczegółową (nie zagregowaną) tabelę zapasów, która zawiera następujące dostępne zapasy:

| Identyfikator pozycji | Oddział | Magazyn | Magazyn fizyczny | Fizycznie dostępne |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>Scenariusz 1

Na stronie **Lista dostępnych** skonfigurowano wyświetlanie następujących ostatecznych wymiarów:

- Identyfikator pozycji
- Oddział
- Magazyn

W okienku **Filtry** są ustawiane następujące kryteria filtrowania:

- **Kod pozycji** \| **jest dokładnie** \| _IA0001_
- **Dostępna wartość fizyczna** \| **mniejsza lub równa** \| _1_

W tym przypadku powstaje wynik.

| Identyfikator pozycji | Oddział | Magazyn | Magazyn fizyczny | Fizycznie dostępne |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>Scenariusz 2

Na stronie **Lista dostępnych** skonfigurowano wyświetlanie następujących ostatecznych wymiarów:

- Identyfikator pozycji
- Oddział

W okienku **Filtry** są ustawiane następujące kryteria filtrowania:

- **Kod pozycji** \| **jest dokładnie** \| _IA0001_
- **Dostępna wartość fizyczna** \| **mniejsza lub równa** \| _1_

W tym przypadku powstaje wynik.

| Identyfikator pozycji | Oddział | Magazyn fizyczny | Fizycznie dostępne |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

Należy zauważyć, że ustawienia w okienku **Filtry** dotyczą szczegółowej (nie zagregowanej) tabeli zapasów pokazanej na początku tej sekcji. Dlatego kryterium **Fizycznie dostępne** \| **mniejsze niż lub równe** \| _1_ powoduje wyszukanie dwóch wierszy z tabeli (pierwszy i trzeci wiersz, z których każdy pokazuje **Fizycznie dostępne** równą  _1_). Jednak w tym scenariuszu strona **Lista dostępnych** nie jest skonfigurowana do wyświetlania wymiaru **Magazynowego**. Z tego względu dwa oryginalne wiersze są agregowane w jeden wynikowy wiersz, ponieważ oba wiersze mają identyczne wartości we wszystkich widocznych wymiarach. Ten wiersz wydaje się naruszać kryterium filtrowania, ponieważ **Fizycznie dostępne** jest wyświetlana jako _2_. Jednak wynik jest poprawny, ponieważ ustawienia w okienku **Filtry** mają zastosowanie do tabeli źródłowej, a nie do zagregowanej tabeli wyświetlanej na stronie **Lista dostępnych**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]