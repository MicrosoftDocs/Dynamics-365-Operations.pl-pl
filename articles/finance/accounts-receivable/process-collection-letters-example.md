---
title: Przykład Przetwarzania ponagleń
description: W tym temacie pokazano przykład, który pokazuje proces tworzenia, drukowania i księgowania ponagleń.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021423"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="dab6b-103">Przykład Przetwarzania ponagleń</span><span class="sxs-lookup"><span data-stu-id="dab6b-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dab6b-104">W tym temacie pokazano przykład, który pokazuje proces tworzenia, drukowania i księgowania ponagleń.</span><span class="sxs-lookup"><span data-stu-id="dab6b-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="dab6b-105">Przykład bazuje na opcji **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia** w kredytach i windykacjach.</span><span class="sxs-lookup"><span data-stu-id="dab6b-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="dab6b-106">Używa danych w firmie demonstracyjnej USMF i nowym odbiorcy, US-045.</span><span class="sxs-lookup"><span data-stu-id="dab6b-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="dab6b-107">Aby rozpocząć, przejdź do **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**, wybierz opcję **Nowy**, a następnie wprowadź wymagane informacje, aby utworzyć odbiorcę US-045.</span><span class="sxs-lookup"><span data-stu-id="dab6b-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="dab6b-108">Po zakończeniu wykonaj poniższe czynności.</span><span class="sxs-lookup"><span data-stu-id="dab6b-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="dab6b-109">Przejdź do strony **Kredyt i windykacja \> Ponaglenie \> Ustaw kolejność ponagleń** i skonfiguruj kolejność ponagleń, jak pokazano w poniższej tabeli, która jest przypisana do profilu księgowania klienta.</span><span class="sxs-lookup"><span data-stu-id="dab6b-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="dab6b-110">Kod ponaglenia</span><span class="sxs-lookup"><span data-stu-id="dab6b-110">Collection   letter code</span></span>      |     <span data-ttu-id="dab6b-111">opis</span><span class="sxs-lookup"><span data-stu-id="dab6b-111">Description</span></span>                           |     <span data-ttu-id="dab6b-112">Waluta</span><span class="sxs-lookup"><span data-stu-id="dab6b-112">Currency</span></span>      |     <span data-ttu-id="dab6b-113">Konto główne</span><span class="sxs-lookup"><span data-stu-id="dab6b-113">Main   account</span></span>        |     <span data-ttu-id="dab6b-114">Opłata   w walucie</span><span class="sxs-lookup"><span data-stu-id="dab6b-114">Fee   in currency</span></span>     |     <span data-ttu-id="dab6b-115">Minimalna    nadwyżka</span><span class="sxs-lookup"><span data-stu-id="dab6b-115">Minimum   over</span></span>        |     <span data-ttu-id="dab6b-116">Blokuj    dni</span><span class="sxs-lookup"><span data-stu-id="dab6b-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="dab6b-117">Ponaglenie   1</span><span class="sxs-lookup"><span data-stu-id="dab6b-117">Collection   letter 1</span></span>         |     <span data-ttu-id="dab6b-118">Drugie    powiadomienie z opłatą</span><span class="sxs-lookup"><span data-stu-id="dab6b-118">Second   notification with fee</span></span>        |     <span data-ttu-id="dab6b-119">USD</span><span class="sxs-lookup"><span data-stu-id="dab6b-119">USD</span></span>           |                           |     <span data-ttu-id="dab6b-120">0,00</span><span class="sxs-lookup"><span data-stu-id="dab6b-120">0.00</span></span>                  |     <span data-ttu-id="dab6b-121">0,00</span><span class="sxs-lookup"><span data-stu-id="dab6b-121">0.00</span></span>                  |     <span data-ttu-id="dab6b-122">2</span><span class="sxs-lookup"><span data-stu-id="dab6b-122">2</span></span>                 |
|     <span data-ttu-id="dab6b-123">Ponaglenie   2</span><span class="sxs-lookup"><span data-stu-id="dab6b-123">Collection   letter 2</span></span>         |     <span data-ttu-id="dab6b-124">Drugie    powiadomienie z opłatą</span><span class="sxs-lookup"><span data-stu-id="dab6b-124">Second   notification with fee</span></span>        |     <span data-ttu-id="dab6b-125">Usc</span><span class="sxs-lookup"><span data-stu-id="dab6b-125">USC</span></span>           |     <span data-ttu-id="dab6b-126">403150</span><span class="sxs-lookup"><span data-stu-id="dab6b-126">403150</span></span>                |     <span data-ttu-id="dab6b-127">20.00</span><span class="sxs-lookup"><span data-stu-id="dab6b-127">20.00</span></span>                 |     <span data-ttu-id="dab6b-128">10,00</span><span class="sxs-lookup"><span data-stu-id="dab6b-128">10.00</span></span>                 |     <span data-ttu-id="dab6b-129">3</span><span class="sxs-lookup"><span data-stu-id="dab6b-129">3</span></span>                 |
|     <span data-ttu-id="dab6b-130">Ponaglenie</span><span class="sxs-lookup"><span data-stu-id="dab6b-130">Collection</span></span>                    |     <span data-ttu-id="dab6b-131">Ostatnie    powiadomienie z opłatą</span><span class="sxs-lookup"><span data-stu-id="dab6b-131">Final   notification with fee</span></span>         |     <span data-ttu-id="dab6b-132">USD</span><span class="sxs-lookup"><span data-stu-id="dab6b-132">USD</span></span>           |     <span data-ttu-id="dab6b-133">403150</span><span class="sxs-lookup"><span data-stu-id="dab6b-133">403150</span></span>                |     <span data-ttu-id="dab6b-134">50.00</span><span class="sxs-lookup"><span data-stu-id="dab6b-134">50.00</span></span>                 |     <span data-ttu-id="dab6b-135">100.00</span><span class="sxs-lookup"><span data-stu-id="dab6b-135">100.00</span></span>                |     <span data-ttu-id="dab6b-136">15</span><span class="sxs-lookup"><span data-stu-id="dab6b-136">15</span></span>                |

<span data-ttu-id="dab6b-137">Na poniższej ilustracji przedstawiono informacje zawarte w tabeli w sposób, w jakby był to widoczny na stronie **Ponaglenia**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="dab6b-138">[![Konfigurowanie kolejności ponagleń](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="dab6b-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="dab6b-139">Teraz trzeba ustawić dwa parametry, które są wymagane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="dab6b-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="dab6b-140">Przejdź do **Kredyty i windykacja \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dab6b-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-141">Na karcie **Windykacje** ustaw **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="dab6b-142">Upewnij się, że w polu **Utwórz ponaglenie dla każdego** jest ustawiona wartość **Odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="dab6b-143">[![Ustawianie parametrów rozrachunków z odbiorcami dla windykacji](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="dab6b-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="dab6b-144">Przejdź do **Rozrachunków z odbiorcami \> Faktury \> Wszystkie faktury bezpłatne**, wybierz opcję **Nowy**, a następnie wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="dab6b-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-145">W polu **Konto odbiorcy** zaznacz wartość **US-045**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="dab6b-146">W polu **Data faktury** wprowadź datę faktury **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="dab6b-147">W polu **Data ukończenia** wprowadź datę faktury **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="dab6b-148">Na skróconej karcie **Wiersze faktury** w polu **Konto główne** wprowadź wartość **401100**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="dab6b-149">W polu **Cena jednostkowa** wpisz **500.00**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="dab6b-150">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-150">Select **Post**.</span></span>

    <span data-ttu-id="dab6b-151">Teraz musisz wprowadzić dwie faktury koryguje dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="dab6b-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="dab6b-152">Wybierz opcję **Nowe**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dab6b-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-153">W polu **Konto odbiorcy** zaznacz wartość **US-045**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="dab6b-154">W polu **Data faktury** wprowadź datę faktury **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="dab6b-155">W polu **Data ukończenia** wprowadź datę faktury **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="dab6b-156">Na skróconej karcie **Wiersze faktury** w polu **Konto główne** wprowadź wartość **401100**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="dab6b-157">W polu **Cena jednostkowa** wpisz **-100.00**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="dab6b-158">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-158">Select **Post**.</span></span>

5. <span data-ttu-id="dab6b-159">Powtórz krok 4, ale wprowadź wartość **-200,00** w polu **Cena jednostkowa**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="dab6b-160">Przejdź do **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy** i wybierz odbiorcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="dab6b-161">Następnie w okienku akcji wybierz opcję **Transakcje \> Transakcje**, aby przejrzeć wcześniej zaksięgowane transakcje odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="dab6b-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="dab6b-162">[![Przeglądanie zaksięgowanych transakcji odbiorcy](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="dab6b-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="dab6b-163">Musisz teraz utworzyć ponaglenia dla klienta US-045.</span><span class="sxs-lookup"><span data-stu-id="dab6b-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="dab6b-164">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dab6b-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-165">Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="dab6b-166">Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="dab6b-167">W polu **Data ponaglenia** wprowadź datę faktury **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="dab6b-168">W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="dab6b-169">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-169">Select **OK**.</span></span>
    5. <span data-ttu-id="dab6b-170">Wybierz **OK**, aby utworzyć ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="dab6b-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="dab6b-171">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dab6b-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-172">Należy zauważyć, że kod ponaglenia w nagłówku i wierszach transakcji to **Ponaglenie 1**, ponieważ to ponaglenie jest pierwszym ponagleniu w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="dab6b-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="dab6b-173">(Aby wyświetlić wiersze transakcji, konieczne może się okazać wybranie opcji skrócona karta **Transakcje**.)</span><span class="sxs-lookup"><span data-stu-id="dab6b-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="dab6b-174">[![Sprawdzanie, czy w nagłówku i wierszach występuje ten sam kod ponaglenia](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="dab6b-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="dab6b-175">W okienku akcji wybierz pozycję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="dab6b-176">W polu **Data księgowania** wprowadź datę faktury **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="dab6b-177">Musisz teraz utworzyć ponowne ponaglenia dla klienta US-045.</span><span class="sxs-lookup"><span data-stu-id="dab6b-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="dab6b-178">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dab6b-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-179">Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="dab6b-180">Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="dab6b-181">W polu **Data ponaglenia** wprowadź datę faktury **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="dab6b-182">W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="dab6b-183">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-183">Select **OK**.</span></span>
    5. <span data-ttu-id="dab6b-184">Wybierz **OK**, aby utworzyć ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="dab6b-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="dab6b-185">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dab6b-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-186">Zwróć uwagę, że kod ponaglenia w nagłówku to **Ponaglenie 1**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="dab6b-187">Jednak kodem w wierszach transakcji jest **Ponaglenie 2**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="dab6b-188">[![Sprawdza, czy w nagłówku i wierszach pojawiają się różne kody ponagleń](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="dab6b-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="dab6b-189">Kod różni się, ponieważ opcja **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** jest ustawiona na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="dab6b-190">Nie księguj tego ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="dab6b-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="dab6b-191">Przejdź do opcji **Kredyt i windykacje \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**, a następnie na karcie **Windykacja** ustaw wartość **Ignoruj płatności i noty kredytowe podczas obliczania kodu ponaglenia** na wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="dab6b-192">[![Ustawianie opcji Ignorowania płatności i not kredytowych przy obliczaniu kodu ponaglenia na Nie](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="dab6b-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="dab6b-193">Musisz teraz utworzyć ponowne ponaglenia dla klienta US-045.</span><span class="sxs-lookup"><span data-stu-id="dab6b-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="dab6b-194">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="dab6b-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="dab6b-195">Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="dab6b-196">Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="dab6b-197">W polu **Data ponaglenia** wprowadź datę faktury **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="dab6b-198">W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="dab6b-199">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-199">Select **OK**.</span></span>
    5. <span data-ttu-id="dab6b-200">Wybierz **OK**, aby utworzyć ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="dab6b-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="dab6b-201">Przejdź do **Kredyt i windykacje \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i należy zauważyć, że kod ponaglenia w nagłówku i wierszach transakcji to **Ponaglenie 2**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="dab6b-202">[![Ponowne pokazanie, czy w nagłówku i wierszach występuje ten sam kod ponaglenia](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="dab6b-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="dab6b-203">Ten sam kod pojawia się w obu miejscach, ponieważ opcja **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** jest teraz ustawiona na **Nie**.</span><span class="sxs-lookup"><span data-stu-id="dab6b-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>
