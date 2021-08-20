---
title: Ilość przekracza procent niedoboru w dostawie podczas generowania dokumentu dostawy
description: Podczas generowania dokumentu pakowania ładunek wychodzący zawiera ilość przekraczającą wartość procentową niedoboru dostawy.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ae02846c0ec937ebaff440dc5272a135e16c8aa7355ecc303929e760a54b6627
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760305"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a>Ilość przekracza procent niedoboru w dostawie podczas generowania dokumentu dostawy

Kod błędu: SYS24921

## <a name="symptoms"></a>Objawy

Podczas generowania dokumentu pakowania ładunek wychodzący zawiera ilość przekraczającą wartość procentową niedoboru dostawy.

Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:

> Niedobór w dostawie w wierszu wynosi %1 procent, a dopuszczalny poziom to tylko %2 procent.

Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.

## <a name="cause"></a>Powód

Ilość pobrana dla ładunku lub przesyłki jest mniejsza niż ilość zamówiona i nie mieści się w zakresie wartości procentowej niedoboru dostawy.

## <a name="resolution"></a>Rozwiązanie

Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się. Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Dostosuj wartość procentową niedoboru dostawy.
- Odwróć i dokonaj korekt.

### <a name="adjust-the-under-delivery-percentage"></a>Dostosuj wartość procentową niedoboru dostawy

Aby dostosować wartość procentową niedoboru dostawy, należy skorzystać z poniższej procedury.

1. Przejdź do pozycji **Rozrachunki z odbiorcami \> Zamówienia \> Wszystkie zamówienia**.
1. Wybierz zlecenie sprzedaży, dla którego nie można wysłać dokumentu pakowania dla ładunku.
1. Na karcie  **Wiersze zamówienia sprzedaży** wybierz wiersz zamówienia sprzedaży dla pozycji, która przekracza procent niedoboru w dostawie.
1. Na karcie  **Szczegóły wiersza** wybierz **Dostawa**.
1. W polu **Niedobór w dostawie** ustaw większą wartość procentową, która mieści się w ilości pobrania w stosunku do ilości ładunku, aby było można przejść dalej w sprawie dokumentu dostawy.

### <a name="reverse-and-make-adjustments"></a>Odwróć i dokonaj korekt

Odwróć wszystko, co zostało zaksięgowane dla danego ładunku (na przykład dowód pakowania, potwierdzenie wysyłki i pracę), dokonaj korekty zamówienia sprzedaży, ponownie zwolnij zamówienie do magazynu i zakończ procedurę wysyłki.

Poniższa procedura służy do anulowania dokumentu dostawy.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Kasowanie dokumentu dostawy**.

Poniższa procedura umożliwia cofnięcie potwierdzenia wysyłki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.

W celu odwrócenia pracy należy zastosować następującą procedurę.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. W okienku akcji, na karcie  **Ładunek**, w grupie  **Praca** wybierz pozycję  **Cofnięcie pracy**.
