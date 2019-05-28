---
title: Konfiguracje parametrów dla zestawień sieci sprzedaży
description: Ta procedura pokazuje konfiguracje parametrów sprzedaży detalicznej, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6dacd2b80ca0d51d81d2bdf5bc2636b47da621ee
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564300"
---
# <a name="parameter-configurations-for-retail-statements"></a>Konfiguracje parametrów dla zestawień sieci sprzedaży

[!include[task guide banner](../includes/task-guide-banner.md)]

Ta procedura pokazuje konfiguracje parametrów sprzedaży detalicznej, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży. Ta procedura wykorzystuje firmę demonstracyjną USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Ustawienia centrali > Parametry > Parametry sieci sprzedaży.
2. Kliknij kartę Księgowanie.
    * Wybierz opcję „Tak”, aby księgować kwoty rabatów okresowych.  
    * Wybierz opcję „Standardowe”, aby używać domyślnych kont, lub opcję „Okresowe”, jeśli chcesz zdefiniować, które konta mają być używane dla każdego rabatu okresowego.  
    * Wybierz opcję „Podsumowanie”, jeśli wiersze zapasów powinny być agregowane zawsze, gdy jest to możliwe.  
    * Wybierz opcję „Tak”, jeśli faktury i płatności powinny być automatycznie rozliczane w ramach procesu księgowania zestawień.  
    * Wybierz opcję „Tak”, jeśli transakcje przekazania pieniędzy do sejfu powinny być agregowane.  
    * Wybierz opcję „Tak”, jeśli transakcje przekazania pieniędzy do banku powinny być agregowane.  
    * Wybierz opcję „Tak”, aby włączyć agregowanie przy księgowaniu zestawień.  
    * Wybierz opcję „Tak”, aby tworzyć i przetwarzać zamówienia równoległe podczas księgowania zestawień.  
    * Wprowadź maksymalną liczba zamówień, które mają być przetwarzane w każdym zadaniu wsadowym.  
3. Kliknij przycisk Zapisz.

