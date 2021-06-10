---
title: Konfigurowanie umiejętności
description: Umiejętności pracownika można śledzić w Dynamics 365 Human Resources. Można również określić umiejętności, które są wymagane dla danego zadania.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076566"
---
# <a name="configure-skills"></a><span data-ttu-id="420bd-104">Konfigurowanie umiejętności</span><span class="sxs-lookup"><span data-stu-id="420bd-104">Configure skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="420bd-105">Umiejętności pracownika można śledzić w Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="420bd-105">You can track your worker's skills in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="420bd-106">Można również określić umiejętności, które są wymagane dla danego zadania.</span><span class="sxs-lookup"><span data-stu-id="420bd-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="420bd-107">Przykłady umiejętności, które można śledzić:</span><span class="sxs-lookup"><span data-stu-id="420bd-107">Examples of skills you can track include:</span></span>

- <span data-ttu-id="420bd-108">Kierownicze — zdolność do nadzorowania pracy innych.</span><span class="sxs-lookup"><span data-stu-id="420bd-108">Supervisory – Ability to supervise the work of others.</span></span>
- <span data-ttu-id="420bd-109">Przywódcze — zdolność do kierowania pracownikami i domenami biznesowymi.</span><span class="sxs-lookup"><span data-stu-id="420bd-109">Leadership – Ability to lead employees and business domains.</span></span>
- <span data-ttu-id="420bd-110">Planowania — zdolność do patrzenia w przyszłość, formułowania wizji i doprowadzania ich do końca.</span><span class="sxs-lookup"><span data-stu-id="420bd-110">Planning – Ability to look ahead, to form vision statements, and to see them through.</span></span>
- <span data-ttu-id="420bd-111">HTML — umożliwia zapis kodu HTML.</span><span class="sxs-lookup"><span data-stu-id="420bd-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="420bd-112">Jeśli nie masz jeszcze skonfigurowanych typów umiejętności i modeli oceniania, musisz je dodać przed utworzeniem umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-112">If you haven't already set up skill types and rating models, you'll need to add some before creating skills.</span></span>

<span data-ttu-id="420bd-113">Następujące osoby mogą wprowadzić umiejętności dla pracownika:</span><span class="sxs-lookup"><span data-stu-id="420bd-113">The following people can enter skills for a worker:</span></span>

- <span data-ttu-id="420bd-114">Pracownicy mogą sami wprowadzać swoje umiejętności w ramach samoobsługi pracowniczej.</span><span class="sxs-lookup"><span data-stu-id="420bd-114">Workers can enter skills for themselves in Employee self-service.</span></span> <span data-ttu-id="420bd-115">Umiejętności te wymagają zatwierdzenia przez kierownika.</span><span class="sxs-lookup"><span data-stu-id="420bd-115">These skills require manager approval.</span></span>
- <span data-ttu-id="420bd-116">Menedżerowie mogą wprowadzać umiejętności dla swoich pracowników.</span><span class="sxs-lookup"><span data-stu-id="420bd-116">Managers can enter skills for their workers.</span></span> <span data-ttu-id="420bd-117">Można utworzyć przepływ pracy, który będzie automatycznie zatwierdzał te umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-117">You can create a workflow that auto-approves these skills.</span></span>

## <a name="create-a-skill-type"></a><span data-ttu-id="420bd-118">Tworzenie typu umiejętności</span><span class="sxs-lookup"><span data-stu-id="420bd-118">Create a skill type</span></span>

<span data-ttu-id="420bd-119">Typy umiejętności to kategorie, do których należą poszczególne umiejętności, takie jak Administracja czy Sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="420bd-119">Skill types are categories that individual skills fall under, such as Administration or Sales.</span></span>

1. <span data-ttu-id="420bd-120">W obszarze roboczym **Rozwój pracowników** wybierz opcję **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="420bd-120">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="420bd-121">W obszarze **Ustawienia umiejętności** wybierz **Typy umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="420bd-121">Under **Competency setup**, select **Skill types**.</span></span>

3. <span data-ttu-id="420bd-122">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="420bd-122">Select **New**.</span></span>

4. <span data-ttu-id="420bd-123">Wypełnij następujące pola:</span><span class="sxs-lookup"><span data-stu-id="420bd-123">Complete the following fields:</span></span>

   - <span data-ttu-id="420bd-124">**Typ umiejętności** – Wprowadź nazwę typu umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-124">**Skill type**: Enter a name for the skill type.</span></span>
   - <span data-ttu-id="420bd-125">**Opis** – Wprowadź opis typu umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-125">**Description**: Enter a description for the skill type.</span></span>

5. <span data-ttu-id="420bd-126">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="420bd-126">Select **Save**.</span></span>

## <a name="create-a-rating-model"></a><span data-ttu-id="420bd-127">Utwórz model oceny</span><span class="sxs-lookup"><span data-stu-id="420bd-127">Create a rating model</span></span>

<span data-ttu-id="420bd-128">Modele oceniania pomagają w ocenie rzeczywistego poziomu umiejętności danej osoby, poziom, do osiągnięcia jakiego powinna ona dążyć lub poziom umiejętności wymagany dla zadania.</span><span class="sxs-lookup"><span data-stu-id="420bd-128">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill required for a job.</span></span> <span data-ttu-id="420bd-129">Każdy poziom w modelu oceniania ma przypisany współczynnik.</span><span class="sxs-lookup"><span data-stu-id="420bd-129">Each level in a rating model is assigned a factor.</span></span>

1. <span data-ttu-id="420bd-130">W obszarze roboczym **Rozwój pracowników** wybierz opcję **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="420bd-130">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="420bd-131">W obszarze **Ustawienia umiejętności** wybierz pozycję **Modele oceniania**.</span><span class="sxs-lookup"><span data-stu-id="420bd-131">Under **Competency setup**, select **Rating models**.</span></span>

3. <span data-ttu-id="420bd-132">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="420bd-132">Select **New**.</span></span>

4. <span data-ttu-id="420bd-133">Wypełnij następujące pola:</span><span class="sxs-lookup"><span data-stu-id="420bd-133">Complete the following fields:</span></span>

   - <span data-ttu-id="420bd-134">**Ocena**: wprowadź nazwę modelu oceniania, na przykład **Umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="420bd-134">**Rating**: Enter a name for the rating model, such as **Skills**.</span></span>
   - <span data-ttu-id="420bd-135">**Opis**: służy do wprowadzania opisu modelu oceniania, takiego jak **Umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="420bd-135">**Description**: Enter a description for the rating model, such as **Skill ratings**.</span></span>

5. <span data-ttu-id="420bd-136">W sekcji **Poziomy** wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="420bd-136">In the **Levels** section, select **New**.</span></span> <span data-ttu-id="420bd-137">Dla każdego poziomu, który chcesz dodać, wypełnij następujące pola:</span><span class="sxs-lookup"><span data-stu-id="420bd-137">For each level you want to add, complete the following fields:</span></span>

   - <span data-ttu-id="420bd-138">**Poziom**: Umożliwia wprowadzenie nazwy poziomu.</span><span class="sxs-lookup"><span data-stu-id="420bd-138">**Level**: Enter a name for the level.</span></span>
   - <span data-ttu-id="420bd-139">**Opis**: Umożliwia wprowadzenie opisu poziomu.</span><span class="sxs-lookup"><span data-stu-id="420bd-139">**Description**: Enter a description for the level.</span></span>
   - <span data-ttu-id="420bd-140">**Współczynnik**: należy wprowadzić wartość współczynnika od 0–9.</span><span class="sxs-lookup"><span data-stu-id="420bd-140">**Factor**: Enter a factor value from 0-9.</span></span> <span data-ttu-id="420bd-141">Czynniki pomagają znormalizować wyniki umiejętności, które wykorzystują różne modele oceny.</span><span class="sxs-lookup"><span data-stu-id="420bd-141">Factors help normalize the scores of skills that use different rating models.</span></span> <span data-ttu-id="420bd-142">Każdy poziom musi mieć unikalny czynnik.</span><span class="sxs-lookup"><span data-stu-id="420bd-142">Each level must have a unique factor.</span></span> <span data-ttu-id="420bd-143">Poziomy z wysokimi wartościami współczynników mają większą wagę w modelu oceniania.</span><span class="sxs-lookup"><span data-stu-id="420bd-143">Levels with higher factor values carry more weight in a rating model.</span></span>

   <span data-ttu-id="420bd-144">W razie potrzeby kontynuuj dodawanie poziomów.</span><span class="sxs-lookup"><span data-stu-id="420bd-144">Continue adding levels as necessary.</span></span> <span data-ttu-id="420bd-145">Dla każdego modelu oceny można wprowadzić do 10 poziomów.</span><span class="sxs-lookup"><span data-stu-id="420bd-145">You can enter up to 10 levels for each rating model.</span></span>

6. <span data-ttu-id="420bd-146">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="420bd-146">Select **Save**.</span></span>

## <a name="create-a-skill"></a><span data-ttu-id="420bd-147">Tworzenie umiejętności</span><span class="sxs-lookup"><span data-stu-id="420bd-147">Create a skill</span></span>

<span data-ttu-id="420bd-148">Przed przypisaniem umiejętności, utworzeniem przeszukiwania mapowania umiejętności lub profilu umiejętności, należy wprowadzić informacje o umiejętnościach na stronie **Umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="420bd-148">Before you can assign a skill, or create a skill-mapping search or skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="420bd-149">Dla każdej umiejętności można wybrać typ umiejętności i model oceniania.</span><span class="sxs-lookup"><span data-stu-id="420bd-149">For each skill, you can select a skill type and a rating model.</span></span>

1. <span data-ttu-id="420bd-150">W obszarze roboczym **Rozwój pracowników** wybierz opcję **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="420bd-150">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="420bd-151">W obszarze **Ustawienia umiejętności** wybierz **Umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="420bd-151">Under **Competency setup**, select **Skills**.</span></span>

3. <span data-ttu-id="420bd-152">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="420bd-152">Select **New**.</span></span>

4. <span data-ttu-id="420bd-153">Wypełnij następujące pola:</span><span class="sxs-lookup"><span data-stu-id="420bd-153">Complete the following fields:</span></span>

   - <span data-ttu-id="420bd-154">**Umiejętność** – Wprowadź nazwę umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-154">**Skill**: Enter a name for the skill.</span></span>
   - <span data-ttu-id="420bd-155">**Opis** – Wprowadź opis umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-155">**Description**: Enter a description for the skill.</span></span>
   - <span data-ttu-id="420bd-156">**Ocena**: Umożliwia wybór modelu oceny, który ma być stosowany w ocenie umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-156">**Rating**: Select the rating model you want to use for this skill.</span></span>
   - <span data-ttu-id="420bd-157">**Typ umiejętności**: umożliwia wybór z listy typów umiejętności.</span><span class="sxs-lookup"><span data-stu-id="420bd-157">**Skill type**: Select from the list of skill types.</span></span>

5. <span data-ttu-id="420bd-158">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="420bd-158">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="420bd-159">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="420bd-159">See also</span></span>

[<span data-ttu-id="420bd-160">Wprowadzanie umiejętności</span><span class="sxs-lookup"><span data-stu-id="420bd-160">Enter skills</span></span>](hr-develop-enter-skills.md)<br>
[<span data-ttu-id="420bd-161">Mapowanie umiejętności</span><span class="sxs-lookup"><span data-stu-id="420bd-161">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]