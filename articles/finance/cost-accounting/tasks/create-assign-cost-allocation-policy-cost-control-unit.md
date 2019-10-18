---
title: Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów
description: Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f0422a9aaf95184b556293bf6ebcaf4dcfb5b59
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179410"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="ea02a-103">Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="ea02a-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ea02a-104">Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="ea02a-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="ea02a-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="ea02a-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="ea02a-106">Tworzenie zasady</span><span class="sxs-lookup"><span data-stu-id="ea02a-106">Create a policy</span></span>
1. <span data-ttu-id="ea02a-107">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="ea02a-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="ea02a-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea02a-108">Click New.</span></span>
3. <span data-ttu-id="ea02a-109">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="ea02a-110">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="ea02a-111">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="ea02a-111">Select Organization.</span></span>  
5. <span data-ttu-id="ea02a-112">W polu Wymiar statystyczny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="ea02a-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ea02a-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="ea02a-114">Tworzenie reguł alokacji</span><span class="sxs-lookup"><span data-stu-id="ea02a-114">Create allocation rules</span></span>
1. <span data-ttu-id="ea02a-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea02a-115">Click New.</span></span>
2. <span data-ttu-id="ea02a-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea02a-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="ea02a-117">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="ea02a-118">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="ea02a-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="ea02a-119">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="ea02a-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea02a-120">Click New.</span></span>
7. <span data-ttu-id="ea02a-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea02a-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="ea02a-122">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="ea02a-123">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="ea02a-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="ea02a-124">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="ea02a-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea02a-125">Click New.</span></span>
12. <span data-ttu-id="ea02a-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea02a-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="ea02a-127">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="ea02a-128">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="ea02a-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="ea02a-129">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="ea02a-130">Kontynuuj, aż utworzysz wszystkie reguły.</span><span class="sxs-lookup"><span data-stu-id="ea02a-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="ea02a-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ea02a-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="ea02a-132">Przypisywanie zasady do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="ea02a-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="ea02a-133">Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="ea02a-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="ea02a-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ea02a-134">Click New.</span></span>
3. <span data-ttu-id="ea02a-135">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="ea02a-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ea02a-136">W polu Ważne od daty księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="ea02a-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="ea02a-137">Reguły mają daty obowiązywania.</span><span class="sxs-lookup"><span data-stu-id="ea02a-137">The rules are date-effective.</span></span> <span data-ttu-id="ea02a-138">Użytkownik lub system może wygasić regułę, jeśli zostanie utworzona nowsza wersja.</span><span class="sxs-lookup"><span data-stu-id="ea02a-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="ea02a-139">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ea02a-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="ea02a-140">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ea02a-140">Click Save.</span></span>

