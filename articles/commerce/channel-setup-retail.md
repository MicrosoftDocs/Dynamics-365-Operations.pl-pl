---
title: Konfigurowanie kanału sprzedaży
description: W tym temacie opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/23/2021
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
ms.openlocfilehash: 3f1f5dc2c8402d9b6b68a049f804932812eb74c0
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937541"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="2a912-103">Konfigurowanie kanału handlu detalicznego</span><span class="sxs-lookup"><span data-stu-id="2a912-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2a912-104">W tym temacie opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a912-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="2a912-105">Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="2a912-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="2a912-106">Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi).</span><span class="sxs-lookup"><span data-stu-id="2a912-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="2a912-107">Każdy kanał sklepu detalicznego ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel.</span><span class="sxs-lookup"><span data-stu-id="2a912-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="2a912-108">Wszystkie te elementy kanału sklepu detalicznego należy skonfigurować przed jego utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="2a912-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="2a912-109">Przed utworzeniem kanału sprzedaży należy przestrzegać [wymagań wstępnych dotyczących kanału](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="2a912-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="2a912-110">Utwórz i skonfiguruj nowy kanał sprzedaży</span><span class="sxs-lookup"><span data-stu-id="2a912-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="2a912-111">W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Sklepy \> Wszystkie sklepy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="2a912-112">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-112">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="2a912-113">W polu **Nazwa** wprowadź nazwę nowego kanału.</span><span class="sxs-lookup"><span data-stu-id="2a912-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="2a912-114">W polu **Numer sklepu** wprowadź indywidualny numer sklepu.</span><span class="sxs-lookup"><span data-stu-id="2a912-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="2a912-115">Liczba może być alfanumeryczna z maksymalną 10 znakami.</span><span class="sxs-lookup"><span data-stu-id="2a912-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="2a912-116">Na liście rozwijanej **Firma** wprowadź odpowiednią firmę.</span><span class="sxs-lookup"><span data-stu-id="2a912-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="2a912-117">Z listy rozwijanej **Magazyn** wybierz odpowiedni magazyn.</span><span class="sxs-lookup"><span data-stu-id="2a912-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="2a912-118">W polu **Strefa czasowa sklepu** wybierz odpowiednią strefę czasową.</span><span class="sxs-lookup"><span data-stu-id="2a912-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="2a912-119">Z listy rozwijanej **Grupa podatków** wybierz odpowiednią grupę podatków dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="2a912-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="2a912-120">W polu **Waluta** wybierz odpowiednią walutę.</span><span class="sxs-lookup"><span data-stu-id="2a912-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="2a912-121">W polu **Książka adresowa klienta** podaj prawidłową książkę adresową.</span><span class="sxs-lookup"><span data-stu-id="2a912-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="2a912-122">W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="2a912-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="2a912-123">W polu **Profil funkcji** wybierz profil funkcji, jeśli ma to zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="2a912-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="2a912-124">W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.</span><span class="sxs-lookup"><span data-stu-id="2a912-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="2a912-125">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2a912-125">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="2a912-126">Poniższy rysunek przedstawia utworzenie nowego kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2a912-126">The following image shows the creation of a new retail channel.</span></span>

![Nowy kanał sprzedaży](media/channel-setup-retail-1.png)

<span data-ttu-id="2a912-128">Poniższy obraz przedstawia przykład kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2a912-128">The following image shows an example retail channel.</span></span>

![Przykład kanału sprzedaży](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="2a912-130">Inne ustawienia</span><span class="sxs-lookup"><span data-stu-id="2a912-130">Other settings</span></span>

<span data-ttu-id="2a912-131">Istnieje wiele innych ustawień opcjonalnych, które można ustawiać w sekcjach **Zestawienie/zamknięcie** i **Różne**, na podstawie potrzeb sklepu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="2a912-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="2a912-132">Ponadto zapoznaj się z tematami [Układy ekranu dla punktu sprzedaży (POS)](pos-screen-layouts.md), aby uzyskać informacje dotyczące konfigurowania domyślnego układu ekranu w sekcji **Układ ekranu** oraz [Konfigurowanie i instalowanie modułu Retail Hardware Station](retail-hardware-station-configuration-installation.md) z informacjami o konfiguracji w sekcji **Stacje sprzętowe**.</span><span class="sxs-lookup"><span data-stu-id="2a912-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="2a912-133">Poniższy obraz przedstawia przykład konfiguracji kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="2a912-133">The following image shows an example retail channel setup configuration.</span></span>

![Przykład konfiguracji kanału sprzedaży](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="2a912-135">Konfiguracja kanałów dodatkowych</span><span class="sxs-lookup"><span data-stu-id="2a912-135">Additional channel set up</span></span>

<span data-ttu-id="2a912-136">Istnieją dodatkowe pozycje, które należy skonfigurować dla kanału, które można znaleźć w okienku akcji w sekcji **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="2a912-136">There are additional items that need to be set up for a channel that can be found on the Action Pane under the **Set up** section.</span></span>

<span data-ttu-id="2a912-137">Dodatkowe zadania wymagane do konfiguracji kanału online obejmują konfigurowanie metod płatności, deklaracji gotówki, metod dostawy, kont przychodów/wydatków, sekcji, przypisania grupy realizacji i sejfów.</span><span class="sxs-lookup"><span data-stu-id="2a912-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="2a912-138">Na poniższym rysunku przedstawiono różne dodatkowe opcje konfiguracji kanału sprzedaży detalicznej na karcie **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="2a912-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Konfigurowanie kanału](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="2a912-140">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="2a912-140">Set up payment methods</span></span>

<span data-ttu-id="2a912-141">Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.</span><span class="sxs-lookup"><span data-stu-id="2a912-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="2a912-142">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="2a912-142">On the Action Pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="2a912-143">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="2a912-144">W okienku nawigacji wybierz żądaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="2a912-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="2a912-145">W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.</span><span class="sxs-lookup"><span data-stu-id="2a912-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="2a912-146">Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.</span><span class="sxs-lookup"><span data-stu-id="2a912-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="2a912-147">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2a912-147">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="2a912-148">Poniższy obraz przedstawia przykład kart i metod płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="2a912-148">The following image shows an example of a cash payment method.</span></span>

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="2a912-150">Ustawienia deklaracji gotówki</span><span class="sxs-lookup"><span data-stu-id="2a912-150">Set up cash declaration</span></span>

1. <span data-ttu-id="2a912-151">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Deklaracja gotówki**.</span><span class="sxs-lookup"><span data-stu-id="2a912-151">On the Action Pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="2a912-152">W okienku akcji wybierz opcję **Nowy**, a następnie Utwórz wszystkie zastosowane oznaczenia **Monety** i **Banknoty**.</span><span class="sxs-lookup"><span data-stu-id="2a912-152">On the Action Pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="2a912-153">Poniższy obraz przedstawia przykład kart i deklaracji gotówki.</span><span class="sxs-lookup"><span data-stu-id="2a912-153">The following image shows an example of a cash declaration.</span></span>

![Ustawienia deklaracji gotówki](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="2a912-155">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="2a912-155">Set up modes of delivery</span></span>

<span data-ttu-id="2a912-156">Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w okienku akcji.</span><span class="sxs-lookup"><span data-stu-id="2a912-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the Action Pane.</span></span>  

<span data-ttu-id="2a912-157">Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="2a912-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="2a912-158">W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="2a912-159">W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.</span><span class="sxs-lookup"><span data-stu-id="2a912-159">On the Action Pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="2a912-160">W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał.</span><span class="sxs-lookup"><span data-stu-id="2a912-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="2a912-161">Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.</span><span class="sxs-lookup"><span data-stu-id="2a912-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="2a912-162">Poniższy obraz przedstawia przykład kart i metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="2a912-162">The following image shows an example of a mode of delivery.</span></span>

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="2a912-164">Konfiguruj konto wpływu/wpłaty lub wpływów/wydatków</span><span class="sxs-lookup"><span data-stu-id="2a912-164">Set up income/expense account</span></span>

<span data-ttu-id="2a912-165">Aby skonfigurować konto wpływów/wydatków, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="2a912-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="2a912-166">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Konto wpływów/wydatków**.</span><span class="sxs-lookup"><span data-stu-id="2a912-166">On the Action Pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="2a912-167">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-167">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="2a912-168">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="2a912-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="2a912-169">W polu **Wyszukaj nazwę** wprowadź wyszukiwaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="2a912-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="2a912-170">Wprowadź typ konta w polu **Typ konta**.</span><span class="sxs-lookup"><span data-stu-id="2a912-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="2a912-171">Wprowadź tekst dla **Wiersza wiadomości 1**, **Wiersz wiadomości 2**, **Tekst dokumentu 1** i **Tekst dokumentu 2** w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="2a912-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="2a912-172">W obszarze **Księgowanie** wprowadź informacje o księgowaniu.</span><span class="sxs-lookup"><span data-stu-id="2a912-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="2a912-173">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2a912-173">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="2a912-174">Poniższy obraz przedstawia przykład konta wpływów/wydatków.</span><span class="sxs-lookup"><span data-stu-id="2a912-174">The following image shows an example of an income/expense account.</span></span>

![Konfiguruj konta wpływów/wydatków](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="2a912-176">Konfigurowanie sekcji</span><span class="sxs-lookup"><span data-stu-id="2a912-176">Set up sections</span></span>

<span data-ttu-id="2a912-177">Aby skonfigurować sekcje, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="2a912-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="2a912-178">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sekcje**.</span><span class="sxs-lookup"><span data-stu-id="2a912-178">On the Action Pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="2a912-179">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-179">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="2a912-180">W obszarze **Numer sekcji** wprowadź numer sekcji.</span><span class="sxs-lookup"><span data-stu-id="2a912-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="2a912-181">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="2a912-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="2a912-182">W obszarze **Rozmiar sekcji** wprowadź rozmiar sekcji.</span><span class="sxs-lookup"><span data-stu-id="2a912-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="2a912-183">W razie potrzeby skonfiguruj dodatkowe ustawienia w **Ogólne** i **Statystka sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="2a912-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="2a912-184">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2a912-184">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="2a912-185">Konfiguracja przypisania grupy realizacji</span><span class="sxs-lookup"><span data-stu-id="2a912-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="2a912-186">Aby skonfigurować przypisanie grupy realizacji, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="2a912-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="2a912-187">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.</span><span class="sxs-lookup"><span data-stu-id="2a912-187">On the Action Pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="2a912-188">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-188">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="2a912-189">Z listy rozwijanej **Grupa realizacji** wybierz grupę realizacja.</span><span class="sxs-lookup"><span data-stu-id="2a912-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="2a912-190">Z listy rozwijanej wybierz **Opis wprowadź** i wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="2a912-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="2a912-191">Na okienku akcji wybierz opcję **Zapisz**</span><span class="sxs-lookup"><span data-stu-id="2a912-191">On the Action Pane, select **Save**</span></span>

<span data-ttu-id="2a912-192">Poniższy obraz przedstawia przykład konfiguracji przypisania grupy realizacji.</span><span class="sxs-lookup"><span data-stu-id="2a912-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Konfiguracja przypisań grupy realizacji](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="2a912-194">Konfiguracja sejfów</span><span class="sxs-lookup"><span data-stu-id="2a912-194">Set up safes</span></span>

<span data-ttu-id="2a912-195">Aby skonfigurować sejfy, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="2a912-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="2a912-196">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sejfy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-196">On the Action Pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="2a912-197">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="2a912-197">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="2a912-198">Wprowadź nazwę sejfu.</span><span class="sxs-lookup"><span data-stu-id="2a912-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="2a912-199">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="2a912-199">On the Action Pane, select **Save**.</span></span>

### <a name="ensure-unique-transaction-ids"></a><span data-ttu-id="2a912-200">Zapewnianie unikatowych identyfikatorów transakcji</span><span class="sxs-lookup"><span data-stu-id="2a912-200">Ensure unique transaction IDs</span></span>

<span data-ttu-id="2a912-201">W Commerce w wersji 10.0.18 identyfikatory transakcji wygenerowane dla punktu sprzedaży (POS) są sekwencyjne i zawierają następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="2a912-201">As of the Commerce version 10.0.18 , transaction IDs generated for the point of sale (POS) are sequential and include the following parts:</span></span>

- <span data-ttu-id="2a912-202">Stała część, która jest zlepkiem identyfikatora sklepu i identyfikatora terminalu.</span><span class="sxs-lookup"><span data-stu-id="2a912-202">A fixed part, which is a concatenation of store ID and terminal ID.</span></span> 
- <span data-ttu-id="2a912-203">Sekwencyjna część, która jest sekwencją numerów.</span><span class="sxs-lookup"><span data-stu-id="2a912-203">A sequential part, which is a number sequence.</span></span> 

<span data-ttu-id="2a912-204">Format to *{store}-{terminal}-{numbersequence}*.</span><span class="sxs-lookup"><span data-stu-id="2a912-204">Specifically, the format is *{store}-{terminal}-{numbersequence}*.</span></span> 

<span data-ttu-id="2a912-205">Ponieważ identyfikatory transakcji mogą być generowane w trybie offline i online, istnieją przypadki duplikowania identyfikatorów transakcji.</span><span class="sxs-lookup"><span data-stu-id="2a912-205">Because transaction IDs can be generated in offline and online modes, there have been instances of duplicate transaction IDs being generated.</span></span> <span data-ttu-id="2a912-206">Eliminacja duplikatów identyfikatorów transakcji wymaga ręcznego poprawiania danych.</span><span class="sxs-lookup"><span data-stu-id="2a912-206">Eliminating duplicate transaction IDs requires a lot of manual data fixing.</span></span> 

<span data-ttu-id="2a912-207">W Commerce w wersji 10.0.19 format identyfikatora transakcji został zaktualizowany w celu usunięcia sekwencyjnej części, a zamiast tego jest używany 13-cyfrowy numer wygenerowany przez obliczenie czasu w milisekundach od 1970 roku.</span><span class="sxs-lookup"><span data-stu-id="2a912-207">With Commerce version 10.0.19, the transaction ID format has been updated to remove the sequential part and instead uses a 13-digit number generated by calculating the time in milliseconds since 1970.</span></span> <span data-ttu-id="2a912-208">Nowy numer identyfikatora transakcji po tej zmianie to *{store}-{terminal}-{millisecondsSince1970}*.</span><span class="sxs-lookup"><span data-stu-id="2a912-208">With this change, the new transaction ID format is *{store}-{terminal}-{millisecondsSince1970}*.</span></span> <span data-ttu-id="2a912-209">Ta aktualizacja powoduje, że identyfikator transakcji nie jest sekwencyjny i że identyfikatory transakcji są zawsze unikatowe.</span><span class="sxs-lookup"><span data-stu-id="2a912-209">This update makes the transaction ID non-sequential and ensures that transaction IDs are always unique.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a912-210">Identyfikatory transakcji są przeznaczone tylko do użytku wewnętrznego, więc nie muszą być sekwencyjne.</span><span class="sxs-lookup"><span data-stu-id="2a912-210">Transaction IDs are meant for internal system use only, so they are not required to be sequential.</span></span> <span data-ttu-id="2a912-211">Jednak w wielu krajach identyfikatory paragonów muszą być sekwencyjne.</span><span class="sxs-lookup"><span data-stu-id="2a912-211">However, many countries require receipt IDs to be sequential.</span></span>

<span data-ttu-id="2a912-212">Nową funkcję formatu identyfikatora transakcji można włączyć w obszarze roboczym **Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="2a912-212">The new transaction ID format feature can be enabled from the **Feature management** workspace.</span></span> 

<span data-ttu-id="2a912-213">Aby umożliwić używanie nowych identyfikatorów transakcji, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="2a912-213">To enable the use of new transaction IDs, follow these steps:</span></span>

1. <span data-ttu-id="2a912-214">W centrali Commerce wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.</span><span class="sxs-lookup"><span data-stu-id="2a912-214">In Commerce headquarters, go to **System administration \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="2a912-215">Wyszukaj na liście moduł „Retail i Commerce”.</span><span class="sxs-lookup"><span data-stu-id="2a912-215">Filter for the "retail and commerce" module.</span></span>
1. <span data-ttu-id="2a912-216">Wyszukaj nazwę funkcji **Włącz nowy identyfikator transakcji w celu uniknięcia duplikatów identyfikatorów transakcji**.</span><span class="sxs-lookup"><span data-stu-id="2a912-216">Search for the **Enable new transaction id to avoid duplicate transaction ids** feature name.</span></span>
1. <span data-ttu-id="2a912-217">Wybierz funkcję, a następnie w prawym okienku naciśnij przycisk **Włącz teraz**.</span><span class="sxs-lookup"><span data-stu-id="2a912-217">Select the feature, and then select **Enable Now** in the right pane.</span></span>  
1. <span data-ttu-id="2a912-218">Wybierz kolejno opcje **Retail i Commerce \> Retail i Commerce IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="2a912-218">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="2a912-219">Uruchom zadania **1070 Konfiguracja kanałów** i **1170 Rejestrator zadań punktu sprzedaży**, aby zsynchronizować włączone funkcje w sklepach.</span><span class="sxs-lookup"><span data-stu-id="2a912-219">Run the **1070 Channel configuration** and **1170 POS task recorder** jobs to synchronize the enabled feature to the stores.</span></span>
1. <span data-ttu-id="2a912-220">Po wysłaniu zmian do sklepów terminale punktu sprzedaży muszą zostać zamknięte i ponownie otwarte, aby używać nowego formatu identyfikatora transakcji.</span><span class="sxs-lookup"><span data-stu-id="2a912-220">After the changes have been sent to the stores, POS terminals must be closed and reopened to use the new transaction ID format.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a912-221">Po włączeniu nowej funkcji formatu identyfikatora transakcji nie będzie można wyłączyć tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="2a912-221">After the new transaction ID format feature is enabled, you will not be able to disable this feature.</span></span> <span data-ttu-id="2a912-222">Jeśli musi zostać wyłączona, skontaktuj się z pomocą techniczną Commerce.</span><span class="sxs-lookup"><span data-stu-id="2a912-222">If it must be disabled, please contact Commerce Support.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2a912-223">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="2a912-223">Additional resources</span></span>

[<span data-ttu-id="2a912-224">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="2a912-224">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="2a912-225">Wymagania wstępne dotyczące konfiguracji kanału</span><span class="sxs-lookup"><span data-stu-id="2a912-225">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="2a912-226">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="2a912-226">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="2a912-227">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="2a912-227">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
