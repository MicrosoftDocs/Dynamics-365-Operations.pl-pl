---
title: Nie można zaktualizować wiersza ładunku, ponieważ zwolniona ilość byłaby ujemna
description: Ten problem występuje, jeśli zaktualizowanie lub usunięcie wiersza ładunku spowodowałoby zwolnioną ilość ujemną.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728466"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>Nie można zaktualizować wiersza ładunku, ponieważ zwolniona ilość byłaby ujemna

Kod błędu: @WAX:ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>Objawy

Ten problem występuje, jeśli zaktualizowanie lub usunięcie wiersza ładunku spowodowałoby zwolnioną ilość ujemną. W takim przypadku podczas próby zaktualizowania lub usunięcia wiersza ładunku system wyświetla następujący komunikat o błędzie:

> Zwolniona ilość nie może być ujemna dla pozycji %1, partii %2.

W związku z tym nie można zaktualizować ani usunąć wiersza ładunku.

## <a name="cause"></a>Powód

Po zaktualizowaniu lub usunięciu wiersza ładunku system aktualizuje zwolnioną ilość powiązanego wiersza sprzedaży (*whsSalesLine.ReleaseQty*). System ocenia zwolnioną ilość, a jeśli stwierdzi, że zwolniona ilość wiersza będzie ujemna po aktualizacji, nie pozwoli Ci zaktualizować ani usunąć wiersza. Ta weryfikacja ma miejsce przy każdej próbie zaktualizowania ilości wiersza ładunku lub jednostki miary za pomocą różnych akcji, takich jak usunięcie wiersza ładunku, usunięcie wysyłki, zmiana ilości wiersza obciążenia, zmniejszenie pobranej ilości i pobieranie w niedomiarze.

Najczęstszą główną przyczyną tego problemu jest zmiana konwersji jednostek, która jest używana dla otwartych wierszy ładunku. Na przykład konwersja jednostkowa po wydaniu zamówienia sprzedaży wynosiła *50 Ea = 1 PL*. Jednak przed sfinalizowaniem powiązanej wysyłki ładunku konwersja jednostki została zmieniona na *100 Ea = 1 PL*.

## <a name="resolution"></a>Rozwiązanie

Rozwiązaniem jest przywrócenie zmian konwersji jednostki, zaktualizowanie lub usunięcie wiersza ładunku, a następnie ponowne wdrożenie konwersji. Do momentu rozwiązania problemu nie należy przetwarzać innych ładunków, które zawierają pozycję, która spowodowała problem. W przeciwnym razie nowe konwersje mogą być używane dla innych ładunków, które są już otwarte.

Aby naprawić ten problem, wykonaj jedno z następujących zadań:

1. Przejrzyj konwersję jednostki, która została użyta dla wiersza ładunku.
2. Przejrzyj bieżącą konwersję jednostki dla pozycji i wykonaj konwersje, które umożliwią zaktualizowanie lub usunięcie wiersza ładunku.
3. Zaktualizuj lub usuń wiersz ładunku i przywróć korekty konwersji jednostek.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>Przejrzyj konwersję jednostki, która została użyta dla wiersza ładunku

Poniższa procedura służy do przeglądania wierszy ładunku i notowania konwersji jednostek, która została użyta dla wiersza ładunku.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, który zawiera wiersz, którego nie można usunąć ani zaktualizować.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. W górnej siatce wybierz odpowiedni identyfikator pracy.
1. Na karcie **Ogólne** u dołu strony oblicz współczynnik konwersji między wartością **Ilość pracy w magazynie** i wartością **Ilość pracy**. Zanotuj współczynnik.
1. Powtórz tę procedurę dla wszystkich odpowiednich identyfikatorów pracy, aby upewnić się, że użyto tej samej konwersji.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>Przejrzyj bieżącą konwersję jednostki dla pozycji i dokonaj korekt

Korzystając z poniższej procedury, należy przejrzeć konwersje jednostek produktu i dokonać korekty, aby upewnić się, że konwersja jednostki została dopasowana do wiersza ładunku.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Otwórz odpowiedni produkt główny, aby przejść do jego strony **Szczegóły zwolnionego produktu**.
1. W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Konwersje jednostek**.
1. Wybierz konwersję między jednostkami i dokonaj korekt przy użyciu konwersji znalezionej w poprzedniej sekcji.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>Zaktualizuj lub usuń wiersz ładunku i przywróć korekty konwersji jednostek

Poniższa procedura umożliwia przetworzenie wiersza ładunku zgodnie z wymaganiami i przywrócenie konwersji jednostek.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Otwórz ładunek, który zawiera wiersz, którego nie można usunąć ani zaktualizować.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.
1. W razie potrzeby kontynuuj wymagane działania. (Na przykład usuń wiersz ładunku lub zmień jego ilość).
1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Otwórz odpowiedni produkt główny, aby przejść do jego strony **Szczegóły zwolnionego produktu**.
1. W okienku akcji na karcie **Produkt** w grupie **Konfiguracja** wybierz pozycję **Konwersje jednostek**.
1. Wybierz konwersję między jednostkami i przywróć korekty wprowadzone w poprzedniej sekcji.
