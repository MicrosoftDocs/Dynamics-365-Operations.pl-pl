---
title: Aby można było zaakceptować planowane zlecenie produkcyjne, należy je najpierw zaplanować
description: Przy próbie zatwierdzenia planowanego zamówienia pojawia się komunikat o błędzie z informacją, że zamówienie musi być zaplanowane, zanim będzie można je zatwierdzić.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294159"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a><span data-ttu-id="d3d15-103">Aby można było zaakceptować planowane zlecenie produkcyjne, należy je najpierw zaplanować</span><span class="sxs-lookup"><span data-stu-id="d3d15-103">Planned production order must be scheduled before it can be firmed</span></span>

<span data-ttu-id="d3d15-104">Kod błędu: SYS309802</span><span class="sxs-lookup"><span data-stu-id="d3d15-104">Error code: SYS309802</span></span>

## <a name="symptoms"></a><span data-ttu-id="d3d15-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="d3d15-105">Symptoms</span></span>

<span data-ttu-id="d3d15-106">Przy próbie potwierdzenia planowanego zlecenia pojawia się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="d3d15-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="d3d15-107">Aby można było zaakceptować planowane zlecenie produkcyjne, należy je najpierw zaplanować.</span><span class="sxs-lookup"><span data-stu-id="d3d15-107">The planned production order must be scheduled before it can be firmed.</span></span>

## <a name="cause"></a><span data-ttu-id="d3d15-108">Powód</span><span class="sxs-lookup"><span data-stu-id="d3d15-108">Cause</span></span>

<span data-ttu-id="d3d15-109">Planowane daty rozpoczęcia i zakończenia nie mogą być puste.</span><span class="sxs-lookup"><span data-stu-id="d3d15-109">The scheduled start and end dates can't be blank.</span></span>

## <a name="resolution"></a><span data-ttu-id="d3d15-110">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="d3d15-110">Resolution</span></span>

<span data-ttu-id="d3d15-111">Aby określić daty rozpoczęcia i zakończenia dla planowanego zlecenia, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="d3d15-111">To specify start and end dates for the planned order, follow these steps.</span></span>

1. <span data-ttu-id="d3d15-112">Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Zamówienia planowane**.</span><span class="sxs-lookup"><span data-stu-id="d3d15-112">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="d3d15-113">Otwórz odnośne planowane zamówienie.</span><span class="sxs-lookup"><span data-stu-id="d3d15-113">Open the relevant planned order.</span></span>
1. <span data-ttu-id="d3d15-114">Na skróconej karcie **Ogólne**, w sekcji **Zaplanowane** określ daty w polach **Data rozpoczęcia** i **Data zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="d3d15-114">On the **General** FastTab, in the **Scheduled** section, specify dates in the **Start date** and **End date** fields.</span></span>
