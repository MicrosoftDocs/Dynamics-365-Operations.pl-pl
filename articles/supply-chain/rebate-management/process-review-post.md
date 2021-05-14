---
title: Przetwarzanie, przegląd i księgowanie rabatów
description: W tym temacie opisano, jak przetwarzać umowy zarządzania rabatami, obliczać ich rabaty, przeglądać generowane transakcje, księgować transakcje i przeglądać księgowania.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: e255c60889fdb49dfd8a1fd01be839b6405b02c6
ms.sourcegitcommit: 890a0b3eb3c1f48d786b0789e5bb8641e0b8455e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5919876"
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

## <a name="process-rebate-management-deals"></a>Przetwarzanie umów zarządzania rabatami

Podczas przetwarzania umowy system oblicza wszystkie odpowiednie rabaty i tantiemy, które są ustawione. Będą przetwarzane tylko wybrane transakcje, które mają okresy obliczania gotowe do obliczenia i mają stan *Aktywne*. Po zakończeniu przetwarzania system wygeneruje zestaw transakcji, które można przejrzeć, a następnie zak zaksięgowania.

> [!NOTE]
> We wszystkich przypadkach rabaty są przetwarzane na poziomie określonym przez ustawienie **Uzgodnij do** (*Umowa* lub *Wiersz*). Obliczenia jedno wierszowe można wykonać tylko dla transakcji, w których w polu **Uzgodnij do** jest ustawiona wartość *Wiersz*.

### <a name="process-all-lines-for-one-or-more-deals"></a>Przetwarzaj wszystkie wiersze dla jednej lub większej liczby transakcji

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Wybierz wiersz dla każdej umowy, która ma być przetwarzana (lub otwórz umowę, która ma być przetwarzana).
1. W okienku akcji, na karcie **Umowy zarządzania rabatami**, w obszarze **Generuj** grupę wybierz jedno z następujących poleceń:

    - **Przetwarzanie \> Wdrażanie** – naliczanie zestawu naliczy dla każdej stosownej umowy rabatowej, ale nie księguj ich.
    - **Przetwarzanie \> Zarządzanie rabatami** – Przetwarzanie szeregu transakcji, które zapewniają wartość rabatu dla każdej umowy.
    - **Przetwarzanie \> Odpisanie** — wycofanie wcześniej zaksięgowanych transakcji w celu ich odpisu w celu obliczenia nowych transakcji umowy rabatowej.

1. W wyświetlonym oknie dialogowym należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla obliczenia.
1. Wybierz przycisk **OK**, aby uruchomić obliczenia.

### <a name="process-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Przetwarzanie jednego lub więcej określonych wierszy umowy dla wybranej umowy

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Otwórz umowę, z której ma zostać przetworzyć wiersz.
1. Wybierz kartę **Wiersze** w prawym górnym rogu.
1. Na skróconej karcie **Zarządzanie rabatami** wybierz wiersz dla każdego wiersza umowy, który chcesz przetworzyć.
1. Na pasku narzędzi skróconej karty **Zarządzanie rabatami** wybierz jedno z następujących poleceń. (Te polecenia są dostępne tylko dla transakcji, w których pole **Uzgodnij do** ma wartość *Wiersz*).

    - **Przetwarzanie \> Prowizje** – naliczanie zestawu naliczeń dla każdego wiersza umowy rabatowej, ale nie księguje ich.
    - **Przetwarzanie \> Zarządzanie rabatami** – Przetwarzanie szeregu transakcji, które zapewniają wartość rabatu dla każdego wiersza umowy.
    - **Przetwarzanie \> Odpisanie** — wycofanie wcześniej zaksięgowanych transakcji w celu ich odpisu w celu obliczenia nowych transakcji umowy rabatowej.

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

## <a name="view-and-edit-rebate-management-transactions"></a>Wyświetlanie i edytowanie transakcji zarządzania rabatami

Podczas przetwarzania jednej lub większej liczby transakcji system tworzy transakcje, które można wyświetlać i, być może, edytować przed zaksięgowaniem.

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

    - Aby zakłać roszczenie dotyczące jednego lub większej liczby wierszy, zaznacz odpowiednie wiersze, a następnie w okienku akcji wybierz opcję **Księguj**. (Przycisk **Księguj** jest dostępny tylko dla transakcji rabatowych. Nie jest dostępny dla transakcji udostępniania i odpisu.) W oknie dialogowym **Księguj** pola **Od dnia** i **Do dnia** są ustawiane automatycznie. Ustaw pole **Data księgowania** i wybierz **OK**.
    - Aby skorygować kwotę pokazywaną dla dowolnej otwartej lub niezaksięgowanych transakcji, wybierz transakcję, a następnie wykonaj jedną z poniższych czynności:

        - Edytuj wartość w polu **Skorygowana kwota**.
        - W okienku akcji wybierz opcję **Ustawianie korekty**. Następnie w oknie rozwijaym, które zostanie wyświetlone, w polu **Skorygowana kwota** wprowadź wartość.

> [!NOTE]
> Podczas przetwarzania następnego okresu lista transakcji będzie zawierać wszelkie transakcje nieodebrane z poprzedniego księgowania plus nowe transakcje dla wybranego okresu.

## <a name="post-rebates-transactions"></a>Zaksięguj transakcje rabatów

Aby zak księgować wartości rabatów i potrąceń, należy uruchomić proces księgowania, chyba że w systemie ustawiono ich automatyczne księgowanie.

### <a name="set-up-the-system-to-post-all-transactions-automatically"></a>Umożliwia skonfigurowanie w systemie automatycznego księgowania wszystkich transakcji

Aby skonfigurować system do zaksięgowania wszystkich transakcji natychmiast po ich wygenerowaniu, włącz opcję **Automatycznie księguj arkusze** i/lub **Automatycznie księguj faktury urzędowe** na stronie **Parametry zarządzania rabatami**. Aby uzyskać więcej informacji, zajrzyj do omówienia [Omówienie parametrów Zarządzanie rabatami](rebate-management-parameters.md).

### <a name="post-transactions-for-all-lines-for-one-or-more-deals"></a>Księguj transakcje dla wszystkich linii dla jednej lub więcej transakcji

Jeśli księgowanie automatyczne nie jest realizowane, po przetworzeniu odpowiednich transakcji należy wykonać poniższe kroki, aby przejrzeć i zak księgować wygenerowane transakcje dla wszystkich wierszy jednej lub większej liczby transakcji.

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Wybierz wiersz dla każdej umowy, która ma być zaksięgowana (lub otwórz umowę, która ma być zaksięgowana).
1. W okienku akcji, na karcie **Umowy zarządzania rabatami**, w obszarze **Generuj** grupę wybierz jedno z następujących poleceń:

    - **Księguj \> Prowizja** – Księguj dostępne transakcje rozliczeniowe, które utworzyłeś.
    - **Księguj \> Zarządzanie rabatami** – Księguj dostępne transakcje rabatów, które utworzyłeś.
    - **Księguj \> Odpis** – Księguj dostępne transakcje odpisów, które utworzyłeś.

1. W wyświetlonym oknie dialogowym można ustawić pole **Data księgowania**. Należy ustawić pola **Od dnia** i **Do dnia**, aby zdefiniować zakres dat dla transakcji, które muszą być zaksięgowane.
1. Wybierz **OK**, aby zaksięgować transakcje.

### <a name="post-transactions-for-one-or-more-specific-deal-lines-for-a-selected-deal"></a>Księgowanie transakcji jednego lub więcej określonych wierszy umowy dla wybranej umowy

Jeśli nie korzystasz z automatycznego księgowania, po przetworzeniu odpowiednich umów wykonaj następujące kroki, aby przejrzeć i zaksięgować wygenerowane transakcje dla co najmniej jednej linii umowy dla wybranej umowy.

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

## <a name="review-rebate-management-journals"></a>Przegląd arkuszy zarządzania rabatami

Po zaksięgowaniu transakcji można przejrzeć wynikowe arkusze, dokumenty lub towary. Transakcje docelowe dotyczące rabatów i tantiem są oparte na typie płatności ustawionym w profilu księgowania oraz typie wyjściowym rabatu. Na przykład, jeśli rabat wyjścia ma wartość *Towar*, tworzone jest zamówienie sprzedaży, które może być przeglądane przy użyciu transakcji docelowych. Jeśli płatność jest ustawiona do korzystania z rozrachunków z dostawcami, dla dostawcy skonfigurowania odbiorcy zostanie utworzona faktura dostawcy z tytułu rabatów dla odbiorcy.

Aby przejrzeć zapisy w arkuszu powiązane z umowami w zakresie zarządzania rabatami, należy wykonać następujące czynności.

1. Otwórz odpowiednią stronę [z listą umów rabatowych](rebate-management-deals.md) dla typu umowy, która ma być zawierana.
1. Wybierz umowę, dla których mają być sprawdzane zapisy w arkuszu.
1. W okienku akcji, na karcie **Zarządzanie rabatami — umowy**, w grupie **Transakcje** wybierz opcję **Transakcje** lub **Transakcje rabatów**, w zależności od typu transakcji, którą chcesz wyświetlić.
1. Upewnij się, że pole **Pokaż** ma wartość *Wszystkie* lub *Zaksięgowane*.
1. Znajdź i zaznacz kolekcję transakcji, którą chcesz sprawdzić, a następnie w okienku akcji wybierz jeden z poniższych przycisków. (Te przyciski są dostępne tylko wtedy, gdy dla wybranej kolekcji transakcji istnieją odpowiednie księgowania)

    - **Transakcje docelowe** – Przegląd odpowiednich arkuszy i innych typów dokumentów wygenerowanych przez wybraną umowę.
    - **Towary** — przegląd odpowiednich towarów wygenerowanych przez wybraną umowę.

1. Zostanie wyświetlona lista odpowiednich arkuszy, dokumentów lub towarów. Aby wyświetlić więcej informacji o dowolnym arkuszu, dokumencie lub towarze, należy wybrać jego wiersz, a następnie w okienku akcji wybrać polecenie **Wyświetl szczegóły**.
