---
title: Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową nadwyżki w dostawie
description: Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową nadwyżki w dostawie
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
ms.openlocfilehash: c9b5ba8dedb927ee049d7e53e9a666902f563f49
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938535"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a>Nie można potwierdzić wysyłki, ponieważ ilość przekracza wartość procentową nadwyżki w dostawie

Kod błędu: WAX1687

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Nie można potwierdzić wysyłki ładunku %1, ponieważ ilość pozycji %2 przekracza procent określony dla nadwyżki w dostawie.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

Ilość ładunku lub wysyłki została tylko częściowo pobrana. Ilość przekracza obecnie ilość pobraną o procent, który jest poza dozwolonym procentem nadwyżki w dostawie.

## <a name="resolution"></a>Rozdzielczość

Aby naprawić ten problem, wykonaj jedno lub więcej z następujących zadań:

- Ustaw ilość w wierszu ładunku.
- Ustaw wartość procentową nadwyżki w dostawie.

### <a name="set-the-load-line-quantity"></a>Ustawianie ilości w wierszu ładunku

Aby ustawić ilość w wierszu ładunku, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent nadwyżki w dostawie.
1. Na skróconej karcie **Szczegóły wiersza** wybierz **Zamówienie**.
1. W polu **Ilość** ustaw wartość na pobraną ilość (to jest wartość **Ilość stworzonych prac**), aby mogło dojść do potwierdzenia wysyłki.

### <a name="set-the-overdelivery-percentage"></a>Ustawianie wartości procentowej nadwyżki w dostawie

Aby ustawić wartość procentową niedoboru w dostawie, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku dla pozycji, która przekracza procent nadwyżki w dostawie.
1. Na skróconej karcie **Szczegóły wiersza** wybierz **Ogólne**.
1. W polu **Nadwyżka w dostawie** ustaw większą wartość procentową, która mieści się w ilości pobrania w stosunku do ilości ładunku, aby było można potwierdzić wysyłkę.
