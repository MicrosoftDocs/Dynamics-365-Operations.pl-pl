--- 
title: "Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów"
description: "Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ff9b4ddeecfdb795c1eead0e9e2100c307f63db4
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="fa80d-103">Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="fa80d-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fa80d-104">Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="fa80d-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="fa80d-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="fa80d-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="fa80d-106">Tworzenie zasady</span><span class="sxs-lookup"><span data-stu-id="fa80d-106">Create a policy</span></span>
1. <span data-ttu-id="fa80d-107">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="fa80d-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="fa80d-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="fa80d-108">Click New.</span></span>
3. <span data-ttu-id="fa80d-109">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="fa80d-110">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="fa80d-111">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="fa80d-111">Select Organization.</span></span>  
5. <span data-ttu-id="fa80d-112">W polu Wymiar statystyczny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="fa80d-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="fa80d-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="fa80d-114">Tworzenie reguł alokacji</span><span class="sxs-lookup"><span data-stu-id="fa80d-114">Create allocation rules</span></span>
1. <span data-ttu-id="fa80d-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="fa80d-115">Click New.</span></span>
2. <span data-ttu-id="fa80d-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="fa80d-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="fa80d-117">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="fa80d-118">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="fa80d-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="fa80d-119">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="fa80d-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="fa80d-120">Click New.</span></span>
7. <span data-ttu-id="fa80d-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="fa80d-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="fa80d-122">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="fa80d-123">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="fa80d-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="fa80d-124">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="fa80d-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="fa80d-125">Click New.</span></span>
12. <span data-ttu-id="fa80d-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="fa80d-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="fa80d-127">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="fa80d-128">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="fa80d-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="fa80d-129">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="fa80d-130">Kontynuuj, aż utworzysz wszystkie reguły.</span><span class="sxs-lookup"><span data-stu-id="fa80d-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="fa80d-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="fa80d-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="fa80d-132">Przypisywanie zasady do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="fa80d-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="fa80d-133">Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="fa80d-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="fa80d-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="fa80d-134">Click New.</span></span>
3. <span data-ttu-id="fa80d-135">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="fa80d-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="fa80d-136">W polu Ważne od daty księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="fa80d-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="fa80d-137">Reguły mają daty obowiązywania.</span><span class="sxs-lookup"><span data-stu-id="fa80d-137">The rules are date-effective.</span></span> <span data-ttu-id="fa80d-138">Użytkownik lub system może wygasić regułę, jeśli zostanie utworzona nowsza wersja.</span><span class="sxs-lookup"><span data-stu-id="fa80d-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="fa80d-139">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="fa80d-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="fa80d-140">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="fa80d-140">Click Save.</span></span>


