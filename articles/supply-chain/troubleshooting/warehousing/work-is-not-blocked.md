---
title: Praca nie jest zablokowana
description: Praca nie jest zablokowana
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924211"
---
# <a name="work-isnt-blocked"></a><span data-ttu-id="97bf5-103">Praca nie jest zablokowana</span><span class="sxs-lookup"><span data-stu-id="97bf5-103">Work isn't blocked</span></span>

<span data-ttu-id="97bf5-104">Kod błędu: WHSUnblockNotBlockedWorkErrorMessage</span><span class="sxs-lookup"><span data-stu-id="97bf5-104">Error code: WHSUnblockNotBlockedWorkErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="97bf5-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="97bf5-105">Symptoms</span></span>

<span data-ttu-id="97bf5-106">W systemie wyświetlany jest następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="97bf5-106">The system shows the following error message:</span></span>

> <span data-ttu-id="97bf5-107">Praca o identyfikatorze %1 nie jest zablokowana.</span><span class="sxs-lookup"><span data-stu-id="97bf5-107">Work with Id %1 is not blocked.</span></span>

## <a name="cause"></a><span data-ttu-id="97bf5-108">Powód</span><span class="sxs-lookup"><span data-stu-id="97bf5-108">Cause</span></span>

<span data-ttu-id="97bf5-109">Opcja **Zablokowana grupy czynności** dla grupy czynności ma wartość *Nie*.</span><span class="sxs-lookup"><span data-stu-id="97bf5-109">The **Blocked wave** option on the wave is set to *No*.</span></span> <span data-ttu-id="97bf5-110">Nie można odblokować pracy, ponieważ nie jest ona obecnie zablokowana.</span><span class="sxs-lookup"><span data-stu-id="97bf5-110">The work can't be unblocked because it isn't currently blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="97bf5-111">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="97bf5-111">Resolution</span></span>

 <span data-ttu-id="97bf5-112">Odblokować można tylko wtedy, gdy dla opcji **Zablokowana grupy czynności** jest ustawiona wartość *Tak*.</span><span class="sxs-lookup"><span data-stu-id="97bf5-112">Only work where the **Blocked wave** option is set to *Yes* can be unblocked.</span></span>
