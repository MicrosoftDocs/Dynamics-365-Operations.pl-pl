---
title: Konfigurowanie typów urlopów i nieobecności
description: Tu opisano konfigurowanie typów urlopów, jakie mogą brać pracownicy w module Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1748ec2a888a50af9b9260720dfd439adc4686f9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010242"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="4a17c-103">Konfigurowanie typów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="4a17c-103">Configure leave and absence types</span></span>

<span data-ttu-id="4a17c-104">Typy urlopów w module Dynamics 365 Human Resources określają różne rodzaje nieobecności, które pracownicy mogą zgłaszać.</span><span class="sxs-lookup"><span data-stu-id="4a17c-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="4a17c-105">Typy urlopów można dostosować zgodnie z potrzebami swojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="4a17c-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="4a17c-106">Przykłady typów urlopów:</span><span class="sxs-lookup"><span data-stu-id="4a17c-106">Examples of leave types include:</span></span>

- <span data-ttu-id="4a17c-107">Płatny urlop (PTO)</span><span class="sxs-lookup"><span data-stu-id="4a17c-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="4a17c-108">Urlop bezpłatny</span><span class="sxs-lookup"><span data-stu-id="4a17c-108">Unpaid leave</span></span>
- <span data-ttu-id="4a17c-109">Urlop płatny</span><span class="sxs-lookup"><span data-stu-id="4a17c-109">Paid vacation</span></span>
- <span data-ttu-id="4a17c-110">Urlop zdrowotny</span><span class="sxs-lookup"><span data-stu-id="4a17c-110">Sick leave</span></span>
- <span data-ttu-id="4a17c-111">Urlop zdrowotny</span><span class="sxs-lookup"><span data-stu-id="4a17c-111">Medical leave</span></span>
- <span data-ttu-id="4a17c-112">Urlop rodziny</span><span class="sxs-lookup"><span data-stu-id="4a17c-112">Family leave</span></span>
- <span data-ttu-id="4a17c-113">Krótkoterminowa niepełnosprawność</span><span class="sxs-lookup"><span data-stu-id="4a17c-113">Short-term disability</span></span>
- <span data-ttu-id="4a17c-114">Urlop okolicznościowy</span><span class="sxs-lookup"><span data-stu-id="4a17c-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="4a17c-115">Dodawanie typu urlopu</span><span class="sxs-lookup"><span data-stu-id="4a17c-115">Add a leave type</span></span>

1. <span data-ttu-id="4a17c-116">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="4a17c-117">W obszarze **Konfiguracja** wybierz opcję **Typy urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="4a17c-118">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-118">Select **New**.</span></span>

4. <span data-ttu-id="4a17c-119">Nadaj nazwę typowi urlopu w polu **Typ**, wybierz przepływ pracy w polu **Identyfikator przepływu pracy** i wprowadź opis w polu **Opis**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="4a17c-120">W obszarze **Ogólne** z listy rozwijanej **Kategoria** wybierz opcję **Brak**, **Zaplanowano** lub **Nie zaplanowano**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="4a17c-121">Wybierz kod zarobków z listy rozwijanej **Kod zarobków**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="4a17c-122">W obszarze **Wymagany kod przyczyny** określ, czy ma być wymagany kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="4a17c-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="4a17c-123">Jeśli kody przyczyn mają być wymagane, może być konieczne ich dodanie.</span><span class="sxs-lookup"><span data-stu-id="4a17c-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="4a17c-124">W obszarze **Kody przyczyn** kliknij przycisk **Dodaj**, wybierz kod przyczyny, a następnie obok niego zaznacz pole wyboru **Włączone**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="4a17c-125">W obszarze **Ogranicz dostęp do wybranych ról** określ, czy chcesz ograniczyć dostęp.</span><span class="sxs-lookup"><span data-stu-id="4a17c-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="4a17c-126">Następnie wybierz role zabezpieczeń w obszarze **Role zabezpieczeń dla tego typu urlopów**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="4a17c-127">Role zabezpieczeń definiuje się w przepływie pracy wybranym w ustawieniu **Identyfikator przepływu pracy** wcześniej w tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="4a17c-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="4a17c-128">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-128">Select **Save**.</span></span>

## <a name="configure-preview-features"></a><span data-ttu-id="4a17c-129">Konfigurowanie funkcji w wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="4a17c-129">Configure preview features</span></span>

<span data-ttu-id="4a17c-130">Jeśli włączono obsługę funkcji w wersji zapoznawczej dla urlopów i nieobecności, należy skonfigurować również ich ustawienia.</span><span class="sxs-lookup"><span data-stu-id="4a17c-130">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="4a17c-131">Ustaw opcje zaokrąglania dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="4a17c-131">Set rounding options for the leave type.</span></span> <span data-ttu-id="4a17c-132">Dostępne opcje to **Brak**, **W górę**, **W dół** i **Do najbliższej**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-132">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="4a17c-133">Można również określić dokładność zaokrąglania dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="4a17c-133">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="4a17c-134">Ustaw dla typu urlopu wartość w polu **Korekta świąt**.</span><span class="sxs-lookup"><span data-stu-id="4a17c-134">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="4a17c-135">Po wybraniu tej opcji moduł Human Resources będzie wykorzystywał liczbę dni świątecznych przypadających w dniach roboczych do określenia sposobu naliczania czasu wolnego dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="4a17c-135">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="4a17c-136">Jeśli na przykład Boże Narodzenie przypada w poniedziałek, moduł Human Resources odejmie jeden dzień od typu urlopu podczas przetwarzania naliczeń.</span><span class="sxs-lookup"><span data-stu-id="4a17c-136">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="4a17c-137">Święta ustawia się w kalendarzu czasu pracy.</span><span class="sxs-lookup"><span data-stu-id="4a17c-137">You set holidays in the working time calendar.</span></span> <span data-ttu-id="4a17c-138">Aby uzyskać więcej informacji, zobacz [Tworzenie kalendarza czasu pracy](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="4a17c-138">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="4a17c-139">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4a17c-139">See also</span></span>

- [<span data-ttu-id="4a17c-140">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="4a17c-140">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="4a17c-141">Tworzenie planu urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="4a17c-141">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="4a17c-142">Tworzenie kalendarza czasu pracy</span><span class="sxs-lookup"><span data-stu-id="4a17c-142">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)