---
title: Pozostała ilość w jednostkach musi być różna od zera
description: Podczas generowania dowodu pakowania dane, które są do niego dostarczane, mają niezerową ilość zapasów, ale zerową ilość sprzedaży.
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
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248798"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a>Pozostała ilość w jednostkach musi być różna od zera

Kod błędu: SYS19591

## <a name="symptoms"></a>Objawy

Podczas generowania dowodu pakowania dane, które są do niego dostarczane, mają niezerową ilość zapasów, ale zerową ilość sprzedaży.

Przy próbie wytworzenia dokumentu dostawy wyświetla następujący komunikat o błędzie:

> Pozostała ilość w jednostkach %1 musi być różna od zera.

Dlatego nie można wygenerować dokumentu dostawy dla tego ładunku.

## <a name="cause"></a>Powód

System ocenia fizyczną ilość pozostałą w jednostce magazynowej i fizyczną ilość pozostałą w jednostce wysyłkowej. Jeśli system stwierdzi, że fizyczna ilość pozostała w jednostce wysyłkowej wynosi 0 (zero), ale fizyczna ilość pozostała w jednostce inwentarzowej nie wynosi 0, nie można wygenerować dokumentu dostawy. Na przykład, ten problem może wystąpić, jeśli jednostka sprzedaży i jednostka magazynowa dla pozycji są różne, a konwersja między jednostkami nie jest dokładna.

## <a name="resolution"></a>Rozwiązanie

Ładunek lub przesyłka znajduje się obecnie w stanie, w którym generowanie dokumentu dostawy nie powiodło się. Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.
- Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem.
- Przejrzyj linie ładunkowe i dokonaj korekty, aby upewnić się, że jednostka i ilość są wyrównane z precyzją dziesiętną jednostki.
- Upewnij się, że jednostka miary zapasów jest mniejsza niż jednostka miary sprzedaży.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Przejrzyj wiersze ładunkowe i upewnij się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają

Poniższa procedura służy do przeglądu linii ładunkowych i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.
1. Zanotuj wartość pola **Ilość stworzonych prac**.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.
1. Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a>Przejrzyj swoje linie ładunkowe i wprowadź poprawki, aby upewnić się, że ilość może być czysto przeliczona bez liczb dziesiętnych i innych problemów związanych z zaokrąglaniem

Skorzystaj z poniższej procedury, aby przejrzeć linie ładunkowe i wprowadzić poprawki w celu zapewnienia, że ilość może być czysto przeliczona bez problemów związanych z zaokrąglaniem.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla których nie można wygenerować dokumentu dostawy.
1. Na pasku akcji, na zakładce  **Wysyłka i odbiór**, w grupie  **Odwróć** zaznaczamy  **Odwrócenie potwierdzenia wysyłki**.
1. Na karcie  **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent nadwyżki w dostawie.
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

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a>Upewnij się, że jednostka miary zapasów jest mniejsza niż jednostka miary sprzedaży

Upewnij się, że jednostka miary zapasów jest mniejsza niż jednostka miary sprzedaży. Rozważ ponowne skonfigurowanie jednostka miary pozycji w razie potrzeby.
