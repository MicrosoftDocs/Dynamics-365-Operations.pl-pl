---
title: Zaokrąglenie dziesiętne ilości aktualizowanej fizycznie jest niepoprawne
description: Podczas generowania dokumentu dostawy ładunek wychodzący zawiera ilość, która nie odpowiada precyzji dziesiętnej zdefiniowanej w jednostce.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ddfac7106eb0e8b934516ca10e3950891d10910a2ccdef1868faf25812243159
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726568"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a>Zaokrąglenie dziesiętne ilości aktualizowanej fizycznie jest niepoprawne

Kod błędu: SYS19589

## <a name="symptoms"></a>Objawy

Podczas generowania dokumentu dostawy ładunek wychodzący zawiera ilość, która nie odpowiada precyzji dziesiętnej zdefiniowanej w jednostce.

Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:

> Zaokrąglenie dziesiętne ilości aktualizowanej fizycznie w jednostce %1 jest niepoprawne.

Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.

## <a name="cause"></a>Powód

System ocenia, czy zaokrąglenie dziesiętne ilości wysyłkowej odpowiada precyzji dziesiętnej, która została zdefiniowana dla jednostki wysyłkowej. Gdy system zaokrągla ilość wysyłkową do określonej liczby miejsc po przecinku, jeśli stwierdzi, że zaokrąglona ilość wysyłkowa nie odpowiada rzeczywistej ilości wysyłkowej, nie można wygenerować dokumentu dostawy. Na przykład ten problem może wystąpić, jeśli ilość sprzedaży wynosi 1,75 kilograma (kg), ale dokładność dziesiętna jest ustawiona na *1*.

## <a name="resolution"></a>Rozwiązanie

Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się. Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem.
- Przejrzyj linie ładunkowe i dokonaj korekty, aby upewnić się, że jednostka i ilość są wyrównane z precyzją dziesiętną jednostki.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a>Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem

Skorzystaj z poniższej procedury, aby przejrzeć linie ładunkowe i wprowadzić poprawki w celu zapewnienia, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.
1. Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.
1. Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem.
1. Wybierz pozycję **Zmniejsz pobraną ilość**, aby dostosować pobraną ilość.
1. Na karcie  **Szczegóły wiersza** wybierz **Zamówienie**.
1. Ustaw pole **Ilość** na ilość pobraną (czyli wartość pola **Ilość utworzona**), aby można było rozpocząć generowanie kartonu.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Przejrzyj linie ładunkowe i dokonaj korekty, aby upewnić się, że jednostka i ilość są wyrównane z precyzją dziesiętną jednostki

Korzystając z poniższej procedury, należy przejrzeć linie ładunkowe i dokonać korekty, aby upewnić się, że jednostka i ilość są wyrównane z dokładnością dziesiętną jednostki.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która powoduje problem. Zanotuj wartość pola **Ilość** i **Jednostka**.
1. Wybierz kolejno opcje **Administrowanie organizacją \> Jednostki \> Jednostki**.
1. Wybierz jednostkę, dla których nie można wygenerować dokumentu dostawy.
1. W razie potrzeby dostosuj wartość pola **Dokładność dziesiętna**.
