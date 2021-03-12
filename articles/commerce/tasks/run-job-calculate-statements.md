---
title: Konfigurowanie i realizowanie zadań obliczania zestawień
description: Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznych zadań wsadowych w celu utworzenia i obliczenia zestawień dla wybranego sklepu lub grupy sklepów.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 402ddf9a2646b2db0346e01504e8188120f16ae5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982220"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="9d3c8-103">Konfigurowanie i realizowanie zadań obliczania zestawień</span><span class="sxs-lookup"><span data-stu-id="9d3c8-103">Configure and run job to calculate statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d3c8-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznych zadań wsadowych w celu utworzenia i obliczenia zestawień dla wybranego sklepu lub grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="9d3c8-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="9d3c8-106">Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-106">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="9d3c8-107">Kliknij opcję Oblicz zestawienia.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="9d3c8-108">Wybierz określony sklep albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="9d3c8-109">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="9d3c8-110">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="9d3c8-111">W polu Przetwarzanie wsadowe wybierz opcję „Tak”.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="9d3c8-112">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-112">Click Recurrence.</span></span>
6. <span data-ttu-id="9d3c8-113">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="9d3c8-114">W polu Godzina rozpoczęcia wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="9d3c8-115">Wybierz opcję Brak daty zakończenia.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-115">Select the No end date option.</span></span>
9. <span data-ttu-id="9d3c8-116">W polu PatternUnit wpisz „Dni”.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="9d3c8-117">W polu Na wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="9d3c8-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-118">Click OK.</span></span>
12. <span data-ttu-id="9d3c8-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="9d3c8-119">Click OK.</span></span>

