---
title: "Akcje dotyczące pracowników (często zadawane pytania)"
description: "Ten temat zawiera odpowiedzi na pytania, które mogą się pojawić, jeśli organizacja używa akcji dotyczących pracowników. Akcje dotyczące pracowników są to dodatkowe kroki, które należy wykonać podczas wykonywania pewnych zadań związanych z pracownikami."
author: shielas
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 4c17441b70a75f032c900c9360da6c0730cf89ba
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Akcje dotyczące pracowników (często zadawane pytania)
<a id="personnel-actions-faq" class="xliff"></a>
Ten temat zawiera odpowiedzi na pytania, które mogą się pojawić, jeśli organizacja używa akcji dotyczących pracowników. Akcje dotyczące pracowników są to dodatkowe kroki, które należy wykonać podczas wykonywania pewnych zadań związanych z pracownikami. Przykłady zadań, które mogą wymagać akcji dotyczących pracowników to zadania podczas tworzenia nowych stanowisk, modyfikowania istniejących wartości stanowisk, zatrudniania nowych pracowników, przenoszenia pracowników, zmiany wynagrodzenia pracownika, zmiany przypisania stanowiska lub zwalniania pracowników.

**Uwaga:** Akcje dotyczące pracowników są dostępne tylko wtedy, gdy wybrano klucz konfiguracji Akcje dotyczące pracowników. 

## Jak sprawdzić, czy moja organizacja potrzebuje akcji dotyczących pracowników?
<a id="how-can-i-tell-if-my-organization-requires-personnel-actions" class="xliff"></a>
Akcje dotyczące pracowników są wymagane przez organizację, jeśli zostanie wyświetlony monit, aby wybrać akcję dotyczącą pracowników podczas tworzenia nowych stanowisk, zmiany istniejących stanowisk, zatrudniania nowych pracowników, przenoszenia pracowników, zmiany wynagrodzenia pracownika, zmiany przypisania stanowiska, zwalniania pracowników lub wprowadzania urlopów dla pracowników. 

## Jaka jest różnica między akcją dotyczącą stanowisk i akcją dotyczącą pracownika?
<a id="what-is-the-difference-between-a-position-action-and-a-worker-action" class="xliff"></a>
Istnieją dwa typy akcji dotyczących pracowników:

- Akcja dotycząca stanowisk — Akcja dotycząca stanowisk jest wykonywana na istniejących lub nowych stanowiskach. Na przykład akcja dotycząca stanowisk może być wymagana w przypadku zmiany wartości na istniejącym stanowisku lub po utworzeniu nowego stanowiska sezonowego. Aby uzyskać szczegółowe informacje o używaniu akcji dotyczących stanowisk, zobacz temat Najważniejsze zadania: istniejące stanowiska pracownika lub temat Najważniejsze zadania: nowe stanowiska pracownika.

- Akcja dotycząca pracownika — Działanie dotyczące pracownika jest wykonywane na istniejących pracownikach lub na nowych pracownikach. Na przykład akcja dotycząca pracownika może być wymagana, gdy nowy pracownik zostaje zatrudniony lub przy awansowaniu istniejącego pracownika. Aby uzyskać szczegółowe informacje o używaniu akcji dotyczących pracownika, zobacz temat Przypisywanie akcji dotyczących pracowników do pracowników.

## Co oznaczają stany akcji dotyczących pracowników?
<a id="what-do-the-statuses-of-the-personnel-actions-mean" class="xliff"></a>
Akcje dotyczące pracowników mogą mieć następujące stany:

- **Wersja robocza** — Jeśli jest używany przepływ pracy, akcja nie została przesłana. Jeśli nie jest używany przepływ pracy, akcja nie została zakończona.
- **W trakcie przeglądu** — Akcja dotycząca pracowników została przesłana do przepływu pracy, ale przepływ pracy nie został zakończony.
- **Oczekujące na zatwierdzenie** — Przepływ pracy został ukończony, ale zmiany są nadal w toku. Anulowano — Przepływ pracy został anulowany lub akcję dotyczącą pracowników odwołano. Odrzucono — Żądanie akcji zostało odrzucone przez osobę zatwierdzającą.
- **Przetwarzanie akcji** — Żądanie akcji zostało zatwierdzone i zmiany są przetwarzane.
- **Przepływ pracy zakończony** — Przepływ pracy został ukończony i zmiany zostały przetworzone. Niepowodzenie — Przepływ pracy nie powiódł się, ponieważ informacje są nieaktualne. Kliknij przycisk Aktywuj ponownie, aby wyświetlić najnowsze informacje i kontynuować.
- **Ukończono** — Stanowisko zostało pomyślnie utworzone lub zmodyfikowane albo pracownik został pomyślnie zatrudniony, przeniesiony lub zwolniony, lub uległo zmianie jego wynagrodzenie. Błąd — Wystąpił inny problem niż ten, że informacje są nieaktualne. Otwórz dziennik komunikatów związanych z akcjami dotyczącymi pracowników, aby określić przyczynę błędu.
- **Odmowa** — Żądanie akcji zostało odrzucone przez osobę zatwierdzającą.

## Czy można usunąć akcję dotyczącą pracowników?
<a id="can-i-delete-a-personnel-action" class="xliff"></a>
Tak, można usuwać akcje dotyczące pracowników, które mają stan **Wersja robocza**, **Błąd**, **Niepowodzenie** lub **Anulowano**.

## Jak najszybciej można sprawdzić stan żądania akcji dotyczących pracowników?
<a id="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request" class="xliff"></a>
Otwórz jakiekolwiek strony listy akcji dotyczących pracowników i wybierz akcję dotyczącą pracowników.

## Co zrobić, jeśli żądanie akcji dotyczących pracowników nie powiedzie się?
<a id="what-should-i-do-if-a-personnel-action-request-fails" class="xliff"></a>
Jeśli żądanie akcji dotyczących pracowników nie powiedzie się, wykonaj następujące kroki w celu usunięcia błędu i ponownego przesłania żądania:

> 1. W **okienku akcji** kliknij przycisk **Tekst błędu**, aby wyświetlić tekst komunikatu, który opisuje problem.

> 2. W **okienku akcji** kliknij przycisk **Aktywuj ponownie**, aby załadować najnowsze informacje i ustawić stan akcji dotyczącej pracowników z powrotem na **Wersja robocza**.

> 3. Usuń błąd, a następnie kliknij przycisk **Zakończ** lub **Prześlij**.

## Co się dzieje z akcją dotyczącą pracowników, używającą przepływu pracy po zakończeniu ostatniego zatwierdzenia?
<a id="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed" class="xliff"></a>
Jeśli nie ma żadnych błędów, akcja dotycząca pracowników staje się akcją tylko do odczytu. (Można przejrzeć historię na stronie listy **Wszystkie akcje dotyczące pracownika**, ale nie można zmienić akcji dotyczącej pracowników). Gdy stan akcji dotyczących pracowników to **Ukończono**, rekord stanowiska lub pracownika został już zaktualizowany. Aby wyświetlić zmiany, które zostały przeprowadzone, otwórz stronę listy **Stanowiska** lub **Pracownicy**.

## Dlaczego wyświetlany jest następujący błąd podczas wprowadzania wartości różnej od zera w polu Stawka płacy? „Wartość jest poza prawidłowym zakresem — musi zawierać się w zakresie od 0,00 do 0,00”
<a id="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000" class="xliff"></a>
Ten komunikat jest wyświetlany, ponieważ pole Poziom w formularzu Zadanie jest puste dla zadania skojarzonego z wybranym stanowiskiem.

Aby rozwiązać ten problem, wykonaj następujące kroki:

> 1. W formularzu Przypisania pracowników do stanowisk kliknij pole Stanowisko.  
> 2. Kliknij wartość pola Zadanie, aby otworzyć stronę Zadanie.
> 3. W okienku akcji kliknij przycisk Edytuj.
> 4. Kliknij kartę Wynagrodzenie.
> 5. W polu Poziom wybierz poziom.
> 6. Zamknij stronę Zadanie.
> 7. Zamknij stronę Stanowisko.
> 8. Wróć do karty Wynagrodzenie na stronie Pracownik i wybierz opcję Stałe wynagrodzenie.  Kliknij przycisk Nowy i w polu Stanowisko wprowadź stanowisko pracownika.  Wprowadź wartość w polu Plan, a następnie w polu Stawka płacy wprowadź wynagrodzenia pracownika.

## Dlaczego nie można zmienić daty obowiązywania w nagłówku formularza akcji dotyczącej pracowników?
<a id="why-cant-i-change-the-effective-date-in-the-header-of-the-worker-action-form" class="xliff"></a>
Daty wejścia w życie nie można zmienić, ponieważ to pole jest wypełniane przy użyciu najbardziej logicznej daty dla tego typu akcji.

Na przykład:

- Data wejścia w życie w nagłówku akcji **Zwolnij pracownika** jest datą wprowadzoną w polu **Data zakończenia**.
- Data wejścia w życie w akcji **Zatrudnij pracownika** jest datą wprowadzoną w polu **Data zatrudnienia**.
- Data wejścia w życie w akcji **Przenieś pracownika** jest datą wprowadzoną w polu **Data rozpoczęcia przypisania** dla pracownika.

