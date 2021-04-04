---
title: Zdarzenia aplikacji magazynowej
description: W tym temacie opisano przetwarzanie zdarzeń aplikacji magazynu używane do przetwarzania komunikatów zdarzeń aplikacji magazynowych w ramach zadania wsadowego.
author: perlynne
manager: tfehr
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0bafcbd5306860cb80d6e813aabf83853a9011c1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248650"
---
# <a name="warehouse-app-event-processing"></a><span data-ttu-id="6c31a-103">Przetwarzanie zdarzenia aplikacji magazynu</span><span class="sxs-lookup"><span data-stu-id="6c31a-103">Warehouse app event processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6c31a-104">Zadania wsadowe działające w module Supply Chain Management mogą używać danych z kolejki do przetwarzania zdarzeń wydawanych przez aplikację magazynu w celu reagowania w razie potrzeby na zdarzenia sygnalizujące.</span><span class="sxs-lookup"><span data-stu-id="6c31a-104">Batch jobs running in Supply Chain Management can use data from a queue for processing events issued by the warehouse app to react as needed to the signaled events.</span></span> <span data-ttu-id="6c31a-105">Ta funkcja umożliwia dodanie odpowiednich zdarzeń do kolejki w odpowiedzi na określone typy akcji podejmowanych przez pracowników korzystających z aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6c31a-105">This feature add relevant events to the queue in response to certain types of actions taken by workers using the app.</span></span> <span data-ttu-id="6c31a-106">Przykładem jest użycie opcji **Utwórz i przetwórz zamówienia przeniesienia z funkcji aplikacji magazynu**, nagłówek i wiersze zamówienia przeniesienia są tworzone i aktualizowane w wewnętrznej odpowiedzi, gdy system uruchamia zadanie wsadowe **Przetwarzanie zdarzeń aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-106">An example is when using the **Create and process transfer orders from the warehouse app** feature, the transfer order header and lines get created and updated in the back end when the system is running the **Process warehouse app events** batch job.</span></span>

## <a name="enable-the-process-warehouse-app-events-feature"></a><span data-ttu-id="6c31a-107">Włączanie funkcji Przetwarzanie zdarzeń aplikacji magazynu</span><span class="sxs-lookup"><span data-stu-id="6c31a-107">Enable the Process warehouse app events feature</span></span>

<span data-ttu-id="6c31a-108">Aby móc używać tej funkcji, musi zosyać włączona w systemie.</span><span class="sxs-lookup"><span data-stu-id="6c31a-108">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="6c31a-109">Administratorzy mogą skorzystać ze strony [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="6c31a-109">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="6c31a-110">Funkcja Przetwarzanie zdarzeń aplikacji magazynu jest wymieniona jako:</span><span class="sxs-lookup"><span data-stu-id="6c31a-110">The Process warehouse app events feature is listed as:</span></span>

- <span data-ttu-id="6c31a-111">**Moduł** - Zarządzanie magazynem</span><span class="sxs-lookup"><span data-stu-id="6c31a-111">**Module** - Warehouse management</span></span>
- <span data-ttu-id="6c31a-112">**Nazwa funkcji** - Przetwarzanie zdarzeń aplikacji magazynu</span><span class="sxs-lookup"><span data-stu-id="6c31a-112">**Feature name** - Process warehouse app events</span></span>

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a><span data-ttu-id="6c31a-113">Umożliwia konfigurowanie zadania wsadowego w celu przetwarzania zdarzeń aplikacji magazynowych</span><span class="sxs-lookup"><span data-stu-id="6c31a-113">Set up a batch job to process warehouse app events</span></span>

### <a name="process-warehouse-app-events"></a><span data-ttu-id="6c31a-114">Przetwarzanie zdarzeń aplikacji magazynowej</span><span class="sxs-lookup"><span data-stu-id="6c31a-114">Process warehouse app events</span></span>

<span data-ttu-id="6c31a-115">Umożliwia konfigurowanie zaplanowanego zadania wsadowego w celu przetwarzania zdarzeń aplikacji magazynowych dla aktualizacji zamówień przeniesienia i aktualizowania wierszy.</span><span class="sxs-lookup"><span data-stu-id="6c31a-115">Set up a scheduled batch job to process the warehouse app events for the transfer order creation and line updates.</span></span>

1. <span data-ttu-id="6c31a-116">Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Przetwarzanie zdarzeń aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-116">Go to **Warehouse management \> Periodic tasks \> Process warehouse app events**.</span></span>
1. <span data-ttu-id="6c31a-117">Zostanie otwarte okno dialogowe Przetwarzanie zdarzeń aplikacji magazynu.</span><span class="sxs-lookup"><span data-stu-id="6c31a-117">The Process warehouse app events dialog box opens.</span></span> <span data-ttu-id="6c31a-118">Rozwiń skróconą kartę **Uruchom w tle** i ustaw opcję **Przetwarzanie wsadowe** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-118">Expand the **Run in background** FastTab and set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="6c31a-119">Na skróconej karcie **Uruchom w tle** wybierz **Cykl**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-119">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="6c31a-120">Zostanie otwarte okno dialogowe **Definiuj cykl**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-120">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="6c31a-121">Umożliwia ustawienie harmonogramu uruchamiania w zależności od potrzeb firmy.</span><span class="sxs-lookup"><span data-stu-id="6c31a-121">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="6c31a-122">Wybierz przycisk **OK**, aby powrócić do okna dialogowego **Przetwarzanie zdarzeń aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-122">Select **OK** to return to the **Process warehouse app events** dialog box.</span></span>
1. <span data-ttu-id="6c31a-123">Aby dodać zadanie wsadowe do kolejki przetwarzania wsadowego, należy wybrać opcję **OK** w oknie dialogowym **Przetwarzanie zdarzeń aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-123">Select **OK** in the **Process warehouse app events** dialog box to add the batch job to the batch queue.</span></span>

## <a name="query-warehouse-app-events"></a><span data-ttu-id="6c31a-124">Kwerenda zdarzeń aplikacji magazynu</span><span class="sxs-lookup"><span data-stu-id="6c31a-124">Query warehouse app events</span></span>

<span data-ttu-id="6c31a-125">Komunikaty dotyczące kolejki zdarzeń i zdarzeń generowane przez aplikację magazynu można przeglądać, przechodząc do **Zarządzanie magazynem \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Zdarzenia aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-125">You can view the event queue and events messages generated by the warehouse app by going to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>

## <a name="the-standard-event-queue-process"></a><span data-ttu-id="6c31a-126">Standardowy proces kolejki zdarzeń</span><span class="sxs-lookup"><span data-stu-id="6c31a-126">The standard event queue process</span></span>

<span data-ttu-id="6c31a-127">Kolejka zdarzeń aplikacji magazynu zazwyczaj będzie używana z następującym opisanym przepływem:</span><span class="sxs-lookup"><span data-stu-id="6c31a-127">The warehouse apps events queue will typically be used with the following described flow:</span></span>

1. <span data-ttu-id="6c31a-128">Zdarzenie jest dodawane do kolejki wraz z komunikatem o zdarzeniu.</span><span class="sxs-lookup"><span data-stu-id="6c31a-128">An event gets added to the queue  with an event message.</span></span> <span data-ttu-id="6c31a-129">Nowa wiadomość zawiera początkowo stan zdarzenia **Oczekujące**, co oznacza, że zadanie wsadowe **Przetwarzania zdarzeń aplikacji magazynu** nie odbiera i nie przetworzy tego komunikatu.</span><span class="sxs-lookup"><span data-stu-id="6c31a-129">The new message initially has an Event state of **Waiting**, which means that the **Process warehouse app events** batch job will not pick up and process this message.</span></span>
1. <span data-ttu-id="6c31a-130">Gdy tylko stan wiadomości zostanie zaktualizowany do stanu **W kolejce**, zadanie wsadowe **Przetwarzanie zdarzeń aplikacji magazynu** będzie pobierać i przetwarzać zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="6c31a-130">As soon as the message state is updated to **Queued**, the **Process warehouse app** events batch job will pick up and process the event.</span></span>
1. <span data-ttu-id="6c31a-131">Zadanie wsadowe aktualizuje stany zdarzeń na **Zakończone** albo **Niepowodzenie**, w zależności od tego, czy żądany proces był możliwy.</span><span class="sxs-lookup"><span data-stu-id="6c31a-131">The batch job updates the event states to either **Completed** or **Failed**, depending on whether the requested process was possible.</span></span>
1. <span data-ttu-id="6c31a-132">Po **zakończeniu** wszystkich pokrewnych komunikatów zdarzeń zdarzenie jest usuwane z kolejki.</span><span class="sxs-lookup"><span data-stu-id="6c31a-132">When all the related event messages are **Completed**, the event is deleted from the queue.</span></span>

 <span data-ttu-id="6c31a-133">Aby zapoznać się z szczegółowym przykładem, patrz [Tworzenie zamówienia przeniesienia z poziomu aplikacji magazynowej](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="6c31a-133">For a detailed example, see [Create transfer order from warehouse app process](create-transfer-order-from-warehouse-app.md).</span></span>

## <a name="handle-event-errors"></a><span data-ttu-id="6c31a-134">Obsługa błędów zdarzeń</span><span class="sxs-lookup"><span data-stu-id="6c31a-134">Handle event errors</span></span>

<span data-ttu-id="6c31a-135">W ramach przetwarzania zdarzenia dotyczącego magazynu żądana czynność wiadomości może nie mieć procesów w ramach zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="6c31a-135">As part of the warehouse event processing, the requested message activity may not receive processes from the batch job.</span></span> <span data-ttu-id="6c31a-136">W takim przypadku komunikat zdarzenia ulegnie zmianie na **Niepowodzenie**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-136">In this case, the event message will change to **Failed**.</span></span> <span data-ttu-id="6c31a-137">Z informacji w **dzienniku partii** można dowiedzieć się, dlaczego i podjąć niezbędne działania w celu rozwiązania problemów.</span><span class="sxs-lookup"><span data-stu-id="6c31a-137">You can use the **Batch log** information to learn why and take needed action to correct any problems.</span></span>

<span data-ttu-id="6c31a-138">Aby zapoznać się z szczegółowym przykładem, patrz [Tworzenie zamówienia przeniesienia z procesu aplikacji magazynu](create-transfer-order-from-warehouse-app.md).</span><span class="sxs-lookup"><span data-stu-id="6c31a-138">For a detailed example, see [Create transfer order from warehouse app](create-transfer-order-from-warehouse-app.md).</span></span>

<span data-ttu-id="6c31a-139">Aby zresetować komunikat o zdarzeniu niepowodzenia aplikacji magazynu:</span><span class="sxs-lookup"><span data-stu-id="6c31a-139">To reset a failed warehouse app event message:</span></span>

1. <span data-ttu-id="6c31a-140">Przejdź do **Zarządzanie magazynem \> Zapytania i raporty \> Dzienniki urządzeń przenośnych \> Zdarzenia aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-140">Go to **Warehouse management \> Inquiries and reports \> Mobile device logs \> Warehouse app events**.</span></span>
1. <span data-ttu-id="6c31a-141">W skróconej karcie **Komunikaty zdarzeń aplikacji magazynu** znajdź i zaznacz odpowiednie zdarzenie, które ma stan **Niepowodzenie** w kolumnie **Stan zdarzenia**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-141">On the **Warehouse app event messages** FastTab, find and select a relevant event that is showing **Failed** in the **Event state** column.</span></span>
1. <span data-ttu-id="6c31a-142">Wybierz opcję **Resetuj** z paska narzędzi **Komunikaty zdarzeń aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-142">Select **Reset** from the **Warehouse app event messages** toolbar.</span></span>
1. <span data-ttu-id="6c31a-143">Kontynuuj pracę do momentu zresetowania wszystkich odpowiednich komunikatów.</span><span class="sxs-lookup"><span data-stu-id="6c31a-143">Continue working until all relevant messages are reset.</span></span>

<span data-ttu-id="6c31a-144">Można również usunąć komunikat o zdarzeniu **Niepowodzenie**, używając opcji **Usuń** na pasku narzędzi **Komunikaty zdarzeń aplikacji magazynu**.</span><span class="sxs-lookup"><span data-stu-id="6c31a-144">You can also remove a **Failed** event message by using the **Delete** option on the **Warehouse app event messages** toolbar.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]