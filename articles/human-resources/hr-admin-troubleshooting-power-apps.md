---
title: Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps
description: W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
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
ms.openlocfilehash: 68e6dbcbbc9811211570e968047f5faa8a2c8bd0
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431068"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="0e4f0-103">Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps</span><span class="sxs-lookup"><span data-stu-id="0e4f0-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="0e4f0-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="0e4f0-104">**Issue**</span></span>

- <span data-ttu-id="0e4f0-105">Administrator dzierżawy/środowiska nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="0e4f0-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="0e4f0-106">Licencja, która daje użytkownikom prawo do wykonywania kroku tworzenia środowiska nie została przypisana bezpośrednio do użytkownika, który wykonuje ten krok.</span><span class="sxs-lookup"><span data-stu-id="0e4f0-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="0e4f0-107">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="0e4f0-107">**Solution**</span></span>

<span data-ttu-id="0e4f0-108">Upewnij się, że administrator dzierżawy ma przypisaną prawidłową licencję usługi Power Apps P2 bezpośrednio do użytkownika, który wykona krok tworzenia środowiska.</span><span class="sxs-lookup"><span data-stu-id="0e4f0-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="0e4f0-109">Poniżej przedstawiono plany usługowe Microsoft Dynamics, które zapewniają te prawa.</span><span class="sxs-lookup"><span data-stu-id="0e4f0-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="0e4f0-110">Ogólna jednostka magazynowa produktu (SKU)</span><span class="sxs-lookup"><span data-stu-id="0e4f0-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="0e4f0-111">Power Apps planu usług P2</span><span class="sxs-lookup"><span data-stu-id="0e4f0-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="0e4f0-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="0e4f0-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="0e4f0-113">Power Apps dla usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0e4f0-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="0e4f0-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="0e4f0-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="0e4f0-115">Power Apps dla usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0e4f0-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="0e4f0-116">Należy zwrócić uwagę, że różne wersje SKU pakietu Microsoft Office także zapewniają to prawo, wraz z autonomicznymi jednostkami SKU Power Apps Plan 2</span><span class="sxs-lookup"><span data-stu-id="0e4f0-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="0e4f0-117">Istotne jest to, że jedna z tych jednostek SKU musi występować.</span><span class="sxs-lookup"><span data-stu-id="0e4f0-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="0e4f0-118">Przejdź do [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="0e4f0-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="0e4f0-119">Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Human Resouces](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="0e4f0-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
