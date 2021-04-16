---
title: Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów
description: Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cff10132e8007be885e9c69d97cf96c30d69f50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822862"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a><span data-ttu-id="64e45-103">Tworzenie i przypisywanie zasady alokacji kosztów do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="64e45-103">Create and assign a cost allocation policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="64e45-104">Ta procedura służy do tworzenia i przypisywania zasady alokacji kosztów wraz z odnośnymi regułami do jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="64e45-104">Use this procedure to create and assign a cost allocation policy and the corresponding rules to a cost control unit.</span></span> <span data-ttu-id="64e45-105">Nagranie wykorzystuje dane firmy demonstracyjnej USP2.</span><span class="sxs-lookup"><span data-stu-id="64e45-105">This recording uses the USP2 demo data company.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="64e45-106">Tworzenie zasady</span><span class="sxs-lookup"><span data-stu-id="64e45-106">Create a policy</span></span>
1. <span data-ttu-id="64e45-107">Wybierz kolejno opcje Rachunek kosztów > Zasady > Zasady alokacji kosztów.</span><span class="sxs-lookup"><span data-stu-id="64e45-107">Go to Cost accounting > Policies > Cost allocation policies.</span></span>
2. <span data-ttu-id="64e45-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="64e45-108">Click New.</span></span>
3. <span data-ttu-id="64e45-109">W polu Nazwa zasad wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="64e45-110">W polu Hierarchia wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-110">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="64e45-111">Wybierz opcję Organizacja.</span><span class="sxs-lookup"><span data-stu-id="64e45-111">Select Organization.</span></span>  
5. <span data-ttu-id="64e45-112">W polu Wymiar statystyczny wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-112">In the Statistical dimension field, enter or select a value.</span></span>
6. <span data-ttu-id="64e45-113">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="64e45-113">Click Save.</span></span>

## <a name="create-allocation-rules"></a><span data-ttu-id="64e45-114">Tworzenie reguł alokacji</span><span class="sxs-lookup"><span data-stu-id="64e45-114">Create allocation rules</span></span>
1. <span data-ttu-id="64e45-115">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="64e45-115">Click New.</span></span>
2. <span data-ttu-id="64e45-116">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="64e45-116">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="64e45-117">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-117">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
4. <span data-ttu-id="64e45-118">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="64e45-118">In the Cost behavior field, select 'Total'.</span></span>
5. <span data-ttu-id="64e45-119">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-119">In the Allocation base field, enter or select a value.</span></span>
6. <span data-ttu-id="64e45-120">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="64e45-120">Click New.</span></span>
7. <span data-ttu-id="64e45-121">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="64e45-121">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="64e45-122">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-122">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
9. <span data-ttu-id="64e45-123">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="64e45-123">In the Cost behavior field, select 'Total'.</span></span>
10. <span data-ttu-id="64e45-124">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-124">In the Allocation base field, enter or select a value.</span></span>
11. <span data-ttu-id="64e45-125">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="64e45-125">Click New.</span></span>
12. <span data-ttu-id="64e45-126">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="64e45-126">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="64e45-127">W polu Węzeł hierarchii wymiarów obiektów kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
14. <span data-ttu-id="64e45-128">W polu Zachowanie kosztów wybierz wartość „Suma”.</span><span class="sxs-lookup"><span data-stu-id="64e45-128">In the Cost behavior field, select 'Total'.</span></span>
15. <span data-ttu-id="64e45-129">W polu Podstawa alokacji wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-129">In the Allocation base field, enter or select a value.</span></span>
    * <span data-ttu-id="64e45-130">Kontynuuj, aż utworzysz wszystkie reguły.</span><span class="sxs-lookup"><span data-stu-id="64e45-130">Continue until you've created all the rules.</span></span>  
16. <span data-ttu-id="64e45-131">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="64e45-131">Click Save.</span></span>

## <a name="assign-the-policy-to-a-cost-control-unit"></a><span data-ttu-id="64e45-132">Przypisywanie zasady do jednostki kontroli kosztów</span><span class="sxs-lookup"><span data-stu-id="64e45-132">Assign the policy to a cost control unit</span></span>
1. <span data-ttu-id="64e45-133">Kliknij opcję Przypisania zasad dla jednostki kontroli kosztów.</span><span class="sxs-lookup"><span data-stu-id="64e45-133">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="64e45-134">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="64e45-134">Click New.</span></span>
3. <span data-ttu-id="64e45-135">Na liście oznacz wybrany wiersz.</span><span class="sxs-lookup"><span data-stu-id="64e45-135">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="64e45-136">W polu Ważne od daty księgowania wpisz datę.</span><span class="sxs-lookup"><span data-stu-id="64e45-136">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="64e45-137">Reguły mają daty obowiązywania.</span><span class="sxs-lookup"><span data-stu-id="64e45-137">The rules are date-effective.</span></span> <span data-ttu-id="64e45-138">Użytkownik lub system może wygasić regułę, jeśli zostanie utworzona nowsza wersja.</span><span class="sxs-lookup"><span data-stu-id="64e45-138">A user or the system can expire the rules if a newer version is created.</span></span>  
5. <span data-ttu-id="64e45-139">W polu Jednostka kontroli kosztów wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="64e45-139">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="64e45-140">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="64e45-140">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]