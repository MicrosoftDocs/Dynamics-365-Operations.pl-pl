---
title: Raporty finansowe bilansu
description: "W tym artykule opisano domyślne raporty o bilansach. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami."
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
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1cb7ef4b1b08caff39f0693eef6743bbe5d3892e
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="balance-sheet-financial-reports"></a>Raporty finansowe bilansu

[!include[banner](../includes/banner.md)]


W tym artykule opisano domyślne raporty o bilansach. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami. 

<a name="default-balance-sheet-reports"></a>Domyślne raporty finansowe bilansu
-----------------------------

Dostępne są dwa domyślne raporty finansowe bilansu. Na jednym raporcie sekcje są ułożone w słupkach. Na drugim raporcie sekcje są ułożone obok siebie.

| Raport domyślny                       | Działanie                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Bilans — domyślne              | Oferuje widok pozycji finansowej organizacji w danym roku.                                                                 |
| Obok arkusza bilansowego — domyślna | Oferuje widok pozycji finansowej organizacji w danym roku. Aktywa i pasywa oraz kapitał własny udziałowców są pokazane równolegle. |

## <a name="building-blocks"></a>Podstawowe elementy
Raporty finansowe bilansu wykorzystują następujące podstawowe elementy.

| Raport domyślny                       | Definicja wiersza                       | Definicja kolumny             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Bilans — domyślna              | Bilans — domyślna              | Od początku roku i odchylenie — domyślna    |
| Obok arkusza bilansowego — domyślna | Obok arkusza bilansowego — domyślna | Kolumna Od początku roku — domyślna |

### <a name="row-definition"></a>Definicja wiersza

Definicje wierszy dla obu raportów bilansu zwierają konkretne sekcje dla każdej z części bilansu tradycyjnego. Raport równoległy zawiera podział kolumn, tak aby pasywa i kapitał własny właściciela były widoczne obok aktywów. Wymiar Kategoria konta głównego jest używany do tworzenia obu definicji wiersza. Dlatego każdy może wygenerować raporty bez konieczności wprowadzania żadnych zmian.

### <a name="column-definition"></a>Definicja kolumny

Definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.

-   **Od początku roku i Odchylenie — domyślne typy kolumn:**
    -   **DESC** — opis z definicji wiersza
    -   **FD** — dane finansowe od początku roku dla bieżącego roku
    -   **FD** — dane finansowe od początku roku dla ostatniego roku
    -   **CALC** — odchylenie od odjęcia ostatniego rok od tego roku

<!-- -->

-   **Kolumna Od początku roku — domyślna:**
    -   **DESC** — opis z definicji wiersza
    -   **FD** — dane finansowe od początku roku dla bieżącego roku

 

<a name="see-also"></a>Informacje dodatkowe
--------

[Raporty finansowe](financial-reporting-getting-started.md)

[Wyświetlanie raportów finansowych](view-financial-reports.md)

[Blog o sprawozdawczości finansowej w systemie Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




