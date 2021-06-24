---
title: Wyświetlanie dzienników historii i planowania planów
description: W tym temacie opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187254"
---
# <a name="view-plan-history-and-planning-logs"></a>Wyświetlanie dzienników historii i planowania planów

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania w Microsoft Dynamics 365 Supply Chain Management.

Aby wyświetlić historię planu, należy otworzyć plan, przechodząc do **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne** i wybierając opcję **historia**. Historia zawiera listę wszystkich zadań wybranego planu. Lista zawiera zakończone i aktywne zadania.

Historia zadań dla przebiegów planowania nadrzędnego Optymalizacja planowania zachowuje tylko do 60 rekordów dla każdego planu nadrzędnego. Przy każdym uruchomieniu nowego obliczenia planu głównego usuwany jest najwcześniejszy zapis historii tego planu.

Oprócz wyświetlania czasu rozpoczęcia i stanu zadań można wyświetlać dziennik dla określonego zadania. Dziennik zawiera dodatkowe informacje i ostrzeżenia. Nie wszystkie zadania mają dziennik. Aby wyświetlić dziennik zadania, wybierz opcję **dziennik**. Wpisy w dzienniku są przechowywane tylko przez 30 dni od daty zakończenia zadania, po tym czasie są automatycznie usuwane.

## <a name="related-resources"></a>Powiązane zasoby

- [Omówienie optymalizacji planowania](planning-optimization-overview.md)
- [Rozpoczęcie optymalizacji planowania](get-started.md)
- [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)
- [Stosowanie filtrów do planu](plan-filters.md)
- [Anuluj planowanie pracy](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]