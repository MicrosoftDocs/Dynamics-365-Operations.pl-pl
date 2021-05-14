---
title: Konfigurowanie kanału online
description: W tym temacie opisano, jak dodać utworzyć nowy kanał online w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: f0f1e0f3e7145c66b8f2b082b44ad7035c57d947
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936951"
---
# <a name="set-up-an-online-channel"></a><span data-ttu-id="a3a5d-103">Konfigurowanie kanału online</span><span class="sxs-lookup"><span data-stu-id="a3a5d-103">Set up an online channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a3a5d-104">W tym temacie opisano, jak dodać utworzyć nowy kanał online w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-104">This topic describes how to create a new online channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a3a5d-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="a3a5d-105">Overview</span></span>

<span data-ttu-id="a3a5d-106">Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="a3a5d-107">Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="a3a5d-108">Sklepy internetowe dają klientom możliwość zakupu produktów w sklepie internetowym detalisty oprócz sklepów detalicznych.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-108">Online stores give customers the option of purchasing products from the retailer's online store in addition to its retail stores.</span></span>

<span data-ttu-id="a3a5d-109">Aby utworzyć sklep internetowy w systemie commerce, należy najpierw utworzyć kanał online.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-109">To create an online store in Commerce, you must first create an online channel.</span></span> <span data-ttu-id="a3a5d-110">Przed utworzeniem nowego kanału online, należy upewnić się, że zakończono [Konfigurowanie wstępnie wymaganych ustawień kanału](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-110">Before you create a new online channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

<span data-ttu-id="a3a5d-111">Aby można było utworzyć nową witrynę, w Commerce musi być utworzony co najmniej jeden sklep internetowy.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-111">Before you can create a new site, at least one online store must be created in Commerce.</span></span> <span data-ttu-id="a3a5d-112">Aby uzyskać więcej informacji, przejrzyj temat [Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-112">For more information, see [Create an e-Commerce site](create-ecommerce-site.md).</span></span>

## <a name="create-and-configure-a-new-online-channel"></a><span data-ttu-id="a3a5d-113">Utwórz i skonfiguruj nowy kanał online</span><span class="sxs-lookup"><span data-stu-id="a3a5d-113">Create and configure a new online channel</span></span>

<span data-ttu-id="a3a5d-114">Aby utworzyć i skonfigurować nowy kanał online, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-114">To create and configure a new online channel, follow these steps.</span></span>

1. <span data-ttu-id="a3a5d-115">W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Sklepy online**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-115">In the navigation pane, go to **Modules \> Channels \> Online Stores**.</span></span>
1. <span data-ttu-id="a3a5d-116">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-116">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a3a5d-117">W polu **Nazwa** wprowadź nazwę nowego kanału.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-117">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="a3a5d-118">Na liście rozwijanej **Firma** wprowadź odpowiednią firmę.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-118">In the **Legal entity** drop-down, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="a3a5d-119">Z listy rozwijanej **Magazyn** wybierz odpowiedni magazyn.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-119">In the **Warehouse** drop-down, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="a3a5d-120">W polu **Strefa czasowa sklepu** wybierz odpowiednią strefę czasową.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-120">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="a3a5d-121">W polu **Waluta** wybierz odpowiednią walutę.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="a3a5d-122">W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="a3a5d-123">W polu **Książka adresowa klienta** podaj prawidłową książkę adresową.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-123">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="a3a5d-124">W polu **Profil funkcji** wybierz profil funkcji, jeśli ma to zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="a3a5d-125">W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="a3a5d-126">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a3a5d-127">Poniższy rysunek przedstawia utworzenie nowego kanału online.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-127">The following image shows the creation of a new online channel.</span></span>

![Nowy kanał online](media/channel-setup-online-1.png)

<span data-ttu-id="a3a5d-129">Poniższy obraz przedstawia przykład kanału online.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-129">The following image shows an example online channel.</span></span>

![Przykład kanału online](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a><span data-ttu-id="a3a5d-131">Konfiguracja języków</span><span class="sxs-lookup"><span data-stu-id="a3a5d-131">Set up languages</span></span>

<span data-ttu-id="a3a5d-132">Jeśli dana witryna handlu elektronicznego będzie obsługiwać wiele języków, rozwiń sekcję **Języki** i dodaj dodatkowe języki w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-132">If your e-Commerce site will support multiple languages, expand the **Languages** section and add additional languages as needed.</span></span>

## <a name="set-up-payment-account"></a><span data-ttu-id="a3a5d-133">Konfiguracja konta płatności</span><span class="sxs-lookup"><span data-stu-id="a3a5d-133">Set up payment account</span></span>

<span data-ttu-id="a3a5d-134">W sekcji **Konto płatności** można dodać innego dostawcę płatności.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-134">From within the **Payment account** section, you can add a third-party payment provider.</span></span> <span data-ttu-id="a3a5d-135">Aby uzyskać informacje o ustawieniu łącznika płatności Adyen, zajrzyj do [Łącznik płatności usługi Dynamics 365 dla Adyen](./dev-itpro/adyen-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a3a5d-135">For information on setting up an Adyen payment connector, see [Dynamics 365 Payment Connector for Adyen](./dev-itpro/adyen-connector.md).</span></span>

## <a name="additional-channel-setup"></a><span data-ttu-id="a3a5d-136">Konfiguracja kanałów dodatkowych</span><span class="sxs-lookup"><span data-stu-id="a3a5d-136">Additional channel setup</span></span>

<span data-ttu-id="a3a5d-137">Dodatkowe zadania wymagane dla konfiguracji kanału online, obejmują Konfigurowanie metod płatności, metod dostawy i przypisania grupy realizacji.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-137">Additional tasks that are required for online channel setup include setting up payment methods, modes of delivery, and the fulfillment group assignment.</span></span>

<span data-ttu-id="a3a5d-138">Poniższy obraz pokazuje opcje ustawień **Metody dostawy**, **Metody płatności** i **Przypisania grupy realizacji** na karcie **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-138">The following image shows **Modes of delivery**, **Payment methods**, and **Fulfillment group assignment** setup options on the **Set up** tab.</span></span>

![Dodatkowe akcje konfiguracji kanału online](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="a3a5d-140">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="a3a5d-140">Set up payment methods</span></span>

<span data-ttu-id="a3a5d-141">Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="a3a5d-142">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="a3a5d-143">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a3a5d-144">W okienku nawigacji wybierz żądaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="a3a5d-145">W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="a3a5d-146">Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="a3a5d-147">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a3a5d-148">Poniższy obraz przedstawia przykład kart i metod płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-148">The following image shows an example of a cash payment method.</span></span>

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="a3a5d-150">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="a3a5d-150">Set up modes of delivery</span></span>

<span data-ttu-id="a3a5d-151">Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-151">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="a3a5d-152">Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-152">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="a3a5d-153">W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-153">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="a3a5d-154">W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-154">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="a3a5d-155">W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-155">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="a3a5d-156">Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-156">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="a3a5d-157">Poniższy obraz przedstawia przykład kart i metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-157">The following image shows an example of a mode of delivery.</span></span>

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="a3a5d-159">Konfiguracja przypisania grupy realizacji</span><span class="sxs-lookup"><span data-stu-id="a3a5d-159">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="a3a5d-160">Aby skonfigurować przypisanie grupy realizacji, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-160">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="a3a5d-161">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-161">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="a3a5d-162">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-162">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a3a5d-163">Z listy rozwijanej **Grupa realizacji** wybierz grupę realizacja.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-163">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="a3a5d-164">Z listy rozwijanej wybierz **Opis wprowadź** i wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-164">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="a3a5d-165">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-165">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a3a5d-166">Poniższy obraz przedstawia przykład konfiguracji przypisania grupy realizacji.</span><span class="sxs-lookup"><span data-stu-id="a3a5d-166">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Konfiguracja przypisania grupy realizacji](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a><span data-ttu-id="a3a5d-168">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="a3a5d-168">Additional resources</span></span>

[<span data-ttu-id="a3a5d-169">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="a3a5d-169">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a3a5d-170">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="a3a5d-170">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a3a5d-171">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="a3a5d-171">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="a3a5d-172">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="a3a5d-172">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="a3a5d-173">Łącznik płatności usługi Dynamics 365 dla Adyen</span><span class="sxs-lookup"><span data-stu-id="a3a5d-173">Dynamics 365 Payment Connector for Adyen</span></span>](./dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]