---
title: Tworzenie zadania wsadowego
description: Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e4360cd7068658a170f5b44c2ce7c71c39c44fa8
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679895"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="33af2-103">Tworzenie zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="33af2-103">Create a batch job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="33af2-104">Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="33af2-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="33af2-105">Zadania wsadowe są uruchamiane przy użyciu poświadczeń zabezpieczeń użytkownika, który je utworzył.</span><span class="sxs-lookup"><span data-stu-id="33af2-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="33af2-106">Aby utworzyć zadanie wsadowe, należy wykonać następującą procedurę.</span><span class="sxs-lookup"><span data-stu-id="33af2-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="33af2-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="33af2-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="33af2-108">Tworzenie zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="33af2-108">Create the batch job</span></span>
1. <span data-ttu-id="33af2-109">Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Zapytania > Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="33af2-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="33af2-110">Kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="33af2-110">Click **New**.</span></span>
3. <span data-ttu-id="33af2-111">W polu **Opis stanowiska** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="33af2-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="33af2-112">W polu **Zaplanowana data/godzina rozpoczęcia** wpisz datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="33af2-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="33af2-113">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="33af2-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="33af2-114">Tworzenie cyklu</span><span class="sxs-lookup"><span data-stu-id="33af2-114">Create a recurrence</span></span>
1. <span data-ttu-id="33af2-115">W Panelu akcji kliknij **Zadanie wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="33af2-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="33af2-116">Kliknij **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="33af2-116">Click **Recurrence**.</span></span> <span data-ttu-id="33af2-117">Te opcje służą do wprowadzania zakresu i wzorca cyklu.</span><span class="sxs-lookup"><span data-stu-id="33af2-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="33af2-118">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="33af2-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="33af2-119">Dodawanie alertów</span><span class="sxs-lookup"><span data-stu-id="33af2-119">Add alerts</span></span>
1. <span data-ttu-id="33af2-120">W Panelu akcji kliknij **Zadanie wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="33af2-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="33af2-121">Kliknij **Ostrzeżenia**.</span><span class="sxs-lookup"><span data-stu-id="33af2-121">Click **Alerts**.</span></span> <span data-ttu-id="33af2-122">Wskaż, czy komunikaty alarmowe mają być wysłane, po zakończeniu zadania wsadowego, wystąpieniu w nim błędu lub anulowaniu.</span><span class="sxs-lookup"><span data-stu-id="33af2-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="33af2-123">Następnie określ, czy alerty mają być wyświetlane w postaci komunikatów podręcznych.</span><span class="sxs-lookup"><span data-stu-id="33af2-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="33af2-124">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="33af2-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="33af2-125">Dostosuj status zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="33af2-125">Adjust batch job status</span></span>
1. <span data-ttu-id="33af2-126">Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="33af2-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="33af2-127">Wybierz właściwe zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="33af2-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="33af2-128">W Panelu akcji kliknij **Zadanie wsadowe > Funkcje > Zmień status**.</span><span class="sxs-lookup"><span data-stu-id="33af2-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="33af2-129">Wybierz właściwy status:</span><span class="sxs-lookup"><span data-stu-id="33af2-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="33af2-130">**Wstrzymane**: Ustaw status zadania wsadowego jako **wstrzymane**, żeby zostało usunięte z planu zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="33af2-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="33af2-131">Jest to odpowiednik *stop*.</span><span class="sxs-lookup"><span data-stu-id="33af2-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="33af2-132">**Oczekujące**: Ustaw status zadania wsadowego jako **oczekujące**, żeby zostało wpisane na listę zadań oczekujących na dodanie do planu zadań wsadowych.</span><span class="sxs-lookup"><span data-stu-id="33af2-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="33af2-133">Jest to odpowiednik *iść*.</span><span class="sxs-lookup"><span data-stu-id="33af2-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="33af2-134">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="33af2-134">Click **OK**.</span></span>
