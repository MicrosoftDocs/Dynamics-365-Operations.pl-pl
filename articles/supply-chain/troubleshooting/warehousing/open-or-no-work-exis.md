---
title: Nie można potwierdzić wysyłki z powodu niekompletnej lub brakującej pracy
description: Nie można potwierdzić wysyłki z powodu niekompletnej lub brakującej pracy
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123850"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a>Nie można potwierdzić wysyłki z powodu niekompletnej lub brakującej pracy

Kod błędu: WAX515

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Nie można potwierdzić wysyłki ładunku %1, ponieważ cała praca dla ładunku musi zostać zakończona.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

Ładunek lub wysyłka jest obecnie w stanie, w którym potwierdzenie wysyłki nie powiedzie się. Aby można było potwierdzić wysyłkę, dla ładunku musi istnieć co najmniej jedna praca, a wszystkie prace muszą mieć stan *Zamknięte* lub *Anulowane*.

## <a name="resolution"></a>Rozdzielczość

Sprawdź powiązane zamówienia sprzedaży lub zamówienia przeniesienia dla ładunku lub wysyłki i upewnij się, że cała powiązana praca została zakończona lub anulowana.

Praca z wysyłkami i ładunkami jest możliwa na różnych stronach. Poniższe podsekcji zawierają kilka przykładów.

### <a name="all-loads-page"></a>Strona Wszystkie ładunki

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. W okienku akcji, na karcie **Ładunki**, w grupie **Informacje pokrewne** wybierz opcję **Praca**.
1. Sprawdź stan każdego identyfikatora pracy. Skontroluj każdy identyfikator pracy, który nie ma stanu *Zamknięty* ani *Anulowany*.
1. Jeśli każdy identyfikator pracy ma stan *Zamknięty* lub *Anulowany*, spróbuj ponownie potwierdzić wysyłkę.

### <a name="all-shipments-page"></a>Strona Wszystkie wysyłki

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Wysyłki \> Wszystkie wysyłki**.
1. Wybierz wysyłkę, która nie może zostać potwierdzona.
1. W okienku akcji, na karcie **Wysyłki**, w grupie **Praca** wybierz pozycję **Szczegóły pracy**.
1. Sprawdź stan każdego identyfikatora pracy. Skontroluj każdy identyfikator pracy, który nie ma stanu *Zamknięty* ani *Anulowany*.
1. Jeśli każdy identyfikator pracy ma stan *Zamknięty* lub *Anulowany*, spróbuj ponownie potwierdzić wysyłkę.

### <a name="all-work-page"></a>Strona Wszystkie prace

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Praca\> Wszystkie prace**.
1. Wybierz pracę dla numeru zamówienia, dla którego nie można potwierdzić wysyłki.
1. W okienku akcji na karcie **Wysyłka** w grupie **Wysyłka** kliknij opcję **Potwierdź wysyłkę**.
1. Sprawdź stan każdego identyfikatora pracy. Skontroluj każdy identyfikator pracy, który nie ma stanu *Zamknięty* ani *Anulowany*.
1. Jeśli każdy identyfikator pracy ma stan *Zamknięty* lub *Anulowany*, spróbuj ponownie potwierdzić wysyłkę.
