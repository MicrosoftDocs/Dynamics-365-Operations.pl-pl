--- 
title: "Konfigurowanie parametrów aplikacji Retail wpływających na zestawienia sieci sprzedaży"
description: "Ta procedura pokazuje konfiguracje parametrów sprzedaży detalicznej, które mają wpływ na sposób tworzenia i księgowana zestawień sieci sprzedaży."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ff12587d8332801131d5b0cac84e0db38f8f6142
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a>Konfigurowanie parametrów aplikacji Retail wpływających na zestawienia sieci sprzedaży

[!include [task guide banner](../includes/task-guide-banner.md)]

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


