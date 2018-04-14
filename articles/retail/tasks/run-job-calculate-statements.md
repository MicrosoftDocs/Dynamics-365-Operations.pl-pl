--- 
title: "Konfigurowanie i realizowanie zadań obliczania zestawień"
description: "Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznych zadań wsadowych w celu utworzenia i obliczenia zestawień dla wybranego sklepu lub grupy sklepów."
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
ms.openlocfilehash: 6d98adc919d50957b92a879b69517e0a826ea45f
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="configure-and-run-a-job-to-calculate-statements"></a><span data-ttu-id="aac19-103">Konfigurowanie i realizowanie zadań obliczania zestawień</span><span class="sxs-lookup"><span data-stu-id="aac19-103">Configure and run a job to calculate statements</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="aac19-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznych zadań wsadowych w celu utworzenia i obliczenia zestawień dla wybranego sklepu lub grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="aac19-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="aac19-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="aac19-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="aac19-106">Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu sieciowego.</span><span class="sxs-lookup"><span data-stu-id="aac19-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="aac19-107">Kliknij opcję Oblicz zestawienia.</span><span class="sxs-lookup"><span data-stu-id="aac19-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="aac19-108">Wybierz określony sklep albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="aac19-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="aac19-109">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="aac19-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="aac19-110">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="aac19-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="aac19-111">W polu Przetwarzanie wsadowe wybierz opcję „Tak”.</span><span class="sxs-lookup"><span data-stu-id="aac19-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="aac19-112">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="aac19-112">Click Recurrence.</span></span>
6. <span data-ttu-id="aac19-113">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="aac19-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="aac19-114">W polu Godzina rozpoczęcia wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="aac19-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="aac19-115">Wybierz opcję Brak daty zakończenia.</span><span class="sxs-lookup"><span data-stu-id="aac19-115">Select the No end date option.</span></span>
9. <span data-ttu-id="aac19-116">W polu PatternUnit wpisz „Dni”.</span><span class="sxs-lookup"><span data-stu-id="aac19-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="aac19-117">W polu Na wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="aac19-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="aac19-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="aac19-118">Click OK.</span></span>
12. <span data-ttu-id="aac19-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="aac19-119">Click OK.</span></span>


