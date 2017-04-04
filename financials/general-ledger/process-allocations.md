---
title: Przetwarzanie alokacji
description: "Ten artykuł zawiera informacje o alokacji, opcje przetwarzania ich w usłudze Microsoft Dynamics 365 dla operacji i jak mogą być używane w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że przychody lub wydatki obciążają odpowiednie obiekty podczas księgowania."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 37f4df5d0b79208a8c565bc9101ddde193a6ef5b
ms.lasthandoff: 03/31/2017


---

# <a name="process-allocations"></a>Przetwarzanie alokacji

Ten artykuł zawiera informacje o alokacji, opcje przetwarzania ich w usłudze Microsoft Dynamics 365 dla operacji i jak mogą być używane w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że przychody lub wydatki obciążają odpowiednie obiekty podczas księgowania.

Microsoft Dynamics 365 dla operacji zawiera następujące funkcje do obsługi tego procesu:

-   Ręcznie przydzielić kwoty transakcji przy użyciu akcji Podziel w zasady podziału księgowań lub przy zastosowaniu domyślnych szablonów wymiaru finansowego do dokumentu. Aby uzyskać więcej informacji, zobacz [zasady podziału księgowań.](\accounts-payable\accounting-distributions.md)
-   Automatyczne przydzielanie kwot transakcji na podstawie warunków alokacji zdefiniowanych na poszczególnych kontach głównych. Zapisy na koncie alokacji zostaną wygenerowane dla każdego arkusza według wartości procentowej i docelowego konta księgowego zawsze gdy zapis księgowy spełnia kryteria określone jako konto księgowe źródła.
-   Automatyczne przydzielanie sald księgi lub stałych kwot na podstawie reguł alokacji księgi. Reguły alokacji księgi są przetwarzane w regularnych odstępach przy użyciu arkuszy alokacji. 

###  <a name="allocations-in-budget-planning"></a>Alokacje w planowaniu budżetu

Reguły alokacji księgi mogą służyć do obsługi planów budżetowych. Korzystając z reguł alokacji księgi do planowania budżetu, reguły alokacji działają tak samo jak w księdze, ale źródło danych oraz miejsce docelowe danych pochodzi z planu budżetu. Można ręcznie wybrać reguły alokacji księgi do użycia dla planów budżetu. Można także użyć harmonogramu alokacji, który jest uruchamiany jako część procesu przepływu pracy.

> [!NOTE]
> Nie można użyć międzyfirmowych reguł alokacji księgi dla planów budżetu.




