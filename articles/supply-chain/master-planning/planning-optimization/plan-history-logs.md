---
title: Wyświetlanie dzienników historii i planowania planów
description: W tym artykule opisano sposób wyświetlania historii zadań planowania.
author: t-benebo
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: ab469686a009364bf53cb963506fd2107075a283
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740939"
---
# <a name="view-plan-history-and-planning-logs"></a>Wyświetlanie dzienników historii i planowania planów

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób wyświetlania historii zadań planowania w Microsoft Dynamics 365 Supply Chain Management.

Aby wyświetlić historię planu, należy otworzyć plan, przechodząc do **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne** i wybierając opcję **historia**. Historia zawiera listę wszystkich zadań wybranego planu. Lista zawiera zakończone i aktywne zadania.

System przechowuje maksymalnie 60 rekordów historii według planu głównego i usuwa rekordy starsze niż 30 dni. Przy każdym uruchomieniu nowego głównego obliczenia planistycznego system dodaje nowy rekord historii, a następnie w razie potrzeby czyści najstarsze rekordy.

Oprócz wyświetlania czasu rozpoczęcia i stanu zadań można wyświetlać dziennik dla określonego zadania. Dziennik zawiera dodatkowe informacje i ostrzeżenia. Nie wszystkie zadania mają dziennik. Aby wyświetlić dziennik zadania, wybierz opcję **dziennik**. Wpisy w dzienniku są przechowywane tylko przez 30 dni od daty zakończenia zadania, po tym czasie są automatycznie usuwane.

Jeśli opcja **Przetwarzanie wsadowe** na karcie **Uruchom w tle** FastTab była włączona podczas konfigurowania głównego przetwarzania planowania, dziennik zadania wsadowego zawiera więcej informacji o ostrzeżeniach i błędach, które zostały wygenerowane podczas przetwarzania głównego planowanie przebiegu. Na przykład błędy automatycznego potwierdzania są przechwytywane tylko w dzienniku zadania wsadowego. Nie są one wyświetlane w dziennikach na stronie **Historia**.

Aby wyświetlić błędy automatycznego potwierdzania i inne ostrzeżenia lub błędy, które wystąpiły podczas głównego przebiegu planowania, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Administrowanie systemem \> Zapytania \> Zadania wsadowe**.
1. Znajdź i wybierz rekord reprezentujący przebieg planowania głównego, który Cię interesuje. (Na przykład wartość pola **Opis stanowiska** może zaczynać się od *Planowanie główne*.)
1. Wykonaj jedną z tych czynności, w zależności od tego, czy używasz *rozszerzonego formularza* czy *starszego (nierozszerzonego) formularza* na stronie **Zadania wsadowe**:

    - Jeśli używasz rozszerzonego formularza: w okienku akcji wybierz historię **Zadań wsadowych**. Następnie na stronie **Historia zadań wsadowych** w okienku akcji wybierz **Dziennik**.
    - Jeśli używasz starszego formularza: w okienku akcji na karcie **Zadanie wsadowe** wybierz **Dziennik**.

1. Wybierz **Szczegóły wiadomości**, by otworzyć okienko **Szczegóły wiadomości**, w którym możesz wyświetlić wszystkie ostrzeżenia i błędy zarejestrowane podczas przetwarzania.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
