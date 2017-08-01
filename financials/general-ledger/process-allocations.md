---
title: Przetwarzanie alokacji
description: "Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że przychody lub wydatki obciążają odpowiednie obiekty podczas księgowania."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: e6d88503972850f6163aba6b45547a111f44abab
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# <a name="process-allocations"></a>Przetwarzanie alokacji

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o alokacjach, opcjach ich przetwarzania w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że przychody lub wydatki obciążają odpowiednie obiekty podczas księgowania.

Microsoft Dynamics 365 for Finance and Operations oferuje następujące funkcje do obsługi tego procesu:

-   Ręczne przydzielanie kwot transakcji przy użyciu akcji Podział w zasadach podziału księgowań lub poprzez zastosowanie względem dokumentu domyślnych szablonów wymiaru finansowego. Aby uzyskać więcej informacji, zobacz [Zasady podziału księgowań](../accounts-payable/accounting-distributions.md).
-   Automatyczne przydzielanie kwot transakcji na podstawie warunków alokacji zdefiniowanych na poszczególnych kontach głównych. Zapisy na koncie alokacji zostaną wygenerowane dla każdego arkusza według wartości procentowej i docelowego konta księgowego zawsze gdy zapis księgowy spełnia kryteria określone jako konto księgowe źródła.
-   Automatyczne przydzielanie sald księgi lub stałych kwot na podstawie reguł alokacji księgi. Reguły alokacji księgi są przetwarzane w regularnych odstępach przy użyciu arkuszy alokacji. 

###  <a name="allocations-in-budget-planning"></a>Alokacje w planowaniu budżetu

Reguły alokacji księgi mogą służyć do obsługi planów budżetowych. Korzystając z reguł alokacji księgi do planowania budżetu, reguły alokacji działają tak samo jak w księdze, ale źródło danych oraz miejsce docelowe danych pochodzi z planu budżetu. Można ręcznie wybrać reguły alokacji księgi do użycia dla planów budżetu. Można także użyć harmonogramu alokacji, który jest uruchamiany jako część procesu przepływu pracy.

> [!NOTE]
> Nie można użyć międzyfirmowych reguł alokacji księgi dla planów budżetu.






