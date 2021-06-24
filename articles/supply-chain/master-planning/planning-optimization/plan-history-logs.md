---
title: Wyświetlanie dzienników historii i planowania planów
description: W tym temacie opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187254"
---
# <a name="view-plan-history-and-planning-logs"></a><span data-ttu-id="8ad52-103">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="8ad52-103">View plan history and planning logs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8ad52-104">W tym temacie opisano sposób wyświetlania historii zadań planowania wyzwalanych przez funkcję optymalizacji planowania w Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8ad52-104">This topic explains how to view the history of planning jobs that are triggered by the Planning Optimization functionality in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="8ad52-105">Aby wyświetlić historię planu, należy otworzyć plan, przechodząc do **Planowanie główne** \> **Ustawienia** \> **Plany** \> **Plany główne** i wybierając opcję **historia**.</span><span class="sxs-lookup"><span data-stu-id="8ad52-105">To view the history for a plan, open the plan by going to **Master planning** \> **Setup** \> **Plans** \> **Master plans** and selecting **History**.</span></span> <span data-ttu-id="8ad52-106">Historia zawiera listę wszystkich zadań wybranego planu.</span><span class="sxs-lookup"><span data-stu-id="8ad52-106">The history lists all the jobs for the selected plan.</span></span> <span data-ttu-id="8ad52-107">Lista zawiera zakończone i aktywne zadania.</span><span class="sxs-lookup"><span data-stu-id="8ad52-107">The list includes completed and active jobs.</span></span>

<span data-ttu-id="8ad52-108">Historia zadań dla przebiegów planowania nadrzędnego Optymalizacja planowania zachowuje tylko do 60 rekordów dla każdego planu nadrzędnego.</span><span class="sxs-lookup"><span data-stu-id="8ad52-108">The history of jobs for Planning Optimization master planning runs keeps only up to 60 records per master plan.</span></span> <span data-ttu-id="8ad52-109">Przy każdym uruchomieniu nowego obliczenia planu głównego usuwany jest najwcześniejszy zapis historii tego planu.</span><span class="sxs-lookup"><span data-stu-id="8ad52-109">Whenever you run a new master planning calculation, that plan's earliest history record is deleted.</span></span>

<span data-ttu-id="8ad52-110">Oprócz wyświetlania czasu rozpoczęcia i stanu zadań można wyświetlać dziennik dla określonego zadania.</span><span class="sxs-lookup"><span data-stu-id="8ad52-110">In addition to seeing the start time and status of jobs, you can view the log for a specific job.</span></span> <span data-ttu-id="8ad52-111">Dziennik zawiera dodatkowe informacje i ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="8ad52-111">The log includes additional information and warnings.</span></span> <span data-ttu-id="8ad52-112">Nie wszystkie zadania mają dziennik.</span><span class="sxs-lookup"><span data-stu-id="8ad52-112">Not all jobs have a log.</span></span> <span data-ttu-id="8ad52-113">Aby wyświetlić dziennik zadania, wybierz opcję **dziennik**.</span><span class="sxs-lookup"><span data-stu-id="8ad52-113">To view the log for a job, select **Log**.</span></span> <span data-ttu-id="8ad52-114">Wpisy w dzienniku są przechowywane tylko przez 30 dni od daty zakończenia zadania, po tym czasie są automatycznie usuwane.</span><span class="sxs-lookup"><span data-stu-id="8ad52-114">Log entries are only stored for 30 days after the date the job finished, after that they are automatically deleted.</span></span>

## <a name="related-resources"></a><span data-ttu-id="8ad52-115">Powiązane zasoby</span><span class="sxs-lookup"><span data-stu-id="8ad52-115">Related resources</span></span>

- [<span data-ttu-id="8ad52-116">Omówienie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="8ad52-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)
- [<span data-ttu-id="8ad52-117">Rozpoczęcie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="8ad52-117">Get started with Planning Optimization</span></span>](get-started.md)
- [<span data-ttu-id="8ad52-118">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="8ad52-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
- [<span data-ttu-id="8ad52-119">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="8ad52-119">Apply filters to a plan</span></span>](plan-filters.md)
- [<span data-ttu-id="8ad52-120">Anuluj planowanie pracy</span><span class="sxs-lookup"><span data-stu-id="8ad52-120">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]