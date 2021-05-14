---
title: Obsługa funkcji podatków dla zamówień przeniesienia
description: W tym temacie wyjaśniono, że nowa funkcja podatków obsługuje zamówienia przeniesienia, używając usługi obliczania podatku.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d1b99046b0e439c9dadbb240050e270a7b2a6914
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920962"
---
# <a name="tax-feature-support-for-transfer-orders"></a><span data-ttu-id="7b722-103">Obsługa funkcji podatków dla zamówień przeniesienia</span><span class="sxs-lookup"><span data-stu-id="7b722-103">Tax feature support for transfer orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b722-104">Ten temat zawiera informacje dotyczące obliczania podatku i księgowania integracji w zamówieniach przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-104">This topic provides information about tax calculation and posting integration in transfer orders.</span></span> <span data-ttu-id="7b722-105">Ta funkcja umożliwia konfigurowanie obliczania podatku i księgowania w zamówieniach przeniesienia dla przeniesień zapasów.</span><span class="sxs-lookup"><span data-stu-id="7b722-105">This functionality lets you set up tax calculation and posting in transfer orders for stock transfers.</span></span> <span data-ttu-id="7b722-106">Zgodnie z obowiązującymi w Unii Europejskiej (UE) przepisami dotyczącymi podatku od wartości dodanej przeniesienia zapasów są traktowane jako wewnątrzunijne oraz wewnątrzunijne nabycia.</span><span class="sxs-lookup"><span data-stu-id="7b722-106">Under European Union (EU) value-added tax (VAT) regulations, stock transfers are considered intra-community supply and intra-community acquisitions.</span></span>

<span data-ttu-id="7b722-107">Aby skonfigurować i korzystać z tej funkcji, musisz wykonać trzy główne kroki:</span><span class="sxs-lookup"><span data-stu-id="7b722-107">To configure and use this functionality, you must complete three main steps:</span></span>

1. <span data-ttu-id="7b722-108">**Ustawienia usługi RCS:** W usłudze konfiguracji wymogów prawnych skonfiguruj funkcję podatków, kody podatków i kody podatków, które mogą być aplikacyjne do określania kodów podatków w zamówieniach przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-108">**RCS setup:** In Regulatory Configuration Service, set up the tax feature, tax codes, and tax codes applicability for tax code determination in transfer orders.</span></span>
2. <span data-ttu-id="7b722-109">**Ustawienia finansów:** W firmie Microsoft Dynamics 365 Finance włącz funkcję **Podatek w zamówieniu przeniesienia**, skonfiguruj parametry usługi podatkowej dla zapasów i skonfiguruj podstawowe parametry podatku.</span><span class="sxs-lookup"><span data-stu-id="7b722-109">**Finance setup:** In Microsoft Dynamics 365 Finance, turn on the **Tax in transfer order** feature, set up the tax service parameters for inventory, and set up core tax parameters.</span></span>
3. <span data-ttu-id="7b722-110">**Konfiguracja zapasów:** konfigurowanie konfiguracji zapasów dla transakcji zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-110">**Inventory setup:** Set up the inventory configuration for transfer order transactions.</span></span>

## <a name="set-up-rcs-for-tax-and-transfer-order-transactions"></a><span data-ttu-id="7b722-111">Konfigurowanie RCS dla transakcji zamówień podatku i przeniesienia</span><span class="sxs-lookup"><span data-stu-id="7b722-111">Set up RCS for tax and transfer order transactions</span></span>

<span data-ttu-id="7b722-112">Aby skonfigurować podatek związany z zamówieniem przeniesienia, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="7b722-112">Follow these steps to set up the tax that is involved in a transfer order.</span></span> <span data-ttu-id="7b722-113">W przykładzie, który zostanie pokazany, zamówienie przeniesienia jest z Holandii do Belgii.</span><span class="sxs-lookup"><span data-stu-id="7b722-113">In the example that is shown here, the transfer order is from the Netherlands to Belgium.</span></span>

1. <span data-ttu-id="7b722-114">Na stronie **Funkcje podatkowe** na karcie **Wersje** wybierz wersję roboczą funkcji, a następnie wybierz pozycję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="7b722-114">On the **Tax features** page, on the **Versions** tab, select the draft feature version, and then select **Edit**.</span></span>

    ![Wybieranie edycji](../media/image1.png)

2. <span data-ttu-id="7b722-116">Na stronie **Ustawienia funkcji podatków**, na karcie **Kody podatków** wybierz opcję **Dodaj**, aby utworzyć nowe kody podatków.</span><span class="sxs-lookup"><span data-stu-id="7b722-116">On the **Tax features setup** page, on the **Tax codes** tab, select **Add** to create new tax codes.</span></span> <span data-ttu-id="7b722-117">W tym przykładzie tworzone są trzy kody podatków:**NL-Exempt**, **BE-RC-21** i **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="7b722-117">For this example, three tax codes are created: **NL-Exempt**, **BE-RC-21**, and **BE-RC+21**.</span></span>

    - <span data-ttu-id="7b722-118">Gdy zamówienie przeniesienia jest wysyłane z magazynu w Holandii, stosowany jest holenderski kod zwolnienia z podatku VAT (**NL-Exempt**).</span><span class="sxs-lookup"><span data-stu-id="7b722-118">When a transfer order is shipped from a warehouse in the Netherlands, the Netherlands VAT exempted tax code (**NL-Exempt**) is applied.</span></span>
      
        <span data-ttu-id="7b722-119">Utwórz kod podatku **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="7b722-119">Create the tax code **NL-Exempt**.</span></span>
        1. <span data-ttu-id="7b722-120">Wybierz opcję **Dodaj** i wprowadź numer **NL-Exempt** w polu **Kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-120">Select **Add**, enter **NL-Exempt** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="7b722-121">Wybierz **Według kwoty netto** w polu **Składnik podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-121">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="7b722-122">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7b722-122">Select **Save**.</span></span>
        4. <span data-ttu-id="7b722-123">Na karcie **Stawka** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="7b722-123">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="7b722-124">Przełącz **Jest zwolniony** na **Tak** w sekcji **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="7b722-124">Swtich **Is Exempt** to **Yes** in the **General** section.</span></span>

        ![Kod zwolnienia z podatku (NL)](../media/image2.png)

    - <span data-ttu-id="7b722-126">Gdy zamówienie przeniesienia zostanie odebrane w magazynie belgijskim, mechanizm opłaty zwrotnej jest stosowany przy użyciu kodów podatków **BE-RC-21** i **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="7b722-126">When a transfer order is received at a Belgium warehouse, the reverse charge mechanism is applied by using the **BE-RC-21** and **BE-RC+21** tax codes.</span></span>
        
        <span data-ttu-id="7b722-127">Utwórz kod podatku **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="7b722-127">Create the tax code **BE-RC-21**.</span></span>      
        1. <span data-ttu-id="7b722-128">Wybierz opcję **Dodaj** i wprowadź numer **BE-RC-21** w polu **Kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-128">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="7b722-129">Wybierz **Według kwoty netto** w polu **Składnik podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-129">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="7b722-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7b722-130">Select **Save**.</span></span>
        4. <span data-ttu-id="7b722-131">Na karcie **Stawka** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="7b722-131">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="7b722-132">Wprowadź **-21** w polu **Stawka podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-132">Enter **-21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="7b722-133">Czy swtich **Wsteczna opłata** z **Tak** w sekcji **Ogólne**.</span><span class="sxs-lookup"><span data-stu-id="7b722-133">Swtich **Is Reverse Charge** to **Yes** in the **General** section.</span></span>
        7. <span data-ttu-id="7b722-134">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7b722-134">Select **Save**.</span></span>

        ![Kod podatku BE-RC-21 dla opłat zwrotnych](../media/image3.png)
        
        <span data-ttu-id="7b722-136">Utwórz kod podatku **BE-RC+21**.</span><span class="sxs-lookup"><span data-stu-id="7b722-136">Create the tax code **BE-RC+21**.</span></span>
        1. <span data-ttu-id="7b722-137">Wybierz opcję **Dodaj** i wprowadź numer **BE-RC-21** w polu **Kod podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-137">Select **Add**, enter **BE-RC-21** in the **Tax code** field.</span></span>
        2. <span data-ttu-id="7b722-138">Wybierz **Według kwoty netto** w polu **Składnik podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-138">Select **By Net Amount** in the **Tax component** field.</span></span>
        3. <span data-ttu-id="7b722-139">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7b722-139">Select **Save**.</span></span>
        4. <span data-ttu-id="7b722-140">Na karcie **Stawka** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="7b722-140">Select **Add** in the **Rate** table.</span></span>
        5. <span data-ttu-id="7b722-141">Wprowadź **21** w polu **Stawka podatku**.</span><span class="sxs-lookup"><span data-stu-id="7b722-141">Enter **21** in the **Tax Rate** field.</span></span>
        6. <span data-ttu-id="7b722-142">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="7b722-142">Select **Save**.</span></span>

        ![Kod podatku BE-RC+21 dla opłat zwrotnych](../media/image4.png)

3. <span data-ttu-id="7b722-144">Zdefiniuj możliwości zastosowania kodów podatków.</span><span class="sxs-lookup"><span data-stu-id="7b722-144">Define the applicability of the tax codes.</span></span>

    1. <span data-ttu-id="7b722-145">Wybierz opcję **Zarządzaj kolumnami**, a następnie wybierz kolumny, które mają być używane do tworzenia tabeli możliwości zastosowania.</span><span class="sxs-lookup"><span data-stu-id="7b722-145">Select **Manage columns**, and then select columns that should be used to build the applicability table.</span></span>

        > [!NOTE]
        > <span data-ttu-id="7b722-146">Pamiętaj, aby dodać do tabeli kolumny **Proces biznesowy** i **Kierunki podatków**.</span><span class="sxs-lookup"><span data-stu-id="7b722-146">Be sure to add the **Business process** and **Tax directions** columns to the table.</span></span> <span data-ttu-id="7b722-147">Obie kolumny są niezbędne do funkcjonalności podatku w zamówieniach przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-147">Both columns are essential to the functionality for tax in transfer orders.</span></span>

    2. <span data-ttu-id="7b722-148">Dodaj Reguły zastosowania.</span><span class="sxs-lookup"><span data-stu-id="7b722-148">Add applicability rules.</span></span> <span data-ttu-id="7b722-149">Nie pozostaw pustych pól **Kody podatków**, **Grupa podatków** i **Grupa podatków dla pozycji**.</span><span class="sxs-lookup"><span data-stu-id="7b722-149">Don't leave the **Tax codes**, **Tax group**, and **Item tax group** fields blank.</span></span>
        
        <span data-ttu-id="7b722-150">Dodaj nową regułę wysyłki zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-150">Add a new rule for transfer order shipment.</span></span>
        1. <span data-ttu-id="7b722-151">Na karcie **Stawka** wybierz tabelę **Reguły stosowania**.</span><span class="sxs-lookup"><span data-stu-id="7b722-151">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="7b722-152">W polu **Proces biznesowy** wybierz pozycję **Zapasy**, aby reguła obowiązywała dla zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-152">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="7b722-153">W polu **Kraj/region wysyłki** wprowadź nazwę **NLD**.</span><span class="sxs-lookup"><span data-stu-id="7b722-153">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="7b722-154">W polu **Kraj/region wysyłki** wprowadź nazwę **BEL**.</span><span class="sxs-lookup"><span data-stu-id="7b722-154">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="7b722-155">W polu **Kierunek podatku** wybierz opcję **Dane wyjściowe**, aby reguła obowiązywała dla wysyłki zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-155">In the **Tax direction** field, select **Output** to make the rule applicable to transfer order shipment.</span></span>
        6. <span data-ttu-id="7b722-156">W polu **Kod podatku** wybierz opcję **NL-Exempt**.</span><span class="sxs-lookup"><span data-stu-id="7b722-156">In the **Tax codes** field, select **NL-Exempt**.</span></span>
        7. <span data-ttu-id="7b722-157">W polach **Grupa podatków** i **Grupa podatków dla pozycji** wprowadź powiązaną grupę podatków i grupę podatków dla towaru zdefiniowaną w systemie Finance.</span><span class="sxs-lookup"><span data-stu-id="7b722-157">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>
        
        <span data-ttu-id="7b722-158">Dodaj kolejną regułę dotyczącą potwierdzenia przelewu.</span><span class="sxs-lookup"><span data-stu-id="7b722-158">Add another rule for transfer order receipt.</span></span>
        1. <span data-ttu-id="7b722-159">Na karcie **Stawka** wybierz tabelę **Reguły stosowania**.</span><span class="sxs-lookup"><span data-stu-id="7b722-159">Select **Add** in the **Applicability rules** table.</span></span>
        2. <span data-ttu-id="7b722-160">W polu **Proces biznesowy** wybierz pozycję **Zapasy**, aby reguła obowiązywała dla zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-160">In the **Business process** field, select **Inventory** to make the rule applicable for a transfer order.</span></span>
        3. <span data-ttu-id="7b722-161">W polu **Kraj/region wysyłki** wprowadź nazwę **NLD**.</span><span class="sxs-lookup"><span data-stu-id="7b722-161">In the **Ship From Country/Region** field, enter **NLD**.</span></span>
        4. <span data-ttu-id="7b722-162">W polu **Kraj/region wysyłki** wprowadź nazwę **BEL**.</span><span class="sxs-lookup"><span data-stu-id="7b722-162">In the **Ship To Country/Region** field, enter **BEL**.</span></span>
        5. <span data-ttu-id="7b722-163">W polu **Kierunek podatku** wybierz opcję **Wejście**, aby reguła obowiązywała dla odbioru zamówienia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-163">In the **Tax direction** field, select **Input** to make the rule applicable to transfer order receipt.</span></span>
        6. <span data-ttu-id="7b722-164">W polu **Kody podatków** wybierz **BE-RC+21** i **BE-RC-21**.</span><span class="sxs-lookup"><span data-stu-id="7b722-164">In the **Tax codes** field, select **BE-RC+21** and **BE-RC-21**.</span></span>
        7. <span data-ttu-id="7b722-165">W polach **Grupa podatków** i **Grupa podatków dla pozycji** wprowadź powiązaną grupę podatków i grupę podatków dla towaru zdefiniowaną w systemie Finance.</span><span class="sxs-lookup"><span data-stu-id="7b722-165">In the **Tax Group** field and the **Item Tax Group**, enter the related sales tax group and item sales tax group which are defined in your Finance system.</span></span>

        ![Reguły zastosowania](../media/image5.png)

4. <span data-ttu-id="7b722-167">Ukończ i opublikuj nową wersję funkcji podatkowej.</span><span class="sxs-lookup"><span data-stu-id="7b722-167">Complete and publish the new tax feature version.</span></span>

    <span data-ttu-id="7b722-168">[![Zmiana statusu nowej wersji](../media/image6.png)](../media/image6.png)</span><span class="sxs-lookup"><span data-stu-id="7b722-168">[![Changing the status of the new version](../media/image6.png)](../media/image6.png)</span></span>

## <a name="set-up-finance-for-transfer-order-transactions"></a><span data-ttu-id="7b722-169">Konfigurowanie Finance dla transakcji zamówień podatku i przeniesienia</span><span class="sxs-lookup"><span data-stu-id="7b722-169">Set up Finance for transfer order transactions</span></span>

<span data-ttu-id="7b722-170">Wykonaj poniższe czynności, aby włączyć i skonfigurować podatki dla zleceń przelewów.</span><span class="sxs-lookup"><span data-stu-id="7b722-170">Follow these steps to enable and set up taxes for transfer orders.</span></span>

1. <span data-ttu-id="7b722-171">W Finance kliknij kolejno opcje **Obszary robocze** \> **Zarządzanie danymi**.</span><span class="sxs-lookup"><span data-stu-id="7b722-171">In Finance, go to **Workspaces** \> **Feature management**.</span></span>
2. <span data-ttu-id="7b722-172">Na liście znajdź i wybierz funkcję **Podatek w zamówieniu przeniesienia**, a następnie wybierz opcję **Włącz teraz**, aby ją włączyć.</span><span class="sxs-lookup"><span data-stu-id="7b722-172">In the list, find and select the **Tax in transfer order** feature, and then select **Enable now** to turn it on.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7b722-173">Funkcja **Podatek w zamówieniu przeniesienia** jest w pełni zależna od usługi podatkowej.</span><span class="sxs-lookup"><span data-stu-id="7b722-173">The **Tax in transfer order** feature is fully dependent on the tax service.</span></span> <span data-ttu-id="7b722-174">Dlatego można ją włączona tylko po zainstalowaniu usługi podatkowej.</span><span class="sxs-lookup"><span data-stu-id="7b722-174">Therefore, it can be turned on only after you've installed the tax service.</span></span>

    ![Podatek funkcji zamówienia przeniesienia](../media/image7.png)

3. <span data-ttu-id="7b722-176">Włącz usługę podatkową i wybierz proces biznesowy **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="7b722-176">Enable the tax service, and select the **Inventory** business process.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7b722-177">Ten krok należy wykonać dla każdej firmy w oknie Finance, gdzie ma być dostępna usługa podatkowa i funkcja podatku w zamówieniach przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-177">You must complete this step for each legal entity in Finance where you want the tax service and the functionality for tax in transfer orders to be available.</span></span>

    1. <span data-ttu-id="7b722-178">przejdź do **Podatek** \> **Ustawienia** \> **Konfiguracja podatku** \> **Konfiguracja usług podatkowych**.</span><span class="sxs-lookup"><span data-stu-id="7b722-178">Go to **Tax** \> **Setup** \> **Tax configuration** \> **Tax service setup**.</span></span>
    2. <span data-ttu-id="7b722-179">W polu **Proces biznesowy** wybierz pozycję **Zapasy**.</span><span class="sxs-lookup"><span data-stu-id="7b722-179">In the **Business process** field, select **Inventory**.</span></span>

    ![Ustawianie pola Proces biznesowy](../media/image8.png)

4. <span data-ttu-id="7b722-181">Sprawdź, czy jest ustawiony mechanizm opłaty zwrotnej.</span><span class="sxs-lookup"><span data-stu-id="7b722-181">Verify that the reverse charge mechanism is set up.</span></span> <span data-ttu-id="7b722-182">Przejdź do **Księga główna** \> **Ustawienia** \> **Parametry**, a następnie na karcie **Opłata zwrotna** sprawdź, czy opcja **Włącz opłatę zwrotną** ma wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="7b722-182">Go to **General ledger** \> **Setup** \> **Parameters**, and then, on the **Reverse charge** tab, verify that the **Enable reverse charge** option is set to **Yes**.</span></span>

    ![Włącz opcję opłaty zwrotnej](../media/image9.png)

5. <span data-ttu-id="7b722-184">Sprawdź, czy powiązane kody podatków, grupy podatków, grupy podatków dla pozycji i numery rejestracji VAT zostały ustawione w finansach zgodnie z wytycznymi usługi podatkowej.</span><span class="sxs-lookup"><span data-stu-id="7b722-184">Verify that the related tax codes, tax groups, item tax groups, and VAT registration numbers have been set up in Finance according to the tax service guidance.</span></span>
6. <span data-ttu-id="7b722-185">Konfigurowanie tymczasowego konta tranzytowego.</span><span class="sxs-lookup"><span data-stu-id="7b722-185">Set up an interim transit account.</span></span> <span data-ttu-id="7b722-186">Ten krok jest wymagany tylko w przypadku, gdy podatek zastosowany do zamówienia przeniesienia nie ma zastosowania do mechanizmu zwolnienia z podatku lub opłaty zwrotnej.</span><span class="sxs-lookup"><span data-stu-id="7b722-186">This step is required only when the tax that is applied to a transfer order isn't applicable to a tax exempted or reverse charge mechanism.</span></span>

    1. <span data-ttu-id="7b722-187">Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Podatek** \> **Grupy księgowania**.</span><span class="sxs-lookup"><span data-stu-id="7b722-187">Go to **Tax** \> **Setup** \> **Sales tax** \> **Ledger posting groups**.</span></span>
    2. <span data-ttu-id="7b722-188">W polu **Tranzyt tymczasowy** wybierz konto księgowe.</span><span class="sxs-lookup"><span data-stu-id="7b722-188">In the **Interim transit** field, select a ledger account.</span></span>

    ![Konfigurowanie tymczasowego konta tranzytowego](../media/image10.png)

## <a name="set-up-basic-inventory-for-transfer-order-transactions"></a><span data-ttu-id="7b722-190">Konfigurowanie Finance dla transakcji zamówień podatku i przeniesienia</span><span class="sxs-lookup"><span data-stu-id="7b722-190">Set up basic inventory for transfer order transactions</span></span>

<span data-ttu-id="7b722-191">Aby włączyć transakcje zamówień przeniesienia, należy wykonać następujące czynności, aby skonfigurować magazyn podstawowy.</span><span class="sxs-lookup"><span data-stu-id="7b722-191">Follow these steps to set up basic inventory to enable transfer order transactions.</span></span>

1. <span data-ttu-id="7b722-192">Należy utworzyć miejsca wysyłki i wysyłki dla magazynów w różnych krajach lub regionach, a następnie dodać adres podstawowy dla poszczególnych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7b722-192">Create ship-from and ship-to sites for your warehouses in different countries or regions, and add the primary address for each site.</span></span>

    1. <span data-ttu-id="7b722-193">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Magazyn** \> **Lokalizacja**.</span><span class="sxs-lookup"><span data-stu-id="7b722-193">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Sites**.</span></span>
    2. <span data-ttu-id="7b722-194">Wybierz **opcję Nowy**, aby utworzyć witrynę, która zostanie później przypisana do magazynu.</span><span class="sxs-lookup"><span data-stu-id="7b722-194">Select **New** to create the site that you will assign to a warehouse later.</span></span>
    3. <span data-ttu-id="7b722-195">Powtórz krok 2 dla wszystkich innych witryn, które musisz utworzyć.</span><span class="sxs-lookup"><span data-stu-id="7b722-195">Repeat step 2 for all the other sites that you must create.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b722-196">Jedno z tworzyć witryn powinno mieć nazwę **Tranzyt**.</span><span class="sxs-lookup"><span data-stu-id="7b722-196">One of the sites that you create should be named **Transit**.</span></span> <span data-ttu-id="7b722-197">W kolejnych krokach tej procedury należy przypisać ten obiekt do magazynu tranzytowego, aby załączniki magazynowe powiązane z podatkami można było księgować w transakcjach „wyślij” i „odbierz” dla zamówień przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-197">In later steps of this procedure, you will assign this site to the transit warehouse, so that tax-related inventory vouchers can be posted in "ship" and "receive" transactions for transfer orders.</span></span> <span data-ttu-id="7b722-198">Adres miejsca tranzytowego nie ma znaczenia w obliczeniach podatku.</span><span class="sxs-lookup"><span data-stu-id="7b722-198">The address of the transit site is irrelevant to tax calculation.</span></span> <span data-ttu-id="7b722-199">Dlatego możesz zostawić to pole puste.</span><span class="sxs-lookup"><span data-stu-id="7b722-199">Therefore, you can leave it blank.</span></span>

    ![Konfigurowanie lokalizacji](../media/image11.png)

2. <span data-ttu-id="7b722-201">Umożliwia tworzenie magazynów miejsc wysyłki, tranzytu i wysyłki do.</span><span class="sxs-lookup"><span data-stu-id="7b722-201">Create ship-from, transit, and ship-to warehouses.</span></span> <span data-ttu-id="7b722-202">Wszystkie informacje adresowe zachowywane w magazynie zastępują adres lokalizacji podczas obliczania podatku.</span><span class="sxs-lookup"><span data-stu-id="7b722-202">Any address information that is maintained in a warehouse will override the site address during tax calculation.</span></span>

    1. <span data-ttu-id="7b722-203">Wybierz kolejno opcje **Zarządzanie magazynem** \> **Ustawienia** \> **Magazyn** \> **Magazyny**.</span><span class="sxs-lookup"><span data-stu-id="7b722-203">Go to **Warehouse management** \> **Setup** \> **Warehouse** \> **Warehouses**.</span></span>
    2. <span data-ttu-id="7b722-204">Wybierz **opcję Nowy**, aby utworzyć witrynę, która zostanie później przypisana do magazynu.</span><span class="sxs-lookup"><span data-stu-id="7b722-204">Select **New** to create a warehouse, and assign it to the corresponding site.</span></span>
    3. <span data-ttu-id="7b722-205">Powtórz krok 2, aby utworzyć magazyn dla każdego wymaganego magazynu.</span><span class="sxs-lookup"><span data-stu-id="7b722-205">Repeat step 2 to create a warehouse for each site as required.</span></span>

    ![Ustawianie magazynów](../media/image12.png)

    > [!NOTE]
    > <span data-ttu-id="7b722-207">W przypadku magazynu wysyłki z transakcji zamówienia przeniesienia w polu **Magazyn tranzytowy** musi być wybrany magazyn tranzytowy.</span><span class="sxs-lookup"><span data-stu-id="7b722-207">For a ship-from warehouse, a transit warehouse must be selected in the **Transit warehouse** field for transfer order transactions.</span></span>
    >
    > ![Wybieranie magazynu tranzytowego](../media/image13.png)

3. <span data-ttu-id="7b722-209">Sprawdź, czy konfiguracja księgowania zapasów jest skonfigurowana dla transakcji zlecenia przeniesienia.</span><span class="sxs-lookup"><span data-stu-id="7b722-209">Verify that the inventory posting configuration is set up for transfer order transactions.</span></span>

    1. <span data-ttu-id="7b722-210">Przejdź do **Zarządzanie zapasami** \> **Konfiguracja** \> **Księgowanie** \> **Księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="7b722-210">Go to **Inventory management** \> **Setup** \> **Posting** \> **Posting**.</span></span>
    2. <span data-ttu-id="7b722-211">Na karcie **Zapasy** sprawdź, czy konto księgowe jest ustawione zarówno dla księgowania **wydania z magazynu**, jak i księgowania **przyjęcia na magazyn**.</span><span class="sxs-lookup"><span data-stu-id="7b722-211">On the **Inventory** tab, verify that a ledger account is set up for both **Inventory issue** and **Inventory receipt** posting.</span></span>

        ![Konfigurowanie księgowania wydania z magazynu i przyjęcia na magazyn](../media/image14.png)

    3. <span data-ttu-id="7b722-213">Sprawdź, czy konto księgowe jest ustawione do księgowania zobowiązań **międzyjednostkowych**.</span><span class="sxs-lookup"><span data-stu-id="7b722-213">Verify that a ledger account is set up for **Inter-unit payable** posting.</span></span>

        ![Konfigurowanie księgowania zobowiązań międzyjednostkowych](../media/image15.png)

    4. <span data-ttu-id="7b722-215">Sprawdź, czy konto księgowe jest ustawione do księgowania **Odbiorów między jednostkami**.</span><span class="sxs-lookup"><span data-stu-id="7b722-215">Verify that a ledger account is set up for **Inter-unit receivable** posting.</span></span>

        ![Konfigurowanie księgowania rachunków z odbiorami między jednostkami](../media/image16.png)
