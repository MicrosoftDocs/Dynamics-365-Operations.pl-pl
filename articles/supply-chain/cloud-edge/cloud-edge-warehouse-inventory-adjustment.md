---
title: Korekta zapasów w magazynie
description: Ten temat zawiera informacje dotyczące arkusza korekt zapasów magazynowych i przetwarzania w przypadku używania jednostek skalowania.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3999c16cdf4fce342ce56ca3a459944566c6d0cb6a8460d30d2254356e5cba82
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748818"
---
# <a name="warehouse-inventory-adjustment"></a>Korekta zapasów w magazynie

[!include [banner](../includes/banner.md)]

Funkcja korygowania zapasów magazynowych jest używana podczas uruchamiania jednostek skalowania chmury i urządzenia brzegowego w przypadku [obciążeń produkcyjnych](cloud-edge-workload-manufacturing.md) oraz [obciążeń zarządzania magazynu](cloud-edge-workload-warehousing.md).

Jeśli pracownik wykonuje korektę zapasów za pomocą aplikacji magazynu na obciążeniu zarządzania magazynem jednostek skalowania, fizyczna aktualizacja dostępnych zapasów musi zostać przetworzona przez zadanie wsadowe **Arkusz korekt zapasów magazynowych**, które uruchamia się i planuje, wybierając pozycję **Zarządzanie magazynem > Zadania okresowe > Arkusz korekt zapasów magazynowych**.

W następujących procesach pracy w aplikacji magazynowej jest obecnie dostępny **arkusz korekt zapasów magazynowych** na obciążeniach pracą jednostek skalowania:

- Korekta wewnętrzna/zewnętrzna
- Inwentaryzacja ciągła
- Ładowanie numeru identyfikacyjnego

Niektóre transakcje magazynowe są tworzone jako część każdego procesu korekty zapasów, ponieważ wdrożenia centrum i jednostki skalowania mają wspólne rekordy zapasów.

## <a name="inventory-adjustment-example"></a>Przykład korekty zapasów

W tym przykładzie pracownik magazynu używa aplikacji magazynu do zarejestrowania dodania dostępnych zapasów.

Najpierw obciążenie pracą jednostki skalowania powoduje utworzenie transakcji korekty zapasów magazynowych dodatniej korekty fizycznej, która jest następnie synchronizowana z centrum i powoduje zwiększenie dostępnych zapasów w centrum.

| Typ                                    | Jednostka skalowania | Kierunek | Piasta |
|-----------------------------------------|------------|-----------|-----|
| Korekta zapasów w magazynie          | +1         | ->        | +1  |

Następnie centrum przetwarza księgowanie arkusza inwentaryzacji odbierane za pomocą [komunikatów procesora komunikatów](cloud-edge-message-processor-messages.md). W ten sposób są automatycznie aktualizowane dodatkowe dostępne zapasy. Aby uniknąć podwójnego stanu dostępnych zapasów, centrum tworzy w ramach tego procesu transakcję przeciwstawną i usuwa poprzednio zarejestrowane dane o dostępnych zapasach, które są związane z korektą zapasów w magazynie.

| Typ                                    | Jednostka skalowania | Kierunek | Piasta |
|-----------------------------------------|------------|-----------|-----|
| Inwentaryzacja                                | +1         | <-        | +1  |
| Korekta zapasów w magazynie (przeciwstawna) | -1         | <-        | -1  |

Po utworzeniu **arkusza korekty zapasów magazynowych** centrum przez jednostkę skalowania można przeglądać zarówno **arkusz inwentaryzacji**, jak i **arkusz przeciwstawny**, które są tworzone przez centrum w procesie korekty.

Aby przejrzeć te wpisy arkusza i transakcję w Supply Chain Management, należy wykonać następujące kroki:

1. Zaloguj się do jednostki skalowania.
1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Arkusz korekty zapasów w magazynie**.
1. Na stronie **Arkusz korekt zapasów w magazynie** znajdź i otwórz arkusz, w których zanotowana jest zmiana dostępnych zapasów. Sekcja **Wiersze arkusza** zawiera poszczególne korekty zarejestrowane przez ten arkusz.
1. Zaloguj się do centrum.
1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Arkusz korekty zapasów w magazynie**.
1. Na stronie **Arkusz korekt zapasów w magazynie** powinien być wyświetlony ten sam arkusz, jeśli centrum i jednostka skalowania zostały zsynchronizowane.
1. Otwórz arkusz. Jeśli [komunikaty procesora komunikatów](cloud-edge-message-processor-messages.md) zostały przetworzone, w nagłówku będą wyświetlane łącza do **arkusza inwentaryzacji** i **arkusza przeciwstawnego**.
    - **Arkusz inwentaryzacji** powinien mieć takie same wartości wymiarów jak wiersze arkusza.
    - **Arkusz przeciwstawny** powinien wyświetlać transakcję przeciwstawną, która usuwa podwójną korektę zapasów.
    > [!NOTE]
    > Po zakończeniu całej synchronizacji i przetwarzania **arkusz inwentaryzacji** i **arkusz przeciwstawny** są synchronizowane z powrotem z jednostką skalowania. Można je również wyświetlić ze odpowiedniej strony **Arkusz korekt zapasów magazynowych**.
