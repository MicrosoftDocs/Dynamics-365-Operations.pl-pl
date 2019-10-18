---
title: Dodawanie kontrolki rekomendacji do ekranu transakcji na urządzeniach z aplikacją POS
description: W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 for Retail.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d646c8ba559ba3e8d2175911e76c57d25eff02ca
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278136"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a><span data-ttu-id="ce872-103">Dodawanie kontrolki rekomendacji do ekranu transakcji na urządzeniach z aplikacją POS</span><span class="sxs-lookup"><span data-stu-id="ce872-103">Add a recommendations control to the transaction screen on POS devices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="ce872-104">W tym temacie opisano sposób dodawania kontrolki rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="ce872-104">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="ce872-105">Aby uzyskać więcej informacji na temat zaleceń dotyczących produktów, zapoznaj się z [zaleceniami dotyczącymi produktów w dokumentacji punktu sprzedaży.](product.md)</span><span class="sxs-lookup"><span data-stu-id="ce872-105">For more information about product recommendations, read the  [product recommendations on POS documentation.](product.md)</span></span>


<span data-ttu-id="ce872-106">Rekomendacje produktów mogą być wyświetlane na urządzeniu punktu sprzedaży podczas używania Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="ce872-106">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 Retail.</span></span> <span data-ttu-id="ce872-107">Aby wyświetlać rekomendacje produktów, należy za pomocą projektanta układu ekranu dodać formant do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="ce872-107">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span> 

## <a name="open-layout-designer"></a><span data-ttu-id="ce872-108">Otwieranie projektanta układu</span><span class="sxs-lookup"><span data-stu-id="ce872-108">Open Layout designer</span></span>

1. <span data-ttu-id="ce872-109">Wybierz kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Punkt sprzedaży** &gt; **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="ce872-109">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2. <span data-ttu-id="ce872-110">Za pomocą szybkiego filtru znajdź ekran, do którego chcesz dodać formant.</span><span class="sxs-lookup"><span data-stu-id="ce872-110">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="ce872-111">Na przykład wyfiltruj według pola **Identyfikator układu ekranu**, używając wartości **F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="ce872-111">For example, filter on the **Screen layout ID** field using a value of **F2CP16:9M**.</span></span>
3. <span data-ttu-id="ce872-112">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="ce872-112">In the list, find and select the desired record.</span></span> <span data-ttu-id="ce872-113">Na przykład zaznacz pozycję **Nazwa: F2CP16:9M Identyfikator układu ekranu: F2CP16:9M**.</span><span class="sxs-lookup"><span data-stu-id="ce872-113">For example, select **Name: F2CP16:9M Screen Layout ID: F2CP16:9M**.</span></span>
4. <span data-ttu-id="ce872-114">Kliknij opcję **Projektant układu**.</span><span class="sxs-lookup"><span data-stu-id="ce872-114">Click **Layout designer**.</span></span>
5. <span data-ttu-id="ce872-115">Postępuj zgodnie z instrukcjami, aby uruchomić projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="ce872-115">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="ce872-116">Gdy zostanie wyświetlony monit o poświadczeniach, wpisz te same poświadczenia, które były używane przy uruchamianiu projektanta układu ze strony **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="ce872-116">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6. <span data-ttu-id="ce872-117">Po zalogowaniu się zobaczysz stronę podobną do przedstawionej poniżej.</span><span class="sxs-lookup"><span data-stu-id="ce872-117">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="ce872-118">Układ może się różnić w zależności od dostosowań wprowadzonych dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="ce872-118">The layout will be different depending on the customizations that were made for your store.</span></span>


    <span data-ttu-id="ce872-119">[![Projektant układu](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span><span class="sxs-lookup"><span data-stu-id="ce872-119">[![Layout designer](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)</span></span>

## <a name="choose-a-display-option"></a><span data-ttu-id="ce872-120">Wybierz opcję wyświetlaną</span><span class="sxs-lookup"><span data-stu-id="ce872-120">Choose a display option</span></span>

<span data-ttu-id="ce872-121">Dostępne są dwie opcje konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ce872-121">There are two configurations options available.</span></span> <span data-ttu-id="ce872-122">Wybierz opcję, która sprawdza się najlepiej dla Twojego sklepu, a następnie postępuj zgodnie z pozostałymi instrukcjami, aby dokończyć konfigurowanie formantu.</span><span class="sxs-lookup"><span data-stu-id="ce872-122">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="ce872-123">Oto te opcje:</span><span class="sxs-lookup"><span data-stu-id="ce872-123">The two options are:</span></span>

- <span data-ttu-id="ce872-124">Rekomendacje są zawsze widoczne.</span><span class="sxs-lookup"><span data-stu-id="ce872-124">Recommendations are always visible.</span></span>
- <span data-ttu-id="ce872-125">W siatce po prawej stronie ekranu jest wyświetlana karta **Zalecenia**.</span><span class="sxs-lookup"><span data-stu-id="ce872-125">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

### <a name="make-recommendations-always-visible"></a><span data-ttu-id="ce872-126">Rekomendacje zawsze widoczne</span><span class="sxs-lookup"><span data-stu-id="ce872-126">Make recommendations always visible</span></span>


1. <span data-ttu-id="ce872-127">Zmniejsz wysokość obszaru szczegółów wierszy transakcji, tak aby była taka sama, jak wysokość panelu odbiorcy po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="ce872-127">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.</span></span>


    <span data-ttu-id="ce872-128">[![Zmniejszona wysokość obszaru szczegółów wierszy transakcji](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="ce872-128">[![Height of the transaction lines details area reduced](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>

2. <span data-ttu-id="ce872-129">Z menu po lewej stronie przeciągnij formant rekomendacji i upuść go między obszar szczegółów wierszy transakcji a siatkę przycisków na środku w dolnej części ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="ce872-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="ce872-130">Zmień rozmiar formantu, tak aby mieścił się w tej przestrzeni.</span><span class="sxs-lookup"><span data-stu-id="ce872-130">Resize the control so it fits in that space.</span></span>

    <span data-ttu-id="ce872-131">[![Formant rekomendacji dodany do układu](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="ce872-131">[![Recommendations control added to the layout](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>


3. <span data-ttu-id="ce872-132">Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="ce872-132">Click the **X** to save and exit Layout designer.</span></span>
4. <span data-ttu-id="ce872-133">W programie Dynamics 365 for Retail wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogramy dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="ce872-133">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5. <span data-ttu-id="ce872-134">Na liście zaznacz pozycję **1090 Kasy**.</span><span class="sxs-lookup"><span data-stu-id="ce872-134">In the list, select **1090 Registers**.</span></span>
6. <span data-ttu-id="ce872-135">Kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="ce872-135">Click **Run now**.</span></span>


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="ce872-136">Dodawanie karty Zalecenia do siatki przycisków po prawej stronie ekranu</span><span class="sxs-lookup"><span data-stu-id="ce872-136">Add a Recommendations tab to the button grid on the right side of the screen</span></span>

1. <span data-ttu-id="ce872-137">Kliknij prawym przyciskiem myszy puste miejsce pod ostatnią kartą w siatce przycisków umieszczoną z prawej strony ekranu.</span><span class="sxs-lookup"><span data-stu-id="ce872-137">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>

2. <span data-ttu-id="ce872-138">Kliknij **Dostosuj**.</span><span class="sxs-lookup"><span data-stu-id="ce872-138">Click **Customize**.</span></span>

    <span data-ttu-id="ce872-139">[![Dostosowywanie — okno dialogowe Formant karty](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="ce872-139">[![Customization - Tab control dialog box](./media/pic-5.png)](./media/pic-5.png)</span></span>

3. <span data-ttu-id="ce872-140">Kliknij opcję **Nowa karta**.</span><span class="sxs-lookup"><span data-stu-id="ce872-140">Click **New tab**.</span></span>
4. <span data-ttu-id="ce872-141">Znajdź nową kartę, który została właśnie dodana.</span><span class="sxs-lookup"><span data-stu-id="ce872-141">Find the new tab that you just added.</span></span> <span data-ttu-id="ce872-142">Może być konieczne przewinięcie w dół.</span><span class="sxs-lookup"><span data-stu-id="ce872-142">You may need to scroll down.</span></span>
5. <span data-ttu-id="ce872-143">Na liście rozwijanej **Zawartość** wybierz opcję **Rekomendowane produkty**.</span><span class="sxs-lookup"><span data-stu-id="ce872-143">In the **Contents** drop-down, select **Recommended products**.</span></span>

    <span data-ttu-id="ce872-144">[![Wybieranie Rekomendowanych produktów w polu Zawartość](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="ce872-144">[![Selecting Recommended products in the Contents field](./media/pic-6.png)](./media/pic-6.png)</span></span>

6. <span data-ttu-id="ce872-145">W polu **Etykieta** wpisz nazwę karty rekomendacji. Na przykład wpisz „Zalecane produkty”.</span><span class="sxs-lookup"><span data-stu-id="ce872-145">In the **Label** field, type a name for the recommendations tab. For example, type 'Recommended products'.</span></span>
7. <span data-ttu-id="ce872-146">W polu **Obraz** zaznacz ilustrację, która ma być wyświetlana na karcie.</span><span class="sxs-lookup"><span data-stu-id="ce872-146">In the **Image** field, select the image to appear on the tab.</span></span>
8. <span data-ttu-id="ce872-147">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce872-147">Click **OK**.</span></span> <span data-ttu-id="ce872-148">Nowa karta zostanie wyświetlone w siatce przycisków.</span><span class="sxs-lookup"><span data-stu-id="ce872-148">The new tab appears in the button grid.</span></span>
9. <span data-ttu-id="ce872-149">Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="ce872-149">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="ce872-150">W programie Dynamics 365 for Retail wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogramy dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="ce872-150">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="ce872-151">Na liście zaznacz pozycję **1090 Kasy**.</span><span class="sxs-lookup"><span data-stu-id="ce872-151">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="ce872-152">Kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="ce872-152">Click **Run now**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ce872-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ce872-153">Additional resources</span></span>

[<span data-ttu-id="ce872-154">rekomendacje produktów w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ce872-154">product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="ce872-155">przegląd rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="ce872-155">product recommendations overview</span></span>](../commerce/product-recommendations.md)
