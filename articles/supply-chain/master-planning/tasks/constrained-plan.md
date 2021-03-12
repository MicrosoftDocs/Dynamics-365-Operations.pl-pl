---
title: Generowanie planu z ograniczeniami
description: W tym temacie pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i wydajności.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d4af946a8dd4e5311bcb90386c88d5e7f205c4eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999863"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="b4ad6-103">Generowanie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="b4ad6-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b4ad6-104">W tym temacie pokazano, jak utworzyć plan, który bierze pod uwagę ograniczenia dotyczące materiałów i wydajności.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="b4ad6-105">Plan gwarantuje, że produkcja nie rozpocznie się przed zapewnieniem dostępności materiałów i wyeliminowaniem ryzyka nadrezerwacji.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="b4ad6-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b4ad6-107">Ta procedura jest przeznaczona dla planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="b4ad6-108">Konfigurowanie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="b4ad6-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="b4ad6-109">Na stronie głównej wybierz obszar roboczy **planowania głównego**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="b4ad6-110">Wybierz **Plany główne** z listy łączy znajdujących się po prawej stronie obszaru roboczego.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="b4ad6-111">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="b4ad6-112">Przykład: **Plan statyczny**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="b4ad6-113">W polu **Ograniczone zdolności produkcyjne** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="b4ad6-114">W polu **Horyzont czasowy ograniczonych zdolności produkcyjnych** wpisz `30`.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="b4ad6-115">Rozwiń sekcję **Horyzonty czasowe w dniach**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="b4ad6-116">W polu **Zdolności produkcyjne** wybierz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="b4ad6-117">W polu **Horyzont czasowy planowania zdolności produkcyjnych (dni)** wpisz liczbę dni.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="b4ad6-118">Przykład: `60`</span><span class="sxs-lookup"><span data-stu-id="b4ad6-118">Example: `60`</span></span>  
9. <span data-ttu-id="b4ad6-119">W polu **Obliczone opóźnienia** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="b4ad6-120">W polu **Oblicz horyzont czasowy opóźnień (dni)** wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="b4ad6-121">Przykład: `60`</span><span class="sxs-lookup"><span data-stu-id="b4ad6-121">Example: `60`</span></span> 
11. <span data-ttu-id="b4ad6-122">Rozwiń sekcję **Obliczone opóźnienia**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="b4ad6-123">W każdym polu **Dodaj obliczone opóźnienie do daty zapotrzebowania** zaznacz opcję **Tak**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="b4ad6-124">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="b4ad6-125">Tworzenie planu z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="b4ad6-125">Create a constrained plan</span></span>
1. <span data-ttu-id="b4ad6-126">Wybierz opcję **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-126">Select **Run**.</span></span>
2. <span data-ttu-id="b4ad6-127">W polu **Plan główny** wprowadź lub wybierz plan, dla którego skonfigurowano ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="b4ad6-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-128">Select **OK**.</span></span>
4. <span data-ttu-id="b4ad6-129">Wybierz **Zamówienia planowane**.</span><span class="sxs-lookup"><span data-stu-id="b4ad6-129">Select **Planned orders**.</span></span>

