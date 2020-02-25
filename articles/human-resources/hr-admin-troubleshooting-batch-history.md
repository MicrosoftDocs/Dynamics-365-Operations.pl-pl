---
title: Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia
description: W tym artykule wyjaśniono, jak rozwiązywać pewne problemy z wydajnością w Microsoft Dynamics 365 Human Resources, czyszcząc historię zadań wsadowych.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a983fde8ba393ab25f2b330014e04a1379f0e4d0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010163"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="f82ca-103">Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia</span><span class="sxs-lookup"><span data-stu-id="f82ca-103">Optimize performance with auto cleanup tasks</span></span>

<span data-ttu-id="f82ca-104">**Wystawienie**</span><span class="sxs-lookup"><span data-stu-id="f82ca-104">**Issue**</span></span>

<span data-ttu-id="f82ca-105">Microsoft Dynamics 365 Human Resources może napotkać problemy z wydajnością, jeśli historia zadania wsadowego rozrasta się zbyt dużą.</span><span class="sxs-lookup"><span data-stu-id="f82ca-105">Microsoft Dynamics 365 Human Resources can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="f82ca-106">**Powód**</span><span class="sxs-lookup"><span data-stu-id="f82ca-106">**Cause**</span></span>

<span data-ttu-id="f82ca-107">Często wykonywane zadania wsadowe mogą prowadzić do nietrwałego wzrostu historii zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="f82ca-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="f82ca-108">Może to spowodować problemy z wydajnością.</span><span class="sxs-lookup"><span data-stu-id="f82ca-108">This can cause performance issues.</span></span> 

<span data-ttu-id="f82ca-109">**Rozdzielczość**</span><span class="sxs-lookup"><span data-stu-id="f82ca-109">**Resolution**</span></span>

<span data-ttu-id="f82ca-110">Umożliwia zaplanowanie automatycznego zadania w celu oczyszczenia historii zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="f82ca-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="f82ca-111">Zalecamy skonfigurowanie zadania, aby było uruchamiane co tydzień, ale może być konieczne ręczne uruchomienie procesu oczyszczania w zależności od używanego środowiska.</span><span class="sxs-lookup"><span data-stu-id="f82ca-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="f82ca-112">Poniższa procedura zawiera zalecane ustawienia, ale można je zmienić zgodnie z potrzebami użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f82ca-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="f82ca-113">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-113">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="f82ca-114">Na pasku **wyszukiwania** wprowadź **oczyszczanie historii zadań wsadowych**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Wyszukaj okresowe oczyszczanie historii zadań wsadowych](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="f82ca-116">W polu **Limit historii (dni)** wprowadź **30**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-116">In **History limit (days)**, enter **30**.</span></span>

   ![Ustaw limit historii 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="f82ca-118">Wybierz **Uruchom w tle**, a następnie **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Ustaw cykl](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="f82ca-120">W obszarze **Zdefiniujcykl** ustaw **datę rozpoczęcia** i **godzinę rozpoczęcia** w godzinach poza godziną lub weekendu, a następnie wybierz opcję **brak daty zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Definiowanie daty i godziny rozpoczęcia](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="f82ca-122">W **wzorzec cyklu** wybierz **dni**, a następnie ustaw opcję **Powtarzaj po określonym przedziale** na **7**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Ustawienie oczyszczania powoduje powtarzanie tygodnia](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="f82ca-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-124">Select **OK**.</span></span>

8. <span data-ttu-id="f82ca-125">W razie potrzeby zmień dowolne inne parametry w obszarze **Uruchom w tle**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f82ca-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>

