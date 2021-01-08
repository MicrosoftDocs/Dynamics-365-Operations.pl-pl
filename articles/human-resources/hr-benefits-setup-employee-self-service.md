---
title: Konfigurowanie samoobsługi pracownika etatowego
description: W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: d1534e37e83e22dd9860de54165c062935db3798
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420118"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="90d52-103">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="90d52-103">Configure employee self service</span></span>

<span data-ttu-id="90d52-104">W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="90d52-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="90d52-105">Kafelki planów świadczeń kierują użytkowników do planów świadczeń, do których są uprawnieni..</span><span class="sxs-lookup"><span data-stu-id="90d52-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="90d52-106">Konfigurowanie kafelka planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="90d52-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="90d52-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="90d52-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="90d52-108">Kliknij kartę **Ustawienia kafelka planów świadczeń**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="90d52-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="90d52-109">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="90d52-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="90d52-110">Pole</span><span class="sxs-lookup"><span data-stu-id="90d52-110">Field</span></span> | <span data-ttu-id="90d52-111">Opis</span><span class="sxs-lookup"><span data-stu-id="90d52-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="90d52-112">**Identyfikator kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-112">**Tile ID**</span></span> | <span data-ttu-id="90d52-113">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="90d52-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="90d52-114">**Tekst etykiety kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-114">**Tile label text**</span></span> | <span data-ttu-id="90d52-115">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="90d52-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="90d52-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="90d52-116">**Description**</span></span> | <span data-ttu-id="90d52-117">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="90d52-117">A description of the tile.</span></span> |
   | <span data-ttu-id="90d52-118">**Adres internetowy**</span><span class="sxs-lookup"><span data-stu-id="90d52-118">**Internet address**</span></span> | <span data-ttu-id="90d52-119">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="90d52-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="90d52-120">**Rozmiar kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-120">**Tile size**</span></span> | <span data-ttu-id="90d52-121">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="90d52-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="90d52-122">**Grupa docelowa**</span><span class="sxs-lookup"><span data-stu-id="90d52-122">**Target**</span></span> | <span data-ttu-id="90d52-123">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="90d52-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="90d52-124">**Obraz tła kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-124">**Tile background image**</span></span> | <span data-ttu-id="90d52-125">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="90d52-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="90d52-126">**Uruchom**</span><span class="sxs-lookup"><span data-stu-id="90d52-126">**Start**</span></span> | <span data-ttu-id="90d52-127">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="90d52-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="90d52-128">**Zakończenie**</span><span class="sxs-lookup"><span data-stu-id="90d52-128">**End**</span></span> | <span data-ttu-id="90d52-129">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="90d52-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="90d52-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="90d52-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="90d52-131">Konfigurowanie kafelka planu kredytu elastycznego</span><span class="sxs-lookup"><span data-stu-id="90d52-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="90d52-132">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="90d52-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="90d52-133">Kliknij kartę **Ustawienia kafelka planu kredytu elastycznego**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="90d52-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="90d52-134">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="90d52-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="90d52-135">Pole</span><span class="sxs-lookup"><span data-stu-id="90d52-135">Field</span></span> | <span data-ttu-id="90d52-136">Opis</span><span class="sxs-lookup"><span data-stu-id="90d52-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="90d52-137">**Identyfikator kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-137">**Tile ID**</span></span> | <span data-ttu-id="90d52-138">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="90d52-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="90d52-139">**Tekst etykiety kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-139">**Tile label text**</span></span> | <span data-ttu-id="90d52-140">Tekst, który będzie wyświetlany dla kafelka w obszarze Samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="90d52-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="90d52-141">**Opis**</span><span class="sxs-lookup"><span data-stu-id="90d52-141">**Description**</span></span> | <span data-ttu-id="90d52-142">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="90d52-142">A description of the tile.</span></span> |
   | <span data-ttu-id="90d52-143">**Adres internetowy**</span><span class="sxs-lookup"><span data-stu-id="90d52-143">**Internet address**</span></span> | <span data-ttu-id="90d52-144">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="90d52-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="90d52-145">**Rozmiar kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-145">**Tile size**</span></span> | <span data-ttu-id="90d52-146">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="90d52-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="90d52-147">**Grupa docelowa**</span><span class="sxs-lookup"><span data-stu-id="90d52-147">**Target**</span></span> | <span data-ttu-id="90d52-148">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="90d52-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="90d52-149">**Obraz tła kafelka**</span><span class="sxs-lookup"><span data-stu-id="90d52-149">**Tile background image**</span></span> | <span data-ttu-id="90d52-150">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="90d52-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="90d52-151">**Uruchom**</span><span class="sxs-lookup"><span data-stu-id="90d52-151">**Start**</span></span> | <span data-ttu-id="90d52-152">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="90d52-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="90d52-153">**Zakończenie**</span><span class="sxs-lookup"><span data-stu-id="90d52-153">**End**</span></span> | <span data-ttu-id="90d52-154">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="90d52-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="90d52-155">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="90d52-155">Select **Save**.</span></span>
