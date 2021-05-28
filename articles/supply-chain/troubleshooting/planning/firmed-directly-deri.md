---
title: Bezpośrednie pochodne zamówienia firmowe są przetwarzane w przepływie pracy w przeglądzie
description: Bezpośrednio wyprowadzone zamówienia potwierdzone są przetwarzane przez przepływ pracy, który ma stan W trakcie przeglądu.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026821"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a><span data-ttu-id="52f35-103">Bezpośrednie pochodne zamówienia firmowe są przetwarzane w przepływie pracy w przeglądzie</span><span class="sxs-lookup"><span data-stu-id="52f35-103">Directly derived firmed orders are processed by an in-review workflow</span></span>

<span data-ttu-id="52f35-104">Numer artykułu z bazy wiedzy: 4612450</span><span class="sxs-lookup"><span data-stu-id="52f35-104">KB number: 4612450</span></span>

## <a name="symptoms"></a><span data-ttu-id="52f35-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="52f35-105">Symptoms</span></span>

<span data-ttu-id="52f35-106">Bezpośrednio wyprowadzone zamówienia potwierdzone są przetwarzane przez przepływ pracy, który ma stan *W trakcie przeglądu*.</span><span class="sxs-lookup"><span data-stu-id="52f35-106">Directly derived firmed orders are processed by a workflow that has a status of *In-review*.</span></span>

## <a name="resolution"></a><span data-ttu-id="52f35-107">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="52f35-107">Resolution</span></span>

<span data-ttu-id="52f35-108">Gdy włączone jest śledzenie zmian, do zatwierdzonych zamówień pochodnych (zamówienia podwykonawstwa) przypisywany jest status *W trakcie przeglądu*.</span><span class="sxs-lookup"><span data-stu-id="52f35-108">When change tracking is enabled, a status of *In-review* is assigned to firmed derived orders (subcontract purchase orders).</span></span> <span data-ttu-id="52f35-109">W związku z tym, jeśli zamówienie zakupu jest pochodne (zamówienie zakupu dla podumowy), jest przesyłane tylko do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="52f35-109">Therefore, if a purchase order is derived (a subcontract purchase order), it's only submitted to a workflow.</span></span> <span data-ttu-id="52f35-110">Jeśli zamówienie zakupu jest zaakceptowane planowane zamówienie zakupu, jest ono automatycznie zatwierdzane w celu zapewnienia, że aparat planowania nie będzie tworzyć nowych zamówień planowanych, dopóki zamówienie zakupu ma nadal stan *Wersja robocza*.</span><span class="sxs-lookup"><span data-stu-id="52f35-110">If a purchase order is a firmed planned purchase order, it's automatically approved to ensure that the planning engine doesn't create new planned orders while the purchase order is still in *Draft* status.</span></span>
