---
title: Przykład Przetwarzania ponagleń
description: W tym temacie pokazano przykład, który pokazuje proces tworzenia, drukowania i księgowania ponagleń.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 1b80532463d86dd59b867fca2ee24675396ce717
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826354"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="edbbb-103">Przykład Przetwarzania ponagleń</span><span class="sxs-lookup"><span data-stu-id="edbbb-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="edbbb-104">W tym temacie pokazano przykład, który pokazuje proces tworzenia, drukowania i księgowania ponagleń.</span><span class="sxs-lookup"><span data-stu-id="edbbb-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="edbbb-105">Przykład bazuje na opcji **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia** w kredytach i windykacjach.</span><span class="sxs-lookup"><span data-stu-id="edbbb-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="edbbb-106">Używa danych w firmie demonstracyjnej USMF i nowym odbiorcy, US-045.</span><span class="sxs-lookup"><span data-stu-id="edbbb-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="edbbb-107">Aby rozpocząć, przejdź do **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy**, wybierz opcję **Nowy**, a następnie wprowadź wymagane informacje, aby utworzyć odbiorcę US-045.</span><span class="sxs-lookup"><span data-stu-id="edbbb-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="edbbb-108">Po zakończeniu wykonaj poniższe czynności.</span><span class="sxs-lookup"><span data-stu-id="edbbb-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="edbbb-109">Przejdź do strony **Kredyt i windykacja \> Ponaglenie \> Ustaw kolejność ponagleń** i skonfiguruj kolejność ponagleń, jak pokazano w poniższej tabeli, która jest przypisana do profilu księgowania klienta.</span><span class="sxs-lookup"><span data-stu-id="edbbb-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="edbbb-110">Kod ponaglenia</span><span class="sxs-lookup"><span data-stu-id="edbbb-110">Collection   letter code</span></span>      |     <span data-ttu-id="edbbb-111">opis</span><span class="sxs-lookup"><span data-stu-id="edbbb-111">Description</span></span>                           |     <span data-ttu-id="edbbb-112">Waluta</span><span class="sxs-lookup"><span data-stu-id="edbbb-112">Currency</span></span>      |     <span data-ttu-id="edbbb-113">Konto główne</span><span class="sxs-lookup"><span data-stu-id="edbbb-113">Main   account</span></span>        |     <span data-ttu-id="edbbb-114">Opłata   w walucie</span><span class="sxs-lookup"><span data-stu-id="edbbb-114">Fee   in currency</span></span>     |     <span data-ttu-id="edbbb-115">Minimalna    nadwyżka</span><span class="sxs-lookup"><span data-stu-id="edbbb-115">Minimum   over</span></span>        |     <span data-ttu-id="edbbb-116">Blokuj    dni</span><span class="sxs-lookup"><span data-stu-id="edbbb-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="edbbb-117">Ponaglenie   1</span><span class="sxs-lookup"><span data-stu-id="edbbb-117">Collection   letter 1</span></span>         |     <span data-ttu-id="edbbb-118">Drugie    powiadomienie z opłatą</span><span class="sxs-lookup"><span data-stu-id="edbbb-118">Second   notification with fee</span></span>        |     <span data-ttu-id="edbbb-119">USD</span><span class="sxs-lookup"><span data-stu-id="edbbb-119">USD</span></span>           |                           |     <span data-ttu-id="edbbb-120">0,00</span><span class="sxs-lookup"><span data-stu-id="edbbb-120">0.00</span></span>                  |     <span data-ttu-id="edbbb-121">0,00</span><span class="sxs-lookup"><span data-stu-id="edbbb-121">0.00</span></span>                  |     <span data-ttu-id="edbbb-122">2</span><span class="sxs-lookup"><span data-stu-id="edbbb-122">2</span></span>                 |
|     <span data-ttu-id="edbbb-123">Ponaglenie   2</span><span class="sxs-lookup"><span data-stu-id="edbbb-123">Collection   letter 2</span></span>         |     <span data-ttu-id="edbbb-124">Drugie    powiadomienie z opłatą</span><span class="sxs-lookup"><span data-stu-id="edbbb-124">Second   notification with fee</span></span>        |     <span data-ttu-id="edbbb-125">Usc</span><span class="sxs-lookup"><span data-stu-id="edbbb-125">USC</span></span>           |     <span data-ttu-id="edbbb-126">403150</span><span class="sxs-lookup"><span data-stu-id="edbbb-126">403150</span></span>                |     <span data-ttu-id="edbbb-127">20.00</span><span class="sxs-lookup"><span data-stu-id="edbbb-127">20.00</span></span>                 |     <span data-ttu-id="edbbb-128">10,00</span><span class="sxs-lookup"><span data-stu-id="edbbb-128">10.00</span></span>                 |     <span data-ttu-id="edbbb-129">3</span><span class="sxs-lookup"><span data-stu-id="edbbb-129">3</span></span>                 |
|     <span data-ttu-id="edbbb-130">Ponaglenie</span><span class="sxs-lookup"><span data-stu-id="edbbb-130">Collection</span></span>                    |     <span data-ttu-id="edbbb-131">Ostatnie    powiadomienie z opłatą</span><span class="sxs-lookup"><span data-stu-id="edbbb-131">Final   notification with fee</span></span>         |     <span data-ttu-id="edbbb-132">USD</span><span class="sxs-lookup"><span data-stu-id="edbbb-132">USD</span></span>           |     <span data-ttu-id="edbbb-133">403150</span><span class="sxs-lookup"><span data-stu-id="edbbb-133">403150</span></span>                |     <span data-ttu-id="edbbb-134">50.00</span><span class="sxs-lookup"><span data-stu-id="edbbb-134">50.00</span></span>                 |     <span data-ttu-id="edbbb-135">100.00</span><span class="sxs-lookup"><span data-stu-id="edbbb-135">100.00</span></span>                |     <span data-ttu-id="edbbb-136">15</span><span class="sxs-lookup"><span data-stu-id="edbbb-136">15</span></span>                |

<span data-ttu-id="edbbb-137">Na poniższej ilustracji przedstawiono informacje zawarte w tabeli w sposób, w jakby był to widoczny na stronie **Ponaglenia**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="edbbb-138">[![Konfigurowanie kolejności ponagleń](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="edbbb-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="edbbb-139">Teraz trzeba ustawić dwa parametry, które są wymagane w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="edbbb-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="edbbb-140">Przejdź do **Kredyty i windykacja \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="edbbb-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-141">Na karcie **Windykacje** ustaw **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="edbbb-142">Upewnij się, że w polu **Utwórz ponaglenie dla każdego** jest ustawiona wartość **Odbiorca**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="edbbb-143">[![Ustawianie parametrów rozrachunków z odbiorcami dla windykacji](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="edbbb-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="edbbb-144">Przejdź do **Rozrachunków z odbiorcami \> Faktury \> Wszystkie faktury bezpłatne**, wybierz opcję **Nowy**, a następnie wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="edbbb-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-145">W polu **Konto odbiorcy** zaznacz wartość **US-045**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="edbbb-146">W polu **Data faktury** wprowadź datę faktury **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="edbbb-147">W polu **Data ukończenia** wprowadź datę faktury **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="edbbb-148">Na skróconej karcie **Wiersze faktury** w polu **Konto główne** wprowadź wartość **401100**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="edbbb-149">W polu **Cena jednostkowa** wpisz **500.00**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="edbbb-150">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-150">Select **Post**.</span></span>

    <span data-ttu-id="edbbb-151">Teraz musisz wprowadzić dwie faktury koryguje dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="edbbb-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="edbbb-152">Wybierz opcję **Nowe**, a następnie wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="edbbb-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-153">W polu **Konto odbiorcy** zaznacz wartość **US-045**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="edbbb-154">W polu **Data faktury** wprowadź datę faktury **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="edbbb-155">W polu **Data ukończenia** wprowadź datę faktury **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="edbbb-156">Na skróconej karcie **Wiersze faktury** w polu **Konto główne** wprowadź wartość **401100**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="edbbb-157">W polu **Cena jednostkowa** wpisz **-100.00**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="edbbb-158">Wybierz opcję **Zaksięguj**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-158">Select **Post**.</span></span>

5. <span data-ttu-id="edbbb-159">Powtórz krok 4, ale wprowadź wartość **-200,00** w polu **Cena jednostkowa**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="edbbb-160">Przejdź do **Rozrachunki z odbiorcami \> Odbiorcy \> Wszyscy odbiorcy** i wybierz odbiorcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="edbbb-161">Następnie w okienku akcji wybierz opcję **Transakcje \> Transakcje**, aby przejrzeć wcześniej zaksięgowane transakcje odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="edbbb-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="edbbb-162">[![Przeglądanie zaksięgowanych transakcji odbiorcy](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="edbbb-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="edbbb-163">Musisz teraz utworzyć ponaglenia dla klienta US-045.</span><span class="sxs-lookup"><span data-stu-id="edbbb-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="edbbb-164">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="edbbb-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-165">Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="edbbb-166">Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="edbbb-167">W polu **Data ponaglenia** wprowadź datę faktury **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="edbbb-168">W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="edbbb-169">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-169">Select **OK**.</span></span>
    5. <span data-ttu-id="edbbb-170">Wybierz **OK**, aby utworzyć ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="edbbb-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="edbbb-171">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="edbbb-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-172">Należy zauważyć, że kod ponaglenia w nagłówku i wierszach transakcji to **Ponaglenie 1**, ponieważ to ponaglenie jest pierwszym ponagleniu w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="edbbb-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="edbbb-173">(Aby wyświetlić wiersze transakcji, konieczne może się okazać wybranie opcji skrócona karta **Transakcje**.)</span><span class="sxs-lookup"><span data-stu-id="edbbb-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="edbbb-174">[![Sprawdzanie, czy w nagłówku i wierszach występuje ten sam kod ponaglenia](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="edbbb-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="edbbb-175">W okienku akcji wybierz pozycję **Księguj**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="edbbb-176">W polu **Data księgowania** wprowadź datę faktury **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="edbbb-177">Musisz teraz utworzyć ponowne ponaglenia dla klienta US-045.</span><span class="sxs-lookup"><span data-stu-id="edbbb-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="edbbb-178">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="edbbb-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-179">Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="edbbb-180">Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="edbbb-181">W polu **Data ponaglenia** wprowadź datę faktury **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="edbbb-182">W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="edbbb-183">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-183">Select **OK**.</span></span>
    5. <span data-ttu-id="edbbb-184">Wybierz **OK**, aby utworzyć ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="edbbb-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="edbbb-185">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="edbbb-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-186">Zwróć uwagę, że kod ponaglenia w nagłówku to **Ponaglenie 1**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="edbbb-187">Jednak kodem w wierszach transakcji jest **Ponaglenie 2**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="edbbb-188">[![Sprawdza, czy w nagłówku i wierszach pojawiają się różne kody ponagleń](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="edbbb-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="edbbb-189">Kod różni się, ponieważ opcja **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** jest ustawiona na **Tak**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="edbbb-190">Nie księguj tego ponaglenia.</span><span class="sxs-lookup"><span data-stu-id="edbbb-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="edbbb-191">Przejdź do opcji **Kredyt i windykacje \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**, a następnie na karcie **Windykacja** ustaw wartość **Ignoruj płatności i noty kredytowe podczas obliczania kodu ponaglenia** na wartość **Nie**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="edbbb-192">[![Ustawianie opcji Ignorowania płatności i not kredytowych przy obliczaniu kodu ponaglenia na Nie](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="edbbb-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="edbbb-193">Musisz teraz utworzyć ponowne ponaglenia dla klienta US-045.</span><span class="sxs-lookup"><span data-stu-id="edbbb-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="edbbb-194">Wybierz kolejno opcje **Okienko nawigacji \> Ponaglenie \> Utwórz ponaglenia** i wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="edbbb-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="edbbb-195">Ustaw w opcjach **Faktura** i **Faktura korygująca** wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="edbbb-196">Domyślnie w polu **Ponaglenie** powinno być ustawiona wartość **Windykacyjny według odbiorcy**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="edbbb-197">W polu **Data ponaglenia** wprowadź datę faktury **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="edbbb-198">W **Rekordach, które mają być uwzględnione** na skróconej karcie, wybierz opcję **Filtruj**, a następnie w polu **Konto odbiorcy** dodaj nabywcę **US-045**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="edbbb-199">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-199">Select **OK**.</span></span>
    5. <span data-ttu-id="edbbb-200">Wybierz **OK**, aby utworzyć ponaglenie.</span><span class="sxs-lookup"><span data-stu-id="edbbb-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="edbbb-201">Przejdź do **Kredyt i windykacje \> Ponaglenie \> Przeglądnij i przetwórz ponaglenia** i należy zauważyć, że kod ponaglenia w nagłówku i wierszach transakcji to **Ponaglenie 2**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="edbbb-202">[![Ponowne pokazanie, czy w nagłówku i wierszach występuje ten sam kod ponaglenia](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="edbbb-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="edbbb-203">Ten sam kod pojawia się w obu miejscach, ponieważ opcja **Ignoruj płatności i noty kredytowe podczas obliczania opcji kodu ponaglenia w kredytach i windykacjach** jest teraz ustawiona na **Nie**.</span><span class="sxs-lookup"><span data-stu-id="edbbb-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>