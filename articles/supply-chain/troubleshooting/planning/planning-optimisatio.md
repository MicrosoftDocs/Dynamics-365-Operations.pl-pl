---
title: Planowane zamówienie zakupu jest tworzone, gdy zakup istnieje w ciągu ujemnych dni
description: Jeśli kod zapotrzebowania to Minimum/Maksimum, optymalizacja planowania tworzy planowane zamówienie zakupu jeśli zakup istnieje w ciągu dni ujemnych.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026819"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a><span data-ttu-id="3fee5-103">Planowane zamówienie zakupu jest tworzone, gdy zakup istnieje w ciągu ujemnych dni</span><span class="sxs-lookup"><span data-stu-id="3fee5-103">Planned purchase order is created when a purchase exists within negative days</span></span>

<span data-ttu-id="3fee5-104">Numer artykułu z bazy wiedzy: 4614298</span><span class="sxs-lookup"><span data-stu-id="3fee5-104">KB number: 4614298</span></span>

## <a name="symptoms"></a><span data-ttu-id="3fee5-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="3fee5-105">Symptoms</span></span>

<span data-ttu-id="3fee5-106">Jeśli kod zapotrzebowania to *Minimum/Maksimum*, optymalizacja planowania tworzy planowane zamówienie zakupu jeśli zakup istnieje w ciągu dni ujemnych.</span><span class="sxs-lookup"><span data-stu-id="3fee5-106">If the coverage code is *Min/max*, Planning Optimization creates a planned purchase order when a purchase exists within negative days.</span></span>

## <a name="resolution"></a><span data-ttu-id="3fee5-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="3fee5-107">Resolution</span></span>

<span data-ttu-id="3fee5-108">Optymalizacja planowania nie obsługuje dni ujemnych..</span><span class="sxs-lookup"><span data-stu-id="3fee5-108">Planning Optimization doesn't support negative days.</span></span> <span data-ttu-id="3fee5-109">Jednak zawsze zapewnia, że planowane zamówienia nie zostaną zaplanowane w czasie realizacji w stosunku do bieżącej daty.</span><span class="sxs-lookup"><span data-stu-id="3fee5-109">However, it always ensures that planned orders won't be scheduled within the lead time relative to the current date.</span></span> <span data-ttu-id="3fee5-110">Na przykład czas realizacji zakupu wynosi 10 dni, a zamówienie powinno dotrzeć osiem dni od dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="3fee5-110">For example, the purchase lead time is 10 days, and a purchase order is expected to arrive eight days from today.</span></span> <span data-ttu-id="3fee5-111">W tym przypadku zamówienie zakupu zostanie użyte jako podaż dla popytu w ciągu pięciu dni od dzisiaj.</span><span class="sxs-lookup"><span data-stu-id="3fee5-111">In this case, the purchase order will be used as supply for demand that is five days from today.</span></span>

<span data-ttu-id="3fee5-112">Dlatego zalecamy skorygowanie czasów realizacji, tak aby pokrywały się wszystkie (lub prawie wszystkie) scenariusze.</span><span class="sxs-lookup"><span data-stu-id="3fee5-112">Therefore, we recommend that you adjust your lead times to cover all (or almost all) of your scenarios.</span></span>
