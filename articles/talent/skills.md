---
title: "Dopasowywanie umiejętności pracowników do potrzeb firmy"
description: "Umiejętności pracowników, kandydatów lub osób kontaktowych, umożliwiające im skuteczne wykonywanie swoich obowiązków, można śledzić. Można również określić umiejętności, które są wymagane dla danego zadania."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0b86a8d134ef553db6719f4cefb02e4acfc00ae5
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="align-workforce-skills-with-business-needs"></a><span data-ttu-id="97586-104">Dopasowywanie umiejętności pracowników do potrzeb firmy</span><span class="sxs-lookup"><span data-stu-id="97586-104">Align workforce skills with business needs</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="97586-105">Umiejętności pracowników, kandydatów lub osób kontaktowych, umożliwiające im skuteczne wykonywanie swoich obowiązków, można śledzić.</span><span class="sxs-lookup"><span data-stu-id="97586-105">You can track the skills that workers, applicants, or contact persons have, or should have, to fulfill their roles effectively.</span></span> <span data-ttu-id="97586-106">Można również określić umiejętności, które są wymagane dla danego zadania.</span><span class="sxs-lookup"><span data-stu-id="97586-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="97586-107">Przykłady umiejętności, które można śledzić:</span><span class="sxs-lookup"><span data-stu-id="97586-107">Examples of skills you can track include the following:</span></span>
-   <span data-ttu-id="97586-108">Kierownicze — zdolność do nadzorowania pracy innych.</span><span class="sxs-lookup"><span data-stu-id="97586-108">Supervisory – Ability to supervise the work of others.</span></span>
-   <span data-ttu-id="97586-109">Przywódcze — zdolność do kierowania pracownikami i domenami biznesowymi.</span><span class="sxs-lookup"><span data-stu-id="97586-109">Leadership – Ability to lead employees and business domains.</span></span>
-   <span data-ttu-id="97586-110">Planowania — zdolność do patrzenia w przyszłość, formułowania wizji i doprowadzania ich do końca.</span><span class="sxs-lookup"><span data-stu-id="97586-110">Planning – Ability to look ahead, to form visions, and to see them through.</span></span>
-   <span data-ttu-id="97586-111">HTML — umożliwia zapis kodu HTML.</span><span class="sxs-lookup"><span data-stu-id="97586-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="97586-112">Przed przypisaniem umiejętności do osoby lub zadania, utworzeniem przeszukiwania mapowania umiejętności lub profilu umiejętności, należy wprowadzić informacje o umiejętnościach na stronie **Umiejętności**.</span><span class="sxs-lookup"><span data-stu-id="97586-112">Before you can assign a skill to a person or a job, create a skill-mapping search, or create a skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="97586-113">Dla każdej umiejętności można wybrać typ umiejętności i model oceniania.</span><span class="sxs-lookup"><span data-stu-id="97586-113">For each skill, you can select a skill type and a rating model.</span></span>

## <a name="rating-models"></a><span data-ttu-id="97586-114">Modele oceniania</span><span class="sxs-lookup"><span data-stu-id="97586-114">Rating models</span></span>
<span data-ttu-id="97586-115">Modele oceniania pomagają w ocenie rzeczywistego poziomu umiejętności danej osoby, poziom, do osiągnięcia jakiego powinna ona dążyć lub poziom umiejętności wymagany dla zadania.</span><span class="sxs-lookup"><span data-stu-id="97586-115">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill that is required for a job.</span></span> <span data-ttu-id="97586-116">Można wprowadzić maksymalnie 10 poziomów modelu klasyfikacji.</span><span class="sxs-lookup"><span data-stu-id="97586-116">You can enter up to 10 levels for a rating model.</span></span>  <span data-ttu-id="97586-117">Każdy poziom w modelu oceniania ma przypisany współczynnik.</span><span class="sxs-lookup"><span data-stu-id="97586-117">Each level in a rating model is assigned a factor.</span></span>  <span data-ttu-id="97586-118">Wartość współczynnika będzie używana do normalizacji wyników umiejętności, które używają różnych modeli oceny.</span><span class="sxs-lookup"><span data-stu-id="97586-118">The factor value will be used to normalize the scores of skills that use different rating models.</span></span>  <span data-ttu-id="97586-119">Współczynnik musi być cyfrą od 0 do 9 i każdy poziom musi mieć unikatowy współczynnik.</span><span class="sxs-lookup"><span data-stu-id="97586-119">The factor must be a number between 0-9 and each level must have a unique factor.</span></span>  <span data-ttu-id="97586-120">Poziomy z wysokimi wartościami współczynników mają większą wagę w modelu oceniania.</span><span class="sxs-lookup"><span data-stu-id="97586-120">Levels with higher factor values carry more weight in a rating model.</span></span>

## <a name="specify-job-skills"></a><span data-ttu-id="97586-121">Określanie umiejętności dla zadania</span><span class="sxs-lookup"><span data-stu-id="97586-121">Specify job skills</span></span>
<span data-ttu-id="97586-122">Po wprowadzeniu informacji o zadaniu można wskazać umiejętności, jakie osoba musi mieć przed rozpoczęciem pracy nad zadaniem.</span><span class="sxs-lookup"><span data-stu-id="97586-122">When you enter information about a job, you can specify the skills that a person should have to perform the work required for the job.</span></span>  <span data-ttu-id="97586-123">Oprócz tego można określić żądany poziom każdego poziomu, a także poziom znaczenia dla każdej umiejętności.</span><span class="sxs-lookup"><span data-stu-id="97586-123">In addition you can specify the desired level for each skill as well the level of importance of the skill.</span></span> <span data-ttu-id="97586-124">Dla różnych stanowisk może być wymagana ta sama umiejętność, ale jej poziom ważności może być różny.</span><span class="sxs-lookup"><span data-stu-id="97586-124">Different jobs can require different levels of importance for the same skill.</span></span>

## <a name="enter-skills-for-workers-applicants-or-contacts"></a><span data-ttu-id="97586-125">Wprowadź umiejętności dla pracowników, kandydatów lub osób kontaktowych</span><span class="sxs-lookup"><span data-stu-id="97586-125">Enter skills for workers, applicants, or contacts</span></span>
<span data-ttu-id="97586-126">Można wprowadzić umiejętności docelowe lub rzeczywiste umiejętności pracowników, kandydatów lub osób kontaktowych.</span><span class="sxs-lookup"><span data-stu-id="97586-126">You can enter target skills or actual skills for workers, applicants, or contacts.</span></span> <span data-ttu-id="97586-127">Umiejętność docelowa jest umiejętnością, jaką osoba planuje zdobyć.</span><span class="sxs-lookup"><span data-stu-id="97586-127">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="97586-128">Rzeczywista umiejętność jest umiejętnością, jaką dana osoba aktualnie dysponuje.</span><span class="sxs-lookup"><span data-stu-id="97586-128">An actual skill is a skill that a person currently has.</span></span>

## <a name="skill-mapping-and-skill-mapping-profiles"></a><span data-ttu-id="97586-129"> Mapowanie umiejętności i profile mapowania umiejętności</span><span class="sxs-lookup"><span data-stu-id="97586-129">Skill mapping and Skill mapping profiles</span></span>
<span data-ttu-id="97586-130">Można utworzyć przeszukiwanie mapowania umiejętności do wyszukiwania pracownika, kandydata lub osoby kontaktowej, która posiada kwalifikacje do wykonywania określonego typu zadania.</span><span class="sxs-lookup"><span data-stu-id="97586-130">You can create a skill-mapping search to find a worker, applicant, or contact person who is qualified to perform a specific type of task.</span></span> <span data-ttu-id="97586-131">Algorytm mapowania stanowisk przeszukuje umiejętności, wykształcenie, stanowiska zaufania i doświadczenie w projektach, a następnie zwraca wyniki pasujące do wpisanego zapytania.</span><span class="sxs-lookup"><span data-stu-id="97586-131">Skill-mapping searches look across skills, education, certificates, positions of trust and project experience and return results that match the criteria entered.</span></span>  <span data-ttu-id="97586-132">Na przykład może być potrzebna informacja o tym, którzy pracownicy w organizacji mają świadectwo CPA (Certified Public Accountant).</span><span class="sxs-lookup"><span data-stu-id="97586-132">For example, it might be useful to know which workers in your organization earned their CPA.</span></span>

<span data-ttu-id="97586-133">Profile mapowania umiejętności pozwalają znaleźć bieżących pracowników lub kandydatów z kwalifikacjami, które bezpośrednio odpowiadają potrzebom firmy.</span><span class="sxs-lookup"><span data-stu-id="97586-133">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>  <span data-ttu-id="97586-134">Na przykład można utworzyć profil mapowania umiejętności dla otwartych stanowisk w organizacji.</span><span class="sxs-lookup"><span data-stu-id="97586-134">For example, you could create a skill-mapping profile for an open position in your organization.</span></span> <span data-ttu-id="97586-135">Tworząc profil dla konkretnego stanowiska, a następnie kopiując umiejętności, certyfikaty i wykształcenie z tego zadania w profilu, można szybko przeszukiwać pracowników, kandydatów i osoby, które odpowiadają co najmniej jednemu z kryteriów wprowadzonych w profilu, skontaktować się i wyświetlić listę elementów, których kwalifikacje najlepiej odpowiadają umiejętności wymaganym dla zadania.</span><span class="sxs-lookup"><span data-stu-id="97586-135">By creating a profile for a particular job and copying the skills, education and certificates from that job to the profile, you can quickly search workers, applicants and contact persons who match one or more of the criteria entered on the profile and view a list of the candidates whose skills most closely match the skills required for the job.</span></span>

> <span data-ttu-id="97586-136">**Uwaga** Tylko pracownicy, kandydaci i osoby kontaktowe, które są zaznaczone do uwzględnienia w wyszukiwaniu mapowania umiejętności, mogą być wyświetleni na liście wyników mapowania umiejętności lub uwzględnieni w profilu umiejętności.</span><span class="sxs-lookup"><span data-stu-id="97586-136">**Note** Only workers, applicants, and contact persons who are selected to be included in skill mapping searches can be displayed in a skill-mapping results list, or included in a skill profile.</span></span> <span data-ttu-id="97586-137">Aby uwzględnić pracownika, kandydata lub osobę kontaktową w wyszukiwaniu mapowania, należy wybrać wartość Tak dla opcji **Uwzględnianie w mapowaniu kwalifikacji** na następujących stronach:</span><span class="sxs-lookup"><span data-stu-id="97586-137">To include a worker, applicant, or contact person in skill mapping searches, set the **Include in skill mapping** selection to Yes in the following pages:</span></span>
> 
> + <span data-ttu-id="97586-138">Pracownik</span><span class="sxs-lookup"><span data-stu-id="97586-138">Worker</span></span>
> + <span data-ttu-id="97586-139">Pracownik</span><span class="sxs-lookup"><span data-stu-id="97586-139">Employee</span></span>
> + <span data-ttu-id="97586-140">Kandydat</span><span class="sxs-lookup"><span data-stu-id="97586-140">Applicant</span></span>
> + <span data-ttu-id="97586-141">Kontakty</span><span class="sxs-lookup"><span data-stu-id="97586-141">Contacts</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="97586-142">Analiza braku umiejętności i analiza profilu umiejętności</span><span class="sxs-lookup"><span data-stu-id="97586-142">Skill gap analysis and skill profile analysis</span></span>
<span data-ttu-id="97586-143">Można utworzyć analizę profilu kwalifikacji, aby wyświetlić listę kompetencji dla pracownika, kandydata lub osoby kontaktowej od określonego dnia.</span><span class="sxs-lookup"><span data-stu-id="97586-143">You can create a skill profile analysis to view a list of the competencies of a worker, applicant, or contact person as of a specific date.</span></span> <span data-ttu-id="97586-144">Można utworzyć analizę kwalifikacji do porównania umiejętności danej osoby i umiejętności, które są wymagane dla danego zadania.</span><span class="sxs-lookup"><span data-stu-id="97586-144">You can create a skill gap analysis to compare a person’s skills and the skills that are required for a specific job.</span></span>  



<a name="additional-resources"></a><span data-ttu-id="97586-145">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="97586-145">Additional resources</span></span>
--------

[<span data-ttu-id="97586-146">Zasoby ludzkie</span><span class="sxs-lookup"><span data-stu-id="97586-146">Human resources</span></span>](index.md)




