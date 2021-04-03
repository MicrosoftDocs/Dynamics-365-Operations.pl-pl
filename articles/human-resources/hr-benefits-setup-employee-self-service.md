---
title: Konfigurowanie samoobsługi pracownika etatowego
description: W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.
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
ms.openlocfilehash: c4fe8f7afd4b77636ce77e58a2e75196fddae132
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466117"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="d14df-103">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="d14df-103">Configure employee self service</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d14df-104">W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="d14df-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="d14df-105">Kafelki planów świadczeń kierują użytkowników do planów świadczeń, do których są uprawnieni..</span><span class="sxs-lookup"><span data-stu-id="d14df-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="d14df-106">Konfigurowanie kafelka planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="d14df-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="d14df-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="d14df-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="d14df-108">Kliknij kartę **Ustawienia kafelka planów świadczeń**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d14df-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="d14df-109">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="d14df-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d14df-110">Pole</span><span class="sxs-lookup"><span data-stu-id="d14df-110">Field</span></span> | <span data-ttu-id="d14df-111">Opis</span><span class="sxs-lookup"><span data-stu-id="d14df-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d14df-112">**Identyfikator kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-112">**Tile ID**</span></span> | <span data-ttu-id="d14df-113">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="d14df-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="d14df-114">**Tekst etykiety kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-114">**Tile label text**</span></span> | <span data-ttu-id="d14df-115">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="d14df-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="d14df-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="d14df-116">**Description**</span></span> | <span data-ttu-id="d14df-117">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="d14df-117">A description of the tile.</span></span> |
   | <span data-ttu-id="d14df-118">**Adres internetowy**</span><span class="sxs-lookup"><span data-stu-id="d14df-118">**Internet address**</span></span> | <span data-ttu-id="d14df-119">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="d14df-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="d14df-120">**Rozmiar kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-120">**Tile size**</span></span> | <span data-ttu-id="d14df-121">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="d14df-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="d14df-122">**Grupa docelowa**</span><span class="sxs-lookup"><span data-stu-id="d14df-122">**Target**</span></span> | <span data-ttu-id="d14df-123">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="d14df-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="d14df-124">**Obraz tła kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-124">**Tile background image**</span></span> | <span data-ttu-id="d14df-125">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="d14df-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="d14df-126">**Uruchom**</span><span class="sxs-lookup"><span data-stu-id="d14df-126">**Start**</span></span> | <span data-ttu-id="d14df-127">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="d14df-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="d14df-128">**Zakończenie**</span><span class="sxs-lookup"><span data-stu-id="d14df-128">**End**</span></span> | <span data-ttu-id="d14df-129">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="d14df-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="d14df-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d14df-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="d14df-131">Konfigurowanie kafelka planu kredytu elastycznego</span><span class="sxs-lookup"><span data-stu-id="d14df-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="d14df-132">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="d14df-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="d14df-133">Kliknij kartę **Ustawienia kafelka planu kredytu elastycznego**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="d14df-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="d14df-134">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="d14df-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="d14df-135">Pole</span><span class="sxs-lookup"><span data-stu-id="d14df-135">Field</span></span> | <span data-ttu-id="d14df-136">Opis</span><span class="sxs-lookup"><span data-stu-id="d14df-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="d14df-137">**Identyfikator kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-137">**Tile ID**</span></span> | <span data-ttu-id="d14df-138">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="d14df-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="d14df-139">**Tekst etykiety kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-139">**Tile label text**</span></span> | <span data-ttu-id="d14df-140">Tekst, który będzie wyświetlany dla kafelka w obszarze Samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="d14df-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="d14df-141">**Opis**</span><span class="sxs-lookup"><span data-stu-id="d14df-141">**Description**</span></span> | <span data-ttu-id="d14df-142">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="d14df-142">A description of the tile.</span></span> |
   | <span data-ttu-id="d14df-143">**Adres internetowy**</span><span class="sxs-lookup"><span data-stu-id="d14df-143">**Internet address**</span></span> | <span data-ttu-id="d14df-144">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="d14df-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="d14df-145">**Rozmiar kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-145">**Tile size**</span></span> | <span data-ttu-id="d14df-146">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="d14df-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="d14df-147">**Grupa docelowa**</span><span class="sxs-lookup"><span data-stu-id="d14df-147">**Target**</span></span> | <span data-ttu-id="d14df-148">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="d14df-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="d14df-149">**Obraz tła kafelka**</span><span class="sxs-lookup"><span data-stu-id="d14df-149">**Tile background image**</span></span> | <span data-ttu-id="d14df-150">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="d14df-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="d14df-151">**Uruchom**</span><span class="sxs-lookup"><span data-stu-id="d14df-151">**Start**</span></span> | <span data-ttu-id="d14df-152">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="d14df-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="d14df-153">**Zakończenie**</span><span class="sxs-lookup"><span data-stu-id="d14df-153">**End**</span></span> | <span data-ttu-id="d14df-154">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="d14df-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="d14df-155">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="d14df-155">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]