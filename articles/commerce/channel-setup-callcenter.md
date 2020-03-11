---
title: Konfigurowanie kanału biura obsługi
description: W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.openlocfilehash: 42448bd54c00b8642b158f422e17d2b46ee25579
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057886"
---
# <a name="set-up-a-call-center-channel"></a><span data-ttu-id="acf12-103">Konfigurowanie kanału biura obsługi</span><span class="sxs-lookup"><span data-stu-id="acf12-103">Set up a call center channel</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="acf12-104">W tym temacie opisano, jak dodać utworzyć nowy biura obsługi w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="acf12-104">This topic describes how to create a new call center channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="acf12-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="acf12-105">Overview</span></span>

<span data-ttu-id="acf12-106">W Dynamics 365 Commerce biuro obsługi jest typem kanału, który można zdefiniować w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="acf12-106">In Dynamics 365 Commerce, a call center is a type of channel that can be defined in the application.</span></span> <span data-ttu-id="acf12-107">Zdefiniowanie kanału dla jednostek biura obsługi telefonicznej umożliwia systemowi na odtworzenie konkretnych danych i zamówień, które są domyślne dla zamówień sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="acf12-107">Defining a channel for your call center entities allows the system to tie specific data and order processing defaults to sales orders.</span></span> <span data-ttu-id="acf12-108">Firma można zdefiniować wiele kanałów biura obsługi w Commerce.</span><span class="sxs-lookup"><span data-stu-id="acf12-108">A company can define multiple call center channels in Commerce.</span></span> 

<span data-ttu-id="acf12-109">Przed utworzeniem nowego kanału biura obsługi, należy upewnić się, że zakończono [Konfigurowanie wstępnie wymaganych ustawień kanału](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="acf12-109">Before you create a new call center channel, ensure that you have completed the [Channel set up prerequisites](channels-prerequisites.md).</span></span>

## <a name="create-and-configure-a-new-call-center-channel"></a><span data-ttu-id="acf12-110">Utwórz i skonfiguruj nowy kanał biura obsługi</span><span class="sxs-lookup"><span data-stu-id="acf12-110">Create and configure a new call center channel</span></span>

<span data-ttu-id="acf12-111">Aby utworzyć i skonfigurować nowy kanał biura obsługi, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="acf12-111">To create and configure a new call center channel, follow these steps.</span></span>

1. <span data-ttu-id="acf12-112">W okienku nawigacji kliknij kolejno opcje **Moduły \> Kanały  \> Biura obsługi \> Wszystkie biura obsługi**.</span><span class="sxs-lookup"><span data-stu-id="acf12-112">In the navigation pane, go to **Modules \> Channels \> Call centers \> All call centers**.</span></span>
1. <span data-ttu-id="acf12-113">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="acf12-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="acf12-114">W polu **Nazwa** wprowadź nazwę nowego kanału.</span><span class="sxs-lookup"><span data-stu-id="acf12-114">In the **Name** field, provide a name for the new channel.</span></span>
1. <span data-ttu-id="acf12-115">Wybierz odpowiednią **Firmę** z rozwijanego menu.</span><span class="sxs-lookup"><span data-stu-id="acf12-115">Select the appropriate **Legal entity** from the drop down.</span></span>
1. <span data-ttu-id="acf12-116">Wybierz odpowiednią lokalizację **Magazynu** z rozwijanego menu.</span><span class="sxs-lookup"><span data-stu-id="acf12-116">Select the appropriate **Warehouse** location from the drop down.</span></span>
1. <span data-ttu-id="acf12-117">W polu **Domyślny odbiorca** wprowadź prawidłowego domyślnego odbiorcę.</span><span class="sxs-lookup"><span data-stu-id="acf12-117">In the **Default customer** field, provide a valid default customer.</span></span>
1. <span data-ttu-id="acf12-118">W polu **Profil powiadomienia pocztą e-mail** wprowadź prawidłowy profil powiadomienia e-mail.</span><span class="sxs-lookup"><span data-stu-id="acf12-118">In the **Email notification profile** field, provide a valid email notification profile.</span></span>
1. <span data-ttu-id="acf12-119">Podaj kod informacji o **Ręczna zmiana ceny**.</span><span class="sxs-lookup"><span data-stu-id="acf12-119">Provide a **Price override** info code.</span></span> <span data-ttu-id="acf12-120">Uwaga konieczne może być utworzenie najpierw kodu informacyjnego.</span><span class="sxs-lookup"><span data-stu-id="acf12-120">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="acf12-121">Podaj kod informacji o **Kod wstrzymania**.</span><span class="sxs-lookup"><span data-stu-id="acf12-121">Provide a **Hold code** info code.</span></span> <span data-ttu-id="acf12-122">Uwaga konieczne może być utworzenie najpierw kodu informacyjnego.</span><span class="sxs-lookup"><span data-stu-id="acf12-122">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="acf12-123">Podaj kod informacji o **Kredycie**.</span><span class="sxs-lookup"><span data-stu-id="acf12-123">Provide a **Credit** info code.</span></span> <span data-ttu-id="acf12-124">Uwaga konieczne może być utworzenie najpierw kodu informacyjnego.</span><span class="sxs-lookup"><span data-stu-id="acf12-124">Note you may need to create an info code for this first.</span></span>
1. <span data-ttu-id="acf12-125">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="acf12-125">Select **Save**.</span></span>

<span data-ttu-id="acf12-126">Poniższy rysunek przedstawia utworzenie nowego kanału biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="acf12-126">The following image shows the creation of a new call center channel.</span></span>

![Nowy kanał biura obsługi](media/channel-setup-callcenter-1.png)

<span data-ttu-id="acf12-128">Poniższy obraz przedstawia przykład kanału biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="acf12-128">The following image shows an example call center channel.</span></span>

![Przykład kanału biura obsługi](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a><span data-ttu-id="acf12-130">Konfiguracja kanałów dodatkowych</span><span class="sxs-lookup"><span data-stu-id="acf12-130">Additional channel setup</span></span>

<span data-ttu-id="acf12-131">Dodatkowe zadania wymagane dla konfiguracji kanału dla biura obsługi, obejmują Konfigurowanie metod płatności i metod dostawy.</span><span class="sxs-lookup"><span data-stu-id="acf12-131">Additional tasks required for call center channel setup include setting up payment methods and modes of delivery.</span></span>

<span data-ttu-id="acf12-132">Poniższy obraz pokazuje **Metody dostawy** i **Metody płatności** ustaw opcje na karcie **Konfiguracja**.</span><span class="sxs-lookup"><span data-stu-id="acf12-132">The following image shows **Modes of delivery** and **Payment methods** set up options on the **Set up** tab.</span></span>

![Dodatkowe akcje konfiguracji kanału biura obsługi](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a><span data-ttu-id="acf12-134">Konfigurowanie metod płatności</span><span class="sxs-lookup"><span data-stu-id="acf12-134">Set up payment methods</span></span>

<span data-ttu-id="acf12-135">Aby skonfigurować metody płatności, należy wykonać następujące kroki dla każdego typu płatności obsługiwanego w tym kanale.</span><span class="sxs-lookup"><span data-stu-id="acf12-135">To set up payment methods, for each payment type supported on this channel follow these steps.</span></span>

1. <span data-ttu-id="acf12-136">W okienku akcji wybierz kartę **Konfiguracja** i wybierz opcję **Metody płatności**.</span><span class="sxs-lookup"><span data-stu-id="acf12-136">On the action pane, select the **Set up** tab, and then select **Payment methods**.</span></span>
1. <span data-ttu-id="acf12-137">W okienku akcji wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="acf12-137">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="acf12-138">W okienku nawigacji wybierz żądaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="acf12-138">In the navigation pane, select a desired payment method.</span></span>
1. <span data-ttu-id="acf12-139">W sekcji **Ogólne** podaj **Nazwę operacji** i skonfiguruj inne żądane ustawienia.</span><span class="sxs-lookup"><span data-stu-id="acf12-139">In the **General** section, provide an **Operation name** and configure any other desired settings.</span></span>
1. <span data-ttu-id="acf12-140">Umożliwia skonfigurowanie dodatkowych ustawień, które są wymagane dla typu płatności.</span><span class="sxs-lookup"><span data-stu-id="acf12-140">Configure any additional settings as required for the payment type.</span></span>
1. <span data-ttu-id="acf12-141">Na okienku akcji wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="acf12-141">On the action pane, select **Save**.</span></span>

<span data-ttu-id="acf12-142">Poniższy obraz przedstawia przykład kart i metod płatności gotówką.</span><span class="sxs-lookup"><span data-stu-id="acf12-142">The following image shows an example of a cash payment method.</span></span>

![Przykład metod płatności](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a><span data-ttu-id="acf12-144">Ustaw metody dostawy</span><span class="sxs-lookup"><span data-stu-id="acf12-144">Set up modes of delivery</span></span>

<span data-ttu-id="acf12-145">Skonfigurowane metody dostawy można wyświetlić, wybierając opcję **Metody dostawy** na karcie **Konfiguracja** w **okienku akcji**.</span><span class="sxs-lookup"><span data-stu-id="acf12-145">You can see the configured modes of delivery by selecting **Modes of delivery** from the **Set up** tab on the **Action pane**.</span></span>  

<span data-ttu-id="acf12-146">Aby zmienić lub dodać metodę dostawy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="acf12-146">To change or add a mode of delivery, follow these steps.</span></span>

1. <span data-ttu-id="acf12-147">W okienku nawigacji przejdź do **Moduły \> Zarządzanie zapasami \> Metody dostawy**.</span><span class="sxs-lookup"><span data-stu-id="acf12-147">In the navigation pane, go to **Modules \> Inventory management \> Modes of delivery**.</span></span>
1. <span data-ttu-id="acf12-148">W okienku akcji wybierz opcję **nowy**, aby utworzyć nowy tryb dostawy, lub wybierz istniejący tryb.</span><span class="sxs-lookup"><span data-stu-id="acf12-148">On the action pane, select **New** to create a new mode of delivery, or select an existing mode.</span></span>
1. <span data-ttu-id="acf12-149">W sekcji **Kanały sprzedaży** wybierz opcję **Dodaj wiersz**, aby dodać kanał.</span><span class="sxs-lookup"><span data-stu-id="acf12-149">In the **Retail channels** section, select **Add line** to add the channel.</span></span> <span data-ttu-id="acf12-150">Dodawanie kanałów przy użyciu węzłów organizacji zamiast dodawania każdego kanału do każdego z nich może usprawnić dodawanie kanałów.</span><span class="sxs-lookup"><span data-stu-id="acf12-150">Adding channels using organization nodes instead of adding each channel individually can streamline adding channels.</span></span>

<span data-ttu-id="acf12-151">Poniższy obraz przedstawia przykład kart i metodę dostawy.</span><span class="sxs-lookup"><span data-stu-id="acf12-151">The following image shows an example of a mode of delivery.</span></span>

![Ustaw metody dostawy](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a><span data-ttu-id="acf12-153">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="acf12-153">Additional resources</span></span>

[<span data-ttu-id="acf12-154">Wymagania wstępne konfiguracji kanałów</span><span class="sxs-lookup"><span data-stu-id="acf12-154">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="acf12-155">Funkcje sprzedaży przez biuro obsługi</span><span class="sxs-lookup"><span data-stu-id="acf12-155">Call center sales functionality</span></span>](call-center-functionality.md)

[<span data-ttu-id="acf12-156">Konfigurowanie opcji przetwarzania zamówień biura obsługi</span><span class="sxs-lookup"><span data-stu-id="acf12-156">Set up call center order processing options</span></span>](set-up-order-processing-options.md)

[<span data-ttu-id="acf12-157">Katalogi biura obsługi</span><span class="sxs-lookup"><span data-stu-id="acf12-157">Call center catalogs</span></span>](call-center-catalogs.md)

[<span data-ttu-id="acf12-158">Konfigurowanie i używanie alertów o oszustwie</span><span class="sxs-lookup"><span data-stu-id="acf12-158">Set up and work with fraud alerts</span></span>](set-up-fraud-alerts.md)

[<span data-ttu-id="acf12-159">Konfigurowanie programów sprzedaży ciągłej dla biur obsługi</span><span class="sxs-lookup"><span data-stu-id="acf12-159">Set up continuity programs for call centers</span></span>](set-up-continuity-program.md)
