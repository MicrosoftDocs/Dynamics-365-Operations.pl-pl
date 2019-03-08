---
title: Zmienianie reguł Kanban dla zadań procesu
description: Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 38d9ff0a7d6aeb0a589fd6b9ab34b818c46644cc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "314953"
---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="fba23-103">Zmienianie reguł Kanban dla zadań procesu</span><span class="sxs-lookup"><span data-stu-id="fba23-103">Change kanban rules for a process job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fba23-104">Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="fba23-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="fba23-105">Jest to przydatne do wyrównywania obciążenia zasobów lub w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="fba23-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="fba23-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="fba23-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fba23-107">Procedura jest przeznaczona dla planisty w firmie stosującej zasady produkcji oszczędnej odpowiedzialnego za strumień wartości.</span><span class="sxs-lookup"><span data-stu-id="fba23-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="fba23-108">Kopiowanie reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="fba23-108">Copy kanban rule</span></span>
1. <span data-ttu-id="fba23-109">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="fba23-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="fba23-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="fba23-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fba23-111">Wybierz regułę Kanban zdarzeń 000022 dla produktu L0001.</span><span class="sxs-lookup"><span data-stu-id="fba23-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="fba23-112">Kliknij opcję Duplikuj regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="fba23-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="fba23-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="fba23-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="fba23-114">Modyfikacja reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="fba23-114">Change kanban rule</span></span>
1. <span data-ttu-id="fba23-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="fba23-115">Close the page.</span></span>
2. <span data-ttu-id="fba23-116">Przejdź do okna Planowanie zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="fba23-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="fba23-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="fba23-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="fba23-118">Wybierz wiersz z kartą Kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="fba23-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="fba23-119">Kliknij opcję Użyj alternatywnej reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="fba23-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="fba23-120">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="fba23-120">Click Next.</span></span>
6. <span data-ttu-id="fba23-121">W polu Reguła Kanban wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fba23-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="fba23-122">Wybierz utworzoną wcześniej regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="fba23-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="fba23-123">Jest to reguła Kanban o najwyższym numerze.</span><span class="sxs-lookup"><span data-stu-id="fba23-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="fba23-124">Kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="fba23-124">Click Finish.</span></span>
    * <span data-ttu-id="fba23-125">Teraz zadanie w systemie Kanban używa innej reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="fba23-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="fba23-126">Może to być przydatne do wyrównywania obciążenia komórek roboczych.</span><span class="sxs-lookup"><span data-stu-id="fba23-126">This can be useful to level load work cells.</span></span>  

