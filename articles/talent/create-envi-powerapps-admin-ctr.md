---
title: Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps
description: W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5923c59ab5dde13fed0483972e76634031404fd8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773226"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="370cf-103">Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps</span><span class="sxs-lookup"><span data-stu-id="370cf-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="370cf-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="370cf-104">**Issue**</span></span>

- <span data-ttu-id="370cf-105">Administrator dzierżawy/środowiska nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="370cf-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="370cf-106">Licencja, która daje użytkownikom prawo do wykonywania kroku tworzenia środowiska nie została przypisana bezpośrednio do użytkownika, który wykonuje ten krok.</span><span class="sxs-lookup"><span data-stu-id="370cf-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="370cf-107">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="370cf-107">**Solution**</span></span>

<span data-ttu-id="370cf-108">Upewnij się, że administrator dzierżawy ma przypisaną prawidłową licencję usługi Power Apps P2 bezpośrednio do użytkownika, który wykona krok tworzenia środowiska.</span><span class="sxs-lookup"><span data-stu-id="370cf-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="370cf-109">Poniżej przedstawiono plany usługowe Microsoft Dynamics, które zapewniają te prawa.</span><span class="sxs-lookup"><span data-stu-id="370cf-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="370cf-110">Ogólna jednostka magazynowa produktu (SKU)</span><span class="sxs-lookup"><span data-stu-id="370cf-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="370cf-111">Power Apps planu usług P2</span><span class="sxs-lookup"><span data-stu-id="370cf-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="370cf-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="370cf-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="370cf-113">Power Apps dla usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="370cf-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="370cf-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="370cf-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="370cf-115">Power Apps dla usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="370cf-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="370cf-116">Należy zwrócić uwagę, że różne wersje SKU pakietu Microsoft Office także zapewniają to prawo, wraz z autonomicznymi jednostkami SKU Power Apps Plan 2</span><span class="sxs-lookup"><span data-stu-id="370cf-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="370cf-117">Istotne jest to, że jedna z tych jednostek SKU musi występować.</span><span class="sxs-lookup"><span data-stu-id="370cf-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="370cf-118">Przejdź do [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="370cf-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="370cf-119">Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="370cf-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
