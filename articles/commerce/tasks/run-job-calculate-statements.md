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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 973236acca0cb8c0d57171e4bb9d4daaa7faaf38
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141207"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="627f3-103">Konfigurowanie i realizowanie zadań obliczania zestawień</span><span class="sxs-lookup"><span data-stu-id="627f3-103">Configure and run job to calculate statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="627f3-104">Ta procedura zawiera instruktaż konfigurowania i wykonywania cyklicznych zadań wsadowych w celu utworzenia i obliczenia zestawień dla wybranego sklepu lub grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="627f3-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="627f3-105">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="627f3-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="627f3-106">Wybierz kolejno opcje Wszystkie obszary robocze > Finanse sklepu.</span><span class="sxs-lookup"><span data-stu-id="627f3-106">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="627f3-107">Kliknij opcję Oblicz zestawienia.</span><span class="sxs-lookup"><span data-stu-id="627f3-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="627f3-108">Wybierz określony sklep albo węzeł, jeśli chcesz utworzyć zadanie wsadowe dla grupy sklepów.</span><span class="sxs-lookup"><span data-stu-id="627f3-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="627f3-109">Kliknij strzałkę, aby dodać zaznaczone obiekty.</span><span class="sxs-lookup"><span data-stu-id="627f3-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="627f3-110">Kliknij kartę Uruchom w tle.</span><span class="sxs-lookup"><span data-stu-id="627f3-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="627f3-111">W polu Przetwarzanie wsadowe wybierz opcję „Tak”.</span><span class="sxs-lookup"><span data-stu-id="627f3-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="627f3-112">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="627f3-112">Click Recurrence.</span></span>
6. <span data-ttu-id="627f3-113">W polu Data początkowa wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="627f3-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="627f3-114">W polu Godzina rozpoczęcia wprowadź godzinę.</span><span class="sxs-lookup"><span data-stu-id="627f3-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="627f3-115">Wybierz opcję Brak daty zakończenia.</span><span class="sxs-lookup"><span data-stu-id="627f3-115">Select the No end date option.</span></span>
9. <span data-ttu-id="627f3-116">W polu PatternUnit wpisz „Dni”.</span><span class="sxs-lookup"><span data-stu-id="627f3-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="627f3-117">W polu Na wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="627f3-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="627f3-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="627f3-118">Click OK.</span></span>
12. <span data-ttu-id="627f3-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="627f3-119">Click OK.</span></span>

