---
title: Nie można potwierdzić wysyłki z powodu problemu z kalendarzem
description: Nie można potwierdzić wysyłki z powodu problemu z kalendarzem
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
ms.openlocfilehash: 8aae45beeef1934760d620874897f46a1cf901995e2b83e148a1d56898d9c717
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735951"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a>Nie można potwierdzić wysyłki z powodu problemu z kalendarzem

Kod błędu: TRX2716

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Typ kalendarza %1 wymaga, aby termin %2 został zaewidencjonowany i wyewidencjonowany.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

Istnieją aktywne terminy dla ładunku. Na przykład istnieje reguła wymagająca zameldowania kierowcy. Dlatego ładunek jest obecnie w stanie, w którym potwierdzenie wysyłki nie powiedzie się.

## <a name="resolution"></a>Rozdzielczość

Musisz zbadać i rozwiązać wszystkie problemy związane z aktywnymi terminami, które są połączone z ładunkiem.

1. Wybierz kolejno opcje **Zarządzanie magazynem \> Ładunki \> Wszystkie ładunki**.
1. Wybierz ładunek, dla którego wysyłka nie może zostać potwierdzona.
1. W Okienku akcji na karcie **Transport** w grupie **Terminy** wybierz **Planowanie terminów**.
1. Wykonaj jeden z następujących kroków:

    - Upewnij się, że zameldowanie/wymeldowanie kierowcy zostało ukończone dla terminu.
    - Ukończ lub anuluj termin.
    - Wyłącz opcję **Wymagane zameldowanie kierowcy** dla powiązanej reguły terminu.
