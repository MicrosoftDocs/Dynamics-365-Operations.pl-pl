---
title: Konfigurowanie parametrów urlopów i nieobecności
description: W programie Dynamics 365 Human Resources można definiować parametry urlopów i nieobecności.
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
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010185"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="dd766-103">Konfigurowanie parametrów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="dd766-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="dd766-104">Przed skonfigurowaniem urlopów i nieobecności w module Dynamics 365 Human Resources dobrze jest sprawdzić ustawienia wszystkich powiązanych parametrów tego modułu, w tym takich jak:</span><span class="sxs-lookup"><span data-stu-id="dd766-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="dd766-105">Numeracja wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="dd766-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="dd766-106">Ustawienia rozporządzenia dotyczącego zwolnień chorobowych i rodzinnych (FMLA)</span><span class="sxs-lookup"><span data-stu-id="dd766-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="dd766-107">Ustawienia obszaru Samoobsługa pracownika etatowego dla wniosków urlopowych</span><span class="sxs-lookup"><span data-stu-id="dd766-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="dd766-108">Parametry urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="dd766-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="dd766-109">Wyświetlanie i zmiana parametrów modułu Human Resources</span><span class="sxs-lookup"><span data-stu-id="dd766-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="dd766-110">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="dd766-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dd766-111">W obszarze **Konfiguracja** wybierz opcję **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="dd766-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="dd766-112">Na karcie **Numery kolejne** sprawdź wartość **Kod sekwencji numerów** dla wartości **Identyfikator wniosku urlopowego** i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="dd766-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="dd766-113">To ustawienie określa numerację używaną do automatycznego przypisywania identyfikatorów do wniosków urlopowych.</span><span class="sxs-lookup"><span data-stu-id="dd766-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="dd766-114">Na karcie **FMLA** sprawdź ustawienia dotyczące rozporządzenia FMLA i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="dd766-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="dd766-115">Na karcie **Samoobsługa pracownika etatowego** wskaż, czy kierownicy mogą wprowadzać wnioski urlopowe w imieniu swoich pracowników.</span><span class="sxs-lookup"><span data-stu-id="dd766-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="dd766-116">Na karcie **Urlopy i nieobecności** sprawdź ustawienia i w razie potrzeby zmień.</span><span class="sxs-lookup"><span data-stu-id="dd766-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="dd766-117">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd766-117">Select **Save**.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="dd766-118">Konfigurowanie parametrów kalendarza</span><span class="sxs-lookup"><span data-stu-id="dd766-118">Configure calendar parameters</span></span>

<span data-ttu-id="dd766-119">Jeśli włączono funkcję w wersji zapoznawczej Kalendarz urlopów i nieobecności, należy skonfigurować dodatkowe parametry.</span><span class="sxs-lookup"><span data-stu-id="dd766-119">If you have enabled the Leave and absence calendar preview feature, you need to configure additional parameters.</span></span> 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> <span data-ttu-id="dd766-120">W wydaniu wersji zapoznawczej z 3 lutego 2020 r. włączono tylko funkcjonalność **Oczekujące wnioski urlopowe**.</span><span class="sxs-lookup"><span data-stu-id="dd766-120">For the preview release on February 3, 2020, only **Pending leave requests** are enabled.</span></span>

1. <span data-ttu-id="dd766-121">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="dd766-121">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dd766-122">W obszarze **Konfiguracja** wybierz opcję **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="dd766-122">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="dd766-123">Na karcie **Kalendarz** w razie potrzeby zmień ustawienia kalendarza.</span><span class="sxs-lookup"><span data-stu-id="dd766-123">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="dd766-124">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd766-124">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd766-125">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="dd766-125">See also</span></span>

- [<span data-ttu-id="dd766-126">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="dd766-126">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
