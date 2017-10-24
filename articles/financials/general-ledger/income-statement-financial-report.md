---
title: "Raport finansowego zestawienia przychodów"
description: "W tym artykule opisano domyślny raport o rachunkach wyników. Omówiono również bloki konstrukcyjne skojarzone z tym raportem."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0017d13b7f7594462dfff4ef896f4139607d4bc5
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="income-statement-financial-report"></a>Raport finansowego zestawienia przychodów

[!include[banner](../includes/banner.md)]


W tym artykule opisano domyślny raport o rachunkach wyników. Omówiono również bloki konstrukcyjne skojarzone z tym raportem. 

<a name="default-income-statement-report"></a>Raport domyślny zestawienia przychodów
-------------------------------

| Raport domyślny             | Działanie                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Zestawienie przychodów — domyślne | Pokazuje rentowność organizacji w bieżącym okresie i od początku roku. |

## <a name="building-blocks"></a>Podstawowe elementy
W raportach finansowych zestawienia przychodów używane są następujące podstawowe elementy.

| Raport domyślny             | Definicja wiersza                     | Definicja kolumny          |
|----------------------------|------------------------------------|----------------------------|
| Zestawienie przychodów — domyślne | Podsumowujące zestawienie przychodów — domyślne | Okresowe i od początku roku — domyślne |

### <a name="row-definition"></a>Definicja wiersza

Definicja wiersza Podsumowujące zestawienie przychodów — domyślne zawiera sekcję dla każdej części tradycyjnego zestawienia przychodów. Wymiar Kategoria konta głównego jest używany do tworzenia definicji tego wiersza. Dlatego każdy może wygenerować raport bez konieczności wprowadzania żadnych zmian.

### <a name="column-definition"></a>Definicja kolumny

Definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.

-   **Okresowo i od początku roku — domyślne typy kolumn:**
    -   **DESC** — opis z definicji wiersza
    -   **FD** — dane finansowe dla bieżącego okresu
    -   **FD** — dane finansowe od początku roku

 

<a name="see-also"></a>Informacje dodatkowe
--------

[Raporty finansowe](financial-reporting-getting-started.md)

[Wyświetlanie raportów finansowych](view-financial-reports.md)

[Blog o sprawozdawczości finansowej w systemie Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




