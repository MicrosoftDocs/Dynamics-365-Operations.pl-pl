---
title: Optymalizacja zamknięcia na koniec roku
description: W tym artykule opisano dodatek Optymalizowanie usługi zamknięcia roku, który jest dostępny w procesie zamknięcia na koniec roku księgi głównej.
author: moaamer
ms.date: 11/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2022-11-28
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 41d0c2975341cf3d612cc36be348326e24e94f1b
ms.sourcegitcommit: 707957bb7bcd98faf2600eff1c98067901a0fb73
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/08/2022
ms.locfileid: "9750014"
---
# <a name="optimize-year-end-close"></a>Optymalizacja zamknięcia na koniec roku

Dodatek Optymalizowanie usługi zamknięcia roku dla Microsoft Dynamics 365 Finance umożliwia uruchomienie przetwarzania zamknięcia na koniec roku poza wystąpieniem serwera obiektów aplikacji (AOS) dla zasobów finansowych usługi Dynamics 365. Korzysta z technologii mikrousługi. Korzyści, które wiążą się z funkcjonalnością Optymalizacja zamknięcia roku to poprawa wydajności i minimalizacja wpływu na bazę danych SQL podczas przetwarzania zamknięcia roku.

Aby korzystać z funkcji Optymalizowanie zamknięcia na koniec roku, należy wykonać następujące zadania:

1. Zainstaluj dodatek Optymalizacja zamknięcia roku dla usługi zamknięcia z swojego projektu w usłudze Microsoft Dynamics Lifecycle Service.
2. Włącz funkcję **Optymalizowanie zamknięcia na koniec roku** w zarządzaniu funkcjami.

> [!NOTE]
> W przypadku zasobów finansowych nadal można korzystać z bieżącej funkcji zamknięcia na koniec roku, wyłączając funkcję **Optymalizowanie zamknięcia na koniec roku** w zarządzaniu funkcjami.

## <a name="improved-performance"></a>Zwiększona wydajność

Funkcja **Optymalizowanie zamknięcia na koniec roku** została zaprojektowana w celu przyspieszenia przetwarzania zamknięcia na koniec roku, zwłaszcza w przypadku klientów, którzy mają duże ilości danych. Gdy zamknięcie na koniec roku jest wykonywane dla usługi, obciążenie zasobów Finance jest odsłaniane w celu skrócenia czasu przetwarzania i usunięcia zasobów, które mogą wpłynąć na codzienne operacje innych użytkowników.

Funkcja **Optymalizowanie zamknięcia na koniec roku** może pomóc w osiągnięciu następujących celów:

- Skrócenie czasu wykonywania zwiększa wydajność zamknięcia na koniec roku.
- Zmniejszenie wpływu na inne procesy podczas zamykania roku.
- Usprawnij raportowanie i korekty dotyczące wyników na koniec roku, ponieważ zamykanie na koniec roku zajmuje mniej czasu.

## <a name="new-options-and-visibility"></a>Nowe opcje i widoczność

Gdy jest włączona funkcja **Optymalizowanie zamknięcia** na koniec roku, w następujących miejscach są dodawane dwie nowe kolumny: **Wyniki** i **Stan**:

- Na stronie **Zamknięcie roku**
- W oknie dialogowym **Wyniki zamknięcia na koniec** roku
- W opcjach **przeniesienia wymiaru finansowego bilansu** na stronie **szablonu zamknięcia na koniec roku**

Na poniższej ilustracji pokazano przykład kolumn **Wyniki** i **Stan** na stronie **Zamknięcie na koniec** roku. Możesz zaznaczyć łącze **Wyświetl wyniki** w kolumnie **Wyniki**, aby otworzyć wyniki zamknięcia na koniec roku. W kolumnie **Stan** jest przedstawiany bieżący stan procesu zamknięcia na koniec roku. Dzięki temu nowe kolumny będą widoczne w postępie procesu zamknięcia na koniec roku.

[![Kolumny Wyniki i Stan na stronie Zamknięcie na koniec roku.](./media/Yearendclose.jpg)](./media/Yearendclose.jpg)

Ponadto po włączeniu funkcji **Optymalizowanie zamknięcia na koniec roku** na stronie szablonu **Zamknięcia na koniec roku** staje się dostępna skrócona karta **Wymiarów finansowych bilansu**. Ta skrócona karta umożliwia szczegółowe określenie wymiarów finansowych bilansu podczas zamykania roku. Ta możliwość jest równoległa do funkcji, która jest już dostępna dla kont wynikowych.

## <a name="architecture-and-data-flow"></a>Architektura i przepływ danych

Aby użyć funkcji **Optymalizowanie zamknięcia na koniec roku** i uruchomić zamknięcie na koniec roku dla mikrousługi, musisz zainstalować dodatek Optymalizowanie usługi zamknięcia na koniec roku z usługi Lifecycle Services, a następnie włączyć funkcję **Optymalizowanie zamknięcia na koniec roku** w zarządzaniu funkcjami.

Jak pokazano na poniższej ilustracji, przetwarzanie zamknięcia na koniec roku sprawdza, czy dodatek jest zainstalowany i czy ta funkcja jest włączona. Jeśli są spełnione oba warunki wstępne, zamknięcie na koniec roku jest uruchamiane dla mikrousługi.

[![Diagram przepływu danych.](./media/Lifecycle-services.jpg)](./media/Lifecycle-services.jpg)

## <a name="high-level-flow-for-year-end-close-processing"></a>Przepływ wysokiego poziomu przetwarzania zamknięcia na koniec roku

1. Proces zamknięcia na koniec roku rozpoczyna się w **Księga główna \> Zamykanie okresu \> Zamknięcie roku**. Proces tworzy zadania wsadowe zamknięcia i zadania dla zamykanych firm.
2. Zamknięcie na koniec roku określa, czy zamknięcie na koniec roku powinno być uruchamiane dla mikrousługi, czy dla bieżącej logiki zamknięcia.

    - Jeśli dodatek usługi Optymalizacja zamknięcia roku jest zainstalowany w Lifecycle Services, a funkcja **Optymalizacja zamknięcia roku** jest włączona w zarządzaniu funkcjami, zamknięcie roku zostanie uruchomione w mikrousłudze.

        1. Funkcja Optymalizowanie zamknięcia na koniec roku tworzy zadanie usługi zamknięcia na koniec roku dla każdej zamykanej firmy, a następnie uruchamia logikę zamknięcia na koniec roku. Mikrousługa wykonuje zamknięcie na koniec roku.
        2. Finanse nasłuchują do zamknięcia na koniec roku dla mikrousługi, aby ustalić, kiedy mikrousługa jest zakończona. Wyniki zamknięcia na koniec roku są aktualizowane na stronie **Zamknięcie na koniec roku** w Finance.

    - W przeciwnym razie zamknięcie na koniec roku będzie uruchamiane przy bieżącej logice zamknięcia.
