---
title: "Dodawanie formantu rekomendacji do strony transakcji na urządzeniu punktu sprzedaży"
description: "W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: aa7d1e5392e4d3fa86bf62943cb4f5b5f4c7b383
ms.contentlocale: pl-pl
ms.lasthandoff: 04/13/2018

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a><span data-ttu-id="bd3ea-103">Dodawanie formantu rekomendacji do strony transakcji na urządzeniu punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="bd3ea-103">Add a recommendations control to the transaction page on a POS device</span></span>

[!INCLUDE [banner](includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="bd3ea-104">Usuwamy obecną wersję usługi rekomendowania produktów, ponieważ w nowej wersji wprowadzamy lepszy algorytm i nowsze funkcje zorientowane na handel detaliczny.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-104">We are removing the current version of the product recommendation service as we redesign this feature with a better algorithm and newer retail-oriented capabilities.</span></span> <span data-ttu-id="bd3ea-105">Aby uzyskać więcej informacji, zobacz [Usunięte i przestarzałe funkcje](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span><span class="sxs-lookup"><span data-stu-id="bd3ea-105">For more information see [Removed or deprecated features](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).</span></span> 

<span data-ttu-id="bd3ea-106">W tym temacie opisano sposób dodawania formantu rekomendacji do ekranu transakcji na urządzeniu w punkcie sprzedaży (POS) przy użyciu projektanta układu ekranu w programie Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-106">This topic describes how to add a recommendations control to the transaction screen on a point of sale (POS) device using the screen layout designer in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="bd3ea-107">Rekomendacje produktów mogą być wyświetlane na urządzeniu punktu sprzedaży podczas używania programu Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-107">You can display product recommendations on your POS device when you use Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="bd3ea-108">*Rekomendacje* to towary, którymi odbiorca może być zainteresowany w związku z wcześniej dokonywanymi zakupami, towary na liście życzeń odbiorcy oraz towary, które inni podobni odbiorcy kupowali w sklepach internetowych i tradycyjnych.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-108">*Recommendations* are items that your customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="bd3ea-109">Aby wyświetlać rekomendacje produktów, należy za pomocą projektanta układu ekranu dodać formant do ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-109">To display product recommendations, you need to add a control to the transaction screen using the screen layout designer.</span></span>

## <a name="open-layout-designer"></a><span data-ttu-id="bd3ea-110">Otwieranie projektanta układu</span><span class="sxs-lookup"><span data-stu-id="bd3ea-110">Open Layout designer</span></span>
1.  <span data-ttu-id="bd3ea-111">Wybierz kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Punkt sprzedaży** &gt; **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-111">Go to **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Screen layouts**.</span></span>
2.  <span data-ttu-id="bd3ea-112">Za pomocą szybkiego filtru znajdź ekran, do którego chcesz dodać formant.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-112">Use the Quick Filter to find the screen that you want to add the control to.</span></span> <span data-ttu-id="bd3ea-113">Na przykład wyfiltruj według pola **Identyfikator układu ekranu**, używając wartości „F2CP16:9M”.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-113">For example, filter on the **Screen layout ID** field using a value of ‘F2CP16:9M’.</span></span>
3.  <span data-ttu-id="bd3ea-114">Na liście znajdź i zaznacz odpowiedni rekord.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-114">In the list, find and select the desired record.</span></span> <span data-ttu-id="bd3ea-115">Na przykład zaznacz pozycję „Nazwa: F2CP16:9M Identyfikator układu ekranu: F2CP16:9M”.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-115">For example, select ‘Name: F2CP16:9M Screen Layout ID: F2CP16:9M’.</span></span>
4.  <span data-ttu-id="bd3ea-116">Kliknij opcję **Projektant układu**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-116">Click **Layout designer**.</span></span>
5.  <span data-ttu-id="bd3ea-117">Postępuj zgodnie z instrukcjami, aby uruchomić projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-117">Follow the prompts to launch the layout designer.</span></span> <span data-ttu-id="bd3ea-118">Gdy zostanie wyświetlony monit o poświadczenia, wpisz te same poświadczenia, które były używane przy uruchamianiu konstruktora układu ze strony **Układy ekranu**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-118">When prompted for credentials, enter the same credentials that were in use when the Layout designer was launched from **Screen layouts** page.</span></span>
6.  <span data-ttu-id="bd3ea-119">Po zalogowaniu się zobaczysz stronę podobną do przedstawionej poniżej.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-119">When you log in, a page similar to the one below appears.</span></span> <span data-ttu-id="bd3ea-120">Układ może się różnić w zależności od dostosowań wprowadzonych dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-120">The layout will be different depending on the customizations that were made for your store.</span></span>

<span data-ttu-id="bd3ea-121">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Wybieranie opcji wyświetlania</span><span class="sxs-lookup"><span data-stu-id="bd3ea-121">[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Choose a display option</span></span>
-----------------------

<span data-ttu-id="bd3ea-122">Dostępne są dwie opcje konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-122">There are two configurations options available.</span></span> <span data-ttu-id="bd3ea-123">Wybierz opcję, która sprawdza się najlepiej dla Twojego sklepu, a następnie postępuj zgodnie z pozostałymi instrukcjami, aby dokończyć konfigurowanie formantu.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-123">Choose the option that works best for your store, and follow the remaining instructions to finish setting up the control.</span></span> <span data-ttu-id="bd3ea-124">Oto te opcje:</span><span class="sxs-lookup"><span data-stu-id="bd3ea-124">The two options are:</span></span>
-   <span data-ttu-id="bd3ea-125">Rekomendacje są zawsze widoczne.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-125">Recommendations are always visible.</span></span>
-   <span data-ttu-id="bd3ea-126">W siatce po prawej stronie ekranu jest wyświetlana karta **Zalecenia**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-126">A **Recommendations** tab appears in the grid on the right side of the screen.</span></span>

#### <a name="to-make-recommendations-always-visible"></a><span data-ttu-id="bd3ea-127">Aby rekomendacje były zawsze widoczne</span><span class="sxs-lookup"><span data-stu-id="bd3ea-127">To make recommendations always visible</span></span>

1.  <span data-ttu-id="bd3ea-128">Zmniejsz wysokość obszaru szczegółów wierszy transakcji, tak aby była taka sama, jak wysokość panelu odbiorcy po lewej stronie.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span><span class="sxs-lookup"><span data-stu-id="bd3ea-128">Reduce the height of the transaction lines details area so that it is the same height as the customer panel to its left.[](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)</span></span>
2.  <span data-ttu-id="bd3ea-129">Z menu po lewej stronie przeciągnij formant rekomendacji i upuść go między obszar szczegółów wierszy transakcji a siatkę przycisków na środku w dolnej części ekranu transakcji.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-129">From the menu on the left, drag and drop the recommendations control to between the transaction line details area and the button grid in the center bottom of the transaction screen.</span></span> <span data-ttu-id="bd3ea-130">Zmień rozmiar formantu, tak aby mieścił się w tej przestrzeni.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span><span class="sxs-lookup"><span data-stu-id="bd3ea-130">Resize the control so it fits in that space.[](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)</span></span>
3.  <span data-ttu-id="bd3ea-131">Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-131">Click the **X** to save and exit Layout designer.</span></span>
4.  <span data-ttu-id="bd3ea-132">W programie Dynamics 365 for Retail wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogramy dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-132">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
5.  <span data-ttu-id="bd3ea-133">Na liście zaznacz pozycję **1090 Kasy**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-133">In the list, select **1090 Registers**.</span></span>
6.  <span data-ttu-id="bd3ea-134">Kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-134">Click **Run now**.</span></span>

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a><span data-ttu-id="bd3ea-135">Dodawanie karty Zalecenia do siatki przycisków po prawej stronie ekranu</span><span class="sxs-lookup"><span data-stu-id="bd3ea-135">To add a Recommendations tab to the button grid on the right side of the screen</span></span>

1.  <span data-ttu-id="bd3ea-136">Kliknij prawym przyciskiem myszy puste miejsce pod ostatnią kartą w siatce przycisków umieszczoną z prawej strony ekranu.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-136">Right-click in the empty space below the last tab on the button grid located on the right side of the page.</span></span>
2.  <span data-ttu-id="bd3ea-137">Kliknij przycisk **Dostosuj**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span><span class="sxs-lookup"><span data-stu-id="bd3ea-137">Click **Customize**.[![pic-5](./media/pic-5.png)](./media/pic-5.png)</span></span>
3.  <span data-ttu-id="bd3ea-138">Kliknij opcję **Nowa karta**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-138">Click **New tab**.</span></span>
4.  <span data-ttu-id="bd3ea-139">Znajdź nową kartę, który została właśnie dodana.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-139">Find the new tab that you just added.</span></span> <span data-ttu-id="bd3ea-140">Może być konieczne przewinięcie ekranu w dół.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-140">You may need to scroll down.</span></span>
5.  <span data-ttu-id="bd3ea-141">Na liście rozwijanej **Zawartość** wybierz opcję **Rekomendowane produkty**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-141">In the **Contents** drop-down, select **Recommended products**.</span></span> <span data-ttu-id="bd3ea-142">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span><span class="sxs-lookup"><span data-stu-id="bd3ea-142">[![pic-6](./media/pic-6.png)](./media/pic-6.png)</span></span>
6.  <span data-ttu-id="bd3ea-143">W polu **Etykieta** wpisz nazwę karty rekomendacji. Na przykład wpisz „Zalecane produkty”.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-143">In the **Label** field, type a name for the recommendations tab. For example, type ‘Recommended products’.</span></span>
7.  <span data-ttu-id="bd3ea-144">W polu **Obraz** zaznacz ilustrację, która ma być wyświetlana na karcie.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-144">In the **Image** field, select the image to appear on the tab.</span></span>
8.  <span data-ttu-id="bd3ea-145">Kliknij przycisk **OK**</span><span class="sxs-lookup"><span data-stu-id="bd3ea-145">Click **OK**.</span></span> <span data-ttu-id="bd3ea-146">Nowa karta zostanie wyświetlone w siatce przycisków.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-146">The new tab appears in the button grid.</span></span>
9.  <span data-ttu-id="bd3ea-147">Kliknij przycisk **X**, aby zapisać zmiany i zamknąć projektanta układu.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-147">Click the **X** to save and exit Layout designer.</span></span>
10. <span data-ttu-id="bd3ea-148">W programie Dynamics 365 for Retail wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogramy dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-148">In Dynamics 365 for Retail, go to **Retail** &gt; **Retail IT** &gt; **Distribution schedules**.</span></span>
11. <span data-ttu-id="bd3ea-149">Na liście zaznacz pozycję **1090 Kasy**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-149">In the list, select **1090 Registers**.</span></span>
12. <span data-ttu-id="bd3ea-150">Kliknij przycisk **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="bd3ea-150">Click **Run now**.</span></span>


<a name="see-also"></a><span data-ttu-id="bd3ea-151">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="bd3ea-151">See also</span></span>
--------

[<span data-ttu-id="bd3ea-152">Podstawowe informacje o spersonalizowanych rekomendacjach produktów</span><span class="sxs-lookup"><span data-stu-id="bd3ea-152">Personalized product recommendations overview</span></span>](personalized-product-recommendations.md)




