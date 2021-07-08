---
title: Anulowane przyjęcia produktów nie aktualizują stanu transakcji na zarejestrowane
description: Po anulowaniu przyjęcia produktów w ładunku przychodzącym system automatycznie aktualizuje status transakcji inwentaryzacyjnej z Otrzymane na Zamówione.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c86457d50a7a9ac2a699a0e0a9c7bdf4cd7c67b
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294153"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a>Anulowane przyjęcia produktów nie aktualizują stanu transakcji na zarejestrowane

## <a name="symptoms"></a>Objawy

Po **Anulowaniu przyjęcia rachunków produktów** w ładunku przychodzącym system automatycznie aktualizuje status transakcji inwentaryzacyjnej z *Otrzymane* na *Zamówione*.

## <a name="resolution"></a>Rozwiązanie

Po anulowaniu dokumentów dostawy dla ładunków wychodzących stan transakcji magazynowych to *Pobrano*. Jednak po anulowaniu dokumentów przyjęcia produktów z ładunku przychodzącego stan transakcji magazynowych nie zostanie przywrócony do stanu *Zarejestrowane*. Dlatego po anulowaniu przyjęcia produktu z ładunku przychodzącego pracownik magazynu musi ponownie zarejestrować ilości pozycji dla ładunków.

Aby uzyskać więcej informacji, zobacz temat [Rejestrowanie ilości towarów przychodzących w ładunku przychodzącym](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).
