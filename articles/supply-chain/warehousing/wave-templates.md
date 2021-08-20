---
title: Szablony grupy czynności
description: W tym temacie opisano sposób konfigurowania kryteriów, które określają, czy grupy czynności są przetwarzane ręcznie czy automatycznie, a pracę, która jest generowana dla magazynu podczas przetwarzania grupy czynności.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: aca03e3fda4405fa6fe2b427a47066af5bb95b644b7f5b47d22736347208a8bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751632"
---
# <a name="wave-templates"></a>Szablony grupy czynności

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania kryteriów, które określają, czy grupy czynności są przetwarzane ręcznie czy automatycznie, a pracę, która jest generowana dla magazynu podczas przetwarzania grupy czynności. Kryteria można określić, definiując szablony grupy czynności i kwerendy, które dopasowują grupy czynności do zwolnionych wierszy w zamówieniach sprzedaży, zleceniach produkcyjnych i kartach Kanban.

## <a name="settings-for-wave-templates"></a>Ustawienia szablonów grupy czynności

Podczas konfigurowania szablonu grupy czynności, można określić następujące ustawienia:

- **Oddział** i **magazyn**, dla których szablon utworzy pracę.
- Kolejność, w jakiej szablony będą oceniane. Kolejność, w jakiej szablony są zestawiane ze zwolnionymi wierszami w zamówieniach sprzedaży, zleceniach produkcyjnych i kartach Kanban. Po zwolnieniu wiersza system stosuje pierwszy szablon grupy czynności, dla których wiersz spełnia kryteria. Im większe jest prawdopodobieństwo spełnienia kryteriów, tym większy prawdopodobieństwo ma wiersz, więc na początku listy należy umieścić szablony z najbardziej określonymi kryteriami. Przyciski **Przenieś w górę** i **Przenieś w dół** w okienku akcji służą do rozmieszczania szablonów na liście.
- Akcje podejmowane przez każdy szablon. **Metody** grupy czynności, które wykonują akcje tworzone przez szablon, tworzą lub dystrybuują pracę dla każdego typu szablonu grup czynności.
- Atrybuty (filtry) grupy czynności, które muszą być stosowane w szablonie grupy czynności.

> [!NOTE]
> W razie potrzeby deweloper może utworzyć dodatkowe metody. Możesz przejrzeć pełną listę metod na stronie **Metody przetwarzania grupy czynności**.

Niektóre ustawienia reprezentują strategiczne decyzje dla przetwarzania grupy czynności w następujący sposób:

- Jeśli szablon jest używany do wysłania towarów dla zamówień sprzedaży i zamówień przeniesienia lub do przenoszenia towarów do produkcji dla zleceń produkcyjnych lub zadań Kanban.
- Jeśli przetwarzanie grupy czynności następuje ręcznie lub automatycznie, ma miejsce, co następuje:

  - **Ręczne przetwarzanie** — wiersz zostanie dodany do grupy czynności i zarezerwowane zostają zapasy, jednak należy kliknąć opcję **przetwórz** na stronie listy **Wszystkie grupy czynności**, aby utworzyć pracę pobrania dla zamówienia.
  - **Automatyczne przetwarzanie** — można całkowicie lub częściowo zautomatyzować przetwarzania grupy czynności. Jeśli w pełni zautomatyzuje się proces przetwarzania grupy czynności, tworzona grupa czynności zawiera wiersz z zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban podczas tworzenia zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban. Towary są odejmowane od dostępnych zapasów i tworzona jest praca pobierania. Jeśli częściowo zautomatyzuje się proces przetwarzania grupy czynności, można określić wartości, które będą powodowały przetwarzanie grupy czynności. Na przykład można określić maksymalną wagę dla dostaw, która będzie powodowała przetwarzanie grupy czynności, gdy łączna waga wierszy w grupie czynności osiągnie daną wartość.

- Po przypisaniu wysyłek do otwartych grup czynności. Na przykład jeśli użytkownik zobowiązuje się wobec odbiorców do dostarczana zamówień złożonych do 12:00w ciągu 24 godzin, można ustawić szablon grupy czynności tak, aby automatycznie przypisywał do otwartej grupy czynności wiersze zamówienia do złożone do 12:00. W takim przypadku grupa czynności jest przetwarzana automatycznie.

Podczas przetwarzania grupy czynności, tworzona praca pobrania jest oparta szablonie pracy i na dyrektywie lokalizacji, która jest określona dla magazynu. Szablon pracy określa sposób tworzenia pracy pobierania, a dyrektywa lokalizacji określa lokalizacje pobrania i odłożenia.

## <a name="create-a-wave-template"></a>Tworzenie szablonu grupy czynności

Aby skonfigurować szablon grupy czynności, należy wykonać następujące czynności:

1. Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Grupy czynności** \> **Szablony grupy czynności**.
1. Wybierz pozycję **Nowy**, aby utworzyć nowy szablon grupy.
1. W polu **Typ szablonu grupy czynności** wybierz jeden z następujących opcji:

    - *Wysyłka* - Użyj szablonu grupy czynności do wysyłania towarów dla zamówień sprzedaży i zamówień przeniesienia.
    - *Zlecenia produkcji* - Użyj szablonu grupy czynności do przeniesienia towarów dla zleceń produkcyjnych.
    - *Kanban* - Użyj szablonu grupy czynności do przeniesienia towarów dla zleceń kanban.

1. W polach **Nazwa szablonu grupy czynności** i **Opis szablonu grupy czynności** wprowadź nazwę i opis szablonu grupy czynności.

    > [!NOTE]
    > Jeśli dla magazynu jest tworzony więcej niż jeden szablon, numer w polu **Sekwencja szablonów grupy czynności** wskazuje pozycję szablonu w kolejności, w jakiej szablony są stosowane po spełnia kryteriów szablonu. Można wybrać opcję **Przenieś w górę** lub **Przenieś w dół**, aby zmienić sekwencję szablonów.

1. W polach **Oddział** i **Magazyn** wybierz witrynę i magazyn, dla których szablon grupy czynności utworzy grupy czynności i pracę pobierania.
1. Aby zautomatyzować przetwarzanie grupy czynności, w razie potrzeby należy wprowadzić następujące ustawienia:

    - **Automatyczne tworzenie grupy czynności** -Wybierz opcję *Tak*, aby automatycznie utworzyć grupę czynności po zwolnieniu do magazynu zamówienia sprzedaży, zlecenia produkcyjnego lub karty kanban.
    - **Przypisz do otwartych grupy czynności** — ustaw wartość *Tak*, aby automatycznie przypisywać wiersze do otwartej grupy czynności po zwolnieniu wierszy. Wiersze są przypisywane do grup czynności w oparciu o filtr kwerendy dla szablonu grupy czynności.
    - **Przetwarzaj grupy czynności podczas zwalniania do magazynu** — ustaw wartość *Tak*, aby automatycznie przetwarzać grupy czynności i tworzyć pracę, gdy wiersz jest zwalniany do magazynu.
    - **Automatyczne przetwarzanie grupy czynności na progu** - Wybierz opcję *Tak*, aby automatycznie wykonywać grupy czynności po osiągnięciu przez jego wartości progów dla wagi, wysyłki i wierszy określonych w grupie pól **Progi grupy czynności**. Ta opcja jest dostępna aktywna po wybraniu opcji *Wysyłka* w polu **Typ szablonu grupy czynności**.
    - **Automatyczne zwalnianie grupy czynności** — ustaw dla tego przycisku wartość *Tak*, aby automatycznie zwolnić grupy czynności. Praca pobierania jest tworzona i udostępniana na urządzeniach przenośnych.
    - **Zautomatyzuj wydawanie prac związanych z uzupełnianiem zapasów** - ustaw opcję na *Tak*, aby tworzyć pracę uzupełnienia opartą na żądaniu, i zwalniać ją automatycznie. Należy dodać do szablonu grupy czynności metodę grupy czynności uzupełnienia i utworzyć szablon uzupełnienia typu *Popyt grupy czynności*. Konfigurowanie szablonu uzupełniania zapasów znajdujących się na stronie **Szablony uzupełniania zapasów**. Wymaga to dodania metody uzupełnienie do szablonu grupy czynności.
    - **Kontynuuj przetwarzanie grupowe, gdy tworzenie pracy nie powiedzie się** - ustwiając *Tak* system użyje pustej lokalizacji, jeśli nie może zarezerwować zapasów w lokalizacji proponowanej przez dyrektywę dotyczącą lokalizacji (na przykład, ponieważ zapasy nie są już dostępne). Gdy jest *Nie*, fala zakończy się niepowodzeniem, jeśli system nie będzie mógł zarezerwować zapasów.

1. Ustaw grupę pól **Progi grupy czynności** w razie potrzeby:
    - **Próg wagi grupy czynności** — wprowadź maksymalną wagę, jaka może zawierać grupy czynności.
    - **Próg wysyłki** — wprowadź maksymalną liczbę wysyłek, które można do grupy czynności.
    - **Wierz wysyłki** — wprowadź maksymalną liczbę wierszy, które można do grupy czynności.

1. W grupie pól **Domyślne wartości**, wybierz atrybuty grupy czynności używanej jako dodatkowe kryteria dla szablonu grupy czynności. Atrybuty grupy czynności są przydatne do przypisywania dodatkowych kryteriów, takich jak nazwa określonego odbiorcy, do szablonu grupy czynności. Utwórz atrybuty na stronie **Atrybuty grupy czynności**. 

1. Ustaw **zasady dotyczące powiadomień grupy czynności** na zasady, których chcesz używać do generowania powiadomień związanych z grupy czynności, które używają tego szablonu. Aby uzyskać przykład zasad dotyczących powiadomień o grupy czynności, zobacz [Powiadomienia dotyczące wykonywania grupy czynności](wave-execution-notifications.md)c

1. Na skróconej karcie **Metody** okienko **Wybrane metody** wymienia metody dla wybranego typu szablonu grupy czynności. Metody grupy czynności, które wykonują akcje tworzone przez szablon, tworzą lub dystrybuują pracę. Te akcje są również zwane krokami grupy czynności. Metody grupy czynności są wstępnie zdefiniowane dla każdego typu szablonu grupy czynności. Nie można usunąć wstępnie zdefiniowanych metod grupy czynności, można jednak zmienić kolejność metod i dodać dodatkowe metody. Na przykład jeśli tworzysz szablon grupy czynności do wysyłki, możesz dodać metody uzupełniania zapasów i tworzenia kontenerów. Można dodawać tworzenia kontenerów grupy czynności do metod grupy czynności w celu definiowania tworzenia kontenerów wierszy przetworzonych w szablonie grupy czynności. Aby dodać dodatkową metodę, wykonaj następujące czynności:

    - W okienku **Pozostałe metody** wybierz metodę, a następnie wybierz przycisk  **Lewej** strzałki, aby dodać go do okienka **Wybrane metody**.
    - Aby zmienić kolejność, wybierz metodę, a następnie kliknij strzałki **w górę** lub **w dół**.

    > [!NOTE]
    > Po dodaniu metody jest ona automatycznie wyświetlana w odpowiednim miejscu w sekwencji etapów.

1. Aby skonfigurować kwerendę, która dopasuje zwolnione wiersze do odpowiedniej grupy czynności, wybierz opcję **Edytuj kwerendę** w okienku akcji.
1. Aby sprawdzić, czy ustawienia szablonu grupy czynności są prawidłowe, kliknij **Zatwierdź szablon**.
