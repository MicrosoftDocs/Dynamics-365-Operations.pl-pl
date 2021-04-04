---
title: Konfigurowanie kanału sprzedaży
description: W tym temacie opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a5d0a081cff9fab8dc0a513496e6a5eccd03c871
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478267"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="6f1d8-103">Konfigurowanie kanału handlu detalicznego</span><span class="sxs-lookup"><span data-stu-id="6f1d8-103">Set up a retail channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6f1d8-104">W tym temacie opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6f1d8-105">Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-105">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="6f1d8-106">Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-106">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="6f1d8-107">Każdy kanał sklepu detalicznego ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-107">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="6f1d8-108">Wszystkie te elementy kanału sklepu detalicznego należy skonfigurować przed jego utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-108">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="6f1d8-109">Przed utworzeniem kanału sprzedaży należy przestrzegać [wymagań wstępnych dotyczących kanału](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-109">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="6f1d8-110">Utwórz i skonfiguruj nowy kanał sprzedaży</span><span class="sxs-lookup"><span data-stu-id="6f1d8-110">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="6f1d8-111">W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Sklepy \> Wszystkie sklepy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-111">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="6f1d8-112">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6f1d8-113">W polu **Nazwa** wprowadź nazwę nowego kanału.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-113">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="6f1d8-114">W polu **Numer sklepu** wprowadź indywidualny numer sklepu.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-114">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="6f1d8-115">Liczba może być alfanumeryczna z maksymalną 10 znakami.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-115">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="6f1d8-116">Na liście rozwijanej **Firma** wprowadź odpowiednią firmę.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-116">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="6f1d8-117">Z listy rozwijanej **Magazyn** wybierz odpowiedni magazyn.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-117">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="6f1d8-118">W polu **Strefa czasowa sklepu** wybierz odpowiednią strefę czasową.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-118">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="6f1d8-119">Z listy rozwijanej **Grupa podatków** wybierz odpowiednią grupę podatków dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-119">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="6f1d8-120">W polu **Waluta** wybierz odpowiednią walutę.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-120">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="6f1d8-121">W polu **Książka adresowa klienta** podaj prawidłową książkę adresową.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-121">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="6f1d8-122">W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-122">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="6f1d8-123">W polu **Profil funkcji** wybierz profil funkcji, jeśli ma to zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-123">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="6f1d8-124">W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-124">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="6f1d8-125">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-125">On the action pane, select **Save**.</span></span>

<span data-ttu-id="6f1d8-126">Poniższy rysunek przedstawia utworzenie nowego kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-126">The following image shows the creation of a new retail channel.</span></span>

![Nowy kanał sprzedaży](media/channel-setup-retail-1.png)

<span data-ttu-id="6f1d8-128">Poniższy obraz przedstawia przykład kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-128">The following image shows an example retail channel.</span></span>

![Przykład kanału sprzedaży](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="6f1d8-130">Inne ustawienia</span><span class="sxs-lookup"><span data-stu-id="6f1d8-130">Other settings</span></span>

<span data-ttu-id="6f1d8-131">Istnieje wiele innych ustawień opcjonalnych, które można ustawiać w sekcjach **Zestawienie/zamknięcie** i **Różne**, na podstawie potrzeb sklepu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-131">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="6f1d8-132">Ponadto zapoznaj się z tematami [Układy ekranu dla punktu sprzedaży (POS)](pos-screen-layouts.md), aby uzyskać informacje dotyczące konfigurowania domyślnego układu ekranu w sekcji **Układ ekranu** oraz [Konfigurowanie i instalowanie modułu Retail Hardware Station](retail-hardware-station-configuration-installation.md) z informacjami o konfiguracji w sekcji **Stacje sprzętowe**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-132">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="6f1d8-133">Poniższy obraz przedstawia przykład konfiguracji kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-133">The following image shows an example retail channel setup configuration.</span></span>

![Przykład konfiguracji kanału sprzedaży](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="6f1d8-135">Konfiguracja kanałów dodatkowych</span><span class="sxs-lookup"><span data-stu-id="6f1d8-135">Additional channel set up</span></span>

<span data-ttu-id="6f1d8-136">Istnieją dodatkowe pozycje, które należy skonfigurować dla kanału, które można znaleźć w **okienku akcji** w sekcji **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-136">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="6f1d8-137">Dodatkowe zadania wymagane do konfiguracji kanału online obejmują konfigurowanie metod płatności, deklaracji gotówki, metod dostawy, kont przychodów/wydatków, sekcji, przypisania grupy realizacji i sejfów.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-137">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="6f1d8-138">Na poniższym rysunku przedstawiono różne dodatkowe opcje konfiguracji kanału sprzedaży detalicznej na karcie **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-138">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Konfigurowanie kanału](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="6f1d8-140">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="6f1d8-140">Set up payment methods</span></span>

<span data-ttu-id="6f1d8-141">Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-141">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="6f1d8-142">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-142">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="6f1d8-143">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-143">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6f1d8-144">W okienku nawigacji wybierz żądaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-144">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="6f1d8-145">W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-145">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="6f1d8-146">Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-146">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="6f1d8-147">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="6f1d8-148">Poniższy obraz przedstawia przykład kart i metod płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-148">The following image shows an example of a cash payment method.</span></span>

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="6f1d8-150">Ustawienia deklaracji gotówki</span><span class="sxs-lookup"><span data-stu-id="6f1d8-150">Set up cash declaration</span></span>

1. <span data-ttu-id="6f1d8-151">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Deklaracja gotówki**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-151">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="6f1d8-152">W okienku akcji wybierz opcję **Nowy**, a następnie Utwórz wszystkie zastosowane oznaczenia **Monety** i **Banknoty**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-152">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="6f1d8-153">Poniższy obraz przedstawia przykład kart i deklaracji gotówki.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-153">The following image shows an example of a cash declaration.</span></span>

![Ustawienia deklaracji gotówki](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="6f1d8-155">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="6f1d8-155">Set up modes of delivery</span></span>

<span data-ttu-id="6f1d8-156">Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-156">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="6f1d8-157">Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-157">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="6f1d8-158">W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-158">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="6f1d8-159">W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-159">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="6f1d8-160">W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-160">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="6f1d8-161">Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-161">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="6f1d8-162">Poniższy obraz przedstawia przykład kart i metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-162">The following image shows an example of a mode of delivery.</span></span>

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="6f1d8-164">Konfiguruj konto wpływu/wpłaty lub wpływów/wydatków</span><span class="sxs-lookup"><span data-stu-id="6f1d8-164">Set up income/expense account</span></span>

<span data-ttu-id="6f1d8-165">Aby skonfigurować konto wpływów/wydatków, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-165">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="6f1d8-166">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Konto wpływów/wydatków**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-166">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="6f1d8-167">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-167">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6f1d8-168">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-168">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="6f1d8-169">W polu **Wyszukaj nazwę** wprowadź wyszukiwaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-169">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="6f1d8-170">Wprowadź typ konta w polu **Typ konta**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-170">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="6f1d8-171">Wprowadź tekst dla **Wiersza wiadomości 1**, **Wiersz wiadomości 2**, **Tekst dokumentu 1** i **Tekst dokumentu 2** w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-171">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="6f1d8-172">W obszarze **Księgowanie** wprowadź informacje o księgowaniu.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-172">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="6f1d8-173">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-173">On the action pane, select **Save**.</span></span>

<span data-ttu-id="6f1d8-174">Poniższy obraz przedstawia przykład konta wpływów/wydatków.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-174">The following image shows an example of an income/expense account.</span></span>

![Konfiguruj konta wpływów/wydatków](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="6f1d8-176">Konfigurowanie sekcji</span><span class="sxs-lookup"><span data-stu-id="6f1d8-176">Set up sections</span></span>

<span data-ttu-id="6f1d8-177">Aby skonfigurować sekcje, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-177">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="6f1d8-178">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sekcje**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-178">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="6f1d8-179">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-179">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6f1d8-180">W obszarze **Numer sekcji** wprowadź numer sekcji.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-180">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="6f1d8-181">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-181">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="6f1d8-182">W obszarze **Rozmiar sekcji** wprowadź rozmiar sekcji.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-182">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="6f1d8-183">W razie potrzeby skonfiguruj dodatkowe ustawienia w **Ogólne** i **Statystka sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-183">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="6f1d8-184">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-184">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="6f1d8-185">Konfiguracja przypisania grupy realizacji</span><span class="sxs-lookup"><span data-stu-id="6f1d8-185">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="6f1d8-186">Aby skonfigurować przypisanie grupy realizacji, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-186">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="6f1d8-187">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-187">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="6f1d8-188">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-188">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6f1d8-189">Z listy rozwijanej **Grupa realizacji** wybierz grupę realizacja.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-189">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="6f1d8-190">Z listy rozwijanej wybierz **Opis wprowadź** i wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-190">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="6f1d8-191">Na okienku akcji wybierz opcję **Zapisz**</span><span class="sxs-lookup"><span data-stu-id="6f1d8-191">On the action pane, select **Save**</span></span>

<span data-ttu-id="6f1d8-192">Poniższy obraz przedstawia przykład konfiguracji przypisania grupy realizacji.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-192">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Konfiguracja przypisań grupy realizacji](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="6f1d8-194">Konfiguracja sejfów</span><span class="sxs-lookup"><span data-stu-id="6f1d8-194">Set up safes</span></span>

<span data-ttu-id="6f1d8-195">Aby skonfigurować sejfy, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-195">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="6f1d8-196">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sejfy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-196">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="6f1d8-197">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-197">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6f1d8-198">Wprowadź nazwę sejfu.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-198">Enter a name for the safe.</span></span>
1. <span data-ttu-id="6f1d8-199">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-199">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f1d8-200">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="6f1d8-200">Additional resources</span></span>

[<span data-ttu-id="6f1d8-201">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="6f1d8-201">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="6f1d8-202">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="6f1d8-202">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="6f1d8-203">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="6f1d8-203">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="6f1d8-204">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="6f1d8-204">Set up a call center channel</span></span>](channel-setup-callcenter.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
