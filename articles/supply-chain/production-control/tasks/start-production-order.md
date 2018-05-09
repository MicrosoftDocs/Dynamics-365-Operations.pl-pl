---
title: Rozpoczynanie zlecenia produkcyjnego
description: "Ta procedura pokazuje sposób rozpoczynania zlecenia produkcyjnego na wydziale produkcji."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 933bf83613f30b544a9cc8e55ad4e32305522b3d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---
# <a name="start-a-production-order"></a><span data-ttu-id="1dbba-103">Rozpoczynanie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="1dbba-103">Start a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1dbba-104">Ta procedura pokazuje sposób rozpoczynania zlecenia produkcyjnego na wydziale produkcji.</span><span class="sxs-lookup"><span data-stu-id="1dbba-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="1dbba-105">W tym procesie jest zgłaszane zużycie materiału i czasu.</span><span class="sxs-lookup"><span data-stu-id="1dbba-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="1dbba-106">Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.</span><span class="sxs-lookup"><span data-stu-id="1dbba-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1dbba-107">Jest to piąta z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="1dbba-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="1dbba-108">Rozpoczynanie zlecenia produkcyjnego</span><span class="sxs-lookup"><span data-stu-id="1dbba-108">Start a production order</span></span>
1. <span data-ttu-id="1dbba-109">Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="1dbba-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="1dbba-110">Zaznacz zlecenie produkcyjne, które ma stan Zwolniono.</span><span class="sxs-lookup"><span data-stu-id="1dbba-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="1dbba-111">W okienku akcji kliknij opcję Zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="1dbba-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="1dbba-112">Kliknij przycisk Rozpocznij.</span><span class="sxs-lookup"><span data-stu-id="1dbba-112">Click Start.</span></span>
    * <span data-ttu-id="1dbba-113">Na tej stronie można potwierdzić rozpoczęcie zlecenia produkcyjnego.</span><span class="sxs-lookup"><span data-stu-id="1dbba-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="1dbba-114">Kliknij kartę Ogólne.</span><span class="sxs-lookup"><span data-stu-id="1dbba-114">Click the General tab.</span></span>
5. <span data-ttu-id="1dbba-115">W polu Od nr operacji</span><span class="sxs-lookup"><span data-stu-id="1dbba-115">In the From Oper.</span></span> <span data-ttu-id="1dbba-116">Nr</span><span class="sxs-lookup"><span data-stu-id="1dbba-116">No.</span></span> <span data-ttu-id="1dbba-117">wpisz „10”.</span><span class="sxs-lookup"><span data-stu-id="1dbba-117">field, enter '10'.</span></span>
6. <span data-ttu-id="1dbba-118">W polu Automatyczne zużycie marszruty zaznacz opcję „Zawsze”.</span><span class="sxs-lookup"><span data-stu-id="1dbba-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="1dbba-119">Zaznacz pole wyboru Księguj kartę marszruty teraz.</span><span class="sxs-lookup"><span data-stu-id="1dbba-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="1dbba-120">W polu Automatyczne zużycie BOM zaznacz opcję „Zawsze”.</span><span class="sxs-lookup"><span data-stu-id="1dbba-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="1dbba-121">Zaznacz pole wyboru Księgowanie listy pobrania.</span><span class="sxs-lookup"><span data-stu-id="1dbba-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="1dbba-122">Zaznacz pole wyboru Drukowanie listy pobrania.</span><span class="sxs-lookup"><span data-stu-id="1dbba-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="1dbba-123">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dbba-123">Click OK.</span></span>
    * <span data-ttu-id="1dbba-124">Jest to wydrukowana lista pobrania, która pokazuje materiały użyte w zleceniu produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="1dbba-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="1dbba-125">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1dbba-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="1dbba-126">Sprawdzanie poprawności listy pobrania</span><span class="sxs-lookup"><span data-stu-id="1dbba-126">Validate the picking list</span></span>
1. <span data-ttu-id="1dbba-127">W okienku akcji kliknij pozycję Widok.</span><span class="sxs-lookup"><span data-stu-id="1dbba-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="1dbba-128">Kliknij opcję Lista pobrania.</span><span class="sxs-lookup"><span data-stu-id="1dbba-128">Click Picking list.</span></span>
3. <span data-ttu-id="1dbba-129">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1dbba-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1dbba-130">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1dbba-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="1dbba-131">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="1dbba-131">Click Edit.</span></span>
6. <span data-ttu-id="1dbba-132">W polu Zużycie wprowadź liczbę.</span><span class="sxs-lookup"><span data-stu-id="1dbba-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="1dbba-133">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="1dbba-133">Click Post.</span></span>
8. <span data-ttu-id="1dbba-134">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dbba-134">Click OK.</span></span>
    * <span data-ttu-id="1dbba-135">W arkuszu listy pobrania są księgowane materiały zużyte przez zlecenie produkcyjne.</span><span class="sxs-lookup"><span data-stu-id="1dbba-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="1dbba-136">Przed zaksięgowaniem arkusza można dokonać korekt, jeśli występuje różnica między oszacowaną ilością a rzeczywiście zużytą ilością.</span><span class="sxs-lookup"><span data-stu-id="1dbba-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="1dbba-137">Kliknij kartę GridPanel.</span><span class="sxs-lookup"><span data-stu-id="1dbba-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="1dbba-138">Zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="1dbba-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="1dbba-139">Weryfikacja arkusza karty marszruty</span><span class="sxs-lookup"><span data-stu-id="1dbba-139">Verify the route card journal</span></span>
1. <span data-ttu-id="1dbba-140">W okienku akcji kliknij pozycję Widok.</span><span class="sxs-lookup"><span data-stu-id="1dbba-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="1dbba-141">Kliknij opcję Karta marszruty.</span><span class="sxs-lookup"><span data-stu-id="1dbba-141">Click Route card.</span></span>
3. <span data-ttu-id="1dbba-142">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="1dbba-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="1dbba-143">Na liście kliknij łącze w wybranym wierszu.</span><span class="sxs-lookup"><span data-stu-id="1dbba-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="1dbba-144">Kliknij przycisk Edytuj.</span><span class="sxs-lookup"><span data-stu-id="1dbba-144">Click Edit.</span></span>
6. <span data-ttu-id="1dbba-145">W polu Godziny wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="1dbba-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="1dbba-146">Kliknij przycisk Księguj.</span><span class="sxs-lookup"><span data-stu-id="1dbba-146">Click Post.</span></span>
8. <span data-ttu-id="1dbba-147">Kliknij przycisk OK.</span><span class="sxs-lookup"><span data-stu-id="1dbba-147">Click OK.</span></span>
    * <span data-ttu-id="1dbba-148">W arkuszu karty marszruty jest rejestrowany czas spędzony na poszczególnych operacjach.</span><span class="sxs-lookup"><span data-stu-id="1dbba-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="1dbba-149">Mogą być również podawane ilości towarów prawidłowych i błędnych.</span><span class="sxs-lookup"><span data-stu-id="1dbba-149">Good and error quantity can also be reported.</span></span>  

