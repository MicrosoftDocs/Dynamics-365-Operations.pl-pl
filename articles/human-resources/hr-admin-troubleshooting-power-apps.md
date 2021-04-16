---
title: Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps
description: W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f1a086f1b710de9bad898abc740286c174ae3be7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797992"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="1e639-103">Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps</span><span class="sxs-lookup"><span data-stu-id="1e639-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1e639-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="1e639-104">**Issue**</span></span>

- <span data-ttu-id="1e639-105">Administrator dzierżawy/środowiska nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1e639-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="1e639-106">Użytkownik nie ma licencji, która daje prawo do tworzenia środowisk.</span><span class="sxs-lookup"><span data-stu-id="1e639-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="1e639-107">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="1e639-107">**Solution**</span></span>

<span data-ttu-id="1e639-108">Upewnij się, że administrator dzierżawy przypisał prawidłową licencję Power Apps P2 do użytkownika tworzącego środowisko.</span><span class="sxs-lookup"><span data-stu-id="1e639-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="1e639-109">Następujące plany usług Microsoft Dynamics zapewniają uprawnienia do tworzenia środowisk:</span><span class="sxs-lookup"><span data-stu-id="1e639-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="1e639-110">Ogólna jednostka magazynowa produktu (SKU)</span><span class="sxs-lookup"><span data-stu-id="1e639-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="1e639-111">Power Apps planu usług P2</span><span class="sxs-lookup"><span data-stu-id="1e639-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="1e639-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="1e639-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="1e639-113">Power Apps dla usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1e639-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="1e639-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="1e639-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="1e639-115">Power Apps dla usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1e639-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="1e639-116">Należy zwrócić uwagę, że różne wersje SKU pakietu Microsoft Office także zapewniają to prawo, wraz z autonomicznymi jednostkami SKU Power Apps Plan 2</span><span class="sxs-lookup"><span data-stu-id="1e639-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="1e639-117">Istotne jest to, że jedna z tych jednostek SKU musi występować.</span><span class="sxs-lookup"><span data-stu-id="1e639-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="1e639-118">Przejdź do [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="1e639-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="1e639-119">Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Human Resouces](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="1e639-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]