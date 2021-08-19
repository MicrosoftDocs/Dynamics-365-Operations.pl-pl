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
ms.openlocfilehash: de471da861785f283eeaa78f97b5d1e1a6b023d71de6fff72ae39edd6bb124cc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765377"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Nie można zaktualizować prognozowanego kosztu jednostkowego podczas importowania rekordów prognozy popytu

Numer artykułu z bazy wiedzy: 4614109

## <a name="symptoms"></a>Objawy

Gdy do importowania rekordów prognozy popytu są wykorzystywane wartości **prognozowanego kosztu jednostkowego**, koszt wewnętrzny istniejących rekordów nie jest aktualizowany, aby był taki taki, jak zaimportowane dane.

## <a name="cause"></a>Powód

**Prognozowany koszt jednostkowy** jest polem tylko do odczytu. Ta wartość jest oparta na kosztach jednostkowych produktu i nie można jej ustawić bezpośrednio w drodze importu.

## <a name="resolution"></a>Rozdzielczość

To pole jest tylko do odczytu, więc nie można dla niego zaimportować wartości. Wartość będzie obliczana zgodnie z istniejącą logiką biznesową.
