---
title: Konfigurowanie parametrów urlopów i nieobecności
description: W programie Dynamics 365 Human Resources można definiować parametry urlopów i nieobecności.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c3a3f4a8a1fa0b5dbc4869f81f091cc66437e978
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6056859"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="48b01-103">Konfigurowanie parametrów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="48b01-103">Configure leave and absence parameters</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="48b01-104">Przed skonfigurowaniem urlopów i nieobecności w module Dynamics 365 Human Resources dobrze jest sprawdzić ustawienia wszystkich powiązanych parametrów tego modułu, w tym takich jak:</span><span class="sxs-lookup"><span data-stu-id="48b01-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="48b01-105">Numeracja wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="48b01-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="48b01-106">Ustawienia rozporządzenia dotyczącego zwolnień chorobowych i rodzinnych (FMLA)</span><span class="sxs-lookup"><span data-stu-id="48b01-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="48b01-107">Ustawienia obszaru Samoobsługa pracownika etatowego dla wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="48b01-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="48b01-108">Parametry urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="48b01-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="48b01-109">Wyświetlanie i zmiana parametrów modułu Human Resources</span><span class="sxs-lookup"><span data-stu-id="48b01-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="48b01-110">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="48b01-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="48b01-111">W obszarze **Konfiguracja** wybierz opcję **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="48b01-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="48b01-112">Na karcie **Numery kolejne** sprawdź wartość **Kod sekwencji numerów** dla wartości **Identyfikator wniosku urlopowego** i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="48b01-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="48b01-113">To ustawienie określa numerację używaną do automatycznego przypisywania identyfikatorów do wniosków urlopowych.</span><span class="sxs-lookup"><span data-stu-id="48b01-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="48b01-114">Na karcie **FMLA** sprawdź ustawienia dotyczące rozporządzenia FMLA i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="48b01-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="48b01-115">Na karcie **Samoobsługa pracownika etatowego** wskaż, czy kierownicy mogą wprowadzać wnioski urlopowe w imieniu swoich pracowników.</span><span class="sxs-lookup"><span data-stu-id="48b01-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="48b01-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48b01-116">Select **Save**.</span></span>

>[!IMPORTANT]
><span data-ttu-id="48b01-117">Funkcja wyświetlania urlopów i nieobecności w różnych firmach jest obecnie dostępna w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="48b01-117">Viewing leave and absence across companies is currently in preview.</span></span> <span data-ttu-id="48b01-118">Aby wyświetlić opcję dla urlopów i nieobecności, należy włączyć funkcję w środowisku **piaskownicy**.</span><span class="sxs-lookup"><span data-stu-id="48b01-118">You'll need to enable it in your **Sandbox** environment to display the option for leave and absence.</span></span> <span data-ttu-id="48b01-119">Aby uzyskać więcej informacji na temat włączania funkcji w wersji zapoznawczej, zobacz temat [Zarządzanie funkcjami](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="48b01-119">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="view-and-change-human-resources-shared-parameters"></a><span data-ttu-id="48b01-120">Wyświetlanie i zmiana Udostępnianych parametrów zasobów ludzkich</span><span class="sxs-lookup"><span data-stu-id="48b01-120">View and change Human resources shared parameters</span></span>

1. <span data-ttu-id="48b01-121">Na stronie **Zarządzanie personelem** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="48b01-121">On the **Personnel management** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="48b01-122">W obszarze **Konfiguracja** wybierz opcję **Udostępniane parametry zasobów ludzkich**.</span><span class="sxs-lookup"><span data-stu-id="48b01-122">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="48b01-123">Na karcie **Zaawansowany dostęp** wybierz **Tak** dla opcji **Włącz międzyfirmowe wyświetlanie urlopu**, aby można było wyświetlać urlopy w różnych firmach.</span><span class="sxs-lookup"><span data-stu-id="48b01-123">On the **Advance access** tab, select **Yes** for **Enable cross company leave view** to allow leave to be viewed across company.</span></span>

4. <span data-ttu-id="48b01-124">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48b01-124">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="48b01-125">Zobacz i zmień parametry urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="48b01-125">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="48b01-126">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="48b01-126">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="48b01-127">W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="48b01-127">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="48b01-128">Na karcie **Ogólne** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="48b01-128">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="48b01-129">Określ **Jednostkę dla urlopu i nieobecności** na godziny lub dni.</span><span class="sxs-lookup"><span data-stu-id="48b01-129">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="48b01-130">Jeśli wybrano dni, można wybrać opcję **Włącz definicję połowy dnia**, aby umożliwić pracownikom wybranie pierwszej lub drugiej połowy dnia w swoich żądaniach czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="48b01-130">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="48b01-131">Wybierz **Data rozpoczęcia miesięcy pracy**, aby określić, kiedy mają obowiązywać stawki naliczania dla planów urlopów za pomocą miesięcy pracy.</span><span class="sxs-lookup"><span data-stu-id="48b01-131">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="48b01-132">Umożliwia wybranie opcji **Obliczanie salda** w celu wyświetlenia widoku sald na dzień dzisiejszy lub w okresie naliczania.</span><span class="sxs-lookup"><span data-stu-id="48b01-132">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="48b01-133">Wybranie **Saldo na dzień dzisiejszy** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i wniosków na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="48b01-133">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="48b01-134">Wybranie **Saldo na okres naliczania** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i żądań podczas okresu naliczania zdefiniowanego przez częstotliwość w planie urlopu.</span><span class="sxs-lookup"><span data-stu-id="48b01-134">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="48b01-135">Umożliwia ustawienie godziny rozpoczęcia zadania wsadowego przeniesienia na następny okres.</span><span class="sxs-lookup"><span data-stu-id="48b01-135">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="48b01-136">Wybierz **Tak** w polu **Umożliw pracownikom zakup urlopu** oraz **Umożliw pracownikom sprzedaż urlopu**.</span><span class="sxs-lookup"><span data-stu-id="48b01-136">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="48b01-137">Jeśli wybierzesz opcję **Tak** dla tych opcji, możesz utworzyć zasady kupna i sprzedaży, a następnie umożliwić pracownikom przesyłanie próśb dot. kupna i sprzedaży urlopu.</span><span class="sxs-lookup"><span data-stu-id="48b01-137">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="48b01-138">Konfigurowanie parametrów kalendarza</span><span class="sxs-lookup"><span data-stu-id="48b01-138">Configure calendar parameters</span></span>

1. <span data-ttu-id="48b01-139">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="48b01-139">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="48b01-140">W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="48b01-140">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="48b01-141">Na karcie **Kalendarz** w razie potrzeby zmień ustawienia kalendarza.</span><span class="sxs-lookup"><span data-stu-id="48b01-141">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="48b01-142">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="48b01-142">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="48b01-143">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="48b01-143">See also</span></span>

- [<span data-ttu-id="48b01-144">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="48b01-144">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]