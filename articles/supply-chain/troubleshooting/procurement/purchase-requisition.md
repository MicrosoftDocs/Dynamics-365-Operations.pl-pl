---
title: Po wniosku o zmianę nie można dodać wiersza do zapotrzebowania zakupu
description: System nie pozwala na dodanie wiersza do zapotrzebowania na zakup po zażądaniu zmiany.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchReqTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: jeyao
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5dbb55a6a352a7acf16729c1cfe1afdac2e2eef8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026818"
---
# <a name="you-cant-add-a-line-to-a-purchase-requisition-after-you-request-a-change"></a><span data-ttu-id="365d7-103">Po wniosku o zmianę nie można dodać wiersza do zapotrzebowania zakupu</span><span class="sxs-lookup"><span data-stu-id="365d7-103">You can't add a line to a purchase requisition after you request a change</span></span>

<span data-ttu-id="365d7-104">Numer artykułu z bazy wiedzy: 4611211</span><span class="sxs-lookup"><span data-stu-id="365d7-104">KB number: 4611211</span></span>

## <a name="symptoms"></a><span data-ttu-id="365d7-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="365d7-105">Symptoms</span></span>

<span data-ttu-id="365d7-106">System nie pozwala na dodanie wiersza do zapotrzebowania na zakup po zażądaniu zmiany.</span><span class="sxs-lookup"><span data-stu-id="365d7-106">The system doesn't allow you to add a line to a purchase requisition after you request a change.</span></span>

## <a name="resolution"></a><span data-ttu-id="365d7-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="365d7-107">Resolution</span></span>

<span data-ttu-id="365d7-108">Wycofaj przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="365d7-108">You must recall the workflow.</span></span> <span data-ttu-id="365d7-109">Gdy stan zapotrzebowania zakupu ma stan *Wersja robocza*, można kontynuować jego edycję lub dodać do niego wiersz.</span><span class="sxs-lookup"><span data-stu-id="365d7-109">After the purchase requisition is in *Draft* status, you can continue to edit it or add a line to it.</span></span>
