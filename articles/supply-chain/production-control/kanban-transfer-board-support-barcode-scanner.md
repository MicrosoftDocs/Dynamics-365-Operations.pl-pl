---
title: Obsługa tablicy Kanban przeniesienia dla skanerów kodów kreskowych
description: Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a7073fb5d77e2d11569e86b92433864371f0e1d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825874"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="a8082-103">Obsługa tablicy Kanban przeniesienia dla skanerów kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="a8082-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8082-104">Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="a8082-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="a8082-105">Tryby rejestracji</span><span class="sxs-lookup"><span data-stu-id="a8082-105">Registration modes</span></span>
------------------

<span data-ttu-id="a8082-106">Na skróconej karcie **Rejestracja skanera** można wybrać tryb rejestracji kontrolujący działanie, podczas którego użytkownik skanuje numer karty Kanban lub ręcznie wpisuje numer w polu Numer karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="a8082-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="a8082-107">Ustaw tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="a8082-107">Set registration mode</span></span> | <span data-ttu-id="a8082-108">Opis</span><span class="sxs-lookup"><span data-stu-id="a8082-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a8082-109">Uruchom</span><span class="sxs-lookup"><span data-stu-id="a8082-109">Start</span></span>                 | <span data-ttu-id="a8082-110">Rejestruje zadanie przeniesienia w systemie Kanban jako zadania w toku.</span><span class="sxs-lookup"><span data-stu-id="a8082-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="a8082-111">Zakończono</span><span class="sxs-lookup"><span data-stu-id="a8082-111">Complete</span></span>              | <span data-ttu-id="a8082-112">Rejestruje zadanie przeniesienia w systemie Kanban jako zakończonego.</span><span class="sxs-lookup"><span data-stu-id="a8082-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="a8082-113">Puste</span><span class="sxs-lookup"><span data-stu-id="a8082-113">Empty</span></span>                 | <span data-ttu-id="a8082-114">Rejestruje magazynową jednostkę obsługi materiału, do której odwołuje się karta Kanban, jako pustą</span><span class="sxs-lookup"><span data-stu-id="a8082-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="a8082-115">Wybierz</span><span class="sxs-lookup"><span data-stu-id="a8082-115">Select</span></span>                | <span data-ttu-id="a8082-116">Rejestruje numer karty Kanban i automatyczne wybiera z listy zadań w systemie Kanban to zadanie, do którego odwołuje się ta karta</span><span class="sxs-lookup"><span data-stu-id="a8082-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="a8082-117">Wybierz tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="a8082-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="a8082-118">Gdy użyjesz czytnika kodów kreskowych do wybrania zadania, tryb wyświetlania na tablicy Kanban zmieni się.</span><span class="sxs-lookup"><span data-stu-id="a8082-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="a8082-119">W tym trybie mają zastosowanie następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="a8082-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="a8082-120">Wyświetlane są tylko zeskanowane zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="a8082-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="a8082-121">Szczegóły wybranego zadania są wyświetlane w na skróconej karcie **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="a8082-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="a8082-122">Skrócona karta **Wiadomości** wyświetla komunikaty tylko dla wybranego zadania.</span><span class="sxs-lookup"><span data-stu-id="a8082-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="a8082-123">Stan zadania można zmienić za pomocą funkcji, które są dostępne w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="a8082-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="a8082-124">Tablica Kanban przeniesienia jest nadal wyświetlana w jednym zadaniu w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="a8082-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="a8082-125">Informacje na liście zadań można aktualizować ręcznie przez kliknięcie przycisku **Odśwież** (Shift + F5) w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="a8082-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="a8082-126">Po odświeżeniu informacji pełne wyniki filtru zadania są wyświetlane ponownie.</span><span class="sxs-lookup"><span data-stu-id="a8082-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="a8082-127">Stan i możliwe akcje zadania</span><span class="sxs-lookup"><span data-stu-id="a8082-127">Job status and possible actions</span></span>
<span data-ttu-id="a8082-128">Stan wybranego zadania oraz stan wszelkich niezaplanowanych zadań dla w dla kart Kanban zdarzenia, określają, czy zadanie może być dalej przetwarzane.</span><span class="sxs-lookup"><span data-stu-id="a8082-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="a8082-129">Poniższa tabela pokazuje informacje dotyczące tych stanów i zadań:</span><span class="sxs-lookup"><span data-stu-id="a8082-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="a8082-130">Stany, które są dostępne dla zadań lub dla jednostek załadunkowych, do których odwołują się zadania.</span><span class="sxs-lookup"><span data-stu-id="a8082-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="a8082-131">Każde zadanie, które można wykonać dla zadania.</span><span class="sxs-lookup"><span data-stu-id="a8082-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="a8082-132">Typ zadania</span><span class="sxs-lookup"><span data-stu-id="a8082-132">Job type</span></span></th>
<th><span data-ttu-id="a8082-133">Stan zadania lub stan jednostki załadunkowej</span><span class="sxs-lookup"><span data-stu-id="a8082-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="a8082-134">Aktualizuj listę pobrania</span><span class="sxs-lookup"><span data-stu-id="a8082-134">Update picking list</span></span></th>
<th><span data-ttu-id="a8082-135">Uruchom</span><span class="sxs-lookup"><span data-stu-id="a8082-135">Start</span></span></th>
<th><span data-ttu-id="a8082-136">Aktualizuj rejestrację</span><span class="sxs-lookup"><span data-stu-id="a8082-136">Update registration</span></span></th>
<th><span data-ttu-id="a8082-137">Zakończono</span><span class="sxs-lookup"><span data-stu-id="a8082-137">Complete</span></span></th>
<th><span data-ttu-id="a8082-138">Puste</span><span class="sxs-lookup"><span data-stu-id="a8082-138">Empty</span></span></th>
<th><span data-ttu-id="a8082-139">Utwórz zdarzenia Kanban</span><span class="sxs-lookup"><span data-stu-id="a8082-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8082-140">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a8082-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="a8082-141">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="a8082-141">Not planned</span></span></li>
<li><span data-ttu-id="a8082-142">Brak ustalonych zadań lub żadne ustalone zadanie nie ma stanu Zakończono</span><span class="sxs-lookup"><span data-stu-id="a8082-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="a8082-143">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-143">Yes</span></span></td>
<td><span data-ttu-id="a8082-144">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-144">Yes</span></span></td>
<td><span data-ttu-id="a8082-145">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-145">Yes</span></span></td>
<td><span data-ttu-id="a8082-146">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-146">Yes</span></span></td>
<td><span data-ttu-id="a8082-147">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-147">No</span></span></td>
<td><span data-ttu-id="a8082-148">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8082-149">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a8082-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="a8082-150">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="a8082-150">Not planned</span></span></li>
<li><span data-ttu-id="a8082-151">Ustalone zadanie nie ma stanu Zakończone</span><span class="sxs-lookup"><span data-stu-id="a8082-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="a8082-152">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-152">Yes</span></span></td>
<td><span data-ttu-id="a8082-153">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-153">No</span></span></td>
<td><span data-ttu-id="a8082-154">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-154">Yes</span></span></td>
<td><span data-ttu-id="a8082-155">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-155">No</span></span></td>
<td><span data-ttu-id="a8082-156">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-156">No</span></span></td>
<td><span data-ttu-id="a8082-157">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8082-158">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a8082-158">Transfer</span></span></td>
<td><span data-ttu-id="a8082-159">W toku</span><span class="sxs-lookup"><span data-stu-id="a8082-159">In progress</span></span></td>
<td><span data-ttu-id="a8082-160">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-160">Yes</span></span></td>
<td><span data-ttu-id="a8082-161">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-161">No</span></span></td>
<td><span data-ttu-id="a8082-162">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-162">Yes</span></span></td>
<td><span data-ttu-id="a8082-163">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-163">Yes</span></span></td>
<td><span data-ttu-id="a8082-164">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-164">No</span></span></td>
<td><span data-ttu-id="a8082-165">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8082-166">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a8082-166">Transfer</span></span></td>
<td><span data-ttu-id="a8082-167">Ukończono</span><span class="sxs-lookup"><span data-stu-id="a8082-167">Completed</span></span></td>
<td><span data-ttu-id="a8082-168">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-168">No</span></span></td>
<td><span data-ttu-id="a8082-169">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-169">No</span></span></td>
<td><span data-ttu-id="a8082-170">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-170">No</span></span></td>
<td><span data-ttu-id="a8082-171">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-171">No</span></span></td>
<td><span data-ttu-id="a8082-172">Tak</span><span class="sxs-lookup"><span data-stu-id="a8082-172">Yes</span></span></td>
<td><span data-ttu-id="a8082-173">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8082-174">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="a8082-174">Transfer or process</span></span></td>
<td><span data-ttu-id="a8082-175">Puste</span><span class="sxs-lookup"><span data-stu-id="a8082-175">Empty</span></span></td>
<td><span data-ttu-id="a8082-176">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-176">No</span></span></td>
<td><span data-ttu-id="a8082-177">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-177">No</span></span></td>
<td><span data-ttu-id="a8082-178">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-178">No</span></span></td>
<td><span data-ttu-id="a8082-179">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-179">No</span></span></td>
<td><span data-ttu-id="a8082-180">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-180">No</span></span></td>
<td><span data-ttu-id="a8082-181">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8082-182">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="a8082-182">Transfer or process</span></span></td>
<td><span data-ttu-id="a8082-183">Nie znaleziono karty Kanban</span><span class="sxs-lookup"><span data-stu-id="a8082-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="a8082-184">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-184">No</span></span></td>
<td><span data-ttu-id="a8082-185">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-185">No</span></span></td>
<td><span data-ttu-id="a8082-186">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-186">No</span></span></td>
<td><span data-ttu-id="a8082-187">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-187">No</span></span></td>
<td><span data-ttu-id="a8082-188">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-188">No</span></span></td>
<td><span data-ttu-id="a8082-189">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8082-190">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="a8082-190">Transfer or process</span></span></td>
<td><span data-ttu-id="a8082-191">Znaleziono kartę Kanban, ale nie jest ona przypisana do zadania Kanban</span><span class="sxs-lookup"><span data-stu-id="a8082-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="a8082-192">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-192">No</span></span></td>
<td><span data-ttu-id="a8082-193">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-193">No</span></span></td>
<td><span data-ttu-id="a8082-194">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-194">No</span></span></td>
<td><span data-ttu-id="a8082-195">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-195">No</span></span></td>
<td><span data-ttu-id="a8082-196">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-196">No</span></span></td>
<td><span data-ttu-id="a8082-197">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8082-198">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="a8082-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="a8082-199">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="a8082-199">Not planned</span></span></li>
<li><span data-ttu-id="a8082-200">Przygotowane</span><span class="sxs-lookup"><span data-stu-id="a8082-200">Prepared</span></span></li>
<li><span data-ttu-id="a8082-201">W toku</span><span class="sxs-lookup"><span data-stu-id="a8082-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="a8082-202">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-202">No</span></span></td>
<td><span data-ttu-id="a8082-203">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-203">No</span></span></td>
<td><span data-ttu-id="a8082-204">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-204">No</span></span></td>
<td><span data-ttu-id="a8082-205">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-205">No</span></span></td>
<td><span data-ttu-id="a8082-206">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-206">No</span></span></td>
<td><span data-ttu-id="a8082-207">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8082-208">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="a8082-208">Process</span></span></td>
<td><span data-ttu-id="a8082-209">Ukończono</span><span class="sxs-lookup"><span data-stu-id="a8082-209">Completed</span></span></td>
<td><span data-ttu-id="a8082-210">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-210">No</span></span></td>
<td><span data-ttu-id="a8082-211">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-211">No</span></span></td>
<td><span data-ttu-id="a8082-212">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-212">No</span></span></td>
<td><span data-ttu-id="a8082-213">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-213">No</span></span></td>
<td><span data-ttu-id="a8082-214">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-214">No</span></span></td>
<td><span data-ttu-id="a8082-215">Nie</span><span class="sxs-lookup"><span data-stu-id="a8082-215">No</span></span></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]