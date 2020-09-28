---
title: Utwórz nowy projekt
description: Ten temat zawiera informacje o metodach tworzenia nowego projektu.
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
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760633"
---
# <a name="create-a-new-project"></a><span data-ttu-id="3fc89-103">Utwórz nowy projekt</span><span class="sxs-lookup"><span data-stu-id="3fc89-103">Create a new project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3fc89-104">Aby utworzyć nowy projekt należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3fc89-104">Complete the following steps to create a new project.</span></span>

1. <span data-ttu-id="3fc89-105">Na stronie **Zarządzanie projektem** wybierz opcję **Nowy projekt** i wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="3fc89-105">On the **Project management** page, select **New project**, and enter the following values:</span></span>

    - <span data-ttu-id="3fc89-106">**Typ projektu:** Czas i materiały</span><span class="sxs-lookup"><span data-stu-id="3fc89-106">**Project type:** Time and material</span></span>
    - <span data-ttu-id="3fc89-107">**Nazwa projektu:** Uaktualnianie XYZ faza 2</span><span class="sxs-lookup"><span data-stu-id="3fc89-107">**Project name:** XYZ Upgrade Phase 2</span></span>
    - <span data-ttu-id="3fc89-108">**Grupa projektów:** TM\_WIP</span><span class="sxs-lookup"><span data-stu-id="3fc89-108">**Project group:** TM\_WIP</span></span>
    - <span data-ttu-id="3fc89-109">**Identyfikator umowy dotyczącej projektu:** 00000002</span><span class="sxs-lookup"><span data-stu-id="3fc89-109">**Project contract ID:** 00000002</span></span>

2. <span data-ttu-id="3fc89-110">Wybierz opcję **Utwórz projekt**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-110">Select **Create project**.</span></span>

## <a name="assign-a-resource-to-a-project"></a><span data-ttu-id="3fc89-111">Przypisywanie zasobu do projektu</span><span class="sxs-lookup"><span data-stu-id="3fc89-111">Assign a resource to a project</span></span>

1. <span data-ttu-id="3fc89-112">Na stronie **Pracownicy** na liście **Pracownicy** wybierz rekord pracownika, dla którego skonfigurowano wcześniej kompetencje, i otwórz ten rekord.</span><span class="sxs-lookup"><span data-stu-id="3fc89-112">On the **Workers** page, in the **Workers** list, select the record for the worker that you previously set up competencies for, and open the worker record.</span></span>
2. <span data-ttu-id="3fc89-113">W okienku akcji na karcie **Projekt** w grupie **Ustawienia** wybierz opcję **Przypisz projekty**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-113">On the Action Pane, on the **Project** tab, in the **Setup** group, select **Assign projects**.</span></span>
3. <span data-ttu-id="3fc89-114">Na stronie **Przypisania projektu weryfikacji zasobów**, na karcie **Projekty**, w polu **Dodaj projekt do wybranych projektów** odfiltruj projekt **Uaktualnianie XYZ faza 2**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-114">On the **Resource validation project assignments** page, on the **Projects** tab, in the **Add the project to selected projects** field, filter on the **XYZ Upgrade Phase 2** project.</span></span>
4. <span data-ttu-id="3fc89-115">W okienku **Pozostałe projekty** wybierz projekt, a następnie wybierz przycisk strzałki, aby dodać go do okienka **Wybrane projekty**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-115">In the **Remaining projects** pane, select a project, and then select the arrow button to add it to the **Selected projects** pane.</span></span>

<span data-ttu-id="3fc89-116">Można również przypisać kategorie do zasobu według potrzeb.</span><span class="sxs-lookup"><span data-stu-id="3fc89-116">You can also assign categories for a resource as you require.</span></span> <span data-ttu-id="3fc89-117">Typem kategorii jest **Koszt** lub **Przychód**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-117">The category type is either **Cost** or **Revenue**.</span></span> <span data-ttu-id="3fc89-118">Typ kategorii jest określany przez organizację.</span><span class="sxs-lookup"><span data-stu-id="3fc89-118">The category type is determined by your organization.</span></span> <span data-ttu-id="3fc89-119">Jeśli zasób nie ma przypisanych żadnych kategorii, Finance wyszuka domyślną kategorię cen godzinowych dla kosztów i przychodów.</span><span class="sxs-lookup"><span data-stu-id="3fc89-119">If no categories are assigned for a resource, Finance looks up the default category on hour prices for cost and revenue.</span></span>

## <a name="set-up-project-resource-and-role-characteristics"></a><span data-ttu-id="3fc89-120">Konfigurowanie cech zasobów i ról w projekcie</span><span class="sxs-lookup"><span data-stu-id="3fc89-120">Set up project resource and role characteristics</span></span>

<span data-ttu-id="3fc89-121">Kierownik projektu może za pomocą funkcji organizowania zasobów projektu utworzyć role wymagane w projekcie.</span><span class="sxs-lookup"><span data-stu-id="3fc89-121">A project manager can use the project resourcing functionality to create the roles that are required for the project.</span></span> <span data-ttu-id="3fc89-122">Ról można używać, jeżeli potwierdzone zasoby są nadal nieznane podczas rezerwowania zasobów.</span><span class="sxs-lookup"><span data-stu-id="3fc89-122">Roles can be used if confirmed resources are still unknown when resources are being reserved.</span></span> <span data-ttu-id="3fc89-123">Role mogą służyć do tymczasowego rezerwowania planowanych zasobów, tak aby można było kontynuować etapy planowania projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-123">Roles can be temporarily reserved as planned resources, so that you can continue the project planning stages.</span></span>

<span data-ttu-id="3fc89-124">[![Przykład roli](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span><span class="sxs-lookup"><span data-stu-id="3fc89-124">[![Example of a role](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span></span> 

<span data-ttu-id="3fc89-125">**Scenariusz:** Firma Contoso została wynajęta do wykonania projektu rozliczanego według czasu i materiałów mającego zatwierdzony statut projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-125">**Scenario:** Contoso was hired to complete a Time and material project that has an approved project charter.</span></span> <span data-ttu-id="3fc89-126">Młodszy kierownik projektu nadal opracowuje zakres projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-126">The junior project manager is still completing the scope of the project.</span></span> <span data-ttu-id="3fc89-127">Menedżer zasobów obecnie identyfikuje konkretne zasoby, które zostaną zarezerwowane do pracy nad nowym projektem.</span><span class="sxs-lookup"><span data-stu-id="3fc89-127">The resource manager is currently identifying specific resources that will be reserved to work on the new project.</span></span> <span data-ttu-id="3fc89-128">Ze względu na krytyczny charakter projektu jedną z ról wnioskowanych przez sponsora projektu jest starszy kierownik projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-128">Because of the critical nature of the project, the project sponsor requested Senior project manager as one of the roles.</span></span> <span data-ttu-id="3fc89-129">Menedżer zasobów musi pozyskać nowy zasób oraz zdefiniować rolę w systemie na wypadek, gdyby młodszy kierownik projektu potrzebował informacji o zasobie podczas planowania projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-129">The resource manager must acquire the new resource and define the role in the system in case the junior project manager requires the resource information during project planning.</span></span>

<span data-ttu-id="3fc89-130">Poniższe kroki pokazują, jak menedżer zasobów może skonfigurować rolę starszego kierownika projektu i skojarzyć z nią cechy zasobu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-130">The following steps show how the resource manager can set up the Senior project manager role and associate resource characteristics with it.</span></span> <span data-ttu-id="3fc89-131">Później rola może służyć do wyszukiwania dostępnych zasobów posiadających wymagane kompetencje.</span><span class="sxs-lookup"><span data-stu-id="3fc89-131">Later, the role can be used to search for available resources that match the required resource competencies.</span></span>

1. <span data-ttu-id="3fc89-132">Na stronie **Konfiguruj role** wybierz opcję **Nowa** i wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="3fc89-132">On the **Setup roles** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="3fc89-133">**Identyfikator roli:** Starszy kierownik projektu</span><span class="sxs-lookup"><span data-stu-id="3fc89-133">**Role ID:** Senior Project Manager</span></span>
    - <span data-ttu-id="3fc89-134">**Opis:** Starszy kierownik projektu</span><span class="sxs-lookup"><span data-stu-id="3fc89-134">**Description:** Senior Project Manager</span></span>

2. <span data-ttu-id="3fc89-135">Wybierz opcję **Utwórz**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-135">Select **Create**.</span></span>
3. <span data-ttu-id="3fc89-136">Wybierz rolę **Starszy kierownik projektu** i wybierz przycisk **Konfiguruj charakterystyki**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-136">Select the **Senior Project Manager** role, and then select **Configure characteristics**.</span></span>
4. <span data-ttu-id="3fc89-137">W polu **Typ charakterystyki** zaznacz opcję **Umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-137">In the **Characteristics type** field, select **Skill**.</span></span>
5. <span data-ttu-id="3fc89-138">W polu **Dostępne charakterystyki** wprowadź umiejętność, której chcesz poszukać.</span><span class="sxs-lookup"><span data-stu-id="3fc89-138">In the **Available characteristics** field, enter the skill to search for.</span></span>
6. <span data-ttu-id="3fc89-139">W polu **Typ charakterystyki** zaznacz opcję **Certyfikat**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-139">In the **Characteristic type** field, select **Certificate**.</span></span>
7. <span data-ttu-id="3fc89-140">W polu **Dostępne charakterystyki** wprowadź typ zaświadczenia, którego chcesz poszukać.</span><span class="sxs-lookup"><span data-stu-id="3fc89-140">In the **Available characteristics** field, enter the certificate type to search for.</span></span>

## <a name="assign-a-project-resource-to-a-project"></a><span data-ttu-id="3fc89-141">Przypisywanie zasobu projektu do projektu</span><span class="sxs-lookup"><span data-stu-id="3fc89-141">Assign a project resource to a project</span></span>

1. <span data-ttu-id="3fc89-142">Na stronie **Wszystkie projekty** wybierz projekt **Uaktualnianie XYZ faza 2**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-142">On the **All projects** page, select the **XYZ Upgrade Phase 2** project.</span></span>
2. <span data-ttu-id="3fc89-143">Na karcie **Zespół projektu i planowanie** wybierz przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-143">On the **Project team and scheduling** tab, select **Add**.</span></span>
3. <span data-ttu-id="3fc89-144">W polu **Rola** zaznacz opcję **Członek zespołu**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-144">In the **Role** field, select **Team member**.</span></span>
4. <span data-ttu-id="3fc89-145">Wybierz opcję **Rezerwuj z kalendarza**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-145">Select **Book from calendar**.</span></span>
5. <span data-ttu-id="3fc89-146">Na stronie **Dostępność zasobów** wybierz opcję **Ustawienia widoku**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-146">On the **Resource availability** page, select **View settings**.</span></span>
6. <span data-ttu-id="3fc89-147">Na stronie **Dostosuj ustawienia widoku** wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="3fc89-147">On the **Adjust view settings** page, enter the following values:</span></span>

    - <span data-ttu-id="3fc89-148">**Format widoku zakresu dat:** Dzień</span><span class="sxs-lookup"><span data-stu-id="3fc89-148">**Format for date range view:** Day</span></span>
    - <span data-ttu-id="3fc89-149">**Wyświetl opisy dostępności:** Tak</span><span class="sxs-lookup"><span data-stu-id="3fc89-149">**Display availability descriptions:** Yes</span></span>
    - <span data-ttu-id="3fc89-150">**Wyświetlanie pozostałych zdolności produkcyjnych:** Tak</span><span class="sxs-lookup"><span data-stu-id="3fc89-150">**Display remaining capacity:** Yes</span></span>

7. <span data-ttu-id="3fc89-151">Na liście zasobów zaznacz zasób.</span><span class="sxs-lookup"><span data-stu-id="3fc89-151">In the list of resources, select a resource.</span></span>
8. <span data-ttu-id="3fc89-152">Wybierz opcję **Rezerwacje ostateczne** i **Pełne zdolności produkcyjne**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-152">Select **Hard book** and **Full capacity**.</span></span>

## <a name="assign-a-resource-to-a-default-role"></a><span data-ttu-id="3fc89-153">Przypisywanie zasobu do roli domyślnej</span><span class="sxs-lookup"><span data-stu-id="3fc89-153">Assign a resource to a default role</span></span>

<span data-ttu-id="3fc89-154">Aby ułatwić pracę kierownikom projektów lub menedżerom zasobów, można przejść do dokładniejszych ustawień zasobów rezerwowanych dla projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-154">To help project or resource managers can drill down further on the resources that can be reserved for a project.</span></span> <span data-ttu-id="3fc89-155">Można skojarzyć domyślną rolę z istniejącym zasobem lub nowo pozyskanym zasobem.</span><span class="sxs-lookup"><span data-stu-id="3fc89-155">You can associate a default role with an existing resource or a newly acquired resource.</span></span> <span data-ttu-id="3fc89-156">Na przykład kiedy Daniel był zatrudniany, miał doświadczenie i umiejętności niezbędne do roli analityka biznesowego.</span><span class="sxs-lookup"><span data-stu-id="3fc89-156">For example, when Daniel was hired, he had the experience and skills to fill the Business analyst role.</span></span> <span data-ttu-id="3fc89-157">Menedżer zasobów przypisał tę rolę jako domyślną rolę Daniela.</span><span class="sxs-lookup"><span data-stu-id="3fc89-157">The resource manager assigned this role as Daniel's default role.</span></span> <span data-ttu-id="3fc89-158">W związku z tym menedżer zasobów dodał Daniela do puli analityków biznesowych, którzy są dostępni do pracy w projektach.</span><span class="sxs-lookup"><span data-stu-id="3fc89-158">Therefore, the resource manager added Daniel to a pool of business analysts who are available to work on projects.</span></span>

<span data-ttu-id="3fc89-159">Podczas rezerwowania zasobów kierownicy projektów mogą filtrować zasoby z rolami dostępne do pracy w projektach.</span><span class="sxs-lookup"><span data-stu-id="3fc89-159">During resource reservation, project managers can filter the role resources that are available to work on projects.</span></span> <span data-ttu-id="3fc89-160">Mogą wykorzystywać te informacje jako jedno z kryteriów wielowątkowej analizy decyzyjnej podczas rozdzielania zasobów.</span><span class="sxs-lookup"><span data-stu-id="3fc89-160">They can use this information as one criterion when they perform multi-criteria decision analysis during resource fulfillment.</span></span> <span data-ttu-id="3fc89-161">Mogą również dodać inne cechy zasobów do filtra w celu wyszukiwania zasobów, które mają określone umiejętności, wykształcenie i doświadczenie dla danego projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-161">They can also add other resource characteristics to the filter to search for resources that have specific skills, education, and experience for a given project.</span></span>

<span data-ttu-id="3fc89-162">**Scenariusz:** Rozpoczął się zatwierdzony projekt, a na etapie planowania projektu rola starszego kierownika projektu została zarezerwowana jako planowany zasób.</span><span class="sxs-lookup"><span data-stu-id="3fc89-162">**Scenario:** An approved project has started, and the Senior project manager role was reserved as a planned resource during the project planning stage.</span></span> <span data-ttu-id="3fc89-163">Menedżer zasobów pozyskał zasób mogący wypełniać rolę starszego kierownika projektu.</span><span class="sxs-lookup"><span data-stu-id="3fc89-163">The resource manager has now acquired a resource to fulfill the Senior project manager role.</span></span>

1. <span data-ttu-id="3fc89-164">Na stronie **Lista zasobów** zaznacz pozycję **Daniel Goldschmidt**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-164">On the **Resources list** page, select **Daniel Goldschmidt**.</span></span>
2. <span data-ttu-id="3fc89-165">Na stronie **Rola zasobu** wybierz opcję **Nowa** i wprowadź następujące wartości:</span><span class="sxs-lookup"><span data-stu-id="3fc89-165">On the **Resource role** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="3fc89-166">**Data wprowadzenia:** Wprowadź bieżącą datę.</span><span class="sxs-lookup"><span data-stu-id="3fc89-166">**Effective:** Enter the current date.</span></span>
    - <span data-ttu-id="3fc89-167">**Data wygaśnięcia:** Wprowadź tekst **Nigdy**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-167">**Expiration:** Enter **Never**.</span></span>
    - <span data-ttu-id="3fc89-168">**Rola:** Wprowadź **Starszy kierownik projektu**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-168">**Role:** Enter **Senior Project Manager**.</span></span>

3. <span data-ttu-id="3fc89-169">Wybierz przycisk **Zapisz** i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="3fc89-169">Select **Save**, and then close the page.</span></span>
4. <span data-ttu-id="3fc89-170">Na karcie **Kompetencje** dodaj umiejętność **ProjectMgmt** i certyfikat **PMP**.</span><span class="sxs-lookup"><span data-stu-id="3fc89-170">On the **Competencies** tab, add the **ProjectMgmt** skill and the **PMP** certificate.</span></span>
