---
title: Strona listy Transakcja dostawcy
description: "Ten temat zawiera informacje o stronie listy Transakcja dostawcy dostępnej w programie Microsoft Dynamics 365 for Finance and Operations."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: pl-pl
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a>Strona listy Transakcja dostawcy

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Wyświetl rozliczenia

Karta **Wyświetl rozliczenia** w okienku akcji zapewnia szybki dostęp do historii rozliczeń oraz dodatkowych informacji na temat całej transakcji rozliczenia. Można również wyświetlać dodatkowe transakcje, które są powiązane z wybraną transakcją, ponieważ były częścią tego samego rozliczenia albo są płatnościami utworzonymi w tym samym arkuszu płatności.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Wszyscy dostawcy**.
2. Wybierz dostawcę mającego transakcje, a następnie wybierz kolejno opcje **Dostawca \> Transakcje**.
3. Wybierz transakcję, którą chcesz zbadać.
4. W okienku akcji kliknij kartę **Wyświetl rozliczenia**.

    Zostanie otwarte okno dialogowe **Wyświetl rozliczenia**, w którym widać wybraną transakcję oraz wszystkie dokumenty, które są rozliczane względem niej. To okno dialogowe przypomina widok historii rozliczeń, ale zawiera wszystkich powiązane dokumenty.

5. Z poziomu tego okna dialogowego można wykonywać różne zadania. Zaznacz jeden lub więcej załączników, a następnie wybierz jedno z następujących menu:

   - **Wyświetl księgowanie** — są wyświetlane wszystkie załączniki powiązane z wybranym dokumentem. Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.
   - **Eksportuj** — eksportowanie wybranych załączników do programu Microsoft Excel.
   - **Wyświetl powiązane płatności** — są wyświetlane wszystkie transakcje, które zostały utworzone w arkuszu płatności powiązanym z wybranym dokumentem. Ponadto zostaną wyświetlone wszystkie rozliczenia powiązane z tymi płatnościami. Etykieta tego menu zmieni się na **Wyświetl rozliczenia**. Wybierz opcję **Wyświetl rozliczenia**, a pojawią się tylko transakcje, które były wyświetlane po pierwszym otwarciu okna dialogowego **Wyświetl rozliczenia**.
    - **Rozlicz transakcje** — to menu jest wyświetlane, jeśli wybrany oryginalny dokument nie został w pełni rozliczony. Po wybraniu tej opcji pojawi się okno dialogowe **Rozlicz transakcje**, którym można wybrać transakcje do rozliczenia.
    - **Cofnij rozliczenia** — to menu jest wyświetlane, jeśli wybrany oryginalny dokument został w pełni rozliczony. Po wybraniu tej opcji pojawia się okno dialogowe **Cofnij rozliczenia**, gdzie można cofnąć rozliczenia dokonane dla tego dokumentu.

