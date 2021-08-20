---
title: Nie można potwierdzić wysyłki, ponieważ ilość wierszy ładunku wynosi zero
description: Nie można potwierdzić wysyłki, ponieważ ilość wierszy ładunku wynosi zero.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 5dc5f8962ba37d21d7ef505fea940dc8767a9d9295588cb0e12e9eebe379a35c
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012203"
---
# <a name="you-cant-confirm-a-shipment-because-load-lines-have-zero-quantity"></a>Nie można potwierdzić wysyłki, ponieważ ilość wierszy ładunku wynosi zero

Kod błędu: WAX:LoadTableWarningAllLinesZero, WAX2543

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Wszystkie wiersze w obciążeniu pracą %1 mają ilość wynoszącą zero.  
> Nie można potwierdzić wysyłki ładunku %1.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

System sprawdza, czy wiersz ładunku może zostać potwierdzony na podstawie utworzonych identyfikatorów pracy, ilości w wierszu ładunku i procentu niedoboru dostawy. Jeśli system stwierdzi, że nie ma identyfikatorów pracy, a wartość procentowa dostawy z niedoborem jest ustawiona na 100 procent, nie można potwierdzić wysyłki.

Ten problem może wystąpić na przykład, jeśli praca została anulowana, a wartość procentowa niedoboru w wierszu ładunku wynosi 100 procent.

## <a name="resolution"></a>Rozwiązanie

Ładunek lub wysyłka jest obecnie w stanie, w którym potwierdzenie wysyłki nie powiedzie się. Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Przejrzyj wiersze ładunku, aby upewnić się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.
- Przejrzyj wiersze ładunku, aby mieć pewność, że wartość procentowa niedoboru i ilości są zgodne z pobraną pracą.

### <a name="review-your-load-lines-to-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Przejrzyj wiersze ładunku, aby upewnić się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają

Poniższa procedura służy do przeglądu wierszy ładunku i upewnienia się, że wszystkie powiązane prace zostały wykonane w ostatecznym miejscu wysyłki, a ilości się zgadzają.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Otwórz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.
1. Zanotuj wartość pola **Ilość stworzonych prac**.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.
1. W przypadku znalezienia niezgodności anuluj odpowiednią pracę, ponownie skonfiguruj dyrektywę lokalizacji i ponownie zwolnij ładunek. Aby uzyskać instrukcje, zobacz temat [Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary](picked-quantity-is-not-on-final.md).
1. Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.

### <a name="review-your-load-lines-to-make-sure-that-the-underdelivery-percentage-and-quantities-are-aligned-with-the-picked-work"></a>Przejrzyj wiersze ładunku, aby mieć pewność, że wartość procentowa niedoboru i ilości są zgodne z pobraną pracą

Użyj następującej procedury, aby przejrzeć wiersze ładunku, aby mieć pewność, że wartość procentowa niedoboru i ilości są zgodne z pobraną pracą.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Otwórz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent niedoboru w dostawie.
1. Zależnie od sytuacji skoryguj wartość pola **Niedobór** lub pola **Ilość**.

> [!TIP]
> Jeśli problem nadal nie zostanie rozwiązany, może być konieczne zakończenie większej ilości prac pobierania dla powiązanych zamówień sprzedaży lub zamówień przeniesienia, aby dostępna ilość została zrównana z ładunkiem lub wysyłką.
