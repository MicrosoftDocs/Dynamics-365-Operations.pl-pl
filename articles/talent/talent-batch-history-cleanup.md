---
title: Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia
description: W tym temacie wyjaśniono, jak rozwiązywać pewne problemy z wydajnością w Microsoft Dynamics 365 Talent, czyszcząc historię zadań wsadowych.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 1e9d237817024800ad9880ec58db3505ac1c493f
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2027091"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia

[!include [banner](../includes/banner.md)]

**Wystawienie**

Microsoft Dynamics 365 Talent może napotkać problemy z wydajnością, jeśli historia zadania wsadowego rozrasta się zbyt dużą.

**Powód**

Często wykonywane zadania wsadowe mogą prowadzić do nietrwałego wzrostu historii zadań wsadowych. Może to spowodować problemy z wydajnością. 

**Rozdzielczość**

Umożliwia zaplanowanie automatycznego zadania w celu oczyszczenia historii zadania wsadowego. Zalecamy skonfigurowanie zadania, aby było uruchamiane co tydzień, ale może być konieczne ręczne uruchomienie procesu oczyszczania w zależności od używanego środowiska. Poniższa procedura zawiera zalecane ustawienia, ale można je zmienić zgodnie z potrzebami użytkownika.

1. W talentów wybierz opcję **Administracja systemu**.

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

