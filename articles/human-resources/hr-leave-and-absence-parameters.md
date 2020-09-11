---
title: Konfigurowanie parametrów urlopów i nieobecności
description: W programie Dynamics 365 Human Resources można definiować parametry urlopów i nieobecności.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
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
ms.openlocfilehash: 196c3901b5bc19f73b882bac7d3361e5bcc37e07
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712383"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="9795c-103">Konfigurowanie parametrów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="9795c-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="9795c-104">Przed skonfigurowaniem urlopów i nieobecności w module Dynamics 365 Human Resources dobrze jest sprawdzić ustawienia wszystkich powiązanych parametrów tego modułu, w tym takich jak:</span><span class="sxs-lookup"><span data-stu-id="9795c-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="9795c-105">Numeracja wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="9795c-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="9795c-106">Ustawienia rozporządzenia dotyczącego zwolnień chorobowych i rodzinnych (FMLA)</span><span class="sxs-lookup"><span data-stu-id="9795c-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="9795c-107">Ustawienia obszaru Samoobsługa pracownika etatowego dla wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="9795c-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="9795c-108">Parametry urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="9795c-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="9795c-109">Wyświetlanie i zmiana parametrów modułu Human Resources</span><span class="sxs-lookup"><span data-stu-id="9795c-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="9795c-110">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="9795c-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="9795c-111">W obszarze **Konfiguracja** wybierz opcję **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="9795c-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="9795c-112">Na karcie **Numery kolejne** sprawdź wartość **Kod sekwencji numerów** dla wartości **Identyfikator wniosku urlopowego** i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="9795c-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="9795c-113">To ustawienie określa numerację używaną do automatycznego przypisywania identyfikatorów do wniosków urlopowych.</span><span class="sxs-lookup"><span data-stu-id="9795c-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="9795c-114">Na karcie **FMLA** sprawdź ustawienia dotyczące rozporządzenia FMLA i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="9795c-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="9795c-115">Na karcie **Samoobsługa pracownika etatowego** wskaż, czy kierownicy mogą wprowadzać wnioski urlopowe w imieniu swoich pracowników.</span><span class="sxs-lookup"><span data-stu-id="9795c-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

7. <span data-ttu-id="9795c-116">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9795c-116">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="9795c-117">Zobacz i zmień parametry urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="9795c-117">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="9795c-118">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="9795c-118">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="9795c-119">W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="9795c-119">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="9795c-120">Na karcie **Ogólne** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="9795c-120">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="9795c-121">Określ **Jednostkę dla urlopu i nieobecności** na godziny lub dni.</span><span class="sxs-lookup"><span data-stu-id="9795c-121">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="9795c-122">Jeśli wybrano dni, można wybrać opcję **Włącz definicję połowy dnia**, aby umożliwić pracownikom wybranie pierwszej lub drugiej połowy dnia w swoich żądaniach czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="9795c-122">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="9795c-123">Wybierz **Data rozpoczęcia miesięcy pracy**, aby określić, kiedy mają obowiązywać stawki naliczania dla planów urlopów za pomocą miesięcy pracy.</span><span class="sxs-lookup"><span data-stu-id="9795c-123">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="9795c-124">Umożliwia wybranie opcji **Obliczanie salda** w celu wyświetlenia widoku sald na dzień dzisiejszy lub w okresie naliczania.</span><span class="sxs-lookup"><span data-stu-id="9795c-124">Select **Balance calculation** to display balances as of today or as of the accrual period.</span></span> <span data-ttu-id="9795c-125">Wybranie **Saldo na dzień dzisiejszy** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i wniosków na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="9795c-125">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="9795c-126">Wybranie **Saldo na okres naliczania** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i żądań podczas okresu naliczania zdefiniowanego przez częstotliwość w planie urlopu.</span><span class="sxs-lookup"><span data-stu-id="9795c-126">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

    - <span data-ttu-id="9795c-127">Umożliwia ustawienie godziny rozpoczęcia zadania wsadowego przeniesienia na następny okres.</span><span class="sxs-lookup"><span data-stu-id="9795c-127">Set the start time for the carry forward expiration batch job.</span></span>  
    
    - <span data-ttu-id="9795c-128">Wybierz **Tak** w polu **Umożliw pracownikom zakup urlopu** oraz **Umożliw pracownikom sprzedaż urlopu**.</span><span class="sxs-lookup"><span data-stu-id="9795c-128">Select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span> <span data-ttu-id="9795c-129">Jeśli wybierzesz opcję **Tak** dla tych opcji, możesz utworzyć zasady kupna i sprzedaży, a następnie umożliwić pracownikom przesyłanie próśb dot. kupna i sprzedaży urlopu.</span><span class="sxs-lookup"><span data-stu-id="9795c-129">If you select **Yes** for these options, you can create buy and sell leave policies and enable employees to submit buy and sell leave requests.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="9795c-130">Konfigurowanie parametrów kalendarza</span><span class="sxs-lookup"><span data-stu-id="9795c-130">Configure calendar parameters</span></span>

1. <span data-ttu-id="9795c-131">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="9795c-131">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="9795c-132">W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="9795c-132">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="9795c-133">Na karcie **Kalendarz** w razie potrzeby zmień ustawienia kalendarza.</span><span class="sxs-lookup"><span data-stu-id="9795c-133">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="9795c-134">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9795c-134">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9795c-135">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="9795c-135">See also</span></span>

- [<span data-ttu-id="9795c-136">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="9795c-136">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
