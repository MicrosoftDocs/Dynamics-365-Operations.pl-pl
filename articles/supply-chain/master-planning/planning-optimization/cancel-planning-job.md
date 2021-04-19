---
title: Anuluj planowanie pracy
description: W tym temacie wyjaśniono, jak usunąć aktywne planowanie pracy, gdy używana jest funkcja optymalizacji planowania.
author: ChristianRytt
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: e9cf4902251c3c2b93af12a8ad9bd571930ef769
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833336"
---
# <a name="cancel-a-planning-job"></a><span data-ttu-id="66290-103">Anulowanie zadania planowania</span><span class="sxs-lookup"><span data-stu-id="66290-103">Cancel a planning job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="66290-104">W Microsoft Dynamics 365 Supply Chain Management, można usunąć aktywne planowanie pracy, gdy używana jest funkcja optymalizacji planowania.</span><span class="sxs-lookup"><span data-stu-id="66290-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning optimization functionality.</span></span> <span data-ttu-id="66290-105">Po wybraniu opcji **Anuluj** w oknie dialogowym, gdy zadanie optymalizacji planowania zostanie wyzwolone bezpośrednio z interfejsu użytkownika (a nie w tle), zadanie optymalizacji planowania nie zostanie anulowane.</span><span class="sxs-lookup"><span data-stu-id="66290-105">When you select **Cancel** in the dialog box when a Planning optimization job is triggered directly from the user interface (not in the background), this will not cancel the Planning optimization job.</span></span> <span data-ttu-id="66290-106">Nawet w przypadku otrzymania ostrzeżenia, na przykład „Operacja anulowana”, trzeba wykonać następujące kroki, aby anulować zadanie planowania z optymalizacją planowania.</span><span class="sxs-lookup"><span data-stu-id="66290-106">Even if you receive a warning such as “Operation canceled”, you will still need to use the following steps to cancel a planning job with Planning optimization.</span></span>


<span data-ttu-id="66290-107">Aby anulować aktywne zadanie planowania, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="66290-107">To cancel an active planning job, follow these steps.</span></span> 

> [!NOTE]
> <span data-ttu-id="66290-108">Tylko aktywna praca może być usunięta.</span><span class="sxs-lookup"><span data-stu-id="66290-108">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="66290-109">Przejdź do **Planowanie główne \> Ustawień \> Plany**.</span><span class="sxs-lookup"><span data-stu-id="66290-109">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="66290-110">Umożliwia wybór odpowiedniego planu dla przebiegu planowania.</span><span class="sxs-lookup"><span data-stu-id="66290-110">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="66290-111">Wybierz **Historia**.</span><span class="sxs-lookup"><span data-stu-id="66290-111">Select **History**.</span></span>
4. <span data-ttu-id="66290-112">Wybierz planowaną pracę do anulowania.</span><span class="sxs-lookup"><span data-stu-id="66290-112">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="66290-113">Wybierz **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="66290-113">Select **Cancel**.</span></span>

<span data-ttu-id="66290-114">Stan zadania będzie **anulowany** do momentu potwierdzenia przez usługę optymalizacji planowania, że zadanie zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="66290-114">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="66290-115">Status zostanie wówczas zaktualizowany do stanu **Anulowane**.</span><span class="sxs-lookup"><span data-stu-id="66290-115">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="66290-116">Aby wyświetlić zmiany stanu, należy odświeżyć stronę, wybierając przycisk **Odśwież**.</span><span class="sxs-lookup"><span data-stu-id="66290-116">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="66290-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="66290-117">Additional resources</span></span>

[<span data-ttu-id="66290-118">Omówienie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="66290-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="66290-119">Rozpoczęcie optymalizacji planowania</span><span class="sxs-lookup"><span data-stu-id="66290-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="66290-120">Analiza dopasowywania optymalizacją planowania</span><span class="sxs-lookup"><span data-stu-id="66290-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="66290-121">Wyświetlanie dzienników historii i planowania planów</span><span class="sxs-lookup"><span data-stu-id="66290-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="66290-122">Stosowanie filtrów do planu</span><span class="sxs-lookup"><span data-stu-id="66290-122">Apply filters to a plan</span></span>](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]