---
title: Konfigurowanie parametrów wpływających na zestawienia sieci sprzedaży
description: Ten temat pokazuje konfiguracje parametrów Commerce, które mają wpływ na sposób tworzenia i księgowana zestawień.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
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
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023664"
---
# <a name="configure-parameters-that-affect-retail-statements"></a>Konfigurowanie parametrów wpływających na zestawienia sieci sprzedaży

[!include[task guide banner](../includes/task-guide-banner.md)]

Ten temat pokazuje konfiguracje parametrów Commerce, które mają wpływ na sposób tworzenia i księgowana zestawień. Ta procedura wykorzystuje firmę demonstracyjną USRT.

1. W okienku nawigacji kliknij kolejno opcje **Moduły > Handel detaliczny i inny > Ustawienia Headquarters > Parametry > Parametry komercyjne**.
2. Wybierz kartę **Księgowanie**.
    - Wybierz opcję **Tak**, aby księgować kwoty rabatów okresowych.  
    - Wybierz opcję **Standardowe**, aby używać domyślnych kont, lub opcję **Okresowe**, jeśli chcesz zdefiniować, które konta mają być używane dla każdego rabatu okresowego.  
      - Wybierz opcję **Podsumowanie**, jeśli wiersze zapasów powinny być agregowane zawsze, gdy jest to możliwe.  
      - Wybierz opcję **Tak**, jeśli faktury i płatności powinny być automatycznie rozliczane w ramach procesu księgowania zestawień.  
      - Wybierz opcję **Tak**, jeśli transakcje przekazania pieniędzy do sejfu powinny być agregowane.  
      - Wybierz opcję **Tak**, jeśli transakcje przekazania pieniędzy do banku powinny być agregowane.  
      - Wybierz opcję **Tak**, aby włączyć agregowanie przy księgowaniu zestawień.  
      - Wybierz opcję **Tak**, aby tworzyć i przetwarzać zamówienia równoległe podczas księgowania zestawień.  
      - Wprowadź maksymalną liczba zamówień, które mają być przetwarzane w każdym zadaniu wsadowym.  
3. Wybierz opcję **Zapisz**.

