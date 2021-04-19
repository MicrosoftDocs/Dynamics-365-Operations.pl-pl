---
title: Planowanie tworzenia pracy podczas grupy czynności
description: W tym temacie opisano sposób konfigurowania i używania metody przetwarzania grupy czynności planowania tworzenia pracy.
author: perlynne
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e4258c03b12a80a5bd81328ae7418835d68f82e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835709"
---
# <a name="schedule-work-creation-during-wave"></a>Planowanie tworzenia pracy podczas grupy czynności

[!include [banner](../../includes/banner.md)]

Użyj funkcji *planowania tworzenia pracy* jako części procesu obsługi grupy czynności, aby zwiększyć przepustowość przetwarzania grupy czynności, ponieważ system tworzy pracę przy użyciu przetwarzania równoległego.

Gdy ta funkcja jest włączona, automatycznie zostanie utworzona planowana praca, która będzie ostatecznie przetwarzana w celu utworzenia rzeczywistej pracy. Jeśli liczba wierszy ładunku grupy czynności osiągnie wstępnie określony próg, system utworzy rzeczywistą pracę szybciej, stosując równoległe przetwarzanie asynchroniczne.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>Włączanie funkcji tworzenia zaplanowanej pracy w zarządzaniu funkcjami

Aby korzystać z funkcji opisanych w tym temacie, należy je włączona dla systemu. Użyj obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) włącz następujące funkcje w kolejności:

1. **Blokowanie pracy w całej organizacji** — Wymagane zarówno do ręcznej, jak i automatycznej konfiguracji tworzenia zaplanowanych prac.
1. **Zaplanuj tworzenie pracy** — Wymagane zarówno do ręcznej, jak i automatycznej konfiguracji tworzenia zaplanowanych prac.
1. **Metoda grupy czynności „Tworzenie harmonogramu pracy” obejmująca całą organizację** — Wymagane zarówno do ręcznej, jak i automatycznej konfiguracji tworzenia zaplanowanych prac. Ta funkcja nie jest potrzebna, jeśli jest potrzebna tylko konfiguracja ręczna.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>Automatyczne konfigurowanie tworzenia zaplanowanej pracy

Po włączeniu funkcji *Metoda grupy czynności „Tworzenie harmonogramu pracy” obejmująca całą organizację* w systemie automatycznie są tworzone następujące elementy:

- Metoda grupy czynności *Planowanie tworzenia pracy* (`WHSScheduleWorkCreationWaveStepMethod`) jest dodawana i skonfigurowana do uruchamiania równoległego we wszystkich firmach.
- W szablonach grupy czynności ze wszystkich firm, dla których jako **Typ szablonu grupy czynności** jest ustawiona wartość *Wysyłka*, a **Stan szablonu** ma wartość *Ważny*, metoda *Tworzenia pracy* zostanie zastąpiona metodą *Planowanie tworzenia pracy*. Szablony grupy czynności z firm, w których można powtarzać metodę *Utwórz pracę*, nie będą jednak modyfikowane.
- Konfiguracje zadań dla metody *Planowanie tworzenia pracy* zostaną utworzone dla wszystkich magazynów ze wszystkich firm, które mają **Użyj procesów zarządzania magazynami**. Oznacza to, że metoda *Planowanie tworzenia pracy* będzie domyślnie uruchamiana równolegle. Istniejące magazyny, dla których zmienisz ustawienie **Użyj procesów zarządzania magazynem** z wartości *Nie* na *Tak*, również będą domyślnie uruchamiać tę metodę równolegle.
- Wszystkie firmy będą przetwarzać grupy czynności w partiach, a **Oczekiwanie na blokadę (ms)** zostanie ustawione na wartość domyślną *60 000* ms, jeśli wcześniej było ustawione na *0* ms.
- Wszystkie nowe szablony grupy czynności, które utworzysz, będą miały metodę *Planowanie tworzenia pracy* zamiast metody *Utwórz pracę*.

Istniejące konfiguracje przetwarzania zadań i grupy czynności zostaną również zachowane dla wszystkich firm, które są już skonfigurowane do przetwarzania grup czynności w partiach, oraz dla wszystkich magazynów, które są już skonfigurowane do równoległego używania metody *Planowanie tworzenia pracy*.

W razie potrzeby można ręcznie przywrócić dowolne lub wszystkie ustawienia wprowadzone automatycznie po włączeniu funkcji *Metody grup czynności tworzenia harmonogramu w całej organizacji*, wykonując następujące czynności:

- Aby uzyskać szablony grup czynności, przejdź do **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**. Zastąp metodę *Planowanie tworzenia pracy* na *Utwórz pracę*.
- Aby zapoznać się z parametrami magazynu, przejdź do **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**. Na karcie **Przetwarzanie grupy czynności** zastosuj preferowane wartości dla **Przetwarzanie grup czynności w partii** i **Oczekiwanie na blokadę (ms)**.
- Aby przejść do metod grupy czynności, przejdź do **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**. W okienku akcji wybierz `WHSScheduleWorkCreationWaveStepMethod`, a następnie wybierz opcję **Konfiguracja zadań**. Zmodyfikuj lub usuń liczbę zadań wsadowych oraz przypisaną grupę czynności dla każdego z wymienionych magazynów, w razie potrzeby.

## <a name="manually-configure-scheduled-work-creation"></a>Ręczne konfigurowanie tworzenia zaplanowanej pracy

Jeśli nie włączyć [funkcji *Metoda grupy czynności „Tworzenie harmonogramu pracy” obejmująca całą organizację*](#Auto-enable-schedule-work-creation), możesz użyć procedur podanych w tej sekcji, aby ręcznie skonfigurować w razie potrzeby tworzenie zaplanowanej pracy.

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
1. Wybierz strzałkę wskazującą kolumnę **Wybrane metody**, aby przenieść wybrany wiersz do tej kolumny. (W danym momencie może być używana tylko jedna wybrana metoda `WHSScheduleWorkCreationWaveStepMethod` lub `createWork`, w związku z tym istniejący wiersz o **Nazwie metody** `createWork` zostanie automatycznie przeniesiony do siatki **Pozostałe metody**).

## <a name="set-wave-task-processing-threshold-data"></a>Ustaw dane progowe przetwarzania zadań grupy czynności

System utworzy domyślne dane progowe przetwarzania zadań grupy czynności podczas pierwszego przetwarzania grupy czynności z użyciem dowolnego przetwarzania opartego na zadaniu. Dane służą do kontrolowania, kiedy przetwarzanie grupy czynności będzie wykonywane asynchronicznie i będzie oparte na zadaniach, co pozwala na równoległe przetwarzanie i tworzenie pracy.

Dane domyślne początkowo korzystają z wartości progowej 15 dla minimalnej liczby wierszy ładunku (`MINIMUMWAVELOADLINES`). Oznacza to, że gdy system przetwarza ładunek grupy czynności z więcej niż 15 wierszami, będzie używać asynchronicznego przetwarzania zadań. Te dane można wstawiać/aktualizować ręcznie `WHSWaveTaskProcessingThresholdParameters` w tabeli w środowiskach testowych. Jeśli musisz zmienić to ustawienie w środowisku produkcyjnym, musisz skontaktować się z pomocą techniczną firmy Microsoft, aby zażądać aktualizacji.

## <a name="work-with-the-scheduled-work-creation"></a>Pracuj z zaplanowanym utworzeniem pracy

Aby uzyskać szczegółowe informacje dotyczące sposobu pracy z zaplanowaną pracą, zobacz temat [Tworzenie i przetwarzanie grupy czynności](wave-processing.md). 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
