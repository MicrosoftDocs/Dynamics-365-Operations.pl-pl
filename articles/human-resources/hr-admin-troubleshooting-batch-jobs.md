---
title: Optymalizowanie wydajności – planowanie zadań wsadowych po godzinach pracy
description: W tym temacie wyjaśniono, jak rozwiązywać pewne problemy z wydajnością w Microsoft Dynamics 365 Human Resources poprzez planowanie długotrwałych zadań wsadowych po godzinach pracy.
author: andreabichsel
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 92dd281ed718be5c7ebd843d015c108ee121f30a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794932"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Optymalizowanie wydajności – planowanie zadań wsadowych po godzinach pracy

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a>Wystawienie

Microsoft Dynamics 365 Human Resources może napotkać problemy z wydajnością, jeśli długotrwałe zadania wsadowe są uruchamiane podczas godzin pracy w firmie.

## <a name="resolution"></a>Rozdzielczość

Zaplanuj następujące zadania wsadowe po godzinach pracy. Zalecamy również przejrzenie częstotliwości zadań wsadowych, które są często wykonywane. Jeśli to możliwe, zmniejsz cykl powtarzalności dla zadania wsadowego. W wielu przypadkach wystarcza domyślna częstotliwość.

Poniższe zadania wsadowe powinny być uruchamiane w nocy lub po godzinach. Należy sprawdzić strefę czasową cyklicznych zadań wsadowych. Niektóre zadania wsadowe mogą wykorzystywać standardowy czas pacyficzny (PST).

| Zadanie przetwarzania wsadowego | Domyślna powtarzalność |
| --- | --- |
| Czyszczenie historii zadań wsadowych | 1 raz na miesiąc |
| Eksportuj czyszczenie danych pośrednich | 1 raz na dzień |
| Synchronizacja pominiętych żądań integracji usługi Common Data Service | 1 raz na dzień |
| Zadanie systemowe kompresji bazy danych, które musi działać regularnie po godzinach pracy | 1 raz na dzień |
| Zadanie systemowe odbudowania indeksu bazy danych, które musi działać regularnie po godzinach pracy | 1 raz na dzień |

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Na pasku **Wyszukiwania** wyszukaj jedno z powyższych zadań wsadowych.

3. Wybierz **Uruchom w tle**, a następnie **Cykl**.

   ![Ustaw cykl](media/talent-batch-history-cleanup-recurrence.png)

4. W obszarze **Zdefiniuj cykl** ustaw **datę rozpoczęcia** i **godzinę rozpoczęcia** na czas poza godzinami pracy lub weekend. Wybierz **Brak daty zakończenia**. 

   ![Definiowanie daty i godziny rozpoczęcia](media/talent-batch-history-cleanup-define-recurrence.png)

5. Kliknij przycisk **OK**.

6. W razie potrzeby zmień dowolne inne parametry w obszarze **Uruchom w tle**, a następnie wybierz przycisk **OK**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]