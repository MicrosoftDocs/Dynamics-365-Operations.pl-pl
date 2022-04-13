---
title: Wyświetlanie dzienników historii i planowania planów
description: W tym temacie opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania.
author: t-benebo
ms.date: 10/30/2019
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
ms.openlocfilehash: 9b4cba4dd94eb198e770d152d4f759a706065dee
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469765"
---
# <a name="view-plan-history-and-planning-logs"></a>Wyświetlanie dzienników historii i planowania planów

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania w Microsoft Dynamics 365 Supply Chain Management.

Aby wyświetlić historię planu, należy otworzyć plan, przechodząc do **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne** i wybierając opcję **historia**. Historia zawiera listę wszystkich zadań wybranego planu. Lista zawiera zakończone i aktywne zadania.

Historia zadań dla przebiegów planowania nadrzędnego Optymalizacja planowania zachowuje tylko do 60 rekordów dla każdego planu nadrzędnego. Przy każdym uruchomieniu nowego obliczenia planu głównego usuwany jest najwcześniejszy zapis historii tego planu.

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
