---
title: Konfigurowanie samoobsługi pracownika etatowego
description: W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.
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
ms.openlocfilehash: 17918fc7b894929c92c54b59b7440ab8aef980bd
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092667"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="54e7b-103">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="54e7b-103">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="54e7b-104">W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="54e7b-104">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="54e7b-105">Kafelki planów świadczeń kierują użytkowników do planów świadczeń, w których można się rejestrować.</span><span class="sxs-lookup"><span data-stu-id="54e7b-105">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="54e7b-106">Konfigurowanie kafelka widoku głównego użytkownika</span><span class="sxs-lookup"><span data-stu-id="54e7b-106">Set up a role center tile</span></span>

1. <span data-ttu-id="54e7b-107">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-107">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="54e7b-108">Kliknij kartę **Ustawienia kafelka widoku głównego użytkownika**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-108">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="54e7b-109">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="54e7b-109">Specify values for the following fields:</span></span>

   | <span data-ttu-id="54e7b-110">Pole</span><span class="sxs-lookup"><span data-stu-id="54e7b-110">Field</span></span> | <span data-ttu-id="54e7b-111">Opis</span><span class="sxs-lookup"><span data-stu-id="54e7b-111">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="54e7b-112">Identyfikator kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-112">Tile ID</span></span> | <span data-ttu-id="54e7b-113">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="54e7b-113">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="54e7b-114">Tekst etykiety kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-114">Tile label text</span></span> | <span data-ttu-id="54e7b-115">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="54e7b-115">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="54e7b-116">Opis</span><span class="sxs-lookup"><span data-stu-id="54e7b-116">Description</span></span> | <span data-ttu-id="54e7b-117">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="54e7b-117">A description of the tile.</span></span> |
   | <span data-ttu-id="54e7b-118">Adres internetowy</span><span class="sxs-lookup"><span data-stu-id="54e7b-118">Internet address</span></span> | <span data-ttu-id="54e7b-119">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="54e7b-119">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="54e7b-120">Rozmiar kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-120">Tile size</span></span> | <span data-ttu-id="54e7b-121">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="54e7b-121">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="54e7b-122">Grupa docelowa</span><span class="sxs-lookup"><span data-stu-id="54e7b-122">Target</span></span> | <span data-ttu-id="54e7b-123">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="54e7b-123">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="54e7b-124">Obraz tła kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-124">Tile background image</span></span> | <span data-ttu-id="54e7b-125">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="54e7b-125">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="54e7b-126">Uruchom</span><span class="sxs-lookup"><span data-stu-id="54e7b-126">Start</span></span> | <span data-ttu-id="54e7b-127">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="54e7b-127">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="54e7b-128">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="54e7b-128">End</span></span> | <span data-ttu-id="54e7b-129">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="54e7b-129">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="54e7b-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-130">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="54e7b-131">Konfigurowanie kafelka planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="54e7b-131">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="54e7b-132">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-132">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="54e7b-133">Kliknij kartę **Ustawienia kafelka planów świadczeń**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-133">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="54e7b-134">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="54e7b-134">Specify values for the following fields:</span></span>

   | <span data-ttu-id="54e7b-135">Pole</span><span class="sxs-lookup"><span data-stu-id="54e7b-135">Field</span></span> | <span data-ttu-id="54e7b-136">Opis</span><span class="sxs-lookup"><span data-stu-id="54e7b-136">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="54e7b-137">Identyfikator kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-137">Tile ID</span></span> | <span data-ttu-id="54e7b-138">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="54e7b-138">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="54e7b-139">Tekst etykiety kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-139">Tile label text</span></span> | <span data-ttu-id="54e7b-140">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="54e7b-140">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="54e7b-141">Opis</span><span class="sxs-lookup"><span data-stu-id="54e7b-141">Description</span></span> | <span data-ttu-id="54e7b-142">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="54e7b-142">A description of the tile.</span></span> |
   | <span data-ttu-id="54e7b-143">Adres internetowy</span><span class="sxs-lookup"><span data-stu-id="54e7b-143">Internet address</span></span> | <span data-ttu-id="54e7b-144">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="54e7b-144">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="54e7b-145">Rozmiar kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-145">Tile size</span></span> | <span data-ttu-id="54e7b-146">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="54e7b-146">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="54e7b-147">Grupa docelowa</span><span class="sxs-lookup"><span data-stu-id="54e7b-147">Target</span></span> | <span data-ttu-id="54e7b-148">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="54e7b-148">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="54e7b-149">Obraz tła kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-149">Tile background image</span></span> | <span data-ttu-id="54e7b-150">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="54e7b-150">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="54e7b-151">Uruchom</span><span class="sxs-lookup"><span data-stu-id="54e7b-151">Start</span></span> | <span data-ttu-id="54e7b-152">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="54e7b-152">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="54e7b-153">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="54e7b-153">End</span></span> | <span data-ttu-id="54e7b-154">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="54e7b-154">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="54e7b-155">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-155">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="54e7b-156">Konfigurowanie kafelka planu kredytu elastycznego</span><span class="sxs-lookup"><span data-stu-id="54e7b-156">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="54e7b-157">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-157">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="54e7b-158">Kliknij kartę **Ustawienia kafelka planu kredytu elastycznego**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-158">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="54e7b-159">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="54e7b-159">Specify values for the following fields:</span></span>

   | <span data-ttu-id="54e7b-160">Pole</span><span class="sxs-lookup"><span data-stu-id="54e7b-160">Field</span></span> | <span data-ttu-id="54e7b-161">Opis</span><span class="sxs-lookup"><span data-stu-id="54e7b-161">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="54e7b-162">Identyfikator kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-162">Tile ID</span></span> | <span data-ttu-id="54e7b-163">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="54e7b-163">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="54e7b-164">Tekst etykiety kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-164">Tile label text</span></span> | <span data-ttu-id="54e7b-165">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="54e7b-165">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="54e7b-166">Opis</span><span class="sxs-lookup"><span data-stu-id="54e7b-166">Description</span></span> | <span data-ttu-id="54e7b-167">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="54e7b-167">A description of the tile.</span></span> |
   | <span data-ttu-id="54e7b-168">Adres internetowy</span><span class="sxs-lookup"><span data-stu-id="54e7b-168">Internet address</span></span> | <span data-ttu-id="54e7b-169">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="54e7b-169">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="54e7b-170">Rozmiar kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-170">Tile size</span></span> | <span data-ttu-id="54e7b-171">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="54e7b-171">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="54e7b-172">Grupa docelowa</span><span class="sxs-lookup"><span data-stu-id="54e7b-172">Target</span></span> | <span data-ttu-id="54e7b-173">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="54e7b-173">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="54e7b-174">Obraz tła kafelka</span><span class="sxs-lookup"><span data-stu-id="54e7b-174">Tile background image</span></span> | <span data-ttu-id="54e7b-175">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="54e7b-175">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="54e7b-176">Uruchom</span><span class="sxs-lookup"><span data-stu-id="54e7b-176">Start</span></span> | <span data-ttu-id="54e7b-177">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="54e7b-177">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="54e7b-178">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="54e7b-178">End</span></span> | <span data-ttu-id="54e7b-179">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="54e7b-179">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="54e7b-180">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="54e7b-180">Select **Save**.</span></span>
