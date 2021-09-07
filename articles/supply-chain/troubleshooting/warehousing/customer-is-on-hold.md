---
title: Nie można potwierdzić wysyłki, ponieważ klient został wstrzymany
description: Nie można potwierdzić wysyłki, ponieważ klient został wstrzymany.
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
ms.openlocfilehash: 801778fc8f04b106bf168a3dcd5a89767a837740
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344271"
---
# <a name="you-cant-confirm-a-shipment-because-the-customer-is-on-hold"></a>Nie można potwierdzić wysyłki, ponieważ klient został wstrzymany

Kod błędu: WAX:CustomerOnHoldShipmentCannotBeConfirmed

## <a name="symptoms"></a>Objawy

Przy próbie potwierdzenia wysyłki system wyświetla następujący komunikat o błędzie:

> Nie można potwierdzić wysyłki %1, ponieważ odbiorca jest wstrzymany dla %2.

W związku z tym nie możesz potwierdzić wysyłki dla tego ładunku.

## <a name="cause"></a>Powód

Konto klienta dla ładunku lub przesyłki jest wstrzymane. W związku z tym stan klienta uniemożliwia potwierdzenie wysyłki.

## <a name="resolution"></a>Rozwiązanie

Aby odblokować konto klienta, użyj poniższej procedury.

1. Wybierz kolejno opcje **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**.
1. Otwórz konto klienta, dla którego wysyłka nie może zostać potwierdzona.
1. Na skróconej karcie **Kredyty i windykacje** ustaw pole **Fakturowania i dostawy zablokowane** na *Nie*.
1. Powtórz tę procedurę dla wszystkich zablokowanych klientów dla ładunku.
