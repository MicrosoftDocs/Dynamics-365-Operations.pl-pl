---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Talent - Core HR (10 września 2018 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: 59cb0203422b7d81b5ca0077370fd9cbdb4a7f89
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010092"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-september-10-2018"></a><span data-ttu-id="7fdef-103">Nowości i zmiany w rozwiązaniu Dynamics 365 Talent: Core HR (10 września 2018 r.)</span><span class="sxs-lookup"><span data-stu-id="7fdef-103">What's new or changed in Dynamics 365 Talent: Core HR (September 10, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7fdef-104">**Kompilacja 8.1.138.0**</span><span class="sxs-lookup"><span data-stu-id="7fdef-104">**Build 8.1.138.0**</span></span>

<span data-ttu-id="7fdef-105">W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="7fdef-105">This topic describes features that are either new or changed in Microsoft Dynamics 365 Talent: Core HR.</span></span>

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a><span data-ttu-id="7fdef-106">Możliwość określania konkretnej pory dnia we wnioskach o czas wolny (połowy dnia)</span><span class="sxs-lookup"><span data-stu-id="7fdef-106">Allow specific time of day on time-off requests (half days)</span></span>

<span data-ttu-id="7fdef-107">Jeśli obszar roboczy Urlopy i nieobecności jest skonfigurowany tak, aby wnioski o czas wolny były przesyłane w dniach, teraz można włączyć określanie połowy dni.</span><span class="sxs-lookup"><span data-stu-id="7fdef-107">If leave and absence is set up so that time off is submitted in days, you can now also enable a half-day definition.</span></span> <span data-ttu-id="7fdef-108">Odtąd gdy użytkownicy przesyłają wnioski o czas wolny, mogą wskazać, czy proszą o zwolnienie na pierwszą, czy drugą połowę dnia.</span><span class="sxs-lookup"><span data-stu-id="7fdef-108">Then, when users submit time-off requests, they can specify whether they are requesting the first half or the second half of the day off.</span></span>

<span data-ttu-id="7fdef-109">Domyślnie ta opcja jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="7fdef-109">By default, this option is turned off.</span></span> <span data-ttu-id="7fdef-110">Aby pracownicy mogli prosić o czas wolny na pierwszą lub drugą połowę dnia, należy włączyć tę opcję w obszarze **Urlopy i nieobecności** w oknie Parametry zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="7fdef-110">For employees to request the first half or second half of the day off, you must turn on this option in the **Leave and absence** area of Human resources parameters.</span></span>

<span data-ttu-id="7fdef-111">Uprawnieniem zabezpieczeń dla tej funkcji jest Obsługa parametrów zasobów ludzkich.</span><span class="sxs-lookup"><span data-stu-id="7fdef-111">The security privilege for this feature is Maintain Human Resources Parameters.</span></span>

## <a name="validation-of-leave-and-absence-entries"></a><span data-ttu-id="7fdef-112">Sprawdzanie poprawności wpisów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="7fdef-112">Validation of leave and absence entries</span></span>

<span data-ttu-id="7fdef-113">Zależnie od konfiguracji funkcjonalności urlopów pracownicy, którzy próbują przesłać wnioski o czas wolny na okres dłuższy niż ich dzień roboczy, otrzymują komunikat ostrzegawczy.</span><span class="sxs-lookup"><span data-stu-id="7fdef-113">Depending on how leave is configured, employees who try to submit a time-off request that is longer than their work day receive a warning message.</span></span> <span data-ttu-id="7fdef-114">Innymi słowy są ostrzegani, jeśli próbują wziąć więcej wolnego niż jeden pełny dzień w danym dniu.</span><span class="sxs-lookup"><span data-stu-id="7fdef-114">In other words, they are warned if they try to take more than a full day off on any given date.</span></span>

<span data-ttu-id="7fdef-115">Ta funkcja weryfikacji jest zawsze włączona.</span><span class="sxs-lookup"><span data-stu-id="7fdef-115">This validation is always turned on.</span></span> <span data-ttu-id="7fdef-116">Ilekroć pracownicy przekroczą zdefiniowany próg dzienny, otrzymują ostrzeżenie w swoich wnioskach o czas wolny.</span><span class="sxs-lookup"><span data-stu-id="7fdef-116">Any time that employees exceed the day threshold that is defined, they receive a warning in their time-off request.</span></span>

## <a name="additional-fields-for-conditional-statements-in-workflows"></a><span data-ttu-id="7fdef-117">Dodatkowe pola instrukcji warunkowych w przepływach pracy</span><span class="sxs-lookup"><span data-stu-id="7fdef-117">Additional fields for conditional statements in workflows</span></span>

<span data-ttu-id="7fdef-118">Dodano więcej pól w instrukcjach warunkowych i symbolach zastępczych w kilku przepływach pracy w aplikacji Core HR.</span><span class="sxs-lookup"><span data-stu-id="7fdef-118">Additional fields have been added to conditional statements and placeholders for several workflows in Core HR.</span></span>

<span data-ttu-id="7fdef-119">Następujące pola zostały dodane do przepływów pracy wynagradzania, rozwiązywania stosunku pracy i przenoszenia:</span><span class="sxs-lookup"><span data-stu-id="7fdef-119">The following fields have been added to the compensation, termination, and transfer workflows:</span></span>

- <span data-ttu-id="7fdef-120">EmploymentType</span><span class="sxs-lookup"><span data-stu-id="7fdef-120">EmploymentType</span></span>
- <span data-ttu-id="7fdef-121">LegalEntity</span><span class="sxs-lookup"><span data-stu-id="7fdef-121">LegalEntity</span></span>
- <span data-ttu-id="7fdef-122">AdjustedWorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="7fdef-122">AdjustedWorkerStartDate</span></span>
- <span data-ttu-id="7fdef-123">EmployerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="7fdef-123">EmployerNoticeAmount</span></span>
- <span data-ttu-id="7fdef-124">EmployerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="7fdef-124">EmployerUnitOfNotice</span></span>
- <span data-ttu-id="7fdef-125">TransitionDate</span><span class="sxs-lookup"><span data-stu-id="7fdef-125">TransitionDate</span></span>
- <span data-ttu-id="7fdef-126">WorkerNoticeAmount</span><span class="sxs-lookup"><span data-stu-id="7fdef-126">WorkerNoticeAmount</span></span>
- <span data-ttu-id="7fdef-127">WorkerStartDate</span><span class="sxs-lookup"><span data-stu-id="7fdef-127">WorkerStartDate</span></span>
- <span data-ttu-id="7fdef-128">WorkerUnitOfNotice</span><span class="sxs-lookup"><span data-stu-id="7fdef-128">WorkerUnitOfNotice</span></span>
- <span data-ttu-id="7fdef-129">ProbationEndDate</span><span class="sxs-lookup"><span data-stu-id="7fdef-129">ProbationEndDate</span></span>
- <span data-ttu-id="7fdef-130">Pozycja</span><span class="sxs-lookup"><span data-stu-id="7fdef-130">Position</span></span>
- <span data-ttu-id="7fdef-131">Organizacja zawodowa</span><span class="sxs-lookup"><span data-stu-id="7fdef-131">Union</span></span>
- <span data-ttu-id="7fdef-132">Dział</span><span class="sxs-lookup"><span data-stu-id="7fdef-132">Department</span></span>
- <span data-ttu-id="7fdef-133">PositionType</span><span class="sxs-lookup"><span data-stu-id="7fdef-133">PositionType</span></span>
- <span data-ttu-id="7fdef-134">CompLocation</span><span class="sxs-lookup"><span data-stu-id="7fdef-134">CompLocation</span></span>
- <span data-ttu-id="7fdef-135">Tytuł</span><span class="sxs-lookup"><span data-stu-id="7fdef-135">Title</span></span>
- <span data-ttu-id="7fdef-136">Funkcja</span><span class="sxs-lookup"><span data-stu-id="7fdef-136">Job</span></span>
- <span data-ttu-id="7fdef-137">JobType</span><span class="sxs-lookup"><span data-stu-id="7fdef-137">JobType</span></span>
- <span data-ttu-id="7fdef-138">JobFamily</span><span class="sxs-lookup"><span data-stu-id="7fdef-138">JobFamily</span></span>
- <span data-ttu-id="7fdef-139">JobFunction</span><span class="sxs-lookup"><span data-stu-id="7fdef-139">JobFunction</span></span>

<span data-ttu-id="7fdef-140">Następujące pola zostały dodane do przepływu pracy stanowiska:</span><span class="sxs-lookup"><span data-stu-id="7fdef-140">The following fields have been added to the position workflow:</span></span>

- <span data-ttu-id="7fdef-141">Pozycja</span><span class="sxs-lookup"><span data-stu-id="7fdef-141">Position</span></span>
- <span data-ttu-id="7fdef-142">Organizacja zawodowa</span><span class="sxs-lookup"><span data-stu-id="7fdef-142">Union</span></span>
- <span data-ttu-id="7fdef-143">Dział</span><span class="sxs-lookup"><span data-stu-id="7fdef-143">Department</span></span>
- <span data-ttu-id="7fdef-144">PositionType</span><span class="sxs-lookup"><span data-stu-id="7fdef-144">PositionType</span></span>
- <span data-ttu-id="7fdef-145">CompLocation</span><span class="sxs-lookup"><span data-stu-id="7fdef-145">CompLocation</span></span>
- <span data-ttu-id="7fdef-146">Tytuł</span><span class="sxs-lookup"><span data-stu-id="7fdef-146">Title</span></span>
- <span data-ttu-id="7fdef-147">Funkcja</span><span class="sxs-lookup"><span data-stu-id="7fdef-147">Job</span></span>
- <span data-ttu-id="7fdef-148">JobType</span><span class="sxs-lookup"><span data-stu-id="7fdef-148">JobType</span></span>
- <span data-ttu-id="7fdef-149">JobFamily</span><span class="sxs-lookup"><span data-stu-id="7fdef-149">JobFamily</span></span>
- <span data-ttu-id="7fdef-150">JobFunction</span><span class="sxs-lookup"><span data-stu-id="7fdef-150">JobFunction</span></span>

<span data-ttu-id="7fdef-151">Pola w instrukcjach warunkowych i symbolach zastępczych są dostępne dla wszystkich użytkowników, którzy mają dostęp do konfigurowania opisanych powyżej przepływy pracy.</span><span class="sxs-lookup"><span data-stu-id="7fdef-151">Fields in conditional statements and placeholders are available to all users who have access to configure the previously mentioned workflows.</span></span>

## <a name="navigation-to-attract-from-personnel-management"></a><span data-ttu-id="7fdef-152">Przechodzenie do aplikacji Attract z obszaru roboczego Zarządzanie pracownikami</span><span class="sxs-lookup"><span data-stu-id="7fdef-152">Navigation to Attract from personnel management</span></span>

<span data-ttu-id="7fdef-153">Jeżeli w obszarze roboczym Zarządzanie personelem nie widać skonfigurowanej aplikacji Attract, sekcja **Kandydaci do zatrudnienia** kieruje użytkowników do rozpoczęcia pracy z aplikacją Attract, podczas gdy wcześniej był wyświetlany komunikat „Brak elementów do wyświetlenia w tym widoku”.</span><span class="sxs-lookup"><span data-stu-id="7fdef-153">In personnel management, if Attract hasn't been set up, the **Candidates to hire** section directs users to get started with Attract instead of showing the message, "We didn't find anything to show here."</span></span>

## <a name="other-changes"></a><span data-ttu-id="7fdef-154">Inne zmiany</span><span class="sxs-lookup"><span data-stu-id="7fdef-154">Other changes</span></span>

<span data-ttu-id="7fdef-155">Ta wersja zawiera kilka dodatkowych poprawek błędów:</span><span class="sxs-lookup"><span data-stu-id="7fdef-155">This release includes several additional bug fixes:</span></span>

- <span data-ttu-id="7fdef-156">Podczas zatrudniania zleceniobiorcy karta **Wynagrodzenie** nie powinna być dostępne na stronie wniosku/akcji.</span><span class="sxs-lookup"><span data-stu-id="7fdef-156">When a contractor is hired, the **Compensation** tab should not be available on the request/action page.</span></span>
- <span data-ttu-id="7fdef-157">W trakcie procesu wnioskowania o zakończenie zatrudnienia można kontynuować dopiero wtedy, gdy wszystkie wymagane pola będą zawierały dane.</span><span class="sxs-lookup"><span data-stu-id="7fdef-157">During the request termination process, you can't continue until all required fields contain data.</span></span>
- <span data-ttu-id="7fdef-158">Rozwiązano problemy z porządkiem sortowania i wyświetlaniem dat w funkcjach analizy w obszarze roboczym Zarządzanie pracownikami.</span><span class="sxs-lookup"><span data-stu-id="7fdef-158">Sort order and date display issues on the Personnel management analytics have been addressed.</span></span>
