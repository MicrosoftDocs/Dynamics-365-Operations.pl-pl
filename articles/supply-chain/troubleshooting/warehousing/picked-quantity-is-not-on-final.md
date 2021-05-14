---
title: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
description: Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938532"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Nie można potwierdzić wysyłki, ponieważ nie zostały jeszcze pobrane towary

Kod błędu: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Niektóre towary wymagane w ładunku %1 nie zostały jeszcze pobrane i przeniesione do końcowej lokalizacji wysyłki.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

Nie można potwierdzić ładunku lub wysyłki w jego bieżącym stanie, ponieważ może istnieć jeden z następujących warunków:

- Powiązana praca nie została jeszcze pobrana i przeniesiona do końcowej lokalizacji wysyłki.
- Ilość pobrania pracy nie odpowiada utworzonej ilości pracy w wierszu ładunku.

## <a name="resolution"></a>Rozdzielczość

Sprawdź powiązane zamówienia sprzedaży lub zamówienia przeniesienia dla ładunku lub wysyłki. Upewnij się, że wszystkie powiązane prace zostały zakończone w końcowej lokalizacji wysyłki i czy ilości są zgodne.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Wiersze ładunku** wybierz wiersz ładunku.
1. Zanotuj wartość pola **Ilość stworzonych prac**.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. Sprawdź, czy praca została zakończona w końcowej lokalizacji wysyłki i czy ilość pobrania pracy odpowiada ilości stworzonych prac w wierszu ładunku.
1. Powtórz tę procedurę dla wszystkich wierszy ładunku, aby upewnić się, że wszystkie kryteria są spełnione.
