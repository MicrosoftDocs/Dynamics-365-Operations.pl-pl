---
title: Tworzenie kalendarza czasu pracy
description: Tu opisano definiowanie kalendarza czasu pracy, świąt i czasu wolnego od pracy w module Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ecabac54134629074ac01944963a037c2cdc63c9
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467176"
---
# <a name="create-a-working-time-calendar"></a><span data-ttu-id="2dd0f-103">Tworzenie kalendarza czasu pracy</span><span class="sxs-lookup"><span data-stu-id="2dd0f-103">Create a working time calendar</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="2dd0f-104">Kalendarz czasu pracy w programie Dynamics 365 Human Resources zawiera dni i godziny, kiedy pracownicy pracują w organizacji.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-104">A working time calendar in Dynamics 365 Human Resources shows the days and hours that employees work in your organization.</span></span> <span data-ttu-id="2dd0f-105">Gdy pracownik prześle wniosek urlopowy, nie musi martwić się o święta ani dni zamknięcia zakładu.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-105">When an employee submits a time-off request, they don't have to worry about holidays and closures.</span></span>

<span data-ttu-id="2dd0f-106">Aby usprawnić obsługę wniosków urlopowych, skonfiguruj te elementy w swojej organizacji:</span><span class="sxs-lookup"><span data-stu-id="2dd0f-106">To streamline time-off requests, configure these items for your organization:</span></span>

- <span data-ttu-id="2dd0f-107">Kalendarz czasu pracy</span><span class="sxs-lookup"><span data-stu-id="2dd0f-107">Working time calendar</span></span>
- <span data-ttu-id="2dd0f-108">Święta i dni wolne od pracy</span><span class="sxs-lookup"><span data-stu-id="2dd0f-108">Holidays and closures</span></span>
- <span data-ttu-id="2dd0f-109">Czas wolny od pracy</span><span class="sxs-lookup"><span data-stu-id="2dd0f-109">Non-work time</span></span>

<span data-ttu-id="2dd0f-110">Dwa ostatnie elementy można dodać podczas konfigurowania kalendarza czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-110">You can add the last two items while you're setting up a working time calendar.</span></span> <span data-ttu-id="2dd0f-111">Można je również konfigurować lub aktualizować osobno.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-111">You can also configure or update them separately.</span></span>

## <a name="set-up-a-working-time-calendar"></a><span data-ttu-id="2dd0f-112">Konfigurowanie kalendarza czasu pracy</span><span class="sxs-lookup"><span data-stu-id="2dd0f-112">Set up a working time calendar</span></span>

<span data-ttu-id="2dd0f-113">Skonfiguruj co najmniej jeden kalendarz czasu pracy, który pokazuje dni i godziny działania zakładu/biura.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-113">Set up at least one working time calendar that shows your days and hours of operation.</span></span> <span data-ttu-id="2dd0f-114">Jeśli istnieją lokalizacje w wielu krajach i regionach, może być konieczne skonfigurowanie kalendarza czasu pracy niezależnie dla każdego obszaru.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-114">If you have locations in multiple countries and regions, you might want to set up a working time calendar for each area.</span></span>

1. <span data-ttu-id="2dd0f-115">Na stronie **Administrowanie organizacją** wybierz opcję **Kalendarze**.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-115">On the **Organization administration** page, select **Calendars**.</span></span>

2. <span data-ttu-id="2dd0f-116">Kliknij przycisk **Nowy** i nadaj kalendarzowi nazwę oraz wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-116">Select **New** and enter a name and description for your calendar.</span></span>

3. <span data-ttu-id="2dd0f-117">W obszarze **Opcje generowania** wybierz dni robocze w organizacji i wprowadź czas pracy.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-117">Under **Generation options**, select the work days for your organization and enter work times.</span></span> 
   - <span data-ttu-id="2dd0f-118">Aby dodać święto lub dzień zamknięcia zakładu, kliknij przycisk **Dodaj** obok pozycji **Święta i dni wolne od pracy**.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-118">To add a holiday or closure, select the **Add** button next to **Holidays and closures**.</span></span>
   - <span data-ttu-id="2dd0f-119">Aby dodać czas wolny od pracy, np. obiady lub przerwy, w obszarze **CZAS WOLNY OD PRACY** kliknij przycisk **Dodaj**, a następnie wprowadź nazwę i przedział czasu.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-119">To add non-work time, like lunches or breaks, select **Add** under **NON-WORK TIME** and enter the name and time range.</span></span>

4. <span data-ttu-id="2dd0f-120">Na karcie **Dni** wybierz opcję **Generuj**, aby wygenerować dni w kalendarzu.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-120">Under **Days**, select **Generate** to generate the days in your calendar.</span></span> <span data-ttu-id="2dd0f-121">Wprowadź zakres dat w kalendarzu, a następnie wybierz opcję **Generuj dni**.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-121">Enter the date range for your calendar and then select **Generate days**.</span></span>

5. <span data-ttu-id="2dd0f-122">Aby dodać harmonogramy pracy, w obszarze **Harmonogram pracy** wybierz opcję **Dodaj**, a następnie wprowadź godziny dla każdego harmonogramu pracy.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-122">To add work schedules, under **Work schedule**, select **Add** and then enter the times for each work schedule.</span></span>

## <a name="configure-holidays-and-closures"></a><span data-ttu-id="2dd0f-123">Konfigurowanie świąt i dni wolnych od pracy</span><span class="sxs-lookup"><span data-stu-id="2dd0f-123">Configure holidays and closures</span></span>

<span data-ttu-id="2dd0f-124">Święta i dni wolne można dodawać lub zmieniać niezależnie od kalendarza czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-124">You can add or change holidays and closures separately from a working time calendar.</span></span>

1. <span data-ttu-id="2dd0f-125">Na stronie **Administrowanie organizacją** wybierz opcję **Święta i dni wolne od pracy**.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-125">On the **Organization administration** page, select **Holidays and closures**.</span></span>

2. <span data-ttu-id="2dd0f-126">Wybierz opcję **Nowy**, a następnie wprowadź nazwę i datę święta lub dnia wolnego od pracy.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-126">Select **New** and enter a name and date for the holiday or closure.</span></span>

## <a name="configure-non-work-time"></a><span data-ttu-id="2dd0f-127">Konfigurowanie czasu wolnego od pracy</span><span class="sxs-lookup"><span data-stu-id="2dd0f-127">Configure non-work time</span></span>

<span data-ttu-id="2dd0f-128">Czas wolny od pracy można dodawać lub zmieniać niezależnie od kalendarza czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-128">You can add or change non-work times separately from a working time calendar.</span></span>

1. <span data-ttu-id="2dd0f-129">Na stronie **Administrowanie organizacją** wybierz opcję **Czas wolny od pracy**.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-129">On the **Organization administration** page, select **Non-work time**.</span></span>

2. <span data-ttu-id="2dd0f-130">Kliknij opcję **Nowy**, a następnie wprowadź nazwę i przedział czasu dla czasu wolnego od pracy.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-130">Select **New** and enter a name and time range for the non-work time.</span></span>

<span data-ttu-id="2dd0f-131">Jeśli włączono funkcję w wersji zapoznawczej o nazwie Korekty urlopów i nieobecności o dni wolne, moduł Human Resources wykorzystuje informacje o świętach i dniach wolnych od pracy do określania liczby dni, o jaką należy skorygować pule urlopów dla pracowników zarejestrowanych w kalendarzu.</span><span class="sxs-lookup"><span data-stu-id="2dd0f-131">If you've enabled the Leave and absence bank holiday corrections preview feature, Human Resources uses holidays and closure dates to determine the number of days to adjust for employees enrolled in the calendar.</span></span>

## <a name="see-also"></a><span data-ttu-id="2dd0f-132">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="2dd0f-132">See also</span></span>

- [<span data-ttu-id="2dd0f-133">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="2dd0f-133">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="2dd0f-134">Konfigurowanie typów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="2dd0f-134">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]