---
title: Rezerwacji nie można usunąć podczas anulowania zamówienia
description: 'Nie można anulować zamówienia sprzedaży, jeśli praca skojarzona z tym zamówieniem zostanie anulowana i wycofana. W tym celu należy wykonać trzy następujące kroki:'
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8d947e64568246dba5eff3c21fd3920b6494b73
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477319"
---
# <a name="reservations-cannot-be-removed-when-canceling-an-order"></a>Rezerwacji nie można usunąć podczas anulowania zamówienia

## <a name="symptoms"></a>Objawy

Jeśli praca jest skojarzona z zamówieniem sprzedaży i spróbujesz anulować to zamówienie, zostanie wyświetlony następujący komunikat o błędzie:

> Nie można usunąć rezerwacji, ponieważ utworzono pracę opartą na rezerwacjach.

Nie można anulować zamówienia sprzedaży, jeśli praca zostanie anulowana i wycofana. To wymaganie ma zastosowanie nawet wtedy, gdy praca skojarzona z zamówieniem sprzedaży jest zamknięta.

## <a name="resolution"></a>Rozwiązanie

Aby naprawić ten problem, należy wykonać następujące czynności:

1. Anuluj pracę i umieść zapasy z powrotem w żądanej lokalizacji. Umożliwia przejście do odpowiedniego ładunku zamówienia sprzedaży i wybranie opcji **Zmniejsz ilość pobraną** w wierszu ładunku lub **Cofnij pracę** w okienku akcji.

    Obecnie praca ma stan *Anulowane*, a nowe prace przesunięcia zapasów są automatycznie tworzone i przetwarzane w celu przeniesienia zapasów z powrotem do lokalizacji, która została opisana w momencie wycofania.

2. Usuń ładunek. Wysyłka jest również usuwana.

3. Teraz powinno być możliwe przejście do tego zamówienia sprzedaży i anulowanie go.
