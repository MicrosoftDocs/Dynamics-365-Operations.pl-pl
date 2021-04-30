---
title: Resetowanie zablokowanych zadań wsadowych
description: W tym temacie opisano sposób rozwiązywania problemów związanych z zadaniami wsadowych, które są zablokowane.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 906a391b3c28d15445f6ddf0fc547ebcf842ba19
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881767"
---
# <a name="reset-stuck-batch-jobs"></a><span data-ttu-id="11c51-103">Resetowanie zablokowanych zadań wsadowych</span><span class="sxs-lookup"><span data-stu-id="11c51-103">Reset stuck batch jobs</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a><span data-ttu-id="11c51-104">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="11c51-104">Issue</span></span>

<span data-ttu-id="11c51-105">Microsoft Dynamics 365 Human Resources może mieć problemy z zadaniami wsadowym, które zablokowały się w stanie **Wykonywanie** lub **Anulowanie** i nie zostały ukończone.</span><span class="sxs-lookup"><span data-stu-id="11c51-105">Microsoft Dynamics 365 Human Resources can experience issues with batch jobs that are stuck in either an **Executing** or **Canceling** state and don't complete.</span></span>

## <a name="resolution"></a><span data-ttu-id="11c51-106">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="11c51-106">Resolution</span></span>

<span data-ttu-id="11c51-107">Gdy zadanie wsadowe znajduje się w stanie **Wykonywanie** lub **Anulowanie**, można zresetować stan, wymuś anulowanie zadania.</span><span class="sxs-lookup"><span data-stu-id="11c51-107">When a batch job is stuck in an **Executing** or **Canceling** state, you can reset the status by forcing the cancellation of the job.</span></span> <span data-ttu-id="11c51-108">Po jego anulowaniu można zresetować zadanie wsadowe, ustawiając dla niego stan **Oczekujące**.</span><span class="sxs-lookup"><span data-stu-id="11c51-108">After you cancel it, you can reset the batch job by setting it to a **Waiting** status.</span></span> <span data-ttu-id="11c51-109">Zostanie on następnie ponownie uruchomiony w celu wykonania w następnym zaplanowanym uruchomieniu wsadowym.</span><span class="sxs-lookup"><span data-stu-id="11c51-109">It will then be picked up again for execution in the next scheduled batch run.</span></span>

1. <span data-ttu-id="11c51-110">W obszarze roboczym **Administrowanie systemem** wybierz stronę **Łącza** i wybierz **Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="11c51-110">In the **System administration** workspace, select the **Links** page, and select **Batch jobs**.</span></span>

2. <span data-ttu-id="11c51-111">Na stronie listy **Zadań wsadowych** wybierz zadanie, które musi zostać zresetowane.</span><span class="sxs-lookup"><span data-stu-id="11c51-111">On the **Batch job** list page, select the job that needs to be reset.</span></span>

3. <span data-ttu-id="11c51-112">Na akcji na wstążce wybierz pozycję **Wymuszaj anulowanie** i potwierdź akcję.</span><span class="sxs-lookup"><span data-stu-id="11c51-112">On the action ribbon, select **Force cancel**, and confirm the action.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11c51-113">Akcja **Wymuszaj anulowanie** jest dostępna tylko wtedy, gdy wybrane zadanie wsadowe ma stan **Wykonywanie** lub **Anulowanie** oraz nie są uruchomione żadne procesy wykonywania wsadowego ani anulowania dla tego zadania.</span><span class="sxs-lookup"><span data-stu-id="11c51-113">The **Force cancel** action is only available when the selected batch job has a status of either **Executing** or **Canceling**, and no batch execution or cancellation processes are running for the job.</span></span>

4. <span data-ttu-id="11c51-114">Na wstążce akcji wybierz opcję **Zmień stan**.</span><span class="sxs-lookup"><span data-stu-id="11c51-114">On the action ribbon, select **Change status**.</span></span>

5. <span data-ttu-id="11c51-115">Na stronie **Wybierz nowy stan** wybierz pozycję **Oczekujące**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="11c51-115">On the **Select new status** page, select **Waiting**, and then select **OK**.</span></span>

   ![Wybierz nowy stan zadania wsadowego](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a><span data-ttu-id="11c51-117">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="11c51-117">See also</span></span>

[<span data-ttu-id="11c51-118">Aby zoptymalizować wydajność, należy zaplanować zadania wsadowe po godzinach</span><span class="sxs-lookup"><span data-stu-id="11c51-118">Optimize performance by scheduling batch jobs after hours</span></span>](hr-admin-troubleshooting-batch-jobs.md)<br>
[<span data-ttu-id="11c51-119">Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia</span><span class="sxs-lookup"><span data-stu-id="11c51-119">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
