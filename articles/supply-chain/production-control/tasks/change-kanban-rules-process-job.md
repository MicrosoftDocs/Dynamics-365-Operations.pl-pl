---
title: Zmienianie reguł Kanban dla zadań procesu
description: Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e0e1989bcc4ca02d097f9ebff40f21158f26546
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981363"
---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="12184-103">Zmienianie reguł Kanban dla zadań procesu</span><span class="sxs-lookup"><span data-stu-id="12184-103">Change kanban rules for a process job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12184-104">Ta procedura skupia się na zmianie używanej reguły kanban dla danej karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="12184-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="12184-105">Jest to przydatne do wyrównywania obciążenia zasobów lub w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="12184-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="12184-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="12184-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="12184-107">Procedura jest przeznaczona dla planisty w firmie stosującej zasady produkcji oszczędnej odpowiedzialnego za strumień wartości.</span><span class="sxs-lookup"><span data-stu-id="12184-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="12184-108">Kopiowanie reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="12184-108">Copy kanban rule</span></span>
1. <span data-ttu-id="12184-109">Przejdź do okna Reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="12184-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="12184-110">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="12184-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="12184-111">Wybierz regułę Kanban zdarzeń 000022 dla produktu L0001.</span><span class="sxs-lookup"><span data-stu-id="12184-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="12184-112">Kliknij opcję Duplikuj regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="12184-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="12184-113">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="12184-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="12184-114">Modyfikacja reguły Kanban</span><span class="sxs-lookup"><span data-stu-id="12184-114">Change kanban rule</span></span>
1. <span data-ttu-id="12184-115">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="12184-115">Close the page.</span></span>
2. <span data-ttu-id="12184-116">Przejdź do okna Planowanie zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="12184-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="12184-117">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="12184-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="12184-118">Wybierz wiersz z kartą Kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="12184-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="12184-119">Kliknij opcję Użyj alternatywnej reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="12184-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="12184-120">Kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="12184-120">Click Next.</span></span>
6. <span data-ttu-id="12184-121">W polu Reguła Kanban wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="12184-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="12184-122">Wybierz utworzoną wcześniej regułę Kanban.</span><span class="sxs-lookup"><span data-stu-id="12184-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="12184-123">Jest to reguła Kanban o najwyższym numerze.</span><span class="sxs-lookup"><span data-stu-id="12184-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="12184-124">Kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="12184-124">Click Finish.</span></span>
    * <span data-ttu-id="12184-125">Teraz zadanie w systemie Kanban używa innej reguły Kanban.</span><span class="sxs-lookup"><span data-stu-id="12184-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="12184-126">Może to być przydatne do wyrównywania obciążenia komórek roboczych.</span><span class="sxs-lookup"><span data-stu-id="12184-126">This can be useful to level load work cells.</span></span>  

