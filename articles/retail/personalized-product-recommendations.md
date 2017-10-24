---
title: "Omówienie spersonalizowanych rekomendacji produktów"
description: "W programie Dynamics 365 for Retail rekomendacje produktów mogą być wyświetlane na urządzenia w punkcie sprzedaży (POS). Rekomendacje to towary, którymi odbiorca może być zainteresowany w związku z wcześniej dokonywanymi zakupami, towary na liście życzeń odbiorcy oraz towary, które inni podobni odbiorcy kupowali w sklepach internetowych i tradycyjnych. U sprzedawców detalicznych z dużymi katalogami rekomendacje pomagają odbiorcom znajdować ciekawe inne produkty. Eksponując produkty ukierunkowane na zainteresowania i nawyki zakupowe odbiorców, rekomendacje produktów mogą pomóc sprzedawać powiązane i dodatkowe produkty oraz wzmacniać lojalność odbiorców. W programie Dynamics 365 for Retail funkcjonalność rekomendacji produktów bazuje na usługach Cognitive Services i aparacie uczenia maszynowego Microsoft Azure."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d727718442f94a2a78a3864741e93439d7c36473
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="personalized-product-recommendations-overview"></a><span data-ttu-id="e3ef4-107">Omówienie spersonalizowanych rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="e3ef4-107">Personalized product recommendations overview</span></span>

[!include[banner](includes/banner.md)]


> [!NOTE]
> <span data-ttu-id="e3ef4-108">Ta funkcja jest obecnie dostępna tylko w topologii wdrażania piaskownicy i produkcji (wysoka dostępność).</span><span class="sxs-lookup"><span data-stu-id="e3ef4-108">This feature is currently available on sandbox and production (high-availability) deployment topologies only.</span></span> 

<span data-ttu-id="e3ef4-109">W programie Dynamics 365 for Retail rekomendacje produktów mogą być wyświetlane na urządzenia w punkcie sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="e3ef4-109">In Dynamics 365 for Retail, product recommendations can be displayed on the point of sale (POS) device.</span></span> <span data-ttu-id="e3ef4-110">Rekomendacje to towary, którymi odbiorca może być zainteresowany w związku z wcześniej dokonywanymi zakupami, towary na liście życzeń odbiorcy oraz towary, które inni podobni odbiorcy kupowali w sklepach internetowych i tradycyjnych.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-110">The recommendations are items that the customer might be interested in based on their purchase history, items in their wish list, and items that other customers purchased online and in brick-and-mortar stores.</span></span> <span data-ttu-id="e3ef4-111">U sprzedawców detalicznych z dużymi katalogami rekomendacje pomagają odbiorcom znajdować ciekawe inne produkty.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-111">For retailers with large catalogs, recommendations help the customer with product discovery.</span></span> <span data-ttu-id="e3ef4-112">Eksponując produkty ukierunkowane na zainteresowania i nawyki zakupowe odbiorców, rekomendacje produktów mogą pomóc sprzedawać powiązane i dodatkowe produkty oraz wzmacniać lojalność odbiorców.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-112">By showcasing products targeted to a customer’s interests and buying habits, product recommendations can help retailers with up-sell and cross-sell, and can enhance customer retention.</span></span> <span data-ttu-id="e3ef4-113">W programie Dynamics 365 for Retail funkcjonalność rekomendacji produktów bazuje na usługach Cognitive Services i aparacie uczenia maszynowego Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-113">In Dynamics 365 for Retail, product recommendations are powered by cognitive services and Microsoft Azure machine learning.</span></span>


<a name="scenarios"></a><span data-ttu-id="e3ef4-114">Scenariusze</span><span class="sxs-lookup"><span data-stu-id="e3ef4-114">Scenarios</span></span>
---------

<span data-ttu-id="e3ef4-115">Rekomendacje produktów działają w opisanych niżej scenariuszach w punkcie sprzedaż.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-115">Product recommendations are enabled for the following POS scenarios.</span></span> <span data-ttu-id="e3ef4-116">Są dostępne dla aplikacji Cloud POS i Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="e3ef4-116">They are available in Cloud POS or Modern POS (MPOS).</span></span>

1.  <span data-ttu-id="e3ef4-117">Na stronie **Szczegóły produktu**:</span><span class="sxs-lookup"><span data-stu-id="e3ef4-117">On the **Product details** page:</span></span>

-   <span data-ttu-id="e3ef4-118">Jeśli pracownik sklepu otworzy stronę **Szczegóły produktu** podczas oglądania wcześniejszych transakcji w różnych kanałach, aparat rekomendacji proponuje dodatkowe towary, które inni odbiorcy często kupowali razem z analizowanym produktem.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-118">If a store associate visits a **Product details** page when looking at previous transactions across different channels, the recommendation engine suggests additional items that are likely to be purchased together.</span></span>
-   <span data-ttu-id="e3ef4-119">Jeśli pracownik sklepu doda odbiorcę do transakcji, a następnie otworzy stronę **Szczegóły produktu**, aparat rekomendacji przedstawi spersonalizowane zalecenia na podstawie historii transakcji odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-119">If the store associate adds a customer to the transaction and then visits a **Product details** page, the recommendation engine provides personalized recommendations using the customer's transaction history.</span></span>

<span data-ttu-id="e3ef4-120">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span><span class="sxs-lookup"><span data-stu-id="e3ef4-120">[![proddetails](./media/proddetails.png)](./media/proddetails.png)</span></span>

2.  <span data-ttu-id="e3ef4-121">Na stronie **Transakcja**:</span><span class="sxs-lookup"><span data-stu-id="e3ef4-121">On the **Transaction** page:</span></span>

-   <span data-ttu-id="e3ef4-122">Aparat rekomendacji proponuje towary na podstawie całej listy towarów w koszyku.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-122">The recommendation engine suggests items based on the entire list of items in the basket.</span></span>
-   <span data-ttu-id="e3ef4-123">Jeśli pracownik sklepu doda odbiorcę do transakcji, aparat rekomendacji przedstawi spersonalizowane zalecenia na podstawie historii transakcji odbiorcy oraz listy towarów w koszyku.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-123">If the store associate adds a customer to the transaction, the recommendation engine provides personal recommendations using the customer’s transaction history and the list of items in the basket.</span></span>

> [!NOTE]
> <span data-ttu-id="e3ef4-124">Aby rekomendacje były wyświetlane na stronie **Transakcja**, sprzedawca detaliczny musi zaktualizować układ ekranu w programie Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-124">To display recommendations on the **Transaction** page, the retailer needs to update the screen layout in Dynamics 365 for Retail.</span></span> <span data-ttu-id="e3ef4-125">Formant **Zalecenia** należy upuścić na stronę **Transakcja**.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-125">The **Recommendations** control must be dropped on to the **Transaction** page.</span></span> <span data-ttu-id="e3ef4-126">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span><span class="sxs-lookup"><span data-stu-id="e3ef4-126">[![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)</span></span>

3.  <span data-ttu-id="e3ef4-127">Na stronie **Szczegóły odbiorcy**:</span><span class="sxs-lookup"><span data-stu-id="e3ef4-127">On the **Customer details** page:</span></span>
    -   <span data-ttu-id="e3ef4-128">Aparat rekomendacji proponuje towary na podstawie identyfikatora użytkownika oraz towarów na liście życzeń odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-128">The recommendation engine suggests items based on the user ID and items in the customer’s wish list.</span></span>

<span data-ttu-id="e3ef4-129">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span><span class="sxs-lookup"><span data-stu-id="e3ef4-129">[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)</span></span>

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a><span data-ttu-id="e3ef4-130">Konfigurowanie programu Dynamics 365 for Retail do wyświetlania rekomendacji w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e3ef4-130">Configure Dynamics 365 for Retail to enable POS recommendations</span></span>
<span data-ttu-id="e3ef4-131">Aby skonfigurować rekomendowanie produktów, należy wykonać poniższe czynności:</span><span class="sxs-lookup"><span data-stu-id="e3ef4-131">To set up product recommendations, you need to do the following.</span></span>

1.  <span data-ttu-id="e3ef4-132">Upewnij się, że wybrano poprawną wartość **Firmy**.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-132">Make sure that you have selected the correct **Legal entity**.</span></span>
2.  <span data-ttu-id="e3ef4-133">Przejdź do okna **Magazyn jednostek**, wybierz opcję **Sprzedaż detaliczna**, a następnie kliknij przycisk **Odśwież**. Spowoduje to użycie danych demonstracyjnych (lub faktycznych danych firmy) z operacyjnej bazy danych i przeniesienie ich do magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-133">Navigate to **Entity store**, select **Retail sales**, and then click **Refresh**.This will use the demo data (or your data) from your operational database and move it to Entity store.</span></span>
3.  <span data-ttu-id="e3ef4-134">Opcjonalnie: Aby wyświetlać rekomendacje na ekranie transakcji, przejdź do okna **Układ ekranu**, wybierz układ ekranu, uruchom narzędzie **Projektant układu ekranu**, a następnie upuść formant **rekomendacji** w żądanym miejscu.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-134">Optional: To display recommendations on the transaction screen, go to **Screen Layout**, choose your screen layout, launch the **Screen layout designer**,and then drop the **recommendations** control where needed.</span></span>
4.  <span data-ttu-id="e3ef4-135">Przejdź do okna **Parametry sieci sprzedaży**, wybierz opcję **Uczenie maszynowe** i w ustawieniu **Włącz rekomendacje w punkcie sprzedaży** wybierz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-135">Go to **Retail parameters**, select **Machine-learning**, select **Yes** under **Enable POS recommendations**.</span></span>
5.  <span data-ttu-id="e3ef4-136">Aby rekomendacje były wyświetlane w punkcie sprzedaży, uruchom zadanie konfiguracji globalnej **1110**.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-136">To see recommendations on POS, run global configuration job **1110**.</span></span> <span data-ttu-id="e3ef4-137">Aby pokazywać zmiany wprowadzone w projektancie układu ekranu punktu sprzedaży, uruchom zadanie konfiguracji kanału **1070**.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-137">To reflect changes made to POS screen layout designer, run channel configuration job **1070**.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="e3ef4-138">[]()Jak to działa?</span><span class="sxs-lookup"><span data-stu-id="e3ef4-138">[]()How does it work?</span></span>
<span data-ttu-id="e3ef4-139">Gdy odświeżasz jednostkę **Magazyn jednostek**, są wykonywane następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e3ef4-139">When you refresh the **Entity store** entity, the following actions take place.</span></span>

-   <span data-ttu-id="e3ef4-140">Dane w formacie wymaganym przez usługi Cognitive Services są wyodrębniane z operacyjnej bazy danych programu Dynamics 365 for Retail i wysyłane do magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-140">Data in the format required by the Cognitive services is extracted from the Dynamics 365 for Retail operational database and sent to the Entity store.</span></span>
-   <span data-ttu-id="e3ef4-141">Dane są wykorzystywane przez Fabrykę danych Azure (ADF) do czyszczenia danych przy użyciu skryptów gałęzi w ramach działań usługi ADF.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-141">The data is used by Azure Data Factory (ADF) to cleanse the data using Hive scripts as part of ADF activities.</span></span> <span data-ttu-id="e3ef4-142">Oczyszczoną dane są umieszczane w magazynie obiektów blob.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-142">Cleansed data is stored in blob storage.</span></span>
-   <span data-ttu-id="e3ef4-143">Dane z magazynu obiektów blob są używane przez interfejs API usług Cognitive Services do uczenia modelu rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-143">Data from blob storage is used by the Cognitive services API to train a recommendation model.</span></span>

<span data-ttu-id="e3ef4-144">Po włączeniu opcji **Włącz rekomendacje** i uruchomieniu zadań konfiguracji zostaną wykonane następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e3ef4-144">When you turn on **Enable recommendations** and run the configuration jobs, the following actions take place.</span></span>

-   <span data-ttu-id="e3ef4-145">Poświadczenia i identyfikator modelu są pobierane z interfejsu API i umieszczane w operacyjnej bazie danych programu Dynamics 365 for Retail, w pliku web.config serwera AOS, a także na serwerze sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-145">Model credentials and ID are picked up from the API and stored in the Dynamics 365 for Retail operational database, in the web.config for AOS, and also in the retail server.</span></span>
-   <span data-ttu-id="e3ef4-146">Poświadczenia i identyfikator modelu są udostępniane środowisku CRT, co umożliwia obsługę wywołań o rekomendacje produktów z aplikacji Cloud POS i MPOS w trybie online.</span><span class="sxs-lookup"><span data-stu-id="e3ef4-146">Model credentials and ID are made available to CRT so that calls for product recommendations from Cloud POS and MPOS in online mode can be honored.</span></span>


<a name="see-also"></a><span data-ttu-id="e3ef4-147">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e3ef4-147">See also</span></span>
--------

[<span data-ttu-id="e3ef4-148">Dodawanie formantu rekomendacji do strony transakcji na urządzeniu punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="e3ef4-148">Add a recommendations control to the transaction page on a POS device</span></span>](add-recommendations-control-pos-screen.md)




