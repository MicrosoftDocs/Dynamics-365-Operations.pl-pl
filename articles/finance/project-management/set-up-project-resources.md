---
title: Konfigurowanie zasobów projektu
description: Ten temat zawiera informacje dotyczące konfigurowania lub występowania o zasoby projektu.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760638"
---
# <a name="set-up-project-resources"></a><span data-ttu-id="ae071-103">Konfigurowanie zasobów projektu</span><span class="sxs-lookup"><span data-stu-id="ae071-103">Set up project resources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae071-104">Należy utworzyć kalendarz i skojarzyć go z pracownikiem.</span><span class="sxs-lookup"><span data-stu-id="ae071-104">You must set up a calendar and associate it with an employee or a worker.</span></span> <span data-ttu-id="ae071-105">Kalendarz jest używany do planowania projektu i czasu pracy zasobów, które są zarezerwowane dla projektu.</span><span class="sxs-lookup"><span data-stu-id="ae071-105">The calendar is used to schedule the project and the working time of the resources that are reserved for the project.</span></span> <span data-ttu-id="ae071-106">Podczas konfigurowania kalendarza kierownicy projektu wykonują bilansowanie zasobów jako część procesu optymalizacji zasobów.</span><span class="sxs-lookup"><span data-stu-id="ae071-106">During calendar setup, project managers can do resource leveling as part of resource optimization.</span></span> <span data-ttu-id="ae071-107">Na podstawie harmonogramu w kalendarzu można nakładać ograniczenia na zasoby.</span><span class="sxs-lookup"><span data-stu-id="ae071-107">Based on the calendar schedule, restrictions can be put on resources.</span></span> <span data-ttu-id="ae071-108">Kalendarz można zdefiniować na stronie **Kalendarze**.</span><span class="sxs-lookup"><span data-stu-id="ae071-108">You can set up a calendar on the **Calendars** page.</span></span>

<span data-ttu-id="ae071-109">Po skonfigurowaniu pracownika jako zasobu projektu można wybrać spośród pracowników, którzy pracują w firmie, dla której konfigurowane są zasoby.</span><span class="sxs-lookup"><span data-stu-id="ae071-109">When you set up a worker as a project resource, you can select from workers who work in the company that you're setting up resources for.</span></span> <span data-ttu-id="ae071-110">Można także wybrać pracowników z innych firm w organizacji.</span><span class="sxs-lookup"><span data-stu-id="ae071-110">Alternatively, you can select workers from other companies in your organization.</span></span> <span data-ttu-id="ae071-111">Ci pracownicy są określani jako zasoby międzyfirmowe.</span><span class="sxs-lookup"><span data-stu-id="ae071-111">These workers are known as intercompany resources.</span></span>

<span data-ttu-id="ae071-112">W poniższych procedurach opisano, jak skonfigurować pracownika jako zasób projektu w swojej firmie i jak skonfigurować międzyfirmowy zasób projektu.</span><span class="sxs-lookup"><span data-stu-id="ae071-112">The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.</span></span>

## <a name="set-up-a-worker-as-a-project-resource"></a><span data-ttu-id="ae071-113">Konfigurowanie pracownika jako zasobu projektu</span><span class="sxs-lookup"><span data-stu-id="ae071-113">Set up a worker as a project resource</span></span>

1. <span data-ttu-id="ae071-114">Na stronie **Pracownicy** na liście **Pracownicy** wybierz pracownika, którego chcesz dodać jako zasób projektu, i otwórz rekord tego pracownika.</span><span class="sxs-lookup"><span data-stu-id="ae071-114">On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.</span></span>
2. <span data-ttu-id="ae071-115">W okienku akcji wybierz kolejno opcje **Projekt** &gt; **Ustawienia** &gt; **Ustawienia projektu**.</span><span class="sxs-lookup"><span data-stu-id="ae071-115">On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.</span></span>
3. <span data-ttu-id="ae071-116">Wybierz kalendarz, a następnie zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="ae071-116">Select a calendar, and then close the page.</span></span>

<span data-ttu-id="ae071-117">Można również określić domyślne projekty dla zasobu jako rodzaj wstępnego przypisania.</span><span class="sxs-lookup"><span data-stu-id="ae071-117">You can also specify default projects for a resource as a type of pre-assignment.</span></span> <span data-ttu-id="ae071-118">Wstępnych przypisań można używać, gdy menedżer zasobów lub kierownik projektu wie z wyprzedzeniem, w których projektach zasób będzie pracował.</span><span class="sxs-lookup"><span data-stu-id="ae071-118">Pre-assignments can be used when the resource manager or project manager knows which projects the resource will be working on in advance.</span></span> <span data-ttu-id="ae071-119">Wstępne przypisania mogą być również oparte na wniosku inwestora projektu lub klienta.</span><span class="sxs-lookup"><span data-stu-id="ae071-119">Pre-assignments can also be based on the request of a project sponsor or customer.</span></span> <span data-ttu-id="ae071-120">Aby wstępnie przypisać projekt, na stronie **Przypisz projekty** na karcie **Projekty** na liście **Pozostałe projekty** wybierz odpowiedni projekt.</span><span class="sxs-lookup"><span data-stu-id="ae071-120">To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.</span></span>

## <a name="set-up-an-intercompany-resource"></a><span data-ttu-id="ae071-121">Konfigurowanie zasobu międzyfirmowego</span><span class="sxs-lookup"><span data-stu-id="ae071-121">Set up an intercompany resource</span></span>

<span data-ttu-id="ae071-122">Podczas konfigurowania pracownika jako zasobu międzyfirmowego należy wypełnić pola konfiguracji w firmach wypożyczającej i pożyczającej.</span><span class="sxs-lookup"><span data-stu-id="ae071-122">When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.</span></span>

### <a name="in-the-lending-company"></a><span data-ttu-id="ae071-123">W firmie wypożyczającej</span><span class="sxs-lookup"><span data-stu-id="ae071-123">In the lending company</span></span>

1. <span data-ttu-id="ae071-124">W usłudze Finance upewnij się, że firma wypożyczająca jest wybrana, a następnie wykonaj procedurę z poprzedniej sekcji „Konfigurowanie pracownika jako zasobu projektu”.</span><span class="sxs-lookup"><span data-stu-id="ae071-124">In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."</span></span>
2. <span data-ttu-id="ae071-125">Na stronie **Księgowanie międzyfirmowe** wybierz opcję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="ae071-125">On the **Intercompany accounting** page, select **New**.</span></span>
3. <span data-ttu-id="ae071-126">W polu **Identyfikator firmy** wybierz firmę wypożyczającą.</span><span class="sxs-lookup"><span data-stu-id="ae071-126">In the **Legal entity ID** field, select the lending company.</span></span> <span data-ttu-id="ae071-127">Wypełnij pozostałe pola, a następnie wybierz przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="ae071-127">Fill in the remaining fields as appropriate, and then select **Save**.</span></span>
4. <span data-ttu-id="ae071-128">Na stronie **Cena transferowa** wybierz opcję **Nowa**.</span><span class="sxs-lookup"><span data-stu-id="ae071-128">On the **Transfer price** page, select **New**.</span></span>
5. <span data-ttu-id="ae071-129">W polu **Firma pożyczająca** wybierz odpowiednią firmę.</span><span class="sxs-lookup"><span data-stu-id="ae071-129">In the **Borrowing legal entity** field, select the appropriate company.</span></span>
6. <span data-ttu-id="ae071-130">Aby wypożyczyć firmie pożyczającej tylko zasób utworzony na początku niniejszej sekcji, w polu **Zasób** zaznacz nazwę utworzonego zasobu.</span><span class="sxs-lookup"><span data-stu-id="ae071-130">To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created.</span></span> <span data-ttu-id="ae071-131">Aby udostępnić firmie pożyczającej wszystkie zasoby firmy wypożyczającej, zostaw pole **Zasób** puste.</span><span class="sxs-lookup"><span data-stu-id="ae071-131">To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.</span></span>
7. <span data-ttu-id="ae071-132">Na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** na stronie **Międzyfirmowe** ustaw w polu **Włącz międzyfirmowe planowanie zasobów i kart czasu pracy** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="ae071-132">On the **Project management and accounting parameters** page, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.</span></span>

### <a name="in-the-borrowing-company"></a><span data-ttu-id="ae071-133">W firmie pożyczającej</span><span class="sxs-lookup"><span data-stu-id="ae071-133">In the borrowing company</span></span>

- <span data-ttu-id="ae071-134">Na stronie **Lista zasobów**, w filtrze wyszukiwania wprowadź nazwę zasobu, który został utworzony dla firmy wypożyczającej, aby sprawdzić, czy nazwa znajduje się na liście zasobów dla firmy pożyczającej.</span><span class="sxs-lookup"><span data-stu-id="ae071-134">On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.</span></span>

## <a name="request-project-resources"></a><span data-ttu-id="ae071-135">Wnioskowanie o zasoby projektu</span><span class="sxs-lookup"><span data-stu-id="ae071-135">Request project resources</span></span>
<span data-ttu-id="ae071-136">Funkcja planowania zasobów projektu tylko pozwala menedżerom zasobów rozdzielać zasoby pracowników w projektach.</span><span class="sxs-lookup"><span data-stu-id="ae071-136">The functionality for project resource scheduling only lets resource managers distribute staffed resources on engagements or projects.</span></span> <span data-ttu-id="ae071-137">Aby włączyć tę funkcję, należy wykonać następujące zadania lub upewnić się, że zostały one wykonane:</span><span class="sxs-lookup"><span data-stu-id="ae071-137">To enable this functionality, complete the following tasks, or verify that they have been completed:</span></span>

- <span data-ttu-id="ae071-138">Ustaw sekwencje numerów.</span><span class="sxs-lookup"><span data-stu-id="ae071-138">Set up number sequences.</span></span>
- <span data-ttu-id="ae071-139">Ustawianie przepływów pracy dla zarządzania projektami i ich księgowania.</span><span class="sxs-lookup"><span data-stu-id="ae071-139">Set up project management and accounting workflows.</span></span>
- <span data-ttu-id="ae071-140">Włącz przepływy pracy żądań zasobów</span><span class="sxs-lookup"><span data-stu-id="ae071-140">Enable resource request workflows.</span></span>

<span data-ttu-id="ae071-141">Po wykonaniu poprzedniego zadania można wykonać następujące zadania według potrzeb:</span><span class="sxs-lookup"><span data-stu-id="ae071-141">After the preceding tasks have been completed, you can complete the following tasks as you require:</span></span>

- <span data-ttu-id="ae071-142">Tworzenie wniosku o zasób w odniesieniu do zasobu pracownika z rezerwacją wstępną.</span><span class="sxs-lookup"><span data-stu-id="ae071-142">Create a resource request from a soft-booked staffed resource.</span></span>
- <span data-ttu-id="ae071-143">Monitorowanie wniosków o zasoby.</span><span class="sxs-lookup"><span data-stu-id="ae071-143">Monitor resource requests.</span></span>
- <span data-ttu-id="ae071-144">Realizacja wniosków o zasoby.</span><span class="sxs-lookup"><span data-stu-id="ae071-144">Fulfill resource requests.</span></span>
- <span data-ttu-id="ae071-145">Wnioskowanie o zasób pracownika z SPP.</span><span class="sxs-lookup"><span data-stu-id="ae071-145">Request a staffed resource from a WBS.</span></span>
- <span data-ttu-id="ae071-146">Rezerwowanie zasobów do projektu bez wnioskowania o zasób pracownika.</span><span class="sxs-lookup"><span data-stu-id="ae071-146">Book resources to a project without having a request for a staffed resource.</span></span>
