---
title: Tworzenie opcji zapotrzebowania
description: Opcje zapotrzebowań w Microsoft Dynamics 365 Human Resources to poziomy zapotrzebowań na wybory uczestnika w planie lub programie świadczeń, takie jak tylko pracownik etatowy dla planu medycznego, lub podwójna wartość wynagrodzenia dla planu ubezpieczenia na życie.
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
ms.openlocfilehash: 0af2b6ae0853b4c7f64c4d4f04299c87089d622b
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092713"
---
# <a name="create-coverage-options"></a><span data-ttu-id="3609e-103">Tworzenie opcji zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="3609e-103">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="3609e-104">Opcje zapotrzebowań w Microsoft Dynamics 365 Human Resources to poziomy zapotrzebowań na wybory uczestnika w planie lub programie świadczeń, takie jak tylko pracownik etatowy dla planu medycznego, lub podwójna wartość wynagrodzenia dla planu ubezpieczenia na życie.</span><span class="sxs-lookup"><span data-stu-id="3609e-104">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="3609e-105">Po zdefiniowaniu opcji świadczeń z tytułu świadczenia można używać ponownie, a także kojarzyć opcję z jednym lub kilkoma planami.</span><span class="sxs-lookup"><span data-stu-id="3609e-105">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="3609e-106">Po zdefiniowaniu opcji zapotrzebowania należy dołączyć opcje zapotrzebowania do typu planu świadczeń.</span><span class="sxs-lookup"><span data-stu-id="3609e-106">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="3609e-107">Typ planu jest następnie kojarzony z planem lub programem świadczeń.</span><span class="sxs-lookup"><span data-stu-id="3609e-107">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="3609e-108">Opcje zapotrzebowania skojarzone z typem planu będą dostępne dla wszystkich planów utworzonych przy użyciu tego typu planu.</span><span class="sxs-lookup"><span data-stu-id="3609e-108">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="3609e-109">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje objęcia świadczeniem**.</span><span class="sxs-lookup"><span data-stu-id="3609e-109">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="3609e-110">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="3609e-110">Select **New**.</span></span>

3. <span data-ttu-id="3609e-111">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="3609e-111">Specify values for the following fields:</span></span>

   | <span data-ttu-id="3609e-112">Pole</span><span class="sxs-lookup"><span data-stu-id="3609e-112">Field</span></span> | <span data-ttu-id="3609e-113">Opis</span><span class="sxs-lookup"><span data-stu-id="3609e-113">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="3609e-114">**Opcja objęcia świadczeniem**</span><span class="sxs-lookup"><span data-stu-id="3609e-114">**Coverage option**</span></span> | <span data-ttu-id="3609e-115">Unikatowa nazwa opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="3609e-115">A unique coverage option name.</span></span> |
   | <span data-ttu-id="3609e-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="3609e-116">**Description**</span></span> | <span data-ttu-id="3609e-117">Opis opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="3609e-117">A description of the coverage option.</span></span> |
   | <span data-ttu-id="3609e-118">**Kod objęcia świadczeniem**</span><span class="sxs-lookup"><span data-stu-id="3609e-118">**Coverage code**</span></span> | <span data-ttu-id="3609e-119">Kody objęcia świadczeniem przypisują kwoty minimalne i maksymalne dla każdego uprawnionego typu osoby objętej.</span><span class="sxs-lookup"><span data-stu-id="3609e-119">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="3609e-120">Kod objęcia świadczeniem wskazuje, kto jest objęty lub jaki jest zakres dozwolony dla typu planu.</span><span class="sxs-lookup"><span data-stu-id="3609e-120">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="3609e-121">Można wyrażać kwotę pokrycia jako kwotę dolara lub procent.</span><span class="sxs-lookup"><span data-stu-id="3609e-121">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="3609e-122">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="3609e-122">For example:</span></span></br></br><span data-ttu-id="3609e-123">- **EMP + 1** — aby się kwalifikować, pracownik etatowy musi mieć wybraną osobę zależną (Jeśli wybrano więcej niż jedną, nie kwalifikuje się on już do tego celu).</span><span class="sxs-lookup"><span data-stu-id="3609e-123">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="3609e-124">- **EMP + Rodzina** — Aby się kwalifikować, pracownik musi mieć wybrane co najmniej dwie osoby zależne.</span><span class="sxs-lookup"><span data-stu-id="3609e-124">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="3609e-125">**Maksymalna liczba**</span><span class="sxs-lookup"><span data-stu-id="3609e-125">**Maximum number**</span></span> | <span data-ttu-id="3609e-126">Maksymalna liczba osób zależnych.</span><span class="sxs-lookup"><span data-stu-id="3609e-126">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="3609e-127">**Stan**</span><span class="sxs-lookup"><span data-stu-id="3609e-127">**Status**</span></span> | <span data-ttu-id="3609e-128">Stan opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="3609e-128">The status of the coverage option.</span></span> <span data-ttu-id="3609e-129">Jeśli stan opcji objęcia świadczeniem jest określony jako nieaktywny, nie można wybierać opcji objęcia w przypadku typów planów.</span><span class="sxs-lookup"><span data-stu-id="3609e-129">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="3609e-130">**Procent**</span><span class="sxs-lookup"><span data-stu-id="3609e-130">**Percent**</span></span> | <span data-ttu-id="3609e-131">Kwota procentu.</span><span class="sxs-lookup"><span data-stu-id="3609e-131">The percent amount.</span></span> <span data-ttu-id="3609e-132">To pole jest aktywne tylko wtedy, gdy w polu Kod objęcia świadczeniem wybrano % x wynagrodzenie.</span><span class="sxs-lookup"><span data-stu-id="3609e-132">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="3609e-133">**Dzielnik**</span><span class="sxs-lookup"><span data-stu-id="3609e-133">**Divisor**</span></span> | <span data-ttu-id="3609e-134">Dzielnik używany w obliczeniach po wybraniu kodu objęcia świadczeniem % x wynagrodzenie.</span><span class="sxs-lookup"><span data-stu-id="3609e-134">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="3609e-135">**Minimalny procent**</span><span class="sxs-lookup"><span data-stu-id="3609e-135">**Percent minimum**</span></span> | <span data-ttu-id="3609e-136">Minimalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="3609e-136">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="3609e-137">**Maksymalny procent**</span><span class="sxs-lookup"><span data-stu-id="3609e-137">**Percent maximum**</span></span> | <span data-ttu-id="3609e-138">Maksymalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="3609e-138">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="3609e-139">W przypadku **Opcji uprawnienia kontaktów osobistych** należy dołączyć do każdej opcji objęcia odpowiednie opcje uprawnienia do kontaktów osobistych.</span><span class="sxs-lookup"><span data-stu-id="3609e-139">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="3609e-140">W **Samoobsługa** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="3609e-140">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="3609e-141">Pole</span><span class="sxs-lookup"><span data-stu-id="3609e-141">Field</span></span> | <span data-ttu-id="3609e-142">Opis</span><span class="sxs-lookup"><span data-stu-id="3609e-142">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="3609e-143">**Zezwalaj na kwotę wkładu pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="3609e-143">**Allow employee contribution amount**</span></span> | <span data-ttu-id="3609e-144">Określa, czy zezwalać pracownikom na modyfikowanie kwoty wkładu w samoobsłudze świadczeń podczas wybierania świadczeń.</span><span class="sxs-lookup"><span data-stu-id="3609e-144">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="3609e-145">Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty udziału, jaką pracownik wprowadzi w ramach modułu samoobsługowego.</span><span class="sxs-lookup"><span data-stu-id="3609e-145">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="3609e-146">**Zezwalaj na kwotę objęcia świadczeniem pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="3609e-146">**Allow employee coverage amount**</span></span> | <span data-ttu-id="3609e-147">Określa, czy zezwalać pracownikom na modyfikowanie kwoty uprawnienia w samoobsłudze świadczeń podczas wybierania świadczeń.</span><span class="sxs-lookup"><span data-stu-id="3609e-147">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="3609e-148">Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty uprawnienia, jaką pracownik wprowadzi w ramach modułu samoobsługowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="3609e-148">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="3609e-149">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="3609e-149">Select **Save**.</span></span> 
