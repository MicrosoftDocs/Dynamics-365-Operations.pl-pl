---
title: "Obsługa tablicy Kanban przeniesienia dla skanerów kodów kreskowych"
description: "Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1dc40de2b77be5c5c2399fd55c3c3bd15a9f24ec
ms.contentlocale: pl-pl
ms.lasthandoff: 08/29/2017

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="25583-103">Obsługa tablicy Kanban przeniesienia dla skanerów kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="25583-103">Kanban transfer board support for barcode scanners</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="25583-104">Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="25583-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="25583-105">Tryby rejestracji</span><span class="sxs-lookup"><span data-stu-id="25583-105">Registration modes</span></span>
------------------

<span data-ttu-id="25583-106">Na skróconej karcie **Rejestracja skanera** można wybrać tryb rejestracji kontrolujący działanie, podczas którego użytkownik skanuje numer karty Kanban lub ręcznie wpisuje numer w polu Numer karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="25583-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>
| <span data-ttu-id="25583-107">Ustaw tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="25583-107">Set registration mode</span></span> | <span data-ttu-id="25583-108">Opis</span><span class="sxs-lookup"><span data-stu-id="25583-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="25583-109">Uruchom</span><span class="sxs-lookup"><span data-stu-id="25583-109">Start</span></span>                 | <span data-ttu-id="25583-110">Rejestruje zadanie przeniesienia w systemie Kanban jako zadania w toku.</span><span class="sxs-lookup"><span data-stu-id="25583-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="25583-111">Zakończono</span><span class="sxs-lookup"><span data-stu-id="25583-111">Complete</span></span>              | <span data-ttu-id="25583-112">Rejestruje zadanie przeniesienia w systemie Kanban jako zakończonego.</span><span class="sxs-lookup"><span data-stu-id="25583-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="25583-113">Puste</span><span class="sxs-lookup"><span data-stu-id="25583-113">Empty</span></span>                 | <span data-ttu-id="25583-114">Rejestruje magazynową jednostkę obsługi materiału, do której odwołuje się karta Kanban, jako pustą</span><span class="sxs-lookup"><span data-stu-id="25583-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="25583-115">Wybierz</span><span class="sxs-lookup"><span data-stu-id="25583-115">Select</span></span>                | <span data-ttu-id="25583-116">Rejestruje numer karty Kanban i automatyczne wybiera z listy zadań w systemie Kanban to zadanie, do którego odwołuje się ta karta</span><span class="sxs-lookup"><span data-stu-id="25583-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="25583-117">Wybierz tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="25583-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="25583-118">Gdy użyjesz czytnika kodów kreskowych do wybrania zadania, tryb wyświetlania na tablicy Kanban zmieni się.</span><span class="sxs-lookup"><span data-stu-id="25583-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="25583-119">W tym trybie mają zastosowanie następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="25583-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="25583-120">Wyświetlane są tylko zeskanowane zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="25583-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="25583-121">Szczegóły wybranego zadania są wyświetlane w na skróconej karcie **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="25583-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="25583-122">Skrócona karta **Wiadomości** wyświetla komunikaty tylko dla wybranego zadania.</span><span class="sxs-lookup"><span data-stu-id="25583-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="25583-123">Stan zadania można zmienić za pomocą funkcji, które są dostępne w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="25583-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="25583-124">Tablica Kanban przeniesienia jest nadal wyświetlana w jednym zadaniu w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="25583-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="25583-125">Informacje na liście zadań można aktualizować ręcznie przez kliknięcie przycisku **Odśwież** (Shift + F5) w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="25583-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="25583-126">Po odświeżeniu informacji pełne wyniki filtru zadania są wyświetlane ponownie.</span><span class="sxs-lookup"><span data-stu-id="25583-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="25583-127">Stan i możliwe akcje zadania</span><span class="sxs-lookup"><span data-stu-id="25583-127">Job status and possible actions</span></span>
<span data-ttu-id="25583-128">Stan wybranego zadania oraz stan wszelkich niezaplanowanych zadań dla w dla kart Kanban zdarzenia, określają, czy zadanie może być dalej przetwarzane.</span><span class="sxs-lookup"><span data-stu-id="25583-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="25583-129">Poniższa tabela pokazuje informacje dotyczące tych stanów i zadań:</span><span class="sxs-lookup"><span data-stu-id="25583-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="25583-130">Stany, które są dostępne dla zadań lub dla jednostek załadunkowych, do których odwołują się zadania.</span><span class="sxs-lookup"><span data-stu-id="25583-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="25583-131">Każde zadanie, które można wykonać dla zadania.</span><span class="sxs-lookup"><span data-stu-id="25583-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25583-132">Typ zadania</span><span class="sxs-lookup"><span data-stu-id="25583-132">Job type</span></span></th>
<th><span data-ttu-id="25583-133">Stan zadania lub stan jednostki załadunkowej</span><span class="sxs-lookup"><span data-stu-id="25583-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="25583-134">Aktualizuj listę pobrania</span><span class="sxs-lookup"><span data-stu-id="25583-134">Update picking list</span></span></th>
<th><span data-ttu-id="25583-135">Uruchom</span><span class="sxs-lookup"><span data-stu-id="25583-135">Start</span></span></th>
<th><span data-ttu-id="25583-136">Aktualizuj rejestrację</span><span class="sxs-lookup"><span data-stu-id="25583-136">Update registration</span></span></th>
<th><span data-ttu-id="25583-137">Zakończono</span><span class="sxs-lookup"><span data-stu-id="25583-137">Complete</span></span></th>
<th><span data-ttu-id="25583-138">Puste</span><span class="sxs-lookup"><span data-stu-id="25583-138">Empty</span></span></th>
<th><span data-ttu-id="25583-139">Utwórz zdarzenia Kanban</span><span class="sxs-lookup"><span data-stu-id="25583-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="25583-140">Przenieś</span><span class="sxs-lookup"><span data-stu-id="25583-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="25583-141">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="25583-141">Not planned</span></span></li>
<li><span data-ttu-id="25583-142">Brak ustalonych zadań lub żadne ustalone zadanie nie ma stanu Zakończono</span><span class="sxs-lookup"><span data-stu-id="25583-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="25583-143">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-143">Yes</span></span></td>
<td><span data-ttu-id="25583-144">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-144">Yes</span></span></td>
<td><span data-ttu-id="25583-145">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-145">Yes</span></span></td>
<td><span data-ttu-id="25583-146">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-146">Yes</span></span></td>
<td><span data-ttu-id="25583-147">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-147">No</span></span></td>
<td><span data-ttu-id="25583-148">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="25583-149">Przenieś</span><span class="sxs-lookup"><span data-stu-id="25583-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="25583-150">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="25583-150">Not planned</span></span></li>
<li><span data-ttu-id="25583-151">Ustalone zadanie nie ma stanu Zakończone</span><span class="sxs-lookup"><span data-stu-id="25583-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="25583-152">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-152">Yes</span></span></td>
<td><span data-ttu-id="25583-153">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-153">No</span></span></td>
<td><span data-ttu-id="25583-154">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-154">Yes</span></span></td>
<td><span data-ttu-id="25583-155">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-155">No</span></span></td>
<td><span data-ttu-id="25583-156">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-156">No</span></span></td>
<td><span data-ttu-id="25583-157">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="25583-158">Przenieś</span><span class="sxs-lookup"><span data-stu-id="25583-158">Transfer</span></span></td>
<td><span data-ttu-id="25583-159">W toku</span><span class="sxs-lookup"><span data-stu-id="25583-159">In progress</span></span></td>
<td><span data-ttu-id="25583-160">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-160">Yes</span></span></td>
<td><span data-ttu-id="25583-161">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-161">No</span></span></td>
<td><span data-ttu-id="25583-162">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-162">Yes</span></span></td>
<td><span data-ttu-id="25583-163">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-163">Yes</span></span></td>
<td><span data-ttu-id="25583-164">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-164">No</span></span></td>
<td><span data-ttu-id="25583-165">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="25583-166">Przenieś</span><span class="sxs-lookup"><span data-stu-id="25583-166">Transfer</span></span></td>
<td><span data-ttu-id="25583-167">Ukończono</span><span class="sxs-lookup"><span data-stu-id="25583-167">Completed</span></span></td>
<td><span data-ttu-id="25583-168">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-168">No</span></span></td>
<td><span data-ttu-id="25583-169">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-169">No</span></span></td>
<td><span data-ttu-id="25583-170">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-170">No</span></span></td>
<td><span data-ttu-id="25583-171">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-171">No</span></span></td>
<td><span data-ttu-id="25583-172">Tak</span><span class="sxs-lookup"><span data-stu-id="25583-172">Yes</span></span></td>
<td><span data-ttu-id="25583-173">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="25583-174">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="25583-174">Transfer or process</span></span></td>
<td><span data-ttu-id="25583-175">Puste</span><span class="sxs-lookup"><span data-stu-id="25583-175">Empty</span></span></td>
<td><span data-ttu-id="25583-176">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-176">No</span></span></td>
<td><span data-ttu-id="25583-177">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-177">No</span></span></td>
<td><span data-ttu-id="25583-178">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-178">No</span></span></td>
<td><span data-ttu-id="25583-179">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-179">No</span></span></td>
<td><span data-ttu-id="25583-180">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-180">No</span></span></td>
<td><span data-ttu-id="25583-181">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="25583-182">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="25583-182">Transfer or process</span></span></td>
<td><span data-ttu-id="25583-183">Nie znaleziono karty Kanban</span><span class="sxs-lookup"><span data-stu-id="25583-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="25583-184">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-184">No</span></span></td>
<td><span data-ttu-id="25583-185">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-185">No</span></span></td>
<td><span data-ttu-id="25583-186">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-186">No</span></span></td>
<td><span data-ttu-id="25583-187">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-187">No</span></span></td>
<td><span data-ttu-id="25583-188">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-188">No</span></span></td>
<td><span data-ttu-id="25583-189">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="25583-190">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="25583-190">Transfer or process</span></span></td>
<td><span data-ttu-id="25583-191">Znaleziono kartę Kanban, ale nie jest ona przypisana do zadania Kanban</span><span class="sxs-lookup"><span data-stu-id="25583-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="25583-192">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-192">No</span></span></td>
<td><span data-ttu-id="25583-193">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-193">No</span></span></td>
<td><span data-ttu-id="25583-194">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-194">No</span></span></td>
<td><span data-ttu-id="25583-195">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-195">No</span></span></td>
<td><span data-ttu-id="25583-196">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-196">No</span></span></td>
<td><span data-ttu-id="25583-197">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="25583-198">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="25583-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="25583-199">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="25583-199">Not planned</span></span></li>
<li><span data-ttu-id="25583-200">Przygotowane</span><span class="sxs-lookup"><span data-stu-id="25583-200">Prepared</span></span></li>
<li><span data-ttu-id="25583-201">W toku</span><span class="sxs-lookup"><span data-stu-id="25583-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="25583-202">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-202">No</span></span></td>
<td><span data-ttu-id="25583-203">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-203">No</span></span></td>
<td><span data-ttu-id="25583-204">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-204">No</span></span></td>
<td><span data-ttu-id="25583-205">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-205">No</span></span></td>
<td><span data-ttu-id="25583-206">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-206">No</span></span></td>
<td><span data-ttu-id="25583-207">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="25583-208">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="25583-208">Process</span></span></td>
<td><span data-ttu-id="25583-209">Ukończono</span><span class="sxs-lookup"><span data-stu-id="25583-209">Completed</span></span></td>
<td><span data-ttu-id="25583-210">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-210">No</span></span></td>
<td><span data-ttu-id="25583-211">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-211">No</span></span></td>
<td><span data-ttu-id="25583-212">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-212">No</span></span></td>
<td><span data-ttu-id="25583-213">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-213">No</span></span></td>
<td><span data-ttu-id="25583-214">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-214">No</span></span></td>
<td><span data-ttu-id="25583-215">Nie</span><span class="sxs-lookup"><span data-stu-id="25583-215">No</span></span></td>
</tr>
</tbody>
</table>






