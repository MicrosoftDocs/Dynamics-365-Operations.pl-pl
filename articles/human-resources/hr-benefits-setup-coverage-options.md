---
title: Tworzenie opcji zapotrzebowania
description: ''
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
ms.openlocfilehash: 27b43d858a92beac526ac0fc40b544649ef658b0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010148"
---
# <a name="create-coverage-options"></a><span data-ttu-id="fe81b-102">Tworzenie opcji zapotrzebowania</span><span class="sxs-lookup"><span data-stu-id="fe81b-102">Create coverage options</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="fe81b-103">Opcje zapotrzebowań w Microsoft Dynamics 365 Human Resources to poziomy zapotrzebowań na wybory uczestnika w planie lub programie świadczeń, takie jak tylko pracownik etatowy dla planu medycznego, lub podwójna wartość wynagrodzenia dla planu ubezpieczenia na życie.</span><span class="sxs-lookup"><span data-stu-id="fe81b-103">Coverage options in Microsoft Dynamics 365 Human Resources are levels of coverage for a participant's election in a benefit plan or program, such as Employee Only for a medical plan, or 2x Salary for a life insurance plan.</span></span> <span data-ttu-id="fe81b-104">Po zdefiniowaniu opcji świadczeń z tytułu świadczenia można używać ponownie, a także kojarzyć opcję z jednym lub kilkoma planami.</span><span class="sxs-lookup"><span data-stu-id="fe81b-104">Once defined, benefit coverage options are re-usable and you can associate an option with one or more plans.</span></span>

<span data-ttu-id="fe81b-105">Po zdefiniowaniu opcji zapotrzebowania należy dołączyć opcje zapotrzebowania do typu planu świadczeń.</span><span class="sxs-lookup"><span data-stu-id="fe81b-105">Once the coverage options are defined, attach the coverage options to a benefit plan type.</span></span> <span data-ttu-id="fe81b-106">Typ planu jest następnie kojarzony z planem lub programem świadczeń.</span><span class="sxs-lookup"><span data-stu-id="fe81b-106">The plan type is then associated with a benefit plan or program.</span></span> <span data-ttu-id="fe81b-107">Opcje zapotrzebowania skojarzone z typem planu będą dostępne dla wszystkich planów utworzonych przy użyciu tego typu planu.</span><span class="sxs-lookup"><span data-stu-id="fe81b-107">Coverage options that are associated with a plan type will be available to all plans that are created with that plan type.</span></span> 

1. <span data-ttu-id="fe81b-108">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje objęcia świadczeniem**.</span><span class="sxs-lookup"><span data-stu-id="fe81b-108">In the **Benefits management** workspace, under **Setup**, select **Coverage options**.</span></span>

2. <span data-ttu-id="fe81b-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="fe81b-109">Select **New**.</span></span>

3. <span data-ttu-id="fe81b-110">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="fe81b-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="fe81b-111">Pole</span><span class="sxs-lookup"><span data-stu-id="fe81b-111">Field</span></span> | <span data-ttu-id="fe81b-112">Opis</span><span class="sxs-lookup"><span data-stu-id="fe81b-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="fe81b-113">**Opcja objęcia świadczeniem**</span><span class="sxs-lookup"><span data-stu-id="fe81b-113">**Coverage option**</span></span> | <span data-ttu-id="fe81b-114">Unikatowa nazwa opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="fe81b-114">A unique coverage option name.</span></span> |
   | <span data-ttu-id="fe81b-115">**Opis**</span><span class="sxs-lookup"><span data-stu-id="fe81b-115">**Description**</span></span> | <span data-ttu-id="fe81b-116">Opis opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="fe81b-116">A description of the coverage option.</span></span> |
   | <span data-ttu-id="fe81b-117">**Kod objęcia świadczeniem**</span><span class="sxs-lookup"><span data-stu-id="fe81b-117">**Coverage code**</span></span> | <span data-ttu-id="fe81b-118">Kody objęcia świadczeniem przypisują kwoty minimalne i maksymalne dla każdego uprawnionego typu osoby objętej.</span><span class="sxs-lookup"><span data-stu-id="fe81b-118">Coverage codes assign minimum and maximum amounts for each eligible covered person type.</span></span> <span data-ttu-id="fe81b-119">Kod objęcia świadczeniem wskazuje, kto jest objęty lub jaki jest zakres dozwolony dla typu planu.</span><span class="sxs-lookup"><span data-stu-id="fe81b-119">A coverage code indicates who is covered or the amount of coverage allowed for a plan type.</span></span> <span data-ttu-id="fe81b-120">Można wyrażać kwotę pokrycia jako kwotę dolara lub procent.</span><span class="sxs-lookup"><span data-stu-id="fe81b-120">You can express the amount of coverage as a dollar amount or a percentage.</span></span> <span data-ttu-id="fe81b-121">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="fe81b-121">For example:</span></span></br></br><span data-ttu-id="fe81b-122">- **EMP + 1** — aby się kwalifikować, pracownik etatowy musi mieć wybraną osobę zależną (Jeśli wybrano więcej niż jedną, nie kwalifikuje się on już do tego celu).</span><span class="sxs-lookup"><span data-stu-id="fe81b-122">- **Emp+1** – to be qualified, the employee must have one dependent selected (if more than one is selected, they no longer qualify).</span></span></br></br><span data-ttu-id="fe81b-123">- **EMP + Rodzina** — Aby się kwalifikować, pracownik musi mieć wybrane co najmniej dwie osoby zależne.</span><span class="sxs-lookup"><span data-stu-id="fe81b-123">- **Emp+family** – to be qualified, the employee must have at least two dependents selected.</span></span> |
   | <span data-ttu-id="fe81b-124">**Maksymalna liczba**</span><span class="sxs-lookup"><span data-stu-id="fe81b-124">**Maximum number**</span></span> | <span data-ttu-id="fe81b-125">Maksymalna liczba osób zależnych.</span><span class="sxs-lookup"><span data-stu-id="fe81b-125">The maximum number of dependents.</span></span> |
   | <span data-ttu-id="fe81b-126">**Stan**</span><span class="sxs-lookup"><span data-stu-id="fe81b-126">**Status**</span></span> | <span data-ttu-id="fe81b-127">Stan opcji objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="fe81b-127">The status of the coverage option.</span></span> <span data-ttu-id="fe81b-128">Jeśli stan opcji objęcia świadczeniem jest określony jako nieaktywny, nie można wybierać opcji objęcia w przypadku typów planów.</span><span class="sxs-lookup"><span data-stu-id="fe81b-128">If the Coverage option status is set to Inactive, the Coverage option can’t be selected on plan types.</span></span> |
   | <span data-ttu-id="fe81b-129">**Procent**</span><span class="sxs-lookup"><span data-stu-id="fe81b-129">**Percent**</span></span> | <span data-ttu-id="fe81b-130">Kwota procentu.</span><span class="sxs-lookup"><span data-stu-id="fe81b-130">The percent amount.</span></span> <span data-ttu-id="fe81b-131">To pole jest aktywne tylko wtedy, gdy w polu Kod objęcia świadczeniem wybrano % x wynagrodzenie.</span><span class="sxs-lookup"><span data-stu-id="fe81b-131">This field is only active if % x Salary was selected in the Coverage code field.</span></span> |
   | <span data-ttu-id="fe81b-132">**Dzielnik**</span><span class="sxs-lookup"><span data-stu-id="fe81b-132">**Divisor**</span></span> | <span data-ttu-id="fe81b-133">Dzielnik używany w obliczeniach po wybraniu kodu objęcia świadczeniem % x wynagrodzenie.</span><span class="sxs-lookup"><span data-stu-id="fe81b-133">The divisor to use in the calculation when you select the coverage code % x salary.</span></span> |
   | <span data-ttu-id="fe81b-134">**Minimalny procent**</span><span class="sxs-lookup"><span data-stu-id="fe81b-134">**Percent minimum**</span></span> | <span data-ttu-id="fe81b-135">Minimalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="fe81b-135">The minimum percentage when you select the Percentage coverage code.</span></span> |
   | <span data-ttu-id="fe81b-136">**Maksymalny procent**</span><span class="sxs-lookup"><span data-stu-id="fe81b-136">**Percent maximum**</span></span> | <span data-ttu-id="fe81b-137">Maksymalna wartość procentowa w przypadku wybrania procentowego kodu objęcia świadczeniem.</span><span class="sxs-lookup"><span data-stu-id="fe81b-137">The maximum percentage when you select the Percentage coverage code.</span></span> |

4. <span data-ttu-id="fe81b-138">W przypadku **Opcji uprawnienia kontaktów osobistych** należy dołączyć do każdej opcji objęcia odpowiednie opcje uprawnienia do kontaktów osobistych.</span><span class="sxs-lookup"><span data-stu-id="fe81b-138">Under **Personal contact eligibility options**, attach the appropriate personal contacts eligibility option to each coverage option.</span></span>

5. <span data-ttu-id="fe81b-139">W **Samoobsługa** wprowadź wartości w następujących polach:</span><span class="sxs-lookup"><span data-stu-id="fe81b-139">Under **Self service**, specify values for the following fields:</span></span>

   | <span data-ttu-id="fe81b-140">Pole</span><span class="sxs-lookup"><span data-stu-id="fe81b-140">Field</span></span> | <span data-ttu-id="fe81b-141">Opis</span><span class="sxs-lookup"><span data-stu-id="fe81b-141">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="fe81b-142">**Zezwalaj na kwotę wkładu pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="fe81b-142">**Allow employee contribution amount**</span></span> | <span data-ttu-id="fe81b-143">Określa, czy zezwalać pracownikom na modyfikowanie kwoty wkładu w samoobsłudze świadczeń podczas wybierania świadczeń.</span><span class="sxs-lookup"><span data-stu-id="fe81b-143">Specifies whether to allow employees to modify the contribution amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="fe81b-144">Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty udziału, jaką pracownik wprowadzi w ramach modułu samoobsługowego.</span><span class="sxs-lookup"><span data-stu-id="fe81b-144">If you select this check box, the system will calculate benefit plan parameters based on the contribution amount the employee enters on benefits self-service.</span></span> |
   | <span data-ttu-id="fe81b-145">**Zezwalaj na kwotę objęcia świadczeniem pracownika etatowego**</span><span class="sxs-lookup"><span data-stu-id="fe81b-145">**Allow employee coverage amount**</span></span> | <span data-ttu-id="fe81b-146">Określa, czy zezwalać pracownikom na modyfikowanie kwoty uprawnienia w samoobsłudze świadczeń podczas wybierania świadczeń.</span><span class="sxs-lookup"><span data-stu-id="fe81b-146">Specifies whether to allow employees to modify the coverage amount on benefits self-service when they select benefits.</span></span> <span data-ttu-id="fe81b-147">Jeśli to pole wyboru zostanie zaznaczone, system będzie obliczał parametry planu świadczeń na podstawie kwoty uprawnienia, jaką pracownik wprowadzi w ramach modułu samoobsługowego pracownika.</span><span class="sxs-lookup"><span data-stu-id="fe81b-147">If you select this check box, the system will calculate benefit plan parameters based on the coverage amount the employee enters in Employee self service.</span></span> |

6. <span data-ttu-id="fe81b-148">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fe81b-148">Select **Save**.</span></span> 
