---
title: Parametry dla planu głównego nie istnieją
description: Podczas próby zatwierdzenia planowanego zlecenia pojawia się komunikat o błędzie, który mówi, że nie istnieją żadne parametry dla planu głównego.
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
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294157"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a><span data-ttu-id="9814b-103">Parametry dla planu głównego nie istnieją</span><span class="sxs-lookup"><span data-stu-id="9814b-103">Parameters for the master plan don't exist</span></span>

<span data-ttu-id="9814b-104">Kod błędu: SYS25368</span><span class="sxs-lookup"><span data-stu-id="9814b-104">Error code: SYS25368</span></span>

## <a name="symptoms"></a><span data-ttu-id="9814b-105">Objawy</span><span class="sxs-lookup"><span data-stu-id="9814b-105">Symptoms</span></span>

<span data-ttu-id="9814b-106">Przy próbie potwierdzenia planowanego zlecenia pojawia się następujący komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="9814b-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="9814b-107">Parametry dla planu głównego %1 nie istnieją.</span><span class="sxs-lookup"><span data-stu-id="9814b-107">Parameters for master plan %1 do not exist.</span></span>

## <a name="cause"></a><span data-ttu-id="9814b-108">Powód</span><span class="sxs-lookup"><span data-stu-id="9814b-108">Cause</span></span>

<span data-ttu-id="9814b-109">Z powodu problemów z konfiguracją system nie może znaleźć ustawień dla określonego planu.</span><span class="sxs-lookup"><span data-stu-id="9814b-109">Because of configuration issues, the system can't find the settings for the specified plan.</span></span>

## <a name="resolution"></a><span data-ttu-id="9814b-110">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="9814b-110">Resolution</span></span>

- <span data-ttu-id="9814b-111">Przejdź do **Planowania głównego \> Konfiguracja \> Plany \> Plany główne** i upewnij się, że istnieje plan o określonej nazwie.</span><span class="sxs-lookup"><span data-stu-id="9814b-111">Go to **Master planning \> Setup \> Plans \> Master plans**, and make sure that a plan that has the specified name exists.</span></span>
