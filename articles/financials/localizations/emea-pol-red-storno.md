---
title: Aktywowanie stornowania dla Polski
description: Ten temat zawiera informacje o funkcji stornowania dla Polski.
author: ShylaThompson
manager: AnnBe
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Poland
ms.author: shylaw
ms.dyn365.ops.version: AX 7.0.1
ms.search.validFrom: 2016-05-31
ms.openlocfilehash: 465d4b5330309462d4b72fc1a387f584a1ac81bd
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "371469"
---
# <a name="activate-storno-accounting"></a><span data-ttu-id="c4ae6-103">Aktywowanie stornowania</span><span class="sxs-lookup"><span data-stu-id="c4ae6-103">Activate storno accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4ae6-104">Niniejsze procedury służą do konfigurowania operacji stornowania w Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-104">Use these procedures to set up storno accounting in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="c4ae6-105">Stornowanie polega na zmianie znaku kwot w celu wycofania błędnych oryginalnych transakcji.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-105">In storno accounting, you reverse the sign on amounts to reverse incorrect original transactions.</span></span> <span data-ttu-id="c4ae6-106">Na przykład następujące transakcje są zarejestrowane niepoprawnie.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-106">For example, the following transactions are incorrectly recorded.</span></span>

|<span data-ttu-id="c4ae6-107">opis</span><span class="sxs-lookup"><span data-stu-id="c4ae6-107">Description</span></span>        | <span data-ttu-id="c4ae6-108">Strona debetowa</span><span class="sxs-lookup"><span data-stu-id="c4ae6-108">Debit</span></span> |<span data-ttu-id="c4ae6-109">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="c4ae6-109">Credit</span></span>  |
|-------------------|-------|--------|
|<span data-ttu-id="c4ae6-110">Przychód ze sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c4ae6-110">Sales revenue</span></span>      |       |<span data-ttu-id="c4ae6-111">100,00</span><span class="sxs-lookup"><span data-stu-id="c4ae6-111">100.00</span></span>  |
|<span data-ttu-id="c4ae6-112">Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="c4ae6-112">Accounts receivable</span></span>|<span data-ttu-id="c4ae6-113">100,00</span><span class="sxs-lookup"><span data-stu-id="c4ae6-113">100.00</span></span> |        |

<span data-ttu-id="c4ae6-114">Aby wycofać transakcje i księgować transakcje wycofywania jako transakcje storno, należy wprowadzić następujące informacje.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-114">To reverse the transactions and post the reversing transactions as storno transactions, you enter the following information.</span></span>

|<span data-ttu-id="c4ae6-115">opis</span><span class="sxs-lookup"><span data-stu-id="c4ae6-115">Description</span></span>        | <span data-ttu-id="c4ae6-116">Strona debetowa</span><span class="sxs-lookup"><span data-stu-id="c4ae6-116">Debit</span></span>  |<span data-ttu-id="c4ae6-117">Strona kredytowa</span><span class="sxs-lookup"><span data-stu-id="c4ae6-117">Credit</span></span>   |
|-------------------|--------|---------|
|<span data-ttu-id="c4ae6-118">Przychód ze sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c4ae6-118">Sales revenue</span></span>      |        |<span data-ttu-id="c4ae6-119">-100,00</span><span class="sxs-lookup"><span data-stu-id="c4ae6-119">-100.00</span></span>  |
|<span data-ttu-id="c4ae6-120">Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="c4ae6-120">Accounts receivable</span></span>|<span data-ttu-id="c4ae6-121">-100,00</span><span class="sxs-lookup"><span data-stu-id="c4ae6-121">-100.00</span></span> |         |

<span data-ttu-id="c4ae6-122">Każda transakcja wycofywania pojawia się w tej samej kolumnie debetowej lub kredytowej co oryginalna transakcja.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-122">Each reversing transaction appears in the same debit or credit column as the original transaction.</span></span> <span data-ttu-id="c4ae6-123">Zachowanie kwot w oryginalnych kolumnach i zmiana znaku kwot powoduje skuteczne „wyzerowanie” oryginalnej transakcji.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-123">By keeping amounts in their original columns and reversing the sign on the amounts, you effectively “zero out” the original transaction.</span></span>

<span data-ttu-id="c4ae6-124">Po wykonaniu poniższej procedury zostanie utworzona transakcja, która automatycznie wycofuje (stornuje) transakcje.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-124">After you complete the following procedure, a transaction is created that automatically reverses storno transactions.</span></span>

## <a name="activate-storno-accounting"></a><span data-ttu-id="c4ae6-125">Uaktywnienie stornowania</span><span class="sxs-lookup"><span data-stu-id="c4ae6-125">Activate storno accounting</span></span>
<span data-ttu-id="c4ae6-126">Należy aktywować stornowanie w module Księga główna, zanim będzie możliwe konfigurowanie parametrów stornowania w dowolnym innym module.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-126">You must activate storno accounting in General ledger before you can set up storno parameters in any other module.</span></span>

1. <span data-ttu-id="c4ae6-127">Kliknij kolejno opcje **Księga główna** > **Ustawienia** > **Parametry księgi głównej**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-127">Click **General ledger** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="c4ae6-128">W obszarze **Księga** na skróconej karcie **Reguły księgowania** w grupie pól **Wycofanie transakcji** ustaw opcję **Korekta** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-128">In the **Ledger** area, on the **Accounting rules** FastTab, in the **Transaction reversal** field group, set the **Correction** option to **Yes**.</span></span>

## <a name="set-up-storno-accounting"></a><span data-ttu-id="c4ae6-129">Konfigurowanie stornowania</span><span class="sxs-lookup"><span data-stu-id="c4ae6-129">Set up storno accounting</span></span>
<span data-ttu-id="c4ae6-130">Po aktywowaniu stornowania można skonfigurować parametry w modułach aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-130">After you activate storno accounting, you can set up parameters in the application modules.</span></span> <span data-ttu-id="c4ae6-131">Parametry specyficzne dla modułu zazwyczaj używają stornowania domyślnie dla różnych procesów w module.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-131">The parameters that are specific to a module typically use storno accounting by default for various processes in the module.</span></span> <span data-ttu-id="c4ae6-132">Można zmieniać domyślne ustawienie wyświetlane na stronie.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-132">You can change the default setting when it appears on a page.</span></span> <span data-ttu-id="c4ae6-133">Jednak ustawienie nie jest widoczne na wszystkich stronach.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-133">However, the setting does not appear on all pages.</span></span> <span data-ttu-id="c4ae6-134">Niektóre strony zawsze używają wartości domyślnej podczas przetwarzania i nie można zmienić tego ustawienia.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-134">Some pages always use the default setting during processing, and you cannot change the setting.</span></span>

### <a name="set-up-storno-accounting-in-accounts-payable"></a><span data-ttu-id="c4ae6-135">Ustawianie stornowania w module Rozrachunki z dostawcami</span><span class="sxs-lookup"><span data-stu-id="c4ae6-135">Set up storno accounting in Accounts payable</span></span>
<span data-ttu-id="c4ae6-136">Na stronie **Parametry modułu rozrachunków z dostawcami** w obszarze **Faktura** w opcji **Faktura korygująca z czerwonym stornem** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-136">On the  **Accounts payable parameters** page, in the **Invoice** area, set the **Credit note as correction** option to **Yes**.</span></span> <span data-ttu-id="c4ae6-137">Domyślnie faktury korygujące teraz są księgowane jako transakcje stornowania.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-137">By default, credit notes are now posted as storno transactions.</span></span>

### <a name="set-up-storno-accounting-in-accounts-receivable"></a><span data-ttu-id="c4ae6-138">Ustawianie stornowania w module Rozrachunki z odbiorcami</span><span class="sxs-lookup"><span data-stu-id="c4ae6-138">Set up storno accounting in Accounts receivable</span></span>
1. <span data-ttu-id="c4ae6-139">Przejdź do strony **Parametry modułu rozrachunków z odbiorcami**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-139">Go to the **Accounts receivable parameters** page.</span></span>
2. <span data-ttu-id="c4ae6-140">W obszarze **Aktualizacje** w grupie pól **Faktura zaliczkowa** w opcji **Faktura korygująca z czerwonym stornem** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-140">In the **Updates** area, in the **Advance invoice** field group, set the **Credit note as correction** option to **Yes**.</span></span> <span data-ttu-id="c4ae6-141">Domyślni, faktury korygujące dla faktur zaliczkowych są teraz księgowane jako transakcje stornowania.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-141">By default, credit notes for advance invoices are now posted as storno transactions.</span></span>
3. <span data-ttu-id="c4ae6-142">W opcji **Wycofanie jako korekta** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-142">Set the **Reversal as correction** option to **Yes**.</span></span> <span data-ttu-id="c4ae6-143">Domyślnie wycofania dla faktur korygujących są teraz księgowane jako transakcje stornowania.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-143">By default, reversals for advance invoices are now posted as storno transactions.</span></span>
4. <span data-ttu-id="c4ae6-144">W grupie pól **Faktura** w opcji **Faktura korygująca z czerwonym stornem** ustaw wartość to **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-144">In the **Invoice** field group, set the **Credit note as correction** option to **Yes**.</span></span> <span data-ttu-id="c4ae6-145">Domyślnie faktury korygujące dla faktur są teraz księgowane jako transakcje stornowania.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-145">By default, credit notes for invoices are now posted as storno transactions.</span></span>

### <a name="set-up-storno-accounting-in-inventory-and-warehouse-management"></a><span data-ttu-id="c4ae6-146">Ustawianie stornowania w module Zarządzanie zapasami i magazynem</span><span class="sxs-lookup"><span data-stu-id="c4ae6-146">Set up storno accounting in Inventory and warehouse management</span></span>
1. <span data-ttu-id="c4ae6-147">Przejdź do strony **Parametry modułu Zarządzanie zapasami i magazynem**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-147">Go to the **Inventory and warehouse management parameters** page.</span></span>
2. <span data-ttu-id="c4ae6-148">W obszarze **Ogólne** w grupie pól **Korekta** w opcji **Korekta zapasów — korekta** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-148">In the **General** area, in the **Correction** field group, set the **Inventory adjustment – correction** option to **Yes**.</span></span> <span data-ttu-id="c4ae6-149">Domyślnie korekty zapasów są teraz księgowane jako transakcje stornowania.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-149">By default, adjustments to inventory are now posted as storno transactions.</span></span>

### <a name="set-up-storno-accounting-in-project-management-and-accounting"></a><span data-ttu-id="c4ae6-150">Ustawianie stornowania w module Zarządzanie projektami i ich księgowanie</span><span class="sxs-lookup"><span data-stu-id="c4ae6-150">Set up storno accounting in Project management and accounting</span></span>
1. <span data-ttu-id="c4ae6-151">Przejdź do strony **Parametry modułu Zarządzanie projektami i ich księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-151">Go to the **Project management and accounting parameters** page.</span></span>
2. <span data-ttu-id="c4ae6-152">W obszarze **Ogólne** w grupie pól **Korekta** w opcji **Korekta transakcji projektów — korekta** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-152">In the **General** area, in the **Adjustment** field group, set the **Adjustment of project transactions – correction** option to  **Yes**.</span></span> <span data-ttu-id="c4ae6-153">Domyślnie korekty transakcji projektów są teraz księgowane jako transakcje stornowania.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-153">By default, adjustments to project transactions are now posted as storno transactions.</span></span>
3. <span data-ttu-id="c4ae6-154">W obszarze **Arkusze** w grupie pól **Księgowanie w księdze** w opcji **Transakcje ujemne — korekta** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-154">In the **Journals** area, in the **Ledger posting** field group, set the **Negative transactions – correction** option to **Yes**.</span></span> <span data-ttu-id="c4ae6-155">Domyślnie wpisy w arkuszu projektów zawierające ujemną kwotę kosztów są teraz księgowane jako transakcje stornowania.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-155">By default, project journal entries that have a negative cost amount are now posted as storno transactions.</span></span>

### <a name="create-an-invoice-storno-credit-note"></a><span data-ttu-id="c4ae6-156">Tworzenie faktury korygującej w celu wystornowania faktury</span><span class="sxs-lookup"><span data-stu-id="c4ae6-156">Create an Invoice storno credit note</span></span>   
 1. <span data-ttu-id="c4ae6-157">Dla potwierdzonego zamówienia zakupu w okienku akcji kliknij opcję **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-157">For a confirmed purchase order, on the Action Pane, click **Invoice**.</span></span>  
 2. <span data-ttu-id="c4ae6-158">Kliknij opcję **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-158">Click **Invoice**.</span></span>  
 3. <span data-ttu-id="c4ae6-159">W okienku akcji kliknij opcję **Domyślnie z: Ilość z dokumentu przyjęcia produktów**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-159">On the Action Pane, click **Default from: Product receipt quantity**.</span></span>  
 4. <span data-ttu-id="c4ae6-160">W polu **Domyślna ilość dla wierszy** zaznacz opcję.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-160">In the **Default quantity for lines** field, select an option.</span></span>  
 5. <span data-ttu-id="c4ae6-161">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-161">Click **OK**.</span></span>  
 6. <span data-ttu-id="c4ae6-162">W opcji **Korekta z czerwonym stornem** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-162">Set the **Credit correction** option to **Yes**.</span></span>  
 7. <span data-ttu-id="c4ae6-163">W polu **Numer** wpisz wartość.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-163">In the **Number** field, type a value.</span></span>  
 8. <span data-ttu-id="c4ae6-164">W polu **Data faktury** wprowadź datę.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-164">In the **Invoice date** field, enter a date.</span></span>  
 9. <span data-ttu-id="c4ae6-165">Kliknij przycisk **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="c4ae6-165">Click **Post**.</span></span>  

