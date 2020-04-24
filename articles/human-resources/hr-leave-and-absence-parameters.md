---
title: Konfigurowanie parametrów urlopów i nieobecności
description: W programie Dynamics 365 Human Resources można definiować parametry urlopów i nieobecności.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197988"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="405ba-103">Konfigurowanie parametrów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="405ba-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="405ba-104">Przed skonfigurowaniem urlopów i nieobecności w module Dynamics 365 Human Resources dobrze jest sprawdzić ustawienia wszystkich powiązanych parametrów tego modułu, w tym takich jak:</span><span class="sxs-lookup"><span data-stu-id="405ba-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="405ba-105">Numeracja wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="405ba-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="405ba-106">Ustawienia rozporządzenia dotyczącego zwolnień chorobowych i rodzinnych (FMLA)</span><span class="sxs-lookup"><span data-stu-id="405ba-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="405ba-107">Ustawienia obszaru Samoobsługa pracownika etatowego dla wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="405ba-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="405ba-108">Parametry urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="405ba-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="405ba-109">Wyświetlanie i zmiana parametrów modułu Human Resources</span><span class="sxs-lookup"><span data-stu-id="405ba-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="405ba-110">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="405ba-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="405ba-111">W obszarze **Konfiguracja** wybierz opcję **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="405ba-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="405ba-112">Na karcie **Numery kolejne** sprawdź wartość **Kod sekwencji numerów** dla wartości **Identyfikator wniosku urlopowego** i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="405ba-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="405ba-113">To ustawienie określa numerację używaną do automatycznego przypisywania identyfikatorów do wniosków urlopowych.</span><span class="sxs-lookup"><span data-stu-id="405ba-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="405ba-114">Na karcie **FMLA** sprawdź ustawienia dotyczące rozporządzenia FMLA i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="405ba-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="405ba-115">Na karcie **Samoobsługa pracownika etatowego** wskaż, czy kierownicy mogą wprowadzać wnioski urlopowe w imieniu swoich pracowników.</span><span class="sxs-lookup"><span data-stu-id="405ba-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="405ba-116">Na karcie **Urlopy i nieobecności** sprawdź ustawienia i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="405ba-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="405ba-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="405ba-117">Select **Save**.</span></span>

## <a name="view-and-change-leave-and-absence-parameters"></a><span data-ttu-id="405ba-118">Zobacz i zmień parametry urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="405ba-118">View and change leave and absence parameters</span></span>

1. <span data-ttu-id="405ba-119">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="405ba-119">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="405ba-120">W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="405ba-120">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="405ba-121">Na karcie **Ogólne** ustaw następujące parametry:</span><span class="sxs-lookup"><span data-stu-id="405ba-121">On the **General** tab, set the following parameters:</span></span>
 
    - <span data-ttu-id="405ba-122">Określ **Jednostkę dla urlopu i nieobecności** na godziny lub dni.</span><span class="sxs-lookup"><span data-stu-id="405ba-122">Set **Unit for leave and absence** to either hours or days.</span></span> <span data-ttu-id="405ba-123">Jeśli wybrano dni, można wybrać opcję **Włącz definicję połowy dnia**, aby umożliwić pracownikom wybranie pierwszej lub drugiej połowy dnia w swoich żądaniach czasu wolnego.</span><span class="sxs-lookup"><span data-stu-id="405ba-123">If days, you can select **Enable half day definition** to allow employees to choose either first or second half of day in their time-off requests.</span></span> 

    - <span data-ttu-id="405ba-124">Wybierz **Data rozpoczęcia miesięcy pracy**, aby określić, kiedy mają obowiązywać stawki naliczania dla planów urlopów za pomocą miesięcy pracy.</span><span class="sxs-lookup"><span data-stu-id="405ba-124">Select **Months of service effective date** to set when the accrual rates take effect for leave plans using months of service.</span></span>

    - <span data-ttu-id="405ba-125">Umożliwia wybranie opcji **Obliczanie salda** w celu wyświetlenia widoku sald na dzień dzisiejszy lub w okresie naliczania.</span><span class="sxs-lookup"><span data-stu-id="405ba-125">Select **Balance calculation** to display balances display as of today or as of the accrual period.</span></span> <span data-ttu-id="405ba-126">Wybranie **Saldo na dzień dzisiejszy** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i wniosków na dzień dzisiejszy.</span><span class="sxs-lookup"><span data-stu-id="405ba-126">If you select **Balance as of today**, the balance displays the total of all accruals, adjustments, and requests as of today.</span></span> <span data-ttu-id="405ba-127">Wybranie **Saldo na okres naliczania** spowoduje wyświetlenie sumy wszystkich naliczeń, korekt i żądań podczas okresu naliczania zdefiniowanego przez częstotliwość w planie urlopu.</span><span class="sxs-lookup"><span data-stu-id="405ba-127">If you select **Balance as of accrual period**, the balance displays the total of all accruals, adjustments, and requests as of the accrual period defined by the frequency in the leave plan.</span></span> 

## <a name="configure-calendar-parameters"></a><span data-ttu-id="405ba-128">Konfigurowanie parametrów kalendarza</span><span class="sxs-lookup"><span data-stu-id="405ba-128">Configure calendar parameters</span></span>

1. <span data-ttu-id="405ba-129">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="405ba-129">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="405ba-130">W obszarze **Konfiguracja** wybierz opcję **Parametry urlopów i nieobecności**.</span><span class="sxs-lookup"><span data-stu-id="405ba-130">Under **Setup**, select **Leave and absence parameters**.</span></span>

3. <span data-ttu-id="405ba-131">Na karcie **Kalendarz** w razie potrzeby zmień ustawienia kalendarza.</span><span class="sxs-lookup"><span data-stu-id="405ba-131">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="405ba-132">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="405ba-132">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="405ba-133">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="405ba-133">See also</span></span>

- [<span data-ttu-id="405ba-134">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="405ba-134">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
