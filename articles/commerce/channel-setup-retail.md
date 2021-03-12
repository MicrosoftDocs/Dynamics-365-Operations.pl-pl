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
ms.openlocfilehash: 100822ecea03d03267f98654c66e74f2f5924bd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997732"
---
# <a name="set-up-a-retail-channel"></a><span data-ttu-id="c918f-103">Konfigurowanie kanału sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c918f-103">Set up a retail channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c918f-104">W tym temacie opisano, jak dodać utworzyć nowy kanał sprzedaży w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c918f-104">This topic describes how to create a new retail channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c918f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c918f-105">Overview</span></span>

<span data-ttu-id="c918f-106">Moduł Dynamics 365 Commerce obsługuje wiele kanałów sprzedaży detalicznej.</span><span class="sxs-lookup"><span data-stu-id="c918f-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="c918f-107">Te kanały sprzedaży detalicznej obejmują sklepy internetowe, internetowe serwisy sprzedażowe i sklepy sieci sprzedaży (nazywane także sklepami tradycyjnymi).</span><span class="sxs-lookup"><span data-stu-id="c918f-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="c918f-108">Każdy kanał sklepu detalicznego ma własne metody płatności, grupy cenowe, kasy punktów sprzedaży, konta przychodów i wydatków oraz personel.</span><span class="sxs-lookup"><span data-stu-id="c918f-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="c918f-109">Wszystkie te elementy kanału sklepu detalicznego należy skonfigurować przed jego utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="c918f-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="c918f-110">Przed utworzeniem kanału sprzedaży należy przestrzegać [wymagań wstępnych dotyczących kanału](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="c918f-110">Before a retail channel is created, ensure you follow the [channel prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-retail-channel"></a><span data-ttu-id="c918f-111">Utwórz i skonfiguruj nowy kanał sprzedaży</span><span class="sxs-lookup"><span data-stu-id="c918f-111">Create and configure a new retail channel</span></span>

1. <span data-ttu-id="c918f-112">W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Sklepy \> Wszystkie sklepy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-112">In the navigation pane, go to **Modules \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="c918f-113">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c918f-114">W polu **Nazwa** wprowadź nazwę nowego kanału.</span><span class="sxs-lookup"><span data-stu-id="c918f-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="c918f-115">W polu **Numer sklepu** wprowadź indywidualny numer sklepu.</span><span class="sxs-lookup"><span data-stu-id="c918f-115">In the **Store number** field, provide a unique store number.</span></span> <span data-ttu-id="c918f-116">Liczba może być alfanumeryczna z maksymalną 10 znakami.</span><span class="sxs-lookup"><span data-stu-id="c918f-116">The number can be alphanumeric with a maximum of 10 characters.</span></span>
1. <span data-ttu-id="c918f-117">Na liście rozwijanej **Firma** wprowadź odpowiednią firmę.</span><span class="sxs-lookup"><span data-stu-id="c918f-117">In the **Legal entity** drop-down list, enter the appropriate legal entity.</span></span>
1. <span data-ttu-id="c918f-118">Z listy rozwijanej **Magazyn** wybierz odpowiedni magazyn.</span><span class="sxs-lookup"><span data-stu-id="c918f-118">In the **Warehouse** drop-down list, enter the appropriate warehouse.</span></span>
1. <span data-ttu-id="c918f-119">W polu **Strefa czasowa sklepu** wybierz odpowiednią strefę czasową.</span><span class="sxs-lookup"><span data-stu-id="c918f-119">In the **Store time zone** field, select the appropriate time zone.</span></span>
1. <span data-ttu-id="c918f-120">Z listy rozwijanej **Grupa podatków** wybierz odpowiednią grupę podatków dla sklepu.</span><span class="sxs-lookup"><span data-stu-id="c918f-120">In the **Sales tax group** drop-down list, select an appropriate sales tax group for the store.</span></span>
1. <span data-ttu-id="c918f-121">W polu **Waluta** wybierz odpowiednią walutę.</span><span class="sxs-lookup"><span data-stu-id="c918f-121">In the **Currency** field, select the appropriate currency.</span></span>
1. <span data-ttu-id="c918f-122">W polu **Książka adresowa klienta** podaj prawidłową książkę adresową.</span><span class="sxs-lookup"><span data-stu-id="c918f-122">In the **Customer address book** field, provide a valid address book.</span></span>
1. <span data-ttu-id="c918f-123">W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="c918f-123">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="c918f-124">W polu **Profil funkcji** wybierz profil funkcji, jeśli ma to zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="c918f-124">In the **Functionality profile** field, select a functionality profile if applicable.</span></span>
1. <span data-ttu-id="c918f-125">W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.</span><span class="sxs-lookup"><span data-stu-id="c918f-125">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="c918f-126">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c918f-126">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c918f-127">Poniższy rysunek przedstawia utworzenie nowego kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c918f-127">The following image shows the creation of a new retail channel.</span></span>

![Nowy kanał sprzedaży](media/channel-setup-retail-1.png)

<span data-ttu-id="c918f-129">Poniższy obraz przedstawia przykład kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c918f-129">The following image shows an example retail channel.</span></span>

![Przykład kanału sprzedaży](media/channel-setup-retail-2.png)

## <a name="other-settings"></a><span data-ttu-id="c918f-131">Inne ustawienia</span><span class="sxs-lookup"><span data-stu-id="c918f-131">Other settings</span></span>

<span data-ttu-id="c918f-132">Istnieje wiele innych ustawień opcjonalnych, które można ustawiać w sekcjach **Zestawienie/zamknięcie** i **Różne**, na podstawie potrzeb sklepu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="c918f-132">There are numerous other optional settings that can be set in the **Statement/closing** and **Miscellaneous** sections, based on the needs of the retail store.</span></span>

<span data-ttu-id="c918f-133">Ponadto zapoznaj się z tematami [Układy ekranu dla punktu sprzedaży (POS)](pos-screen-layouts.md), aby uzyskać informacje dotyczące konfigurowania domyślnego układu ekranu w sekcji **Układ ekranu** oraz [Konfigurowanie i instalowanie modułu Retail Hardware Station](retail-hardware-station-configuration-installation.md) z informacjami o konfiguracji w sekcji **Stacje sprzętowe**.</span><span class="sxs-lookup"><span data-stu-id="c918f-133">In addition, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information on setting up the default screen layout in the **Screen layout** section and [Configure and install Retail hardware station](retail-hardware-station-configuration-installation.md) for setup information about the **Hardware stations** section.</span></span>

<span data-ttu-id="c918f-134">Poniższy obraz przedstawia przykład konfiguracji kanału sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="c918f-134">The following image shows an example retail channel setup configuration.</span></span>

![Przykład konfiguracji kanału sprzedaży](media/channel-setup-retail-3.png)

## <a name="additional-channel-set-up"></a><span data-ttu-id="c918f-136">Konfiguracja kanałów dodatkowych</span><span class="sxs-lookup"><span data-stu-id="c918f-136">Additional channel set up</span></span>

<span data-ttu-id="c918f-137">Istnieją dodatkowe pozycje, które należy skonfigurować dla kanału, które można znaleźć w **okienku akcji** w sekcji **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="c918f-137">There are additional items that need to be set up for a channel that can be found on the **Action pane** under the **Set up** section.</span></span>

<span data-ttu-id="c918f-138">Dodatkowe zadania wymagane do konfiguracji kanału online obejmują konfigurowanie metod płatności, deklaracji gotówki, metod dostawy, kont przychodów/wydatków, sekcji, przypisania grupy realizacji i sejfów.</span><span class="sxs-lookup"><span data-stu-id="c918f-138">Additional tasks required for online channel setup include setting up payment methods, cash declaration, modes of delivery, income/expense account, sections, the fulfillment group assignment, and safes.</span></span>

<span data-ttu-id="c918f-139">Na poniższym rysunku przedstawiono różne dodatkowe opcje konfiguracji kanału sprzedaży detalicznej na karcie **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="c918f-139">The following image shows various additional retail channel setup options on the **Set up** tab.</span></span>

![Konfigurowanie kanału](media/channel-setup-retail-4.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="c918f-141">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="c918f-141">Set up payment methods</span></span>

<span data-ttu-id="c918f-142">Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.</span><span class="sxs-lookup"><span data-stu-id="c918f-142">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="c918f-143">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="c918f-143">On the action pane, select the **Set Up** tab, then select **Payment methods**.</span></span>
1. <span data-ttu-id="c918f-144">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-144">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c918f-145">W okienku nawigacji wybierz żądaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="c918f-145">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="c918f-146">W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.</span><span class="sxs-lookup"><span data-stu-id="c918f-146">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="c918f-147">Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.</span><span class="sxs-lookup"><span data-stu-id="c918f-147">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="c918f-148">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c918f-148">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c918f-149">Poniższy obraz przedstawia przykład kart i metod płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="c918f-149">The following image shows an example of a cash payment method.</span></span>

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-cash-declaration"></a><span data-ttu-id="c918f-151">Ustawienia deklaracji gotówki</span><span class="sxs-lookup"><span data-stu-id="c918f-151">Set up cash declaration</span></span>

1. <span data-ttu-id="c918f-152">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Deklaracja gotówki**.</span><span class="sxs-lookup"><span data-stu-id="c918f-152">On the action pane, select the **Set Up** tab, and then select **Cash declaration**.</span></span>
1. <span data-ttu-id="c918f-153">W okienku akcji wybierz opcję **Nowy**, a następnie Utwórz wszystkie zastosowane oznaczenia **Monety** i **Banknoty**.</span><span class="sxs-lookup"><span data-stu-id="c918f-153">On the action pane, select **New**, and then create all **Coin** and **Note** denominations that are applicable.</span></span>

<span data-ttu-id="c918f-154">Poniższy obraz przedstawia przykład kart i deklaracji gotówki.</span><span class="sxs-lookup"><span data-stu-id="c918f-154">The following image shows an example of a cash declaration.</span></span>

![Ustawienia deklaracji gotówki](media/channel-setup-retail-6.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="c918f-156">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="c918f-156">Set up modes of delivery</span></span>

<span data-ttu-id="c918f-157">Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.</span><span class="sxs-lookup"><span data-stu-id="c918f-157">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="c918f-158">Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="c918f-158">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="c918f-159">W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-159">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="c918f-160">W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.</span><span class="sxs-lookup"><span data-stu-id="c918f-160">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="c918f-161">W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał.</span><span class="sxs-lookup"><span data-stu-id="c918f-161">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="c918f-162">Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.</span><span class="sxs-lookup"><span data-stu-id="c918f-162">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="c918f-163">Poniższy obraz przedstawia przykład kart i metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="c918f-163">The following image shows an example of a mode of delivery.</span></span>

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

### <a name="set-up-incomeexpense-account"></a><span data-ttu-id="c918f-165">Konfiguruj konto wpływu/wpłaty lub wpływów/wydatków</span><span class="sxs-lookup"><span data-stu-id="c918f-165">Set up income/expense account</span></span>

<span data-ttu-id="c918f-166">Aby skonfigurować konto wpływów/wydatków, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c918f-166">To set up income/expense account, follow these steps.</span></span>

1. <span data-ttu-id="c918f-167">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Konto wpływów/wydatków**.</span><span class="sxs-lookup"><span data-stu-id="c918f-167">On the action pane, select the **Set Up** tab, and then select **Income/Expense account**.</span></span>
1. <span data-ttu-id="c918f-168">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-168">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c918f-169">W polu **Nazwa** wprowadź nazwę.</span><span class="sxs-lookup"><span data-stu-id="c918f-169">Under **Name**, enter a name.</span></span>
1. <span data-ttu-id="c918f-170">W polu **Wyszukaj nazwę** wprowadź wyszukiwaną nazwę.</span><span class="sxs-lookup"><span data-stu-id="c918f-170">Under **Search name**, enter a search name.</span></span>
1. <span data-ttu-id="c918f-171">Wprowadź typ konta w polu **Typ konta**.</span><span class="sxs-lookup"><span data-stu-id="c918f-171">Under **Account type**, enter the account type.</span></span>
1. <span data-ttu-id="c918f-172">Wprowadź tekst dla **Wiersza wiadomości 1**, **Wiersz wiadomości 2**, **Tekst dokumentu 1** i **Tekst dokumentu 2** w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="c918f-172">Enter text for **Message line 1**, **Message line 2**, **Slip text 1**, and **Slip text 2** as needed.</span></span>
1. <span data-ttu-id="c918f-173">W obszarze **Księgowanie** wprowadź informacje o księgowaniu.</span><span class="sxs-lookup"><span data-stu-id="c918f-173">Under **Posting**, enter posting information.</span></span>
1. <span data-ttu-id="c918f-174">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c918f-174">On the action pane, select **Save**.</span></span>

<span data-ttu-id="c918f-175">Poniższy obraz przedstawia przykład konta wpływów/wydatków.</span><span class="sxs-lookup"><span data-stu-id="c918f-175">The following image shows an example of an income/expense account.</span></span>

![Konfiguruj konta wpływów/wydatków](media/channel-setup-retail-8.png)

### <a name="set-up-sections"></a><span data-ttu-id="c918f-177">Konfigurowanie sekcji</span><span class="sxs-lookup"><span data-stu-id="c918f-177">Set up sections</span></span>

<span data-ttu-id="c918f-178">Aby skonfigurować sekcje, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c918f-178">To set up sections, follow these steps.</span></span>

1. <span data-ttu-id="c918f-179">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sekcje**.</span><span class="sxs-lookup"><span data-stu-id="c918f-179">On the action pane, select the **Set Up** tab and click **Sections**.</span></span>
1. <span data-ttu-id="c918f-180">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-180">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c918f-181">W obszarze **Numer sekcji** wprowadź numer sekcji.</span><span class="sxs-lookup"><span data-stu-id="c918f-181">Under **Section number**, enter a section number.</span></span>
1. <span data-ttu-id="c918f-182">W polu **Opis** wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="c918f-182">Under **Description**, enter a description.</span></span>
1. <span data-ttu-id="c918f-183">W obszarze **Rozmiar sekcji** wprowadź rozmiar sekcji.</span><span class="sxs-lookup"><span data-stu-id="c918f-183">Under **Section size**, enter a section size.</span></span>
1. <span data-ttu-id="c918f-184">W razie potrzeby skonfiguruj dodatkowe ustawienia w **Ogólne** i **Statystka sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="c918f-184">Configure additional settings for **General** and **Sales statistics** as needed.</span></span>
1. <span data-ttu-id="c918f-185">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c918f-185">On the action pane, select **Save**.</span></span>

### <a name="set-up-a-fulfillment-group-assignment"></a><span data-ttu-id="c918f-186">Konfiguracja przypisania grupy realizacji</span><span class="sxs-lookup"><span data-stu-id="c918f-186">Set up a fulfillment group assignment</span></span>

<span data-ttu-id="c918f-187">Aby skonfigurować przypisanie grupy realizacji, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c918f-187">To set up a fulfillment group assignment, follow these steps.</span></span>

1. <span data-ttu-id="c918f-188">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Przypisanie grupy realizacji**.</span><span class="sxs-lookup"><span data-stu-id="c918f-188">On the action pane, select the **Set up** tab, then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="c918f-189">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-189">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c918f-190">Z listy rozwijanej **Grupa realizacji** wybierz grupę realizacja.</span><span class="sxs-lookup"><span data-stu-id="c918f-190">In the **Fulfillment group** drop-down list, select a fulfillment group.</span></span>
1. <span data-ttu-id="c918f-191">Z listy rozwijanej wybierz **Opis wprowadź** i wprowadź opis.</span><span class="sxs-lookup"><span data-stu-id="c918f-191">In the **Description** drop-down list, enter a description.</span></span>
1. <span data-ttu-id="c918f-192">Na okienku akcji wybierz opcję **Zapisz**</span><span class="sxs-lookup"><span data-stu-id="c918f-192">On the action pane, select **Save**</span></span>

<span data-ttu-id="c918f-193">Poniższy obraz przedstawia przykład konfiguracji przypisania grupy realizacji.</span><span class="sxs-lookup"><span data-stu-id="c918f-193">The following image shows an example of a fulfillment group assignment setup.</span></span>

![Konfiguracja przypisań grupy realizacji](media/channel-setup-retail-9.png)

### <a name="set-up-safes"></a><span data-ttu-id="c918f-195">Konfiguracja sejfów</span><span class="sxs-lookup"><span data-stu-id="c918f-195">Set up safes</span></span>

<span data-ttu-id="c918f-196">Aby skonfigurować sejfy, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="c918f-196">To set up safes, follow these steps.</span></span>

1. <span data-ttu-id="c918f-197">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Sejfy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-197">On the action pane, select the **Set Up** tab and click **Safes**.</span></span>
1. <span data-ttu-id="c918f-198">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="c918f-198">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="c918f-199">Wprowadź nazwę sejfu.</span><span class="sxs-lookup"><span data-stu-id="c918f-199">Enter a name for the safe.</span></span>
1. <span data-ttu-id="c918f-200">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="c918f-200">On the action pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c918f-201">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="c918f-201">Additional resources</span></span>

[<span data-ttu-id="c918f-202">Omówienie kanałów</span><span class="sxs-lookup"><span data-stu-id="c918f-202">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="c918f-203">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="c918f-203">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="c918f-204">Konfigurowanie kanału internetowego</span><span class="sxs-lookup"><span data-stu-id="c918f-204">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="c918f-205">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="c918f-205">Set up a call center channel</span></span>](channel-setup-callcenter.md)

