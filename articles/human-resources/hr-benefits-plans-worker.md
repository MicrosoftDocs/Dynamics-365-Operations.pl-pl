---
title: Tworzenie planów świadczeń pracowniczych
description: W programie Microsoft Dynamics 365 Human Resources można tworzyć plany świadczeń pracowniczych, aby umożliwić wybieranie planów świadczeń dla pracowników i zatwierdzać wybory planów świadczeń.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanEmployee, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5ac357bbef4bf84b9eaf153834bc7a609240c45e
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464233"
---
# <a name="create-worker-benefit-plans"></a><span data-ttu-id="43d2d-103">Tworzenie planów świadczeń pracowniczych</span><span class="sxs-lookup"><span data-stu-id="43d2d-103">Create worker benefit plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="43d2d-104">W programie Microsoft Dynamics 365 Human Resources można tworzyć plany świadczeń pracowniczych, aby umożliwić wybieranie planów świadczeń dla pracowników i zatwierdzać wybory planów świadczeń.</span><span class="sxs-lookup"><span data-stu-id="43d2d-104">You can create worker benefit plans in Microsoft Dynamics 365 Human Resources to select benefit plans for employees and to confirm benefit plan selections.</span></span> <span data-ttu-id="43d2d-105">Zazwyczaj pracownicy sami wybierają plany świadczeń w obszarze Samoobsługa pracownika etatowego, a następnie administratorowi świadczeń zatwierdza te wybory.</span><span class="sxs-lookup"><span data-stu-id="43d2d-105">Typically, employees select benefit plans themselves by using Employee self service, and then a benefits administrator confirms the selections.</span></span> 

1. <span data-ttu-id="43d2d-106">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Plany** wybierz opcję **Plany świadczeń pracowniczych**.</span><span class="sxs-lookup"><span data-stu-id="43d2d-106">In the **Benefits management** workspace, under **Plans**, select **Worker benefit plans**.</span></span>

2. <span data-ttu-id="43d2d-107">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="43d2d-107">Select **New**.</span></span>

3. <span data-ttu-id="43d2d-108">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="43d2d-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="43d2d-109">Pole</span><span class="sxs-lookup"><span data-stu-id="43d2d-109">Field</span></span> | <span data-ttu-id="43d2d-110">Opis</span><span class="sxs-lookup"><span data-stu-id="43d2d-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="43d2d-111">Okres</span><span class="sxs-lookup"><span data-stu-id="43d2d-111">Period</span></span> | <span data-ttu-id="43d2d-112">Określa okres świadczeniowy, który ma być używany do filtrowania planów na skróconej karcie Plany. Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-112">Specifies a benefits period to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> <span data-ttu-id="43d2d-113">Na przykład wybierz utworzony okres o nazwie 2015, aby zatwierdzić wszystkie wybory rejestracji na świadczenia dla 2015 roku.</span><span class="sxs-lookup"><span data-stu-id="43d2d-113">For example, select a period you created called 2015 to confirm all the benefit enrollment selections for 2015.</span></span> |
   | <span data-ttu-id="43d2d-114">Pracownik</span><span class="sxs-lookup"><span data-stu-id="43d2d-114">Worker</span></span> | <span data-ttu-id="43d2d-115">Określa pracownika, który ma być używany do filtrowania planów na skróconej karcie Plany. Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-115">Specifies a worker to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="43d2d-116">Firma</span><span class="sxs-lookup"><span data-stu-id="43d2d-116">Legal entity</span></span> | <span data-ttu-id="43d2d-117">Określa firmę, która ma być używana do filtrowania planów na skróconej karcie Plany. Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-117">Specifies a legal entity to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="43d2d-118">Opcja objęcia świadczeniem</span><span class="sxs-lookup"><span data-stu-id="43d2d-118">Coverage option</span></span> | <span data-ttu-id="43d2d-119">Określa opcję objęcia świadczeniem, która ma być używana do filtrowania planów na skróconej karcie Plany. Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-119">Specifies a coverage option to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="43d2d-120">Domyślnie</span><span class="sxs-lookup"><span data-stu-id="43d2d-120">Default</span></span> | <span data-ttu-id="43d2d-121">Filtruje plany świadczeń na podstawie tego, czy są one planem domyślnym.</span><span class="sxs-lookup"><span data-stu-id="43d2d-121">Filters the benefit plans based on whether they are a default plan.</span></span> <span data-ttu-id="43d2d-122">Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-122">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="43d2d-123">Stan</span><span class="sxs-lookup"><span data-stu-id="43d2d-123">Status</span></span> | <span data-ttu-id="43d2d-124">Filtruje plany świadczeń na podstawie ich stanu.</span><span class="sxs-lookup"><span data-stu-id="43d2d-124">Filters benefit plans based on their status.</span></span> <span data-ttu-id="43d2d-125">Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-125">Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="43d2d-126">Potwierdzenie</span><span class="sxs-lookup"><span data-stu-id="43d2d-126">Confirmation</span></span> | <span data-ttu-id="43d2d-127">Określa stan potwierdzenia, który ma być używany do filtrowania planów na skróconej karcie Plany. Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-127">Specifies the confirmation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="43d2d-128">Anulowanie</span><span class="sxs-lookup"><span data-stu-id="43d2d-128">Cancellation</span></span> | <span data-ttu-id="43d2d-129">Określa stan anulowania, który ma być używany do filtrowania planów na skróconej karcie Plany. Wyfiltrowanie planów pomoże wybrać podzbiór spośród wszystkich rekordów planu i wtedy zatwierdzić tylko ten podzbiór.</span><span class="sxs-lookup"><span data-stu-id="43d2d-129">Specifies the cancellation status to use to filter the plans in the Plans fast tab. Filter the plans to help you select a subset of all the plan records so that you can confirm the subset.</span></span> |
   | <span data-ttu-id="43d2d-130">Filtr dat efektywnych</span><span class="sxs-lookup"><span data-stu-id="43d2d-130">Effective date filter</span></span> | <span data-ttu-id="43d2d-131">Filtruje plamy w zależności od tego, czy wygasły, są aktywne, czy też będą aktywne w przyszłości.</span><span class="sxs-lookup"><span data-stu-id="43d2d-131">Filters the plans based on whether they’re expired, active, or will be active in the future.</span></span> <span data-ttu-id="43d2d-132">Zaznacz pola wyboru odpowiadające planom, które chcesz widzieć na skróconej karcie Plany.</span><span class="sxs-lookup"><span data-stu-id="43d2d-132">Select the check boxes that correspond to the plans you want to see in the Plans fast tab.</span></span> |
   | <span data-ttu-id="43d2d-133">Plany</span><span class="sxs-lookup"><span data-stu-id="43d2d-133">Plans</span></span> | <span data-ttu-id="43d2d-134">Skrócona karta Plany zawiera plany spełniające ustawione kryteria filtrowania.</span><span class="sxs-lookup"><span data-stu-id="43d2d-134">The Plans fast tab contains the plans that meet the filter criteria you specified.</span></span> <span data-ttu-id="43d2d-135">W każdym wierszu znajdują się odpowiednie opcje konfiguracji, które zostały ustawione przez pracowników działu kadr, oraz wybory rejestracji dokonane przez pracowników.</span><span class="sxs-lookup"><span data-stu-id="43d2d-135">The relevant configuration options that were set by HR staff and the enrollment selections that were chosen by employees are included on each line.</span></span> <span data-ttu-id="43d2d-136">Pole Kwalifikowany określa, czy wybrane opcje nie powodują konfliktu z wybranym planem.</span><span class="sxs-lookup"><span data-stu-id="43d2d-136">The Qualified field specifies whether there is a validation conflict with the plan selection.</span></span> |

4. <span data-ttu-id="43d2d-137">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="43d2d-137">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]