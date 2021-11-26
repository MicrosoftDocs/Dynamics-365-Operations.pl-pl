---
title: Planowanie drukowania etykiety grupy czynności podczas grupy czynności
description: W tym temacie opisano sposób konfigurowania i używania funkcji drukowania etykiet grup czynności w oparciu o zadania.
author: MSFTGarm
ms.date: 06/09/2021
ms.topic: article
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-obaranov
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 4883f8a548645436e17b933d87d4ee6330570d48
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777872"
---
# <a name="schedule-wave-label-printing-during-wave"></a>Planowanie drukowania etykiety grupy czynności podczas grupy czynności

[!include [banner](../../includes/banner.md)]

Funkcja *Drukowanie etykiet grup czynności w oparciu o zadania* jest częścią procesu grup czynności, która pomaga zwiększyć wydajność oraz umożliwia systemowi tworzenie etykiet grup czynności i pracę w oddzielnych zadaniach.

Proces konfigurowania drukowania etykiet na fali jest złożony i zależy od dokładnej konfiguracji i danych głównych. Nie jest rzadkością, że generowanie rekordów etykiet grup czynności nie powiedzie się, a gdy tak się stanie, całe przetwarzanie grup czynności jest cofane. Funkcja *drukowania etykiet grupy czynności oparta na zadaniu* pomaga uniknąć ponownego tworzenia pracy i wierszy pracy po każdym niepoprawnym wydrukowaniu etykiety grupy czynności.

W przypadku korzystania z funkcji *drukowania etykiet grupy czynności opartej na zadaniu* system najpierw tworzy pracę i wiersze pracy. Następnie tworzy i drukuje etykiety grupy czynności. Jeśli etykiety grupy czynności zostały prawidłowo utworzone, zwalnia ona pracę i grupy czynności do pobrania.

## <a name="turn-on-the-task-based-wave-label-printing-feature-in-feature-management"></a>Włącz funkcję drukowania etykiet grupy czynności na podstawie zadania w zarządzaniu funkcjami

Aby korzystać z funkcji opisanych w tym temacie, należy je włączona dla systemu. Użyj obszaru roboczego [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) włącz następujące funkcje w kolejności:

1. *Drukowanie etykiety grupy czynności* – funkcja wymagana do włączenia metody przetwarzania grupy czynności na potrzeby drukowania etykiet grupy czynności.
1. *Blokowanie pracy w całej organizacji* — wymagana funkcja zarówno do ręcznej, jak i automatycznej konfiguracji tworzenia zaplanowanych prac. (W przypadku Supply Chain Management w wersji 10.0.21 ta funkcja jest obowiązkowa, więc jest domyślnie włączona i nie można jej ponownie wyłączyć).
1. *Drukowanie etykiet grupy czynności opartych na zadaniu* — ta funkcja jest wymagana do rozdzielenia drukowania etykiet grupy czynności na oddzielny zakres transakcji.

## <a name="manually-enable-the-new-wave-step-method"></a>Ręcznie włącz nową metodę kroku grupy czynności

Rozpocznij od utworzenia nowej metody kroku grupy czynności i włączenia jej do równoległego przetwarzania zadań asynchronicznych.

1. Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Metody procesów grupy czynności**.
1. W okienku akcji wybierz pozycję **Ponownie utwórz metodę**. Należy zauważyć, że *waveLabelPrinting* zostało dodane do listy metod przetwarzania grupy czynności, których można używać w szablonach grupy czynności wysyłki.
1. Wybierz rekord, w którym w polu **Nazwa metody** jest ustawiona wartość *waveLabelPrinting*, a następnie w okienku akcji wybierz **konfigurację zadania**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Magazyn** — umożliwia wybranie magazynu, który ma być podstawą do zaplanowania przetwarzania tworzenia pracy. (Jeśli do testowania są wykorzystywane dane demonstracyjne, można wybrać magazyn *24*).
    - **Maksymalna liczba zadań wsadowych** — umożliwia określenie maksymalnej liczby zadań wsadowych. W większości przypadków wartość musi być z wartości od *8* do *16*. Zaleca się jednak eksperymentowanie w celu znalezienia optymalnych ustawień dla scenariuszy.
    - **Grupa przetwarzania wsadowego grupy czynności** — wybierz dedykowaną grupę przetwarzania grupy czynności w celu zoptymalizowania przetwarzania wsadowego.

Istniejący szablon grupy czynności można teraz zaktualizować, tak aby był on używany z metodą przetwarzania grupy czynności *drukowania etykiet grupy czynności*. Można również utworzyć nowy szablon grupy czynności, który go używa.

1. Wybierz kolejno opcje  **Zarządzanie magazynem \> Ustawienia \> Grupy czynności \> Szablony grupy czynności**.
1. W okienku akcji wybierz pozycję **Edytuj**.
1. W lewym okienku wybierz szablon grupy czynności do aktualizacji. (Jeśli do testowania są wykorzystywane dane demonstracyjne, można wybrać magazyn *24 Domyślna wysyłka*).
1. Na skróconej karcie **Metody** w kolumnie **Pozostałe metody** wybierz wiersz, w którym pole **Nazwa** ma wartość *waveLabelPrinting*.
1. Korzystaj z przycisku Strzałka w prawo – **dodaj** – aby przesunąć wybrany wiersz na kolumnę **Wybrane metody**.
1. W polu **Kod kroku grupy czynności** wprowadź kod kroku grupy czynności, który będzie używany do łączenia szablonu grupy czynności z szablonem etykiety grupy czynności.

## <a name="set-wave-task-processing-threshold-data"></a>Ustaw dane progowe przetwarzania zadań grupy czynności

Przy pierwszym uruchomieniu procesu grupy czynności z wykorzystaniem przetwarzania opartego na zadaniach system tworzy domyślne dane progowe przetwarzania zadań grupy czynności. Dane służą do kontrolowania, czy przetwarzanie grupy czynności będzie wykonywane asynchronicznie i będzie oparte na zadaniach, co pozwala na równoległe przetwarzanie i tworzenie grup czynności.

Dane domyślne początkowo korzystają z wartości progowej *1* dla minimalnej liczby wierszy ładunku (`MinimumWorkThresholdForLabelPrinting`). Dlatego, gdy system przetwarza grupy czynności, która ma więcej niż jeden identyfikator pracy, będzie korzystać z przetwarzania etykiet grupy czynności w osobnej transakcji. Te dane można wstawiać/aktualizować ręcznie `WHSWaveTaskProcessingThresholdParameters` w tabeli w środowiskach testowych. Jeśli musisz zmienić to ustawienie w środowisku produkcyjnym, musisz skontaktować się z pomocą techniczną firmy Microsoft, aby zażądać aktualizacji.

## <a name="changes-to-the-wave-processing-logic-when-task-based-wave-label-printing-is-used"></a>Zmiany logiki przetwarzania grupy czynności w przypadku korzystania z drukowania etykiet grupy czynności na podstawie zadania

Jeśli przetwarzanie etykiet grupy czynności przekracza próg przetwarzania zadania grupy czynności, inicjowane jest przetwarzanie oparte na zadaniu. W następnym przetwarzaniu grupy czynności, który pasuje do szablonu grupy czynności, drukowanie etykiet grupy czynności zostanie uruchomione w autonomicznej transakcji *ttsbegin*/*ttscommit* natychmiast po utworzeniu pracy. Jeśli w szablonie grupy czynności skonfigurowano automatyczne uruchamianie zwolnienia pracy (odblokowania), ma ono miejsce dopiero po pomyślnym zakończeniu procesu drukowania etykiety grupy czynności.

Jeśli generowanie etykiety grupy czynności nie powiedzie się (na przykład, jeśli konwersja ilości pracy na ilość etykiety grupy czynności nie powiedzie się i zostanie zgłaszany błąd), tylko odpowiednia transakcja nie powiedzie się. Wcześniej utworzona praca pozostaje zamrożona. Aby poprawić błędy i wydrukować etykiety grupy czynności, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie magazynem \> Wychodzące grupy czynności \> Grupy czynności wysyłki \> Wszystkie grupy czynności**.
1. Wybierz odpowiedniej grupy czynności w siatce.
1. W okienku akcji na karcie **Grupa czynności** w grupie **Drukuj** wybierz opcję **Etykiety grup czynności**.
1. Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie, aby wysłać etykiety do wydrukowania.
1. W okienku akcji, na karcie **Grupa czynności**, w grupie **Grupy czynności** wybierz pozycję **Zwolnij**, aby ręcznie zwolnić pracę dla wybranej grupy czynności.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Drukowanie etykiety grupy czynności](configure-wave-label-printing.md)
- [Tworzenie planu pracy podczas grupy czynności](configure-wave-schedule-work-creation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
