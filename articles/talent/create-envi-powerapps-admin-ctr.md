---
title: Nie można utworzyć środowiska w centrum administracyjnym usługi PowerApps
description: W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft PowerApps.
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
ms.openlocfilehash: 97d44dc034cb8097fc0ecf9ac4e485425f097102
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/19/2019
ms.locfileid: "857253"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a><span data-ttu-id="c20b6-103">Nie można utworzyć środowiska w centrum administracyjnym usługi PowerApps</span><span class="sxs-lookup"><span data-stu-id="c20b6-103">Can't create an environment in the PowerApps Admin center</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c20b6-104">**Wydaj**</span><span class="sxs-lookup"><span data-stu-id="c20b6-104">**Issue**</span></span>

- <span data-ttu-id="c20b6-105">Administrator dzierżawy/środowiska nie może utworzyć środowiska w Centrum administracyjnym Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="c20b6-105">The tenant/environment admin can't create an environment in the Microsoft PowerApps Admin center.</span></span>
- <span data-ttu-id="c20b6-106">Licencja, która daje użytkownikom prawo do wykonywania kroku tworzenia środowiska nie została przypisana bezpośrednio do użytkownika, który wykonuje ten krok.</span><span class="sxs-lookup"><span data-stu-id="c20b6-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="c20b6-107">**Rozwiązanie**</span><span class="sxs-lookup"><span data-stu-id="c20b6-107">**Solution**</span></span>

<span data-ttu-id="c20b6-108">Upewnij się, że administrator dzierżawy ma przypisaną prawidłową licencję usługi PowerApps P2 bezpośrednio do użytkownika, który wykona krok tworzenia środowiska.</span><span class="sxs-lookup"><span data-stu-id="c20b6-108">Make sure that the tenant admin has assigned a valid PowerApps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="c20b6-109">Poniżej przedstawiono plany usługowe Microsoft Dynamics, które zapewniają te prawa.</span><span class="sxs-lookup"><span data-stu-id="c20b6-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="c20b6-110">Ogólna jednostka magazynowa produktu (SKU)</span><span class="sxs-lookup"><span data-stu-id="c20b6-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="c20b6-111">Plan usług PowerApps P2</span><span class="sxs-lookup"><span data-stu-id="c20b6-111">PowerApps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="c20b6-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="c20b6-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="c20b6-113">PowerApps dla Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c20b6-113">PowerApps for Dynamics 365</span></span> |
| <span data-ttu-id="c20b6-114">Microsoft Dynamics 365 Plan Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c20b6-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="c20b6-115">PowerApps dla Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c20b6-115">PowerApps for Dynamics 365</span></span> |

<span data-ttu-id="c20b6-116">Należy zwrócić uwagę, że różne wersje SKU pakietu Microsoft Office także zapewniają to prawo, wraz z autonomicznymi jednostkami SKU PowerApps Plan 2</span><span class="sxs-lookup"><span data-stu-id="c20b6-116">Note that various Microsoft Office SKUs also provide the right, together with standalone PowerApps Plan 2 SKUs.</span></span> <span data-ttu-id="c20b6-117">Istotne jest to, że jedna z tych jednostek SKU musi występować.</span><span class="sxs-lookup"><span data-stu-id="c20b6-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="c20b6-118">Przejdź do [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="c20b6-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="c20b6-119">Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="c20b6-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
