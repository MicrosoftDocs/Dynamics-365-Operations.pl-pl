---
title: Definiowanie punktów lojalnościowych
description: Ta procedura prowadzi przez definiowanie punktów lojalnościowych.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af217a5e756db571e3e351b743aa44b842f478f1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000491"
---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="ac1c0-103">Definiowanie punktów lojalnościowych</span><span class="sxs-lookup"><span data-stu-id="ac1c0-103">Define loyalty reward points</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac1c0-104">Ta procedura prowadzi przez definiowanie punktów lojalnościowych.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="ac1c0-105">Punkty lojalnościowe powinny być skonfigurowane przed skonfigurowaniem programu lojalnościowego.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="ac1c0-106">Procedura wykorzystuje dane firmy demonstracyjnej USRT.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="ac1c0-107">Wybierz kolejno opcje Retail i Commerce > Odbiorcy > Lojalność > Punkty lojalnościowe.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-107">Go to Retail and Commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="ac1c0-108">Kliknij przycisk Nowy.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-108">Click New.</span></span>
3. <span data-ttu-id="ac1c0-109">W polu Identyfikator punktów lojalnościowych wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="ac1c0-110">Wypełnij pole Opis.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ac1c0-111">W polu Typ punktów lojalnościowych wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="ac1c0-112">Zaznacz opcję Ilość, jeśli chcesz zaokrąglać punkty lojalnościowe do najbliższej liczby całkowitej.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="ac1c0-113">Zaznacz opcję Kwota, jeśli chcesz zaokrąglać punkty lojalnościowe według reguł zaokrąglania walut.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="ac1c0-114">W przypadku zaznaczenia opcji Ilość przejdź do następnego kroku tej procedury.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="ac1c0-115">W polu Waluta wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="ac1c0-116">Dla punktów lojalnościowych typu Kwota wszystkie przyznane punkty będą miały wybraną walutę.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="ac1c0-117">Do punktów lojalnościowych typu Ilość to pole nie ma zastosowania — pomiń ten krok.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="ac1c0-118">Zaznacz pole wyboru Można spieniężyć lub usuń jego zaznaczenie.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="ac1c0-119">W polu Klasyfikacja spieniężeń wpisz liczbę.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="ac1c0-120">Klasyfikacja spieniężeń jest używana, gdy co najmniej dwa wymienialne punkty lojalnościowe mogą zostać użyte do zapłaty za produkty.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="ac1c0-121">Jeśli dwa punkty lojalnościowe mają taką samą klasyfikację spieniężeń, zostanie użyty ten, który musi być wykorzystywany w mniejszej liczbie.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="ac1c0-122">W polu Wartość okresu ważności wprowadź lub wybierz wartość.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="ac1c0-123">Punkty lojalnościowe wygasają określoną liczbę dni, miesięcy lub lat po wydaniu.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="ac1c0-124">Wartość „0” oznacza, że punkty lojalnościowe nigdy nie wygasną.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-124">A value of '0' means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="ac1c0-125">W polu Jednostka okresu ważności wybierz opcję.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="ac1c0-126">Kliknij przycisk Zapisz.</span><span class="sxs-lookup"><span data-stu-id="ac1c0-126">Click Save.</span></span>

