---
title: Przetwarzanie, przegląd i księgowanie rabatów
description: W tym temacie opisano, jak przetwarzać umowy zarządzania rabatami, obliczać ich rabaty, przeglądać generowane transakcje, księgować transakcje i przeglądać księgowania.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 524aec8025378391057275f77e31191f88e4a98b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690282"
---
# <a name="process-review-and-post-rebates"></a>Przetwarzanie, przegląd i księgowanie rabatów

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak przetwarzać umowy zarządzania rabatami, obliczać ich rabaty, przeglądać generowane transakcje, księgować transakcje i przeglądać księgowania.

## <a name="change-the-status-of-a-deal"></a>Zmiana stanu umowy

Do każdej umowy można przypisać stan, aby ułatwić jej śledzenie. Ten stan jest używany wyłącznie w celach informacyjnych.

1. Wybierz umowę (na przykład na [stronie **Wszystkie transakcje dotyczące zarządzania rabatami**](rebate-management-deals.md)).
1. W okienku akcji, na karcie **Zarządzanie rabatami — umowy** w grupie **Obsługa** wybierz **Zmień stan**.
1. W oknie dialogowym **Zmiana stanu** w polu **Stan rabatu** ustaw nowy stan.
1. Kliknij przycisk **OK**.

## <a name="calculate-fifo-purchase-prices"></a>Obliczanie cen zakupu FIFO

Zadanie okresowe **Obliczanie ceny zakupu FIFO** musi zostać uruchomione w celu obliczenia rabatów dla [umów](rebate-management-deals.md), w których w polu **Podstawa ceny** jest ustawiona wartość *FIFO*. W celu obliczenia wartości sprzedanych zapasów system użyje reguły FIFO. Wartość ta zostanie następnie użyta do obliczenia rabatów dostawcy.

Przejdź do zadania **Zarządzanie rabatami \> Zadania okresowe \> Obliczanie ceny zakupu FIFO**. W wyświetlonym oknie dialogowym wybierz przycisk **OK**, aby uruchomić obliczanie

## <a name="create-source-transactions"></a>Tworzenie transakcji źródłowych

Można utworzyć zamówienia sprzedaży lub zamówienia zakupu, które mają transakcje źródłowe przed lub po utworzeniu odpowiedniej umowy zarządzania rabatami.

Każdy wiersz transakcji można skonfigurować w taki sposób, aby automatycznie tworzył rezerwę rabatową, księgując dostawę lub fakturę dla zamówienia sprzedaży lub zamówienia zakupu. Ustaw pole **Typ transakcji** dla wiersza transakcji na *Dostawa* lub *Faktura* i ustaw opcję **Przetwarzanie podczas księgowania** na *Tak*. Jeśli pole **Typ transakcji** jest ustawione na *Zamówienie*, przetwarzanie podczas księgowania jest wyłączone. W przypadku transakcji źródłowych, które zostały utworzone po aktywowaniu transakcji, nadal można przetworzyć rezerwę zgodnie z opisem w sekcji [Przetwarzanie umów zarządzania rabatami](#process-deals) w dalszej części tego tematu.

### <a name="enable-price-details"></a>Włączanie szczegółów ceny

Przed utworzeniem transakcji źródłowych należy włączyć opcję **Włącz szczegóły ceny** na potrzeby rozrachunków z odbiorcami.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
1. Na karcie **Ceny** na skróconej karcie **Szczegóły ceny** dla opcji **Włącz szczegóły ceny** wybierz ustawienie *Tak*.

### <a name="create-a-source-transaction"></a>Tworzenie transakcji źródłowej

Aby utworzyć transakcję źródłową, należy wykonać poniższe kroki.

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Wybierz pozycję **Nowy**.

    Aby zilustrować sposób generowania roszczeń rabatowych, musisz teraz utworzyć zamówienie sprzedaży, w którym produkt i ilość będą kwalifikowały klienta do otrzymania rabatu.

1. W polu **Konto klienta** wprowadź lub wybierz klienta, który zakwalifikuje się do umowy rabatowej.
1. Wybierz przycisk **OK**, aby utworzyć zamówienie sprzedaży.
1. Na skróconej karcie **Wiersze zamówienia sprzedaży** dodaj wiersz i ustaw dla niego następujące pola:

    - **Numer pozycji** — określ pozycję, która kwalifikuje się do rabatu.
    - **Ilość** — umożliwia określenie ilości kwalifikującej się do umowy rabatowej zawierającej wiersz, w którym pole **Podstawa** jest ustawione na *Ilość*.
    - **Cena jednostkowa** — umożliwia określenie ceny kwalifikującej się do umowy rabatowej zawierającej wiersz, w którym pole **Podstawa** jest ustawione na *Wartość*.
    - **Witryna** — wybierz witrynę, w której produkt jest dostępny i która kwalifikuje się do umowy rabatowej.
    - **Magazyn** — wybierz magazyn, w której produkt jest dostępny i który kwalifikuje się do umowy rabatowej.

1. Na pasku narzędzi na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz pozycję **Wiersz zamówienia sprzedaży \> Ceny szczegóły**. To polecenie jest dostępne tylko wtedy, gdy włączono szczegóły ceny zgodnie z opisem w poprzedniej sekcji.
1. Na stronie **Szczegóły ceny** wybierz skróconą kartę **Zarządzanie rabatami**. Na tej skróconej karcie znajduje się lista wszystkich umów rabatowych, które mają zastosowanie do bieżącego wiersza zamówienia, oraz szacowane kwoty rabatów w walucie zamówienia. Należy zauważyć, że kwoty są tylko szacunkami przyszłych roszczeń rabatowych. Rzeczywiste kwoty rabatu mogą się różnić. Oto niektóre z czynników, które mogą mieć wpływ na rzeczywiste kwoty:

    - Całkowita wielkość sprzedaży osiągnięta przez klienta w ramach okresowej umowy rabatowej.
    - Czy klient zwrócił wszystkie ilości, czy częściowe ilości.
    - Czy odpowiednie zamówienie sprzedaży uzyskało typ transakcji (*Zamówienie, dostawa* lub *Faktura*), który jest zdefiniowany dla umowy zarządzania rabatem.
    - Wartość **wyjściowa** umowy. Pusta kwota rabatu zostanie wyświetlona dla umów, w których pole **wartości wyjściowej** jest ustawione na *Pozycja*.

1. Na skróconej karcie **Szczegóły** zauważ, że sekcja **Szacowanie marży** zawiera następujące pola. Te pola są dodawane przez zarządzanie rabatami. Wszystkie z nich pokazują wartości na jednostkę (podczas gdy pola na skróconej karcie **Zarządzanie rabatami** pokazują wartości całkowite dla wiersza).

    - **Kwota rabatu w zarządzaniu rabatami** (tylko zamówienia sprzedaży)
    - **Kwota tantiem w zarządzaniu rabatami** (tylko zamówienia sprzedaży)
    - **Kwota rabatu dostawcy w zarządzaniu rabatami** (zamówienia sprzedaży i zamówienia zakupu)

1. Zamknij stronę **szczegółów cen**.
1. Jeśli zamówienie sprzedaży nie powinno kwalifikować się do rabatów, które zostały właśnie wyświetlone, wykonaj następujące kroki, aby wykluczyć rabaty. (Jednak zazwyczaj nie wykluczasz rabatów).

    1. Na skróconej karcie **Wiersze zamówienia sprzedaży** wybierz odpowiedni wiersz.
    1. Na skróconej karcie **Szczegóły wiersza** na karcie **Cena i rabat** ustaw opcję **Wyklucz z zarządzania rabatami** na *Tak*. Ta opcja nie ma zastosowania do zamówień zakupu. Ponadto tylko rabaty dla klientów są wykluczone, gdy ta opcja jest ustawiona na *Tak*. Nadal obowiązują rabaty tantiem i rabaty dostawców.

1. W okienku akcji na karcie **Pobierz i zapakuj** w grupie **Generowanie** wybierz opcję **Księguj dokument dostawy**.
1. Na skróconej karcie **Parametry** w polu **Ilość** wybierz pozycję *Wszystkie*.
1. Kliknij przycisk **OK**.
1. Wybierz przycisk **OK**, jeśli zostanie wyświetlony monit o potwierdzenie operacji.
1. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
1. Na skróconej karcie **Parametry** w polu **Ilość** wybierz pozycję *Wszystkie* lub *Dokument dostawy*.
1. Kliknij przycisk **OK**.
1. Wybierz przycisk **OK**, jeśli zostanie wyświetlony monit o potwierdzenie operacji.

## <a name="process-rebate-management-deals"></a><a name="process-deals"></a>Przetwarzanie umów zarządzania rabatami

Podczas przetwarzania umowy system oblicza wszystkie odpowiednie rabaty i tantiemy, które są ustawione. Będą przetwarzane tylko wybrane transakcje, które mają okresy obliczania gotowe do obliczenia i mają stan *Aktywne*. Po zakończeniu przetwarzania system wygeneruje zestaw transakcji, które można przejrzeć, a następnie zak zaksięgowania.

> [!NOTE]
> We wszystkich przypadkach rabaty są przetwarzane na poziomie określonym przez ustawienie **Uzgodnij do** (*Umowa* lub *Wiersz*). Obliczenia jedno wierszowe można wykonać tylko dla transakcji, w których w polu **Uzgodnij do** jest ustawiona wartość *Wiersz*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Przetwarzaj wszystkie wiersze dla jednej lub większej liczby transakcji

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Wybierz wiersz dla każdej umowy, która ma być przetwarzana (lub otwórz umowę, która ma być przetwarzana).
1. W okienku akcji, na karcie **Umowy zarządzania rabatami**, w obszarze **Generuj** grupę wybierz jedno z następujących poleceń:

    - **Przetwarzanie \> Wdrażanie** – naliczanie zestawu naliczy dla każdej stosownej umowy rabatowej, ale nie księguj ich. Ta pozycja menu jest niedostępna dla transakcji, w których pole **Wynik rabatu** jest ustawione na *Element*.
    - **Przetwarzanie \> Zarządzanie rabatami** – Przetwarzanie szeregu transakcji, które zapewniają wartość rabatu dla każdej umowy.
    - **Proces \> Odpis** — dla każdej transakcji źródłowej dla umowy rabatowej i określonego okresu, przetworzyć wariancję pomiędzy kwotami, które zostały zaksięgowane na rezerwę i na zarządzanie rabatem. Ta pozycja menu jest niedostępna dla transakcji, w których pole **Wynik rabatu** jest ustawione na *Element*.

1. W wyświetlonym oknie dialogowym należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla obliczenia.
1. Wybierz przycisk **OK**, aby uruchomić obliczenia.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Przetwarzanie jednego lub więcej określonych wierszy umowy dla wybranej umowy

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Otwórz umowę, z której ma zostać przetworzyć wiersz.
1. Wybierz kartę **Wiersze** w prawym górnym rogu.
1. Na skróconej karcie **Zarządzanie rabatami** wybierz wiersz dla każdego wiersza umowy, który chcesz przetworzyć.
1. Na pasku narzędzi skróconej karty **Zarządzanie rabatami** wybierz jedno z następujących poleceń. (Te polecenia są dostępne tylko dla transakcji, w których pole **Uzgodnij do** ma wartość *Wiersz*).

    - **Przetwarzanie \> Prowizje** – naliczanie zestawu naliczeń dla każdego wiersza umowy rabatowej, ale nie księguje ich. Ta pozycja menu jest niedostępna dla transakcji, w których pole **Wynik rabatu** jest ustawione na *Element*.
    - **Przetwarzanie \> Zarządzanie rabatami** – Przetwarzanie szeregu transakcji, które zapewniają wartość rabatu dla każdego wiersza umowy.
    - **Proces \> Odpis** — dla każdej transakcji źródłowej dla umowy rabatowej i określonego okresu, przetworzyć wariancję pomiędzy kwotami, które zostały zaksięgowane na rezerwę i na zarządzanie rabatem. Ta pozycja menu jest niedostępna dla transakcji, w których pole **Wynik rabatu** jest ustawione na *Element*. 

1. W wyświetlonym oknie dialogowym należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla obliczenia.
1. Wybierz przycisk **OK**, aby uruchomić obliczenia.

### <a name="process-deals-using-a-batch-job"></a>Przetwarzaj transakcje przy użyciu zadania wsadowego

Zamiast przetwarzać określone transakcje lub wiersze umów, można uruchomić zadanie wsadowe w celu przetworzenia kilku transakcji jednocześnie. Opcjonalnie można zastosować filtry rekordów i/lub skonfigurować harmonogram cykliczny. Aby przetwarzać transakcje za pomocą zadania wsadowego, należy wykonać następujące czynności.

1. Wykonaj jeden z następujących kroków:

    - Przejdź do zadania procesowego **Zarządzanie rabatami \> Zadania okresowe \> Procesy \> Obsługa** dla każdej konkretnej umowy, ale nie księguje ich.
    - Przejdź **Zarządzanie rabatami \> Zadania okresowe \> Przetwarzanie \> Zarządzanie rabatami**, aby przetworzyć serię transakcji, które podają wartość rabatu dla każdej transakcji.
    - Przejdź do **Zarządzanie rabatami \> Zadania okresowe \> Przetwarzanie \> Odpisz**, aby wycofać wcześniej zaksięgowanych transakcji w celu ich odpisu w celu obliczenia nowych transakcji umowy rabatowej.

1. W oknie dialogowym, który zostanie wyświetlony, na skróconej karcie **Parametry**, w sekcji **Okres** ustaw pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla transakcji w obliczeniach.
1. W sekcji **Okres gwarancji** należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat gwarantowanych dla obliczenia.
1. W **Rekordy do uwzględnienia**, można skonfigurować filtry, aby ograniczyć zestaw transakcji przetwarzanych przez zadanie wsadowe. Te ustawienia działają w taki sam sposób, jak działają w przypadku innych typów zadań wsadowych.
1. Możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe na skróconej karcie **Uruchom w tle**. Te ustawienia działają w taki sam sposób, jak działają w przypadku innych typów zadań wsadowych.
1. Wybierz przycisk **OK**, aby uruchomić i/lub zaplanować wybrane obliczenia.

### <a name="process-deals-by-using-the-rebate-workbench"></a>Przetwarzanie umów przy użyciu pulpitu rabatów

Zamiast przetwarzać określone umowy lub wiersze umów, można uruchomić *pulpit rabatów* w celu przetworzenia wielu umów jednocześnie. Opcjonalnie można zastosować filtry rekordów i/lub skonfigurować harmonogram cykliczny. Nie musisz wybierać żadnych wierszy. System przetworzy wszystkie wiersze, które spełniają wymagania dotyczące daty i filtru, które zostały skonfigurowane.

Aby przetwarzać transakcje za pomocą pulpitu rabatów, należy wykonać następujące czynności.

1. Przejdź do oferty **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Pulpit rabatów**.
1. W okienku akcji, na karcie **Pulpit rabatów**, w grupie **Przetwarzanie** wybierz jedno z następujących poleceń:

    - **Przetwarzanie \> Prowizje** – naliczanie zestawu naliczeń dla każdego wiersza umowy rabatowej, ale bez księgowania naliczeń.
    - **Przetwarzanie \> Zarządzanie rabatami** – Przetwarzanie szeregu transakcji, które zapewniają wartość rabatu dla każdego wiersza umowy.
    - **Proces \> Odpis** — przetwarzanie odchylenia między prowizją i zarządzaniem rabatami, które jest księgowane dla każdej transakcji źródłowej na umowę rabatową i wybrany okres.

1. W oknie dialogowym **Zarządzanie rabatami**, w sekcji **Okres** ustaw pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla transakcji w obliczeniach.
1. W sekcji **Okres gwarancji** należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat gwarantowanych dla obliczenia.
1. W **Rekordy do uwzględnienia**, można skonfigurować filtry, aby ograniczyć zestaw transakcji przetwarzanych przez zadanie wsadowe. Te ustawienia działają w taki sam sposób, jak działają w przypadku innych typów zadań wsadowych.
1. Możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe na skróconej karcie **Uruchom w tle**. Te ustawienia działają w taki sam sposób, jak działają w przypadku innych typów zadań wsadowych.
1. Wybierz przycisk **OK**, aby uruchomić i/lub zaplanować wybrane obliczenia.

## <a name="view-and-edit-rebate-management-transactions"></a>Wyświetlanie i edytowanie transakcji zarządzania rabatami

Podczas przetwarzania jednej lub większej liczby transakcji system tworzy transakcje, które można wyświetlać i, być może, edytować przed zaksięgowaniem.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-deals-list-page"></a>Wyświetlanie i edytowanie transakcji zarządzania rabatami przy użyciu strony listy umów rabatowych

Aby wyświetlić i edytować transakcje zarządzania rabatami przy użyciu strony listy umów rabatowych, wykonaj następujące kroki.

1. Wykonaj jeden z następujących kroków:

    - Wybierz umowę, dla których chcesz wyświetlić transakcje (na przykład na stronie [**Wszystkie transakcje dotyczące zarządzania rabatami**](rebate-management-deals.md)). W okienku akcji, na karcie **Zarządzanie rabatami — umowy**, w grupie **Transakcje** wybierz opcję **Transakcje** lub **Gwarantowane transakcje**, w zależności od typu transakcji, którą chcesz wyświetlić.
    - Otwórz (na przykład na stronie [**Wszystkie transakcje dotyczące zarządzania rabatami**](rebate-management-deals.md)), aby wyświetlić szczegóły. Na skróconej karcie **Zarządzanie rabatami** wybierz wiersz umowy, dla których chcesz wyświetlić transakcje. Następnie na pasku narzędzi wybierz opcję **Transakcje** lub **Gwarantowane transakcje**, w zależności od typu transakcji, którą chcesz wyświetlić. (Te przyciski są dostępne tylko dla transakcji, w których pole **Uzgodnij do** ma wartość *Wiersz*).

1. Zostanie wyświetlona strona **Transakcje dotyczące daty zarządzania rabatami** lub **Transakcje gwarancji zarządzania rabatami**. Zawiera siatkę, w której każdy wiersz reprezentuje zbiór transakcji z jednego rabatu lub okresu gwarancji. Zaznacz wiersz w siatce, a następnie w okienku akcji wybierz **Transakcje źródłowe**, aby wyświetlić transakcje należące do tego wiersza.
1. Na stronie, która zostanie wyświetlona lista transakcji wybranego typu należących do wybranego wiersza. W zależności od typu transakcji każda transakcja udostępnia odpowiednie szczegóły. Dla transakcji poręczenia można tylko wyświetlić listę. W przypadku innych typów transakcji na tej stronie można wykonywać następujące czynności:

    - Aby sprawdzić wartość całkowitą wszystkich roszczenia transakcji na stronie, wyświetl pole **Kwota odebrana**.
    - Aby wyświetlić więcej informacji o dowolnej transakcji, zaznacz ją, a następnie wybierz kartę **Ogólne**, **Wymiar finansowy** lub **Wymiar**.
    - Aby wyświetlić ewentualne redukcje, należy wybrać **Transakcje redukcji** w okienku akcji. Aby uzyskać więcej informacji, zobacz [Zasady redukcji rabatów](rebate-reduction-principle.md).
    - Aby oznaczyć transakcje jako roszczenia lub zwroty, jeśli jest wykonywany proces oświadczeń, zaznacz odpowiednie wiersze, a następnie w okienku akcji wybierz jedno z poniższych poleceń. (Procesy oświadczeń są włączane na [stronie **Parametrów zarządzania rabatami**](rebate-management-parameters.md).)

        - **Ustaw odebrane \> Wszystkie** — oznacz wszystkie transakcje jako odebraną.
        - **Ustaw odebrane \> Wybrane** – Oznacz wybrane transakcje jako odebraną.
        - **Ustaw nieodebrane \> Wszystkie** — oznacz wszystkie transakcje jako nieodebrane.
        - **Ustaw nieodebrane \> Wybrane** – Oznacz wybrane transakcje jako nieodebrane.

    - Wybierz **Opublikuj** na panelu akcji, aby zaksięgować roszczenie dla wszystkich odpowiednich linii. Jeśli używasz procesu reklamacyjnego (gdy opcja **Użyj procesu reklamacyjnego** jest włączona na stronie **Parametry zarządzania reklamacjami**), tylko wiersze, które są oznaczone jako **Reklamowane** są księgowane. W przeciwnym razie księgowane są wszystkie transakcje źródłowe dla wybranej transakcji rabatowej. Przycisk **Księguj** jest dostępny tylko dla transakcji rabatowych. Nie jest dostępny dla transakcji aprowizyjnych i odpisów. W oknie dialogowym **Księgowanie pola** **Data od** i **Data do** są ustawiane automatycznie. Ustaw pole **Data księgowania** i wybierz **OK**.
    - Aby skorygować kwotę pokazywaną dla dowolnej otwartej lub niezaksięgowanych transakcji, wybierz transakcję, a następnie wykonaj jedną z poniższych czynności:

        - Edytuj wartość w polu **Skorygowana kwota**.
        - W okienku akcji wybierz opcję **Ustawianie korekty**. Następnie w oknie rozwijaym, które zostanie wyświetlone, w polu **Skorygowana kwota** wprowadź wartość.

> [!NOTE]
> Jeśli używasz procesu reklamacji, podczas przetwarzania następnego okresu, lista transakcji będzie zawierała wszystkie nieodebrane transakcje z poprzedniego księgowania oraz wszystkie nowe transakcje dla wybranego okresu.

### <a name="view-and-edit-rebate-management-transactions-by-using-the-rebate-workbench"></a>Wyświetlanie i edytowanie transakcji zarządzania rabatami przy użyciu pulpitu rabatów

Aby wyświetlić i edytować transakcje zarządzania rabatami przy użyciu pulpitu rabatów, wykonaj następujące kroki.

1. Przejdź do oferty **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Pulpit rabatów**.
1. Ustaw pole **Pokaż** na *Niezaksięgowane*.
1. Na stronie **Pulpit rabatów** znajduje się lista transakcji. Każda transakcja zawiera odpowiednie szczegóły. Te szczegóły różnią się w zależności od typu transakcji. Na tej stronie możesz wykonać następujące akcje:

    - Aby wyświetlić więcej informacji o dowolnej transakcji, zaznacz ją, a następnie wybierz kartę **Ogólne**, **Wymiar finansowy** lub **Wymiar**.
    - Jeśli używasz procesu roszczeń, możesz oznaczyć transakcje jako odebrane lub nieodebrane. Wybierz odpowiednie wiersze, a następnie w okienku akcji na karcie **Pulpit rabatów**, w grupie wybierz jedno z następujących poleceń. (Procesy roszczeń są włączane na stronie [**Parametry zarządzania rabatami**](rebate-management-parameters.md)).

        - **Ustaw odebrane** — oznacz wybrane transakcje jako odebrane.
        - **Ustaw nieodebrane** — oznacz wybrane transakcje jako nieodebrane.

    - Aby zaksięgować roszczenie dla jednego lub większej liczby wierszy, zaznacz odpowiednie wiersze. Następnie w okienku akcji na karcie **Pulpit rabatów** wybierz opcję **Księguj**. Przycisk **Księguj** jest dostępny dla transakcji prowizji, rabatów i odpisów. W oknie dialogowym **Księgowanie pola** **Data od** i **Data do** są ustawiane automatycznie. Ustaw pole **Data księgowania** i wybierz **OK**.
    - Aby skorygować kwotę pokazywaną dla dowolnej otwartej lub niezaksięgowanych transakcji, wybierz transakcję, a następnie wykonaj jedną z poniższych czynności:

        - Edytuj wartość w polu **Skorygowana kwota**.
        - W okienku akcji na karcie **Pulpit rabatów** wybierz opcję **Ustaw korektę**. Następnie w oknie rozwijaym, które zostanie wyświetlone, w polu **Skorygowana kwota** wprowadź wartość.

> [!NOTE]
> Jeśli używasz procesu reklamacji, podczas przetwarzania następnego okresu, lista transakcji będzie zawierała wszystkie nieodebrane transakcje z poprzedniego księgowania oraz wszystkie nowe transakcje dla wybranego okresu.

## <a name="post-rebates-transactions"></a>Zaksięguj transakcje rabatów

Aby zaksięgować wartość przetworzonej rezerwy, kwoty zarządzania rabatem oraz odpisu, należy uruchomić proces księgowania. Proces księgowania oznacza transakcje rezerw, zarządzania rabatami lub odpisami jako zaksięgowane i tworzy transakcję docelową. Jeśli nie musisz przeglądać transakcji docelowej, transakcje te można skonfigurować tak, aby były automatycznie księgowane.

### <a name="set-up-the-system-to-post-all-target-transactions-automatically"></a>Umożliwia skonfigurowanie w systemie automatycznego księgowania wszystkich transakcji docelowych

Aby skonfigurować system do zaksięgowania wszystkich transakcji docelowych z chwilą ich wygenerowania przez rezerwę księgową, kwotę zarządzania rabatem oraz odpis, włącz opcję **Automatycznie księguj arkusze** i/lub **Automatycznie księguj faktury urzędowe** na stronie **Parametry zarządzania rabatami**. Aby uzyskać więcej informacji, zajrzyj do omówienia [Omówienie parametrów Zarządzanie rabatami](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Księguj transakcje dla wszystkich linii dla jednej lub więcej transakcji

Po przetworzeniu odpowiednich transakcji należy wykonać poniższe kroki, aby przejrzeć i zaksięgować wygenerowane transakcje dla wszystkich wierszy jednej lub większej liczby transakcji.

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Wybierz wiersz dla każdej umowy, która ma być zaksięgowana (lub otwórz umowę, która ma być zaksięgowana).
1. W okienku akcji, na karcie **Umowy zarządzania rabatami**, w obszarze **Generuj** grupę wybierz jedno z następujących poleceń:

    - **Księguj \> Prowizja** – Księguj dostępne transakcje rozliczeniowe, które utworzyłeś.
    - **Księguj \> Zarządzanie rabatami** – Księguj dostępne transakcje rabatów, które utworzyłeś.
    - **Księguj \> Odpis** – Księguj dostępne transakcje odpisów, które utworzyłeś.

1. W wyświetlonym oknie dialogowym można ustawić pole **Data księgowania**. Należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla transakcji, które muszą być zaksięgowane.
1. Wybierz **OK**, aby zaksięgować transakcje.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Księgowanie transakcji jednego lub więcej określonych wierszy umowy dla wybranej umowy

Po przetworzeniu odpowiednich transakcji, wykonaj poniższe kroki, aby przejrzeć i zaksięgować wygenerowane transakcje dla jednej lub więcej linii dla wybranej transakcji. Procedura ta ma zastosowanie wyłącznie do transakcji, w których **Uzgodnij do** ma wartość *Wiersz*.

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Otwórz umowę, w której znajduje się wiersz, dla którego mają zostać zaksięgowane transakcje.
1. Wybierz kartę **Wiersze** w prawym górnym rogu.
1. Na skróconej karcie **Zarządzanie rabatami** wybierz wiersz dla każdego wiersza umowy, który chcesz zaksięgować.
1. Na pasku narzędzi skróconej karty **Zarządzanie rabatami** wybierz jedno z następujących poleceń. (Te polecenia są dostępne tylko dla transakcji, w których pole **Uzgodnij do** ma wartość *Wiersz*).

    - **Księguj \> Prowizja** – Księguj dostępne transakcje rozliczeniowe, które utworzyłeś.
    - **Księguj \> Zarządzanie rabatami** – Księguj dostępne transakcje rabatów, które utworzyłeś.
    - **Księguj \> Odpis** – Księguj dostępne transakcje odpisów, które utworzyłeś.

1. W wyświetlonym oknie dialogowym można ustawić pole **Data księgowania**. Należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla transakcji, które muszą być zaksięgowane.
1. Wybierz **OK**, aby zaksięgować transakcje.

### <a name="post-transactions-using-a-batch-job"></a>Księgowanie transakcji przy użyciu zadania wsadowego

Zamiast księgować transakcje dla określonych transakcji lub linii transakcji, możesz uruchomić zadanie wsadowe, aby księgować transakcje dla kilku umów jednocześnie. Opcjonalnie można zastosować filtry rekordów i/lub skonfigurować harmonogram cykliczny. Aby zaksięgować transakcje za pomocą zadania wsadowego, należy wykonać następujące czynności.

1. Wykonaj jeden z następujących kroków:

    - Przejdź do **Zarządzanie rabatami \> Zadania okresowe \> Księguj \> Prowizja**, aby zakresować utworzone transakcje naliczania.
    - Przejdź do **Zarządzanie rabatami \> Zadania okresowe \> Księguj \> Zarządzaj rabatami**, aby zakresować utworzone transakcje rabatów.
    - Przejdź do **Zarządzanie rabatami \> Zadania okresowe \> Księguj \> Odpis**, aby zakresować utworzone transakcje ospisów.

1. W oknie dialogowym, który zostanie wyświetlony, na skróconej karcie **Parametry**, w sekcji **Okres** ustaw pole **Data księgowania**. Należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla transakcji, które muszą być zaksięgowane.
1. W sekcji **Okres gwarancji** należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat gwarantowanych do zaksięgowania.
1. W **Rekordy do uwzględnienia**, można skonfigurować filtry, aby ograniczyć zestaw transakcji przetwarzanych przez zadanie wsadowe. Te ustawienia działają w taki sam sposób, jak działają w przypadku innych typów zadań wsadowych.
1. Możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe na skróconej karcie **Uruchom w tle**. Te ustawienia działają w taki sam sposób, jak działają w przypadku innych typów zadań wsadowych.
1. Wybierz przycisk **OK**, aby uruchomić i/lub zaplanować wybrane obliczenia.

### <a name="post-transactions-by-using-the-rebate-workbench"></a>Księgowanie transakcji przy użyciu pulpitu rabatów

Po przetworzeniu transakcji prowizji, rabatów lub odpisów wykonaj następujące kroki, aby użyć pulpitu rabatów do przeglądania i księgowania wygenerowanych transakcji dla jednego lub większej liczby określonych wierszy transakcji dla wszystkich umów.

1. Przejdź do oferty **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Pulpit rabatów**.
1. W siatce zaznacz wiersz dla każdej linii transakcji, którą chcesz zaksięgować. Można wybrać niezaksięgowane transakcje prowizji, rabatów i/lub odpisów. Obowiązują następujące zasady:

    - System zaksięguje również wszystkie wiersze, które mają taką samą wartość **numeru transakcji rabatu**, jak wybrane wiersze.
    - System nie będzie księgował żadnych wierszy z typem transakcji *Rabat*, które nie są oznaczone jako odebrane.
    - Jeśli wybierzesz wiersze, które zostały już zaksięgowane, system pominie zaksięgowane wiersze.
    - Przycisk **Księguj** jest dostępny tylko wtedy, gdy wybierzesz co najmniej jeden niezaksięgowany wiersz.

1. W okienku akcji na karcie **Pulpit rabatów** w grupie **Przetwarzanie** wybierz pozycję **Księguj**.
1. W oknie dialogowym **księgowania** można ustawić pole **Data księgowania**. Pola **Od dnia** i **Do dnia** są ustawiane automatycznie na podstawie najwcześniejszej wartości **Od dnia** i najnowszej wartości **Do dnia** dla wybranych wierszy.
1. Wybierz **OK**, aby zaksięgować transakcje.

## <a name="review-rebate-management-journals"></a><a name="review-journals"></a>Przegląd arkuszy zarządzania rabatami

Po zaksięgowaniu transakcji można przejrzeć wynikowe arkusze, dokumenty lub towary. Transakcje docelowe dotyczące rabatów i tantiem są oparte na typie płatności ustawionym w profilu księgowania oraz typie wyjściowym rabatu. Na przykład, jeśli wyjście rabatu jest ustawione na *Element*, zamówienie sprzedaży zostanie utworzone dla rabatu klienta, a zamówienie zakupu zostanie utworzone dla rabatu sprzedawcy. Zlecenia te można przeglądać poprzez transakcje docelowe. Jeśli płatność jest ustawiona do korzystania z rozrachunków z dostawcami, dla dostawcy skonfigurowania odbiorcy zostanie utworzona faktura dostawcy z tytułu rabatów dla odbiorcy.

### <a name="review-journals-by-using-the-rebate-deals-list-page"></a>Przeglądanie arkuszy przy użyciu strony listy umów rabatowych

Aby przejrzeć zapisy w arkuszu powiązane z umowami w zakresie zarządzania rabatami, należy wykonać następujące czynności.

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Wybierz umowę, dla których mają być sprawdzane zapisy w arkuszu.
1. W okienku akcji, na karcie **Zarządzanie rabatami — umowy**, w grupie **Transakcje** wybierz opcję **Transakcje** lub **Gwarantowanie transakcji**, w zależności od typu transakcji, którą chcesz wyświetlić.
1. Ustaw pole **Pokaż** na *Wszystkie* lub *Niezaksięgowane*.
1. Znajdź i zaznacz kolekcję transakcji, którą chcesz sprawdzić, a następnie w okienku akcji wybierz jeden z poniższych przycisków. (Te przyciski są dostępne tylko wtedy, gdy dla wybranej kolekcji transakcji istnieją odpowiednie księgowania)

    - **Transakcje docelowe** – Przegląd odpowiednich arkuszy i innych typów dokumentów wygenerowanych przez wybraną umowę.
    - **Towary** — przejrzyj odpowiednie zamówienia sprzedaży lub zamówienia zakupu, które zostały wygenerowane przez wybraną ofertę.

1. Zostanie wyświetlona lista odpowiednich arkuszy, dokumentów lub towarów. Aby wyświetlić więcej informacji o dowolnym arkuszu, dokumencie lub towarze, należy wybrać jego wiersz, a następnie w okienku akcji wybrać polecenie **Wyświetl szczegóły**.

### <a name="review-journals-by-using-the-rebate-workbench"></a>Przeglądanie dzienników przy użyciu pulpitu rabatów

Aby przejrzeć dzienniki za pomocą pulpitu rabatów, należy wykonać następujące czynności.

1. Przejdź do oferty **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Pulpit rabatów**.
1. Ustaw pole **Pokaż** na _Wszystkie_ lub _Niezaksięgowane_.
1. Odszukaj i zaznacz wiersz, który chcesz zbadać. Następnie w okienku akcji na karcie **Pulpit rabatów** w grupie **Wyświetlanie** wybierz pozycję **Transakcje docelowe**. Ten przycisk jest dostępny tylko wtedy, gdy istnieją odpowiednie księgowania dla wybranego wiersza.
1. Zostanie wyświetlona lista odpowiednich arkuszy, dokumentów lub towarów. Aby wyświetlić więcej informacji o dowolnym arkuszu, dokumencie lub towarze, należy wybrać jego wiersz, a następnie w okienku akcji wybrać polecenie **Wyświetl szczegóły**.

## <a name="rebate-management-transactions-on-the-deduction-workbench"></a>Transakcje zarządzania rabatami na pulpicie potrąceń

Podczas księgowania transakcji zarządzania rabatami, która ma jedną z następujących wartości **Typ płatności**, system tworzy arkusz potrąceń klienta lub fakturę niezależną dla odpowiedniego konta klienta:

- Potrącenia od odbiorcy
- Potrącenia odbiorcy z faktury podatkowej
- Wydatki handlowe
- Raportowania

Po utworzeniu i zaksięgowaniu transakcji docelowej będzie ona dostępna jako otwarta transakcja na stronie **pulpitu potrąceń** (**Sprzedaż i marketing \> Odpisy handlowe \> Potrącenia \> Pulpit potrącenia**). Otwarte transakcje mają wartość **typu roszczenia** ustawioną na *Zarządzanie rabatami*, a wartość **numeru transakcji rabatu** jest dostępna, dzięki czemu można śledzić daną transakcję. Data jest ustawiona na datę księgowania transakcji docelowej zarządzania rabatami. Aby użyć pulpitu potrącenia do rozliczania otwartych transakcji z istniejącymi potrąceniami dla tego samego konta klienta, wybierz pozycję **Obsługa \> Dopasuj** w okienku akcji.

Aby uzyskać więcej informacji, zobacz [Zarządzanie potrąceniami przy użyciu pulpitu potrącenia](deduction-workbench.md).

## <a name="purge-unposted-transactions"></a>Przeczyszczanie niezaksięgowanych transakcji

Po przetworzeniu transakcji prowizji, rabatów lub odpisów wykonaj następujące kroki, aby przeczyścić wybrane transakcje niezaksięgowane.

1. Przejdź do oferty **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Pulpit rabatów**.
2. Ustaw pole **Pokaż** na *Niezaksięgowane*.
3. Znajdź i wybierz transakcje do usunięcia. Następnie w okienku akcji na karcie **Pulpit rabatów** w grupie **Przetwarzanie** wybierz pozycję **Przeczyść**.
4. Wybierz przycisk **OK**, aby usunąć niezaksięgowane transakcje.

## <a name="cancel-a-posted-provision"></a>Anulowanie zaksięgowanej prowizji

Po przetworzeniu i zaksięgowanym prowizji wykonaj następujące kroki, aby anulować zaksięgowane transakcje prowizji.

1. Przejdź do oferty **Zarządzanie rabatami \> Zarządzanie rabatami — umowy \> Pulpit rabatów**.
2. Ustaw pole **Pokaż** na *Zaksięgowane*.
3. Znajdź i wybierz transakcje prowizji do anulowania. Następnie w okienku akcji na karcie **Pulpit rabatów** w grupie **Przetwarzanie** wybierz pozycję **Anuluj prowizję**.
4. Wybierz **OK**, aby wycofać transakcje.

Te cofnięcia prowizji będą również widoczne w odpowiednich [arkuszach zarządzania rabatami](#review-journals).
