---
title: Ilość ze rozpoczętego zlecenia kwarantanny nie jest aktualizowana po podziale zamówienia
description: Po utworzeniu zlecenia kwarantanny i próbie jego podziału ilość zamówienia nie zostanie zaktualizowana zgodnie z pozostałą do podziału ilością.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026826"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a><span data-ttu-id="13c41-103">Ilość ze rozpoczętego zlecenia kwarantanny nie jest aktualizowana po podziale zamówienia</span><span class="sxs-lookup"><span data-stu-id="13c41-103">Quantity on a started quarantine order isn't updated when the order is split</span></span>

<span data-ttu-id="13c41-104">Numer artykułu z bazy wiedzy: 4613113</span><span class="sxs-lookup"><span data-stu-id="13c41-104">KB number: 4613113</span></span>

## <a name="symptoms"></a><span data-ttu-id="13c41-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="13c41-105">Symptoms</span></span>

<span data-ttu-id="13c41-106">Po utworzeniu zlecenia kwarantanny i próbie jego podziału ilość zamówienia nie zostanie zaktualizowana zgodnie z pozostałą do podziału ilością po podziale.</span><span class="sxs-lookup"><span data-stu-id="13c41-106">When you create a quarantine order and try to split it, the order quantity isn't updated to the remaining quantity after the split.</span></span>

## <a name="resolution"></a><span data-ttu-id="13c41-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="13c41-107">Resolution</span></span>

<span data-ttu-id="13c41-108">System nie zmienia oryginalnej ilości ze zlecenia kwarantanny, aby upewnić się, że można śledzić oryginalną ilość utworzoną dla tego zlecenia kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="13c41-108">The system doesn't change the original quantity from a quarantine order to ensure that you can track the original quantity that was created for that quarantine order.</span></span> <span data-ttu-id="13c41-109">System śledzi jednak ilość, która jest dzielona ze zlecenia kwarantanny.</span><span class="sxs-lookup"><span data-stu-id="13c41-109">However, the system does track the quantity that is split from a quarantine order.</span></span> <span data-ttu-id="13c41-110">Do tego śledzenia jest używane pole bazy danych o nazwie `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span><span class="sxs-lookup"><span data-stu-id="13c41-110">To do this tracking, it uses a database field that is named `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span></span> <span data-ttu-id="13c41-111">Jednak to pole nie jest wyświetlane w interfejsie użytkownika (UI).</span><span class="sxs-lookup"><span data-stu-id="13c41-111">However, this field isn't visible in the user interface (UI).</span></span>
