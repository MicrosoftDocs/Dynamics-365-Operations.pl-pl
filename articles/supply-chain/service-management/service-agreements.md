---
title: Omówienie opracowania i ustanawiania przeglądów umów serwisowych
description: Umowy serwisowe pozwalają definiować zasoby, które mają być używane podczas typowej wizyty serwisowej, i sposób fakturowania tych zasobów dla klienta.
author: ShylaThompson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f906beb4f239add265cf280f6bfade66cb9eadc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835949"
---
# <a name="develop-and-establish-service-agreements-overview"></a><span data-ttu-id="92615-103">Omówienie opracowania i ustanawiania przeglądów umów serwisowych</span><span class="sxs-lookup"><span data-stu-id="92615-103">Develop and establish service agreements overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92615-104">Umowy serwisowe pozwalają definiować zasoby, które mają być używane podczas typowej wizyty serwisowej, i sposób fakturowania tych zasobów dla klienta.</span><span class="sxs-lookup"><span data-stu-id="92615-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="92615-105">Każda umowa serwisowa jest dołączona do projektu, za pośrednictwem którego transakcje są księgowane i fakturowane.</span><span class="sxs-lookup"><span data-stu-id="92615-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="92615-106">Jednak transakcje ze zlecenia serwisowego można również fakturować bezpośrednio w projekcie bez konieczności łączenia zlecenia serwisowego z umową serwisową.</span><span class="sxs-lookup"><span data-stu-id="92615-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="92615-107">Z tej opcji można skorzystać, jeśli zlecenie serwisowe dotyczy tylko jednorazowej wizyty serwisowej i jeśli konieczność szybkiego przetworzenia transakcji serwisowych jest ważniejsza niż konieczność rejestrowania szczegółowych informacji umowy serwisowej dotyczących klienta w określonym czasie.</span><span class="sxs-lookup"><span data-stu-id="92615-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="92615-108">Umowa serwisowa</span><span class="sxs-lookup"><span data-stu-id="92615-108">Service agreement</span></span>

<span data-ttu-id="92615-109">W każdej umowie serwisowej trzeba określić projekt, identyfikator umowy serwisowej i grupę umów serwisowych.</span><span class="sxs-lookup"><span data-stu-id="92615-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="92615-110">Dzięki grupie umów serwisowych można sortować i porządkować umowy serwisowe.</span><span class="sxs-lookup"><span data-stu-id="92615-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="92615-111">Nagłówek umowy serwisowej zawiera ustawienia dotyczące wszystkich dołączonych wierszy umowy:</span><span class="sxs-lookup"><span data-stu-id="92615-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="92615-112">Czy umowa serwisowa jest zawieszona.</span><span class="sxs-lookup"><span data-stu-id="92615-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="92615-113">Jeśli tak, nie można na jej podstawie generować zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="92615-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="92615-114">Czas trwania umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="92615-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="92615-115">Sposób łączenia wierszy zleceń serwisowych w zlecenia serwisowe.</span><span class="sxs-lookup"><span data-stu-id="92615-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="92615-116">Czy umowa serwisowa jest szablonem.</span><span class="sxs-lookup"><span data-stu-id="92615-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="92615-117">W nagłówku umowy serwisowej można również skonfigurować wszystkie przedmioty serwisu i zadania serwisowe, które mają zastosowanie do umowy serwisowej. W tym celu należy wprowadzić konkretne zadania serwisowe lub przedmioty serwisu, które mają zostać dołączone do różnych wierszy umowy.</span><span class="sxs-lookup"><span data-stu-id="92615-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="92615-118">W nagłówku umowy serwisowej można także kopiować wiersze umowy serwisowej i wiersze szablonu usługi do bieżącej umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="92615-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="92615-119">W programie można zawieszać umowę serwisową oraz blokować jej poszczególne wiersze.</span><span class="sxs-lookup"><span data-stu-id="92615-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="92615-120">Zaznaczenie pola wyboru **Zawieszone** w umowie serwisowej uniemożliwi wykonywanie następujących operacji:</span><span class="sxs-lookup"><span data-stu-id="92615-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="92615-121">Automatyczne lub ręczne tworzenie zleceń serwisowych z poziomu umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="92615-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="92615-122">Zaznaczenie pola wyboru **Zablokowane** w wierszu umowy serwisowej uniemożliwi wykonywanie następujących operacji:</span><span class="sxs-lookup"><span data-stu-id="92615-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="92615-123">Automatyczne lub ręczne tworzenie zleceń serwisowych z poziomu wiersza umowy serwisowej.</span><span class="sxs-lookup"><span data-stu-id="92615-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="92615-124">Kopiowanie wiersza umowy serwisowej do innej umowy serwisowej lub zlecenia serwisowego.</span><span class="sxs-lookup"><span data-stu-id="92615-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="92615-125">Jeśli umowa serwisowa zostanie zawieszona, wszystkie dołączone wiersze są blokowane niezależnie od ich indywidualnego statusu.</span><span class="sxs-lookup"><span data-stu-id="92615-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="92615-126">Wiersze umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="92615-126">Service-agreement lines</span></span>

<span data-ttu-id="92615-127">Każdy wiersz umowy serwisowej zawiera szczegółowy opis proponowanych czynności serwisowych.</span><span class="sxs-lookup"><span data-stu-id="92615-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="92615-128">Wiersze te zawierają następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="92615-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="92615-129">typ transakcji i opis typu transakcji;</span><span class="sxs-lookup"><span data-stu-id="92615-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="92615-130">pracownik wykonujący czynności serwisowe;</span><span class="sxs-lookup"><span data-stu-id="92615-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="92615-131">przedmioty, których dotyczą czynności serwisowe wykonywane na mocy umowy serwisowej;</span><span class="sxs-lookup"><span data-stu-id="92615-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="92615-132">częstotliwość, z jaką są wykonywane czynności oraz z jaką są rejestrowane towary, wydatki i opłaty;</span><span class="sxs-lookup"><span data-stu-id="92615-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="92615-133">okno czasowe, w którym można grupować wiersze zlecenia serwisowego w jedno zlecenie serwisowe;</span><span class="sxs-lookup"><span data-stu-id="92615-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="92615-134">zadania serwisowe, przy użyciu których grupuje się zbiory wierszy umowy w zadania robocze oraz przedstawia technikom serwisu i klientom podsumowanie informacji o zadaniu serwisowym, które ma zostać wykonane;</span><span class="sxs-lookup"><span data-stu-id="92615-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="92615-135">informacja, czy wiersz jest zablokowany —</span><span class="sxs-lookup"><span data-stu-id="92615-135">Whether a line is stopped.</span></span> <span data-ttu-id="92615-136">jeśli tak, nie można tworzyć zleceń serwisowych dla danego wiersza;</span><span class="sxs-lookup"><span data-stu-id="92615-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="92615-137">ustawienia projektu, takie jak kategoria i właściwość wiersza.</span><span class="sxs-lookup"><span data-stu-id="92615-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="92615-138">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="92615-138">Related topics</span></span>

[<span data-ttu-id="92615-139">Tworzenie umów o świadczenie usług</span><span class="sxs-lookup"><span data-stu-id="92615-139">Create service agreements</span></span>](create-service-agreements.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]