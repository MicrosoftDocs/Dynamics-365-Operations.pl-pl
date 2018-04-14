--- 
title: "Konfigurowanie i realizowanie zadań księgowania zestawień"
description: "Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego w celu księgowania zestawień dla wybranego sklepu lub grupy sklepów."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 564f628ff082887a0f6476ded76c13d2824abf08
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="configure-and-run-a-job-to-post-statements"></a><span data-ttu-id="8821f-103">Konfigurowanie i realizowanie zadań księgowania zestawień</span><span class="sxs-lookup"><span data-stu-id="8821f-103">Configure and run a job to post statements</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="8821f-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego w celu księgowania zestawień dla wybranego sklepu lub grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="8821f-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="8821f-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="8821f-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="8821f-106">Wybierz kolejno opcje Wszystkie obszary robocze > ..</span><span class="sxs-lookup"><span data-stu-id="8821f-106">Go to All workspaces > ..</span></span> <span data-ttu-id="8821f-107">> Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="8821f-107">> Retail store financials.</span></span>
2. <span data-ttu-id="8821f-108">Kliknij opcję Księgowanie zestawień.</span><span class="sxs-lookup"><span data-stu-id="8821f-108">Click Post statements.</span></span>
    * <span data-ttu-id="8821f-109">Wybierz hierarchię organizacyjną, a następnie w drzewie węzłów organizacji zaznacz jeden sklep lub węzeł.</span><span class="sxs-lookup"><span data-stu-id="8821f-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="8821f-110">Wybierz węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="8821f-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="8821f-111">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="8821f-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="8821f-112">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="8821f-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="8821f-113">Zaznacz pole wyboru Przetwarzanie wsadowe lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="8821f-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="8821f-114">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="8821f-114">Click Recurrence.</span></span>
6. <span data-ttu-id="8821f-115">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="8821f-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="8821f-116">W polu Godzina rozpoczęcia wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="8821f-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="8821f-117">Wybierz, czy chcesz zakończyć cykl po określonej liczbie sesji, w określonym dniu czy nigdy.</span><span class="sxs-lookup"><span data-stu-id="8821f-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="8821f-118">Następnie wybierz różne opcje, aby określić, jak często zadanie ma być wykonywane.</span><span class="sxs-lookup"><span data-stu-id="8821f-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="8821f-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8821f-119">Click OK.</span></span>
9. <span data-ttu-id="8821f-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="8821f-120">Click OK.</span></span>


