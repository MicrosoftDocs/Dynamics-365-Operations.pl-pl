---
title: Planowanie tworzenia pracy podczas grupy czynności
description: W tym temacie opisano sposób konfigurowania i używania metody przetwarzania grupy czynności planowania tworzenia pracy.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078296"
---
# <a name="schedule-work-creation-during-wave"></a>Planowanie tworzenia pracy podczas grupy czynności

[!include [banner](../includes/banner.md)]

Użyj funkcji *planowania tworzenia pracy* jako części procesu obsługi grupy czynności, aby zwiększyć przepustowość przetwarzania grupy czynności, ponieważ system tworzy pracę przy użyciu przetwarzania równoległego.

Gdy ta funkcja jest włączona, automatycznie zostanie utworzona planowana praca, która będzie ostatecznie przetwarzana w celu utworzenia rzeczywistej pracy. Jeśli liczba wierszy ładunku grupy czynności osiągnie wstępnie określony próg, system utworzy rzeczywistą pracę szybciej, stosując równoległe przetwarzanie asynchroniczne.

## <a name="enable-the-schedule-work-creation-feature"></a>Włącz funkcję planowania tworzenia pracy

### <a name="enable-the-feature-in-feature-management"></a>Włącz funkcję w zarządzaniu funkcjami

Aby móc używać funkcji *Planowanie tworzenia pracy*, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:

- **Moduł:** *Zarządzanie magazynem*
- **Nazwa funkcji:** *Planowanie tworzenia pracy*

> [!NOTE]
> Aby można było włączyć *planowanie tworzenia pracy*, należy włączyć funkcję *blokowania pracy w całej organizacji*.

### <a name="manually-enable-batch-processing-of-waves"></a>Ręczne włączanie przetwarzania wsadowego grup czynności

Aby można było korzystać z równoległej metody asynchronicznej tworzenia pracy magazynowej, proces grupy czynności musi być uruchomiony w partii. Aby to skonfigurować:

1. Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.

1. Na karcie **Ogólne** ustaw opcję **Przetwarzaj grupy czynności partiami** na *Tak*. Opcjonalnie możesz również wybrać dedykowaną **grupę przetwarzania wsadowego grupy czynności**, aby uniemożliwić uruchomienie przetwarzania kolejki przetwarzania wsadowego w tym samym czasie, co inne procesy.

1. Ustaw **czas oczekiwania na blokadę (ms)**, który ma zastosowanie, gdy system przetwarza kilka grup czynności w tym samym czasie. W przypadku większości procesów grup czynności zalecane jest użycie wartości *60 000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Ręcznie włącz nową metodę kroku grupy czynności dla istniejących szablonów grupy czynności

Rozpocznij od utworzenia nowej metody kroku grupy czynności i włączenia jej do równoległego przetwarzania zadań asynchronicznych.

1. Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.

1. Wybierz opcję  **Ponownie utwórz metody** i zauważ, że do listy metod przetwarzania grupy czynności, których można używać w szablonach grupy czynności wysyłki, dodano metodę *WHSScheduleWorkCreationWaveStepMethod*.

1. Wybierz rekord z **nazwą metody** *WHSScheduleWorkCreationWaveStepMethod* i wybierz **Konfiguracja zadania**.

1. Aby dodać nowy wiersz do siatki, wybierz opcję **Nowy** w okienku akcji i użyj następujących ustawień:

    - **Magazyn** — umożliwia wybranie magazynu, który ma być podstawą do zaplanowania przetwarzania tworzenia pracy.

    - **Maksymalna liczba zadań wsadowych** — umożliwia określenie maksymalnej liczby zadań wsadowych. W większości przypadków ta wartość powinna być w przedziale od 8 do 16, jednak zalecamy eksperymentowanie z ustawieniami optymalnymi na podstawie scenariuszy.

    - **Grupa przetwarzania wsadowego grupy czynności** — wybierz dedykowaną grupę przetwarzania grupy czynności w celu zoptymalizowania przetwarzania wsadowego.

Teraz można zaktualizować istniejący szablon grupy czynności (lub utworzyć nowy), aby użyć metody przetwarzania grupy czynności *Planowanie tworzenia pracy*.

1. Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.

1. W okienku akcji wybierz pozycję **Edytuj**.

1. W okienku listy wybierz szablon grupy czynności, który chcesz zaktualizować (w przypadku testowania danych pokazowych możesz użyć *domyślnej wysyłki w 24 godziny*).

1. Rozwiń skróconą kartę **Metody** i zaznacz wiersz z **nazwą** *Planowanie tworzenia pracy* w siatce **Pozostałe metody**.

1. Wybierz strzałkę wskazującą kolumnę **Wybrane metody**, aby przenieść wybrany wiersz do tej kolumny. (W danym momencie może być używana tylko jedna wybrana metoda *WHSScheduleWorkCreationWaveStepMethod* lub *createWork*, w związku z tym istniejący wiersz o **nazwie metody** *createWork* zostanie automatycznie przeniesiony do siatki metod **Pozostałe metody**).

## <a name="set-wave-task-processing-threshold-data"></a>Ustaw dane progowe przetwarzania zadań grupy czynności

System utworzy domyślne dane progowe przetwarzania zadań grupy czynności podczas pierwszego przetwarzania grupy czynności z użyciem dowolnego przetwarzania opartego na zadaniu. Dane służą do kontrolowania, kiedy przetwarzanie grupy czynności będzie wykonywane asynchronicznie i będzie oparte na zadaniach, co pozwala na równoległe przetwarzanie i tworzenie pracy.

Dane domyślne początkowo korzystają z wartości progowej 15 dla minimalnej liczby wierszy ładunku (MINIMUMWAVELOADLINES). Oznacza to, że gdy system przetwarza ładunek grupy czynności z więcej niż 15 wierszami, będzie używać asynchronicznego przetwarzania zadań. Dane te można ręcznie wstawiać/aktualizować w tabeli **WHSWaveTaskProcessingThresholdParameters** w środowiskach testowych, ale jeśli musisz zmienić to ustawienie w środowisku produkcyjnym, skontaktuj się z pomocą techniczną firmy Microsoft, aby poprosić o aktualizację.

## <a name="work-with-the-feature"></a>Pracuj z funkcją

Gdy jest włączona funkcja *planowania tworzenia pracy*, przetwarzanie grupy czynności utworzy planowaną pracę, która będzie ostatecznie używana przez nowy proces tworzenia pracy. Podczas tworzenia pracy praca zostanie zablokowana za pomocą funkcji *blokowania pracy w całej organizacji*.

Poniższy schemat blokowy pokazuje, jak planowana praca jest tworzona podczas przetwarzania grupy czynności.

![Planowanie tworzenia pracy](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Zaplanowana praca

Strona **szczegółów planowanej pracy** (**Zarządzanie magazynem \> Praca \> Szczegóły planowanej pracy**) zawiera informacje o planowanej pracy, która jest początkowo tworzona podczas przetwarzania grupy czynności. Dostępne są następujące wartości opcji **Stan procesu**:

- **W kolejce** — planowana praca oczekuje na utworzenie pracy.
- **Zakończono** — planowana praca została użyta do utworzenia pracy.
- **Niepowodzenie** — przetwarzanie grupy czynności nie powiodło się. Należy zauważyć, że praca planowana może mieć stan **Niepowodzenie** z rzeczywistą pracą lub bez niej. Jeśli rzeczywisty proces tworzenia pracy nie powiedzie się, rzeczywista praca pozostaje w stanie *Anulowana*.

### <a name="batch-job-for-the-work-creation-process"></a>Zadanie wsadowe dla procesu tworzenia pracy

Aby wyświetlić zadania wsadowe przetwarzania grup czynności, wybierz **Zadania wsadowe** w okienku akcji na stronie **Wszystkie grupy czynności**.

W tym miejscu można wyświetlić wszystkie szczegóły zadania wsadowego dla każdego z identyfikatorów zadań wsadowych.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]