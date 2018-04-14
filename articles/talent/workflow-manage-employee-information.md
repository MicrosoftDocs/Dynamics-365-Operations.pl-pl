---
title: "Zarządzanie informacjami o pracownikach za pomocą przepływów pracy"
description: "W tym temacie wyjaśniono, jak za pomocą funkcji przepływów pracy dostępnych w module Zasoby ludzkie zarządzać informacjami o pracownikach. Można na przykład skojarzyć przepływ pracy ze stanowiskiem oraz skonfigurować przepływ pracy zatwierdzania, który jest uruchamiany, gdy pracownicy zmodyfikuje swój rekord."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ab84dd4e5ad87c2f3176265f81b0395cfb744315
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="use-workflows-to-manage-employee-information"></a><span data-ttu-id="b4238-104">Zarządzanie informacjami o pracownikach za pomocą przepływów pracy</span><span class="sxs-lookup"><span data-stu-id="b4238-104">Use workflows to manage employee information</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="b4238-105">W tym temacie wyjaśniono, jak za pomocą funkcji przepływów pracy dostępnych w module Zasoby ludzkie zarządzać informacjami o pracownikach.</span><span class="sxs-lookup"><span data-stu-id="b4238-105">This topic explains how you can use the workflow capability for Human resources to manage employee information.</span></span> <span data-ttu-id="b4238-106">Można na przykład skojarzyć przepływ pracy ze stanowiskiem oraz skonfigurować przepływ pracy zatwierdzania, który jest uruchamiany, gdy pracownicy zmodyfikuje swój rekord.</span><span class="sxs-lookup"><span data-stu-id="b4238-106">For example, you can associate a workflow with a position and configure an approval workflow that is started when employees change their record.</span></span>

<span data-ttu-id="b4238-107">Funkcjonalność przepływów pracy zawarta w module Zasoby ludzkie oferuje wiele przepływów pracy do zarządzania działaniami dotyczącymi zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="b4238-107">The workflow capability for Human resources provides numerous workflows for managing human resources activities.</span></span> <span data-ttu-id="b4238-108">Ponadto są dostępne liczne opcje umożliwiające modyfikowanie konkretnych przepływów pracy i ich kojarzenie z hierarchią raportowania.</span><span class="sxs-lookup"><span data-stu-id="b4238-108">Additionally, numerous options are available so that you can modify specific workflows and associate them with a reporting hierarchy.</span></span> <span data-ttu-id="b4238-109">Dostępne są przepływy pracy pomagające zarządzać zmianami w kilku standardowych typach informacji o pracownikach.</span><span class="sxs-lookup"><span data-stu-id="b4238-109">Workflows are available to help manage changes to several standard types of employee information.</span></span> <span data-ttu-id="b4238-110">Przepływ pracy można skojarzyć ze stanowiskiem.</span><span class="sxs-lookup"><span data-stu-id="b4238-110">You can associate a workflow with a position.</span></span> <span data-ttu-id="b4238-111">Następnie jeśli pracownicy zmodyfikują swoje rekordy pracowników, będzie uruchamiany przepływ pracy, który wymaga zatwierdzenia, zanim nowe informacje zostaną zapisane.</span><span class="sxs-lookup"><span data-stu-id="b4238-111">Then, if employees change their employee record, a workflow is started that requires approval before the new information is saved.</span></span> <span data-ttu-id="b4238-112">Przepływy pracy są wstępnie zdefiniowane dla następujących typów informacji, aby ułatwić efektywne zarządzanie zmianami i zachować rzetelność danych pracowników:</span><span class="sxs-lookup"><span data-stu-id="b4238-112">Workflows are predefined for the following types of information to help you efficiently manage changes and keep your employees’ data accurate:</span></span>

-   <span data-ttu-id="b4238-113">Numery identyfikacyjne</span><span class="sxs-lookup"><span data-stu-id="b4238-113">Identification numbers</span></span>
-   <span data-ttu-id="b4238-114">Kursy</span><span class="sxs-lookup"><span data-stu-id="b4238-114">Courses</span></span>
-   <span data-ttu-id="b4238-115">Wykształcenie</span><span class="sxs-lookup"><span data-stu-id="b4238-115">Education</span></span>
-   <span data-ttu-id="b4238-116">Wizerunek</span><span class="sxs-lookup"><span data-stu-id="b4238-116">Image</span></span>
-   <span data-ttu-id="b4238-117">Wypożyczone elementy</span><span class="sxs-lookup"><span data-stu-id="b4238-117">Loaned items</span></span>
-   <span data-ttu-id="b4238-118">Doświadczenie zawodowe</span><span class="sxs-lookup"><span data-stu-id="b4238-118">Professional experience</span></span>
-   <span data-ttu-id="b4238-119">Doświadczenie w projekcie</span><span class="sxs-lookup"><span data-stu-id="b4238-119">Project experience</span></span>
-   <span data-ttu-id="b4238-120">Umiejętności</span><span class="sxs-lookup"><span data-stu-id="b4238-120">Skills</span></span>
-   <span data-ttu-id="b4238-121">Stanowiska zaufania</span><span class="sxs-lookup"><span data-stu-id="b4238-121">Positions of trust</span></span>
-   <span data-ttu-id="b4238-122">Akcje w module Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="b4238-122">Human resources actions</span></span>
-   <span data-ttu-id="b4238-123">Rejestracja na kurs</span><span class="sxs-lookup"><span data-stu-id="b4238-123">Course registration</span></span>

<span data-ttu-id="b4238-124">Kiedy pracownicy są zatrudniani, przenoszeni lub zwalniani, przepływ pracy może zawierać proces weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="b4238-124">When employees are hired, transferred, or terminated, the workflow can include a review process.</span></span> <span data-ttu-id="b4238-125">W ten sposób w ramach przepływu pracy można sprawdzić dokument lub zdefiniować warunki czynności.</span><span class="sxs-lookup"><span data-stu-id="b4238-125">In this way, a document can be revised or the terms of an action can be defined as part of the workflow.</span></span> <span data-ttu-id="b4238-126">Po zakończeniu procesu weryfikacji następuje finalizacja dokumentu lub czynność, a przepływ pracy przechodzi do ostatniego etapu zatwierdzania.</span><span class="sxs-lookup"><span data-stu-id="b4238-126">When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.</span></span>

## <a name="associate-a-workflow-with-a-position-hierarchy"></a><span data-ttu-id="b4238-127">Kojarzenie przepływu pracy z hierarchią stanowisk</span><span class="sxs-lookup"><span data-stu-id="b4238-127">Associate a workflow with a position hierarchy</span></span>
<span data-ttu-id="b4238-128">Przepływ pracy można skojarzyć z dowolną skonfigurowaną hierarchią.</span><span class="sxs-lookup"><span data-stu-id="b4238-128">You can associate a workflow with any hierarchy that you configure.</span></span> <span data-ttu-id="b4238-129">Na przykład jeśli stanowisko jest skojarzone z macierzową hierarchią raportowania, można skonfigurować przepływ pracy, który kieruje wydatki danego projektu do kierownika projektu zamiast do menedżera pracownika skojarzonego z tym stanowiskiem.</span><span class="sxs-lookup"><span data-stu-id="b4238-129">For example, if a position is associated with a matrix reporting hierarchy, you might configure a workflow that routes expenses for a specific project to the project lead instead of the manager of the employee who is associated with that position.</span></span> <span data-ttu-id="b4238-130">Aby utworzyć nowy przepływ pracy lub zmodyfikować istniejący przepływ pracy, na stronie **Przepływy pracy modułu Zasoby ludzkie** kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b4238-130">To create a new workflow or modify an existing workflow, on the **Human resources workflow** page, click **New**.</span></span> <span data-ttu-id="b4238-131">Zaznacz przepływ pracy na liście, a zostanie uruchomiony projektant przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="b4238-131">Select a workflow in the list to start the Workflow designer.</span></span> <span data-ttu-id="b4238-132">Za pomocą projektanta można utworzyć nowy przepływ pracy lub zmienić kroki w istniejącym przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="b4238-132">You can use the designer to create a new workflow or change the steps in an existing workflow.</span></span> <span data-ttu-id="b4238-133">Po modyfikacji istniejącego przepływu pracy zmiany zostaną zapisane jako nowa wersja.</span><span class="sxs-lookup"><span data-stu-id="b4238-133">When you change an existing workflow, your changes are saved as a new version.</span></span> <span data-ttu-id="b4238-134">W związku z tym zawsze można wrócić do poprzedniej wersji, jeśli trzeba.</span><span class="sxs-lookup"><span data-stu-id="b4238-134">Therefore, you can always go back to a previous version if you have to.</span></span>

## <a name="configure-a-human-resources-workflow"></a><span data-ttu-id="b4238-135">Konfigurowanie przepływu pracy dla modułu Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="b4238-135">Configure a Human resources workflow</span></span>
<span data-ttu-id="b4238-136">Aby skonfigurować podstawowy przepływ pracy uruchamiany w momencie, gdy pracownicy proszą o zmiany ich osobistych numerów identyfikacyjnych, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="b4238-136">To configure a basic workflow that is started when employees request changes to their personal identification, follow these steps.</span></span>

1.  <span data-ttu-id="b4238-137">Na stronie **Przepływy pracy modułu Zasoby ludzkie** kliknij przycisk **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="b4238-137">On the **Human resources workflows** page, click **New**.</span></span>
2.  <span data-ttu-id="b4238-138">Na liście dostępnych przepływów pracy wybierz opcję **Numery identyfikacyjne**.</span><span class="sxs-lookup"><span data-stu-id="b4238-138">In the list of available workflows, select **Identification numbers**.</span></span>
3.  <span data-ttu-id="b4238-139">Kliknij przycisk **Uruchom**, aby uruchomić projektanta przepływów pracy, a następnie w odpowiedzi na monit wprowadź swoją nazwę użytkownika i hasło.</span><span class="sxs-lookup"><span data-stu-id="b4238-139">Click **Run** to start the Workflow designer, and then enter your user name and password when you're prompted.</span></span>
4.  <span data-ttu-id="b4238-140">Przeciągnij element **Zatwierdź numer identyfikacyjny** z listy elementów przepływu pracy na kanwę projektanta.</span><span class="sxs-lookup"><span data-stu-id="b4238-140">Drag the **Approve identification number** element from the list of workflow elements to the designer canvas.</span></span>
5.  <span data-ttu-id="b4238-141">Połącz element zatwierdzania z czynnościami **Rozpocznij** i **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="b4238-141">Connect the approval element to **Start** and **Finish**.</span></span>
6.  <span data-ttu-id="b4238-142">Kliknij dwukrotnie pozycję **Element zatwierdzania**, a następnie kliknij prawym przyciskiem myszy i wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="b4238-142">Double-click **Approve element**, and then right-click, and select **Properties**.</span></span>
7.  <span data-ttu-id="b4238-143">Wykonaj następujące kroki, aby dodać instrukcje elementu pracy:</span><span class="sxs-lookup"><span data-stu-id="b4238-143">Follow these steps to add work item instructions:</span></span>
    1.  <span data-ttu-id="b4238-144">Wybierz opcję **Przypisanie**, a następnie w polu typu przypisania wybierz opcję **Hierarchia**.</span><span class="sxs-lookup"><span data-stu-id="b4238-144">Select **Assignment**, and then select **Hierarchy** under the assignment type.</span></span>
    2.  <span data-ttu-id="b4238-145">W obszarze **Hierarchia** zaznacz opcję **Konfigurowalna hierarchia**.</span><span class="sxs-lookup"><span data-stu-id="b4238-145">Under the **Hierarchy** selection, select **Configurable hierarchy**.</span></span>
    3.  <span data-ttu-id="b4238-146">Dodaj warunek zatrzymania i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="b4238-146">Add a stop condition, and close the page.</span></span>

8.  <span data-ttu-id="b4238-147">Wykonaj wszelkie dodatkowe instrukcje (nie powinny być generowane żadne dodatkowe ostrzeżenia).</span><span class="sxs-lookup"><span data-stu-id="b4238-147">Complete any additional instructions (no additional warnings should exist).</span></span>
9.  <span data-ttu-id="b4238-148">Kliknij przycisk **Zapisz i zamknij**.</span><span class="sxs-lookup"><span data-stu-id="b4238-148">Click **Save and close**.</span></span> <span data-ttu-id="b4238-149">Gdy zostanie otwarte okno dialogowe, wybierz opcję **Uaktywnij**.</span><span class="sxs-lookup"><span data-stu-id="b4238-149">Activate the new workflow when the dialog box opens, and select **Make active**.</span></span>
10. <span data-ttu-id="b4238-150">Wybierz kolejno opcje **Zasoby ludzkie** &gt; **Stanowiska** &gt; **Typy hierarchii stanowisk**.</span><span class="sxs-lookup"><span data-stu-id="b4238-150">Go to **Human Resources** &gt; **Positions** &gt; **Position hierarchy types**.</span></span>
11. <span data-ttu-id="b4238-151">Wybierz opcję **Macierz**.</span><span class="sxs-lookup"><span data-stu-id="b4238-151">Select **Matrix**.</span></span>
12. <span data-ttu-id="b4238-152">Dodaj przepływ pracy **Numer identyfikacyjny pracownika** do listy.</span><span class="sxs-lookup"><span data-stu-id="b4238-152">Add the **Worker identification number** workflow to the list.</span></span>





