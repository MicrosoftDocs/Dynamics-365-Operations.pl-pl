---
title: Konfigurowanie i realizowanie zadań księgowania zestawień
description: Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego w celu księgowania zestawień dla wybranego sklepu lub grupy sklepów.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a24014f7e1b925e0fdb20b91bcc9594feb8f4c5c
ms.sourcegitcommit: fc40279d0e56f8a43c601bca6265fdde4c8c4c7e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2019
ms.locfileid: "1792255"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="56df3-103">Konfigurowanie i realizowanie zadań księgowania zestawień</span><span class="sxs-lookup"><span data-stu-id="56df3-103">Configure and run job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="56df3-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznego zadania wsadowego w celu księgowania zestawień dla wybranego sklepu lub grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="56df3-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="56df3-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="56df3-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="56df3-106">Wybierz kolejno opcje Wszystkie obszary robocze > ..</span><span class="sxs-lookup"><span data-stu-id="56df3-106">Go to All workspaces > ..</span></span> <span data-ttu-id="56df3-107">> Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="56df3-107">> Retail store financials.</span></span>
2. <span data-ttu-id="56df3-108">Kliknij Zaksięguj zestawienia w partii.</span><span class="sxs-lookup"><span data-stu-id="56df3-108">Click Post statements in batch.</span></span>
    * <span data-ttu-id="56df3-109">Wybierz hierarchię organizacyjną, a następnie w drzewie węzłów organizacji zaznacz jeden sklep lub węzeł.</span><span class="sxs-lookup"><span data-stu-id="56df3-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="56df3-110">Wybierz węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="56df3-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="56df3-111">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="56df3-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="56df3-112">Kliknij kartę Uruchom w tle. ![Uruchom w tle](../dev-itpro/media/runbackground.png "Uruchom w tle")</span><span class="sxs-lookup"><span data-stu-id="56df3-112">Click the Run in the background tab. ![Run in the background](../dev-itpro/media/runbackground.png "Run in the background")</span></span> 
4. <span data-ttu-id="56df3-113">Zaznacz pole wyboru Przetwarzanie wsadowe lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="56df3-113">Check or uncheck the Batch processing checkbox.</span></span>
<span data-ttu-id="56df3-114">![Przetwarzanie wsadowe](../dev-itpro/media/batchprocessing.png "Przetwarzanie wsadowe i cykl")</span><span class="sxs-lookup"><span data-stu-id="56df3-114">![Batch Processing](../dev-itpro/media/batchprocessing.png "Batch Processing & Recurrance")</span></span> 
5. <span data-ttu-id="56df3-115">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="56df3-115">Click Recurrence.</span></span>
6. <span data-ttu-id="56df3-116">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="56df3-116">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="56df3-117">W polu Godzina rozpoczęcia wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="56df3-117">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="56df3-118">Wybierz, czy chcesz zakończyć cykl po określonej liczbie sesji, w określonym dniu czy nigdy.</span><span class="sxs-lookup"><span data-stu-id="56df3-118">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="56df3-119">Następnie wybierz różne opcje, aby określić, jak często zadanie ma być wykonywane.</span><span class="sxs-lookup"><span data-stu-id="56df3-119">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="56df3-120">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="56df3-120">Click OK.</span></span>
9. <span data-ttu-id="56df3-121">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="56df3-121">Click OK.</span></span>

