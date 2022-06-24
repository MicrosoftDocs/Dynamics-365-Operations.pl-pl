---
title: Wyświetlanie dzienników historii i planowania planów
description: W tym artykule opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania.
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
ms.openlocfilehash: b2c9257fc67a06b57418b2f5b035b2b540131405
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863948"
---
# <a name="view-plan-history-and-planning-logs"></a>Wyświetlanie dzienników historii i planowania planów

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania w Microsoft Dynamics 365 Supply Chain Management.

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

## <a name="related-resources"></a>Powiązane zasoby

- [Omówienie optymalizacji planowania](planning-optimization-overview.md)
- [Rozpoczęcie optymalizacji planowania](get-started.md)
- [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)
- [Stosowanie filtrów do planu](plan-filters.md)
- [Anuluj planowanie pracy](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
