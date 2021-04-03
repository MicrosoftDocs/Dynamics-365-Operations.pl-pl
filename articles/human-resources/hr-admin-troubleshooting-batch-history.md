---
title: Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia
description: W tym artykule wyjaśniono, jak rozwiązywać pewne problemy z wydajnością w Microsoft Dynamics 365 Human Resources, czyszcząc historię zadań wsadowych.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 8fef2152f7c65a6678e6cb94da8ea2bbe99ea51d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466695"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Wystawienie**

Microsoft Dynamics 365 Human Resources może napotkać problemy z wydajnością, jeśli historia zadania wsadowego rozrasta się zbyt dużą.

**Powód**

Często wykonywane zadania wsadowe mogą prowadzić do nietrwałego wzrostu historii zadań wsadowych. Może to spowodować problemy z wydajnością. 

**Rozdzielczość**

Umożliwia zaplanowanie automatycznego zadania w celu oczyszczenia historii zadania wsadowego. Zalecamy skonfigurowanie zadania, aby było uruchamiane co tydzień, ale może być konieczne ręczne uruchomienie procesu oczyszczania w zależności od używanego środowiska. Poniższa procedura zawiera zalecane ustawienia, ale można je zmienić zgodnie z potrzebami użytkownika.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Na pasku **wyszukiwania** wprowadź **oczyszczanie historii zadań wsadowych**.

   ![Wyszukaj okresowe oczyszczanie historii zadań wsadowych](media/talent-batch-history-cleanup-search-bar.png)

3. W polu **Limit historii (dni)** wprowadź **30**.

   ![Ustaw limit historii 30](media/talent-batch-history-cleanup-history-limit.png)

4. Wybierz **Uruchom w tle**, a następnie **Cykl**.

   ![Ustaw cykl](media/talent-batch-history-cleanup-recurrence.png)

5. W obszarze **Zdefiniujcykl** ustaw **datę rozpoczęcia** i **godzinę rozpoczęcia** w godzinach poza godziną lub weekendu, a następnie wybierz opcję **brak daty zakończenia**. 

   ![Definiowanie daty i godziny rozpoczęcia](media/talent-batch-history-cleanup-define-recurrence.png)

6. W **wzorzec cyklu** wybierz **dni**, a następnie ustaw opcję **Powtarzaj po określonym przedziale** na **7**.

   ![Ustawienie oczyszczania powoduje powtarzanie tygodnia](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Kliknij przycisk **OK**.

8. W razie potrzeby zmień dowolne inne parametry w obszarze **Uruchom w tle**, a następnie wybierz przycisk **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]