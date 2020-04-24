---
title: Omówienie umów dotyczących poziomu usług
description: Podpisując umowę dotyczącą poziomu usług, klient akceptuje minimalny czas reakcji liczony od momentu przyjęcia zgłoszenia przez firmę usługową do chwili rozwiązania problemu.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30b06e537b010b6b32799f76964cb85af892bc3f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216144"
---
# <a name="service-level-agreements-overview"></a><span data-ttu-id="9ae76-103">Omówienie umów dotyczących poziomu usług</span><span class="sxs-lookup"><span data-stu-id="9ae76-103">Service level agreements overview</span></span>       

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9ae76-104">Umowa dotycząca poziomu usług jest zawierana między firmą usługową a klientem korzystającym z jej usług.</span><span class="sxs-lookup"><span data-stu-id="9ae76-104">A service level agreement (SLA) is an agreement between a service company and a service customer.</span></span> <span data-ttu-id="9ae76-105">Podpisując ją, klient akceptuje minimalny czas reakcji liczony od momentu przyjęcia zgłoszenia przez firmę usługową do chwili rozwiązania problemu.</span><span class="sxs-lookup"><span data-stu-id="9ae76-105">In a SLA, the customer agrees to a minimum response time based on when the service company records the issue and when the issue is resolved.</span></span>

<span data-ttu-id="9ae76-106">W umowie takiej jest zdefiniowany standardowy poziom usług oferowanych klientom. Ponadto zawarty jest w niej jednoznacznie określony termin wykonania usługi.</span><span class="sxs-lookup"><span data-stu-id="9ae76-106">A SLA enforces a standard level of service that is offered to customers, and also makes it transparent to a service company when a service job should be completed.</span></span>

<span data-ttu-id="9ae76-107">W celu zapewnienia klientom różnych poziomów usług można przygotować dowolną liczbę umów dotyczących tych poziomów.</span><span class="sxs-lookup"><span data-stu-id="9ae76-107">Any number of SLAs can be created to offer service customers different levels of service.</span></span>

## <a name="create-a-service-level-agreement"></a><span data-ttu-id="9ae76-108">Tworzenie umowy dotyczącej poziomu usług</span><span class="sxs-lookup"><span data-stu-id="9ae76-108">Create a service level agreement</span></span>

1.  <span data-ttu-id="9ae76-109">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Umowy serwisowe** \> **Umowy dotyczące poziomu usług**.</span><span class="sxs-lookup"><span data-stu-id="9ae76-109">Click **Service management** \> **Setup** \> **Service agreements** \> **Service level agreements**.</span></span>

2.  <span data-ttu-id="9ae76-110">W polu **Umowa dotycząca poziomu usług** nadaj nazwę umowie SLA.</span><span class="sxs-lookup"><span data-stu-id="9ae76-110">Type a name for the service level agreement in the **Service level agreement** field.</span></span>

3.  <span data-ttu-id="9ae76-111">Wprowadź dozwolony czas rozwiązywania problemu zasygnalizowanego w zgłoszeniu serwisowym, do jakiego klient jest uprawniony na mocy umowy dotyczącej poziomu usług.</span><span class="sxs-lookup"><span data-stu-id="9ae76-111">Type the time that you want to allow for completion of service calls that are attached to the service level agreement.</span></span> <span data-ttu-id="9ae76-112">Następnie wybierz kalendarz, jeśli ma on zostać uwzględniony w umowie.</span><span class="sxs-lookup"><span data-stu-id="9ae76-112">Then select a calendar if you want to base the service level agreement on a specific calendar.</span></span>

## <a name="apply-a-service-level-agreement"></a><span data-ttu-id="9ae76-113">Stosowanie umowy dotyczącej poziomu usług</span><span class="sxs-lookup"><span data-stu-id="9ae76-113">Apply a service level agreement</span></span>

<span data-ttu-id="9ae76-114">Umowa dotycząca poziomu usług jest stosowana bezpośrednio do umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="9ae76-114">The SLA is applied directly to a service agreement.</span></span>

<span data-ttu-id="9ae76-115">Zlecenia serwisowe utworzone ręcznie i dołączone do umowy serwisowej z przypisaną umową dotyczącą poziomu usług są analizowane z uwzględnieniem tej drugiej umowy.</span><span class="sxs-lookup"><span data-stu-id="9ae76-115">Service orders that you create manually and attach to a service agreement that has an SLA are measured against that SLA.</span></span>

<span data-ttu-id="9ae76-116">Z kolei zlecenia serwisowe utworzone automatycznie nie są dołączane do umowy dotyczącej poziomu usług.</span><span class="sxs-lookup"><span data-stu-id="9ae76-116">Service orders that you create automatically are not attached to an SLA.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a><span data-ttu-id="9ae76-117">Stosowanie umowy dotyczącej poziomu usług do umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="9ae76-117">Apply the service level agreement to the service agreement</span></span>

1.  <span data-ttu-id="9ae76-118">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Umowy serwisowe** \> **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="9ae76-118">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="9ae76-119">Zaznacz umowę serwisową, do której chcesz stosować umowę SLA, a następnie w **okienku akcji** kliknij przycisk **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="9ae76-119">Select the service agreement that you want to apply the SLA to, and then click **Edit** on the **Action Pane**.</span></span>

2.  <span data-ttu-id="9ae76-120">W polu **Umowa dotycząca poziomu usług** wybierz umowę SLA, którą chcesz przypisać.</span><span class="sxs-lookup"><span data-stu-id="9ae76-120">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a><span data-ttu-id="9ae76-121">Stosowanie umowy dotyczącej poziomu usług do grupy umów serwisowych</span><span class="sxs-lookup"><span data-stu-id="9ae76-121">Apply the service level agreement to the service agreement group</span></span>

1.  <span data-ttu-id="9ae76-122">Kliknij kolejno opcje **Zarządzanie serwisem** \> **Ustawienia** \> **Umowy serwisowe** \> **Grupy umów serwisowych**.</span><span class="sxs-lookup"><span data-stu-id="9ae76-122">Click **Service management** \> **Setup** \> **Service agreements** \> **Service agreement groups**.</span></span>

2.  <span data-ttu-id="9ae76-123">W polu **Umowa dotycząca poziomu usług** wybierz umowę SLA, którą chcesz przypisać.</span><span class="sxs-lookup"><span data-stu-id="9ae76-123">In the **Service level agreement** field, select the SLA that you want to assign.</span></span>

## <a name="track-time-on-a-service-order-against-an-sla"></a><span data-ttu-id="9ae76-124">Monitorowanie czasu realizacji zlecenia serwisowego na podstawie umowy dotyczącej poziomu usług</span><span class="sxs-lookup"><span data-stu-id="9ae76-124">Track time on a service order against an SLA</span></span>

<span data-ttu-id="9ae76-125">Po utworzeniu nowego zlecenia serwisowego dla umowy serwisowej, która ma przypisaną umowę dotycząca poziomu usług, jest inicjowany przedział czasu na wykonanie usługi, a system zaczyna monitorować czas realizacji.</span><span class="sxs-lookup"><span data-stu-id="9ae76-125">When you create a new service order for a service agreement that an SLA is assigned to, the time interval for the delivery of the service is initiated, and the system starts to track the delivery time.</span></span> <span data-ttu-id="9ae76-126">Ponadto można skonfigurować następujące opcje:</span><span class="sxs-lookup"><span data-stu-id="9ae76-126">Additionally, you can set the following options:</span></span>

  - <span data-ttu-id="9ae76-127">Istnieje możliwość rozpoczęcia i zatrzymania rejestracji czasu odnośnie do zlecenia serwisowego. Pozwala to zarejestrować łączny czas realizacji zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="9ae76-127">You can start and stop time recording on the service order to register the total amount of time that is spent on service orders.</span></span>

  - <span data-ttu-id="9ae76-128">Możliwe jest monitorowanie zgodności z przedziałem czasu zdefiniowanym w umowie dotyczącej poziomu usług.</span><span class="sxs-lookup"><span data-stu-id="9ae76-128">You can monitor compliance with the time interval that is set in the service level agreement.</span></span>

  - <span data-ttu-id="9ae76-129">Istnieje możliwość zdefiniowania kodów przyczyn, które muszą zostać określone w przypadku przekroczenia przedziału czasu zdefiniowanego w umowie dotyczącej poziomu usług.</span><span class="sxs-lookup"><span data-stu-id="9ae76-129">You can define reason codes that must be set if the time interval of the service level agreement is exceeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ae76-130">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="9ae76-130">See also</span></span>

[<span data-ttu-id="9ae76-131">Podgląd zgodności z umowami SLA</span><span class="sxs-lookup"><span data-stu-id="9ae76-131">View compliance with service level agreements</span></span>](view-compliance-with-service-level-agreements.md)

  


