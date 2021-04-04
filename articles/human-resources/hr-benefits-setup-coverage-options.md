---
title: Tworzenie opcji zapotrzebowania
description: Opcje zapotrzebowań w Microsoft Dynamics 365 Human Resources to poziomy zapotrzebowań na wybory uczestnika w planie lub programie świadczeń.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e1d5fc80d93e41626da8eb5bdf8f389fb0bd531
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466189"
---
# <a name="create-coverage-options"></a><span data-ttu-id="f1df4-103">Tworzenie opcji zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="f1df4-103">Create coverage options</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f1df4-104">Opcje zapotrzebowań w Microsoft Dynamics 365 Human Resources to poziomy zapotrzebowań na wybory uczestnika w planie lub programie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="f1df4-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program.</span></span> <span data-ttu-id="f1df4-105">Na przykład opcje pokrycia mogą obejmować **Tylko pracownik** dla planu medycznego lub **Wynagrodzenie x2** dla planu ubezpieczenia na życie.</span><span class="sxs-lookup"><span data-stu-id="f1df4-105">For example, coverage options could include **Employee Only** for a medical plan, or **2x Salary** for a life insurance plan.</span></span> <span data-ttu-id="f1df4-106">Po zdefiniowaniu można ponownie użyć opcji świadczeń.</span><span class="sxs-lookup"><span data-stu-id="f1df4-106">Once defined, you can reuse benefit coverage options.</span></span> <span data-ttu-id="f1df4-107">Istnieje możliwość skojarzenia opcji z jednym lub kilkoma planami.</span><span class="sxs-lookup"><span data-stu-id="f1df4-107">You can associate an option with one or more plans.</span></span>

<span data-ttu-id="f1df4-108">Po zdefiniowaniu opcji zapotrzebowania należy dołączyć opcje zapotrzebowania do typu planu świadczeń.</span><span class="sxs-lookup"><span data-stu-id="f1df4-108">After you define coverage options, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="f1df4-109">Typ planu jest następnie kojarzony z planem lub programem świadczeń.</span><span class="sxs-lookup"><span data-stu-id="f1df4-109">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="f1df4-110">Opcje zapotrzebowania skojarzone z typem planu będą dostępne dla wszystkich planów utworzonych przy użyciu tego typu planu.</span><span class="sxs-lookup"><span data-stu-id="f1df4-110">Coverage options that are associated with a plan type are available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="f1df4-111">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje objęcia świadczeniem**.</span><span class="sxs-lookup"><span data-stu-id="f1df4-111">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="f1df4-112">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="f1df4-112">Select **New**.</span></span>

3. <span data-ttu-id="f1df4-113">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="f1df4-113">Specify values for the following fields:</span></span>

   | <span data-ttu-id="f1df4-114">Pole</span><span class="sxs-lookup"><span data-stu-id="f1df4-114">Field</span></span> | <span data-ttu-id="f1df4-115">Opis</span><span class="sxs-lookup"><span data-stu-id="f1df4-115">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f1df4-116">**Opcja objęcia świadczeniem**</span><span class="sxs-lookup"><span data-stu-id="f1df4-116">**Coverage option**</span></span> | <span data-ttu-id="f1df4-117">Unikatowa nazwa opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="f1df4-117">A unique coverage option name.</span></span> |
   | <span data-ttu-id="f1df4-118">**Opis**</span><span class="sxs-lookup"><span data-stu-id="f1df4-118">**Description**</span></span> | <span data-ttu-id="f1df4-119">Opis opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="f1df4-119">A description of the coverage option.</span></span> |
   | <span data-ttu-id="f1df4-120">**Kod objęcia świadczeniem**</span><span class="sxs-lookup"><span data-stu-id="f1df4-120">**Coverage code**</span></span> | <span data-ttu-id="f1df4-121">Kody objęcia świadczeniem przypisują kwoty minimalne i maksymalne dla każdego uprawnionego typu osoby objętej.</span><span class="sxs-lookup"><span data-stu-id="f1df4-121">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="f1df4-122">Kod objęcia świadczeniem wskazuje, kto jest objęty lub jaki jest zakres dozwolony dla typu planu.</span><span class="sxs-lookup"><span data-stu-id="f1df4-122">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="f1df4-123">Można wyrażać kwotę pokrycia jako kwotę dolara lub procent.</span><span class="sxs-lookup"><span data-stu-id="f1df4-123">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="f1df4-124">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="f1df4-124">For example:</span></span></br></br><span data-ttu-id="f1df4-125">- **EMP + 1** — aby się kwalifikować, pracownik etatowy musi mieć wybraną osobę zależną (Jeśli wybrano więcej niż jedną, nie kwalifikuje się on już do tego celu).</span><span class="sxs-lookup"><span data-stu-id="f1df4-125">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="f1df4-126">- **EMP + Rodzina** — Aby się kwalifikować, pracownik musi mieć wybrane co najmniej dwie osoby zależne.</span><span class="sxs-lookup"><span data-stu-id="f1df4-126">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="f1df4-127">**Maksymalna liczba**</span><span class="sxs-lookup"><span data-stu-id="f1df4-127">**Maximum number**</span></span> | <span data-ttu-id="f1df4-128">Maksymalna liczba osób zależnych.</span><span class="sxs-lookup"><span data-stu-id="f1df4-128">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="f1df4-129">**Stan**</span><span class="sxs-lookup"><span data-stu-id="f1df4-129">**Status**</span></span> | <span data-ttu-id="f1df4-130">Stan opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="f1df4-130">The status of the coverage option.</span></span> <span data-ttu-id="f1df4-131">Jeśli stan opcji objęcia świadczeniem jest określony jako nieaktywny, nie można wybierać opcji objęcia w przypadku typów planów.</span><span class="sxs-lookup"><span data-stu-id="f1df4-131">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="f1df4-132">**Procent**</span><span class="sxs-lookup"><span data-stu-id="f1df4-132">**Percent**</span></span> | <span data-ttu-id="f1df4-133">Kwota procentu.</span><span class="sxs-lookup"><span data-stu-id="f1df4-133">The percent amount.</span></span> <span data-ttu-id="f1df4-134">To pole jest aktywne tylko wtedy, gdy w polu Kod objęcia świadczeniem wybrano % x wynagrodzenie.</span><span class="sxs-lookup"><span data-stu-id="f1df4-134">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="f1df4-135">**Dzielnik**</span><span class="sxs-lookup"><span data-stu-id="f1df4-135">**Divisor**</span></span> | <span data-ttu-id="f1df4-136">Dzielnik używany w obliczeniach po wybraniu kodu objęcia świadczeniem % x wynagrodzenie.</span><span class="sxs-lookup"><span data-stu-id="f1df4-136">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="f1df4-137">**Minimalny procent**</span><span class="sxs-lookup"><span data-stu-id="f1df4-137">**Percent minimum**</span></span> | <span data-ttu-id="f1df4-138">Minimalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="f1df4-138">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="f1df4-139">**Maksymalny procent**</span><span class="sxs-lookup"><span data-stu-id="f1df4-139">**Percent maximum**</span></span> | <span data-ttu-id="f1df4-140">Maksymalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="f1df4-140">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="f1df4-141">W przypadku **Opcji uprawnienia kontaktów osobistych** należy dołączyć do każdej opcji objęcia odpowiednie opcje uprawnienia do kontaktów osobistych.</span><span class="sxs-lookup"><span data-stu-id="f1df4-141">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="f1df4-142">W **Samoobsługa** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="f1df4-142">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="f1df4-143">Pole</span><span class="sxs-lookup"><span data-stu-id="f1df4-143">Field</span></span> | <span data-ttu-id="f1df4-144">Opis</span><span class="sxs-lookup"><span data-stu-id="f1df4-144">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f1df4-145">**Zezwalaj na kwotę wkładu pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="f1df4-145">**Allow employee contribution amount**</span></span> | <span data-ttu-id="f1df4-146">Określa, czy zezwalać pracownikom na modyfikowanie kwoty wkładu w samoobsłudze świadczeń podczas wybierania świadczeń.</span><span class="sxs-lookup"><span data-stu-id="f1df4-146">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="f1df4-147">Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty udziału, jaką pracownik wprowadzi w ramach modułu samoobsługowego.</span><span class="sxs-lookup"><span data-stu-id="f1df4-147">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="f1df4-148">**Zezwalaj na kwotę objęcia świadczeniem pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="f1df4-148">**Allow employee coverage amount**</span></span> | <span data-ttu-id="f1df4-149">Określa, czy zezwalać pracownikom na modyfikowanie kwoty uprawnienia w samoobsłudze świadczeń podczas wybierania świadczeń.</span><span class="sxs-lookup"><span data-stu-id="f1df4-149">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="f1df4-150">Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty uprawnienia, jaką pracownik wprowadzi w ramach modułu samoobsługowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="f1df4-150">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="f1df4-151">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f1df4-151">Select **Save**.</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]