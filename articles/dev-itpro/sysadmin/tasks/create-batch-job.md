--- 
title: "Utwórz zadań wsadowych"
description: "Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b32c16a0c0045e22128746f81c6e9fd03370ac1f
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="create-batch-jobs"></a><span data-ttu-id="aea29-103">Utwórz zadań wsadowych</span><span class="sxs-lookup"><span data-stu-id="aea29-103">Create batch jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aea29-104">Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="aea29-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="aea29-105">Zadania wsadowe są uruchamiane przy użyciu poświadczeń zabezpieczeń użytkownika, który je utworzył.</span><span class="sxs-lookup"><span data-stu-id="aea29-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="aea29-106">Aby utworzyć zadanie wsadowe, należy wykonać następującą procedurę.</span><span class="sxs-lookup"><span data-stu-id="aea29-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="aea29-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="aea29-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="aea29-108">Tworzenie zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="aea29-108">Create the batch job</span></span>
1. <span data-ttu-id="aea29-109">Wybierz kolejno opcje Administrowanie systemem > Zapytania > Zadania wsadowe.</span><span class="sxs-lookup"><span data-stu-id="aea29-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="aea29-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="aea29-110">Click New.</span></span>
3. <span data-ttu-id="aea29-111">W polu Opis stanowiska wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="aea29-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="aea29-112">W polu Planowana data/godzina rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="aea29-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="aea29-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="aea29-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="aea29-114">Tworzenie cyklu</span><span class="sxs-lookup"><span data-stu-id="aea29-114">Create a recurrence</span></span>
1. <span data-ttu-id="aea29-115">W okienku akcji kliknij opcję Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="aea29-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="aea29-116">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="aea29-116">Click Recurrence.</span></span>
    * <span data-ttu-id="aea29-117">Te opcje służą do wprowadzania zakresu i wzorca cyklu.</span><span class="sxs-lookup"><span data-stu-id="aea29-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="aea29-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="aea29-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="aea29-119">Dodawanie alertów</span><span class="sxs-lookup"><span data-stu-id="aea29-119">Add alerts</span></span>
1. <span data-ttu-id="aea29-120">W okienku akcji kliknij opcję Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="aea29-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="aea29-121">Kliknij opcję Alerty.</span><span class="sxs-lookup"><span data-stu-id="aea29-121">Click Alerts.</span></span>
    * <span data-ttu-id="aea29-122">Wskaż, czy komunikaty alarmowe mają być wysłane, po zakończeniu zadania wsadowego, wystąpieniu w nim błędu lub anulowaniu.</span><span class="sxs-lookup"><span data-stu-id="aea29-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="aea29-123">Następnie określ, czy alerty mają być wyświetlane w postaci komunikatów podręcznych.</span><span class="sxs-lookup"><span data-stu-id="aea29-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="aea29-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="aea29-124">Click OK.</span></span>


