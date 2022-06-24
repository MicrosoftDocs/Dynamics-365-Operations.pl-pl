---
title: Zdarzenia aplikacji magazynowej
description: W tym artykule opisano przetwarzanie zdarzeń aplikacji magazynu używane do przetwarzania komunikatów zdarzeń aplikacji magazynowych w ramach zadania wsadowego.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 41b9538d3064bad24c4c5c60d401605e47e9c655
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905462"
---
# <a name="warehouse-app-event-processing"></a>Przetwarzanie zdarzenia aplikacji magazynu

[!include [banner](../includes/banner.md)]

Zadania wsadowe działające w module Supply Chain Management mogą używać danych z kolejki do przetwarzania zdarzeń wydawanych przez aplikację Warehouse Management w celu reagowania w razie potrzeby na zdarzenia sygnalizujące. Ta funkcja umożliwia dodanie odpowiednich zdarzeń do kolejki w odpowiedzi na określone typy akcji podejmowanych przez pracowników korzystających z aplikacji. Przykładem jest użycie opcji *Utwórz i przetwórz zamówienia przeniesienia z funkcji aplikacji magazynu*, nagłówek i wiersze zamówienia przeniesienia są tworzone i aktualizowane w wewnętrznej odpowiedzi, gdy system uruchamia zadanie wsadowe **Przetwarzanie zdarzeń aplikacji magazynu**.

## <a name="turn-the-process-warehouse-app-events-feature-on-or-off"></a>Włącz lub wyłącz funkcję Zdarzenia aplikacji magazynu procesów

Od wersji 10.0.25 Supply Chain Management version ta funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Zdarzenia aplikacji magazynu procesów* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Umożliwia konfigurowanie zadania wsadowego w celu przetwarzania zdarzeń aplikacji magazynowych

### <a name="process-warehouse-app-events"></a>Przetwarzanie zdarzeń aplikacji magazynowej

Umożliwia konfigurowanie zaplanowanego zadania wsadowego w celu przetwarzania zdarzeń aplikacji magazynowych dla aktualizacji zamówień przeniesienia i aktualizowania wierszy.

1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Przetwarzanie zdarzeń aplikacji magazynu**.
1. Zostanie otwarte okno dialogowe Przetwarzanie zdarzeń aplikacji magazynu. Rozwiń skróconą kartę **Uruchom w tle** i ustaw opcję **Przetwarzanie wsadowe** na wartość **Tak**.
1. Na skróconej karcie **Uruchom w tle** wybierz **Cykl**.
1. Zostanie otwarte okno dialogowe **Definiuj cykl**. Umożliwia ustawienie harmonogramu uruchamiania w zależności od potrzeb firmy.
1. Wybierz przycisk **OK**, aby powrócić do okna dialogowego **Przetwarzanie zdarzeń aplikacji magazynu**.
1. Aby dodać zadanie wsadowe do kolejki przetwarzania wsadowego, należy wybrać opcję **OK** w oknie dialogowym **Przetwarzanie zdarzeń aplikacji magazynu**.

## <a name="query-warehouse-app-events"></a>Kwerenda zdarzeń aplikacji magazynu

Komunikaty dotyczące kolejki zdarzeń i zdarzeń generowane przez aplikację Warehouse Management można przeglądać, przechodząc do **Zarządzanie magazynem \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Zdarzenia aplikacji magazynu**.

## <a name="the-standard-event-queue-process"></a>Standardowy proces kolejki zdarzeń

Kolejka zdarzeń aplikacji magazynu zazwyczaj będzie używana z następującym opisanym przepływem:

1. Zdarzenie jest dodawane do kolejki wraz z komunikatem o zdarzeniu. Nowa wiadomość zawiera początkowo stan zdarzenia **Oczekujące**, co oznacza, że zadanie wsadowe **Przetwarzania zdarzeń aplikacji magazynu** nie odbiera i nie przetworzy tego komunikatu.
1. Gdy tylko stan wiadomości zostanie zaktualizowany do stanu **W kolejce**, zadanie wsadowe **Przetwarzanie zdarzeń aplikacji magazynu** będzie pobierać i przetwarzać zdarzenie.
1. Zadanie wsadowe aktualizuje stany zdarzeń na **Zakończone** albo **Niepowodzenie**, w zależności od tego, czy żądany proces był możliwy.
1. Po **zakończeniu** wszystkich pokrewnych komunikatów zdarzeń zdarzenie jest usuwane z kolejki.

 Aby zapoznać się z szczegółowym przykładem, patrz [Tworzenie zamówienia przeniesienia z poziomu aplikacji magazynowej](create-transfer-order-from-warehouse-app.md).

## <a name="handle-event-errors"></a>Obsługa błędów zdarzeń

W ramach przetwarzania zdarzenia dotyczącego magazynu żądana czynność wiadomości może nie mieć procesów w ramach zadania wsadowego. W takim przypadku komunikat zdarzenia ulegnie zmianie na **Niepowodzenie**. Z informacji w **dzienniku partii** można dowiedzieć się, dlaczego i podjąć niezbędne działania w celu rozwiązania problemów.

Aby zapoznać się z szczegółowym przykładem, patrz [Tworzenie zamówienia przeniesienia z procesu aplikacji magazynu](create-transfer-order-from-warehouse-app.md).

Aby zresetować komunikat o zdarzeniu niepowodzenia aplikacji magazynu:

1. Przejdź do **Zarządzanie magazynem \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Zdarzenia aplikacji magazynu**.
1. W skróconej karcie **Komunikaty zdarzeń aplikacji magazynu** znajdź i zaznacz odpowiednie zdarzenie, które ma stan **Niepowodzenie** w kolumnie **Stan zdarzenia**.
1. Wybierz opcję **Resetuj** z paska narzędzi **Komunikaty zdarzeń aplikacji magazynu**.
1. Kontynuuj pracę do momentu zresetowania wszystkich odpowiednich komunikatów.

Można również usunąć komunikat o zdarzeniu **Niepowodzenie**, używając opcji **Usuń** na pasku narzędzi **Komunikaty zdarzeń aplikacji magazynu**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]