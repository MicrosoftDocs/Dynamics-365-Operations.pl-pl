---
title: Omówienie zarządzania usługą
description: W module Zarządzanie serwisem można ustalić umowy serwisowe i subskrypcje serwisu, obsługiwać zlecenia serwisowe i zapytania odbiorców oraz analizować usługi świadczone klientom i zarządzać nimi.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 451aeebd46d60251eed940016486509c4aa3f458
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987469"
---
# <a name="service-management-overview"></a><span data-ttu-id="d3962-103">Omówienie zarządzania usługą</span><span class="sxs-lookup"><span data-stu-id="d3962-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d3962-104">W module **Zarządzanie serwisem** można ustalić umowy serwisowe i subskrypcje serwisu, obsługiwać zlecenia serwisowe i zapytania odbiorców oraz analizować usługi świadczone klientom i zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="d3962-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="d3962-105">Umowy serwisowe służą do definiowania zasobów, które są używane w typowej wizycie serwisowej.</span><span class="sxs-lookup"><span data-stu-id="d3962-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="d3962-106">Umowy serwisowe umożliwiają także wyświetlanie sposobu fakturowania tych zasobów do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d3962-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="d3962-107">Umowa serwisowa może również uwzględnić umowę dotyczącą poziomu usług, która określa standardowe czasy odpowiedzi i oferuje narzędzia do rejestrowania czasu rzeczywistego.</span><span class="sxs-lookup"><span data-stu-id="d3962-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="d3962-108">Można utworzyć zlecenia serwisowe, aby zarządzać informacjami o zaplanowanych lub niezaplanowanych wizytach technika serwisu w siedzibie klienta.</span><span class="sxs-lookup"><span data-stu-id="d3962-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="d3962-109">Zlecenia serwisowe zawierają informacje, takie jak:</span><span class="sxs-lookup"><span data-stu-id="d3962-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="d3962-110">Godziny pracy technika serwisu</span><span class="sxs-lookup"><span data-stu-id="d3962-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="d3962-111">Typ usługi lub naprawy</span><span class="sxs-lookup"><span data-stu-id="d3962-111">The type of service or repair</span></span>

3.  <span data-ttu-id="d3962-112">Element do naprawienia, w tym szczegóły dotyczące objawów i diagnozy</span><span class="sxs-lookup"><span data-stu-id="d3962-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="d3962-113">Wszelkie wydatki i opłaty związane z usługą lub naprawą</span><span class="sxs-lookup"><span data-stu-id="d3962-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="d3962-114">Można odbierać, przetwarzać i wysyłać żądania obsługi.</span><span class="sxs-lookup"><span data-stu-id="d3962-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="d3962-115">Po utworzeniu zlecenia serwisowego, można używać etapów serwisu, aby monitorować postęp i określać reguły, które kontrolują, jakie akcje są włączone na każdym etapie.</span><span class="sxs-lookup"><span data-stu-id="d3962-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="d3962-116">Po zakończeniu zlecenia serwisowego, wyrejestruj się na zamówieniu, aby potwierdzić, że jest zakończone, a następnie zaksięguj zamówienie w celu uruchomienia procesu fakturowania.</span><span class="sxs-lookup"><span data-stu-id="d3962-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="d3962-117">Użyj narzędzi raportowania, aby monitorować marże zleceń serwisowych i transakcji dotyczących subskrypcji oraz drukować opisy i pokwitowania pracy.</span><span class="sxs-lookup"><span data-stu-id="d3962-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="d3962-118">Procesy biznesowe</span><span class="sxs-lookup"><span data-stu-id="d3962-118">Business processes</span></span>

<span data-ttu-id="d3962-119">Poniższy diagram ilustruje ogólne procesy biznesowe w module **Zarządzanie serwisem** oraz pokazuje, gdzie procesy serwisowe integrują się z innymi modułami.</span><span class="sxs-lookup"><span data-stu-id="d3962-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules.</span></span>

<span data-ttu-id="d3962-120">[![Diagram procesów biznesowych w module Zarządzanie serwisem](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="d3962-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="d3962-121">Zarządzanie usługami w skrócie</span><span class="sxs-lookup"><span data-stu-id="d3962-121">Service management at a glance</span></span>

|<span data-ttu-id="d3962-122">Ważne zadania</span><span class="sxs-lookup"><span data-stu-id="d3962-122">Important tasks</span></span>           | <span data-ttu-id="d3962-123">Strony podstawowe</span><span class="sxs-lookup"><span data-stu-id="d3962-123">Primary pages</span></span>                         |<span data-ttu-id="d3962-124">Popularne raporty</span><span class="sxs-lookup"><span data-stu-id="d3962-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="d3962-125">Realizacja umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="d3962-125">Fulfill service agreements</span></span>|<span data-ttu-id="d3962-126">Umowy serwisowe</span><span class="sxs-lookup"><span data-stu-id="d3962-126">Service agreements</span></span>                     |<span data-ttu-id="d3962-127">Marża zlecenia serwisowego</span><span class="sxs-lookup"><span data-stu-id="d3962-127">Service order margin</span></span>         |
|<span data-ttu-id="d3962-128">Obsługa zapytań odbiorców</span><span class="sxs-lookup"><span data-stu-id="d3962-128">Handle customer inquiries</span></span> |<span data-ttu-id="d3962-129">Zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="d3962-129">Service orders</span></span>                         |<span data-ttu-id="d3962-130">Opis pracy</span><span class="sxs-lookup"><span data-stu-id="d3962-130">Work description</span></span>             |
|                          |<span data-ttu-id="d3962-131">Pulpit wysyłki</span><span class="sxs-lookup"><span data-stu-id="d3962-131">Dispatch board</span></span>                         |<span data-ttu-id="d3962-132">Transakcja — subskrypcja</span><span class="sxs-lookup"><span data-stu-id="d3962-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="d3962-133">Transakcje opłat subskrypcji</span><span class="sxs-lookup"><span data-stu-id="d3962-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="d3962-134">Integracja zarządzania usługami</span><span class="sxs-lookup"><span data-stu-id="d3962-134">Integration of Service management</span></span>

<span data-ttu-id="d3962-135">Zarządzanie usługami można zintegrować z następującymi modułami:</span><span class="sxs-lookup"><span data-stu-id="d3962-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="d3962-136">Sprzedaż i marketing — omówienie</span><span class="sxs-lookup"><span data-stu-id="d3962-136">Sales and marketing overview</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="d3962-137">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="d3962-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

