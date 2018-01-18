---
title: "Omówienie zarządzania urlopami i nieobecnościami"
description: "Ten temat zawiera omówienie modułu Zarządzanie urlopami i nieobecnościami. Moduł ten oferuje elastyczną architekturę definiowania procesu zarządzania nieobecnościami. Można tworzyć plany urlopów i nieobecności w celu określenia, jak pracownikom jest naliczany lub przyznawany czas wolny."
author: ryansandness
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: 331e3eae38d3abc9fa545e84d18de91b81352af9
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---
# <a name="leave-and-absence-management-overview"></a><span data-ttu-id="59b96-105">Omówienie zarządzania urlopami i nieobecnościami</span><span class="sxs-lookup"><span data-stu-id="59b96-105">Leave and absence management overview</span></span>

<span data-ttu-id="59b96-106">Moduł **Zarządzanie urlopami i nieobecnościami** oferuje elastyczną architekturę definiowania procesu zarządzania nieobecnościami.</span><span class="sxs-lookup"><span data-stu-id="59b96-106">The **Leave and absence management** module offers a flexible framework for defining the absence management process.</span></span> <span data-ttu-id="59b96-107">Można tworzyć plany urlopów i nieobecności w celu określenia, jak pracownikom jest naliczany lub przyznawany czas wolny.</span><span class="sxs-lookup"><span data-stu-id="59b96-107">Leave and absence plans can be created to determine how employees accrue or are granted time off.</span></span> <span data-ttu-id="59b96-108">Gdy pracownicy zostaną zarejestrowani w planie, mogą przesyłać wnioski o czas wolny do zatwierdzenia przez menedżerów.</span><span class="sxs-lookup"><span data-stu-id="59b96-108">After employees are enrolled in a plan, they can submit time-off requests for approval by managers.</span></span> <span data-ttu-id="59b96-109">Funkcja śledzenia urlopów umożliwia zarówno menedżerom pierwszego szczebla, jak i menedżerom kadr (HR) sprawdzanie, kto korzysta z czasu wolnego i ile ma jeszcze czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="59b96-109">Leave tracking lets both first-level managers and Human Resources (HR) managers see who is taking time off and how much time off each employee still has.</span></span>  

<span data-ttu-id="59b96-110">Moduł Zarządzanie urlopami i nieobecnościami udostępnia następujące funkcje:</span><span class="sxs-lookup"><span data-stu-id="59b96-110">Leave and absence management provides the following features:</span></span> 

- <span data-ttu-id="59b96-111">**Definiowanie typów urlopów i nieobecności.**</span><span class="sxs-lookup"><span data-stu-id="59b96-111">**Define leave and absence types.**</span></span>

    <span data-ttu-id="59b96-112">Typy urlopów określają różne rodzaje nieobecności, które pracownicy mogą zgłaszać.</span><span class="sxs-lookup"><span data-stu-id="59b96-112">Leave types define the various types of absences that employees can report.</span></span> <span data-ttu-id="59b96-113">Ponieważ te typy są definiowane przez użytkowników, mogą być dostosowane do organizacji.</span><span class="sxs-lookup"><span data-stu-id="59b96-113">Because these types are user-defined, they can be tailored to your organization.</span></span> <span data-ttu-id="59b96-114">Popularne typy urlopów to m.in. płatny urlop (PTO), urlop, urlop z powodu krótkotrwałej niezdolności do pracy, urlop z powodu obowiązków sędziego przysięgłego (specyficzny dla Stanów Zjednoczonych) i urlop okolicznościowy.</span><span class="sxs-lookup"><span data-stu-id="59b96-114">Some typical leave types include paid time off (PTO), leave, short-term disability, jury duty (this leave type is specific to the United States), and bereavement.</span></span> 

- <span data-ttu-id="59b96-115">**Definiowanie warstwowych planów urlopów i nieobecności uwzględniających specyfikę firmy.**</span><span class="sxs-lookup"><span data-stu-id="59b96-115">**Define leave and absence plans that are tiered to fit your business.**</span></span>

    <span data-ttu-id="59b96-116">Plany urlopów i nieobecności można zdefiniować tak, aby naliczanie odbywało się z określoną częstotliwością, na przykład raz w roku, co miesiąc czy dwa razy w miesiącu.</span><span class="sxs-lookup"><span data-stu-id="59b96-116">Leave and absence plans can be defined so that accrual occurs at specific frequencies, such as annually, monthly, or semimonthly.</span></span> <span data-ttu-id="59b96-117">Plany można również zdefiniować jako przydziały, gdzie jedno naliczanie odbywa się w określonym dniu.</span><span class="sxs-lookup"><span data-stu-id="59b96-117">Plans can also be defined as a grant, where a single accrual occurs on a specific date.</span></span> 

    <span data-ttu-id="59b96-118">Plany urlopów często zawierają warstwy, w których pewne grupy pracowników otrzymują dodatkowe świadczenia zależne od ilości czasu przynależności do organizacji.</span><span class="sxs-lookup"><span data-stu-id="59b96-118">Leave plans often contain tiers, where some groups of employees receive additional benefits, based on the amount of time that they have been with the organization.</span></span> <span data-ttu-id="59b96-119">Te warstwy są definiowane przez użytkowników i umożliwiają automatyczne rejestrowanie na godziny dodatkowych świadczeń w oparciu o ustalone kryteria dat.</span><span class="sxs-lookup"><span data-stu-id="59b96-119">These user-defined tiers enable automatic enrollment in additional benefit hours, based on the date criteria that are defined.</span></span> <span data-ttu-id="59b96-120">W planach urlopów można również skonfigurować wymuszanie maksymalnej ilości przeniesienia lub minimalnego salda, tak aby zapobiec wykorzystywaniu przez pracowników większej liczby godzin świadczeń, niż zostało naliczone.</span><span class="sxs-lookup"><span data-stu-id="59b96-120">Leave plans can also be configured to enforce a maximum carry-over amount or a minimum balance, to prevent employees from using more benefit hours than they have accrued.</span></span> 

    <span data-ttu-id="59b96-121">Typowe plany urlopów obejmują plany warstwowe, które przyznają 80 godzin płatnego urlopu nowym pracownikom, ale 120 godzin po upływie 60 miesięcy pracy.</span><span class="sxs-lookup"><span data-stu-id="59b96-121">Typical leave plans include tiered plans that grant a benefit of 80 hours of PTO to new employees but a benefit of 120 hours after 60 months of service.</span></span> <span data-ttu-id="59b96-122">Dodatkowe plany mogą przyznawać urlopy na żądanie lub świadczenia zależne od stanowiska, na przykład urlopy tylko dla członków wyższej kadry kierowniczej.</span><span class="sxs-lookup"><span data-stu-id="59b96-122">Additional plans might grant floating holidays or position-based benefits, such as executive-only benefit hours.</span></span>

- <span data-ttu-id="59b96-123">**Rejestrowanie pracowników w planach urlopów i zwolnień indywidualnie lub w ramach przypisania grupowego opartego na kryteriach stanowiska.**</span><span class="sxs-lookup"><span data-stu-id="59b96-123">**Enroll employees in leave and absence plans individually or through mass assignment that is based on job criteria.**</span></span>

    <span data-ttu-id="59b96-124">Można użyć kilku filtrów związanych ze stanowiskami, aby przypisać grupę pracowników do planu urlopów.</span><span class="sxs-lookup"><span data-stu-id="59b96-124">Several job-related filters can be used to assign a group of employees to a leave plan.</span></span> <span data-ttu-id="59b96-125">Menedżerowie ds. HR mogą wyświetlać pracownika, aby zobaczyć, w jakich planach urlopów i nieobecności jest zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="59b96-125">HR managers can view an employee to see what leave and absence plans the employee is enrolled in.</span></span> <span data-ttu-id="59b96-126">Alternatywie menedżerowie ds. HR mogą wyświetlać wszystkie plany i odnośne rejestracje pracowników.</span><span class="sxs-lookup"><span data-stu-id="59b96-126">Alternatively, HR managers can view all plans and the related employee enrollments.</span></span>

- <span data-ttu-id="59b96-127">**Zawieszanie planów urlopów i nieobecności.**</span><span class="sxs-lookup"><span data-stu-id="59b96-127">**Suspend leave and absence plans.**</span></span>

    <span data-ttu-id="59b96-128">Plany urlopów i nieobecności można zawieszać, aby je zdezaktywować i zapobiec dodatkowym naliczeniom.</span><span class="sxs-lookup"><span data-stu-id="59b96-128">Leave and absence plans can be suspended to make them inactive and prevent additional accruals.</span></span> <span data-ttu-id="59b96-129">Naliczenia zostają zawieszone dla pracowników, gdy kończy się ich zatrudnienie.</span><span class="sxs-lookup"><span data-stu-id="59b96-129">Accruals are suspended for employees if their employment ends.</span></span>  

- <span data-ttu-id="59b96-130">**Dostosowywanie uprawnień i przydziałów.**</span><span class="sxs-lookup"><span data-stu-id="59b96-130">**Adjust entitlements and grants.**</span></span>

    <span data-ttu-id="59b96-131">Pracownik może zostać zarejestrowany w wyższej warstwie planu przy użyciu daty specyficznej dla pracownika, co zastąpi domyślną ofertę planu dla pracownika.</span><span class="sxs-lookup"><span data-stu-id="59b96-131">An employee can be enrolled in a higher plan tier by using a worker-specific date to override the employee's default plan offering.</span></span> <span data-ttu-id="59b96-132">Pracownicy mogą otrzymywać ręczne korekty salda urlopów i nieobecności w momencie rejestrowania w planie lub też dział kadr może wprowadzać ręczne korekty w dowolnym momencie.</span><span class="sxs-lookup"><span data-stu-id="59b96-132">Employees can receive a manual adjustment to their leave and absence balance at the time of plan enrollment, or HR can make a manual adjustment at any time.</span></span> 

- <span data-ttu-id="59b96-133">**Stosowanie przepływu pracy do wniosków o czas wolny.**</span><span class="sxs-lookup"><span data-stu-id="59b96-133">**Apply a workflow to time-off requests.**</span></span>

     <span data-ttu-id="59b96-134">Przepływ pracy może być dostosowywany i stosowany do wniosków o czas wolny zgodnie z wymaganiami organizacji.</span><span class="sxs-lookup"><span data-stu-id="59b96-134">A workflow can be customized and applied to time-off requests to meet the organization’s requirements.</span></span>  

- <span data-ttu-id="59b96-135">**Śledzenie salda nieobecności pracowników.**</span><span class="sxs-lookup"><span data-stu-id="59b96-135">**Track employee absence balances.**</span></span>

    <span data-ttu-id="59b96-136">Pracownicy, ich menedżerowie i dział kadr mogą wyświetlać salda urlopów i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="59b96-136">Employees, their manager, and HR can view leave and absence balances.</span></span> <span data-ttu-id="59b96-137">Dział kadr może używać interaktywnych raportów do śledzenia rejestracji w planach i sald czasu wolnego według typów.</span><span class="sxs-lookup"><span data-stu-id="59b96-137">HR can use interactive reports to track plan enrollments and time-off balances by type.</span></span> 

- <span data-ttu-id="59b96-138">**Przesyłanie wniosków o czas wolny.**</span><span class="sxs-lookup"><span data-stu-id="59b96-138">**Submit time-off requests.**</span></span>

    <span data-ttu-id="59b96-139">Pracownicy mogą przesyłać wnioski o czas wolny względem dostępnej dla siebie liczby godzin.</span><span class="sxs-lookup"><span data-stu-id="59b96-139">Employees can submit time-off requests against their available hours.</span></span> <span data-ttu-id="59b96-140">Wnioski mogą być prostymi wnioskami na jeden dzień lub obejmować wiele dni, z kilkoma typami urlopów i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="59b96-140">Requests can be simple single-day requests or multiple-day requests that include multiple leave and absence types.</span></span> <span data-ttu-id="59b96-141">Jeśli funkcja przepływu pracy nie jest włączona, wnioski są automatycznie zatwierdzane.</span><span class="sxs-lookup"><span data-stu-id="59b96-141">If a workflow isn't enabled, the requests are automatically approved.</span></span> <span data-ttu-id="59b96-142">Gdy funkcja przepływu pracy jest włączona, zatwierdzenie może odbywać się automatycznie lub wymagać podpisania, zależnie od konfiguracji przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="59b96-142">If a workflow is enabled, the approval can be automatic, or it can require sign-off, depending on the workflow configuration.</span></span>

