---
title: Obsługa tablicy Kanban przeniesienia dla skanerów kodów kreskowych
description: Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e63a33af63144b78d0c375022b9802e11c255598
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "319461"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="a5b22-103">Obsługa tablicy Kanban przeniesienia dla skanerów kodów kreskowych</span><span class="sxs-lookup"><span data-stu-id="a5b22-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5b22-104">Tablica Kanban przeniesienia obsługuje wprowadzanie ze skanera przy użyciu widżetu skanera kodów kreskowych, który obsługuje funkcje wybierania, rozpoczynania, kończenia i opróżniania zadań Kanban.</span><span class="sxs-lookup"><span data-stu-id="a5b22-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="a5b22-105">Tryby rejestracji</span><span class="sxs-lookup"><span data-stu-id="a5b22-105">Registration modes</span></span>
------------------

<span data-ttu-id="a5b22-106">Na skróconej karcie **Rejestracja skanera** można wybrać tryb rejestracji kontrolujący działanie, podczas którego użytkownik skanuje numer karty Kanban lub ręcznie wpisuje numer w polu Numer karty Kanban.</span><span class="sxs-lookup"><span data-stu-id="a5b22-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="a5b22-107">Ustaw tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="a5b22-107">Set registration mode</span></span> | <span data-ttu-id="a5b22-108">Opis</span><span class="sxs-lookup"><span data-stu-id="a5b22-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a5b22-109">Uruchom</span><span class="sxs-lookup"><span data-stu-id="a5b22-109">Start</span></span>                 | <span data-ttu-id="a5b22-110">Rejestruje zadanie przeniesienia w systemie Kanban jako zadania w toku.</span><span class="sxs-lookup"><span data-stu-id="a5b22-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="a5b22-111">Zakończono</span><span class="sxs-lookup"><span data-stu-id="a5b22-111">Complete</span></span>              | <span data-ttu-id="a5b22-112">Rejestruje zadanie przeniesienia w systemie Kanban jako zakończonego.</span><span class="sxs-lookup"><span data-stu-id="a5b22-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="a5b22-113">Puste</span><span class="sxs-lookup"><span data-stu-id="a5b22-113">Empty</span></span>                 | <span data-ttu-id="a5b22-114">Rejestruje magazynową jednostkę obsługi materiału, do której odwołuje się karta Kanban, jako pustą</span><span class="sxs-lookup"><span data-stu-id="a5b22-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="a5b22-115">Wybierz</span><span class="sxs-lookup"><span data-stu-id="a5b22-115">Select</span></span>                | <span data-ttu-id="a5b22-116">Rejestruje numer karty Kanban i automatyczne wybiera z listy zadań w systemie Kanban to zadanie, do którego odwołuje się ta karta</span><span class="sxs-lookup"><span data-stu-id="a5b22-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<span data-ttu-id="a5b22-117">Wybierz tryb rejestracji</span><span class="sxs-lookup"><span data-stu-id="a5b22-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="a5b22-118">Gdy użyjesz czytnika kodów kreskowych do wybrania zadania, tryb wyświetlania na tablicy Kanban zmieni się.</span><span class="sxs-lookup"><span data-stu-id="a5b22-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span><span data-ttu-id="a5b22-119"> W tym trybie mają zastosowanie następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="a5b22-119"> In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="a5b22-120">Wyświetlane są tylko zeskanowane zadania Kanban.</span><span class="sxs-lookup"><span data-stu-id="a5b22-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="a5b22-121">Szczegóły wybranego zadania są wyświetlane w na skróconej karcie **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="a5b22-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="a5b22-122">Skrócona karta **Wiadomości** wyświetla komunikaty tylko dla wybranego zadania.</span><span class="sxs-lookup"><span data-stu-id="a5b22-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="a5b22-123">Stan zadania można zmienić za pomocą funkcji, które są dostępne w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="a5b22-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="a5b22-124">Tablica Kanban przeniesienia jest nadal wyświetlana w jednym zadaniu w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="a5b22-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="a5b22-125">Informacje na liście zadań można aktualizować ręcznie przez kliknięcie przycisku **Odśwież** (Shift + F5) w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="a5b22-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="a5b22-126">Po odświeżeniu informacji pełne wyniki filtru zadania są wyświetlane ponownie.</span><span class="sxs-lookup"><span data-stu-id="a5b22-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="a5b22-127">Stan i możliwe akcje zadania</span><span class="sxs-lookup"><span data-stu-id="a5b22-127">Job status and possible actions</span></span>
<span data-ttu-id="a5b22-128">Stan wybranego zadania oraz stan wszelkich niezaplanowanych zadań dla w dla kart Kanban zdarzenia, określają, czy zadanie może być dalej przetwarzane.</span><span class="sxs-lookup"><span data-stu-id="a5b22-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="a5b22-129">Poniższa tabela pokazuje informacje dotyczące tych stanów i zadań:</span><span class="sxs-lookup"><span data-stu-id="a5b22-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="a5b22-130">Stany, które są dostępne dla zadań lub dla jednostek załadunkowych, do których odwołują się zadania.</span><span class="sxs-lookup"><span data-stu-id="a5b22-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="a5b22-131">Każde zadanie, które można wykonać dla zadania.</span><span class="sxs-lookup"><span data-stu-id="a5b22-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="a5b22-132">Typ zadania</span><span class="sxs-lookup"><span data-stu-id="a5b22-132">Job type</span></span></th>
<th><span data-ttu-id="a5b22-133">Stan zadania lub stan jednostki załadunkowej</span><span class="sxs-lookup"><span data-stu-id="a5b22-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="a5b22-134">Aktualizuj listę pobrania</span><span class="sxs-lookup"><span data-stu-id="a5b22-134">Update picking list</span></span></th>
<th><span data-ttu-id="a5b22-135">Uruchom</span><span class="sxs-lookup"><span data-stu-id="a5b22-135">Start</span></span></th>
<th><span data-ttu-id="a5b22-136">Aktualizuj rejestrację</span><span class="sxs-lookup"><span data-stu-id="a5b22-136">Update registration</span></span></th>
<th><span data-ttu-id="a5b22-137">Zakończono</span><span class="sxs-lookup"><span data-stu-id="a5b22-137">Complete</span></span></th>
<th><span data-ttu-id="a5b22-138">Puste</span><span class="sxs-lookup"><span data-stu-id="a5b22-138">Empty</span></span></th>
<th><span data-ttu-id="a5b22-139">Utwórz zdarzenia Kanban</span><span class="sxs-lookup"><span data-stu-id="a5b22-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a5b22-140">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a5b22-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="a5b22-141">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="a5b22-141">Not planned</span></span></li>
<li><span data-ttu-id="a5b22-142">Brak ustalonych zadań lub żadne ustalone zadanie nie ma stanu Zakończono</span><span class="sxs-lookup"><span data-stu-id="a5b22-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="a5b22-143">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-143">Yes</span></span></td>
<td><span data-ttu-id="a5b22-144">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-144">Yes</span></span></td>
<td><span data-ttu-id="a5b22-145">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-145">Yes</span></span></td>
<td><span data-ttu-id="a5b22-146">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-146">Yes</span></span></td>
<td><span data-ttu-id="a5b22-147">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-147">No</span></span></td>
<td><span data-ttu-id="a5b22-148">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a5b22-149">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a5b22-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="a5b22-150">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="a5b22-150">Not planned</span></span></li>
<li><span data-ttu-id="a5b22-151">Ustalone zadanie nie ma stanu Zakończone</span><span class="sxs-lookup"><span data-stu-id="a5b22-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="a5b22-152">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-152">Yes</span></span></td>
<td><span data-ttu-id="a5b22-153">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-153">No</span></span></td>
<td><span data-ttu-id="a5b22-154">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-154">Yes</span></span></td>
<td><span data-ttu-id="a5b22-155">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-155">No</span></span></td>
<td><span data-ttu-id="a5b22-156">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-156">No</span></span></td>
<td><span data-ttu-id="a5b22-157">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a5b22-158">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a5b22-158">Transfer</span></span></td>
<td><span data-ttu-id="a5b22-159">W toku</span><span class="sxs-lookup"><span data-stu-id="a5b22-159">In progress</span></span></td>
<td><span data-ttu-id="a5b22-160">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-160">Yes</span></span></td>
<td><span data-ttu-id="a5b22-161">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-161">No</span></span></td>
<td><span data-ttu-id="a5b22-162">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-162">Yes</span></span></td>
<td><span data-ttu-id="a5b22-163">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-163">Yes</span></span></td>
<td><span data-ttu-id="a5b22-164">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-164">No</span></span></td>
<td><span data-ttu-id="a5b22-165">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a5b22-166">Przenieś</span><span class="sxs-lookup"><span data-stu-id="a5b22-166">Transfer</span></span></td>
<td><span data-ttu-id="a5b22-167">Ukończono</span><span class="sxs-lookup"><span data-stu-id="a5b22-167">Completed</span></span></td>
<td><span data-ttu-id="a5b22-168">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-168">No</span></span></td>
<td><span data-ttu-id="a5b22-169">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-169">No</span></span></td>
<td><span data-ttu-id="a5b22-170">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-170">No</span></span></td>
<td><span data-ttu-id="a5b22-171">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-171">No</span></span></td>
<td><span data-ttu-id="a5b22-172">Tak</span><span class="sxs-lookup"><span data-stu-id="a5b22-172">Yes</span></span></td>
<td><span data-ttu-id="a5b22-173">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a5b22-174">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="a5b22-174">Transfer or process</span></span></td>
<td><span data-ttu-id="a5b22-175">Puste</span><span class="sxs-lookup"><span data-stu-id="a5b22-175">Empty</span></span></td>
<td><span data-ttu-id="a5b22-176">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-176">No</span></span></td>
<td><span data-ttu-id="a5b22-177">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-177">No</span></span></td>
<td><span data-ttu-id="a5b22-178">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-178">No</span></span></td>
<td><span data-ttu-id="a5b22-179">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-179">No</span></span></td>
<td><span data-ttu-id="a5b22-180">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-180">No</span></span></td>
<td><span data-ttu-id="a5b22-181">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a5b22-182">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="a5b22-182">Transfer or process</span></span></td>
<td><span data-ttu-id="a5b22-183">Nie znaleziono karty Kanban</span><span class="sxs-lookup"><span data-stu-id="a5b22-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="a5b22-184">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-184">No</span></span></td>
<td><span data-ttu-id="a5b22-185">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-185">No</span></span></td>
<td><span data-ttu-id="a5b22-186">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-186">No</span></span></td>
<td><span data-ttu-id="a5b22-187">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-187">No</span></span></td>
<td><span data-ttu-id="a5b22-188">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-188">No</span></span></td>
<td><span data-ttu-id="a5b22-189">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a5b22-190">Przeniesienie lub proces</span><span class="sxs-lookup"><span data-stu-id="a5b22-190">Transfer or process</span></span></td>
<td><span data-ttu-id="a5b22-191">Znaleziono kartę Kanban, ale nie jest ona przypisana do zadania Kanban</span><span class="sxs-lookup"><span data-stu-id="a5b22-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="a5b22-192">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-192">No</span></span></td>
<td><span data-ttu-id="a5b22-193">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-193">No</span></span></td>
<td><span data-ttu-id="a5b22-194">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-194">No</span></span></td>
<td><span data-ttu-id="a5b22-195">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-195">No</span></span></td>
<td><span data-ttu-id="a5b22-196">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-196">No</span></span></td>
<td><span data-ttu-id="a5b22-197">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a5b22-198">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="a5b22-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="a5b22-199">Niezaplanowane</span><span class="sxs-lookup"><span data-stu-id="a5b22-199">Not planned</span></span></li>
<li><span data-ttu-id="a5b22-200">Przygotowane</span><span class="sxs-lookup"><span data-stu-id="a5b22-200">Prepared</span></span></li>
<li><span data-ttu-id="a5b22-201">W toku</span><span class="sxs-lookup"><span data-stu-id="a5b22-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="a5b22-202">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-202">No</span></span></td>
<td><span data-ttu-id="a5b22-203">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-203">No</span></span></td>
<td><span data-ttu-id="a5b22-204">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-204">No</span></span></td>
<td><span data-ttu-id="a5b22-205">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-205">No</span></span></td>
<td><span data-ttu-id="a5b22-206">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-206">No</span></span></td>
<td><span data-ttu-id="a5b22-207">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a5b22-208">Przetwórz</span><span class="sxs-lookup"><span data-stu-id="a5b22-208">Process</span></span></td>
<td><span data-ttu-id="a5b22-209">Ukończono</span><span class="sxs-lookup"><span data-stu-id="a5b22-209">Completed</span></span></td>
<td><span data-ttu-id="a5b22-210">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-210">No</span></span></td>
<td><span data-ttu-id="a5b22-211">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-211">No</span></span></td>
<td><span data-ttu-id="a5b22-212">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-212">No</span></span></td>
<td><span data-ttu-id="a5b22-213">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-213">No</span></span></td>
<td><span data-ttu-id="a5b22-214">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-214">No</span></span></td>
<td><span data-ttu-id="a5b22-215">Nie</span><span class="sxs-lookup"><span data-stu-id="a5b22-215">No</span></span></td>
</tr>
</tbody>
</table>





