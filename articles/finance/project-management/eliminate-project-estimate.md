---
title: Eliminowanie szacowania projektu
description: Ten temat zawiera informacje dotyczące eliminowania szacowania projektu po jego zakończeniu.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410254"
---
# <a name="eliminate-a-project-estimate"></a><span data-ttu-id="ef8df-103">Eliminowanie szacowania projektu</span><span class="sxs-lookup"><span data-stu-id="ef8df-103">Eliminate a project estimate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ef8df-104">Szacowania projektu zapewniają informacje finansowe dla pracy, która jest szacowana i planowana dla projektu.</span><span class="sxs-lookup"><span data-stu-id="ef8df-104">Project estimates provide the financial view for work that is estimated and scheduled for a project.</span></span> <span data-ttu-id="ef8df-105">Aby wykorzystywać szacowania dla projektu, należy dołączyć projekt do projektu szacunkowego.</span><span class="sxs-lookup"><span data-stu-id="ef8df-105">To work with estimates for a project, you must attach the project to an estimate project.</span></span> <span data-ttu-id="ef8df-106">Projekt szacunkowy jest zawsze oparty na istniejącym projekcie, jednak wiele projektów może odnosić się do jednego projektu szacunkowego.</span><span class="sxs-lookup"><span data-stu-id="ef8df-106">An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project.</span></span> <span data-ttu-id="ef8df-107">Tylko projekty o stałej cenie i inwestycje mogą być dołączone do projektów szacunkowych, a projekty te muszą należeć do tej samej grupy projektów, co projekt szacunkowy.</span><span class="sxs-lookup"><span data-stu-id="ef8df-107">Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.</span></span>

<span data-ttu-id="ef8df-108">Aby wyeliminować projekt szacunkowy, musi on być ukończony.</span><span class="sxs-lookup"><span data-stu-id="ef8df-108">To eliminate an estimate project, it must be complete.</span></span> <span data-ttu-id="ef8df-109">Poniższe kroki wyjaśniają, jak wyeliminować szacowanie.</span><span class="sxs-lookup"><span data-stu-id="ef8df-109">The following steps explain how to eliminate an estimate.</span></span>

1. <span data-ttu-id="ef8df-110">Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** > **Wszystkie projekty** i otworzyć projekt.</span><span class="sxs-lookup"><span data-stu-id="ef8df-110">Go to **Project management and accounting** > **All Projects** and open the project.</span></span> 
2. <span data-ttu-id="ef8df-111">Na karcie **Zarządzanie** wybierz opcję **Szacowanie**, a następnie na stronie **Szacowanie** wybierz pozycję **Eliminacja**.</span><span class="sxs-lookup"><span data-stu-id="ef8df-111">On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.</span></span>
3. <span data-ttu-id="ef8df-112">Na stronie **Eliminuj oszacowania** na karcie **Ogólne** określ następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="ef8df-112">On the **Eliminate estimate** page on the **General** tab, set the following options:</span></span>

   - <span data-ttu-id="ef8df-113">**Kod okresu**: Umożliwia wybór kodu okresu pozwalającego na wybór odpowiednich projektów szacowanych.</span><span class="sxs-lookup"><span data-stu-id="ef8df-113">**Period code**: Select the period code to choose the appropriate estimate projects.</span></span> 
   - <span data-ttu-id="ef8df-114">**Data szacowania**: Umożliwia wybór daty szacowania do usunięcia.</span><span class="sxs-lookup"><span data-stu-id="ef8df-114">**Estimate date**: Select the appropriate estimate date for elimination.</span></span>
   - <span data-ttu-id="ef8df-115">**Eliminuj z ostrzeżeniami PWT**: Włącz tę opcję, aby zapewnić powiadamianie, gdy szacowanie, które jest skojarzone z pracą w toku (PWT) zostanie wyeliminowane.</span><span class="sxs-lookup"><span data-stu-id="ef8df-115">**Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated.</span></span> <span data-ttu-id="ef8df-116">Jeśli ta opcja nie jest włączona, nie można kontynuować eliminacji, jeśli istnieją nieoszacowane transakcje.</span><span class="sxs-lookup"><span data-stu-id="ef8df-116">When this option is not enabled, elimination can’t continue if any non-estimated transactions exist.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="ef8df-117">Ta opcja jest dostępna tylko wtedy, gdy do projektu szacowanego zastosowano eliminację.</span><span class="sxs-lookup"><span data-stu-id="ef8df-117">This option is available only when elimination is applied to an estimate project.</span></span> <span data-ttu-id="ef8df-118">Jest ona niedostępna w przypadku korzystania z księgowania okresowego.</span><span class="sxs-lookup"><span data-stu-id="ef8df-118">It is not available if you are using periodic postings.</span></span> <span data-ttu-id="ef8df-119">To ustawienie działa z ustawieniami na karcie **Szacowanie** na stronie **Parametry projektu** w grupie pól **Zezwalaj na eliminacje, gdy istnieją nieoszacowane transakcje**.</span><span class="sxs-lookup"><span data-stu-id="ef8df-119">This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.</span></span>
   - <span data-ttu-id="ef8df-120">**Określ etap jako zakończony**: Włącz tę opcję, aby po uruchomieniu eliminacji ustawić etap projektu szacunkowego na **Zakończone**.</span><span class="sxs-lookup"><span data-stu-id="ef8df-120">**Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.</span></span>
   - <span data-ttu-id="ef8df-121">**Wydrukuj listę szacunkową**: Umożliwia wybór informacji, które będą uwzględniane podczas drukowania listy szacunkowej.</span><span class="sxs-lookup"><span data-stu-id="ef8df-121">**Print estimate list**: Select the information to be included when the estimate list is printed.</span></span>
   - <span data-ttu-id="ef8df-122">**Wyświetl dziennik informacyjny**: Włącz tę opcję, aby wyświetlić dziennik informacyjny.</span><span class="sxs-lookup"><span data-stu-id="ef8df-122">**Show Infolog**: Enable this option to display the Infolog.</span></span>
   - <span data-ttu-id="ef8df-123">**Data księgowania**: Należy wybrać datę księgowania w księdze.</span><span class="sxs-lookup"><span data-stu-id="ef8df-123">**Posting date**: Choose the ledger posting date of the estimate.</span></span>

4.  <span data-ttu-id="ef8df-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef8df-124">Select **OK**.</span></span>
5. <span data-ttu-id="ef8df-125">Po zakończeniu procesu eliminacji zostanie wyświetlony usunięty projekt szacunkowy z wartością ujemną.</span><span class="sxs-lookup"><span data-stu-id="ef8df-125">After the elimination process is complete, the eliminated estimate project is displayed with a negative value.</span></span> 

<span data-ttu-id="ef8df-126">Jeśli nie zamierzasz wyeliminować oszacowania, możesz wybrać wyeliminowane oszacowanie i wybrać pozycję **Wycofanie eliminacji**.</span><span class="sxs-lookup"><span data-stu-id="ef8df-126">If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.</span></span>   
