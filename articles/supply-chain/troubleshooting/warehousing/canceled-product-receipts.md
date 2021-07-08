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
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a><span data-ttu-id="cb01c-103">Anulowane przyjęcia produktów nie aktualizują stanu transakcji na zarejestrowane</span><span class="sxs-lookup"><span data-stu-id="cb01c-103">Canceled product receipts don't update transaction status to Registered</span></span>

## <a name="symptoms"></a><span data-ttu-id="cb01c-104">Objawy</span><span class="sxs-lookup"><span data-stu-id="cb01c-104">Symptoms</span></span>

<span data-ttu-id="cb01c-105">Po **Anulowaniu przyjęcia rachunków produktów** w ładunku przychodzącym system automatycznie aktualizuje status transakcji inwentaryzacyjnej z *Otrzymane* na *Zamówione*.</span><span class="sxs-lookup"><span data-stu-id="cb01c-105">After you run the **Cancel product receipts** action on an inbound load, the system automatically updates the status of inventory transactions from *Received* to *Ordered*.</span></span>

## <a name="resolution"></a><span data-ttu-id="cb01c-106">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="cb01c-106">Resolution</span></span>

<span data-ttu-id="cb01c-107">Po anulowaniu dokumentów dostawy dla ładunków wychodzących stan transakcji magazynowych to *Pobrano*.</span><span class="sxs-lookup"><span data-stu-id="cb01c-107">When packing slips are canceled for outbound loads, the status of inventory transactions remains *Picked*.</span></span> <span data-ttu-id="cb01c-108">Jednak po anulowaniu dokumentów przyjęcia produktów z ładunku przychodzącego stan transakcji magazynowych nie zostanie przywrócony do stanu *Zarejestrowane*.</span><span class="sxs-lookup"><span data-stu-id="cb01c-108">However, when product receipts from an inbound load are canceled, the status of inventory transactions isn't restored to *Registered*.</span></span> <span data-ttu-id="cb01c-109">Dlatego po anulowaniu przyjęcia produktu z ładunku przychodzącego pracownik magazynu musi ponownie zarejestrować ilości pozycji dla ładunków.</span><span class="sxs-lookup"><span data-stu-id="cb01c-109">Therefore, after a product receipt from an inbound load is canceled, the warehouse worker must re-register item quantities for the loads.</span></span>

<span data-ttu-id="cb01c-110">Aby uzyskać więcej informacji, zobacz temat [Rejestrowanie ilości towarów przychodzących w ładunku przychodzącym](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span><span class="sxs-lookup"><span data-stu-id="cb01c-110">For more information, see [Register item quantities that arrive on an inbound load](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).</span></span>
