---
title: Tworzenie zadania wsadowego
description: Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fbb844ebcf8d4b47b127132a5bf0ea45fa40f747
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "313366"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="e926c-103">Tworzenie zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="e926c-103">Create a batch job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e926c-104">Zadanie wsadowe to grupa podzadań, które są przesyłane do wystąpienia serwera obiektów aplikacji (AOS) w celu automatycznego przetworzenia.</span><span class="sxs-lookup"><span data-stu-id="e926c-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="e926c-105">Zadania wsadowe są uruchamiane przy użyciu poświadczeń zabezpieczeń użytkownika, który je utworzył.</span><span class="sxs-lookup"><span data-stu-id="e926c-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="e926c-106">Aby utworzyć zadanie wsadowe, należy wykonać następującą procedurę.</span><span class="sxs-lookup"><span data-stu-id="e926c-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="e926c-107">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="e926c-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="e926c-108">Tworzenie zadania wsadowego</span><span class="sxs-lookup"><span data-stu-id="e926c-108">Create the batch job</span></span>
1. <span data-ttu-id="e926c-109">Wybierz kolejno opcje Administrowanie systemem > Zapytania > Zadania wsadowe.</span><span class="sxs-lookup"><span data-stu-id="e926c-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="e926c-110">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="e926c-110">Click New.</span></span>
3. <span data-ttu-id="e926c-111">W polu Opis stanowiska wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="e926c-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="e926c-112">W polu Planowana data/godzina rozpoczęcia wprowadź datę i godzinę.</span><span class="sxs-lookup"><span data-stu-id="e926c-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="e926c-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="e926c-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="e926c-114">Tworzenie cyklu</span><span class="sxs-lookup"><span data-stu-id="e926c-114">Create a recurrence</span></span>
1. <span data-ttu-id="e926c-115">W okienku akcji kliknij opcję Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="e926c-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="e926c-116">Kliknij przycisk Cykl.</span><span class="sxs-lookup"><span data-stu-id="e926c-116">Click Recurrence.</span></span>
    * <span data-ttu-id="e926c-117">Te opcje służą do wprowadzania zakresu i wzorca cyklu.</span><span class="sxs-lookup"><span data-stu-id="e926c-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="e926c-118">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e926c-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="e926c-119">Dodawanie alertów</span><span class="sxs-lookup"><span data-stu-id="e926c-119">Add alerts</span></span>
1. <span data-ttu-id="e926c-120">W okienku akcji kliknij opcję Zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="e926c-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="e926c-121">Kliknij opcję Alerty.</span><span class="sxs-lookup"><span data-stu-id="e926c-121">Click Alerts.</span></span>
    * <span data-ttu-id="e926c-122">Wskaż, czy komunikaty alarmowe mają być wysłane, po zakończeniu zadania wsadowego, wystąpieniu w nim błędu lub anulowaniu.</span><span class="sxs-lookup"><span data-stu-id="e926c-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="e926c-123">Następnie określ, czy alerty mają być wyświetlane w postaci komunikatów podręcznych.</span><span class="sxs-lookup"><span data-stu-id="e926c-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="e926c-124">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="e926c-124">Click OK.</span></span>

