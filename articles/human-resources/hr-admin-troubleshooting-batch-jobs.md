---
title: Optymalizowanie wydajności – planowanie zadań wsadowych po godzinach pracy
description: W tym temacie wyjaśniono, jak rozwiązywać pewne problemy z wydajnością w Microsoft Dynamics 365 Human Resources poprzez planowanie długotrwałych zadań wsadowych po godzinach pracy.
author: andreabichsel
manager: AnnBe
ms.date: 06/23/2020
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
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 452a87cf5ba6c1ac73636584d75b2ec2ac555e02
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527772"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="ab488-103">Optymalizowanie wydajności – planowanie zadań wsadowych po godzinach pracy</span><span class="sxs-lookup"><span data-stu-id="ab488-103">Optimize performance by scheduling batch jobs after hours</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="ab488-104">Wystawienie</span><span class="sxs-lookup"><span data-stu-id="ab488-104">Issue</span></span>

<span data-ttu-id="ab488-105">Microsoft Dynamics 365 Human Resources może napotkać problemy z wydajnością, jeśli długotrwałe zadania wsadowe są uruchamiane podczas godzin pracy w firmie.</span><span class="sxs-lookup"><span data-stu-id="ab488-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="ab488-106">Rozdzielczość</span><span class="sxs-lookup"><span data-stu-id="ab488-106">Resolution</span></span>

<span data-ttu-id="ab488-107">Zaplanuj następujące zadania wsadowe po godzinach pracy.</span><span class="sxs-lookup"><span data-stu-id="ab488-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="ab488-108">Zalecamy również przejrzenie częstotliwości zadań wsadowych, które są często wykonywane.</span><span class="sxs-lookup"><span data-stu-id="ab488-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="ab488-109">Jeśli to możliwe, zmniejsz cykl powtarzalności dla zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="ab488-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="ab488-110">W wielu przypadkach wystarcza domyślna częstotliwość.</span><span class="sxs-lookup"><span data-stu-id="ab488-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="ab488-111">Poniższe zadania wsadowe powinny być uruchamiane w nocy lub po godzinach.</span><span class="sxs-lookup"><span data-stu-id="ab488-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="ab488-112">Należy sprawdzić strefę czasową cyklicznych zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="ab488-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="ab488-113">Niektóre zadania wsadowe mogą wykorzystywać standardowy czas pacyficzny (PST).</span><span class="sxs-lookup"><span data-stu-id="ab488-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="ab488-114">Zadanie przetwarzania wsadowego</span><span class="sxs-lookup"><span data-stu-id="ab488-114">Batch job</span></span> | <span data-ttu-id="ab488-115">Domyślna powtarzalność</span><span class="sxs-lookup"><span data-stu-id="ab488-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="ab488-116">Czyszczenie historii zadań wsadowych</span><span class="sxs-lookup"><span data-stu-id="ab488-116">Batch job history cleanup</span></span> | <span data-ttu-id="ab488-117">1 raz na miesiąc</span><span class="sxs-lookup"><span data-stu-id="ab488-117">1 time per month</span></span> |
| <span data-ttu-id="ab488-118">Eksportuj czyszczenie danych pośrednich</span><span class="sxs-lookup"><span data-stu-id="ab488-118">Export staging cleanup</span></span> | <span data-ttu-id="ab488-119">1 raz na dzień</span><span class="sxs-lookup"><span data-stu-id="ab488-119">1 time per day</span></span> |
| <span data-ttu-id="ab488-120">Synchronizacja pominiętych żądań integracji usługi Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ab488-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="ab488-121">1 raz na dzień</span><span class="sxs-lookup"><span data-stu-id="ab488-121">1 time per day</span></span> |
| <span data-ttu-id="ab488-122">Zadanie systemowe kompresji bazy danych, które musi działać regularnie po godzinach pracy</span><span class="sxs-lookup"><span data-stu-id="ab488-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="ab488-123">1 raz na dzień</span><span class="sxs-lookup"><span data-stu-id="ab488-123">1 time per day</span></span> |
| <span data-ttu-id="ab488-124">Zadanie systemowe odbudowania indeksu bazy danych, które musi działać regularnie po godzinach pracy</span><span class="sxs-lookup"><span data-stu-id="ab488-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="ab488-125">1 raz na dzień</span><span class="sxs-lookup"><span data-stu-id="ab488-125">1 time per day</span></span> |

1. <span data-ttu-id="ab488-126">W module Human Resources wybierz opcję **administrowanie systemem**.</span><span class="sxs-lookup"><span data-stu-id="ab488-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="ab488-127">Na pasku **Wyszukiwania** wyszukaj jedno z powyższych zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="ab488-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="ab488-128">Wybierz **Uruchom w tle**, a następnie **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="ab488-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Ustaw cykl](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="ab488-130">W obszarze **Zdefiniuj cykl** ustaw **datę rozpoczęcia** i **godzinę rozpoczęcia** na czas poza godzinami pracy lub weekend.</span><span class="sxs-lookup"><span data-stu-id="ab488-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="ab488-131">Wybierz **Brak daty zakończenia**.</span><span class="sxs-lookup"><span data-stu-id="ab488-131">Select **No end date**.</span></span> 

   ![Definiowanie daty i godziny rozpoczęcia](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="ab488-133">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab488-133">Select **OK**.</span></span>

6. <span data-ttu-id="ab488-134">W razie potrzeby zmień dowolne inne parametry w obszarze **Uruchom w tle**, a następnie wybierz przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab488-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ab488-135">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ab488-135">Additional resources</span></span>

[<span data-ttu-id="ab488-136">Optymalizowanie wydajności za pomocą zadań automatycznego czyszczenia</span><span class="sxs-lookup"><span data-stu-id="ab488-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)
