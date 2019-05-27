---
title: 'Przepływ pracy: często zadawane pytania'
description: W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509298"
---
# <a name="workflow-system"></a><span data-ttu-id="1d50b-103">System przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="1d50b-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d50b-104">W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1d50b-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="1d50b-105">Powiadomienia</span><span class="sxs-lookup"><span data-stu-id="1d50b-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="1d50b-106">Dlaczego otrzymuję wiele powiadomień, gdy element pracy został odrzucony?</span><span class="sxs-lookup"><span data-stu-id="1d50b-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="1d50b-107">Gdy element pracy został odrzucony, zostaje zakończony jako odrzucony.</span><span class="sxs-lookup"><span data-stu-id="1d50b-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="1d50b-108">Inny element pracy zostanie utworzony i przypisany do inicjatora.</span><span class="sxs-lookup"><span data-stu-id="1d50b-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="1d50b-109">Oznacza to, że inicjator otrzyma powiadomienie o odrzuconym elemencie pracy, a osobne powiadomienie zostanie wysłane do użytkownika przypisanego nowego elementu pracy „Zażądano zmiany”.</span><span class="sxs-lookup"><span data-stu-id="1d50b-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="1d50b-110">Każde powiadomienie dotyczy innego elementu pracy, ale podobieństwa mogą powodować zamieszanie.</span><span class="sxs-lookup"><span data-stu-id="1d50b-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="1d50b-111">Szukamy sposobów, aby to poprawić w przyszłej wersji.</span><span class="sxs-lookup"><span data-stu-id="1d50b-111">We are looking at ways to improve this in a future release.</span></span>

### <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="1d50b-112">Dlaczego moje próby eksportu przepływu pracy kończą się niepowodzeniem?</span><span class="sxs-lookup"><span data-stu-id="1d50b-112">Why are my workflow exports failing?</span></span>
<span data-ttu-id="1d50b-113">Obecnie istnieje ograniczenie funkcji eksportu przepływu pracy, które zapobiega przekraczaniu 48 znaków w nazwach przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="1d50b-113">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="1d50b-114">Użycie nazwy, która jest dłuższa niż 48 znaków może spowodować wyświetlenie komunikatu o błędzie „Serwer nie może uwierzytelnić żądania” lub uniemożliwienie wyeksportowania pliku bez typu pliku.</span><span class="sxs-lookup"><span data-stu-id="1d50b-114">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="1d50b-115">Poniższy wpis w blogu zawiera dodatkowe szczegóły [Rozwiązywanie problemów z eksportowaniem przepływów pracy](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="1d50b-115">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>
