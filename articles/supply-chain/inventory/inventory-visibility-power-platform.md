---
title: Aplikacja Widoczność magazynu
description: W tym artykule opisano sposób korzystania z aplikacji Widoczność magazynu.
author: yufeihuang
ms.date: 09/15/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0a4e436cc1af6b71049f75fb66bdfb89ca38df9f
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831782"
---
# <a name="use-the-inventory-visibility-app"></a>Używanie aplikacji Inventory Visibility

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób korzystania z aplikacji Widoczność magazynu.

Widoczność magazynu to aplikacja oparta na modelu służąca do wizualizacji. Aplikacja zawiera trzy strony: **Konfiguracja**, **Widoczność operacyjna** i **Podsumowanie zapasów**. Jej właściwości są następujące

- Zawiera interfejs użytkownika (UI) do konfigurowania rezerwacji dostępnych zapasów i konfigurowania rezerwacji wstępnej.
- Obsługuje zapytania o dostępne zapasy w czasie rzeczywistym dla różnych kombinacji wymiarów.
- Zawiera interfejs użytkownika do księgowania żądań rezerwacji.
- Zapewnia widok dostępnych zapasów produktów wraz ze wszystkimi wymiarami.
- Zapewnia widok listy dostępnych zapasów produktów wraz ze wstępnie zdefiniowanymi wymiarami. Widok dostępnej listy może być pełnym podsumowaniem lub wstępnie załadowanym wynikiem dostępnego zapytania.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem należy zainstalować i skonfigurować dodatek Widoczność zapasów w sposób opisany w temacie [Instalowanie i ustawianie dodatku Widoczność magazynu](inventory-visibility-setup.md).

## <a name="open-and-authenticate-the-inventory-visibility-app"></a><a name="open-authenticate"></a>Otwieranie i uwierzytelnianie aplikacji Widoczność zapasów

Aby otworzyć i uwierzytelnić aplikację Widoczność zapasów, wykonaj następujące kroki.

1. Zaloguj się do swojego środowiska Power Apps.
1. Otwieranie aplikacji **Widoczność magazynu**.
1. Otwórz stronę **Widoczność operacyjną** z lewego okienka.
1. Kliknij przycisk **Ustawienia** (symbol koła zębatego) w prawym górnym rogu strony.
1. W oknie dialogowym **Ustawienia** wprowadź **identyfikator klienta**, **identyfikator dzierżawy** i **tajny klucz klienta**, [które zostały odnotowane podczas instalacji i skonfigurowania widoczności zapasów](inventory-visibility-setup.md).
1. Wybierz przycisk **Odśwież** obok **pola Token okaziciela**. Na podstawie wprowadzonych informacji system wygeneruje nowy token na okaziciela.

    ![Ustawienia zapytania o dostępne zapasy.](media/inventory-visibility-query-settings.png "Ustawienia zapytania o dostępne zapasy")

1. Po otrzymaniu prawidłowego tokenu na okaziciela zamknij okno dialogowe. Token na okaziciela wygaśnie za jakiś czas. Dlatego konieczne jest sporadycznie odświeżenie danych, gdy konieczne jest aktualizowanie konfiguracji, księgować dane lub kwerendy.

## <a name="configure-the-inventory-visibility-app"></a><a name="configuration"></a>Skonfiguruj aplikację Widoczność magazynu

Strona **Konfiguracja** aplikacji Widoczność magazynu pomaga skonfigurować ogólną konfigurację zarządzania danymi i konfigurację funkcji. Po zainstalowaniu tego dodatku domyślna konfiguracja obejmuje domyślne ustawienia z aplikacji Microsoft Dynamics 365 Supply Chain Management (źródło danych `fno`). Ustawienie domyślne można przejrzeć. Następnie na podstawie wymagań firmy oraz wymagań księgowania zapasów w zewnętrznym systemie można zmodyfikować konfigurację w celu standaryzacji sposobu, w jaki zmiany zapasów mogą być księgowane, organizowane i wyszukiwane w różnych systemach.

Aby uzyskać pełne informacje o konfigurowaniu rozwiązania, zobacz temat [Konfiguracja aplikacji Widoczność magazynu](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Widoczność operacyjna

Strona **Widoczność operacyjna** zawiera wyniki kwerendy dostępnych zapasów w czasie rzeczywistym, księgowania rezerwacji i alokacji w oparciu o różne kombinacje wymiarów. Po [włączeniu](inventory-visibility-configuration.md) funkcji *OnHandReservation* można również księgować żądania rezerwacji ze strony **Widoczność operacyjna**.

### <a name="on-hand-query"></a>Zapytanie o dostępne zapasy

Karta **Obecne zapytanie** na stronie **Widoczność operacyjna** umożliwia wysyłanie zapytań o dostępne zapasy w czasie rzeczywistym. Wykonaj poniższe kroki, aby skonfigurować i uruchomić zapytanie.

1. Otwieranie aplikacji **Widoczność magazynu**.
1. Otwórz stronę **Widoczność operacyjną** z lewego okienka.
1. Na karcie **Zapytanie bieżące** wprowadź wartości **Identyfikator organizacji**, **Identyfikator witryny** i **Identyfikator lokalizacji**, o które chcesz zapytać.
1. W polu **Identyfikator produktu** wprowadź jeden lub więcej identyfikatorów produktów, aby dokładnie dopasować je do kwerendy. Jeśli pole Identyfikator **produktu jest** puste, zostaną w nich wymienione wszystkie produkty w określonej lokalizacji i w określonej lokalizacji.
1. Aby uzyskać bardziej szczegółowych wyników (na przykład: widok według wartości wymiarów, takich jak kolor i rozmiar), wybierz wymiary grupuj według w polu **Wynik grupy według**.
1. Aby znaleźć towary o określonej wartości wymiaru (np. kolor = czerwony), wybierz wymiar w polu **Filtruj wymiary**, a następnie wprowadź wartość wymiaru.
1. Wybierz **kwerendę**. Zostanie wyświetlony komunikat o błędzie (zielony) lub komunikat o błędzie (czerwony). Jeśli kwerenda nie powiedzie się, sprawdź kryteria kwerendy i upewnij się, [że token okaziciela](#open-authenticate) nie wygasł.

Innym sposobem wykonywania kwerendy są bezpośrednie żądania interfejsu API. Można użyć `/api/environment/{environmentId}/onhand/indexquery` albo `/api/environment/{environmentId}/onhand`. Więcej informacji zawiera temat [Publiczne interfejsy API widoczności zasobów reklamowych](inventory-visibility-api.md).

### <a name="reservation-posting"></a>Księgowanie rezerwacji

Użyj karty **Księgowanie rezerwacji** strony **Widoczność operacyjna**, aby zaksięgować żądanie rezerwacji. Aby można było zaksięgować żądanie rezerwacji, należy włączyć funkcję *OnHandReservation*. Więcej informacji na temat tej funkcji i jak ją włączyć zawiera temat [Rezerwacje dodatku Widoczność zapasów](inventory-visibility-reservations.md).

> [!NOTE]
> Możliwość dokonywania rezerwacji programowej za pomocą interfejsu użytkownika jest przeznaczona do testowania funkcji. Każdy wniosek o rezerwację programową powinien być skojarzony ze zmianą wiersza zamówienia transakcji (tworzenie, modyfikowanie, usuwanie itd.). Dlatego zaleca się, aby dokonać tylko rezerwacji miękkich, które są połączone z zamówieniem za back-end. Więcej informacji zawiera temat [Rezerwacje dodatku Widoczność magazynu](inventory-visibility-reservations.md).

Aby zakłać wniosek o rezerwację programną za pomocą interfejsu użytkownika, należy wykonać następujące kroki.

1. Otwieranie aplikacji **Widoczność magazynu**.
1. Otwórz stronę **Widoczność operacyjną** z lewego okienka.
1. Na karcie **Księgowanie rezerwacji** w polu **Ilość** określ ilość, która ma zostać zarezerwowana wcześniej.
1. Wyczyść pole wyboru **Włącz ujemny stan** magazynu, aby zapobiec nadsprzedarzeniu lub zarezerwowaniu zapasów.
1. W polu **Operator** wybierz źródło danych i miarę fizyczną, które mają zastosowanie do ilości zarezerwowanej programowo.
1. Wprowadź wartości **Identyfikator organizacji**, **Identyfikator witryny**, **Identyfikator lokalizacji** i **Identyfikator produktu**, o które chcesz zapytać.
1. Aby uzyskać bardziej szczegółowych wyników, wybierz źródło danych, wymiary i wartości wymiarów.

Innym sposobem zaksięgowania rezerwacji programowej jest bezpośrednie żądania interfejsu API. Użyj wzorca opisanego w temacie [Tworzenie jednego zdarzenia rezerwacji](inventory-visibility-api.md#create-one-reservation-event). Następnie kliknij przycisk **Zaksięguj**. Aby wyświetlić szczegóły odpowiedzi na żądanie, wybierz opcję **Pokaż szczegóły**. Wartość `reservationId` można odczytać również ze szczegółów odpowiedzi.

### <a name="allocation"></a>Alokacja

Aby uzyskać informacje dotyczące zarządzania alokacjami z interfejsu użytkownika i interfejsów API, zobacz alokacje [zapasów widoczności zapasów](inventory-visibility-allocation.md).

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Podsumowanie zapasów

Strona **Podsumowanie zapasów** zapewnia podsumowanie zapasów produktów wraz ze wszystkimi wymiarami. Jest dostosowanym widokiem encji *Łącznie dostępnych zapasów*. Podsumowanie zapasów będzie okresowo synchronizowane z Widocznością magazynu.

Aby włączyć stronę **Podsumowanie zapasów** i ustawić częstotliwość synchronizacji, wykonaj poniższe kroki:

1. Otwórz stronę **Konfiguracja**.
1. Otwórz kartę **Zarządzanie funkcjami i ustawienia**.
1. Ustaw przełącznik dla funkcji *OnHandMostSpecificBackgroundService* na wartość *Tak*.
1. Gdy ta funkcja jest włączona, sekcja **Konfiguracja usługi** staje się dostępna i zawiera wiersz do konfigurowania usługi **OnHandMostSpecificBackgroundService**. To ustawienie umożliwia wybranie częstotliwości synchronizacji danych zbiorczych zapasów. Przyciski **W górę** i **W dół** w kolumnie **Wartość** umożliwiają zmianę czasu między synchronizacjami (czas do 5 minut). Następnie kliknij przycisk **Zapisz**.

    ![Ustawienie OnHandMostSpecificBackgroundService](media/inventory-visibility-ohms-freq.png "Ustawienie OnHandMostSpecificBackgroundService")

1. Wybierz opcję **Aktualizuj konfigurację**, aby zapisać wszystkie zmiany.

> [!NOTE]
> Funkcja *OnHandMostSpecificBackgroundService* śledzi tylko zmiany w dostępnych zapasach, które wystąpiły po włączeniu tej funkcji. Dane produktów, które nie zostały zmienione od czasu włączeniu tej funkcji, nie będą synchronizowane z pamięci podręcznej usługi magazynowej do środowiska Dataverse. Jeśli strona **Podsumowanie zapasów** nie pokazuje wszystkich oczekiwanych informacji o stanie zapasów, otwórz rozwiązanie Supply Chain Management, przejdź do menu **Zarządzanie zapasami > Zadania okresowe > Integracja widoczności zapasów**, wyłącz zadanie wsadowe i włącz je ponownie. W ciągu najbliższych 15 minut wszystkie dane zostaną zsynchronizowane z jednostką *Łącznie dostępnych zapasów*. Jeśli chcesz korzystać z funkcji *OnHandMostSpecificBackgroundService*, zalecamy jej włączenie przed utworzeniem jakichkolwiek zmian w stanie inwentaryzacji oraz włączenie zadania wsadowego **Integracja widoczności zapasów**.

## <a name="preload-a-streamlined-on-hand-query"></a><a name="preload-streamlined-onhand-query"></a>Wstępnie załaduj ujednolicone zapytanie dostępnych zapasów

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: Preview until further notice -->

W rozwiązaniu Supply Chain Management przechowywanych jest wiele informacji o bieżących dostępnych zapasach i udostępnia je ono do różnych celów. Jednak wiele codziennych operacji i integracji innych firm wymaga jedynie małych podzestawów tych szczegółów, a zapytania systemowe dla wszystkich tych elementów mogą spowodować tworzenie dużych zestawów danych, które czas wymagają połączenia i przeniesienia. Dzięki temu usługa widoczności zapasów może okresowo pobierać i przechowywać ujednolicony zestaw dostępnych danych magazynowych, co zapewnia ciągły dostęp do zoptymalizowanych informacji. Przechowywane szczegóły dotyczące dostępnych zapasów są filtrowane na podstawie konfigurowalnych kryteriów biznesowych, aby zagwarantować, że będą uwzględniane tylko najważniejsze informacje. Ponieważ filtrowane listy dostępnych zapasów są przechowywane lokalnie w usłudze widoczności magazynu i są regularnie aktualizowane, obsługują szybki dostęp, eksport danych na żądanie oraz lepszej integracji z systemami zewnętrznymi.

Strona **Wstępne załadowanie podsumowania widoczności magazynu** zawiera widok jednostki *Wyniki wstępnego ładowania zapytania indeksu dostępnych zapasów*. W przeciwieństwie do jednostki *Podsumowanie zapasów*, jednostka *Wyniki wstępnego ładowania zapytania indeksu dostępnych zapasów* zawiera listę dostępnych zapasów produktów wraz z wybranymi wymiarami. Widoczność magazynu synchronizuje wstępnie załadowane dane zbiorcze co 15 minut.

Aby wyświetlić dane na zakładce **Wstępne załadowanie podsumowania widoczności zapasów**, musisz włączyć i skonfigurować funkcję *OnHandIndexQueryPreloadBackgroundService*. Patrz [Włączanie i konfigurowanie wstępnie załadowanych zapytań z ręki](inventory-visibility-configuration.md#query-preload-configuration) , aby uzyskać instrukcje.

> [!NOTE]
> Podobnie jak w przypadku funkcji *OnHandMostSpecificBackgroundService*, funkcja *OnHandIndexQueryPreloadBackgroundService* śledzi tylko zmiany dostępnych zapasów, które wystąpiły po włączeniu tej funkcji. Dane produktów, które nie zostały zmienione od czasu włączeniu tej funkcji, nie będą synchronizowane z pamięci podręcznej usługi magazynowej do środowiska Dataverse. Jeśli strona **Podsumowanie zapasów** nie pokazuje wszystkich oczekiwanych informacji o stanie zapasów, przejdź do menu **Zarządzanie zapasami > Zadania okresowe > Integracja widoczności zapasów**, wyłącz zadanie wsadowe i włącz je ponownie. W ciągu najbliższych 15 minut wszystkie dane zostaną zsynchronizowane z jednostką *Wyniki wstępnego ładowania zapytania indeksu dostępnych zapasów*. Jeśli chcesz korzystać z tej funkcji, zalecamy jej włączenie przed utworzeniem jakichkolwiek zmian w stanie inwentaryzacji oraz włączenie zadania wsadowego **Integracja widoczności zapasów**.

## <a name="filter-and-browse-the-inventory-summaries"></a><a name="additional-tip-for-viewing-data"></a>Filtrowanie i przeglądanie podsumowań zapasów

Korzystając z **filtru zaawansowanego** z Dataverse, można utworzyć osobisty widok, który pokazuje ważne dla użytkownika wiersze. Zaawansowane opcje filtrowania pozwalają na tworzenie szerokiego zakresu widoków, od prostych do złożonych. Umożliwiają one również dodawanie grupowanych i zagnieżdżonych warunków do filtrów. Aby dowiedzieć się więcej o używaniu filtru zaawansowanego, zobacz temat [Edytowanie lub tworzenie widoków osobistych przy użyciu zaawansowanych filtrów siatki](/powerapps/user/grid-filters-advanced).

Strona **Podsumowanie zapasów** zawiera trzy pola powyżej siatki (**Wymiar domyślny**, **Wymiar niestandardowy** i **Miara**), których można użyć do kontrolowania widocznych kolumn. Możesz również wybrać którykolwiek nagłówek kolumny, aby filtrować lub sortować bieżący wynik według tej kolumny. Poniższy zrzut ekranu wyróżnia pola wymiaru, filtrowania, liczby wyników i „załaduj więcej” dostępne na stronie **Podsumowanie zapasów**.

![Strona Podsumowanie zapasów.](media/inventory-visibility-onhand-list.png "Strona Podsumowanie zapasów")

Ponieważ będziesz mieć wstępnie zdefiniowane wymiary używane do ładowania danych zbiorczych, na stronie **Wstępne załadowanie podsumowania widoczności magazynu** są wyświetlane kolumny powiązane z wymiarami. *Wymiary nie mogą być dostosowywane &mdash; system obsługuje tylko wymiary lokalizacji i lokalizacji dla wstępnie załadowanych list dostępnych zapasów.* Na stronie **Podsumowanie widoczności zapasów** znajdują się filtry podobne do filtrów widocznych na stronie **Podsumowanie zapasów** z wyjątkiem już wybranych wymiarów. Poniższy zrzut ekranu wyróżnia pola filtrowania dostępne na stronie **Wstępne załadowanie podsumowania widoczności magazynu**.

![Strona Wstępne załadowanie podsumowania widoczności magazynu.](media/inventory-visibility-preload-onhand-list.png "Strona Wstępne załadowanie podsumowania widoczności magazynu")

W dolnej części strony **Wstępne załadowanie podsumowania widoczności magazynu** oraz strony **Podsumowanie zapasów** znajdują się informacje, takie jak „50 rekordów (wybrano 29 rekordów)” lub „50 rekordów”. Te informacje odnoszą się do aktualnie załadowanych rekordów z wyniku **filtru zaawansowanego**. Tekst „Wybrano 29” oznacza liczbę rekordów wybranych za pomocą filtru nagłówka kolumny dla ładowanych rekordów. W dolnej części widoku znajduje się także przycisk **Załaduj więcej**, który umożliwia załadowanie większej liczby rekordów z Dataverse. Domyślna liczba ładowanych rekordów to 50. W przypadku wybrania opcji **Załaduj więcej** do widoku zostanie załadowanych następnych 1000 dostępnych rekordów. Liczba na przycisku **Załaduj więcej** wskazuje aktualnie załadowane rekordy oraz łączną liczbę rekordów dla wyniku **filtru zaawansowanego**.
