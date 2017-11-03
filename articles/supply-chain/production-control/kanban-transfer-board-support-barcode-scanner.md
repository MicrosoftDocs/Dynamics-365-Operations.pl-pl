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
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a8393efd51032271d3023f1e0569425a16222cc3
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="51e65-103">Obsługa tablicy Kanban przeniesienia dla skanerów kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="51e65-103">Kanban transfer board support for barcode scanners</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="51e65-104">Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="51e65-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="51e65-105">Tryby rejestracji</span><span class="sxs-lookup"><span data-stu-id="51e65-105">Registration modes</span></span>
------------------

<span data-ttu-id="51e65-106">Na skróconej karcie **Rejestracja skanera** można wybrać tryb rejestracji kontrolujący działanie, podczas którego użytkownik skanuje numer karty Kanban lub ręcznie wpisuje numer w polu Numer karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="51e65-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>
| <span data-ttu-id="51e65-107">Ustaw tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="51e65-107">Set registration mode</span></span> | <span data-ttu-id="51e65-108">Opis</span><span class="sxs-lookup"><span data-stu-id="51e65-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="51e65-109">Uruchom</span><span class="sxs-lookup"><span data-stu-id="51e65-109">Start</span></span>                 | <span data-ttu-id="51e65-110">Rejestruje zadanie przeniesienia w systemie Kanban jako zadania w toku.</span><span class="sxs-lookup"><span data-stu-id="51e65-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="51e65-111">Zakończono</span><span class="sxs-lookup"><span data-stu-id="51e65-111">Complete</span></span>              | <span data-ttu-id="51e65-112">Rejestruje zadanie przeniesienia w systemie Kanban jako zakończonego.</span><span class="sxs-lookup"><span data-stu-id="51e65-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="51e65-113">Puste</span><span class="sxs-lookup"><span data-stu-id="51e65-113">Empty</span></span>                 | <span data-ttu-id="51e65-114">Rejestruje magazynową jednostkę obsługi materiału, do której odwołuje się karta Kanban, jako pustą</span><span class="sxs-lookup"><span data-stu-id="51e65-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="51e65-115">Wybierz</span><span class="sxs-lookup"><span data-stu-id="51e65-115">Select</span></span>                | <span data-ttu-id="51e65-116">Rejestruje numer karty Kanban i automatyczne wybiera z listy zadań w systemie Kanban to zadanie, do którego odwołuje się ta karta</span><span class="sxs-lookup"><span data-stu-id="51e65-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="51e65-117">Wybierz tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="51e65-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="51e65-118">Gdy użyjesz czytnika kodów kreskowych do wybrania zadania, tryb wyświetlania na tablicy Kanban zmieni się.</span><span class="sxs-lookup"><span data-stu-id="51e65-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="51e65-119">W tym trybie mają zastosowanie następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="51e65-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="51e65-120">Wyświetlane są tylko zeskanowane zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="51e65-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="51e65-121">Szczegóły wybranego zadania są wyświetlane w na skróconej karcie **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="51e65-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="51e65-122">Skrócona karta **Wiadomości** wyświetla komunikaty tylko dla wybranego zadania.</span><span class="sxs-lookup"><span data-stu-id="51e65-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="51e65-123">Stan zadania można zmienić za pomocą funkcji, które są dostępne w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="51e65-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="51e65-124">Tablica Kanban przeniesienia jest nadal wyświetlana w jednym zadaniu w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="51e65-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="51e65-125">Informacje na liście zadań można aktualizować ręcznie przez kliknięcie przycisku **Odśwież** (Shift + F5) w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="51e65-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="51e65-126">Po odświeżeniu informacji pełne wyniki filtru zadania są wyświetlane ponownie.</span><span class="sxs-lookup"><span data-stu-id="51e65-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="51e65-127">Stan i możliwe akcje zadania</span><span class="sxs-lookup"><span data-stu-id="51e65-127">Job status and possible actions</span></span>
<span data-ttu-id="51e65-128">Stan wybranego zadania oraz stan wszelkich niezaplanowanych zadań dla w dla kart Kanban zdarzenia, określają, czy zadanie może być dalej przetwarzane.</span><span class="sxs-lookup"><span data-stu-id="51e65-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="51e65-129">Poniższa tabela pokazuje informacje dotyczące tych stanów i zadań:</span><span class="sxs-lookup"><span data-stu-id="51e65-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="51e65-130">Stany, które są dostępne dla zadań lub dla jednostek załadunkowych, do których odwołują się zadania.</span><span class="sxs-lookup"><span data-stu-id="51e65-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="51e65-131">Każde zadanie, które można wykonać dla zadania.</span><span class="sxs-lookup"><span data-stu-id="51e65-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="51e65-132">Typ zadania</span><span class="sxs-lookup"><span data-stu-id="51e65-132">Job type</span></span></th>
<th><span data-ttu-id="51e65-133">Stan zadania lub stan jednostki załadunkowej</span><span class="sxs-lookup"><span data-stu-id="51e65-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="51e65-134">Aktualizuj listę pobrania</span><span class="sxs-lookup"><span data-stu-id="51e65-134">Update picking list</span></span></th>
<th><span data-ttu-id="51e65-135">Uruchom</span><span class="sxs-lookup"><span data-stu-id="51e65-135">Start</span></span></th>
<th><span data-ttu-id="51e65-136">Aktualizuj rejestrację</span><span class="sxs-lookup"><span data-stu-id="51e65-136">Update registration</span></span></th>
<th><span data-ttu-id="51e65-137">Zakończono</span><span class="sxs-lookup"><span data-stu-id="51e65-137">Complete</span></span></th>
<th><span data-ttu-id="51e65-138">Puste</span><span class="sxs-lookup"><span data-stu-id="51e65-138">Empty</span></span></th>
<th><span data-ttu-id="51e65-139">Utwórz zdarzenia Kanban</span><span class="sxs-lookup"><span data-stu-id="51e65-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="51e65-140">Przenieś</span><span class="sxs-lookup"><span data-stu-id="51e65-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="51e65-141">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="51e65-141">Not planned</span></span></li>
<li><span data-ttu-id="51e65-142">Brak ustalonych zadań lub żadne ustalone zadanie nie ma stanu Zakończono</span><span class="sxs-lookup"><span data-stu-id="51e65-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="51e65-143">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-143">Yes</span></span></td>
<td><span data-ttu-id="51e65-144">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-144">Yes</span></span></td>
<td><span data-ttu-id="51e65-145">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-145">Yes</span></span></td>
<td><span data-ttu-id="51e65-146">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-146">Yes</span></span></td>
<td><span data-ttu-id="51e65-147">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-147">No</span></span></td>
<td><span data-ttu-id="51e65-148">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51e65-149">Przenieś</span><span class="sxs-lookup"><span data-stu-id="51e65-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="51e65-150">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="51e65-150">Not planned</span></span></li>
<li><span data-ttu-id="51e65-151">Ustalone zadanie nie ma stanu Zakończone</span><span class="sxs-lookup"><span data-stu-id="51e65-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="51e65-152">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-152">Yes</span></span></td>
<td><span data-ttu-id="51e65-153">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-153">No</span></span></td>
<td><span data-ttu-id="51e65-154">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-154">Yes</span></span></td>
<td><span data-ttu-id="51e65-155">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-155">No</span></span></td>
<td><span data-ttu-id="51e65-156">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-156">No</span></span></td>
<td><span data-ttu-id="51e65-157">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51e65-158">Przenieś</span><span class="sxs-lookup"><span data-stu-id="51e65-158">Transfer</span></span></td>
<td><span data-ttu-id="51e65-159">W toku</span><span class="sxs-lookup"><span data-stu-id="51e65-159">In progress</span></span></td>
<td><span data-ttu-id="51e65-160">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-160">Yes</span></span></td>
<td><span data-ttu-id="51e65-161">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-161">No</span></span></td>
<td><span data-ttu-id="51e65-162">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-162">Yes</span></span></td>
<td><span data-ttu-id="51e65-163">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-163">Yes</span></span></td>
<td><span data-ttu-id="51e65-164">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-164">No</span></span></td>
<td><span data-ttu-id="51e65-165">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51e65-166">Przenieś</span><span class="sxs-lookup"><span data-stu-id="51e65-166">Transfer</span></span></td>
<td><span data-ttu-id="51e65-167">Ukończono</span><span class="sxs-lookup"><span data-stu-id="51e65-167">Completed</span></span></td>
<td><span data-ttu-id="51e65-168">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-168">No</span></span></td>
<td><span data-ttu-id="51e65-169">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-169">No</span></span></td>
<td><span data-ttu-id="51e65-170">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-170">No</span></span></td>
<td><span data-ttu-id="51e65-171">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-171">No</span></span></td>
<td><span data-ttu-id="51e65-172">Tak</span><span class="sxs-lookup"><span data-stu-id="51e65-172">Yes</span></span></td>
<td><span data-ttu-id="51e65-173">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51e65-174">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="51e65-174">Transfer or process</span></span></td>
<td><span data-ttu-id="51e65-175">Puste</span><span class="sxs-lookup"><span data-stu-id="51e65-175">Empty</span></span></td>
<td><span data-ttu-id="51e65-176">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-176">No</span></span></td>
<td><span data-ttu-id="51e65-177">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-177">No</span></span></td>
<td><span data-ttu-id="51e65-178">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-178">No</span></span></td>
<td><span data-ttu-id="51e65-179">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-179">No</span></span></td>
<td><span data-ttu-id="51e65-180">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-180">No</span></span></td>
<td><span data-ttu-id="51e65-181">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51e65-182">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="51e65-182">Transfer or process</span></span></td>
<td><span data-ttu-id="51e65-183">Nie znaleziono karty Kanban</span><span class="sxs-lookup"><span data-stu-id="51e65-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="51e65-184">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-184">No</span></span></td>
<td><span data-ttu-id="51e65-185">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-185">No</span></span></td>
<td><span data-ttu-id="51e65-186">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-186">No</span></span></td>
<td><span data-ttu-id="51e65-187">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-187">No</span></span></td>
<td><span data-ttu-id="51e65-188">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-188">No</span></span></td>
<td><span data-ttu-id="51e65-189">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51e65-190">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="51e65-190">Transfer or process</span></span></td>
<td><span data-ttu-id="51e65-191">Znaleziono kartę Kanban, ale nie jest ona przypisana do zadania Kanban</span><span class="sxs-lookup"><span data-stu-id="51e65-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="51e65-192">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-192">No</span></span></td>
<td><span data-ttu-id="51e65-193">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-193">No</span></span></td>
<td><span data-ttu-id="51e65-194">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-194">No</span></span></td>
<td><span data-ttu-id="51e65-195">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-195">No</span></span></td>
<td><span data-ttu-id="51e65-196">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-196">No</span></span></td>
<td><span data-ttu-id="51e65-197">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51e65-198">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="51e65-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="51e65-199">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="51e65-199">Not planned</span></span></li>
<li><span data-ttu-id="51e65-200">Przygotowane</span><span class="sxs-lookup"><span data-stu-id="51e65-200">Prepared</span></span></li>
<li><span data-ttu-id="51e65-201">W toku</span><span class="sxs-lookup"><span data-stu-id="51e65-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="51e65-202">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-202">No</span></span></td>
<td><span data-ttu-id="51e65-203">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-203">No</span></span></td>
<td><span data-ttu-id="51e65-204">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-204">No</span></span></td>
<td><span data-ttu-id="51e65-205">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-205">No</span></span></td>
<td><span data-ttu-id="51e65-206">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-206">No</span></span></td>
<td><span data-ttu-id="51e65-207">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="51e65-208">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="51e65-208">Process</span></span></td>
<td><span data-ttu-id="51e65-209">Ukończono</span><span class="sxs-lookup"><span data-stu-id="51e65-209">Completed</span></span></td>
<td><span data-ttu-id="51e65-210">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-210">No</span></span></td>
<td><span data-ttu-id="51e65-211">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-211">No</span></span></td>
<td><span data-ttu-id="51e65-212">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-212">No</span></span></td>
<td><span data-ttu-id="51e65-213">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-213">No</span></span></td>
<td><span data-ttu-id="51e65-214">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-214">No</span></span></td>
<td><span data-ttu-id="51e65-215">Nie</span><span class="sxs-lookup"><span data-stu-id="51e65-215">No</span></span></td>
</tr>
</tbody>
</table>






