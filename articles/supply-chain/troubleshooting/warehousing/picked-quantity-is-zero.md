---
title: Nie można potwierdzić wysyłki, ponieważ ilość jest zerowa
description: Nie można potwierdzić wysyłki, ponieważ ilość jest zerowa
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938531"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a>Nie można potwierdzić wysyłki, ponieważ ilość jest zerowa

Kod błędu: LoadLineWarningUpdatedToZero

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Wiersz obciążenia pracą dla pozycji %1 i wysyłki %2 został zaktualizowany tak, aby zawierał ilość zerową, z powodu konfiguracji niedoboru w dostawie, która zezwala na rezygnację z wysyłki dowolnych ilości dla tej pozycji.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

System sprawdza, czy ilość pobrana jest w oczekiwanym zakresie na podstawie pobranej ilości, ilości w wierszu ładunku i wartości procentowej niedoboru. Jeśli system znajdzie w wierszu ładunku ilość pobrania równą 0 (zero), nie będzie można potwierdzić wysyłki. Ten problem może wystąpić na przykład, jeśli praca została anulowana, a wartość procentowa niedoboru w wierszu ładunku wynosi 100 procent.

## <a name="resolution"></a>Rozdzielczość

Sprawdź wiersze ładunku, aby mieć pewność, że wartość procentowa niedoboru i ilości są zgodne z pobraną pracą.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent niedoboru w dostawie.
1. Zależnie od sytuacji skoryguj wartość pola **Niedobór** lub pola **Ilość**.

> [!TIP]
> Jeśli problem nadal nie zostanie rozwiązany, może być konieczne zakończenie większej ilości prac pobierania dla powiązanych zamówień sprzedaży lub zamówień przeniesienia, aby dostępna ilość została zrównana z ładunkiem lub wysyłką.
