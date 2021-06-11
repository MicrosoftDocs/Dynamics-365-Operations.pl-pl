---
title: Wprowadzanie umiejętności
description: Pracownicy i kierownicy mogą wprowadzać umiejętności w Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: b24d37292a2e9749fb2fde06b9f03fcd13db0bbe
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076610"
---
# <a name="enter-skills"></a><span data-ttu-id="80c2a-103">Wprowadzanie umiejętności</span><span class="sxs-lookup"><span data-stu-id="80c2a-103">Enter skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="80c2a-104">Można wprowadzić umiejętności docelowe lub rzeczywiste umiejętności pracowników, kandydatów lub osób kontaktowych w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="80c2a-104">You can enter target skills or actual skills for workers, applicants, or contacts in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="80c2a-105">Umiejętność docelowa jest umiejętnością, jaką osoba planuje zdobyć.</span><span class="sxs-lookup"><span data-stu-id="80c2a-105">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="80c2a-106">Rzeczywista umiejętność jest umiejętnością, jaką dana osoba aktualnie dysponuje.</span><span class="sxs-lookup"><span data-stu-id="80c2a-106">An actual skill is a skill that a person currently has.</span></span>

## <a name="create-a-workflow-to-auto-approve-skills"></a><span data-ttu-id="80c2a-107">Tworzenie przepływu pracy w celu automatycznego zatwierdzania umiejętności</span><span class="sxs-lookup"><span data-stu-id="80c2a-107">Create a workflow to auto-approve skills</span></span>

<span data-ttu-id="80c2a-108">Aby wprowadzić umiejętności bez konieczności ich zatwierdzania, należy stworzyć przepływ pracy, który będzie automatycznie zatwierdzał umiejętności.</span><span class="sxs-lookup"><span data-stu-id="80c2a-108">To enter skills without requiring approval, you must create a workflow to auto-approve skills.</span></span>

> [!NOTE]
> <span data-ttu-id="80c2a-109">Umiejętności wprowadzane przez pracowników zawsze wymagają zatwierdzenia przez kierownika.</span><span class="sxs-lookup"><span data-stu-id="80c2a-109">Skills entered by workers always require manager approval.</span></span> <span data-ttu-id="80c2a-110">Ten przepływ pracy automatycznie zatwierdza jedynie umiejętności wprowadzone przez menedżerów w imieniu swoich pracowników.</span><span class="sxs-lookup"><span data-stu-id="80c2a-110">This workflow only auto-approves skills entered by managers on behalf of their workers.</span></span>

1. <span data-ttu-id="80c2a-111">W obszarze roboczym **Zarządzanie personelem** wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-111">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="80c2a-112">W obszarze **Konfiguracja** wybierz opcję **Przepływy pracy modułu zasobów ludzkich**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-112">Under **Setup**, select **Human resources workflows**.</span></span>

3. <span data-ttu-id="80c2a-113">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-113">Select **New**.</span></span>

4. <span data-ttu-id="80c2a-114">W okienku **Utwórz przepływpracy** wybierz opcję **Umiejętności pracownika**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-114">In the **Create workflow** pane, select **Worker skills**.</span></span>

   <span data-ttu-id="80c2a-115">[![Wybierz przepływ pracy umiejętności pracownika](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span><span class="sxs-lookup"><span data-stu-id="80c2a-115">[![Select Worker skills workflow](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span></span>

5. <span data-ttu-id="80c2a-116">W okienku **Otworzyć ten plik?** należy wybrać **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-116">In the **Open this file?** dialogue, select **Open**.</span></span> <span data-ttu-id="80c2a-117">Po wyświetleniu monitu wprowadź swoje dane uwierzytelniające.</span><span class="sxs-lookup"><span data-stu-id="80c2a-117">When prompted, enter your credentials.</span></span>

6. <span data-ttu-id="80c2a-118">W edytorze przepływu pracy wybierz element **Zatwierdź umiejętności** i przeciągnij go na kanwę.</span><span class="sxs-lookup"><span data-stu-id="80c2a-118">In the workflow editor, select the **Approve skills** workflow element and drag it onto the canvas.</span></span>

   <span data-ttu-id="80c2a-119">[![Wybierz element Zatwierdź przepływ pracy umiejętności](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span><span class="sxs-lookup"><span data-stu-id="80c2a-119">[![Select Approve skills workflow element](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span></span>

7. <span data-ttu-id="80c2a-120">Połącz element **Rozpoczęcie** z elementem **Zatwierdź umiejętności 1**, a następnie połącz element **Zatwierdź umiejętności 1** z elementem **Zakończ**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-120">Connect the **Start** element to the **Approve skills 1** element, and then connect the **Approve skills 1** element to the **End** element.</span></span> <span data-ttu-id="80c2a-121">Może być konieczne przewiniecie w dół, aby zobaczyć element **Koniec**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-121">You might need to scroll down to see the **End** element.</span></span> <span data-ttu-id="80c2a-122">Możesz przeciągnąć go bliżej innych elementów.</span><span class="sxs-lookup"><span data-stu-id="80c2a-122">You can drag it closer to the other elements.</span></span>

   <span data-ttu-id="80c2a-123">[![Łączenie elementów przepływu pracy](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span><span class="sxs-lookup"><span data-stu-id="80c2a-123">[![Connect workflow elements](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span></span>

8. <span data-ttu-id="80c2a-124">Kliknij dwukrotnie element przepływu pracy **Zatwierdź kwalifikacje 1**, a następnie kliknij prawym przyciskiem myszy element **Krok 1**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-124">Double-click the **Approve skills 1** workflow element, and then right-click the **Step 1** element.</span></span> <span data-ttu-id="80c2a-125">Kliknij prawym przyciskiem myszy element **Krok 1**, a następnie wybierz polecenie **Właściwości**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-125">Right-click the **Step 1** element, and then select **Properties**.</span></span>

9. <span data-ttu-id="80c2a-126">W oknie **Właściwości** wybierz **Warunek** na pasku z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="80c2a-126">In the **Properties** window, select **Condition** on the left-hand nav bar.</span></span>

10. <span data-ttu-id="80c2a-127">Wybierz opcję **Wykonaj ten krok, tylko jeśli zostanie spełniony następujący warunek**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-127">Select **Run this step only when the following condition is met**.</span></span>

11. <span data-ttu-id="80c2a-128">Wybierz **Dodaj warunek**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-128">Select **Add condition**.</span></span> <span data-ttu-id="80c2a-129">Po wybraniu opcji **Gdzie** wybierz **Umiejętności samoobsługi pracownika**, a następnie wybierz **Umiejętności samoobsługi pracownika.Osoba**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-129">After **Where**, select **Employee self service skills**, and then select **Employee self service skills.Person**.</span></span> <span data-ttu-id="80c2a-130">Po zaznaczeniu **jest**, wybierz **pole**, a następnie **Stosunek użytkownika do osoby.Osoba**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-130">After **is**, select **field**, and then select **User to person relationship.Person**.</span></span>

    <span data-ttu-id="80c2a-131">[![Określ warunek](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span><span class="sxs-lookup"><span data-stu-id="80c2a-131">[![Specify condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span></span>

12. <span data-ttu-id="80c2a-132">Wybierz pozycję **Przypisanie** na pasku adresu z lewej strony.</span><span class="sxs-lookup"><span data-stu-id="80c2a-132">Select **Assignment** on the left-hand nav bar.</span></span>

13. <span data-ttu-id="80c2a-133">Na karcie **Typ przypisania** wybierz pozycję **Hierarchia**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-133">On the **Assignment type** tab, select **Hierarchy**.</span></span>

14. <span data-ttu-id="80c2a-134">Na karcie **Wybór hierarchii** w polu **Typ hierarchii** wybierz pozycję **Hierarchia menedżerska**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-134">On the **Hierarchy selection** tab, in the **Hierarchy type:** field, select **Managerial hierarchy**.</span></span>

    <span data-ttu-id="80c2a-135">[![Określ hierarchię menedżerską](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span><span class="sxs-lookup"><span data-stu-id="80c2a-135">[![Specify managerial hierarchy](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span></span>

15. <span data-ttu-id="80c2a-136">Wybierz opcję **Zamknij**, wybierz **Przepływ pracy** w kanwie modułu nawigacyjnego, a następnie wybierz polecenie **Zapisz i zamknij**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-136">Select **Close**, select **Workflow** in the canvas breadcrumb, and then select **Save and close**.</span></span>

<span data-ttu-id="80c2a-137">Więcej informacji na temat tworzenia przepływów pracy zawiera temat [Omówienie tworzenia przepływów pracy](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="80c2a-137">For more information about creating workflows, see [Workflow system overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/overview-workflow-system?toc=/dynamics365/human-resources/toc.json).</span></span>

## <a name="enter-skills-for-a-worker"></a><span data-ttu-id="80c2a-138">Wprowadzanie umiejętności pracownika</span><span class="sxs-lookup"><span data-stu-id="80c2a-138">Enter skills for a worker</span></span>

1. <span data-ttu-id="80c2a-139">Wybierz pracownika.</span><span class="sxs-lookup"><span data-stu-id="80c2a-139">Select a worker.</span></span>

2. <span data-ttu-id="80c2a-140">Na pasku akcji strony **Pracownik** wybierz pozycję **Osoba**, a następnie wybierz pozycję **Umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-140">In the action bar of the **Worker** page, select **Person**, and then select **Skills**.</span></span>

3. <span data-ttu-id="80c2a-141">Na stronie **Umiejętności** wypełnij następujące pola dla każdej umiejętności:</span><span class="sxs-lookup"><span data-stu-id="80c2a-141">On the **Skills** page, complete the following fields for each skill:</span></span>

   - <span data-ttu-id="80c2a-142">**Umiejętność**: wybierz daną umiejętność.</span><span class="sxs-lookup"><span data-stu-id="80c2a-142">**Skill**: Select a skill.</span></span>
   - <span data-ttu-id="80c2a-143">**Poziom**: wybierz wartość **Rzeczywista** dla umiejętności, która jest już posiadana przez pracownika, lub wybierz pozycję **Docelowa** dla umiejętności, nad którą pracownik pracuje.</span><span class="sxs-lookup"><span data-stu-id="80c2a-143">**Level type**: Select **Actual** for a skill the worker already has, or select **Target** for a skill the worker is working toward.</span></span>
   - <span data-ttu-id="80c2a-144">**Poziom**: wybierz poziom kwalifikacji pracownika.</span><span class="sxs-lookup"><span data-stu-id="80c2a-144">**Level**: Select a level for the worker's skill.</span></span>
   - <span data-ttu-id="80c2a-145">**Data zdobycia poziomu**: aby wybrać datę, należy kliknąć datę w kalendarzu.</span><span class="sxs-lookup"><span data-stu-id="80c2a-145">**Level date**: Select a date in the calendar tool.</span></span>
   - <span data-ttu-id="80c2a-146">**Egzaminator**: w razie potrzeby wybierz z listy kandydata.</span><span class="sxs-lookup"><span data-stu-id="80c2a-146">**Examiner**: If appropriate, select an examiner from the list.</span></span> <span data-ttu-id="80c2a-147">Wyszukiwanie można filtrować.</span><span class="sxs-lookup"><span data-stu-id="80c2a-147">You can filter your search.</span></span>
   - <span data-ttu-id="80c2a-148">**Lata doświadczenia**: wprowadź lata doświadczenia.</span><span class="sxs-lookup"><span data-stu-id="80c2a-148">**Years of experience**: Enter years of experience.</span></span>
   - <span data-ttu-id="80c2a-149">**Zweryfikowano**: jeśli umiejętność została zweryfikowana, zaznacz pole.</span><span class="sxs-lookup"><span data-stu-id="80c2a-149">**Verified**: If the skill is verified, check the box.</span></span>
   - <span data-ttu-id="80c2a-150">**Zweryfikowane przez**: wprowadź nazwę weryfikatora.</span><span class="sxs-lookup"><span data-stu-id="80c2a-150">**Verified by**: Enter the name of the verifier.</span></span>

4. <span data-ttu-id="80c2a-151">Po wprowadzeniu umiejętności wybierz przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="80c2a-151">When you're done entering skills, select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="80c2a-152">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="80c2a-152">See also</span></span>

[<span data-ttu-id="80c2a-153">Konfigurowanie umiejętności</span><span class="sxs-lookup"><span data-stu-id="80c2a-153">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="80c2a-154">Mapowanie umiejętności</span><span class="sxs-lookup"><span data-stu-id="80c2a-154">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]