---
title: Prawa dostępu dla kontrolerów obiektów kosztów
description: Ten temat zawiera informacje o uprawnieniach dostępu kontrolerów obiektu kosztów.
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 68fc97ed27460ac0a2bee9c10cb9bda67d506e78
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978896"
---
# <a name="access-rights-for-cost-object-controllers"></a><span data-ttu-id="25903-103">Prawa dostępu dla kontrolerów obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-103">Access rights for cost object controllers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25903-104">Obszar roboczy **Kontrola kosztów** jest centralnym miejscem, w którym menedżerowie mogą wyświetlać działanie podlegających im obiektów ich kosztów.</span><span class="sxs-lookup"><span data-stu-id="25903-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="25903-105">Ten obszar roboczy umożliwia menedżerom wykorzystywanie danych z modułu Rachunek kosztów, mimo iż sami nie są księgowymi kosztów.</span><span class="sxs-lookup"><span data-stu-id="25903-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="25903-106">Ze względów bezpieczeństwa menedżerowie powinni móc wyświetlać tylko dane rachunku kosztów powiązane z konkretnymi obiektami kosztów, za które odpowiadają.</span><span class="sxs-lookup"><span data-stu-id="25903-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="25903-107">Istnieją cztery unikatowe role w module Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="25903-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="25903-108">Nazwa roli</span><span class="sxs-lookup"><span data-stu-id="25903-108">Role name</span></span>               | <span data-ttu-id="25903-109">Licencja</span><span class="sxs-lookup"><span data-stu-id="25903-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="25903-110">Menedżer rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-110">Cost accounting manager</span></span> | <span data-ttu-id="25903-111">Działanie</span><span class="sxs-lookup"><span data-stu-id="25903-111">Activity</span></span>     |
| <span data-ttu-id="25903-112">Księgowy kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-112">Cost accountant</span></span>         | <span data-ttu-id="25903-113">Operations</span><span class="sxs-lookup"><span data-stu-id="25903-113">Operations</span></span>   |
| <span data-ttu-id="25903-114">Księgowy rachunku kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-114">Cost accountant clerk</span></span>   | <span data-ttu-id="25903-115">Operations</span><span class="sxs-lookup"><span data-stu-id="25903-115">Operations</span></span>   |
| <span data-ttu-id="25903-116">Kontroler obiektów kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-116">Cost object controller</span></span>  | <span data-ttu-id="25903-117">Członkowie zespołu</span><span class="sxs-lookup"><span data-stu-id="25903-117">Team members</span></span> |

<span data-ttu-id="25903-118">W tym temacie wyjaśniono, jak przypisać rolę **Kontroler obiektów kosztów** do menedżera.</span><span class="sxs-lookup"><span data-stu-id="25903-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="25903-119">Gdy rola **Kontroler obiektów kosztów** jest przypisana do menedżera, menedżer może wykonywać następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="25903-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="25903-120">Dostęp do obszaru roboczego **Kontrola kosztów** (na urządzeniu klienckim).</span><span class="sxs-lookup"><span data-stu-id="25903-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="25903-121">Drążenie wskroś i prawo wyświetlania stron obsługujących funkcjonalność drążenia wskroś.</span><span class="sxs-lookup"><span data-stu-id="25903-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="25903-122">Dostęp do obszaru roboczego **Kontrola kosztów** (w aplikacji komórkowej).</span><span class="sxs-lookup"><span data-stu-id="25903-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="25903-123">Rola **Kontroler obiektów kosztów** nie pozwala decydować, do których obiektów kosztów użytkownik ma dostęp i z których może wyświetlać dane.</span><span class="sxs-lookup"><span data-stu-id="25903-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="25903-124">Zabezpieczenia na poziomie wiersza są dostarczane za pośrednictwem hierarchii wymiarów i hierarchii listy dostępu.</span><span class="sxs-lookup"><span data-stu-id="25903-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="25903-125">Przyznawanie praw dostępu</span><span class="sxs-lookup"><span data-stu-id="25903-125">Grant access rights</span></span>
<span data-ttu-id="25903-126">W poniższym przykładzie pokazano, jak może wyglądać hierarchia wymiarów.</span><span class="sxs-lookup"><span data-stu-id="25903-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="25903-127">**Szczegóły hierarchii wymiarów**</span><span class="sxs-lookup"><span data-stu-id="25903-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="25903-128">Nazwa hierarchii wymiarów</span><span class="sxs-lookup"><span data-stu-id="25903-128">Dimension hierarchy name</span></span> | <span data-ttu-id="25903-129">Wymiar</span><span class="sxs-lookup"><span data-stu-id="25903-129">Dimension</span></span>    | <span data-ttu-id="25903-130">Nazwa typu hierarchii wymiarów</span><span class="sxs-lookup"><span data-stu-id="25903-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="25903-131">Hierarchia list dostępu</span><span class="sxs-lookup"><span data-stu-id="25903-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="25903-132">Organizacja</span><span class="sxs-lookup"><span data-stu-id="25903-132">Organization</span></span>             | <span data-ttu-id="25903-133">Centra kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-133">Cost centers</span></span> | <span data-ttu-id="25903-134">Hierarchia klasyfikacji wymiarów</span><span class="sxs-lookup"><span data-stu-id="25903-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="25903-135">**Tak**</span><span class="sxs-lookup"><span data-stu-id="25903-135">**Yes**</span></span>               |

<span data-ttu-id="25903-136">Można użyć skróconej karty **Użytkownicy** w projektancie hierarchii w celu wstawienia jednego lub więcej identyfikatorów użytkowników w każdym węźle.</span><span class="sxs-lookup"><span data-stu-id="25903-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="25903-137">Użytkownicy</span><span class="sxs-lookup"><span data-stu-id="25903-137">Users</span></span>            | <span data-ttu-id="25903-138">Zakresy elementów członkowskich wymiaru</span><span class="sxs-lookup"><span data-stu-id="25903-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="25903-139">**Węzły**</span><span class="sxs-lookup"><span data-stu-id="25903-139">**Nodes**</span></span>                         | <span data-ttu-id="25903-140">**Identyfikator użytkownika**</span><span class="sxs-lookup"><span data-stu-id="25903-140">**User ID**</span></span>      | <span data-ttu-id="25903-141">**Element członkowskiego wymiaru źródłowego**</span><span class="sxs-lookup"><span data-stu-id="25903-141">**From dimension member**</span></span> | <span data-ttu-id="25903-142">**Element członkowski wymiaru docelowego**</span><span class="sxs-lookup"><span data-stu-id="25903-142">**To dimension member**</span></span> |
| <span data-ttu-id="25903-143">Organizacja</span><span class="sxs-lookup"><span data-stu-id="25903-143">Organization</span></span>                      | <span data-ttu-id="25903-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="25903-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="25903-145">&nbsp;&nbsp;Administrator</span><span class="sxs-lookup"><span data-stu-id="25903-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="25903-146">kwiecień</span><span class="sxs-lookup"><span data-stu-id="25903-146">April</span></span>            |                           |                         |
| <span data-ttu-id="25903-147">&nbsp;&nbsp;&nbsp;&nbsp;Finanse</span><span class="sxs-lookup"><span data-stu-id="25903-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="25903-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="25903-148">Alicia</span></span>           | <span data-ttu-id="25903-149">CC002</span><span class="sxs-lookup"><span data-stu-id="25903-149">CC002</span></span>                     | <span data-ttu-id="25903-150">CC003</span><span class="sxs-lookup"><span data-stu-id="25903-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="25903-151">CC007</span><span class="sxs-lookup"><span data-stu-id="25903-151">CC007</span></span>                     | <span data-ttu-id="25903-152">CC007</span><span class="sxs-lookup"><span data-stu-id="25903-152">CC007</span></span>                   |
| <span data-ttu-id="25903-153">&nbsp;&nbsp;&nbsp;&nbsp;Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="25903-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="25903-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="25903-154">Arnie</span></span>            | <span data-ttu-id="25903-155">CC001</span><span class="sxs-lookup"><span data-stu-id="25903-155">CC001</span></span>                     | <span data-ttu-id="25903-156">CC001</span><span class="sxs-lookup"><span data-stu-id="25903-156">CC001</span></span>                   |
| <span data-ttu-id="25903-157">&nbsp;&nbsp;Produkcja</span><span class="sxs-lookup"><span data-stu-id="25903-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="25903-158">David</span><span class="sxs-lookup"><span data-stu-id="25903-158">David</span></span>            |                           |                         |
| <span data-ttu-id="25903-159">&nbsp;&nbsp;&nbsp;&nbsp;Opakowanie</span><span class="sxs-lookup"><span data-stu-id="25903-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="25903-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="25903-160">Ellen</span></span>            | <span data-ttu-id="25903-161">CC005</span><span class="sxs-lookup"><span data-stu-id="25903-161">CC005</span></span>                     | <span data-ttu-id="25903-162">CC005</span><span class="sxs-lookup"><span data-stu-id="25903-162">CC005</span></span>                   |
| <span data-ttu-id="25903-163">&nbsp;&nbsp;&nbsp;&nbsp;Zestaw</span><span class="sxs-lookup"><span data-stu-id="25903-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="25903-164">Chris</span><span class="sxs-lookup"><span data-stu-id="25903-164">Chris</span></span>            | <span data-ttu-id="25903-165">CC006</span><span class="sxs-lookup"><span data-stu-id="25903-165">CC006</span></span>                     | <span data-ttu-id="25903-166">CC006</span><span class="sxs-lookup"><span data-stu-id="25903-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="25903-167">Księgowi kosztów powinni być przypisani do najwyższego poziomu hierarchii, tak aby widzieli wszystkie wpisy w module Rachunek kosztów.</span><span class="sxs-lookup"><span data-stu-id="25903-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="25903-168">Aby można było zastosować hierarchię list dostępu i jej ustawienia zabezpieczeń, na karcie **Ogólne** na stronie **Parametrów rachunku kosztów** (**Rachunek kosztów** > **Ustawienia** > **Parametry**) w opcji **Włącz dostęp z prawem do wyświetlania elementów członkowskich wymiaru obiektu kosztów** musi być zaznaczona wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="25903-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="25903-169">Ustawienia hierarchii list dostępu umożliwiają kontrolowanie danych, które są wyświetlane w następujących obszarach:</span><span class="sxs-lookup"><span data-stu-id="25903-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="25903-170">Obszar roboczy **Kontrola kosztów** (na urządzeniu klienckim):</span><span class="sxs-lookup"><span data-stu-id="25903-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="25903-171">Dane na stronach używanych do drążenia wskroś</span><span class="sxs-lookup"><span data-stu-id="25903-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="25903-172">Obszar roboczy **Kontrola kosztów** (w aplikacji komórkowej):</span><span class="sxs-lookup"><span data-stu-id="25903-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="25903-173">Salda na kartach</span><span class="sxs-lookup"><span data-stu-id="25903-173">Balances in cards</span></span>

- <span data-ttu-id="25903-174">Microsoft Power BI:</span><span class="sxs-lookup"><span data-stu-id="25903-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="25903-175">Dane wyświetlane w wizualizacjach programu Power BI</span><span class="sxs-lookup"><span data-stu-id="25903-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="25903-176">Wizualizacje danych w rozwiązaniu Power BI osadzone w Dynamics 365 Finance, wersja kliencka</span><span class="sxs-lookup"><span data-stu-id="25903-176">Data Power BI visualizations that are embedded in the Dynamics 365 Finance client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="25903-177">Aby hierarchia list dostępu mogła wpływać na dane w programie Power BI, należy w tym programie sparować hierarchię list dostępu i zabezpieczenia na poziomie wiersza w programie Power BI.</span><span class="sxs-lookup"><span data-stu-id="25903-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="25903-178">Aby uzyskać więcej informacji, zobacz [Konfigurowanie zabezpieczeń pakietu zawartości Rachunek kosztów](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="25903-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="25903-179">W tym temacie przedstawiono warunki wstępne, które muszą być spełnione, aby można było używać obszaru roboczego **Kontrola kosztów**.</span><span class="sxs-lookup"><span data-stu-id="25903-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="25903-180">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="25903-180">Additional resources</span></span>

- [<span data-ttu-id="25903-181">Obszar roboczy Kontrola kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="25903-182">Hierarchia wymiarów</span><span class="sxs-lookup"><span data-stu-id="25903-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="25903-183">Konfigurowanie zabezpieczeń pakietu zawartości Rachunek kosztów</span><span class="sxs-lookup"><span data-stu-id="25903-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)
