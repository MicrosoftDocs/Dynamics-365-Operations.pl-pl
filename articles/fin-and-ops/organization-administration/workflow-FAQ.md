---
title: 'Przepływ pracy: często zadawane pytania'
description: W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/01/2019
ms.locfileid: "773227"
---
# <a name="workflow-system"></a><span data-ttu-id="45ac2-103">System przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="45ac2-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45ac2-104">W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="45ac2-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="45ac2-105">Powiadomienia</span><span class="sxs-lookup"><span data-stu-id="45ac2-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="45ac2-106">Dlaczego otrzymuję wiele powiadomień, gdy element pracy został odrzucony?</span><span class="sxs-lookup"><span data-stu-id="45ac2-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="45ac2-107">Gdy element pracy został odrzucony, zostaje zakończony jako odrzucony.</span><span class="sxs-lookup"><span data-stu-id="45ac2-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="45ac2-108">Inny element pracy zostanie utworzony i przypisany do inicjatora.</span><span class="sxs-lookup"><span data-stu-id="45ac2-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="45ac2-109">Oznacza to, że inicjator otrzyma powiadomienie o odrzuconym elemencie pracy, a osobne powiadomienie zostanie wysłane do użytkownika przypisanego nowego elementu pracy „Zażądano zmiany”.</span><span class="sxs-lookup"><span data-stu-id="45ac2-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="45ac2-110">Każde powiadomienie dotyczy innego elementu pracy, ale podobieństwa mogą powodować zamieszanie.</span><span class="sxs-lookup"><span data-stu-id="45ac2-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="45ac2-111">Szukamy sposobów, aby to poprawić w przyszłej wersji.</span><span class="sxs-lookup"><span data-stu-id="45ac2-111">We are looking at ways to improve this in a future release.</span></span>
