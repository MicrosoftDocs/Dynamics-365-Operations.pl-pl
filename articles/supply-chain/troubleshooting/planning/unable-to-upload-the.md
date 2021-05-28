---
title: Nie można zaktualizować prognozowanego kosztu jednostkowego podczas importowania rekordów prognozy popytu
description: Gdy do importowania rekordów prognozy popytu są wykorzystywane jednostki danych, koszt wewnętrzny istniejących rekordów nie jest aktualizowany, aby był taki taki, jak zaimportowane dane.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026817"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Nie można zaktualizować prognozowanego kosztu jednostkowego podczas importowania rekordów prognozy popytu

Numer artykułu z bazy wiedzy: 4614109

## <a name="symptoms"></a>Objawy

Gdy do importowania rekordów prognozy popytu są wykorzystywane wartości **prognozowanego kosztu jednostkowego**, koszt wewnętrzny istniejących rekordów nie jest aktualizowany, aby był taki taki, jak zaimportowane dane.

## <a name="cause"></a>Powód

**Prognozowany koszt jednostkowy** jest polem tylko do odczytu. Ta wartość jest oparta na kosztach jednostkowych produktu i nie można jej ustawić bezpośrednio w drodze importu.

## <a name="resolution"></a>Rozdzielczość

To pole jest tylko do odczytu, więc nie można dla niego zaimportować wartości. Wartość będzie obliczana zgodnie z istniejącą logiką biznesową.
