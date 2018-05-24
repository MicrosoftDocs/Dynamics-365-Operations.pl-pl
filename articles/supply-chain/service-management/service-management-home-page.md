---
title: "Zarządzanie serwisem"
description: "W module Zarządzanie serwisem można ustalić umowy serwisowe i subskrypcje serwisu, obsługiwać zlecenia serwisowe i zapytania odbiorców oraz analizować usługi świadczone klientom i zarządzać nimi."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: pl-pl
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a><span data-ttu-id="0109f-103">Zarządzanie serwisem</span><span class="sxs-lookup"><span data-stu-id="0109f-103">Service management</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="0109f-104">W module **Zarządzanie serwisem** można ustalić umowy serwisowe i subskrypcje serwisu, obsługiwać zlecenia serwisowe i zapytania odbiorców oraz analizować usługi świadczone klientom i zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="0109f-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="0109f-105">Umowy serwisowe służą do definiowania zasobów, które są używane w typowej wizycie serwisowej.</span><span class="sxs-lookup"><span data-stu-id="0109f-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="0109f-106">Umowy serwisowe umożliwiają także wyświetlanie sposobu fakturowania tych zasobów do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="0109f-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="0109f-107">Umowa serwisowa może również uwzględnić umowę dotyczącą poziomu usług, która określa standardowe czasy odpowiedzi i oferuje narzędzia do rejestrowania czasu rzeczywistego.</span><span class="sxs-lookup"><span data-stu-id="0109f-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="0109f-108">Można utworzyć zlecenia serwisowe, aby zarządzać informacjami o zaplanowanych lub niezaplanowanych wizytach technika serwisu w siedzibie klienta.</span><span class="sxs-lookup"><span data-stu-id="0109f-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="0109f-109">Zlecenia serwisowe zawierają informacje, takie jak:</span><span class="sxs-lookup"><span data-stu-id="0109f-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="0109f-110">Godziny pracy technika serwisu</span><span class="sxs-lookup"><span data-stu-id="0109f-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="0109f-111">Typ usługi lub naprawy</span><span class="sxs-lookup"><span data-stu-id="0109f-111">The type of service or repair</span></span>

3.  <span data-ttu-id="0109f-112">Element do naprawienia, w tym szczegóły dotyczące objawów i diagnozy</span><span class="sxs-lookup"><span data-stu-id="0109f-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="0109f-113">Wszelkie wydatki i opłaty związane z usługą lub naprawą</span><span class="sxs-lookup"><span data-stu-id="0109f-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="0109f-114">Klienci mogą przesyłać żądania serwisowe za pośrednictwem Internetu przy użyciu witryny Enterprise Portal.</span><span class="sxs-lookup"><span data-stu-id="0109f-114">Customers can submit service requests through the Internet by using the Enterprise Portal.</span></span> <span data-ttu-id="0109f-115">Można odbierać, przetwarzać i wysyłać te żądania.</span><span class="sxs-lookup"><span data-stu-id="0109f-115">You can receive, process, and dispatch these requests.</span></span> <span data-ttu-id="0109f-116">Po utworzeniu zlecenia serwisowego, można używać etapów serwisu, aby monitorować postęp i określać reguły, które kontrolują, jakie akcje są włączone na każdym etapie.</span><span class="sxs-lookup"><span data-stu-id="0109f-116">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="0109f-117">Po zakończeniu zlecenia serwisowego, wyrejestruj się na zamówieniu, aby potwierdzić, że jest zakończone, a następnie zaksięguj zamówienie w celu uruchomienia procesu fakturowania.</span><span class="sxs-lookup"><span data-stu-id="0109f-117">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="0109f-118">Użyj narzędzi raportowania, aby monitorować marże zleceń serwisowych i transakcji dotyczących subskrypcji oraz drukować opisy i pokwitowania pracy.</span><span class="sxs-lookup"><span data-stu-id="0109f-118">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="0109f-119">Procesy biznesowe</span><span class="sxs-lookup"><span data-stu-id="0109f-119">Business processes</span></span>

<span data-ttu-id="0109f-120">Poniższy diagram ilustruje ogólne procesy biznesowe w module **Zarządzanie serwisem** oraz pokazuje, gdzie procesy serwisowe integrują się z innymi modułami w programie Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0109f-120">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="0109f-121">[![Diagram procesów biznesowych w module Zarządzanie serwisem](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="0109f-121">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="0109f-122">Zarządzanie usługami w skrócie</span><span class="sxs-lookup"><span data-stu-id="0109f-122">Service management at a glance</span></span>

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0109f-123">Ważne zadania</span><span class="sxs-lookup"><span data-stu-id="0109f-123">Important tasks</span></span></p></th>
<th><p><span data-ttu-id="0109f-124">Formularze podstawowe</span><span class="sxs-lookup"><span data-stu-id="0109f-124">Primary forms</span></span></p></th>
<th><p><span data-ttu-id="0109f-125">Popularne raporty</span><span class="sxs-lookup"><span data-stu-id="0109f-125">Popular reports</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0109f-126">Realizacja umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="0109f-126">Fulfill service agreements</span></span></a></p></td>
<td><p><span data-ttu-id="0109f-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Umowy serwisowe (formularz)</a></span><span class="sxs-lookup"><span data-stu-id="0109f-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Service agreements (form)</a></span></span></p></td>
<td><p><span data-ttu-id="0109f-128"><strong>Marża zlecenia serwisowego</strong></span><span class="sxs-lookup"><span data-stu-id="0109f-128"><strong>Service order margin</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0109f-129">Obsługa zapytań odbiorców</span><span class="sxs-lookup"><span data-stu-id="0109f-129">Handle customer inquiries</span></span></a></p></td>
<td><p><span data-ttu-id="0109f-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Zlecenia serwisowe (formularz)</a></span><span class="sxs-lookup"><span data-stu-id="0109f-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Service orders (form)</a></span></span></p></td>
<td><p><span data-ttu-id="0109f-131"><strong>Opis pracy</strong></span><span class="sxs-lookup"><span data-stu-id="0109f-131"><strong>Work description</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="0109f-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Pulpit wysyłki (formularz)</a></span><span class="sxs-lookup"><span data-stu-id="0109f-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Dispatch board (form)</a></span></span></p></td>
<td><p><span data-ttu-id="0109f-133"><strong>Transakcja — subskrypcja</strong></span><span class="sxs-lookup"><span data-stu-id="0109f-133"><strong>Transaction - subscription</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="0109f-134"><strong>Transakcje opłat subskrypcji</strong></span><span class="sxs-lookup"><span data-stu-id="0109f-134"><strong>Subscription fee transactions</strong></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a><span data-ttu-id="0109f-135">Integracja zarządzania usługami</span><span class="sxs-lookup"><span data-stu-id="0109f-135">Integration of Service management</span></span>

<span data-ttu-id="0109f-136">Moduł Zarządzanie serwisem może być zintegrowany z następujących modułami w programie Microsoft Dynamics 365 for Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="0109f-136">Service management can be integrated with the following modules in Microsoft Dynamics 365 for Finance and Operations:</span></span>

  - [<span data-ttu-id="0109f-137">Sprzedaż i marketing</span><span class="sxs-lookup"><span data-stu-id="0109f-137">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)

  - [<span data-ttu-id="0109f-138">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="0109f-138">Human resources</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


