---
title: Konfigurowanie kanału biura obsługi
description: W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3f8c47c00b920dae01213d1d241ac8ee6a18d4e3
ms.sourcegitcommit: 776758a0ff95c3c7398986095104d1d2b9814514
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2020
ms.locfileid: "4107191"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="63f49-103">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="63f49-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="63f49-104">W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="63f49-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="63f49-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="63f49-105">Overview</span></span>


<span data-ttu-id="63f49-106">W Dynamics 365 Commerce biuro obsługi jest typem kanału Commerce, który można zdefiniować w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="63f49-106">In Dynamics 365 Commerce, a call center is a type of Commerce channel that can be defined in the application.</span></span> <span data-ttu-id="63f49-107">Zdefiniowanie kanału dla jednostek biura obsługi telefonicznej umożliwia systemowi na odtworzenie konkretnych danych i zamówień, które są domyślne dla zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="63f49-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="63f49-108">Firma może definiować wiele kanałów biura obsługi w module Commerce, dlatego należy zauważyć, że pojedynczy użytkownik może być połączony tylko z jednym kanałem biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-108">While a company can define multiple call center channels in Commerce, it is important to note that an individual user may only be linked to one call center channel.</span></span> 

<span data-ttu-id="63f49-109">Przed utworzeniem nowego kanału biura obsługi, należy upewnić się, że zakończono [Konfigurowanie wstępnie wymaganych ustawień kanału](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="63f49-109">Before you create a new call center channel, ensure that you have completed the [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="63f49-110">Utwórz i skonfiguruj nowy kanał biura obsługi</span><span class="sxs-lookup"><span data-stu-id="63f49-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="63f49-111">Aby utworzyć i skonfigurować nowy kanał biura obsługi, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="63f49-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="63f49-112">W panelu nawigacyjnym wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Biura obsługi \> Wszystkie biura obsługi**.</span><span class="sxs-lookup"><span data-stu-id="63f49-112">In the navigation pane, go to **Retail and Commerce \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="63f49-113">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="63f49-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="63f49-114">W polu **Nazwa** wprowadź nazwę nowego kanału.</span><span class="sxs-lookup"><span data-stu-id="63f49-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="63f49-115">Wybierz odpowiednią **Firmę** z rozwijanego menu.</span><span class="sxs-lookup"><span data-stu-id="63f49-115">Select the appropriate **Legal entity** from the drop-down.</span></span>
1. <span data-ttu-id="63f49-116">Wybierz odpowiednią lokalizację **Magazynu** z rozwijanego menu.</span><span class="sxs-lookup"><span data-stu-id="63f49-116">Select the appropriate **Warehouse** location from the drop-down.</span></span> <span data-ttu-id="63f49-117">Ta lokalizacja będzie używana jako domyślna wartość w zamówieniach sprzedaży utworzonych dla tego kanału biura obsługi połączenia, o ile nie zdefiniowano innych wartości domyślnych na poziomie odbiorcy lub towaru.</span><span class="sxs-lookup"><span data-stu-id="63f49-117">This location will be used as the default on sales orders created for this call center channel, unless other defaults have been defined at the customer or item level.</span></span>
1. <span data-ttu-id="63f49-118">W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="63f49-118">In the **Default customer** field, provide a valid default customer.</span></span> <span data-ttu-id="63f49-119">Te dane służą do automatycznego wypełniania domyślnych ustawień tworzenia rekordów odbiorców.</span><span class="sxs-lookup"><span data-stu-id="63f49-119">This data is used to assist in autopopulating defaults when new customer records are created.</span></span> <span data-ttu-id="63f49-120">Podczas tworzenia zamówień biura obsługi nie zaleca się tworzenia zamówień dla domyślnego odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="63f49-120">When creating call center orders, it is not advisable to create orders for the default customer.</span></span>
1. <span data-ttu-id="63f49-121">W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.</span><span class="sxs-lookup"><span data-stu-id="63f49-121">In the **Email notification profile** field, provide a valid email notification profile.</span></span> <span data-ttu-id="63f49-122">Podczas tworzenia i przetwarzania zamówień rozmów telefonicznych profil powiadomień e-mail jest używany do wyzwalania automatycznych alertów e-mail dla odbiorców z informacjami o stanie zamówienia.</span><span class="sxs-lookup"><span data-stu-id="63f49-122">As call center orders are created and processed, the email notification profile is used to trigger automated email alerts to customers with information about their order status.</span></span>
1. <span data-ttu-id="63f49-123">Podaj kod informacji o **Ręczna zmiana ceny**.</span><span class="sxs-lookup"><span data-stu-id="63f49-123">Provide a **Price override** info code.</span></span> <span data-ttu-id="63f49-124">Konieczne może być utworzenie najpierw kodu informacyjnego.</span><span class="sxs-lookup"><span data-stu-id="63f49-124">You may need to create an info code for this first.</span></span> <span data-ttu-id="63f49-125">Ten kod informacji określa zestaw kodów przyczyn, które użytkownik będzie monitowany o wybranie w przypadku korzystania z funkcji zastępowanie cen w zamówieniu biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-125">This info code provides the set of reason codes that the user will be prompted to choose from when using the price override functionality on a call center order.</span></span>
1. <span data-ttu-id="63f49-126">Podaj kod informacji o **Kod wstrzymania**.</span><span class="sxs-lookup"><span data-stu-id="63f49-126">Provide a **Hold code** info code.</span></span> <span data-ttu-id="63f49-127">Konieczne może być utworzenie najpierw kodu informacyjnego.</span><span class="sxs-lookup"><span data-stu-id="63f49-127">You may need to create an info code for this first.</span></span> <span data-ttu-id="63f49-128">Ten kod informacji określa zestaw opcjonalnych kodów przyczyn, które użytkownik będzie monitowany o wybranie w przypadku składania wstrzymanego zamówienia.</span><span class="sxs-lookup"><span data-stu-id="63f49-128">This info code provides the set of optional reason codes that the user will be prompted to choose from when placing an order on hold.</span></span>
1. <span data-ttu-id="63f49-129">Podaj kod informacji o **Kredycie**.</span><span class="sxs-lookup"><span data-stu-id="63f49-129">Provide a **Credit** info code.</span></span> <span data-ttu-id="63f49-130">Konieczne może być utworzenie najpierw kodu informacyjnego.</span><span class="sxs-lookup"><span data-stu-id="63f49-130">You may need to create an info code for this first.</span></span> <span data-ttu-id="63f49-131">Kod ten udostępnia zestaw kodów przyczyn, z których użytkownik może wybierać, korzystając z funkcji kredytu zamówienia w serwisie telefonicznej w celu uzyskania dodatkowych zwrotów dla odbiorcy w związku z przyczynami obsługi klienta.</span><span class="sxs-lookup"><span data-stu-id="63f49-131">This info code provides the set of reason codes that the user can choose from when using the order credit functionality of call center to give misc refunds to the customer for customer service reasons.</span></span>
1. <span data-ttu-id="63f49-132">Opcjonalnie: konfiguruj wymiary finansowe na skróconej karcie **Wymiary finansowe**.</span><span class="sxs-lookup"><span data-stu-id="63f49-132">Optional: set up financial dimensions on the **Financial dimensions** FastTab.</span></span> <span data-ttu-id="63f49-133">Wprowadzone tutaj wymiary są domyślne w każdym zamówieniu sprzedaży utworzonym w tym kanale biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-133">The dimensions entered here will default on any sales order created in this call center channel.</span></span>
1. <span data-ttu-id="63f49-134">Kliknij przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="63f49-134">Click **Save**.</span></span>

<span data-ttu-id="63f49-135">Poniższy rysunek przedstawia utworzenie nowego kanału biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-135">The following image shows the creation of a new call center channel.</span></span>

![Nowy kanał biura obsługi](media/channel-setup-callcenter-1.png)

<span data-ttu-id="63f49-137">Poniższy obraz przedstawia przykład kanału biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-137">The following image shows an example call center channel.</span></span>

![Przykład kanału biura obsługi](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="63f49-139">Konfiguracja kanałów dodatkowych</span><span class="sxs-lookup"><span data-stu-id="63f49-139">Additional channel setup</span></span>

<span data-ttu-id="63f49-140">Dodatkowe zadania wymagane dla konfiguracji kanału dla biura obsługi, obejmują Konfigurowanie metod płatności i metod dostawy.</span><span class="sxs-lookup"><span data-stu-id="63f49-140">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="63f49-141">Poniższy obraz pokazuje **Metody dostawy** i **Metody płatności** ustaw opcje na karcie **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="63f49-141">The following image shows **Modes of delivery** and **Payment methods** setup options on the **Set up** tab.</span></span>

![Dodatkowe akcje konfiguracji kanału biura obsługi](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="63f49-143">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="63f49-143">Set up payment methods</span></span>

<span data-ttu-id="63f49-144">Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.</span><span class="sxs-lookup"><span data-stu-id="63f49-144">To set up payment methods, follow these steps for each payment type supported on this channel.</span></span> <span data-ttu-id="63f49-145">Użytkownicy będą zobowiązani do wybrania wstępnie zdefiniowanych metod płatności w celu połączenia ich z kanałem biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-145">Users will be required to select from pre-defined payment methods to link them to the call center channel.</span></span> <span data-ttu-id="63f49-146">Przed skonfigurowaniem metod płatności biura obsługi, należy najpierw skonfigurować główne metody płatności w **Retail i Commerce \> Konfiguracja kanału \> Metody płatności \> Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="63f49-146">Before setting up your call center payment methods, first set up your master methods of payment in **Retail and Commerce \> Channel setup \> Payment methods \> Payment methods**.</span></span>

1. <span data-ttu-id="63f49-147">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="63f49-147">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="63f49-148">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="63f49-148">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="63f49-149">W okienku nawigacji wybierz metodę płatności z dostępnych wstępnie zdefiniowanych płatności.</span><span class="sxs-lookup"><span data-stu-id="63f49-149">In the navigation pane, select a payment method from the pre-defined payments available.</span></span>
1. <span data-ttu-id="63f49-150">Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.</span><span class="sxs-lookup"><span data-stu-id="63f49-150">Configure any additional settings as required for the payment type.</span></span> <span data-ttu-id="63f49-151">W przypadku kart kredytowych, kart upominkowych lub kart lojalnościowych dodatkowe ustawienia są wymagane po wybraniu funkcji **ustawienia karty**.</span><span class="sxs-lookup"><span data-stu-id="63f49-151">For credit cards, gift cards, or loyalty cards, additional setup is required by selecting the **Card setup** function.</span></span> 
1. <span data-ttu-id="63f49-152">Skonfiguruj poprawne konta księgowania dla typu płatności w sekcji **księgowanie**.</span><span class="sxs-lookup"><span data-stu-id="63f49-152">Configure proper posting accounts for the payment type in the **Posting** section.</span></span>
1. <span data-ttu-id="63f49-153">W okienku akcji kliknij pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="63f49-153">On the action pane, click **Save**.</span></span>

<span data-ttu-id="63f49-154">Poniższy obraz przedstawia przykład kart i metod płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="63f49-154">The following image shows an example of a cash payment method.</span></span>

![Przykład metod płatności](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="63f49-156">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="63f49-156">Set up modes of delivery</span></span>

<span data-ttu-id="63f49-157">Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.</span><span class="sxs-lookup"><span data-stu-id="63f49-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="63f49-158">Aby zmienić lub dodać metodę dostawy skojarzoną z kanałem biura obsługi, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="63f49-158">To change or add a mode of delivery to be associated to the call center channel, follow these steps.</span></span>

1. <span data-ttu-id="63f49-159">W formularzu metody dostawy biura obsługi, wybierz opcję **Zarządzaj metodami dostawy**</span><span class="sxs-lookup"><span data-stu-id="63f49-159">From the Call center modes of delivery form, select **Manage modes of delivery**</span></span>
1. <span data-ttu-id="63f49-160">W okienku akcji wybierz opcję **nowy** , aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.</span><span class="sxs-lookup"><span data-stu-id="63f49-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="63f49-161">W sekcji **Kanały sprzedaży** kliknij opcję **Dodaj wiersz** , aby dodać kanał biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-161">In the **Retail channels** section, click **Add line** to add the call center channel.</span></span> <span data-ttu-id="63f49-162">Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.</span><span class="sxs-lookup"><span data-stu-id="63f49-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>
1. <span data-ttu-id="63f49-163">Upewnij się, że metoda dostawy została skonfigurowana z danymi na skróconej karcie **produkty** i **adresy**.</span><span class="sxs-lookup"><span data-stu-id="63f49-163">Ensure the mode of delivery has been configured with data on the **Products** FastTab and the **Addresses** FastTab.</span></span> <span data-ttu-id="63f49-164">Jeśli żadne produkty lub adresy dostawy nie są prawidłowe dla metody dostawy, wybranie ich podczas wprowadzania zamówienia spowoduje błędy.</span><span class="sxs-lookup"><span data-stu-id="63f49-164">If no products or delivery addresses are valid for the mode of delivery, choosing it during order entry will result in errors.</span></span>
1. <span data-ttu-id="63f49-165">Po dokonaniu jakichkolwiek zmian w metodach konfiguracji dostawy w ramach procesu obsługi zleceń należy uruchomić zadanie **Metody dostawy dla procesu** , aby rozłożyć matrycę zmiany.</span><span class="sxs-lookup"><span data-stu-id="63f49-165">After any changes have been made to the call center mode of delivery configurations, the **Process delivery modes** job must be run to explode the change matrix.</span></span> <span data-ttu-id="63f49-166">To zadanie można znaleźć, przechodząc **Retail i Commerce \> Retail i Commerce — składniki IT \> Metody dostawy dla procesu**.</span><span class="sxs-lookup"><span data-stu-id="63f49-166">This job can be found by navigating to **Retail and Commerce \> Retail and Commerce IT \> Process delivery modes**.</span></span>

<span data-ttu-id="63f49-167">Poniższy obraz przedstawia przykład kart i metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="63f49-167">The following image shows an example of a mode of delivery.</span></span>

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a><span data-ttu-id="63f49-169">Konfigurowanie użytkowników kanału</span><span class="sxs-lookup"><span data-stu-id="63f49-169">Set up channel users</span></span>

<span data-ttu-id="63f49-170">Aby utworzyć zamówienie sprzedaży połączone z pracownikiem biura obsługi w module Commerce Headquarters, użytkownik tworzący zamówienie musi być połączony z kanałem biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-170">To create a sales order that is linked to the call center channel from Commerce Headquarters, the user creating the sales order must be linked to the call center channel.</span></span> <span data-ttu-id="63f49-171">Użytkownik nie może ręcznie połączyć zamówienia sprzedaży utworzonego w module Commerce Headquarters z kanałem biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-171">The user cannot manually link a sales order created in Commerce Headquarters to the call center channel.</span></span> <span data-ttu-id="63f49-172">Łącze jest systematyczne i jest oparte na użytkowniku i relacji użytkownika z kanałem biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-172">The link is systematic, and is based on the user and the user's relationship to the call center channel.</span></span> <span data-ttu-id="63f49-173">Użytkownik może być połączony tylko z jednym kanałem biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-173">A user may only be linked to one call center channel.</span></span>

1. <span data-ttu-id="63f49-174">W okienku akcji wybierz kartę **Kanał** i wybierz opcję **Użytkownicy kanału**.</span><span class="sxs-lookup"><span data-stu-id="63f49-174">On the action pane, select the **Channel** tab, and then select **Channel users**.</span></span>
1. <span data-ttu-id="63f49-175">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="63f49-175">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="63f49-176">Wybierz istniejący **identyfikator użytkownika** z listy rozwijanej zaznacz, aby połączyć tego użytkownika z kanałem biura obsługi</span><span class="sxs-lookup"><span data-stu-id="63f49-176">Choose an existing **User ID** from the dropdown selection list to link this user to the call center channel</span></span>

<span data-ttu-id="63f49-177">Po zakończeniu konfiguracji użytkownika kanału i gdy użytkownik utworzy nowe zamówienie sprzedaży w module Commerce Headquarters, użytkownik tworzący zamówienie zostanie połączony ze swoim kanałem biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-177">After the channel user setup is done and the user creates a new sales order in Commerce Headquarters, the sales order will be linked to their associated call center channel.</span></span> <span data-ttu-id="63f49-178">Wszelkie konfiguracje dla tego kanału będą stosowane systematycznie w zamówieniu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="63f49-178">Any configurations for this channel will be applied systematically to the sales order.</span></span> <span data-ttu-id="63f49-179">Użytkownik może potwierdzić, który kanał biura obsługi jest połączony z danym zamówieniem sprzedaży, wyświetlając odwołanie do nazwy kanału w nagłówku zamówienia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="63f49-179">A user can confirm which call center channel the sales order is linked to by viewing the channel name reference on the sales order header.</span></span>


### <a name="set-up-price-groups"></a><span data-ttu-id="63f49-180">Konfigurowanie grup cenowych</span><span class="sxs-lookup"><span data-stu-id="63f49-180">Set up price groups</span></span>

<span data-ttu-id="63f49-181">Grupy cenowe są opcjonalne, ale jeśli są używane, mogą określać, które ceny sprzedaży będą oferowane odbiorcom do realizacji zamówień w kanale biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="63f49-181">Price groups are optional, but if used, can control which sales prices will be offered to customers placing orders in the call center channel.</span></span> <span data-ttu-id="63f49-182">Jeśli grupa cenowa nie została skonfigurowana dla odbiorcy lub nie są stosowane grupy cenowe w katalogu w zamówieniu sprzedaży (przy użyciu pola **Identyfikator kodu źródłowego** w nagłówku zlecenia biura obsługi), Grupa cenowa w kanale jest używana do lokalizowania cen towarów.</span><span class="sxs-lookup"><span data-stu-id="63f49-182">If a price group has not been configured for the customer, or if catalog price groups are not being applied to the sales order (using the **Source code ID** field on the call center order header), then the channel price group is used to locate item prices.</span></span> <span data-ttu-id="63f49-183">Jeśli w kanale biura obsługi nie znaleziono grupy cenowej, używane są domyślne ceny główne towaru.</span><span class="sxs-lookup"><span data-stu-id="63f49-183">If a price group is not found on the call center channel, the default item master prices are used.</span></span> 

<span data-ttu-id="63f49-184">Aby skonfigurować grupę cenową, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="63f49-184">To set up a price group, do the following.</span></span>

1. <span data-ttu-id="63f49-185">W okienku akcji kliknij kartę **Kanał** i wybierz opcję **Grupy cenowe**.</span><span class="sxs-lookup"><span data-stu-id="63f49-185">On the action pane, click the **Channel** tab, and then select **Price groups**.</span></span>
1. <span data-ttu-id="63f49-186">W okienku akcji kliknij **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="63f49-186">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="63f49-187">Wybierz **grupę cenową sieci sprzedaży** z listy rozwijanej wyboru.</span><span class="sxs-lookup"><span data-stu-id="63f49-187">Select a **Retail price group** from the dropdown selection list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63f49-188">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="63f49-188">Additional resources</span></span>

[<span data-ttu-id="63f49-189">Wymagania wstępne dotyczące konfiguracji kanału</span><span class="sxs-lookup"><span data-stu-id="63f49-189">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="63f49-190">Funkcje sprzedaży przez biuro obsługi</span><span class="sxs-lookup"><span data-stu-id="63f49-190">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="63f49-191">Konfigurowanie opcji przetwarzania zamówień biura obsługi</span><span class="sxs-lookup"><span data-stu-id="63f49-191">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="63f49-192">Katalogi biura obsługi</span><span class="sxs-lookup"><span data-stu-id="63f49-192">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="63f49-193">Konfigurowanie i używanie alertów o oszustwie</span><span class="sxs-lookup"><span data-stu-id="63f49-193">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="63f49-194">Konfigurowanie programów sprzedaży ciągłej dla biur obsługi</span><span class="sxs-lookup"><span data-stu-id="63f49-194">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
