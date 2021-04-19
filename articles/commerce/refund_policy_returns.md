---
title: Tworzenie i aktualizowanie zasad zwrotu i zwrotów dla kanału
description: W tym temacie wyjaśniono, jak skonfigurować zasady zwrotu i zwrotów dla kanału.
author: ShalabhjainMSFT
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: e23291130d55fdfb5c2e2077b78c221866d72c5d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792082"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="d32d7-103">Tworzenie i aktualizowanie zasad zwrotów i refundacji dla kanału</span><span class="sxs-lookup"><span data-stu-id="d32d7-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d32d7-104">Zasady dotyczące zwrotów kanałów w systemie Dynamics 365 Commerce umożliwiają detalistom Konfigurowanie wymuszeń, dla których może być dozwolone przetworzenie zwrotów na urządzeniu punktu sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="d32d7-104">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="d32d7-105">W tym temacie wyjaśniono kroki, jak skonfigurować zasady zwrotu i zwrotów dla kanału.</span><span class="sxs-lookup"><span data-stu-id="d32d7-105">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="d32d7-106">Zakres zasad obecnie ogranicza się do ustawiania ofert płatności, które mogą być dozwolone dla kanału.</span><span class="sxs-lookup"><span data-stu-id="d32d7-106">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="d32d7-107">Lista „dozwolone” jest oparta na metodach płatności używanych do dokonywania zakupu.</span><span class="sxs-lookup"><span data-stu-id="d32d7-107">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="d32d7-108">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="d32d7-108">For example:</span></span>

- <span data-ttu-id="d32d7-109">Jeśli zakup został dokonany przy użyciu karty upominkowej, zasady sklepu umożliwiają przetwarzanie zwrotów tylko na nową kartę upominkową lub na kredyt sklepowy.</span><span class="sxs-lookup"><span data-stu-id="d32d7-109">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="d32d7-110">Jeśli sprzedaż zostanie dokonana przy użyciu środków pieniężnych, opcje dozwolone dla zwrotu to gotówka, karta upominkowa i konto odbiorcy, ale nie karta kredytowa.</span><span class="sxs-lookup"><span data-stu-id="d32d7-110">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="d32d7-111">Włącz zasady zwrotów</span><span class="sxs-lookup"><span data-stu-id="d32d7-111">Enable return policy</span></span>

<span data-ttu-id="d32d7-112">Aby włączyć funkcję zasad dotyczących zwrotów kanałów, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="d32d7-112">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="d32d7-113">Otwórz obszar roboczy **Zarządzanie funkcjami** w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d32d7-113">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="d32d7-114">Wyszukaj funkcję **Włącz zasady zwrotów kanału** na liście nazw funkcji.</span><span class="sxs-lookup"><span data-stu-id="d32d7-114">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="d32d7-115">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="d32d7-115">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="d32d7-116">Konfiguruj zasady zwrotów</span><span class="sxs-lookup"><span data-stu-id="d32d7-116">Configure return policy</span></span>

<span data-ttu-id="d32d7-117">Aby skonfigurować zasady dotyczące zwrotów dla sklepu detalicznego lub kanału sprzedaży online, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="d32d7-117">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="d32d7-118">Przejdź do ustawień **Handel detaliczny i inny** \> **Konfiguracja kanału** \> **Zwroty** \> **Zasady zwrotów kanału**.</span><span class="sxs-lookup"><span data-stu-id="d32d7-118">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="d32d7-119">Naciśnij przycisk **Nowy**, aby utworzyć nowy szablon zasad zwrotów.</span><span class="sxs-lookup"><span data-stu-id="d32d7-119">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="d32d7-120">Aby skorzystać z istniejącego szablonu, wybierz szablon w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="d32d7-120">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="d32d7-121">W przypadku nowych szablonów należy dodać nazwę i opis, które ułatwią identyfikowanie zasady, kiedy jest ona stosowana w kanale.</span><span class="sxs-lookup"><span data-stu-id="d32d7-121">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="d32d7-122">![Dodaj nowe zasady dotyczące zwrotów](media/Return-policy-page1.png "Dodaj nowe zasady dotyczące zwrotów")</span><span class="sxs-lookup"><span data-stu-id="d32d7-122">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="d32d7-123">W sekcji **dozwolona Metoda płatności dla zwrotu** Określ **dozwolone** płatności zwrotne, które są właściwe dla każdej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="d32d7-123">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="d32d7-124">![Dodaj metody płatności](media/Return-policy-page2.PNG "Umożliwia ustawienie dozwolonych metod płatności dla typu płatności")</span><span class="sxs-lookup"><span data-stu-id="d32d7-124">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="d32d7-125">Metody płatności pochodzą z metod płatności ustawionych dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="d32d7-125">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="d32d7-126">Dodanie dozwolonego typu metody płatności zwrotnej dla każdej wymienionej metody płatności zapewni, że można wprowadzać zwroty do dozwolonego typu metody płatności zwrotnej.</span><span class="sxs-lookup"><span data-stu-id="d32d7-126">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="d32d7-127">Szablonem zasad zwrotów należy skojarzyć ze sklepami, w których będzie używany.</span><span class="sxs-lookup"><span data-stu-id="d32d7-127">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="d32d7-128">Wybierz opcję **Dodaj** na karcie **kanały sprzedaży detalicznej** i skojarz dostępne kanały.</span><span class="sxs-lookup"><span data-stu-id="d32d7-128">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="d32d7-129">W oknie dialogowym **Wybieranie węzłów organizacji** wybierz sklepy, regiony i organizacje, z którymi szablon ma być skojarzony.</span><span class="sxs-lookup"><span data-stu-id="d32d7-129">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="d32d7-130">Z każdym sklepem można skojarzyć tylko jeden szablon zasad zwrotów.</span><span class="sxs-lookup"><span data-stu-id="d32d7-130">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="d32d7-131">Za pomocą przycisków strzałek wybierz sklepy, regiony lub organizacje</span><span class="sxs-lookup"><span data-stu-id="d32d7-131">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="d32d7-132">Data wejścia w życie zasady będzie datą zastosowania zasad do kanałów i uruchomienia zadań kanału.</span><span class="sxs-lookup"><span data-stu-id="d32d7-132">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="d32d7-133">![Wybierz okienko dialogowe węzły organizacji](media/Return-policy-page3.PNG "Wybierz okienko dialogowe węzły organizacji")</span><span class="sxs-lookup"><span data-stu-id="d32d7-133">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="d32d7-134">Na stronie **harmonogram dystrybucji** Uruchom zadanie **1070**, aby zasady dotyczące zwrotów kanałów były dostępne dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="d32d7-134">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="d32d7-135">Podgląd zasad dotyczących zwrotów dotyczących kanału w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="d32d7-135">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="d32d7-136">Aby wyświetlić dozwolone typy płatności zwrotnych w punkcie sprzedaży, należy wykonać kroki podane w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="d32d7-136">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="d32d7-137">Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.</span><span class="sxs-lookup"><span data-stu-id="d32d7-137">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="d32d7-138">W obszarze **Zmiana i szuflada** wybierz opcję **Wyświetl arkusz**.</span><span class="sxs-lookup"><span data-stu-id="d32d7-138">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="d32d7-139">Umożliwia wybranie transakcji, która jest częścią zwrotu.</span><span class="sxs-lookup"><span data-stu-id="d32d7-139">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="d32d7-140">Wybierz towary do zwrotu i wybierz metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="d32d7-140">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="d32d7-141">Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.</span><span class="sxs-lookup"><span data-stu-id="d32d7-141">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="d32d7-142">Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="d32d7-142">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="d32d7-143">Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.</span><span class="sxs-lookup"><span data-stu-id="d32d7-143">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="d32d7-144">— lub —</span><span class="sxs-lookup"><span data-stu-id="d32d7-144">-or-</span></span>

1. <span data-ttu-id="d32d7-145">Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.</span><span class="sxs-lookup"><span data-stu-id="d32d7-145">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="d32d7-146">Wybierz opcję **transakcja zwrotu** i wprowadź identyfikator paragonu przy użyciu skanowania kodu kreskowego lub za pomocą wpisu ręcznego.</span><span class="sxs-lookup"><span data-stu-id="d32d7-146">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="d32d7-147">Umożliwia wybranie transakcji, która jest częścią zwrotu.</span><span class="sxs-lookup"><span data-stu-id="d32d7-147">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="d32d7-148">Wybierz towary do zwrotu i wybierz metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="d32d7-148">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="d32d7-149">Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.</span><span class="sxs-lookup"><span data-stu-id="d32d7-149">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="d32d7-150">Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="d32d7-150">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="d32d7-151">Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.</span><span class="sxs-lookup"><span data-stu-id="d32d7-151">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="d32d7-152">![Niedozwolone zwroty płatności](media/Return-policy-page6.png "Typ płatności zwrotu jest niedozwolony")</span><span class="sxs-lookup"><span data-stu-id="d32d7-152">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="d32d7-153">![Lista metod płatności](media/Return-policy-page5.PNG "Dozwolone typy płatności zwrotu")</span><span class="sxs-lookup"><span data-stu-id="d32d7-153">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
