---
title: Raporty finansowe bilansu
description: W tym artykule opisano domyślne raporty o bilansach. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami.
author: jinniew
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aad297f401143388d682da175a6b14727a8f2f0
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643831"
---
# <a name="balance-sheet-financial-reports"></a>Raporty finansowe bilansu

[!include [banner](../includes/banner.md)]

W tym artykule opisano domyślne raporty o bilansach. Omówiono również bloki konstrukcyjne skojarzone z tymi raportami. 

## <a name="default-balance-sheet-reports"></a>Domyślne raporty finansowe bilansu

Dostępne są dwa domyślne raporty finansowe bilansu. Na jednym raporcie sekcje są ułożone w słupkach. Na drugim raporcie sekcje są ułożone obok siebie.

| Raport domyślny                       | Działanie                                                                                                                           |
|--------------------------------------|--------------------------------------------------------------------------------------|
| Bilans — domyślne              | Oferuje widok pozycji finansowej organizacji w danym roku.                    |
| Bilans i rachunek wyników obok siebie — domyślny | Oferuje obok siebie widok pozycji finansowej organizacji w danym roku. |

## <a name="building-blocks"></a>Moduły konstrukcyjne
Raporty finansowe bilansu wykorzystują następujące podstawowe elementy.

| Raport domyślny                       | Definicja wiersza                       | Definicja kolumny             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Bilans — domyślna              | Bilans — domyślna              | Od początku roku i odchylenie — domyślna    |
| Bilans i rachunek wyników obok siebie — domyślny | Bilans i rachunek wyników obok siebie — domyślny | Kolumna Od początku roku — domyślna |

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



## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie raportowania finansowego](financial-reporting-getting-started.md)

[Wyświetlanie raportów finansowych](view-financial-reports.md)

[Blog o sprawozdawczości finansowej w systemie Dynamics](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
