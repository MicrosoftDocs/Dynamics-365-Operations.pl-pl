---
title: Powiadomienia dotyczące wykonania grupy czynności
description: W tym artykule opisano powiadomienia o wykonywaniu grupy czynności i wyjaśniono, jak je skonfigurować.
author: Mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 6f8f43bcdaae9a14350c66039d204caf38d33768
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906979"
---
# <a name="wave-execution-notifications"></a>Powiadomienia dotyczące wykonania grupy czynności

[!include [banner](../includes/banner.md)]

Funkcja *powiadomień o wykonaniu grupy czynności* korzysta ze zdarzeń biznesowych i centrum akcji w celu dostarczania powiadomień dotyczących wykonywania grupy czynności. Użytkownik może określać typy zdarzeń generujące powiadomienia, magazyny je generujące oraz użytkowników, którzy je otrzymują.

Przycisk **Pokaż komunikaty** (symbol dzwonka) po prawej stronie paska nawigacji wskazuje, kiedy wiadomość z centrum akcji jest dostępna dla bieżącego użytkownika. Użytkownik może wybrać przycisk **Pokaż wiadomości**, aby otworzyć Centrum akcji i przejrzeć wiadomości.

Zdarzenia biznesowe mają miejsce podczas uruchamiania procesów biznesowych. Procesy biznesowe są składa się z zadań. W trakcie procesu biznesowego użytkownicy, którzy uczestniczą w tym procesie, wykonują akcje biznesowe w celu wykonania tych zadań. Zdarzenia biznesowe zapewniają mechanizm, za który zewnętrzne systemy otrzymują powiadomienia od aplikacji finansowych i operacyjnych. W ten sposób systemy mogą wykonywać akcje biznesowe w odpowiedzi na zdarzenia biznesowe. Aby uzyskać więcej informacji, zajrzyj do [Zdarzenia biznesowe - omówienie](../../fin-ops-core/dev-itpro/business-events/home-page.md).

## <a name="turn-the-wave-execution-notifications-feature-on-or-off"></a>Włącz lub wyłącz funkcję powiadomień o wykonaniu Wave

Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Powiadomienia o wykonaniu fali* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>Scenariusz: wysyłanie powiadomień o przetwarzaniu wsadowym grupy czynności do centrum akcji

Ten scenariusz przedstawia przepływ końca okresu, w którym można wysyłać powiadomienia o błędach przetwarzania wsadowego grupy czynności do określonej roli za pośrednictwem centrum akcji.

### <a name="make-demo-data-available"></a>Udostępnianie danych pokazu

W tym scenariuszu trzeba mieć zainstalowane dane demonstracyjne oraz musi być wybrana firma **USMF**.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>Upewnij się, że partie są uruchamiane w trybie wsadowym

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Parametry zarządzania magazynem**.
1. Na skróconej karcie **Przetwarzanie grupy czynności** należy skonfigurować **Przetwarzanie wsadowe grup czynności** na wartość *Tak*.

> [!NOTE]
> Jeśli chcesz wyłączyć powiadomienia dotyczące przetwarzania wsadowego grupy czynności, ustaw opcję **Wyłącz powiadomienia o przetwarzaniu wsadowym grupy czynności** na Wartość *Tak*.

### <a name="configure-a-wave-notification-policy"></a>Konfigurowanie zasad powiadamiania o grupy czynności

Zasady powiadomień grupy czynności określają typy wysyłanych powiadomień oraz powiadamianych użytkowników.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Zasady powiadamiania o grupie czynności**.
1. Dodaj rekord z następującymi ustawieniami:

    - **Zasady powiadamiania o grupie czynności:** *24BatchError*
    - **Opis:** *Błąd partii grupy czynności magazynu 24*
    - **Wyślij powiadomienie w:** *tylko błąd*
    - **Do roli:** *Administrator systemu*

        > [!NOTE]
        > Ponieważ w tym scenariuszu są używane dane demonstracyjne, rola *Administrator systemu* jest wybierana na potrzeby zakańca. Dlatego, ponieważ jesteś zalogowanym użytkownikiem administratora systemu, otrzymasz powiadomienia. Jednak w praktyce zazwyczaj należy wybrać bardziej specyficzną rolę, aby powiadamiać o błędach przetwarzania wsadowego grupy czynności, takich jak *Menedżer magazynu*.

1. Na okienku akcji wybierz opcję **Zapisz**.

### <a name="configure-a-wave-template"></a>Skonfiguruj szablon grupy czynności

Szablony grupy czynności umożliwiają łączenie konkretnych instancji metod grupy czynności z odpowiednim szablonem etykiety grupy czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. W okienku listy ustaw w polu **Typ szablonu grupy czynności** wartość *Wysyłka*, a następnie wybierz szablon *domyślnej wysyłki 24* grupy czynności dla magazynu 24.
1. Na skróconej karcie **Ogólne** należy określić wartość w polu **Zasady powiadomień grupy** na *24BatchError*.

### <a name="configure-a-work-template"></a>Skonfiguruj szablon pracy

Szablony pracy są używane podczas wykonywania grupy czynności do generowania pracy. W tym scenariuszu wykonanie grupy czynności powinno wyzwolić błąd. Ustawienie kwerendy szablonu pracy na użycie nieistniejącego magazynu pozwoli upewnić się, że wykonanie grupy czynności nie powiedzie się i dlatego zostanie wysyłane powiadomienie.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Szablony pracy**.
1. W okienku listy ustaw w polu **Typ szablonu pracy** wartość *Zlecenie sprzedaży*, a następnie wybierz szablon *24 SO Stage* pracy dla magazynu 24.
1. W okienku akcji wybierz pozycję **Edytuj zapytanie**.
1. W oknie dialogowym edytora zapytań, na karcie **Zakres** dokonaj edycji następującego wiersza (lub dodaj go, jeśli nie istnieje):

    - **Tabela:** *Tymczasowe transakcje pracy*
    - **Tabela pochodna:** *Tymczasowe transakcje pracy*
    - **Pole:** *Magazyn*
    - **Kryteria:** zmień wartość z *24* na *Błąd*.

1. Potwierdź zmiany i kliknij przycisk **OK**.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Utwórz zamówienie sprzedaży i zwolnij je do magazynu

1. Wybierz kolejno opcje **Sprzedaż i marketing \> Zamówienie sprzedaży \> Wszystkie zamówienia sprzedaży**.
1. Utwórz zamówienie sprzedaży z następującymi ustawieniami:

    - **Konto odbiorcy:** *US-001*
    - **Magazyn:** *24*

1. Na skróconej karcie **Wierszy zamówienia sprzedaży** dodaj drugie zamówienie sprzedaży o następujących ustawieniach:

    - **Numer pozycji:** *A0001*
    - **Ilość:** *10*

    > [!NOTE]
    > Te towary i ilości są tylko przykładami. Określony magazyn musi zawierać wystarczającą ilość zapasów.

1. Gdy nowy wiersz zamówienia jest wciąż wybrany na skróconej karcie **Wiersze zamówienia sprzedaży**, w menu **Inventory \> Rezerwacja** na pasku narzędzi..
1. Na stronie **Rezerwacje** w okienku akcji wybierz **Rezerwacja partii**. Następnie zamknij stronę.
1. W okienku akcji na karcie **Magazyn** wybierz opcję **Zwolnienie do magazynu**.

### <a name="notifications-from-wave-batch-job-execution"></a>Powiadomienia z wykonania zadania wsadowego grupy czynności

W zależności od konfiguracji zdarzeń biznesowych użytkownik ostatecznie otrzyma powiadomienie o niepowodzeniu wykonania grupy czynności. Komunikat centrum akcji przypomina poniższy przykład i zawiera łącze do grupy czynności, która zakończyła się niepowodzeniem.

> **Błąd podczas wykonywania grupy czynności**  
> Wystąpił błąd podczas wykonywania grupy czynności USMF-000000001.  
> Ostatnie komunikaty: Nie utworzono pracy dla grupy czynności USMF-000000001.
>
> **STAN**  
> Aktywni
>
> Otwórz szczegóły grupy czynności

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
