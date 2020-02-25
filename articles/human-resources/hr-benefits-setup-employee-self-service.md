---
title: Konfigurowanie samoobsługi pracownika etatowego
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
ms.openlocfilehash: e44a35071b8d0987e6c949fb11312204317b44a1
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010213"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="32edb-102">Konfigurowanie samoobsługi pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="32edb-102">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="32edb-103">W rozwiązaniu Microsoft Dynamics 365 Human Resources można skonfigurować kafelki do nawigacji najwyższego poziomu w obszarze Samoobsługa pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="32edb-103">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="32edb-104">Kafelki planów świadczeń kierują użytkowników do planów świadczeń, w których można się rejestrować.</span><span class="sxs-lookup"><span data-stu-id="32edb-104">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="32edb-105">Konfigurowanie kafelka widoku głównego użytkownika</span><span class="sxs-lookup"><span data-stu-id="32edb-105">Set up a role center tile</span></span>

1. <span data-ttu-id="32edb-106">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="32edb-106">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="32edb-107">Kliknij kartę **Ustawienia kafelka widoku głównego użytkownika**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="32edb-107">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="32edb-108">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="32edb-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="32edb-109">Pole</span><span class="sxs-lookup"><span data-stu-id="32edb-109">Field</span></span> | <span data-ttu-id="32edb-110">Opis</span><span class="sxs-lookup"><span data-stu-id="32edb-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="32edb-111">Identyfikator kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-111">Tile ID</span></span> | <span data-ttu-id="32edb-112">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="32edb-112">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="32edb-113">Tekst etykiety kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-113">Tile label text</span></span> | <span data-ttu-id="32edb-114">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="32edb-114">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="32edb-115">Opis</span><span class="sxs-lookup"><span data-stu-id="32edb-115">Description</span></span> | <span data-ttu-id="32edb-116">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="32edb-116">A description of the tile.</span></span> |
   | <span data-ttu-id="32edb-117">Adres internetowy</span><span class="sxs-lookup"><span data-stu-id="32edb-117">Internet address</span></span> | <span data-ttu-id="32edb-118">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="32edb-118">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="32edb-119">Rozmiar kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-119">Tile size</span></span> | <span data-ttu-id="32edb-120">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="32edb-120">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="32edb-121">Grupa docelowa</span><span class="sxs-lookup"><span data-stu-id="32edb-121">Target</span></span> | <span data-ttu-id="32edb-122">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="32edb-122">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="32edb-123">Obraz tła kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-123">Tile background image</span></span> | <span data-ttu-id="32edb-124">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="32edb-124">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="32edb-125">Uruchom</span><span class="sxs-lookup"><span data-stu-id="32edb-125">Start</span></span> | <span data-ttu-id="32edb-126">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="32edb-126">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="32edb-127">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="32edb-127">End</span></span> | <span data-ttu-id="32edb-128">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="32edb-128">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="32edb-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="32edb-129">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="32edb-130">Konfigurowanie kafelka planów świadczeń</span><span class="sxs-lookup"><span data-stu-id="32edb-130">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="32edb-131">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="32edb-131">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="32edb-132">Kliknij kartę **Ustawienia kafelka planów świadczeń**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="32edb-132">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="32edb-133">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="32edb-133">Specify values for the following fields:</span></span>

   | <span data-ttu-id="32edb-134">Pole</span><span class="sxs-lookup"><span data-stu-id="32edb-134">Field</span></span> | <span data-ttu-id="32edb-135">Opis</span><span class="sxs-lookup"><span data-stu-id="32edb-135">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="32edb-136">Identyfikator kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-136">Tile ID</span></span> | <span data-ttu-id="32edb-137">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="32edb-137">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="32edb-138">Tekst etykiety kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-138">Tile label text</span></span> | <span data-ttu-id="32edb-139">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="32edb-139">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="32edb-140">Opis</span><span class="sxs-lookup"><span data-stu-id="32edb-140">Description</span></span> | <span data-ttu-id="32edb-141">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="32edb-141">A description of the tile.</span></span> |
   | <span data-ttu-id="32edb-142">Adres internetowy</span><span class="sxs-lookup"><span data-stu-id="32edb-142">Internet address</span></span> | <span data-ttu-id="32edb-143">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="32edb-143">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="32edb-144">Rozmiar kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-144">Tile size</span></span> | <span data-ttu-id="32edb-145">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="32edb-145">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="32edb-146">Grupa docelowa</span><span class="sxs-lookup"><span data-stu-id="32edb-146">Target</span></span> | <span data-ttu-id="32edb-147">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="32edb-147">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="32edb-148">Obraz tła kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-148">Tile background image</span></span> | <span data-ttu-id="32edb-149">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="32edb-149">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="32edb-150">Uruchom</span><span class="sxs-lookup"><span data-stu-id="32edb-150">Start</span></span> | <span data-ttu-id="32edb-151">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="32edb-151">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="32edb-152">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="32edb-152">End</span></span> | <span data-ttu-id="32edb-153">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="32edb-153">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="32edb-154">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="32edb-154">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="32edb-155">Konfigurowanie kafelka planu kredytu elastycznego</span><span class="sxs-lookup"><span data-stu-id="32edb-155">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="32edb-156">W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry samoobsługi pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="32edb-156">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="32edb-157">Kliknij kartę **Ustawienia kafelka planu kredytu elastycznego**, a następnie wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="32edb-157">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="32edb-158">Określ wartości dla następujących pól:</span><span class="sxs-lookup"><span data-stu-id="32edb-158">Specify values for the following fields:</span></span>

   | <span data-ttu-id="32edb-159">Pole</span><span class="sxs-lookup"><span data-stu-id="32edb-159">Field</span></span> | <span data-ttu-id="32edb-160">Opis</span><span class="sxs-lookup"><span data-stu-id="32edb-160">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="32edb-161">Identyfikator kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-161">Tile ID</span></span> | <span data-ttu-id="32edb-162">Unikatowy identyfikator dla kafelka.</span><span class="sxs-lookup"><span data-stu-id="32edb-162">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="32edb-163">Tekst etykiety kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-163">Tile label text</span></span> | <span data-ttu-id="32edb-164">Tekst, który będzie wyświetlany dla kafelka w obszarze samoobsługi.</span><span class="sxs-lookup"><span data-stu-id="32edb-164">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="32edb-165">Opis</span><span class="sxs-lookup"><span data-stu-id="32edb-165">Description</span></span> | <span data-ttu-id="32edb-166">Opis kafelka.</span><span class="sxs-lookup"><span data-stu-id="32edb-166">A description of the tile.</span></span> |
   | <span data-ttu-id="32edb-167">Adres internetowy</span><span class="sxs-lookup"><span data-stu-id="32edb-167">Internet address</span></span> | <span data-ttu-id="32edb-168">Wprowadź adres URL do strony samoobsługi pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="32edb-168">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="32edb-169">Rozmiar kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-169">Tile size</span></span> | <span data-ttu-id="32edb-170">Rozmiar kafelka: Mały, Średni lub Duży.</span><span class="sxs-lookup"><span data-stu-id="32edb-170">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="32edb-171">Grupa docelowa</span><span class="sxs-lookup"><span data-stu-id="32edb-171">Target</span></span> | <span data-ttu-id="32edb-172">Określa, czy strona ma być otwierana w nowym, czy w bieżącym oknie.</span><span class="sxs-lookup"><span data-stu-id="32edb-172">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="32edb-173">Obraz tła kafelka</span><span class="sxs-lookup"><span data-stu-id="32edb-173">Tile background image</span></span> | <span data-ttu-id="32edb-174">Adres URL obrazu, który ma być używany dla kafelka (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="32edb-174">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="32edb-175">Uruchom</span><span class="sxs-lookup"><span data-stu-id="32edb-175">Start</span></span> | <span data-ttu-id="32edb-176">Data i godzina, od kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="32edb-176">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="32edb-177">Zakończenie</span><span class="sxs-lookup"><span data-stu-id="32edb-177">End</span></span> | <span data-ttu-id="32edb-178">Data i godzina, do kiedy kafelek powinien być dostępny.</span><span class="sxs-lookup"><span data-stu-id="32edb-178">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="32edb-179">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="32edb-179">Select **Save**.</span></span>
