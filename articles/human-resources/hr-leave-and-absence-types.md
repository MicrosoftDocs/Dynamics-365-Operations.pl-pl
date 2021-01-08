---
title: Konfigurowanie typów urlopów i nieobecności
description: Tu opisano konfigurowanie typów urlopów, jakie mogą brać pracownicy w module Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 6e6ca7d04b86232ba48474fcbe288a18995661ae
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420041"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="f373c-103">Konfigurowanie typów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="f373c-103">Configure leave and absence types</span></span>

<span data-ttu-id="f373c-104">Typy urlopów w module Dynamics 365 Human Resources określają różne rodzaje nieobecności, które pracownicy mogą zgłaszać.</span><span class="sxs-lookup"><span data-stu-id="f373c-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="f373c-105">Typy urlopów można dostosować zgodnie z potrzebami swojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="f373c-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="f373c-106">Przykłady typów urlopów:</span><span class="sxs-lookup"><span data-stu-id="f373c-106">Examples of leave types include:</span></span>

- <span data-ttu-id="f373c-107">Płatny urlop (PTO)</span><span class="sxs-lookup"><span data-stu-id="f373c-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="f373c-108">Urlop bezpłatny</span><span class="sxs-lookup"><span data-stu-id="f373c-108">Unpaid leave</span></span>
- <span data-ttu-id="f373c-109">Urlop płatny</span><span class="sxs-lookup"><span data-stu-id="f373c-109">Paid vacation</span></span>
- <span data-ttu-id="f373c-110">Urlop zdrowotny</span><span class="sxs-lookup"><span data-stu-id="f373c-110">Sick leave</span></span>
- <span data-ttu-id="f373c-111">Urlop zdrowotny</span><span class="sxs-lookup"><span data-stu-id="f373c-111">Medical leave</span></span>
- <span data-ttu-id="f373c-112">Urlop rodziny</span><span class="sxs-lookup"><span data-stu-id="f373c-112">Family leave</span></span>
- <span data-ttu-id="f373c-113">Krótkoterminowa niepełnosprawność</span><span class="sxs-lookup"><span data-stu-id="f373c-113">Short-term disability</span></span>
- <span data-ttu-id="f373c-114">Urlop okolicznościowy</span><span class="sxs-lookup"><span data-stu-id="f373c-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="f373c-115">Dodawanie typu urlopu</span><span class="sxs-lookup"><span data-stu-id="f373c-115">Add a leave type</span></span>

1. <span data-ttu-id="f373c-116">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="f373c-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="f373c-117">W obszarze **Konfiguracja** wybierz opcję **Typy urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="f373c-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="f373c-118">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f373c-118">Select **New**.</span></span>

4. <span data-ttu-id="f373c-119">Nadaj nazwę typowi urlopu w polu **Typ**, wybierz przepływ pracy w polu **Identyfikator przepływu pracy** i wprowadź opis w polu **Opis**.</span><span class="sxs-lookup"><span data-stu-id="f373c-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="f373c-120">W obszarze **Ogólne** z listy rozwijanej **Kategoria** wybierz opcję **Brak**, **Zaplanowano** lub **Nie zaplanowano**.</span><span class="sxs-lookup"><span data-stu-id="f373c-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="f373c-121">Wybierz kod zarobków z listy rozwijanej **Kod zarobków**.</span><span class="sxs-lookup"><span data-stu-id="f373c-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="f373c-122">W obszarze **Wymagany kod przyczyny** określ, czy ma być wymagany kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="f373c-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="f373c-123">Jeśli kody przyczyn mają być wymagane, może być konieczne ich dodanie.</span><span class="sxs-lookup"><span data-stu-id="f373c-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="f373c-124">W obszarze **Kody przyczyn** kliknij przycisk **Dodaj**, wybierz kod przyczyny, a następnie obok niego zaznacz pole wyboru **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="f373c-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="f373c-125">W obszarze **Ogranicz dostęp do wybranych ról** określ, czy chcesz ograniczyć dostęp.</span><span class="sxs-lookup"><span data-stu-id="f373c-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="f373c-126">Następnie wybierz role zabezpieczeń w obszarze **Role zabezpieczeń dla tego typu urlopów**.</span><span class="sxs-lookup"><span data-stu-id="f373c-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="f373c-127">Role zabezpieczeń definiuje się w przepływie pracy wybranym w ustawieniu **Identyfikator przepływu pracy** wcześniej w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="f373c-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="f373c-128">W obszarze **Kolor kalendarza** określ, jaki kolor ma być wyświetlany w kalendarzach urlopów i nieobecności dla tego typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-128">Under **Calendar color**, choose what color to display on leave and absence calendars for this leave type.</span></span> 

10. <span data-ttu-id="f373c-129">W obszarze **Relacje zawieszenia** określ, czy chcesz, aby ten typ urlopu miał zawieszać inny typ urlopu, czy był zawieszony przez inny typ urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-129">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="f373c-130">Gdy zostanie złożony wniosek o urlop dla typu urlopu zawieszonego, automatycznie zostanie utworzone zawieszenie urlopu dla typu urlopu zawieszonego.</span><span class="sxs-lookup"><span data-stu-id="f373c-130">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="f373c-131">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f373c-131">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="f373c-132">Konfiguruj reguły typu urlopu</span><span class="sxs-lookup"><span data-stu-id="f373c-132">Configure leave type rules</span></span>

1. <span data-ttu-id="f373c-133">Ustaw opcje zaokrąglania dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-133">Set rounding options for the leave type.</span></span> <span data-ttu-id="f373c-134">Dostępne opcje to **Brak**, **W górę**, **W dół** i **Do najbliższej**.</span><span class="sxs-lookup"><span data-stu-id="f373c-134">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="f373c-135">Można również określić dokładność zaokrąglania dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-135">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="f373c-136">Ustaw dla typu urlopu wartość w polu **Korekta świąt**.</span><span class="sxs-lookup"><span data-stu-id="f373c-136">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="f373c-137">Po wybraniu tej opcji moduł Human Resources będzie wykorzystywał liczbę dni świątecznych przypadających w dniach roboczych do określenia sposobu naliczania czasu wolnego dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-137">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="f373c-138">Jeśli na przykład Boże Narodzenie przypada w poniedziałek, moduł Human Resources odejmie jeden dzień od typu urlopu podczas przetwarzania naliczeń.</span><span class="sxs-lookup"><span data-stu-id="f373c-138">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="f373c-139">Święta ustawia się w kalendarzu czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="f373c-139">You set holidays in the working time calendar.</span></span> <span data-ttu-id="f373c-140">Aby uzyskać więcej informacji, zobacz [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="f373c-140">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="f373c-141">Określ **Typ urlopu przeniesiony na późniejszy okres** na następny okres dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-141">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="f373c-142">Po wybraniu tej opcji wszelkie salda przeniesione zostaną przeniesione do określonego rodzaju urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-142">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="f373c-143">Typ urlopu do przodu musi być również uwzględniony w planie urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="f373c-143">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="f373c-144">Określ **Reguły wygasania** dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-144">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="f373c-145">Po skonfigurowaniu tej opcji możesz wybrać jednostkę dni lub miesięcy i ustawić czas wygaśnięcia.</span><span class="sxs-lookup"><span data-stu-id="f373c-145">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="f373c-146">Można również określić datę wejścia w życie reguły wygasania.</span><span class="sxs-lookup"><span data-stu-id="f373c-146">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="f373c-147">Salda urlopu, które istnieją w momencie wygaśnięcia, zostaną odjęte od typu urlopu i zostaną odzwierciedlone w saldzie urlopu.</span><span class="sxs-lookup"><span data-stu-id="f373c-147">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
 
## <a name="see-also"></a><span data-ttu-id="f373c-148">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="f373c-148">See also</span></span>

- [<span data-ttu-id="f373c-149">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="f373c-149">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="f373c-150">Tworzenie planu urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="f373c-150">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="f373c-151">Tworzenie kalendarza czasu pracy</span><span class="sxs-lookup"><span data-stu-id="f373c-151">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="f373c-152">Wstrzymywanie urlopu</span><span class="sxs-lookup"><span data-stu-id="f373c-152">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)

