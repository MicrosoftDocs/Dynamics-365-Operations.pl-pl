---
title: Wymagania konfiguracji produkcji
description: "Ten artykuł zawiera informacje o konfiguracji, jaką należy zapewnić przed rozpoczęciem używania modułu Kontrola produkcji."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47fe11168ad2ddea2a7033eda8d8bd8220efea32
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="production-setup-requirements"></a><span data-ttu-id="c693e-103">Wymagania konfiguracji produkcji</span><span class="sxs-lookup"><span data-stu-id="c693e-103">Production setup requirements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c693e-104">Ten artykuł zawiera informacje o konfiguracji, jaką należy zapewnić przed rozpoczęciem używania modułu Kontrola produkcji.</span><span class="sxs-lookup"><span data-stu-id="c693e-104">This article provides information about setup requirements before you can work with Production control.</span></span> 

<span data-ttu-id="c693e-105">Kontrola produkcji współpracuje z funkcjami w innych modułach.</span><span class="sxs-lookup"><span data-stu-id="c693e-105">Production control is integrated with features in other modules.</span></span> <span data-ttu-id="c693e-106">Dzięki możliwości łączenia się z innymi aplikacjami można zmieniać zlecenia produkcyjne i mieć pewność, że są automatycznie aktualizowane w innych pokrewnych procesach i obliczeniach wykonywanych w systemie.</span><span class="sxs-lookup"><span data-stu-id="c693e-106">This interconnectivity lets you change production orders and make sure that they are automatically updated in all other related processes and calculations in the system.</span></span> <span data-ttu-id="c693e-107">Poniżej znajduje się wykaz procedur konfiguracji w kolejności, w jakiej należy je wykonać.</span><span class="sxs-lookup"><span data-stu-id="c693e-107">The following setup processes are listed in the order that you should complete them in.</span></span>

## <a name="required-baseline-setup-in-other-modules"></a><span data-ttu-id="c693e-108">Wymagana konfiguracja podstawowa w innych modułach</span><span class="sxs-lookup"><span data-stu-id="c693e-108">Required baseline setup in other modules</span></span>
<span data-ttu-id="c693e-109">Aby używać modułu Kontrola produkcji, trzeba skonfigurować informacje w innych modułach.</span><span class="sxs-lookup"><span data-stu-id="c693e-109">Information in other modules must be set up before you can work with Production control.</span></span> <span data-ttu-id="c693e-110">Podzielono je na następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="c693e-110">This setup includes the following tasks:</span></span>

-   <span data-ttu-id="c693e-111">Wprowadzić podstawowe informacje o firmie.</span><span class="sxs-lookup"><span data-stu-id="c693e-111">Set up general company information.</span></span>
-   <span data-ttu-id="c693e-112">Skonfigurować księgę główną.</span><span class="sxs-lookup"><span data-stu-id="c693e-112">Set up the general ledger.</span></span>
-   <span data-ttu-id="c693e-113">Zdefiniować grupy towarów.</span><span class="sxs-lookup"><span data-stu-id="c693e-113">Define item groups.</span></span>
-   <span data-ttu-id="c693e-114">Skonfigurować konta księgowa grup towarów.</span><span class="sxs-lookup"><span data-stu-id="c693e-114">Set up ledger accounts for item groups.</span></span>
-   <span data-ttu-id="c693e-115">Utworzyć tabelę pozycji magazynowych w module Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="c693e-115">Set up the inventory item table in Inventory management.</span></span>
-   <span data-ttu-id="c693e-116">Utworzyć Listy składowe (BOM) i ich wersje w module Zarządzanie zapasami.</span><span class="sxs-lookup"><span data-stu-id="c693e-116">Create bills of materials (BOMs) and BOM versions in Inventory management.</span></span>

## <a name="required-calendar-and-resource-setup"></a><span data-ttu-id="c693e-117">Wymagana konfiguracja kalendarza i zasobu</span><span class="sxs-lookup"><span data-stu-id="c693e-117">Required calendar and resource setup</span></span>
<span data-ttu-id="c693e-118">Aby używać modułu Kontrola produkcji, otwórz moduł Administrowanie organizacją i utwórz oraz zdefiniuj kalendarz i zasoby operacyjne w następującej kolejności:</span><span class="sxs-lookup"><span data-stu-id="c693e-118">Before you use Production control, open Organization administration, and create and define the calendar and operations resources in the following order:</span></span>

1.  <span data-ttu-id="c693e-119">**Szablony czasu pracy** — skonfiguruj szablony czasu pracy, aby zdefiniować czas na planowanie produkcji.</span><span class="sxs-lookup"><span data-stu-id="c693e-119">**Working time templates** – Set up working time templates to define the times that are available for production scheduling.</span></span>
2.  <span data-ttu-id="c693e-120">**Kalendarze** — skonfiguruj kalendarze czasu pracy w celu określenia dni w roku na planowanie produkcji.</span><span class="sxs-lookup"><span data-stu-id="c693e-120">**Calendars** – Set up working time calendars to define the days of the year that are available for production scheduling.</span></span>
3.  <span data-ttu-id="c693e-121">**Grupy zasobów** — skonfiguruj grupy zasobów, aby pogrupować zasoby operacyjne. Dzięki temu można uzyskać przegląd wszelkich wolnych zdolności produkcyjnych po uruchomieniu planowania.</span><span class="sxs-lookup"><span data-stu-id="c693e-121">**Resource groups** – Set up resource groups to group the operations resources, so that you can get an overview of any free capacity when you run scheduling.</span></span> <span data-ttu-id="c693e-122">Nie masz ustawiać grup zasobów przed ustawieniem zasobów operacyjnych.</span><span class="sxs-lookup"><span data-stu-id="c693e-122">You don't have to set up resource groups before you set up operations resources.</span></span> <span data-ttu-id="c693e-123">Warto jednak znać sposób grupowania zasobów, kiedy ustawia się Kontrolę produkcji.</span><span class="sxs-lookup"><span data-stu-id="c693e-123">However, we recommend that you understand how to group resources when you set up Production control.</span></span>
4.  <span data-ttu-id="c693e-124">**Zasoby** — skonfiguruj zasoby operacyjne w celu zdefiniowania zasobów stosowanych do ukończenia procesu produkcyjnego i planowania zdolności produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="c693e-124">**Resources** – Set up operations resources to define the resources that are used to complete the production process and plan for capacity.</span></span>

## <a name="required-production-parameters-setup"></a><span data-ttu-id="c693e-125">Konfiguracja wymaganych parametrów produkcyjnych</span><span class="sxs-lookup"><span data-stu-id="c693e-125">Required production parameters setup</span></span>
<span data-ttu-id="c693e-126">**Parametry kontroli produkcji** — skonfiguruj podstawowe parametry produkcji w celu zdefiniowania sposobu, w jaki system obsługuje i przetwarza zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="c693e-126">**Production control parameters** – Set up basic production parameters to define how the system handles and processes production orders.</span></span> <span data-ttu-id="c693e-127">Zdefiniuj sposób tworzenia, szacowania, planowania i stosowania zleceń produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="c693e-127">Define how production orders are created, estimated, scheduled, and consumed.</span></span> <span data-ttu-id="c693e-128">Można także wybrać rodzaj informacji zwrotnych i sposób rozliczania kosztów.</span><span class="sxs-lookup"><span data-stu-id="c693e-128">You can also select what kind of feedback you want and how cost accounting is done.</span></span>

## <a name="required-journal-name-identification"></a><span data-ttu-id="c693e-129">Określanie nazwy wymaganego arkusza</span><span class="sxs-lookup"><span data-stu-id="c693e-129">Required journal name identification</span></span>
<span data-ttu-id="c693e-130">**Nazwy arkuszy produkcji** — określ nazwy arkusza produkcji, które są używane do rejestrowania i księgowania transakcji.</span><span class="sxs-lookup"><span data-stu-id="c693e-130">**Production journal names** – Specify the production journal names that are used to record and post transactions.</span></span>

## <a name="setup-if-you-use-operations"></a><span data-ttu-id="c693e-131">Skonfiguruj operacje (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="c693e-131">Setup if you use operations</span></span>
<span data-ttu-id="c693e-132">Operacje to określone działania, wykonywane w celu wykonania gotowego produktu.</span><span class="sxs-lookup"><span data-stu-id="c693e-132">Operations represent the specific activities that are completed to produce the finished product.</span></span> <span data-ttu-id="c693e-133">**Uwaga:** należy znać rodzaje działań, które są wymagane w celu wyprodukowania towaru, oraz kolejność i priorytety tych działań.</span><span class="sxs-lookup"><span data-stu-id="c693e-133">**Note:** You must know the types of activities that are required in order to produce your item, and the order and priorities of those activities.</span></span> <span data-ttu-id="c693e-134">Należy również ustalić, rodzaj i ilość potrzebnych zasobów.</span><span class="sxs-lookup"><span data-stu-id="c693e-134">You must also know which resources are involved, and how many.</span></span>

1.  <span data-ttu-id="c693e-135">**Operacje** — skonfiguruj operacje odpowiadające zadaniom, które trzeba wykonać w celu wyprodukowania gotowego towaru.</span><span class="sxs-lookup"><span data-stu-id="c693e-135">**Operations** – Set up operations to represent the tasks that must be completed to produce the finished item.</span></span>
2.  <span data-ttu-id="c693e-136">**Relacje** — skonfiguruj powiązania między operacjami, aby zdefiniować szczegółowe właściwości.</span><span class="sxs-lookup"><span data-stu-id="c693e-136">**Relations** – Set up operation relations to establish detailed properties.</span></span> <span data-ttu-id="c693e-137">Aby zdefiniować relacje operacji, kliknij przycisk **Relacje** na stronie **Operacje**.</span><span class="sxs-lookup"><span data-stu-id="c693e-137">To define operation relations, click **Relations** on the **Operations** page.</span></span>

## <a name="setup-if-you-use-routes"></a><span data-ttu-id="c693e-138">Skonfiguruj marszruty (jeśli są używane)</span><span class="sxs-lookup"><span data-stu-id="c693e-138">Setup if you use routes</span></span>
<span data-ttu-id="c693e-139">W wypadku stosowania marszrut operacje muszą zostać zdefiniowane dla każdej skonfigurowanej marszruty produkcji.</span><span class="sxs-lookup"><span data-stu-id="c693e-139">If you're working with routes, operations must be defined for every production route that you set up.</span></span> <span data-ttu-id="c693e-140">Marszruta to ścieżka towaru między kolejnymi operacjami, od początku do końca procesu produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="c693e-140">The route represents the path that the item takes from operation to operation, from the start of the production process to the end.</span></span>

1.  <span data-ttu-id="c693e-141">**Kategorie kosztów** — skonfiguruj kategorie kosztów w celu zdefiniowania kosztu odpowiednich procesów na godzinę. Skonfiguruj czasy.</span><span class="sxs-lookup"><span data-stu-id="c693e-141">**Cost categories** – Set up cost categories to define the cost per hour of specified processes and setup times.</span></span>
2.  <span data-ttu-id="c693e-142">**Grupy kosztów** — skonfiguruj grupy kosztów w celu utworzenia i obsługiwania różnych typów wyceny.</span><span class="sxs-lookup"><span data-stu-id="c693e-142">**Cost groups** – Set up cost groups to create and maintain different types of costing.</span></span>
3.  <span data-ttu-id="c693e-143">**Grupy marszrut** — skonfiguruj grupy marszrut w celu zdefiniowania parametrów dotyczących grup marszrut.</span><span class="sxs-lookup"><span data-stu-id="c693e-143">**Route groups** – Set up route groups to define parameters that are related to groups of routes.</span></span> <span data-ttu-id="c693e-144">Grupy marszrut trzeba skonfigurować przed utworzeniem marszrut produkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="c693e-144">You must set up route groups before you can create production routes.</span></span>
4.  <span data-ttu-id="c693e-145">**Marszruty** — skonfiguruj marszruty produkcyjne i zdefiniuj ustawienia domyślne kontroli planowania, wyznaczania kosztów i cen operacji marszrut, a także raportowania postępów.</span><span class="sxs-lookup"><span data-stu-id="c693e-145">**Routes** – Set up production routes, and define default settings to control scheduling, costing, and pricing of route operations, and to control progress reporting.</span></span>
5.  <span data-ttu-id="c693e-146">**Grupy marszrut** — skonfiguruj wersje marszruty, aby pozwolić na odchylenia produkcyjne towaru.</span><span class="sxs-lookup"><span data-stu-id="c693e-146">**Routes** – Set up route versions to enable item variations in production.</span></span>

## <a name="optional-advanced-settings"></a><span data-ttu-id="c693e-147">Opcjonalne ustawienia zaawansowane</span><span class="sxs-lookup"><span data-stu-id="c693e-147">Optional advanced settings</span></span>
1.  <span data-ttu-id="c693e-148">**Grupy produkcji** — skonfiguruj grupy produkcji w celu utworzenia relacji między zleceniem produkcyjnym i kontami księgowymi.</span><span class="sxs-lookup"><span data-stu-id="c693e-148">**Production groups** – Set up production groups to establish relationships between the production order and ledger accounts.</span></span> <span data-ttu-id="c693e-149">Konta księgowe są używane do księgowania lub grupowania zleceń do raportowania.</span><span class="sxs-lookup"><span data-stu-id="c693e-149">The ledger accounts are used to post or group orders for reporting.</span></span>
2.  <span data-ttu-id="c693e-150">**Grupy produkcji** — utwórz pule produkcji w celu pogrupowania zleceń produkcyjnych do przetwarzania pilnych zleceń produkcyjnych lub usunięcia i księgowania grup zleceń.</span><span class="sxs-lookup"><span data-stu-id="c693e-150">**Production pools** – Create production pools to group production orders so that you can process urgent production orders, or delete and post groups of orders.</span></span>
3.  <span data-ttu-id="c693e-151">**Właściwości** — zdefiniuj właściwości, aby utworzyć atrybuty specjalne, które można przypisać do zasobów w celu kontrolowania kolejnością produkcji.</span><span class="sxs-lookup"><span data-stu-id="c693e-151">**Properties** – Define properties to create special attributes that you can assign to your resources to control the order of productions.</span></span> <span data-ttu-id="c693e-152">Te atrybuty są powiązane z szablonem czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="c693e-152">These attributes are connected to the working time template.</span></span>





