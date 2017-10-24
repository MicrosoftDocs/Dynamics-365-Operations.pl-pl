---
title: "Konfigurowanie kursów szkoleniowych"
description: "Administratorzy zasobów ludzkich i menedżerowie mogą korzystać z funkcji kursów do obsługi informacji o szkoleniu oferowanym pracownikom."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0ab79e85872c19e30f24e182ea483687ecc0bc09
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-training-courses"></a><span data-ttu-id="b9f19-103">Konfigurowanie kursów szkoleniowych</span><span class="sxs-lookup"><span data-stu-id="b9f19-103">Set up training courses</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="b9f19-104">Administratorzy zasobów ludzkich i menedżerowie mogą korzystać z funkcji kursów do obsługi informacji o szkoleniu oferowanym pracownikom.</span><span class="sxs-lookup"><span data-stu-id="b9f19-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="b9f19-105"> Ustawianie wymagań wstępnych</span><span class="sxs-lookup"><span data-stu-id="b9f19-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="b9f19-106">Następujące informacje są wymagane i muszą być skonfigurowane przed utworzeniem kursów.</span><span class="sxs-lookup"><span data-stu-id="b9f19-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="b9f19-107">**Typy kursów**</span><span class="sxs-lookup"><span data-stu-id="b9f19-107">**Course types**</span></span>

<span data-ttu-id="b9f19-108">Następujące informacje to opcjonalne informacje, które można określić dla kursów.</span><span class="sxs-lookup"><span data-stu-id="b9f19-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="b9f19-109">Jeśli wiadomo, że użytkownik będzie wprowadzał te informacje dla kursów, powinien skonfigurować te informacje przed utworzeniem rekordów kursów.</span><span class="sxs-lookup"><span data-stu-id="b9f19-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="b9f19-110">**Grupy klas**</span><span class="sxs-lookup"><span data-stu-id="b9f19-110">**Classroom groups**</span></span>
-   <span data-ttu-id="b9f19-111">**Grupy kursów**</span><span class="sxs-lookup"><span data-stu-id="b9f19-111">**Course groups**</span></span>
-   <span data-ttu-id="b9f19-112">**Lokalizacje kursu**</span><span class="sxs-lookup"><span data-stu-id="b9f19-112">**Course locations**</span></span>
-   <span data-ttu-id="b9f19-113">**Klasy**</span><span class="sxs-lookup"><span data-stu-id="b9f19-113">**Classrooms**</span></span>
-   <span data-ttu-id="b9f19-114">**Instruktorzy**</span><span class="sxs-lookup"><span data-stu-id="b9f19-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="b9f19-115">Typy kursów</span><span class="sxs-lookup"><span data-stu-id="b9f19-115">Course types</span></span>
<span data-ttu-id="b9f19-116">Typy kursów służą do klasyfikowania kursów według struktury lub zawartości kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="b9f19-117">Typy kursów można tworzyć na stronie **Typy kursów**.</span><span class="sxs-lookup"><span data-stu-id="b9f19-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="b9f19-118">Tworząc rekord kursu należy wybrać typ dla tego kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="b9f19-119">Rodzaj ustawień kursu</span><span class="sxs-lookup"><span data-stu-id="b9f19-119">Course setup type</span></span>
<span data-ttu-id="b9f19-120">W poniższej tabeli wymieniono trzy rodzaje ustawień kursów.</span><span class="sxs-lookup"><span data-stu-id="b9f19-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="b9f19-121">Typy ustawień określają struktury kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b9f19-122">Typ ustawień</span><span class="sxs-lookup"><span data-stu-id="b9f19-122">Setup type</span></span></th>
<th><span data-ttu-id="b9f19-123">Opis</span><span class="sxs-lookup"><span data-stu-id="b9f19-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b9f19-124"><strong>Standardowe</strong></span><span class="sxs-lookup"><span data-stu-id="b9f19-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="b9f19-125">Wybierz ten typ dla kursów, które nie będą miały dziennego terminarza.</span><span class="sxs-lookup"><span data-stu-id="b9f19-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="b9f19-126">Jest to domyślny typ ustawień przy tworzeniu nowego kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9f19-127"><strong>Terminarz</strong></span><span class="sxs-lookup"><span data-stu-id="b9f19-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="b9f19-128">Wybierz ten typ, aby zaplanować szczegóły każdego dnia kursu, który odbywa się przez kilka dni.</span><span class="sxs-lookup"><span data-stu-id="b9f19-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b9f19-129"><strong>Terminarz + sesja</strong></span><span class="sxs-lookup"><span data-stu-id="b9f19-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="b9f19-130">Wybierz ten typ dla bardziej złożonych kursów.</span><span class="sxs-lookup"><span data-stu-id="b9f19-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="b9f19-131">Na przykład można podzielić terminarz kursu na ścieżki i sesje.</span><span class="sxs-lookup"><span data-stu-id="b9f19-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="b9f19-132"><strong>Ścieżka</strong>— Ścieżki to określone obszary tematyczne kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="b9f19-133"><strong>Sesje </strong> – sesje rozdzielają ścieżki i pomagają w określeniu procesów i technik, które są związane z każdą ścieżką.</span><span class="sxs-lookup"><span data-stu-id="b9f19-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="b9f19-134">Zadania kursu</span><span class="sxs-lookup"><span data-stu-id="b9f19-134">Course tasks</span></span>
<span data-ttu-id="b9f19-135">Dla każdego kursu można wykonać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="b9f19-135">For each course, you can complete the following tasks.</span></span>
-   <span data-ttu-id="b9f19-136">Rejestracja uczestników</span><span class="sxs-lookup"><span data-stu-id="b9f19-136">Register participants</span></span>
-   <span data-ttu-id="b9f19-137">Określenie ostatecznego terminu rejestracji</span><span class="sxs-lookup"><span data-stu-id="b9f19-137">Specify a registration deadline</span></span>
-   <span data-ttu-id="b9f19-138">Określenie minimalnej i maksymalnej liczby uczestników</span><span class="sxs-lookup"><span data-stu-id="b9f19-138">Define the minimum and maximum number of participants</span></span>
-   <span data-ttu-id="b9f19-139">Przypisanie lokalizacji i sali</span><span class="sxs-lookup"><span data-stu-id="b9f19-139">Assign a course location and classroom</span></span>
-   <span data-ttu-id="b9f19-140">Hotele rekomendowane uczestnikom kursu</span><span class="sxs-lookup"><span data-stu-id="b9f19-140">Recommend hotels to course participants</span></span>
-   <span data-ttu-id="b9f19-141">Utworzenie opisu kursu, który później może zostać zareklamowany w Samoobsłudze pracownika</span><span class="sxs-lookup"><span data-stu-id="b9f19-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="b9f19-142">**Uwaga** Kurs można usunąć tylko wtedy, gdy nikt się na niego nie zarejestrował.</span><span class="sxs-lookup"><span data-stu-id="b9f19-142">**Note** You can delete a course only if no one has registered for it.</span></span> 
    
## <a name="course-statuses"></a><span data-ttu-id="b9f19-143">Stany kursu</span><span class="sxs-lookup"><span data-stu-id="b9f19-143">Course statuses</span></span>
<span data-ttu-id="b9f19-144">W poniższej tabeli wymieniono możliwe stany i akcje kursu, które można wykonać, gdy kurs ma określony stan.</span><span class="sxs-lookup"><span data-stu-id="b9f19-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b9f19-145">Stan</span><span class="sxs-lookup"><span data-stu-id="b9f19-145">Status</span></span></th>
<th><span data-ttu-id="b9f19-146">Akcje</span><span class="sxs-lookup"><span data-stu-id="b9f19-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b9f19-147"><strong>Utworzony</strong></span><span class="sxs-lookup"><span data-stu-id="b9f19-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="b9f19-148">Wprowadzanie i modyfikowanie informacji o kursie.</span><span class="sxs-lookup"><span data-stu-id="b9f19-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="b9f19-149">Zmienianie stanu kursu na <strong>Otwarty</strong>, dzięki czemu pracownicy mogą rejestrować się na kursie.</span><span class="sxs-lookup"><span data-stu-id="b9f19-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9f19-150"><strong>Otwórz</strong></span><span class="sxs-lookup"><span data-stu-id="b9f19-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="b9f19-151">Rejestrowanie uczestników kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="b9f19-152">Usuwanie uczestników z kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="b9f19-153">Zatwierdzanie uczestników kursu.</span><span class="sxs-lookup"><span data-stu-id="b9f19-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="b9f19-154">Zmienianie stanu kursu na <strong> Zamknięty</strong> lub <strong>Anulowany</strong>.</span><span class="sxs-lookup"><span data-stu-id="b9f19-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="b9f19-155">Planowanie kwestionariuszy dla uczestników ze stanem <strong>Potwierdzony</strong>.</span><span class="sxs-lookup"><span data-stu-id="b9f19-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b9f19-156"><strong>Zamknięto</strong></span><span class="sxs-lookup"><span data-stu-id="b9f19-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="b9f19-157">Kurs można otworzyć ponownie.</span><span class="sxs-lookup"><span data-stu-id="b9f19-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b9f19-158"><strong>Anulowano</strong></span><span class="sxs-lookup"><span data-stu-id="b9f19-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="b9f19-159">Kurs można otworzyć ponownie.</span><span class="sxs-lookup"><span data-stu-id="b9f19-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="b9f19-160">Uczestnicy kursu</span><span class="sxs-lookup"><span data-stu-id="b9f19-160">Course participants</span></span>
<span data-ttu-id="b9f19-161">Uczestnicy kursu to pracownicy, kandydaci lub osoby kontaktowe biorące udział w kursie lub w imprezie szkoleniowej.</span><span class="sxs-lookup"><span data-stu-id="b9f19-161">Course participants are workers, applicants, or contact persons who participate in a training course or event.</span></span> <span data-ttu-id="b9f19-162">Można zarejestrować uczestników tylko na kursach otwartych.</span><span class="sxs-lookup"><span data-stu-id="b9f19-162">You can only register participants for open courses.</span></span> <span data-ttu-id="b9f19-163">Minimalną i maksymalną liczbę uczestników, jaką można zarejestrować na kurs, określa się na skróconej karcie **Ogólne** na stronie **Kursy**.</span><span class="sxs-lookup"><span data-stu-id="b9f19-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="b9f19-164">System Workflow</span><span class="sxs-lookup"><span data-stu-id="b9f19-164">Workflow</span></span>
--------

<span data-ttu-id="b9f19-165">Rejestracje pracowników, którzy zapisali się na kurs poprzez stronę **Samoobsługa pracownika etatowego**, mogą zostać przekierowane przez przepływ pracy celem zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="b9f19-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span>  <span data-ttu-id="b9f19-166">Przepływ pracy dla kursu można ustawić na skróconej karcie **Ogólne** na stronie **Kursy**.</span><span class="sxs-lookup"><span data-stu-id="b9f19-166">A workflow can be assigned to a course on the **General** FastTab on the **Courses** page.</span></span>






