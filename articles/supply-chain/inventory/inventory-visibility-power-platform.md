---
title: Aplikacja Widoczność magazynu
description: W tym artykule opisano sposób korzystania z aplikacji Widoczność magazynu.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: db158e3b6ae76f69149db04096f99d3dc4251146
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895765"
---
# <a name="use-the-inventory-visibility-app"></a>Używanie aplikacji Inventory Visibility

[!include [banner](../includes/banner.md)]


W tym artykule opisano sposób korzystania z aplikacji Widoczność magazynu.

Widoczność magazynu to aplikacja oparta na modelu służąca do wizualizacji. Aplikacja zawiera trzy strony: **Konfiguracja**, **Widoczność operacyjna** i **Podsumowanie zapasów**. Jej właściwości są następujące

- Zawiera interfejs użytkownika (UI) do konfigurowania rezerwacji dostępnych zapasów i konfigurowania rezerwacji wstępnej.
- Obsługuje zapytania o dostępne zapasy w czasie rzeczywistym dla różnych kombinacji wymiarów.
- Zawiera interfejs użytkownika do księgowania żądań rezerwacji.
- Zapewnia spersonalizowany widok dostępnych zapasów produktów wraz ze wszystkimi wymiarami.

## <a name="prerequisites"></a>Wymagania wstępne

Przed rozpoczęciem należy zainstalować i skonfigurować dodatek Widoczność zapasów w sposób opisany w temacie [Instalowanie i ustawianie dodatku Widoczność magazynu](inventory-visibility-setup.md).

## <a name="open-the-inventory-visibility-app"></a>Otwieranie aplikacji Widoczność magazynu

Aby otworzyć aplikację Widoczność magazynu, zaloguj się do środowiska Power Apps i otwórz aplikację **Widoczność magazynu**.

## <a name="configuration"></a><a name="configuration"></a>Konfiguracja

Strona **Konfiguracja** aplikacji Widoczność magazynu ułatwia skonfigurowanie dostępnych zapasów i rezerwacji wstępnej. Po zainstalowaniu tego dodatku domyślna konfiguracja obejmuje domyślne ustawienia z aplikacji Microsoft Dynamics 365 Supply Chain Management (źródło danych `fno`). Ustawienie domyślne można przejrzeć. Następnie na podstawie wymagań firmy oraz wymagań księgowania zapasów w zewnętrznym systemie można zmodyfikować konfigurację w celu standaryzacji sposobu, w jaki zmiany zapasów mogą być księgowane, organizowane i wyszukiwane w różnych systemach.

Aby uzyskać pełne informacje o konfigurowaniu rozwiązania, zobacz temat [Konfiguracja aplikacji Widoczność magazynu](inventory-visibility-configuration.md).

## <a name="operational-visibility"></a>Widoczność operacyjna

Strona **Widoczność operacyjna** zawiera wyniki zapytania o dostępne zapasy w czasie rzeczywistym oparte na różnych kombinacjach wymiarów. Po włączeniu funkcji *OnHandReservation* można również księgować żądania rezerwacji ze strony **Widoczność operacyjna**.

### <a name="on-hand-query"></a>Zapytanie o dostępne zapasy

Na karcie **Zapytanie o dostępne zapasy** są wyświetlane wyniki zapytania o dostępne zapasy w czasie rzeczywistym.

Po wybraniu karty **Zapytanie o dostępne zapasy** system żąda poświadczeń użytkownika, aby uzyskać token elementu nośnego wymagany do wykonywania zapytania w usłudze Widoczność magazynu. Token elementu nośnego można po prostu wkleić w polu **Token elementu nośnego** i zamknąć okno dialogowe. Następnie można zaksięgować żądanie zapytania o dostępne zapasy.

Jeśli token elementu nośnego jest nieprawidłowy lub wygasł, należy wkleić nowy w polu **Token elementu nośnego**. Wprowadź poprawne wartości w polach **Identyfikator klienta**, **Identyfikator dzierżawcy** i **Klucz tajny klienta**, a następnie wybierz opcję **Odśwież**. System automatycznie otrzyma nowy, prawidłowy token elementu nośnego.

Aby zaksięgować zapytanie o dostępne zapasy, wprowadź zapytanie w treści żądania. Użyj wzorca opisanego w temacie [Zapytanie przy użyciu metody księgowania](inventory-visibility-api.md#query-with-post-method).

![Ustawienia zapytania o dostępne zapasy](media/inventory-visibility-query-settings.png "Ustawienia zapytania o dostępne zapasy")

### <a name="reservation-posting"></a>Księgowanie rezerwacji

Użyj karty **Księgowanie rezerwacji**, aby zaksięgować żądanie rezerwacji. Aby można było zaksięgować żądanie rezerwacji, należy włączyć funkcję *OnHandReservation*. Więcej informacji na temat tej funkcji zawiera temat [Rezerwacje dodatku Widoczność zapasów](inventory-visibility-reservations.md).

Aby zaksięgować żądanie rezerwacji, musisz wprowadzić wartość w treści żądania. Użyj wzorca opisanego w temacie [Tworzenie jednego zdarzenia rezerwacji](inventory-visibility-api.md#create-one-reservation-event). Następnie kliknij przycisk **Zaksięguj**. Aby wyświetlić szczegóły odpowiedzi na żądanie, wybierz opcję **Pokaż szczegóły**. Wartość `reservationId` można odczytać również ze szczegółów odpowiedzi.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>Podsumowanie zapasów

**Podsumowanie zapasów** jest dostosowanym widokiem encji *Suma dostępnych zapasów*. Zawiera podsumowanie zapasów dla produktów wraz ze wszystkimi wymiarami. Dane podsumowujące stan zapasów są okresowo synchronizowane z narzędziem Widoczność magazynu co 15 minut. Aby wyświetlić dane na karcie **Podsumowanie zapasów**, należy włączyć funkcję *OnHandMostSpecificBackgroundService* na karcie **Zarządzanie funkcjami** i wybrać **Uaktualnij konfigurację**.

> [!NOTE]
> Funkcja *OnHandMostSpecificBackgroundService* śledzi tylko zmiany w dostępnych towarach, które wystąpiły po włączeniu tej funkcji. Dane produktów, które nie zostały zmienione od czasu włączeniu tej funkcji, nie będą synchronizowane z pamięci podręcznej usługi magazynowej do środowiska Dataverse. Jeśli strona **Podsumowanie zapasów** nie pokazuje wszystkich oczekiwanych informacji o stanie zapasów, przejdź do menu **Zarządzanie zapasami > Zadania okresowe > Integracja widoczności zapasów**, wyłącz zadanie wsadowe i włącz je ponownie. W ciągu najbliższych 15 minut wszystkie dane zostaną zsynchronizowane z jednostką *Łącznie dostępnych zapasów*. Jeśli chcesz korzystać z tej funkcji, zalecamy jej włączenie przed utworzeniem jakichkolwiek zmian w stanie inwentaryzacji oraz włączenie zadania wsadowego **Integracja widoczności zapasów**.

Korzystając z **filtru zaawansowanego** z Dataverse, można utworzyć osobisty widok, który pokazuje ważne dla użytkownika wiersze. Zaawansowane opcje filtrowania pozwalają na tworzenie szerokiego zakresu widoków, od prostych do złożonych. Umożliwiają one również dodawanie grupowanych i zagnieżdżonych warunków do filtrów. Aby dowiedzieć się więcej o używaniu **filtru zaawansowanego**, zobacz temat [Edytowanie lub tworzenie widoków osobistych przy użyciu zaawansowanych filtrów siatki](/powerapps/user/grid-filters-advanced).

W górnej części dostosowanego widoku są trzy pola: **Wymiar domyślny**, **Wymiar niestandardowy** i **Miara**. Za pomocą tych pól można kontrolować, które kolumny są widoczne.

Możesz wybrać nagłówek kolumny, aby filtrować lub sortować bieżący wynik.

W dolnej części niestandardowego widoku są wyświetlane informacje, jak „50 rekordów (wybrano 29)” lub „50 rekordów” Te informacje odnoszą się do aktualnie załadowanych rekordów z wyniku **filtru zaawansowanego**. Tekst „Wybrano 29” oznacza liczbę rekordów wybranych za pomocą filtru nagłówka kolumny dla ładowanych rekordów.

W dolnej części widoku znajduje się przycisk **Załaduj więcej**, który umożliwia załadowanie większej liczby rekordów z Dataverse. Domyślna liczba ładowanych rekordów wynosi 50. W przypadku wybrania opcji **Załaduj więcej** do widoku zostanie załadowanych następnych 1000 dostępnych rekordów. Liczba na przycisku **Załaduj więcej** wskazuje aktualnie załadowane rekordy oraz łączną liczbę rekordów dla wyniku **filtru zaawansowanego**.

![Podsumowanie zapasów](media/inventory-visibility-onhand-list.png "Podsumowanie zapasów")
