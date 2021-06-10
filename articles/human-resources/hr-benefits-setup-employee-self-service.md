---
title: Konfigurowanie samoobsługi pracownika etatowego
description: W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1f0d39b30b7c8d0a5729ebe3b1ed9e0d569a6660
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052992"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="6edc6-103">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="6edc6-103">Configure employee self service</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6edc6-104">W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="6edc6-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="6edc6-105">Kafelki planów świadczeń kierują użytkowników do planów świadczeń, do których są uprawnieni..</span><span class="sxs-lookup"><span data-stu-id="6edc6-105">Benefit plan tiles direct users to benefit plans that they're eligible for.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="6edc6-106">Konfigurowanie kafelka planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="6edc6-106">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="6edc6-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="6edc6-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="6edc6-108">Kliknij kartę **Ustawienia kafelka planów świadczeń**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6edc6-108">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="6edc6-109">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="6edc6-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="6edc6-110">Pole</span><span class="sxs-lookup"><span data-stu-id="6edc6-110">Field</span></span> | <span data-ttu-id="6edc6-111">Opis</span><span class="sxs-lookup"><span data-stu-id="6edc6-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6edc6-112">**Identyfikator kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-112">**Tile ID**</span></span> | <span data-ttu-id="6edc6-113">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="6edc6-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="6edc6-114">**Tekst etykiety kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-114">**Tile label text**</span></span> | <span data-ttu-id="6edc6-115">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="6edc6-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="6edc6-116">**Opis**</span><span class="sxs-lookup"><span data-stu-id="6edc6-116">**Description**</span></span> | <span data-ttu-id="6edc6-117">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="6edc6-117">A description of the tile.</span></span> |
   | <span data-ttu-id="6edc6-118">**Adres internetowy**</span><span class="sxs-lookup"><span data-stu-id="6edc6-118">**Internet address**</span></span> | <span data-ttu-id="6edc6-119">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="6edc6-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="6edc6-120">**Rozmiar kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-120">**Tile size**</span></span> | <span data-ttu-id="6edc6-121">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="6edc6-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="6edc6-122">**Grupa docelowa**</span><span class="sxs-lookup"><span data-stu-id="6edc6-122">**Target**</span></span> | <span data-ttu-id="6edc6-123">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="6edc6-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="6edc6-124">**Obraz tła kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-124">**Tile background image**</span></span> | <span data-ttu-id="6edc6-125">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="6edc6-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="6edc6-126">**Uruchom**</span><span class="sxs-lookup"><span data-stu-id="6edc6-126">**Start**</span></span> | <span data-ttu-id="6edc6-127">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="6edc6-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="6edc6-128">**Zakończenie**</span><span class="sxs-lookup"><span data-stu-id="6edc6-128">**End**</span></span> | <span data-ttu-id="6edc6-129">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="6edc6-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="6edc6-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6edc6-130">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="6edc6-131">Konfigurowanie kafelka planu kredytu elastycznego</span><span class="sxs-lookup"><span data-stu-id="6edc6-131">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="6edc6-132">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="6edc6-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="6edc6-133">Kliknij kartę **Ustawienia kafelka planu kredytu elastycznego**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6edc6-133">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="6edc6-134">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="6edc6-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="6edc6-135">Pole</span><span class="sxs-lookup"><span data-stu-id="6edc6-135">Field</span></span> | <span data-ttu-id="6edc6-136">Opis</span><span class="sxs-lookup"><span data-stu-id="6edc6-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="6edc6-137">**Identyfikator kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-137">**Tile ID**</span></span> | <span data-ttu-id="6edc6-138">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="6edc6-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="6edc6-139">**Tekst etykiety kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-139">**Tile label text**</span></span> | <span data-ttu-id="6edc6-140">Tekst, który będzie wyświetlany dla kafelka w obszarze Samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="6edc6-140">The text that will appear for the tile on Self service.</span></span> |
   | <span data-ttu-id="6edc6-141">**Opis**</span><span class="sxs-lookup"><span data-stu-id="6edc6-141">**Description**</span></span> | <span data-ttu-id="6edc6-142">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="6edc6-142">A description of the tile.</span></span> |
   | <span data-ttu-id="6edc6-143">**Adres internetowy**</span><span class="sxs-lookup"><span data-stu-id="6edc6-143">**Internet address**</span></span> | <span data-ttu-id="6edc6-144">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="6edc6-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="6edc6-145">**Rozmiar kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-145">**Tile size**</span></span> | <span data-ttu-id="6edc6-146">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="6edc6-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="6edc6-147">**Grupa docelowa**</span><span class="sxs-lookup"><span data-stu-id="6edc6-147">**Target**</span></span> | <span data-ttu-id="6edc6-148">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="6edc6-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="6edc6-149">**Obraz tła kafelka**</span><span class="sxs-lookup"><span data-stu-id="6edc6-149">**Tile background image**</span></span> | <span data-ttu-id="6edc6-150">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="6edc6-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="6edc6-151">**Uruchom**</span><span class="sxs-lookup"><span data-stu-id="6edc6-151">**Start**</span></span> | <span data-ttu-id="6edc6-152">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="6edc6-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="6edc6-153">**Zakończenie**</span><span class="sxs-lookup"><span data-stu-id="6edc6-153">**End**</span></span> | <span data-ttu-id="6edc6-154">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="6edc6-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="6edc6-155">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6edc6-155">Select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]