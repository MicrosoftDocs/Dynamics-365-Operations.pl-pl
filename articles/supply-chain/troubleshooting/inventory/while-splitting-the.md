---
title: Po podziale ilości w ilości catch zamiast ilości nominalnej używana jest ilość minimalna
description: W przypadku podziału ilości catch na partie w polu Ilość pobrania jest używana minimalna ilość ustawiona dla towaru, a nie ilość nominalna.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026822"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a><span data-ttu-id="49fa6-103">Po podziale ilości w ilości catch zamiast ilości nominalnej używana jest ilość minimalna</span><span class="sxs-lookup"><span data-stu-id="49fa6-103">When a catch-weight quantity is split, minimum quantity is used instead of nominal quantity</span></span>

<span data-ttu-id="49fa6-104">Numer artykułu z bazy wiedzy: 4612073</span><span class="sxs-lookup"><span data-stu-id="49fa6-104">KB number: 4612073</span></span>

## <a name="symptoms"></a><span data-ttu-id="49fa6-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="49fa6-105">Symptoms</span></span>

<span data-ttu-id="49fa6-106">W przypadku podziału ilości catch na partie w polu **Ilość pobrania** jest używana minimalna ilość ustawiona dla towaru, a nie ilość nominalna.</span><span class="sxs-lookup"><span data-stu-id="49fa6-106">When a catch-weight quantity is being split into batches, the **Pick qty** field uses the minimum quantity that is set for the item, not the nominal quantity.</span></span>

## <a name="resolution"></a><span data-ttu-id="49fa6-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="49fa6-107">Resolution</span></span>

<span data-ttu-id="49fa6-108">System jest szybując tak jak zaprojektowany.</span><span class="sxs-lookup"><span data-stu-id="49fa6-108">The system is behaving as designed.</span></span> <span data-ttu-id="49fa6-109">Do pobrania system używa konfiguracji minimalnej ilości poszczególnych towarów.</span><span class="sxs-lookup"><span data-stu-id="49fa6-109">The system uses each item's minimum quantity setup for picking.</span></span>
