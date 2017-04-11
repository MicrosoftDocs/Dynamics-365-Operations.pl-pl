---
title: "Raporty finansowe bilansu próbnego"
description: "W tym artykule opisano domyślne raporty dla sald. Opisano również bloki konstrukcyjne, które są skojarzone z tych raportów i modyfikowaniu raportów dostosowanych do wymagań biznesowych."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 750e2975eb75511afd75b6be0c8dfe90c8a9c89c
ms.lasthandoff: 03/31/2017


---

# <a name="trial-balance-financial-reports"></a>Raporty finansowe bilansu próbnego

W tym artykule opisano domyślne raporty dla sald. Opisano również bloki konstrukcyjne, które są skojarzone z tych raportów i modyfikowaniu raportów dostosowanych do wymagań biznesowych. 

<a name="default-trial-balance-reports"></a>Domyślne raporty finansowe bilansu próbnego
-----------------------------

Raporty bilansu próbnego są dostępne na karcie Raporty finansowe w systemie Microsoft Dynamics AX 7.

| Raport domyślny                                 | Działanie                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szczegółowy bilans próbny — domyślne               | Oferuje informacje dla wszystkich kont i obejmuje wszystkie salda po stronie debetowej i kredytowej, oraz ich wartości netto, wraz z datą transakcji, załącznikiem i opisem arkusza.                  |
| Sumaryczny bilans próbny — domyślny                | Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto.                                        |
| Sumaryczny bilans próbny rok do roku — domyślny | Oferuje informacje o saldzie dla wszystkich kont i zawiera salda otwarcia i zamknięcia oraz salda po stronie debetowej i kredytowej razem z ich różnicą netto dla bieżącego roku i roku ubiegłego. |

## <a name="building-blocks"></a>Podstawowe elementy
Raporty finansowe bilansu próbnego wykorzystują następujące podstawowe elementy.

| Raport domyślny                                 | Definicja wiersza          | Definicja kolumny                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Szczegółowy bilans próbny — domyślne               | Bilans próbny — domyślny | Szczegółowy bilans próbny — domyślne               |
| Sumaryczny bilans próbny — domyślny                | Bilans próbny — domyślny | Sumaryczny bilans próbny — domyślny                |
| Sumaryczny bilans próbny rok do roku — domyślny | Bilans próbny — domyślny | Sumaryczny bilans próbny rok do roku — domyślny |

### <a name="row-definition"></a>Definicja wiersza

Definicja wiersza bilansu próbnego — domyślny, zawiera pojedynczy wiersz, który w przypadku wszystkich kont głównych. Dlatego każdy może wygenerować raport bez konieczności wprowadzania żadnych zmian. Podczas przeglądania raportu można przejść do pojedynczego wiersza, aby wyświetlić szczegóły dotyczące poszczególnych kont. Można zmodyfikować definicję wiersza, tak aby zawierała więcej szczegółów. Aby zmodyfikować definicję wiersza Bilans próbny — domyślny, by zawierał wiesze dla wszystkich kont, należy wykonać następujące kroki.

1.  Kliknij **Edycja**, a następnie kliknij **Wstaw wiersze z wymiarów**. Polecenie **Wstaw wiersze z wymiarów** pozwala wybrać wymiary, które mają znaleźć się w definicji wiersza. Dla tej definicji wiersza użyjesz **Konta głównego**.
2.  Upewnij się, że **Konto główne** zawiera wszystkie znaki „&”, a następnie kliknij przycisk **OK**.

Teraz definicja wiersza zawiera wszystkie konta główne dla Twojej domyślnej firmy.

### <a name="column-definition"></a>Definicja kolumny

Każdy raport bilansu próbnego używa innej definicji kolumny. Te definicje kolumn zawierają różnego rodzaju kolumny oferujący różne poziomu szczegółowości i danych finansowych.

-   **Szczegółowy bilans próbny — domyślne typy kolumn:**
    -   **DESC** — opis z definicji wiersza
    -   **ACCT** — kody konta
    -   **ATTR (3)** — atrybuty:
        -   Data transakcji
        -   Załącznik
        -   Opis arkusza
    -   **FD** — dane finansowe zawierające tylko debety
    -   **FD** — dane finansowe zawierające tylko kredyty
    -   **CALC** — różnica netto
-   **Sumaryczny bilans próbny — domyślne typy kolumn:**
    -   **ACCT** — kody konta
    -   **DESC** — opis z definicji wiersza
    -   **ATTR** – atrybut:
        -   Załącznik
    -   **FD** — dane finansowe salda początkowego
    -   **FD** — dane finansowe zawierające tylko debety
    -   **FD** — dane finansowe zawierające tylko kredyty
    -   **CALC** — różnica netto
    -   **CALC** — saldo zamknięcia
-   **Sumaryczny bilans próbny rok do roku — domyślny:**
    -   **ACCT** — kody konta
    -   **DESC** — opis z definicji wiersza
    -   **ATTR** – atrybut
        -   Załącznik
    -   **FD** — dane finansowe salda początkowego dla bieżącego roku
    -   **FD** — dane finansowe zawierające tylko debety dla bieżącego roku
    -   **FD** — dane finansowe zawierające tylko kredyty dla bieżącego roku
    -   **CALC** — różnica netto
    -   **CALC** — saldo zamknięcia
    -   **FD** — dane finansowe zawierające tylko debety dla ostatniego roku
    -   **FD** — dane finansowe zawierające tylko kredyty dla ostatniego roku

 

<a name="see-also"></a>Informacje dodatkowe
--------

[Financial reporting](financial-reporting-getting-started.md)

[View financial reports](view-financial-reports.md)

[Blog sprawozdawczości finansowej Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)


