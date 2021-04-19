---
title: Anulowanie zadania planowania głównego
description: W tym temacie wyjaśniono, jak anulować aktywne planowanie pracy, gdy używana jest wbudowana funkcja planowania.
author: ChristianRytt
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 513aee3b9475506e28db4bffe90df58567b6b281
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816611"
---
# <a name="cancel-a-master-planning-job"></a><span data-ttu-id="4ac0b-103">Anulowanie zadania planowania głównego</span><span class="sxs-lookup"><span data-stu-id="4ac0b-103">Cancel a master planning job</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ac0b-104">W aplikacji Microsoft Dynamics 365 Supply Chain Management istnieje wiele opcji anulowania zadania planowania głównego.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-104">In Microsoft Dynamics 365 Supply Chain Management, there are multiple options for canceling a master planning job.</span></span> <span data-ttu-id="4ac0b-105">Na przykład można anulować zadanie planowania głównego, jeśli zostało uruchomiony przez pomyłkę lub działa dłużej niż oczekiwano i chcesz je zakończyć.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-105">For example, you may want to cancel a master planning job if it was started by mistake or is running longer than expected and you want to end it.</span></span> <span data-ttu-id="4ac0b-106">Najlepszym sposobem anulowania zadania planowania jest przejście na stronę **niedokończonych procesów planowania**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-106">The best way to cancel a planning job is from  the **Unfinished planning processes** page.</span></span> <span data-ttu-id="4ac0b-107">Alternatywne opcje ze stron **Zadania wsadowe** i **Rozszerzone zadania wsadowe** powinny być używane tylko wtedy, gdy anulowanie zadania planowania głównego na stronie **Nieukończone procesy planowania** nie zostało ukończone w ciągu kilku minut.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-107">Alternative options from the **Batch jobs** and **Batch jobs enhanced** pages should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

## <a name="preferred-cancel-option"></a><span data-ttu-id="4ac0b-108">Preferowana opcja anulowania</span><span class="sxs-lookup"><span data-stu-id="4ac0b-108">Preferred cancel option</span></span>
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a><span data-ttu-id="4ac0b-109">Anulowanie zadania planowania głównego ze strony **Nieukończone procesy planowania**</span><span class="sxs-lookup"><span data-stu-id="4ac0b-109">Cancel master planning job from **Unfinished planning processes** page</span></span>
1. <span data-ttu-id="4ac0b-110">Przejdź do pozycji **Planowanie główne > Zapytania i raporty > Planowanie główne > Nieukończone procesy planowania**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-110">Go to **Master planning > Inquiries and reports > Master planning > Unfinished planning processes**.</span></span>
2. <span data-ttu-id="4ac0b-111">Wybierz wiersz z procesem planowania, który chcesz anulować.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-111">Select the line with the planning process that you want to cancel.</span></span>
3. <span data-ttu-id="4ac0b-112">Kliknij **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-112">Click **Cancel**.</span></span>

## <a name="additional-cancel-options"></a><span data-ttu-id="4ac0b-113">Dodatkowe opcje anulowania</span><span class="sxs-lookup"><span data-stu-id="4ac0b-113">Additional cancel options</span></span>
<span data-ttu-id="4ac0b-114">Te opcji powinny być używane tylko, jeśli anulowanie zadania planowania głównego na stronie **Nieukończone procesy planowania** nie zostały ukończone w ciągu kilku minut.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-114">These should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a><span data-ttu-id="4ac0b-115">Usuwanie zadania planowania głównego ze strony **Zadania wsadowe**</span><span class="sxs-lookup"><span data-stu-id="4ac0b-115">Delete master planning job from the **Batch jobs** page</span></span>
1. <span data-ttu-id="4ac0b-116">Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-116">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="4ac0b-117">Wybierz wiersz z zadaniem planowania, które chcesz usunąć.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-117">Select the line with the planning job that you want to delete.</span></span>
3. <span data-ttu-id="4ac0b-118">Kliknij przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-118">Click **Delete**.</span></span>

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a><span data-ttu-id="4ac0b-119">Przerywanie zadania dla zadania planowania głównego ze strony **Rozszerzone zadania wsadowe**</span><span class="sxs-lookup"><span data-stu-id="4ac0b-119">Abort master planning job task from the **Batch jobs enhanced** page</span></span>
1. <span data-ttu-id="4ac0b-120">Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-120">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="4ac0b-121">Jeśli identyfikator zadania nie jest wyświetlany na liście, kliknij pozycję **Przełącz do formularza rozszerzonego**, w przeciwnym razie przejdź do następnego kroku.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-121">If the job ID is not shown in the list, click **Switch to enhanced form**, otherwise proceed with the next step.</span></span>
3. <span data-ttu-id="4ac0b-122">Otwórz zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-122">Open the batch job.</span></span> <span data-ttu-id="4ac0b-123">Kliknij **identyfikator zadania** dla zadania wsadowego z zadaniami, które chcesz zakończyć.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-123">Click the **Job ID** for the batch job with tasks that you want to end.</span></span>
4. <span data-ttu-id="4ac0b-124">W obszarze **Zadania wsadowe** wybierz zadania do zakończenia.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-124">In **Batch tasks**, select the tasks to end.</span></span>
5. <span data-ttu-id="4ac0b-125">Kliknij pozycję **Zmień stan**, wybierz pozycję **Anuluj** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-125">Click **Change status**, choose **Canceling** and click **OK**.</span></span>
6. <span data-ttu-id="4ac0b-126">Na skróconej karcie **Zadania wsadowe** kliknij pozycję **Przerwij**.</span><span class="sxs-lookup"><span data-stu-id="4ac0b-126">On the **Batch tasks** FastTab, click **Abort**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]