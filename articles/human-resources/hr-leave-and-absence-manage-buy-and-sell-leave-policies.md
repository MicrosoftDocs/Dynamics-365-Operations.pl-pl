---
title: Zarządzaj zasadami dotyczącymi kupna i sprzedaży urlopu
description: Można umożliwić pracownikom kupowanie i sprzedawanie urlopu w Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 55d29c42cc1b2d69517e2fcd458ee6a1bdf5277f
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712126"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="42fd7-103">Zarządzaj zasadami Kupowania i Sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="42fd7-103">Manage buy and sell leave policies</span></span>

<span data-ttu-id="42fd7-104">Można umożliwić pracownikom kupowanie i sprzedawanie urlopu, tworząc zasadę kupowania i sprzedawania urlopu.</span><span class="sxs-lookup"><span data-stu-id="42fd7-104">You can enable employees to buy and sell leave by creating a buy and sell leave policy.</span></span> <span data-ttu-id="42fd7-105">Te zasady można skonfigurować do używania przepływu pracy dla zatwierdzeń, określania maksymalnych kwot i stawek oraz ustalania stawek kupowania i sprzedawania.</span><span class="sxs-lookup"><span data-stu-id="42fd7-105">You can configure these policies to use workflow for approvals, set maximum amounts and rates, and set rates for buying and selling.</span></span> 

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="42fd7-106">Umożliwienie pracownikom kupowania i sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="42fd7-106">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="42fd7-107">Na stronie **Parametry urlopów i nieobecności** wybierz opcję **Tak** dla **Pozwól pracownikom kupić urlop** oraz **Pozwól pracownikom sprzedać urlop**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-107">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave** and **Allow employees to sell leave**.</span></span>

## <a name="create-a-buy-and-sell-leave-policy"></a><span data-ttu-id="42fd7-108">Tworzenie zasad dot. zakupów i sprzedaży urlopów</span><span class="sxs-lookup"><span data-stu-id="42fd7-108">Create a buy and sell leave policy</span></span>

1. <span data-ttu-id="42fd7-109">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-109">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="42fd7-110">Wybierz **Zasady kupowania i sprzzedawania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-110">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="42fd7-111">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-111">Select **New**.</span></span>

4. <span data-ttu-id="42fd7-112">Wprowadź **Nazwę** i **Opis** zasady w obszarze **Zasady kupowania i sprzedawania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-112">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="42fd7-113">Wybierz **Typ zasad**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-113">Select a **Policy type**.</span></span> 

   <span data-ttu-id="42fd7-114">Dostępne typy zasad to **Ilość** i **Godziny na tydzień**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-114">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="42fd7-115">Wybierz opcję **Ilość**, aby wprowadzić **Stałą ilość** dla maksymalnych ilości, które pracownicy mogą kupować i sprzedawać.</span><span class="sxs-lookup"><span data-stu-id="42fd7-115">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="42fd7-116">W przypadku wybrania **Godziny w tygodniu** czas pracy określony w kalendarzu czasu pracy pracownika jest używany do określenia maksymalnej ilości zasady.</span><span class="sxs-lookup"><span data-stu-id="42fd7-116">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="42fd7-117">Wybierz **Datę początkową** i **Datę końcową** dla zasady.</span><span class="sxs-lookup"><span data-stu-id="42fd7-117">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="42fd7-118">Żądania kupna lub sprzedaży urlopu będą dostępne tylko do przesyłania w tym przedziale czasowym.</span><span class="sxs-lookup"><span data-stu-id="42fd7-118">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="42fd7-119">Wybierz **Identyfikator przepływu pracy** dla zasady.</span><span class="sxs-lookup"><span data-stu-id="42fd7-119">Select a **Workflow ID** for the policy.</span></span> <span data-ttu-id="42fd7-120">Wszystkie żądania zakupu i sprzedaży używają tego przepływu pracy do przeglądu i zatwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="42fd7-120">Any buy and sell requests will use this workflow for review and approval.</span></span> 

8. <span data-ttu-id="42fd7-121">W obszarze **Kup zasadę** wybierz opcję **Odpowiednik pełnego etatu**, aby ustalić maksymalną kwotę na podstawie pełnego etatu zdefiniowanego dla stanowiska pracownika.</span><span class="sxs-lookup"><span data-stu-id="42fd7-121">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="42fd7-122">Jeśli typem zasady jest **Ilość**, wprowadź **Maksymalną stałą ilość**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-122">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

9. <span data-ttu-id="42fd7-123">Wybierz przycisk **Dodaj**, aby dodać typy urlopów dla pracowników, którzy będą kupować urlop.</span><span class="sxs-lookup"><span data-stu-id="42fd7-123">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="42fd7-124">Do zasady można dodać wiele typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="42fd7-124">You can add multiple leave types to the policy.</span></span> 

10. <span data-ttu-id="42fd7-125">Wprowadź **Miesiące usługi** dla typu urlop, aby umożliwić różnym miesiącom usługi określenie maksymalnej kwoty, jaką może zakupić pracownik.</span><span class="sxs-lookup"><span data-stu-id="42fd7-125">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

11. <span data-ttu-id="42fd7-126">Wprowadź **Maksymalną ilość** dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="42fd7-126">Enter the **Maximum amount** for the leave type.</span></span> 

12. <span data-ttu-id="42fd7-127">Umożliwia wprowadzenie **Stawki**, za którą pracownik będzie kupować urlop.</span><span class="sxs-lookup"><span data-stu-id="42fd7-127">Enter the **Rate** at which the employee will buy the leave.</span></span> 

13. <span data-ttu-id="42fd7-128">Opcjonalnie można wprowadzić **Kod zarobków**, który ma być używany przy zakupie urlopu.</span><span class="sxs-lookup"><span data-stu-id="42fd7-128">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

14. <span data-ttu-id="42fd7-129">Opcjonalnie określ, czy ma być używany ekwiwalent pełnego wymiaru czasu, aby określić maksymalną ilość dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="42fd7-129">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

15. <span data-ttu-id="42fd7-130">Aby utworzyć zasadę sprzedaży, wykonaj czynności opisane w punktach 8 – 14 w ramach **Zasad sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-130">To create a sell policy, follow steps 8 through 14 under **Sell policy**.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="42fd7-131">Dodaj zasadę Kup i Sprzedaj urlop do planu urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="42fd7-131">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="42fd7-132">Na stronie **Urlopy i nieobecności** wybierz plan urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="42fd7-132">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="42fd7-133">W **Reguły** wybierz **Zasady kupowania i sprzzedawania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="42fd7-133">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="42fd7-134">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="42fd7-134">See also</span></span>

[<span data-ttu-id="42fd7-135">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="42fd7-135">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="42fd7-136">Konfigurowanie typów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="42fd7-136">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="42fd7-137">Naliczanie planów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="42fd7-137">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="42fd7-138">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="42fd7-138">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

