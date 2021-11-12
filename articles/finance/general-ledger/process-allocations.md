---
title: Przetwarzanie alokacji
description: Ten temat zawiera informacje o alokacjach, opcjach ich przetwarzania w Microsoft Dynamics 365 Finance oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że wydatki lub przychody obciążają odpowiednie obiekty podczas księgowania.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b79282abd0edf86f1a9f39fd869cf1fab28b9a4
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2021
ms.locfileid: "7726999"
---
# <a name="process-allocations"></a>Przetwarzanie alokacji

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o alokacjach, opcjach ich przetwarzania oraz o sposobach ich wykorzystywania w planowaniu budżetu. Alokacje służą do dystrybucji kwot między wiele kombinacji kont księgowych. Pomagają zagwarantować, że wydatki lub przychody obciążają odpowiednie obiekty podczas księgowania.

Ten proces obsługuje następujące możliwości:

-   Ręczne przydzielanie kwot transakcji przy użyciu akcji Podział w zasadach podziału księgowań lub poprzez zastosowanie względem dokumentu domyślnych szablonów wymiaru finansowego. Aby uzyskać więcej informacji, zobacz [Zasady podziału księgowań](../accounts-payable/accounting-distributions.md).
-   Automatyczne przydzielanie kwot transakcji na podstawie warunków alokacji zdefiniowanych na poszczególnych kontach głównych. Zapisy na koncie alokacji zostaną wygenerowane dla każdego arkusza według wartości procentowej i docelowego konta księgowego zawsze gdy zapis księgowy spełnia kryteria określone jako konto księgowe źródła. Aby uzyskać więcej informacji, zobacz [Warunki alokacji konta głównego](../general-ledger/main-account-allocation-terms.md)
-   Automatyczne przydzielanie sald księgi lub stałych kwot na podstawie reguł alokacji księgi. Reguły alokacji księgi są przetwarzane w regularnych odstępach przy użyciu arkuszy alokacji. Aby uzyskać więcej informacji, zobacz temat [Reguły alokacji](../general-ledger/ledger-allocation-rules.md).

###  <a name="allocations-in-budget-planning"></a>Alokacje w planowaniu budżetu

Reguły alokacji księgi mogą służyć do obsługi planów budżetowych. Korzystając z reguł alokacji księgi do planowania budżetu, reguły alokacji działają tak samo jak w księdze, ale źródło danych oraz miejsce docelowe danych pochodzi z planu budżetu. Można ręcznie wybrać reguły alokacji księgi do użycia dla planów budżetu. Można także użyć harmonogramu alokacji, który jest uruchamiany jako część procesu przepływu pracy.

> [!NOTE]
> Nie można użyć międzyfirmowych reguł alokacji księgi dla planów budżetu.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
