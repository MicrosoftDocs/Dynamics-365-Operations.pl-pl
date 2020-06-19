---
title: Zarządzaj zasadami dotyczącymi kupna i sprzedaży urlopu
description: Można umożliwić pracownikom kupowanie i sprzedawanie urlopu w Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
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
ms.openlocfilehash: 859445f2b6e980b5960e512e69129f6a8fc6df2b
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429020"
---
# <a name="manage-buy-and-sell-leave-policies"></a><span data-ttu-id="bf308-103">Zarządzaj zasadami dotyczącymi kupna i sprzedaży urlopu</span><span class="sxs-lookup"><span data-stu-id="bf308-103">Manage buy and sell leave policies</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="bf308-104">Można umożliwić pracownikom kupowanie urlopu, tworząc zasadę kupowania urlopu.</span><span class="sxs-lookup"><span data-stu-id="bf308-104">You can enable employees to buy leave by creating a buy leave policy.</span></span>  

## <a name="enable-employees-to-buy-and-sell-leave"></a><span data-ttu-id="bf308-105">Umożliwienie pracownikom kupowania i sprzedawania urlopu</span><span class="sxs-lookup"><span data-stu-id="bf308-105">Enable employees to buy and sell leave</span></span>

1. <span data-ttu-id="bf308-106">Na stronie **Parametry urlopów i nieobecności** wybierz opcję **Tak** dla **Pozwól pracownikom kupić urlop**.</span><span class="sxs-lookup"><span data-stu-id="bf308-106">On the **Leave and absence parameters** page, select **Yes** for **Allow employees to buy leave**.</span></span> 

## <a name="create-a-buy-leave-policy"></a><span data-ttu-id="bf308-107">Tworzenie zasady kupowania urlopu</span><span class="sxs-lookup"><span data-stu-id="bf308-107">Create a buy leave policy</span></span>

1. <span data-ttu-id="bf308-108">Na stronie **Urlopy i nieobecności** wybierz kartę **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="bf308-108">On the **Leave and absence** page, select the **Links** tab.</span></span> 

2. <span data-ttu-id="bf308-109">Wybierz **Zasady kupowania i sprzzedawania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="bf308-109">Select **Buy and sell leave policy**.</span></span>

3. <span data-ttu-id="bf308-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="bf308-110">Select **New**.</span></span>

4. <span data-ttu-id="bf308-111">Wprowadź **Nazwę** i **Opis** zasady w obszarze **Zasady kupowania i sprzedawania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="bf308-111">Enter a **Name** and **Description** for the policy under **Buy and sell leave policy**.</span></span> 

5. <span data-ttu-id="bf308-112">Wybierz **Typ zasad**.</span><span class="sxs-lookup"><span data-stu-id="bf308-112">Select a **Policy type**.</span></span> 

   <span data-ttu-id="bf308-113">Dostępne typy zasad to **Ilość** i **Godziny na tydzień**.</span><span class="sxs-lookup"><span data-stu-id="bf308-113">The available policy types are **Amount** and **Hours per week**.</span></span> <span data-ttu-id="bf308-114">Wybierz opcję **Ilość**, aby wprowadzić **Stałą ilość** dla maksymalnych ilości, które pracownicy mogą kupować i sprzedawać.</span><span class="sxs-lookup"><span data-stu-id="bf308-114">Select **Amount** to enter a **Fixed amount** for the maximum amounts employees can buy and sell.</span></span> <span data-ttu-id="bf308-115">W przypadku wybrania **Godziny w tygodniu** czas pracy określony w kalendarzu czasu pracy pracownika jest używany do określenia maksymalnej ilości zasady.</span><span class="sxs-lookup"><span data-stu-id="bf308-115">If you select **Hours per week**, the working time defined in the employee's assigned working time calendar is used to determine the maximum amount of the policy.</span></span> 

6. <span data-ttu-id="bf308-116">Wybierz **Datę początkową** i **Datę końcową** dla zasady.</span><span class="sxs-lookup"><span data-stu-id="bf308-116">Select a **Start date** and **End date** for the policy.</span></span> <span data-ttu-id="bf308-117">Żądania kupna lub sprzedaży urlopu będą dostępne tylko do przesyłania w tym przedziale czasowym.</span><span class="sxs-lookup"><span data-stu-id="bf308-117">Requests to buy or sell leave will only be available for submission during this time frame.</span></span> 

7. <span data-ttu-id="bf308-118">W obszarze **Kup zasadę** wybierz opcję **Odpowiednik pełnego etatu**, aby ustalić maksymalną kwotę na podstawie pełnego etatu zdefiniowanego dla stanowiska pracownika.</span><span class="sxs-lookup"><span data-stu-id="bf308-118">Under **Buy policy**, select **Full time equivalency** (FTE) to prorate the maximum amount based on the FTE defined on the employee's position.</span></span> <span data-ttu-id="bf308-119">Jeśli typem zasady jest **Ilość**, wprowadź **Maksymalną stałą ilość**.</span><span class="sxs-lookup"><span data-stu-id="bf308-119">If the policy type is **Amount**, enter a **Maximum fixed amount**.</span></span> 

8. <span data-ttu-id="bf308-120">Wybierz przycisk **Dodaj**, aby dodać typy urlopów dla pracowników, którzy będą kupować urlop.</span><span class="sxs-lookup"><span data-stu-id="bf308-120">Select **Add** to add the leave types for employees to buy leave.</span></span> <span data-ttu-id="bf308-121">Do zasady można dodać wiele typów urlopów.</span><span class="sxs-lookup"><span data-stu-id="bf308-121">You can add multiple leave types to the policy.</span></span> 

9. <span data-ttu-id="bf308-122">Wprowadź **Miesiące usługi** dla typu urlop, aby umożliwić różnym miesiącom usługi określenie maksymalnej kwoty, jaką może zakupić pracownik.</span><span class="sxs-lookup"><span data-stu-id="bf308-122">Enter the **Months of service** for the leave type to enable different months of service to determine the maximum amount an employee can buy.</span></span> 

10. <span data-ttu-id="bf308-123">Wprowadź **Maksymalną ilość** dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="bf308-123">Enter the **Maximum amount** for the leave type.</span></span> 

11. <span data-ttu-id="bf308-124">Umożliwia wprowadzenie **Stawki**, za którą pracownik będzie kupować urlop.</span><span class="sxs-lookup"><span data-stu-id="bf308-124">Enter the **Rate** at which the employee will buy the leave.</span></span> 

12. <span data-ttu-id="bf308-125">Opcjonalnie można wprowadzić **Kod zarobków**, który ma być używany przy zakupie urlopu.</span><span class="sxs-lookup"><span data-stu-id="bf308-125">Optionally enter the **Earning code** to be used for buying leave.</span></span> 

13. <span data-ttu-id="bf308-126">Opcjonalnie określ, czy ma być używany ekwiwalent pełnego wymiaru czasu, aby określić maksymalną ilość dla typu urlopu.</span><span class="sxs-lookup"><span data-stu-id="bf308-126">Optionally set whether to use FTE to determine the maximum amount for the leave type.</span></span> 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a><span data-ttu-id="bf308-127">Dodaj zasadę Kup i Sprzedaj urlop do planu urlopu i nieobecności</span><span class="sxs-lookup"><span data-stu-id="bf308-127">Add the buy and sell leave policy to a leave and absence plan</span></span>

1. <span data-ttu-id="bf308-128">Na stronie **Urlopy i nieobecności** wybierz plan urlopu i nieobecności.</span><span class="sxs-lookup"><span data-stu-id="bf308-128">On the **Leave and absence** page, select a leave and absence plan.</span></span>

2. <span data-ttu-id="bf308-129">W **Reguły** wybierz **Zasady kupowania i sprzzedawania urlopu**.</span><span class="sxs-lookup"><span data-stu-id="bf308-129">Under **Rules**, select **Buy and sell leave policy**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf308-130">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="bf308-130">See also</span></span>

[<span data-ttu-id="bf308-131">Omówienie urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="bf308-131">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="bf308-132">Konfigurowanie typów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="bf308-132">Configure leave and absence types</span></span>](hr-leave-and-absence-types.md)</br>
[<span data-ttu-id="bf308-133">Naliczanie planów urlopów i nieobecności</span><span class="sxs-lookup"><span data-stu-id="bf308-133">Accrue leave and absence plans</span></span>](hr-leave-and-absence-accrue.md)</br>
[<span data-ttu-id="bf308-134">Kupuj i sprzedawaj urlop</span><span class="sxs-lookup"><span data-stu-id="bf308-134">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

