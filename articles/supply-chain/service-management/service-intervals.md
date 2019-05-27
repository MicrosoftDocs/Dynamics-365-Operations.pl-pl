---
title: Zakresy serwisów
description: Interwał serwisu określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej podczas tworzenia zleceń serwisowych.
author: ShylaThompson
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 10078cbd02209126e9655b823fcf844b692a4794
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562656"
---
# <a name="service-intervals"></a><span data-ttu-id="f90f2-103">Zakresy serwisów</span><span class="sxs-lookup"><span data-stu-id="f90f2-103">Service intervals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f90f2-104">Interwał umowy serwisowej określa częstotliwość, z jaką są tworzone wiersze umowy serwisowej podczas automatycznego tworzenia zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="f90f2-104">The service agreement interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders automatically.</span></span>

<span data-ttu-id="f90f2-105">Jeśli zlecenia serwisowe są tworzone automatycznie, wiersze zlecenia serwisowego są tworzone zgodnie z interwałem określonym dla wiersza umowy serwisowej według daty początkowej tego wiersza.</span><span class="sxs-lookup"><span data-stu-id="f90f2-105">When you create service orders automatically, service order lines are created according to the interval that you have specified for the service agreement line from the start date of the agreement line.</span></span>

<span data-ttu-id="f90f2-106">Jeśli pole **Interwał** wiersza umowy serwisowej na stronie **Umowy serwisowe** jest puste, wiersz określa zdarzenie jednorazowe i nie będzie używany do wielokrotnego tworzenia zleceń serwisowych.</span><span class="sxs-lookup"><span data-stu-id="f90f2-106">If the **Interval** field of a service agreement line in the **Service agreements** page is blank, the line is a one-time event, and it is not used to create service orders repeatedly.</span></span>

## <a name="example"></a><span data-ttu-id="f90f2-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="f90f2-107">Example</span></span>

<span data-ttu-id="f90f2-108">Ten przykład ilustruje wpływ ram czasowych serwisu na wiersze umowy serwisowej i wiersze zlecenia serwisowego w zleceniu serwisowym.</span><span class="sxs-lookup"><span data-stu-id="f90f2-108">This example illustrates how a service interval will affect service agreement lines and service order lines on a service order.</span></span>

### <a name="create-a-service-agreement"></a><span data-ttu-id="f90f2-109">Tworzenie umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="f90f2-109">Create a service agreement</span></span>

<span data-ttu-id="f90f2-110">Najpierw należy utworzyć umowę serwisową i ustawić w opcji **Łączenie zleceń serwisowych** wartość **Według umowy serwisowej**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-110">First, you create a service agreement and set the **Combine service orders** option to **By service agreement**.</span></span>

1. <span data-ttu-id="f90f2-111">Kliknij opcję **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-111">Click **Service agreements**</span></span>
2. <span data-ttu-id="f90f2-112">W **okienku akcji** na karcie **Umowa serwisowa** w grupie **Nowy** kliknij opcję **Umowa serwisowa**, aby utworzyć nową umowę serwisową.</span><span class="sxs-lookup"><span data-stu-id="f90f2-112">On the **Action Pane**, on the **Service agreement** tab, in the **New** group, click **Service agreement** to create a new service agreement.</span></span>
3. <span data-ttu-id="f90f2-113">Wprowadź opis, w polu **Identyfikator projektu** zaznacz projekt, a w polu **Data rozpoczęcia** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="f90f2-113">Enter a description, select a project in the **Project ID** field, and enter a date in the **Start date** field.</span></span>
4. <span data-ttu-id="f90f2-114">W polu **Łączenie zleceń serwisowych** zaznacz opcje **Według umowy serwisowej**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-114">In the **Combine service orders** field, select **By service agreement**.</span></span>

<span data-ttu-id="f90f2-115">Utworzona została następująca umowa serwisowa:</span><span class="sxs-lookup"><span data-stu-id="f90f2-115">You have now created the following service agreement:</span></span>

| <span data-ttu-id="f90f2-116">Project</span><span class="sxs-lookup"><span data-stu-id="f90f2-116">Project</span></span>      | <span data-ttu-id="f90f2-117">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="f90f2-117">Start date</span></span>                                                                         |
|--------------|------------------------------------------------------------------------------------|
| <span data-ttu-id="f90f2-118">Projekt</span><span class="sxs-lookup"><span data-stu-id="f90f2-118">Your project</span></span> | <span data-ttu-id="f90f2-119">Data określona dla projektu.</span><span class="sxs-lookup"><span data-stu-id="f90f2-119">The date you specified for the project.</span></span> <span data-ttu-id="f90f2-120">W tym przykładzie jest używana bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="f90f2-120">In this example, the current date is used.</span></span> |

### <a name="create-a-service-agreement-line"></a><span data-ttu-id="f90f2-121">Tworzenie wiersza umowy serwisowej</span><span class="sxs-lookup"><span data-stu-id="f90f2-121">Create a service agreement line</span></span>

<span data-ttu-id="f90f2-122">Następnie tworzony jest wiersz umowy serwisowej z typem transakcji **Godzina**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-122">Next, you create a service agreement line that has the transaction type **Hour**.</span></span>

<span data-ttu-id="f90f2-123">Aby zakończyć tę część przykładu, należy na stronie **Ramy czasowe serwisów** utworzyć interwał serwisowy wynoszący 10 dni.</span><span class="sxs-lookup"><span data-stu-id="f90f2-123">To complete this part of the example, you must create a service interval of 10 days in the **Service intervals** page.</span></span> 

1. <span data-ttu-id="f90f2-124">Zaznacz umowę serwisową, która właśnie została utworzona.</span><span class="sxs-lookup"><span data-stu-id="f90f2-124">Select the service agreement that you just created.</span></span> 
2. <span data-ttu-id="f90f2-125">Na skróconej karcie **Wiersze** kliknij przycisk **Dodaj**, aby utworzyć nowy wiersz w dolnym okienku strony **Umowy serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-125">On the **Lines** FastTab, click the **Add** button to create a new line in the lower pane of the **Service agreements** page.</span></span>
3. <span data-ttu-id="f90f2-126">W polu **Typ transakcji** wybierz opcję **Godzina**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-126">In the **Transaction type** field, select **Hour**.</span></span>
4. <span data-ttu-id="f90f2-127">W polu **Pracownik** zaznacz pracownika, który wykona prace serwisowe.</span><span class="sxs-lookup"><span data-stu-id="f90f2-127">In the **Worker** field, select the worker who will deliver the service.</span></span>
5. <span data-ttu-id="f90f2-128">W polu **Ramy czasowe serwisu** wybierz interwał wynoszący 10 dni.</span><span class="sxs-lookup"><span data-stu-id="f90f2-128">In the **Service interval** field, select the 10 days interval.</span></span>

<span data-ttu-id="f90f2-129">Został utworzony wiersz umowy serwisowej z następującymi informacjami:</span><span class="sxs-lookup"><span data-stu-id="f90f2-129">You have now created a service agreement line with the following information:</span></span>

| <span data-ttu-id="f90f2-130">Typ transakcji</span><span class="sxs-lookup"><span data-stu-id="f90f2-130">Transaction type</span></span> | <span data-ttu-id="f90f2-131">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="f90f2-131">Start date</span></span>                               | <span data-ttu-id="f90f2-132">Zakres usług</span><span class="sxs-lookup"><span data-stu-id="f90f2-132">Service interval</span></span> |
|------------------|------------------------------------------|------------------|
| <span data-ttu-id="f90f2-133">Godzina</span><span class="sxs-lookup"><span data-stu-id="f90f2-133">Hour</span></span>             | <span data-ttu-id="f90f2-134">Bieżąca data.</span><span class="sxs-lookup"><span data-stu-id="f90f2-134">The current date.</span></span>                        | <span data-ttu-id="f90f2-135">Co 10 dni</span><span class="sxs-lookup"><span data-stu-id="f90f2-135">Every 10 days</span></span>    |
| <span data-ttu-id="f90f2-136">Pracownik</span><span class="sxs-lookup"><span data-stu-id="f90f2-136">Worker</span></span>           | <span data-ttu-id="f90f2-137">Pracownik, który wykona serwis.</span><span class="sxs-lookup"><span data-stu-id="f90f2-137">The worker who will perform the service.</span></span> |                  |

<span data-ttu-id="f90f2-138">Dla tego wiersza nie zostało określone okno czasu.</span><span class="sxs-lookup"><span data-stu-id="f90f2-138">There is no time window specified for the line.</span></span> 

### <a name="create-planned-service-orders"></a><span data-ttu-id="f90f2-139">Tworzenie planowanych zleceń serwisowych</span><span class="sxs-lookup"><span data-stu-id="f90f2-139">Create planned service orders</span></span>

<span data-ttu-id="f90f2-140">Teraz można utworzyć planowane zlecenia serwisowe i wiersze zleceń serwisowych na nadchodzący miesiąc.</span><span class="sxs-lookup"><span data-stu-id="f90f2-140">You can now create planned service orders and service order lines for the coming month.</span></span>

1. <span data-ttu-id="f90f2-141">Na stronie **Umowy serwisowe** w **okienku akcji** na karcie **Dostarcz** kliknij opcję **Planowane zlecenia serwisowe**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-141">In the **Service agreements** page, on the **Action Pane**, on the **Deliver** tab, click **Planned service orders**.</span></span>
2. <span data-ttu-id="f90f2-142">Na stronie **Tworzenie zleceń serwisowych** wprowadź bieżącą datę w polu **Od dnia** oraz datę jeden miesiąc w przód od bieżącej daty w polu **Do dnia**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-142">In the **Create service orders** page, enter the current date in the **From date** field and a date that is one month from the current date in the **To date** field.</span></span>
3. <span data-ttu-id="f90f2-143">Ustaw suwak **Godzina** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-143">Set the **Hour** slider to **Yes**.</span></span> 
4. <span data-ttu-id="f90f2-144">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-144">Click **OK**.</span></span>

<span data-ttu-id="f90f2-145">Ponieważ grupowanie w zleceniu serwisowym nie zostało określone (co umożliwia opcja **Według umowy serwisowej** w polu **Łączenie zleceń serwisowych**), tworzony jest jeden wiersz zlecenia serwisowego na każde zlecenie serwisowe.</span><span class="sxs-lookup"><span data-stu-id="f90f2-145">Because there is no grouping on the service order (defined by the **By service agreement** option in the **Combine service orders** field), one service order line is created per service order.</span></span>

### <a name="service-orders-created"></a><span data-ttu-id="f90f2-146">Utworzone zlecenia serwisowe</span><span class="sxs-lookup"><span data-stu-id="f90f2-146">Service orders created</span></span>

<span data-ttu-id="f90f2-147">Zostały utworzone trzy wiersze zlecenia serwisowego w ramach czasowych określonych w oknie dialogowym **Tworzenie zleceń serwisowych**.</span><span class="sxs-lookup"><span data-stu-id="f90f2-147">Three service order lines have been created within the time frame that you specified in the **Create service orders** dialog box.</span></span> <span data-ttu-id="f90f2-148">Możesz przejrzeć wiersze zlecenia serwisowego na stronie **Umowy serwisowe** (**okienko akcji** \> karta **Dostarcz** przycisk \>**Widok**).</span><span class="sxs-lookup"><span data-stu-id="f90f2-148">You can view the service order lines in the **Service agreements** page (**Action Pane** \> **Deliver** tab \>**View** button).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f90f2-149">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="f90f2-149">Related topics</span></span>

[<span data-ttu-id="f90f2-150">Konfigurowanie ram czasowych serwisu</span><span class="sxs-lookup"><span data-stu-id="f90f2-150">Set up service intervals</span></span>](set-up-service-intervals.md)  

