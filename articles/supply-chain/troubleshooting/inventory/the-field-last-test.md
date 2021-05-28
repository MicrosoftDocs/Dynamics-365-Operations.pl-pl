---
title: Pole Data ostatniego testu nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości
description: Pole Data ostatniego testu nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026824"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a><span data-ttu-id="9caaa-103">Pole Data ostatniego testu nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości</span><span class="sxs-lookup"><span data-stu-id="9caaa-103">The Last tested date field isn't updated when multiple quality orders are created</span></span>

<span data-ttu-id="9caaa-104">Numer artykułu z bazy wiedzy: 4612803</span><span class="sxs-lookup"><span data-stu-id="9caaa-104">KB number: 4612803</span></span>

## <a name="symptoms"></a><span data-ttu-id="9caaa-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="9caaa-105">Symptoms</span></span>

<span data-ttu-id="9caaa-106">Pole **Data ostatniego testu** nie jest aktualizowane podczas tworzenia wielu zleceń kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="9caaa-106">The **Last tested date** field isn't updated when multiple quality orders are created.</span></span>

## <a name="resolution"></a><span data-ttu-id="9caaa-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="9caaa-107">Resolution</span></span>

<span data-ttu-id="9caaa-108">System jest szybując tak jak zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="9caaa-108">The system is behaving as designed.</span></span> <span data-ttu-id="9caaa-109">Data ostatniego testowego nie jest powiązana ze zleceniami kontroli jakości.</span><span class="sxs-lookup"><span data-stu-id="9caaa-109">The last tested date isn't related to quality orders.</span></span> <span data-ttu-id="9caaa-110">Przechowuje datę, kiedy ukończone towary zostały zakupione lub wytworzone.</span><span class="sxs-lookup"><span data-stu-id="9caaa-110">It stores the date when the finished goods were first purchased or manufactured.</span></span> <span data-ttu-id="9caaa-111">Data ta jest używana do obliczania terminu przydatności.</span><span class="sxs-lookup"><span data-stu-id="9caaa-111">This date is used to calculate the shelf life advice date.</span></span>
