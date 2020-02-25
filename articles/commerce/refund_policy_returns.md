---
title: Tworzenie i aktualizowanie zasad zwrotu i zwrotów dla kanału
description: W tym temacie wyjaśniono, jak skonfigurować zasady zwrotu i zwrotów dla kanału.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 66bb9bbd338561315f2f69ae4aff86a67513b190
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3023749"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="e76da-103">Tworzenie i aktualizowanie zasad zwrotu i zwrotów dla kanału</span><span class="sxs-lookup"><span data-stu-id="e76da-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]


## <a name="overview"></a><span data-ttu-id="e76da-104">Omówienie</span><span class="sxs-lookup"><span data-stu-id="e76da-104">Overview</span></span>

<span data-ttu-id="e76da-105">Zasady dotyczące zwrotów kanałów w systemie Dynamics 365 Commerce umożliwiają detalistom Konfigurowanie wymuszeń, dla których może być dozwolone przetworzenie zwrotów na urządzeniu punktu sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="e76da-105">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="e76da-106">W tym temacie wyjaśniono kroki, jak skonfigurować zasady zwrotu i zwrotów dla kanału.</span><span class="sxs-lookup"><span data-stu-id="e76da-106">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="e76da-107">Zakres zasad obecnie ogranicza się do ustawiania ofert płatności, które mogą być dozwolone dla kanału.</span><span class="sxs-lookup"><span data-stu-id="e76da-107">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="e76da-108">Lista „dozwolone” jest oparta na metodach płatności używanych do dokonywania zakupu.</span><span class="sxs-lookup"><span data-stu-id="e76da-108">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="e76da-109">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="e76da-109">For example:</span></span>

- <span data-ttu-id="e76da-110">Jeśli zakup został dokonany przy użyciu karty upominkowej, zasady sklepu umożliwiają przetwarzanie zwrotów tylko na nową kartę upominkową lub na kredyt sklepowy.</span><span class="sxs-lookup"><span data-stu-id="e76da-110">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="e76da-111">Jeśli sprzedaż zostanie dokonana przy użyciu środków pieniężnych, opcje dozwolone dla zwrotu to gotówka, karta upominkowa i konto odbiorcy, ale nie karta kredytowa.</span><span class="sxs-lookup"><span data-stu-id="e76da-111">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="e76da-112">Włącz zasady zwrotów</span><span class="sxs-lookup"><span data-stu-id="e76da-112">Enable return policy</span></span>

<span data-ttu-id="e76da-113">Aby włączyć funkcję zasad dotyczących zwrotów kanałów, wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e76da-113">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="e76da-114">Otwórz obszar roboczy **Zarządzanie funkcjami** w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e76da-114">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="e76da-115">Wyszukaj funkcję **Włącz zasady zwrotów kanału** na liście nazw funkcji.</span><span class="sxs-lookup"><span data-stu-id="e76da-115">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="e76da-116">Wybierz **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="e76da-116">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="e76da-117">Konfiguruj zasady zwrotów</span><span class="sxs-lookup"><span data-stu-id="e76da-117">Configure return policy</span></span>

<span data-ttu-id="e76da-118">Aby skonfigurować zasady dotyczące zwrotów dla sklepu detalicznego lub kanału sprzedaży online, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="e76da-118">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="e76da-119">Przejdź do ustawień **Handel detaliczny i inny** \> **Konfiguracja kanału** \> **Zwroty** \> **Zasady zwrotów kanału**.</span><span class="sxs-lookup"><span data-stu-id="e76da-119">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="e76da-120">Naciśnij przycisk **Nowy**, aby utworzyć nowy szablon zasad zwrotów.</span><span class="sxs-lookup"><span data-stu-id="e76da-120">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="e76da-121">Aby skorzystać z istniejącego szablonu, wybierz szablon w lewym okienku.</span><span class="sxs-lookup"><span data-stu-id="e76da-121">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="e76da-122">W przypadku nowych szablonów należy dodać nazwę i opis, które ułatwią identyfikowanie zasady, kiedy jest ona stosowana w kanale.</span><span class="sxs-lookup"><span data-stu-id="e76da-122">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="e76da-123">![Dodaj nowe zasady dotyczące zwrotów](media/Return-policy-page1.png "Dodaj nowe zasady dotyczące zwrotów")</span><span class="sxs-lookup"><span data-stu-id="e76da-123">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="e76da-124">W sekcji **dozwolona Metoda płatności dla zwrotu** Określ **dozwolone** płatności zwrotne, które są właściwe dla każdej metody płatności.</span><span class="sxs-lookup"><span data-stu-id="e76da-124">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="e76da-125">![Dodaj metody płatności](media/Return-policy-page2.PNG "Umożliwia ustawienie dozwolonych metod płatności dla typu płatności")</span><span class="sxs-lookup"><span data-stu-id="e76da-125">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="e76da-126">Metody płatności pochodzą z metod płatności ustawionych dla organizacji.</span><span class="sxs-lookup"><span data-stu-id="e76da-126">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="e76da-127">Dodanie dozwolonego typu metody płatności zwrotnej dla każdej wymienionej metody płatności zapewni, że można wprowadzać zwroty do dozwolonego typu metody płatności zwrotnej.</span><span class="sxs-lookup"><span data-stu-id="e76da-127">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="e76da-128">Szablonem zasad zwrotów należy skojarzyć ze sklepami, w których będzie używany.</span><span class="sxs-lookup"><span data-stu-id="e76da-128">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="e76da-129">Wybierz opcję **Dodaj** na karcie **kanały sprzedaży detalicznej** i skojarz dostępne kanały.</span><span class="sxs-lookup"><span data-stu-id="e76da-129">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="e76da-130">W oknie dialogowym **Wybieranie węzłów organizacji** wybierz sklepy, regiony i organizacje, z którymi szablon ma być skojarzony.</span><span class="sxs-lookup"><span data-stu-id="e76da-130">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="e76da-131">Z każdym sklepem można skojarzyć tylko jeden szablon zasad zwrotów.</span><span class="sxs-lookup"><span data-stu-id="e76da-131">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="e76da-132">Za pomocą przycisków strzałek wybierz sklepy, regiony lub organizacje</span><span class="sxs-lookup"><span data-stu-id="e76da-132">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="e76da-133">Data wejścia w życie zasady będzie datą zastosowania zasad do kanałów i uruchomienia zadań kanału.</span><span class="sxs-lookup"><span data-stu-id="e76da-133">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="e76da-134">![Wybierz okienko dialogowe węzły organizacji](media/Return-policy-page3.PNG "Wybierz okienko dialogowe węzły organizacji")</span><span class="sxs-lookup"><span data-stu-id="e76da-134">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="e76da-135">Na stronie **harmonogram dystrybucji** Uruchom zadanie **1070**, aby zasady dotyczące zwrotów kanałów były dostępne dla punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e76da-135">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="e76da-136">Podgląd zasad dotyczących zwrotów dotyczących kanału w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e76da-136">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="e76da-137">Aby wyświetlić dozwolone typy płatności zwrotnych w punkcie sprzedaży, należy wykonać kroki podane w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="e76da-137">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="e76da-138">Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.</span><span class="sxs-lookup"><span data-stu-id="e76da-138">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="e76da-139">W obszarze **Zmiana i szuflada** wybierz opcję **Wyświetl arkusz**.</span><span class="sxs-lookup"><span data-stu-id="e76da-139">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="e76da-140">Umożliwia wybranie transakcji, która jest częścią zwrotu.</span><span class="sxs-lookup"><span data-stu-id="e76da-140">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="e76da-141">Wybierz towary do zwrotu i wybierz metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="e76da-141">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="e76da-142">Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.</span><span class="sxs-lookup"><span data-stu-id="e76da-142">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="e76da-143">Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="e76da-143">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="e76da-144">Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.</span><span class="sxs-lookup"><span data-stu-id="e76da-144">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="e76da-145">— lub —</span><span class="sxs-lookup"><span data-stu-id="e76da-145">-or-</span></span>

1. <span data-ttu-id="e76da-146">Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.</span><span class="sxs-lookup"><span data-stu-id="e76da-146">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="e76da-147">Wybierz opcję **transakcja zwrotu** i wprowadź identyfikator paragonu przy użyciu skanowania kodu kreskowego lub za pomocą wpisu ręcznego.</span><span class="sxs-lookup"><span data-stu-id="e76da-147">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="e76da-148">Umożliwia wybranie transakcji, która jest częścią zwrotu.</span><span class="sxs-lookup"><span data-stu-id="e76da-148">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="e76da-149">Wybierz towary do zwrotu i wybierz metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="e76da-149">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="e76da-150">Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.</span><span class="sxs-lookup"><span data-stu-id="e76da-150">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="e76da-151">Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.</span><span class="sxs-lookup"><span data-stu-id="e76da-151">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="e76da-152">Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.</span><span class="sxs-lookup"><span data-stu-id="e76da-152">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="e76da-153">![Niedozwolone zwroty płatności](media/Return-policy-page6.png "Typ płatności zwrotu jest niedozwolony")</span><span class="sxs-lookup"><span data-stu-id="e76da-153">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="e76da-154">![Lista metod płatności](media/Return-policy-page5.PNG "Dozwolone typy płatności zwrotu")</span><span class="sxs-lookup"><span data-stu-id="e76da-154">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>
