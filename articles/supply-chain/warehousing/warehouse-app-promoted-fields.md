---
title: Konfiguracja promowanych pól dla kroków w aplikacji mobilnej Warehouse Management
description: W tym artykule opisano sposób promowania i wyróżniania określonych informacji dla dowolnego kroku w przepływach zadań w aplikacji mobilnej Warehouse Management.
author: Mirzaab
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5f5f24f47d0a2376be714f9208cd383cf3aacc07
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857062"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>Konfiguracja promowanych pól dla kroków w aplikacji mobilnej Warehouse Management

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Funkcje opisane w tym artykule dotyczą tylko nowej aplikacji mobilnej Warehouse Management. Nie wpływają one na starą aplikację magazynu, która jest obecnie przestarzała.

W tym artykule opisano sposób promowania i wyróżniania określonych informacji dla dowolnego kroku w przepływach zadań w aplikacji mobilnej Warehouse Management. Ta możliwość może pomóc w skupieniu uwagi pracowników na najważniejszych polach podczas pracy nad przepływem. Dla każdego kroku w każdym procesie administratorzy mogą wybrać, które pola mają być promowane, a które wyróżnione.

## <a name="enable-promoted-fields-in-your-system"></a>Włącz promowane pola w swoim systemie

Zanim będzie można ustawić pola promowane, należy wykonać poniższą procedurę, aby włączyć wymagane funkcje i wygenerować wymagane nazwy pól w aplikacji mobilnej Warehouse Management.

1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
1. W [**obszarze roboczym Zarządzanie funkcjami**](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) włącz funkcję, która jest wymieniona w następujący sposób:

    - **Moduł:** *Zarządzanie magazynem*
    - **Nazwa funkcji:** *instrukcje kroków aplikacji magazynu*

    Aby uzyskać więcej informacji na temat funkcji *Instrukcje krok po kroku aplikacji Warehouse*, patrz [Dostosowywanie tytułów i instrukcji krok po kroku dla aplikacji mobilnej Warehouse Management](mobile-app-titles-instructions.md). Ta funkcja jest warunkiem koniecznym dla funkcji *Promowane pola aplikacji Warehouse*.

1. Włącz funkcję, która jest wymieniona w następujący sposób:

    - **Moduł:** *Zarządzanie magazynem*
    - **Nazwa funkcji** *Pola promowane w aplikacji magazynowej*

    Ta funkcja jest opisana w tym artykule.

1. Zaktualizuj nazwy pól w aplikacji mobilnej Warehouse Management, przechodząc do **Zarządzanie magazynem \> Konfiguracja \> Urządzenie mobilne \> Nazwy pól aplikacji Warehouse** i wybierając **Utwórz konfigurację domyślną**. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie pól aplikacji mobilnej Warehouse Management](configure-app-field-names-priorities-warehouse.md).
1. Powtórz poprzedni krok dla każdej osoby prawnej (firmy), w której korzystasz z aplikacji mobilnej Warehouse Management.

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>Konfiguracja promowanych pól z poziomu nadpisania specyficznego dla menu

Użyj poniższej procedury, aby skonfigurować promowane pola.

1. Utworzyć nadpisanie dla danego menu i kroku zgodnie z opisem w punkcie [Dostosowywanie tytułów kroków i instrukcji dla aplikacji mobilnej Warehouse Management](mobile-app-titles-instructions.md).
1. Znajdź kombinację wartości **Identyfikator kroku** i **Nazwa opcji menu**, które chcesz edytować, i wybierz wartość w kolumnie **Identyfikator kroku**.
1. Na stronie, która się pojawi, na skróconej karcie **Wybierz promowane pola**, wybierz **Wybierz pola** na pasku narzędzi.
1. W oknie dialogowym **Promowane pola** wybierz pola, które chcesz promować. Można również zaznaczyć maksymalnie dwa z wybranych pól. Podkreślone pola będą wyświetlane w aplikacji mobilnej Warehouse Management pogrubioną czcionką. Wybierając pola, weź pod uwagę fakt, że niektóre ekrany mogą być wystarczająco duże, aby pokazać tylko jedno lub dwa najlepsze promowane pola. Przykład użycia tych ustawień można znaleźć w scenariuszu w dalszej części tego artykułu.

    > [!NOTE]
    > Lista **Dostępne pola** jest ograniczona do pól, które mogą być wyświetlane dla danej pozycji menu. Jednak o tym, czy dane pole rzeczywiście pojawi się w aplikacji mobilnej Warehouse Management decydują inne czynniki (takie jak skład pozycji). Jeśli skonfigurowałeś pola promowane, na stronie głównej aplikacji mobilnej Warehouse Management pojawią się tylko wybrane pola. Pracownicy mogą jednak nadal przeglądać pozostałe pola, stukając na stronie szczegółów.

1. Wybierz **OK**, aby zastosować ustawienia. Wybrane pola zostaną teraz wyświetlone na skróconej karcie **Wybierz pola promowane**.

## <a name="example-scenario"></a>Przykładowy scenariusz

### <a name="enable-sample-data"></a>Włącz dane przykładowe

Aby użyć określonych przykładowych rekordów i wartości do pracy z tym scenariuszem, musisz używać systemu, w którym zainstalowane są standardowe dane demo. Należy również wybrać firmę **USMF** przed rozpoczęciem.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>Konfiguracja kompletacji sprzedaży z promowanymi krokami na etapie tablicy rejestracyjnej

W tej procedurze skonfigurujesz promowane i podświetlane pola dla pozycji menu **Kolekcja sprzedaży** w kroku tablicy rejestracyjnej.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Urządzenie przenośne \> Kroki urządzenia przenośnego**.
1. Znajdź identyfikator kroku o nazwie *LicensePlateId* i zaznacz go.
1. W okienku akcji wybierz pozycję **Dodaj konfigurację kroku**.
1. W rozwijanym oknie dialogowym użyj pola **Element menu**, aby znaleźć i wybrać *Pobieranie z Sales*.
1. Kliknij przycisk **OK**.
1. Pojawia się strona szczegółów dla właśnie utworzonego zastępstwa. Na skróconej karcie **Wybierz promowane pola**, wybierz **Wybierz pola** na pasku narzędzi.
1. W oknie dialogowym **Promowane pola** można wybrać pola, które mają być promowane i wyróżnione. Na liście **Dostępne pola** znajdź i wybierz następujące pola, a następnie użyj przycisków, aby przenieść je na listę **Wybranych pól**:

    - Lokalizacja
    - Towar
    - Nazwa produktu
    - Stan zapasów

1. Użyj przycisków strzałki w górę i strzałki w dół, aby dostosować kolejność pól na liście **Wybranych pól**. W aplikacji mobilnej Warehouse Management, pola pojawią się w kolejności, którą tutaj ustawisz.
1. Zaznacz pole **Lokalizacja**, a następnie wybierz **Podświetl**.
1. Wybierz **OK**, aby zapisać konfigurację.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>Wyświetlanie promowanych pól w aplikacji mobilnej Warehouse Management

W tej procedurze otworzysz aplikację mobilną Warehouse Management i przejdziesz przez kolejne kroki, aby wyświetlić pola, które promowałeś i zaznaczyłeś w poprzedniej procedurze.

1. W Microsoft Dynamics 365 Supply Chain Management utwórz zamówienie sprzedaży, które będzie wymagało kroku kompletacji w celu pobrania z lokalizacji, która jest śledzona na podstawie tablic rejestracyjnych. Teraz wydaj zamówienie sprzedaży do magazynu. Zanotuj pokazany identyfikator pracy.
1. Zaloguj się do aplikacji Warehouse Management jako użytkownik w magazynie 24. (W standardowych danych demonstracyjnych zaloguj się, używając *24* jako identyfikatora użytkownika i *1* jako hasła.)
1. Wybierz menu **Wychodzące**, a następnie wybierz element menu **Pobranie z Sales**.
1. Postępuj zgodnie z instrukcjami wprowadzania danych na ekranie, aby wprowadzić identyfikator pracy, który został wygenerowany w kroku 1.
1. W kroku, który zawiera tekst **Skanuj numer identyfikacyjny**, powinieneś zobaczyć zmiany wprowadzone na stronie szczegółów. Pola pojawiają się w kolejności ustawionej dla promowanych pól, a pole **Lokalizacja** jest wyświetlane pogrubioną czcionką.
