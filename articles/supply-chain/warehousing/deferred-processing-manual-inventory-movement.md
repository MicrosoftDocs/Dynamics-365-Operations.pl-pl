---
title: Odroczone przetwarzanie ręcznego przesunięcia magazynowego
description: W tym temacie opisano sposób użycia odroczonego przetwarzania ręcznego przesunięcia magazynowego w systemie Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: Mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 54a202b7e6728bc83022851c901d3c5db17510bf
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956784"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>Odroczone przetwarzanie ręcznego przesunięcia magazynowego

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób użycia odroczonego przetwarzania ręcznego przesunięcia magazynowego w systemie Microsoft Dynamics 365 Supply Chain Management.

Odroczone przetwarzania umożliwia pracownikom magazynu kontynuowanie innych prac podczas przetwarzania operacji odłożenia w tle. Odroczone przetwarzanie jest przydatne, kiedy na serwer zdarzają się nieplanowane wydłużenia czasu przetwarzania, a zwiększony czas przetwarzania może wpłynąć na produktywność pracownika. Typ pracy *Przesunięcie magazynowe* został dodany do zestawu typów pracy, które obsługuje ta funkcja.

Przetwarzanie w tle jest możliwe za pomocą [funkcji Przetwarzanie zdarzeń aplikacji magazynu](warehouse-app-events.md).

## <a name="turn-on-this-feature-for-your-system"></a>Włączanie funkcji w systemie

Aby ta funkcja była dostępna, włącz następujące funkcje w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md): Musisz je włączyć w następującej kolejności:

1. Blokowanie pracy na poziomie organizacji
1. Przetwarzanie zdarzeń aplikacji magazynowej
1. Odroczone operacje odłożenia
1. Odroczone przetwarzanie operacji ręcznego przenoszenia zapasów

## <a name="configure-the-work-processing-policies"></a>Konfigurowanie zasad przetwarzania pracy

Aby użyć odroczonego przetwarzania, należy skonfigurować zasady przetwarzania pracy i używać ich. W przypadku odroczonego przetwarzania odłożenia funkcja [Odroczone przetwarzanie pracy magazynowej](deferred-put.md) obsługuje następujące typy pracy: *Zamówienie sprzedaży*, *Wydanie zamówienia przeniesienia* i *Uzupełnienie zapasów*. Funkcja *Odroczone przetwarzanie ręcznego przesunięcia magazynowego* dodaje nowy typ pracy: *Przesunięcie magazynowe*.

Aby skonfigurować zasady przetwarzania pracy, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ustawienia \> Praca \> Zasady przetwarzania pracy**.
1. Wybierz istniejącą zasadę na liście lub utwórz nową zasadę, wybierając opcję **Nowa** w okienku akcji. Nagłówek każdej zasady zawiera następujące pola:

    - **Nazwa zasady przetwarzania pracy**— nazwa zasady przetwarzania pracy.
    - **Opis** — jest to opis zasady przetwarzania pracy.

1. Na skróconej karcie **Reguły przetwarzania** skonfiguruj kolekcję reguł, do których będą obowiązywały zasady. Użyj następujących przycisków na pasku narzędzi, aby dodawać i usuwać reguły według potrzeb. Dla każdej reguły ustaw następujące pola:

    - **Typ zlecenia pracy** — umożliwia wybór typu pracy, do którego ma zastosowanie zasada.
    - **Operacja** — umożliwia wybór operacji, do przetwarzania której są stosowane zasady. Jeśli w polu **Typ zlecenia pracy** wybrano opcję *Przesunięcie magazynowe*, nie trzeba ustawiać tego pola, ponieważ operacje pobrania i odkładania są przetwarzane jako pojedyncze zdarzenie.
    - **Metoda przetwarzania pracy** — umożliwia wybór metody używanej do przetwarzania wiersza pracy. Jeśli wybierzesz opcję *Natychmiastowe*, zachowanie przypomina zachowanie, gdy żadne zasady przetwarzania pracy nie są używane do przetworzenia wiersza. W przypadku wybrania opcji *Odroczone* system zastosuje przetwarzanie odroczone, które korzysta ze struktury przetwarzania wsadowego.
    - **Próg przetwarzania odroczonego** — jeśli w tym polu zostanie ustawiona wartość *0* (zero), to nie ma progu. W takim przypadku używana jest metoda przetwarzanie *Odroczone*, o ile jest to możliwe. Jeśli wynik obliczenia konkretnego progu jest poniżej progu, używana jest metoda *Natychmiastowe*. W przeciwnym razie używana jest metoda *Odroczona*, o ile jest to możliwe. W przypadku pracy związanej ze sprzedażą i przenoszeniem próg jest obliczany jako liczba skojarzonych źródłowych wierszy obciążenia, które są przetwarzane w odniesieniu do pracy. W odniesieniu do pracy uzupełniania, próg jest obliczany jako liczba wierszy pracy, które są uzupełniane przez pracę. Ustawienie progu, na przykład *5* dla sprzedaży, powoduje, że w przypadku mniejszych prac, które mają mniej niż pięć wierszy początkowego obciążenia źródła, nie będzie używane przetwarzanie odroczonego, ale w przypadku większych prac będzie ono używane. Próg ma zastosowane tylko wtedy, gdy w polu **Metoda przetwarzania pracy** jest wybrane ustawienie *Odroczone*.
    - **Grupa przetwarzania wsadowego odroczonego przetwarzania**— służy do określania grupy przetwarzania wsadowego. Jeśli w polu **Typ zlecenia pracy** wybrano opcję *Przesunięcie magazynowe*, nie trzeba ustawiać tego pola, ponieważ grupa przetwarzania wsadowego jest wybrana w oknie dialogowym **Przetwarzanie zdarzeń aplikacji magazynowej**.

## <a name="assign-the-work-creation-policy"></a>Przypisywanie zasad tworzenia pracy

Aby uzyskać szczegółowe informacje dotyczące przypisywania zasad tworzenia pracy, zobacz temat [Odroczone przetwarzanie pracy magazynowej](deferred-put.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Umożliwia konfigurowanie zadania wsadowego w celu przetwarzania zdarzeń aplikacji magazynowych

Aby użyć procesu *Odroczone przetwarzanie ręcznego przesunięcia magazynowego*, skonfiguruj zaplanowane zadanie wsadowe.

1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Przetwarzanie zdarzeń aplikacji magazynu**.
1. W oknie dialogowym **Przetwarzanie zdarzeń aplikacji magazynowej** na skróconej karcie **Uruchom w tle ustaw** wartość opcji **Przetwarzanie wsadowe** na *Tak*.
1. Wybierz opcję **Cykl** i skonfiguruj harmonogram, który spełnia wymagania firmy.
1. W każdym oknie dialogowym kliknij **OK**.

## <a name="inquire-about-the-warehouse-app-events"></a>Uzyskiwanie informacji o zdarzeniach aplikacji magazynowej

Komunikaty dotyczące kolejki zdarzeń i zdarzeń, które są generowane przez aplikację magazynu, można przeglądać, przechodząc do **Zarządzanie magazynem \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Zdarzenia aplikacji magazynu**.

Komunikaty o zdarzeniu *Przesunięcie magazynowe* będą mieć stan *W kolejce*, gdy zostaną utworzone. Ten stan oznacza, że zadanie wsadowe **Przetwarzanie zdarzeń aplikacji magazynu** będzie pobierać i przetwarzać komunikaty o zdarzeniu. Gdy stan zostanie zmieniony na *Zakończone*, wszystkie powiązane ze sobą zdarzenia zostaną usunięte z kolejki.

Wszystkie zdarzenia *Przesunięcie magazynowe* są akumulowane w ramach jednej kolekcji według typu zdarzenia i magazynu.

Zadanie wsadowe będzie przetwarzać zdarzenia aplikacji magazynu zgodnie z cyklem ustawionym w oknie dialogowym **Przetwarzanie zdarzeń aplikacji magazynowej**. Dlatego do czasu przetworzenia komunikatu identyfikator magazynu można znaleźć w polu **Identyfikator**.

Szczegóły komunikatu zawierają szczegóły dotyczące przesunięcia (na przykład lokalizacje „od” i „do”).

Aby uzyskać więcej informacji, zobacz temat [Przetwarzania zdarzeń aplikacji magazynowej](warehouse-app-events.md).

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Konfigurowanie menu urządzenia przenośnego w celu pominięcia zasady odroczonego przetwarzania

Aby uzyskać szczegółowe informacje dotyczące sposobu konfigurowania menu urządzenia przenośnego w celu pomijania zasad odroczonego przetwarzania, zobacz temat [Odroczone przetwarzanie pracy magazynowej](deferred-put.md).

## <a name="impact-on-closed-work-dates"></a>Wpływ na zamknięte daty pracy

Aby uzyskać szczegółowe informacje dotyczące wpływu na zamknięte daty pracy, zobacz temat [Odroczone przetwarzanie pracy magazynowej](deferred-put.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Odroczone przetwarzanie pracy magazynowej](deferred-put.md)
- [Przetwarzanie zdarzenia aplikacji magazynu](warehouse-app-events.md)
- [Konfigurowanie urządzeń przenośnych do pracy magazynowej](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
