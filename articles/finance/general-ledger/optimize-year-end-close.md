---
title: Optymalizacja zamknięcia na koniec roku
description: W tym artykule opisano dodatek Optymalizowanie usługi zamknięcia roku, który jest dostępny w procesie zamknięcia na koniec roku księgi głównej.
author: moaamer
ms.date: 12/02/2022
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
ms.openlocfilehash: bc6ab7e36f37707442f8d5d5b6e0d5f5d42e2171
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831537"
---
# <a name="optimize-year-end-close"></a>Optymalizacja zamknięcia na koniec roku 

Dodatek Optymalizowanie usługi zamknięcia roku dla Microsoft Dynamics 365 Finance umożliwia uruchomienie przetwarzania zamknięcia na koniec roku poza wystąpieniem serwera obiektów aplikacji (AOS) dla zasobów finansowych usługi Dynamics 365. Korzysta z technologii mikrousługi. Korzyści, które wiążą się z funkcjonalnością Optymalizacja zamknięcia roku to poprawa wydajności i minimalizacja wpływu na bazę danych SQL podczas przetwarzania zamknięcia roku.

>[!NOTE]
> Zoptymalizowane zamknięcie roku jest dostępne w wersji 10.0.31 Microsoft Dynamics 365 Finance. Ta funkcja została przeniesiona do wersji Dynamics Finance 10.0.30 i 10.0.29, dlatego należy skorzystać z najnowszej aktualizacji jakości.   

Aby korzystać z funkcji Optymalizowanie zamknięcia na koniec roku, należy wykonać następujące zadania:

1. Zainstaluj dodatek Optymalizacja zamknięcia roku dla usługi zamknięcia z swojego projektu w usłudze Microsoft Dynamics Lifecycle Service.
2. Włącz funkcję **Optymalizowanie zamknięcia na koniec roku** w zarządzaniu funkcjami.

> [!NOTE]
> W przypadku Finance nadal można korzystać z bieżącej funkcji zamknięcia na koniec roku, wyłączając funkcję **Optymalizowanie zamknięcia na koniec roku** w zarządzaniu funkcjami.

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

[![Kolumny Wyniki i Stan na stronie Zamknięcie na koniec roku.](./media/Optimize-year-end-close-Image3.png)](./media/Optimize-year-end-close-Image3.png)

Ponadto po włączeniu funkcji **Optymalizowanie zamknięcia na koniec roku** na stronie szablonu **Zamknięcia na koniec roku** staje się dostępna skrócona karta **Wymiarów finansowych bilansu**. Ta skrócona karta umożliwia szczegółowe określenie wymiarów finansowych bilansu podczas zamykania roku. Ta możliwość jest równoległa do funkcji, która jest już dostępna dla kont wynikowych.

[![Skrócona karta Wymiary finansowe bilansu](./media/Optimize-year-end-close-Image4.png)](./media/Optimize-year-end-close-Image4.png)

## <a name="architecture-and-data-flow"></a>Architektura i przepływ danych

Aby użyć funkcji **Optymalizowanie zamknięcia na koniec roku** i uruchomić zamknięcie na koniec roku dla mikrousługi, musisz zainstalować dodatek **Optymalizowanie usługi zamknięcia na koniec roku** z usługi Lifecycle Services, a następnie włączyć funkcję **Optymalizowanie zamknięcia na koniec roku** w zarządzaniu funkcjami.

Jak pokazano na poniższej ilustracji, przetwarzanie zamknięcia na koniec roku sprawdza, czy dodatek jest zainstalowany i czy ta funkcja jest włączona. Jeśli są spełnione oba warunki wstępne, zamknięcie na koniec roku jest uruchamiane dla mikrousługi.

[![Diagram przepływu danych.](./media/Optimize-year-end-close-Image5.png)](./media/Optimize-year-end-close-Image5.png)

## <a name="high-level-flow-for-year-end-close-processing"></a>Przepływ wysokiego poziomu przetwarzania zamknięcia na koniec roku

1. Proces zamknięcia na koniec roku rozpoczyna się w **Księga główna \> Zamykanie okresu \> Zamknięcie roku**. Proces tworzy zadania wsadowe zamknięcia i zadania dla zamykanych firm.
2. Zamknięcie na koniec roku określa, czy zamknięcie na koniec roku powinno być uruchamiane dla mikrousługi, czy dla bieżącej logiki zamknięcia.

    - Jeśli dodatek usługi **Optymalizacja zamknięcia roku** jest zainstalowany w Lifecycle Services, a funkcja **Optymalizacja zamknięcia roku** jest włączona w zarządzaniu funkcjami, zamknięcie roku zostanie uruchomione w mikrousłudze.

        1. Funkcja Optymalizowanie zamknięcia na koniec roku tworzy zadanie usługi zamknięcia na koniec roku dla każdej zamykanej firmy, a następnie uruchamia logikę zamknięcia na koniec roku. Mikrousługa wykonuje zamknięcie na koniec roku.
        2. Finanse nasłuchują do zamknięcia na koniec roku dla mikrousługi, aby ustalić, kiedy mikrousługa jest zakończona. Wyniki zamknięcia na koniec roku są aktualizowane na stronie **Zamknięcie na koniec roku** w Finance.

    - W przeciwnym razie zamknięcie na koniec roku będzie uruchamiane przy bieżącej logice zamknięcia.
