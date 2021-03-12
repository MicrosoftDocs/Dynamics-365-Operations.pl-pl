---
title: Usuwanie zadania systemu Kanban z harmonogramu
description: Ta procedura skupia się na usunięciu zaplanowanego zadania przetwarzania w systemie Kanban z harmonogramu poprzez przywrócenie stanu zadania do Niezaplanowane.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcd9247e24323ba606377d7e51bd4447ab51c905
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961622"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="0a0c2-103">Usuwanie zadania systemu Kanban z harmonogramu</span><span class="sxs-lookup"><span data-stu-id="0a0c2-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0a0c2-104">Ta procedura skupia się na usunięciu zaplanowanego zadania przetwarzania w systemie Kanban z harmonogramu poprzez przywrócenie stanu zadania do Niezaplanowane.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="0a0c2-105">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0a0c2-106">Procedura jest przeznaczona dla kierownika zakładu produkcyjnego lub planisty produkcji.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="0a0c2-107">Znajdowanie zaplanowanego zadania w systemie Kanban</span><span class="sxs-lookup"><span data-stu-id="0a0c2-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="0a0c2-108">Wybierz kolejno opcje Kontrola produkcji > Kanban > Planowanie zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="0a0c2-109">W polu Komórka robocza kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="0a0c2-110">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0a0c2-111">Zaznacz komórkę roboczą 1250.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="0a0c2-112">Kliknij opcję Wybierz.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-112">Click Select.</span></span>
5. <span data-ttu-id="0a0c2-113">W polu Wyświetl stan zadania zaznacz opcję „Zaplanowane”.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="0a0c2-114">Usuwanie zaplanowanego zadania systemu Kanban z harmonogramu</span><span class="sxs-lookup"><span data-stu-id="0a0c2-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="0a0c2-115">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0a0c2-116">Wybierz zadanie, które ma stan Zaplanowane, na przykład zadanie z 19 grudnia 2012 roku.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="0a0c2-117">W okienku akcji kliknij opcję Plan.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="0a0c2-118">Kliknij opcję Przywróć stan zadania.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-118">Click Revert job status.</span></span>
4. <span data-ttu-id="0a0c2-119">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-119">Click OK.</span></span>
    * <span data-ttu-id="0a0c2-120">Spowoduje to przywrócenie bieżącego stanu zadania z „Zaplanowane” na „Niezaplanowane” i usunięcie go z tablicy procesów.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   

