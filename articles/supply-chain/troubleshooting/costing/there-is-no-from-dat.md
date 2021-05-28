---
title: Brak wartości Od dnia na karcie Aktywne ceny na stronie Cena pozycji
description: Brak wartości Od dnia na karcie Aktywne ceny na stronie Cena pozycji.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026828"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a><span data-ttu-id="3918a-103">Brak wartości Od dnia na karcie Aktywne ceny na stronie Cena pozycji</span><span class="sxs-lookup"><span data-stu-id="3918a-103">There is no From date value on the Active prices tab of the Item price page</span></span>

<span data-ttu-id="3918a-104">Numer artykułu z bazy wiedzy: 4613548</span><span class="sxs-lookup"><span data-stu-id="3918a-104">KB number: 4613548</span></span>

## <a name="symptoms"></a><span data-ttu-id="3918a-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="3918a-105">Symptoms</span></span>

<span data-ttu-id="3918a-106">Brak wartości **Od dnia** na karcie **Aktywne ceny** na stronie **Cena pozycji**.</span><span class="sxs-lookup"><span data-stu-id="3918a-106">There is no **From date** value on the **Active prices** tab of the **Item price** page.</span></span>

## <a name="resolution"></a><span data-ttu-id="3918a-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="3918a-107">Resolution</span></span>

<span data-ttu-id="3918a-108">Wartość **Od dnia** (data wejścia w życie) ustawiona dla ceny oczekującej nie jest przeniesiona do aktywnej ceny.</span><span class="sxs-lookup"><span data-stu-id="3918a-108">The **From date** value (effective date) that is set on the pending price isn't transferred to the active price.</span></span>

<span data-ttu-id="3918a-109">Rekord kosztu towaru początkowo jest wprowadzany ze stanem *Oczekujący* oraz zamierzoną datą wprowadzenia.</span><span class="sxs-lookup"><span data-stu-id="3918a-109">When an item cost record is first entered, it has a status of *Pending* and an intended effective date.</span></span> <span data-ttu-id="3918a-110">Aktywacja rekordu kosztu towaru aktualizuje stan (do wartości *Aktywny*)i datę wprowadzenia (do daty aktywacji).</span><span class="sxs-lookup"><span data-stu-id="3918a-110">When you activate the item cost record, the status is updated to *Active*, and the effective date is updated to the activation date.</span></span> <span data-ttu-id="3918a-111">Dlatego data aktywacji aktywnej ceny jest zawsze rzeczywistą datą aktywacji.</span><span class="sxs-lookup"><span data-stu-id="3918a-111">Therefore, the active price's activation date is always the actual date of the activation.</span></span>

<span data-ttu-id="3918a-112">Aby uzyskać więcej informacji, zobacz temat [Omówienie wersji wyceny](../../cost-management/costing-versions.md).</span><span class="sxs-lookup"><span data-stu-id="3918a-112">For more information, see [Costing versions overview](../../cost-management/costing-versions.md).</span></span>
