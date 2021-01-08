---
title: Konfigurowanie programów sprzedaży ciągłej dla biur obsługi
description: W tym artykule opisano sposób konfigurowania programu sprzedaży ciągłej dla biura obsługi.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 738841407b63ef604da092b7c8f4d0f2064d3886
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414819"
---
# <a name="set-up-continuity-programs-for-call-centers"></a><span data-ttu-id="4eff5-103">Konfigurowanie programów sprzedaży ciągłej dla biur obsługi</span><span class="sxs-lookup"><span data-stu-id="4eff5-103">Set up continuity programs for call centers</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4eff5-104">W tym artykule opisano sposób konfigurowania programu sprzedaży ciągłej dla biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="4eff5-104">This article describes how to set up a continuity program for a call center.</span></span>

<span data-ttu-id="4eff5-105">W programie ciągłości nazywanym także programem cyklicznych zamówień, klienci otrzymują regularne wysyłki produktów według wstępnie zdefiniowanego harmonogramu.</span><span class="sxs-lookup"><span data-stu-id="4eff5-105">In a continuity program, which is also known as a recurring order program, customers receive regular product shipments according to a predefined schedule.</span></span> <span data-ttu-id="4eff5-106">Każda wysyłka może zawierać inny produkt, tak jak w przypadku klubu książki miesiąca, lub ten sam produkt, który jest wysyłany wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="4eff5-106">Each shipment can contain a different product, as in the case of a book-of-the-month club, or the same product can be sent repeatedly.</span></span> <span data-ttu-id="4eff5-107">Aby skonfigurować program sprzedaży ciągłej, należy wykonać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="4eff5-107">To set up a continuity program, you must complete the following tasks.</span></span>

1. <span data-ttu-id="4eff5-108">Ustaw parametry ciągłości na stronie **Parametry biura obsługi**.</span><span class="sxs-lookup"><span data-stu-id="4eff5-108">Set the continuity parameters on the **Call center parameters** page.</span></span>
2. <span data-ttu-id="4eff5-109">Utwórz program sprzedaży ciągłej, który określa szczegóły, takie jak harmonogram płatności, czas wysyłki, oraz czy fakturowanie dokonywane jest na początku.</span><span class="sxs-lookup"><span data-stu-id="4eff5-109">Create a continuity program that specifies details such as the payment schedule, the timing of the shipments, and whether billing is up front.</span></span> <span data-ttu-id="4eff5-110">Należy także dodać listę produktów, które są uwzględniane w programie sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="4eff5-110">You must also add a list of products that are included in the continuity program.</span></span> <span data-ttu-id="4eff5-111">Każdy produkt otrzymuje numer identyfikacyjny zdarzenia przypisany kolejno, począwszy od 1.</span><span class="sxs-lookup"><span data-stu-id="4eff5-111">Each product receives an event ID number that is assigned sequentially, beginning with 1.</span></span> <span data-ttu-id="4eff5-112">Identyfikatory zdarzeń określają kolejność, w której produkty są wysyłane.</span><span class="sxs-lookup"><span data-stu-id="4eff5-112">The event IDs determine the order that products are sent in.</span></span>

    - <span data-ttu-id="4eff5-113">Klienci otrzymują inny produkt w każdej wysyłce, produkty są wysyłane w kolejności według ich identyfikatorów zdarzeń, począwszy od bieżącego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4eff5-113">If customers receive a different product in each shipment, the products are sent in sequential order, based on their event IDs and beginning with the current event.</span></span>
    - <span data-ttu-id="4eff5-114">Kiedy klienci otrzymują ten sam produkt w każdej wysyłce, lista zawiera tylko jeden produkt, który zawiera jeden identyfikator zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4eff5-114">If customers receive the same product in each shipment, the list contains only one product that has one event ID.</span></span> <span data-ttu-id="4eff5-115">To samo zdarzenie powtarza się.</span><span class="sxs-lookup"><span data-stu-id="4eff5-115">The same event occurs repeatedly.</span></span> <span data-ttu-id="4eff5-116">Można określić, ile razy każde zdarzenie ma być powtórzone.</span><span class="sxs-lookup"><span data-stu-id="4eff5-116">You can specify how many times each event is repeated.</span></span>

3. <span data-ttu-id="4eff5-117">Utwórz produkt nadrzędny, który reprezentuje program ciągłości sprzedaży utworzony w zadaniu 2.</span><span class="sxs-lookup"><span data-stu-id="4eff5-117">Create a parent product that represents the continuity program that you created in task 2.</span></span> <span data-ttu-id="4eff5-118">Po dodaniu tego produktu do zamówienia sprzedaży otworzy się okno **Ciągłość**.</span><span class="sxs-lookup"><span data-stu-id="4eff5-118">If you add this product to a sales order, the **Continuity** page opens.</span></span> <span data-ttu-id="4eff5-119">Tej strony można następnie użyć do tworzenia rzeczywistego zamówienia sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="4eff5-119">You can then use that page to create the actual continuity order.</span></span> <span data-ttu-id="4eff5-120">Produkt nadrzędny nie określa poszczególnych produktów, które użytkownik otrzymuje w każdej wysyłce.</span><span class="sxs-lookup"><span data-stu-id="4eff5-120">The parent product doesn't specify the individual products that the customer receives in each shipment.</span></span>

<span data-ttu-id="4eff5-121">Po skonfigurowaniu programu ciągłości zgodnie z opisem powyżej można utworzyć zamówienie ciągłe dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="4eff5-121">After you've set up a continuity program as described above, you can create a continuity order for a customer.</span></span> <span data-ttu-id="4eff5-122">Również wystąpić konieczność wykonania następujących dodatkowych zadań konserwacyjnych.</span><span class="sxs-lookup"><span data-stu-id="4eff5-122">You might also have to perform the following additional maintenance tasks.</span></span>

- <span data-ttu-id="4eff5-123">**Aktualizuj okres bieżącego zdarzenia ciągłości** — skonfiguruj zadanie wsadowe, które informuje system, jaki jest okres bieżącego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4eff5-123">**Update the current continuity event period** – Set up a batch job that tells the system what the current event period is.</span></span>
- <span data-ttu-id="4eff5-124">**Utwórz podrzędne zamówienia ciągłej sprzedaży** — utwórz podrzędne zamówienia z nadrzędnego zamówienia ciągłej sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="4eff5-124">**Create continuity child orders** – Create child orders from the parent continuity order.</span></span>
- <span data-ttu-id="4eff5-125">**Płatności w procesie sprzedaży ciągłej** — rozliczenia i powiadomienia przetwarzania dla płatności, które są skojarzone z zamówieniami sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="4eff5-125">**Process continuity payments** – Process billing and notifications for payments that are associated with continuity sales orders.</span></span>
- <span data-ttu-id="4eff5-126">**Rozszerzanie wierszy sprzedaży ciągłej** (jeśli wymagane) — rozszerzenie liczby przypadków, w których można powtarzać zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="4eff5-126">**Extend continuity lines** (if required) – Extend the number of times that a continuity event can be repeated.</span></span> <span data-ttu-id="4eff5-127">Powtarzanie wysyłek można następnie powiększyć poza limit, który został ustawiony w polu **Próg powtarzania zdarzenia ciągłości pracy** w parametrach biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="4eff5-127">The repetition of shipments can then extend beyond the limit that was set in the **Continuity repeat threshold** field in the call center parameters.</span></span>
- <span data-ttu-id="4eff5-128">**Dokonaj aktualizacji ciągłości** (jeśli wymagane) — synchronizuj zmiany między program ciągłości i nadrzędnymi zamówieniami sprzedaży ciągłej.</span><span class="sxs-lookup"><span data-stu-id="4eff5-128">**Perform a continuity update** (if required) – Synchronize changes between the continuity program and the continuity parent sales orders.</span></span>
- <span data-ttu-id="4eff5-129">**Zamknij wiersze i zamówienia nadrzędne ciągłe** — zamknij zamówienia ciągłe.</span><span class="sxs-lookup"><span data-stu-id="4eff5-129">**Close continuity parent lines and orders** – Close continuity orders.</span></span>
