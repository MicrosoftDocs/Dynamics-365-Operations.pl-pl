---
title: Konfiguracja obejść dla kroków w elementach menu urządzeń mobilnych
description: W tym artykule opisano sposób konfigurowania obejść dla pozycji menu, tak aby pracownicy mogli przerwać bieżące zadanie, wykonać inne zadanie, a następnie powrócić do pierwotnego zadania bez utraty jakichkolwiek informacji.
author: Mirzaab
ms.date: 09/01/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage, WHSMobileAppFlowStepAddDetour, WHSMobileAppFlowStepDetourSelectFields, WHSMobileAppFlowStepSelectPromotedFields
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2e387dd4e6499912f2d53dddc17ccc053f1ca699
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689318"
---
# <a name="configure-detours-for-steps-in-mobile-device-menu-items"></a>Konfiguracja obejść dla kroków w elementach menu urządzeń mobilnych

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 10.0.31 GA -->

> [!IMPORTANT]
> Funkcje opisane w tym artykule dotyczą tylko nowej aplikacji mobilnej Warehouse Management. Nie wpływają one na starą aplikację magazynu, która jest obecnie przestarzała.

W tym artykule opisano sposób konfigurowania obejść dla pozycji menu, tak aby pracownicy mogli przerwać bieżące zadanie, wykonać inne zadanie, a następnie powrócić do pierwotnego zadania bez utraty jakichkolwiek informacji.

Obejście to osobna pozycja menu, którą można otworzyć z kroku zadania głównego. Po zakończeniu obejścia pracownik wraca do miejsca, w którym opuścił główne zadanie. Podczas konfiguracji należy określić pozycję menu, która ma pełnić funkcję obejścia. Wybierasz również, które wartości pól z zadania głównego mają być automatycznie przekazywane (kopiowane) do obejścia i tam wprowadzane. Dlatego musisz zrozumieć, w którym miejscu przepływu zadań chcesz, aby obejście było dostępne dla pracowników. Należy również upewnić się, że informacje, które muszą być skopiowane do obejścia, są dostępne dla tego kroku przepływu zadań.

## <a name="enable-detours-in-your-system"></a>Włącz obejścia w swoim systemie

Zanim będzie można skonfigurować obejścia dla kroków w pozycjach menu urządzenia mobilnego, należy wykonać poniższą procedurę, aby włączyć wymagane funkcje i wygenerować wymagane nazwy pól w aplikacji mobilnej Warehouse Management.

1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
1. Upewnij się, że funkcja *Instrukcje kroku aplikacji magazynowej* jest włączona w Twoim systemie. Od wersji 10.0.29 Supply Chain Management version ta funkcja jest domyślnie włączona. Aby uzyskać więcej informacji na temat funkcji *Instrukcje krok po kroku aplikacji Warehouse*, patrz [Dostosowywanie tytułów i instrukcji krok po kroku dla aplikacji mobilnej Warehouse Management](mobile-app-titles-instructions.md). Ta funkcja jest warunkiem koniecznym dla funkcji *Obejścia aplikacji zarządzania magazynem*.
1. Włącz następujące funkcje, które zapewniają funkcje opisane w tym artykule:
    - *Przełączanie aplikacji Warehouse Management*<br>(Od wersji 10.0.29 Supply Chain Management version ta funkcja jest domyślnie włączona)
    - *Wielopoziomowe przekierowanie dla aplikacji mobilnej Warehouse Management*
    - *Automatycznie przesyłaj kroki przekierowania dla aplikacji mobilnej Warehouse Management*
1. Jeśli funkcje *Objazdy aplikacji do zarządzania magazynem* i/lub *Wielopoziomowe przekierowanie dla aplikacji mobilnej Warehouse Management* nie były jeszcze włączone, zaktualizuj nazwy pól w aplikacji mobilnej Warehouse Management, przechodząc do **Zarządzanie magazynem \> Konfiguracja \> Urządzenie mobilne \> Nazwy pól aplikacji Warehouse** i wybierając **Utwórz konfigurację domyślną**. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie pól aplikacji mobilnej Warehouse Management](configure-app-field-names-priorities-warehouse.md).
1. Powtórz poprzedni krok dla każdej osoby prawnej (firmy), w której korzystasz z aplikacji mobilnej Warehouse Management.

## <a name="configure-a-detour-from-a-menu-specific-override"></a>Konfiguracja obejścia na podstawie wymuszenia określonego w menu

Aby skonfigurować obejście na podstawie wymuszenia określonego w menu, należy skorzystać z poniższej procedury.

1. Utworzyć nadpisanie dla danego menu i kroku zgodnie z opisem w punkcie [Dostosowywanie tytułów kroków i instrukcji dla aplikacji mobilnej Warehouse Management](mobile-app-titles-instructions.md).
1. Znajdź kombinację wartości **Identyfikator kroku** i **Nazwa opcji menu**, które chcesz edytować, i wybierz wartość w kolumnie **Identyfikator kroku**.
1. Na stronie, która się pojawi, na skróconej karcie **Dostępne obejścia (pozycje menu)**, można określić pozycję menu, która powinna działać jako obejścia. Możesz także wybrać, które wartości pól z zadania głównego powinny być automatycznie kopiowane do i z obejścia. Przykłady pokazujące, jak korzystać z tych ustawień, można znaleźć w scenariuszach w dalszej części tego artykułu.

## <a name="sample-scenario-1-sales-picking-where-a-location-inquiry-acts-as-a-detour"></a><a name="scenario-1"></a>Przykładowy scenariusz 1: Kompletacja sprzedaży, w której zapytanie o lokalizację pełni rolę obejścia

Ten scenariusz pokazuje, jak skonfigurować zapytanie o lokalizację jako obejście w przepływie zadań kompletacji sprzedaży kierowanej przez pracownika. To obejście umożliwi pracownikom sprawdzenie wszystkich numerów identyfikacyjnych w miejscu, z którego dokonują odbioru i wybranie numeru identyfikacyjnego, który chcą użyć do zakończenia odbioru. Ten rodzaj obejścia może być przydatny, jeśli kod kreskowy jest uszkodzony i dlatego nie może być odczytany przez urządzenie skanujące. Alternatywnie, może być przydatna, gdy pracownik musi dowiedzieć się, co jest aktualnie dostępne w systemie. Zauważ, że ten scenariusz działa tylko wtedy, gdy wybierasz z miejsc kontrolowanych przez numery identyfikacyjne.

### <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby użyć określonych przykładowych rekordów i wartości do pracy z tym scenariuszem, musisz używać systemu, w którym zainstalowane są standardowe [dane demo](../../fin-ops-core/fin-ops/get-started/demo-data.md). Należy również wybrać firmę **USMF** przed rozpoczęciem.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-1"></a>Utwórz specyficzne dla menu nadpisanie i skonfiguruj obejście dla scenariusza 1

W tej procedurze zostanie skonfigurowane obejście dla elementu menu **Pobieranie sprzedaży** w kroku numeru identyfikacyjnego.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Kroki urządzenia przenośnego**.
1. Znajdź identyfikator kroku o nazwie *LicensePlateId* i zaznacz go.
1. W okienku akcji wybierz pozycję **Dodaj konfigurację kroku**.
1. W rozwijanym oknie dialogowym użyj pola **Element menu**, aby znaleźć i wybrać *Pobieranie z Sales*.
1. Kliknij przycisk **OK**.
1. Pojawia się strona szczegółów dla właśnie utworzonego zastępstwa. Na skróconej karcie **Dostępne obejścia (pozycje menu)**, wybierz **Dodaj** na pasku narzędzi.
1. W oknie dialogowym **Dodaj obejście** należy wybrać **Zapytanie o lokalizację** jako obejście, który zostanie udostępnione w aplikacji mobilnej Warehouse Management.
1. Kliknij przycisk **OK**.
1. Na skróconej karcie **Dostępne obejścia (pozycje menu)**, wybierz obejście, który właśnie dodałeś, a następnie wybierz **Wybierz pola do wysłania** na pasku narzędzi.
1. W oknie dialogowym **Wybierz pola do wysłania**, określ informacje, które mają być wysyłane do i z obejścia. W tym scenariuszu umożliwiasz pracownikom wykorzystanie lokalizacji, z której mają pobierać, jako danych wejściowych dla obejścia z zapytaniem o lokalizację. W związku z tym w sekcji **Wyślij z pobrania z Sales** wybierz pozycję **Dodaj** na pasku narzędzi, aby dodać wiersz do siatki. Następnie należy ustawić następujące wartości dla nowego wiersza:

    - **Kopiowanie z pobierania z Sales:** *Lokalizacja*
    - **Wklej zapytanie o lokalizację:** *Lokalizacja*
    - **Automatyczne przesyłanie:** opcja *zaznaczona* (strona zostanie odświeżona przy użyciu wklejonej wartości *Lokalizacja*)

1. Ponieważ obejście w tym scenariuszu jest skonfigurowane na kroku numeru identyfikacyjnego, przydatne będzie, jeśli pracownicy będą mogli przenieść numer identyfikacyjny z zapytania z powrotem do głównego przepływu. W związku z tym w sekcji **Sprowadzenie z zapytania o lokalizację** wybierz pozycję **Dodaj** na pasku narzędzi, aby dodać wiersz do siatki. Następnie należy ustawić następujące wartości dla nowego wiersza:

    - **Kopia z zapytania o lokalizację:** *numer identyfikacyjny*
    - **Wklej do pobierania z Sales:** *numer identyfikacyjny*
    - **Automatyczne przesyłanie:** opcja *wyczyszczona* (automatyczna aktualizacja nie będzie przeprowadzana podczas zwracania z obejścia z wartością *Numer identyfikacyjny*)

1. Kliknij przycisk **OK**.

Obejście jest teraz w pełni skonfigurowane. Przycisk uruchamiający obejście **Zapytanie o lokalizację** pojawi się teraz na kroku numeru identyfikacyjnego dla pozycji menu **Pobieranie z Sales**.

### <a name="complete-a-sales-pick-on-a-mobile-device-and-use-the-detour"></a>Dokonaj pobranie sprzedaży na urządzeniu mobilnym i skorzystaj z obejścia

W ramach tej procedury wykonasz pobieranie sprzedaży za pomocą aplikacji mobilnej Warehouse Management. Skorzystasz z właśnie skonfigurowanego obejścia, aby znaleźć numer identyfikacyjny, którego użyjesz, aby zakończyć krok pobierania.

1. W Microsoft Dynamics 365 Supply Chain Management utwórz zamówienie sprzedaży, które będzie wymagało kroku kompletacji w celu pobrania z lokalizacji, która jest śledzona na podstawie tablic rejestracyjnych. Teraz wydaj zamówienie sprzedaży do magazynu. Zanotuj pokazany identyfikator pracy.
1. Zaloguj się do aplikacji Warehouse Management jako użytkownik w magazynie 24. (W standardowych danych demonstracyjnych zaloguj się, używając *24* jako identyfikatora użytkownika i *1* jako hasła.)
1. Wybierz menu **Wychodzące**, a następnie wybierz element menu **Pobranie z Sales**.
1. Postępuj zgodnie z instrukcjami wprowadzania danych na ekranie, aby wprowadzić identyfikator pracy, który został wygenerowany w kroku 1.
1. W kroku, który zawiera tekst **Skanuj numer identyfikacyjny**, otwórz menu akcje. Powinien zostać wyświetlony nowy przycisk o etykiecie **Zapytanie o lokalizację**. Strzałka w lewym górnym rogu oznacza, że przycisk rozpocznie obejście. Wybierz **Zapytanie o lokalizację**.
1. Obejście zostało rozpoczęte. Na następnej stronie potwierdź lokalizację skopiowaną z głównego przepływu.
1. Na liście dostępnych numerów identyfikacyjnych w lokalizacji naciśnij numer identyfikacyjny, który chcesz skopiować z powrotem do głównego przepływu. Następnie wybierz przycisk **Wstecz**.
1. Wracasz do głównego przepływu pobierania sprzedaży, a numer identyfikacyjny został skopiowany z powrotem do niego z obejścia. Potwierdzić wartość, aby przejść do następnego kroku.
1. Teraz można wykonać pozostałą część standardowego przepływu, wprowadzając wymagane instrukcje wprowadzania danych.

Prace magazynowe zostały już zakończone. Pracownik z powodzeniem otworzył obejście, aby wykonać zadanie dodatkowe (zapytanie o lokalizację), nie tracąc miejsca w zadaniu głównym, i przyniósł z powrotem informacje, które były wymagane do ukończenia zadania głównego.

## <a name="sample-scenario-2-item-inquiry-with-movement-and-adjustment-detours"></a>Przykładowy scenariusz 2: Zapytanie o pozycję z obejściem i dostosowaniem

Ten scenariusz pokazuje, jak skonfigurować ruch i korekty jako wielokrotne obejścia w przepływie zadań zapytania o lokalizację. Ta możliwość może być przydatna w sytuacjach, gdy pracownik przybywa do danej lokalizacji, stwierdza, że stan zapasów w danej lokalizacji różni się od tego, co jest zarejestrowane w systemie, i dlatego musi dostosować lub przenieść towary.

W zależności od potrzeb zapytanie o lokalizację można zastąpić zapytaniem o numer identyfikacyjny lub zapytaniem o przedmiot.

### <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby użyć określonych przykładowych rekordów i wartości do pracy z tym scenariuszem, musisz używać systemu, w którym zainstalowane są standardowe [dane demo](../../fin-ops-core/fin-ops/get-started/demo-data.md). Należy również wybrać firmę **USMF** przed rozpoczęciem.

### <a name="create-a-menu-specific-override-and-configure-the-detour-for-scenario-2"></a>Utwórz specyficzne dla menu nadpisanie i skonfiguruj obejście dla scenariusza 2

W tej procedurze zostanie skonfigurowane obejście dla elementu menu **Pobieranie sprzedaży** w kroku numeru identyfikacyjnego.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Kroki urządzenia przenośnego**.
1. Znajdź identyfikator kroku o nazwie *LocationInquiryList* i zaznacz go.

    > [!NOTE]
    > Aby użyć zapytania o przedmiot zamiast zapytania o lokalizację, wybierz wiersz, w którym ID kroku ma nazwę *ItemInquiryList*. Aby użyć zapytania o numery identyfikacyjne, należy wybrać wiersz, w którym identyfikator kroku nosi nazwę *LPInquiryList*.

1. W okienku akcji wybierz pozycję **Dodaj konfigurację kroku**.
1. W rozwijanym oknie dialogowym użyj pola **Element menu**, aby znaleźć i wybrać *Zapytanie o lokalizację*.
1. Kliknij przycisk **OK**.
1. Pojawia się strona szczegółów dla właśnie utworzonego zastępstwa. Na skróconej karcie **Dostępne obejścia (pozycje menu)**, wybierz **Dodaj** na pasku narzędzi.
1. W oknie dialogowym **Dodaj obejście** należy wybrać **Ruch** jako obejście, które zostanie udostępnione w aplikacji mobilnej Warehouse Management.
1. Kliknij przycisk **OK**.
1. Na skróconej karcie **Dostępne obejścia (pozycje menu)**, wybierz obejście, który właśnie dodałeś, a następnie wybierz **Wybierz pola do wysłania** na pasku narzędzi.
1. W oknie dialogowym **Wybierz pola do wysłania**, określ informacje, które mają być wysyłane do i z obejścia. W tym scenariuszu oczekujesz od pracowników, że będą szukać miejsc z numerami identyfikacyjnymi. Dlatego pomocne będzie skopiowanie numeru identyfikacyjnego z zapytania obejścia **Ruch**. W sekcji **Wyślij z pobrania z Sales** wybierz pozycję **Dodaj** na pasku narzędzi, aby dodać wiersz do siatki. Następnie należy ustawić następujące wartości dla nowego wiersza:

    - **Kopiuj z zapytania o lokalizację:** *Lokalizacja*
    - **Wklej do Ruchu:** *Loc/LP*
    - **Automatyczne przesyłanie:** opcja *wyczyszczona* (automatyczna aktualizacja nie będzie przeprowadzana)

    W tym obejściu nie oczekujesz, że jakiekolwiek informacje zostaną skopiowane z powrotem, ponieważ główny przepływ był zapytaniem, w którym nie są wymagane żadne dodatkowe kroki.

1. Kliknij przycisk **OK**.

Obejście jest teraz w pełni skonfigurowane. Przycisk uruchamiający obejście **Ruch** pojawi się teraz na kroku numeru identyfikacyjnego dla pozycji menu **Zapytanie o lokalizację**.

### <a name="do-a-location-inquiry-on-a-mobile-device-and-use-the-detour"></a>Wykonaj zapytanie o lokalizację na urządzeniu mobilnym i skorzystaj z obejścia

W tej procedurze wykonasz zapytanie o lokalizację za pomocą aplikacji mobilnej Warehouse Management. Następnie wykorzystasz obejście do ukończenia ruchu towarów.

1. Zaloguj się do aplikacji Warehouse Management jako użytkownik w magazynie 24. (W standardowych danych demonstracyjnych zaloguj się, używając *24* jako identyfikatora użytkownika i *1* jako hasła.)
1. Wybierz menu **Zapasy**, a następnie wybierz element menu **Zapytanie o lokalizację**.
1. Wprowadź lokalizację, o którą chcesz zapytać, np. *FL-001*.
1. Gdy pojawi się lista, dotknij i przytrzymaj jedną z kart, aby wyświetlić dostępne obejścia.
1. Wybierz **Ruch**.
1. Zauważ, że numer identyfikacyjny został skopiowany z wybranej karty. Potwierdź wartość.
1. Możesz teraz wykonać standardowy przepływ zadań, aby zakończyć ruch. Po zakończeniu pracy otwórz menu akcji i wybierz polecenie **Anuluj**.
1. Wróć do strony **zapytania o lokalizację**. Należy zauważyć, że wartości nie są automatycznie aktualizowane. W związku z tym należy ręcznie odświeżyć stronę, aby zobaczyć zmiany.

> [!NOTE]
> Funkcja *Wielopoziomowe przekierowanie dla aplikacji mobilnej Warehouse Management* umożliwia definiowanie wielopoziomowych tras objazdowych (objazdów w objazdach), co pozwoli pracownikom na przejście z istniejącego objazdu na następnie i z powrotem. Ta funkcja obsługuje dwa gotowe poziomy objazdów i w razie potrzeby można dostosować system do obsługi trzech lub większej liczby poziomów objazdów, tworząc rozszerzenia kodu w tabeli `WHSWorkUserSessionState`.
>
> Funkcja *Automatycznie przesyłaj kroki przekierowania dla aplikacji mobilnej Warehouse Management* może przyspieszyć i ułatwić pracownikom wykonywanie przepływów przekierowania w aplikacji mobilnej Warehouse Management. Umożliwia ona pomijanie niektórych kroków przepływu, pozwalając aplikacji na wypełnianie danych przekierowania na zapleczu, a następnie na automatyczne przechodzenie do następnego kroku przez automatyczne przesłanie strony, tak jak pokazano w temacie [*Przykładowy scenariusz 1. Kompletacja sprzedaży, w której zapytanie o lokalizację pełni rolę obejścia*](#scenario-1).
