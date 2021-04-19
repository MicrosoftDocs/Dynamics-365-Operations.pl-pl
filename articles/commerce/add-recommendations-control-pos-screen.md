---
title: Dodawanie rekomendacji do ekranu transakcji
description: W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 38099909f169391c17760ac381af07f0848fc384
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797486"
---
# <a name="add-recommendations-to-the-transaction-screen"></a><span data-ttu-id="a0a84-103">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="a0a84-103">Add recommendations to the transaction screen</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="a0a84-104">W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a0a84-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="a0a84-105">Aby uzyskać więcej informacji na temat zaleceń dotyczących produktów, zapoznaj się z [zaleceniami dotyczącymi produktów w dokumentacji punktu sprzedaży](product.md).</span><span class="sxs-lookup"><span data-stu-id="a0a84-105">For more information about product recommendations, read the  [product recommendations on POS documentation](product.md).</span></span>


<span data-ttu-id="a0a84-106">Rekomendacje produktów mogą być wyświetlane na urządzeniu punktu sprzedaży podczas używania Commerce.</span><span class="sxs-lookup"><span data-stu-id="a0a84-106">You can display product recommendations on your POS device when you use Commerce.</span></span> <span data-ttu-id="a0a84-107">Aby wyświetlać rekomendacje produktów, należy za pomocą projektanta układu ekranu dodać formant do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="a0a84-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="a0a84-108">Otwieranie projektanta układu</span><span class="sxs-lookup"><span data-stu-id="a0a84-108">Open Layout designer</span></span>

1. <span data-ttu-id="a0a84-109">Wybierz kolejno opcje **Retail i Commerce** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Punkt sprzedaży** &gt; **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-109">Go to **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="a0a84-110">Za pomocą szybkiego filtru znajdź ekran, do którego chcesz dodać formant.</span><span class="sxs-lookup"><span data-stu-id="a0a84-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="a0a84-111">Na przykład wyfiltruj według pola **Identyfikator układu ekranu**, używając wartości **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="a0a84-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="a0a84-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="a0a84-113">Na przykład zaznacz pozycję **Nazwa: F2CP16:9M Identyfikator układu ekranu: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="a0a84-114">Kliknij opcję **Projektant układu**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="a0a84-115">Postępuj zgodnie z instrukcjami, aby uruchomić projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="a0a84-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="a0a84-116">Gdy zostanie wyświetlony monit o poświadczeniach, wpisz te same poświadczenia, które były używane przy uruchamianiu projektanta układu ze strony **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="a0a84-117">Po zalogowaniu się zobaczysz stronę podobną do przedstawionej poniżej.</span><span class="sxs-lookup"><span data-stu-id="a0a84-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="a0a84-118">Układ może się różnić w zależności od dostosowań wprowadzonych dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="a0a84-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="a0a84-119">[![Projektant układu](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="a0a84-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="a0a84-120">Wybierz opcję wyświetlaną</span><span class="sxs-lookup"><span data-stu-id="a0a84-120">Choose a display option</span></span>

<span data-ttu-id="a0a84-121">Dostępne są dwie opcje konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a0a84-121">There are two configurations options available.</span></span> <span data-ttu-id="a0a84-122">Wybierz opcję, która sprawdza się najlepiej dla Twojego sklepu, a następnie postępuj zgodnie z pozostałymi instrukcjami, aby dokończyć konfigurowanie formantu.</span><span class="sxs-lookup"><span data-stu-id="a0a84-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="a0a84-123">Oto te opcje:</span><span class="sxs-lookup"><span data-stu-id="a0a84-123">The two options are:</span></span>

- <span data-ttu-id="a0a84-124">Rekomendacje są zawsze widoczne.</span><span class="sxs-lookup"><span data-stu-id="a0a84-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="a0a84-125">W siatce po prawej stronie ekranu jest wyświetlana karta **Zalecenia**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="a0a84-126">Rekomendacje zawsze widoczne</span><span class="sxs-lookup"><span data-stu-id="a0a84-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="a0a84-127">Zmniejsz wysokość obszaru szczegółów wierszy transakcji, tak aby była taka sama, jak wysokość panelu odbiorcy po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="a0a84-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="a0a84-128">[![Zmniejszona wysokość obszaru szczegółów wierszy transakcji](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="a0a84-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="a0a84-129">Z menu po lewej stronie przeciągnij formant rekomendacji i upuść go między obszar szczegółów wierszy transakcji a siatkę przycisków na środku w dolnej części ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="a0a84-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="a0a84-130">Zmień rozmiar formantu, tak aby mieścił się w tej przestrzeni.</span><span class="sxs-lookup"><span data-stu-id="a0a84-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="a0a84-131">[![Formant rekomendacji dodany do układu](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="a0a84-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="a0a84-132">Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="a0a84-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="a0a84-133">W Commerce wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sprzedaży** &gt; **Harmonogramy dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-133">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="a0a84-134">Na liście zaznacz pozycję **1090 Kasy**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="a0a84-135">Kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="a0a84-136">Dodawanie karty Zalecenia do siatki przycisków po prawej stronie ekranu</span><span class="sxs-lookup"><span data-stu-id="a0a84-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="a0a84-137">Kliknij prawym przyciskiem myszy puste miejsce pod ostatnią kartą w siatce przycisków umieszczoną z prawej strony ekranu.</span><span class="sxs-lookup"><span data-stu-id="a0a84-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="a0a84-138">Kliknij **Dostosuj**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-138">Click **Customize**.</span></span>

    <span data-ttu-id="a0a84-139">[![Dostosowywanie — okno dialogowe Formant karty](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="a0a84-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="a0a84-140">Kliknij opcję **Nowa karta**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-140">Click **New tab**.</span></span>
4. <span data-ttu-id="a0a84-141">Znajdź nową kartę, który została właśnie dodana.</span><span class="sxs-lookup"><span data-stu-id="a0a84-141">Find the new tab that you just added.</span></span> <span data-ttu-id="a0a84-142">Może być konieczne przewinięcie w dół.</span><span class="sxs-lookup"><span data-stu-id="a0a84-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="a0a84-143">Na liście rozwijanej **Zawartość** wybierz opcję **Rekomendowane produkty**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="a0a84-144">[![Wybieranie Rekomendowanych produktów w polu Zawartość](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="a0a84-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="a0a84-145">W polu **Etykieta** wpisz nazwę karty rekomendacji. Na przykład wpisz „Zalecane produkty”.</span><span class="sxs-lookup"><span data-stu-id="a0a84-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="a0a84-146">W polu **Obraz** zaznacz ilustrację, która ma być wyświetlana na karcie.</span><span class="sxs-lookup"><span data-stu-id="a0a84-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="a0a84-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-147">Click **OK**.</span></span> <span data-ttu-id="a0a84-148">Nowa karta zostanie wyświetlone w siatce przycisków.</span><span class="sxs-lookup"><span data-stu-id="a0a84-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="a0a84-149">Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="a0a84-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="a0a84-150">W Commerce wybierz kolejno opcje **Handel detaliczny i inny** &gt; **Dane IT sprzedaży** &gt; **Harmonogramy dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-150">In Commerce, go to **Retail and Commerce** &gt; **Retail and Commerce IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="a0a84-151">Na liście zaznacz pozycję **1090 Kasy**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="a0a84-152">Kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="a0a84-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a0a84-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a0a84-153">Additional resources</span></span>

[<span data-ttu-id="a0a84-154">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="a0a84-154">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="a0a84-155">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a0a84-155">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="a0a84-156">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="a0a84-156">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="a0a84-157">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="a0a84-157">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="a0a84-158">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="a0a84-158">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="a0a84-159">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="a0a84-159">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="a0a84-160">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a0a84-160">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="a0a84-161">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="a0a84-161">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="a0a84-162">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="a0a84-162">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="a0a84-163">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="a0a84-163">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="a0a84-164">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="a0a84-164">Product recommendations FAQ</span></span>](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]