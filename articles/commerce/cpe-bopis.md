---
title: Konfigurowanie BOPIS w środowisku oceny usługi Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania modułu kupowanie online, odbiór w sklepie (BOPIS) w środowisku oceny Microsoft Dynamics 365 Commerce po jego zainicjowaniu.
author: rubendel
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ec1c556a70ed92a40d3cb2bf45fb6156b7dbf7fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993482"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="dd9a8-103">Konfigurowanie BOPIS w środowisku oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dd9a8-103">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dd9a8-104">W tym temacie opisano sposób konfigurowania modułu kupowanie online, odbiór w sklepie (BOPIS) w środowisku oceny Microsoft Dynamics 365 Commerce po zainicjowaniu środowiska.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-104">This topic explains how to configure buy online, pickup in store (BOPIS) in a Microsoft Dynamics 365 Commerce evaluation environment after the environment has been provisioned.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="dd9a8-105">Wymaganie wstępne</span><span class="sxs-lookup"><span data-stu-id="dd9a8-105">Prerequisite</span></span>

<span data-ttu-id="dd9a8-106">Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji i konfiguracji środowiska oceny wersji zapoznawczej usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned and configured.</span></span> <span data-ttu-id="dd9a8-107">Aby uzyskać informacje dotyczące sposobu prowizji i konfigurowania środowiska, zobacz [Inicjowaniw środowiska oceny wersji zapoznawczej Dynamics 365 Commerce](provisioning-guide.md) i [Konfiguracja środowiska oceny wersji zapoznawczej Dynamics 365 Commerce](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span><span class="sxs-lookup"><span data-stu-id="dd9a8-107">For information about how to provision and configure your environment, see [Provision a Dynamics 365 Commerce evaluation environment](provisioning-guide.md) and [Configure a Dynamics 365 Commerce evaluation environment](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span></span>

<span data-ttu-id="dd9a8-108">Po zainicjowaniu obsługi i skonfigurowaniu środowiska Commerce można skorzystać z tego tematu w celu włączenia scenariuszy BOPIS.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-108">After your Commerce environment has been provisioned and configured end to end, you can use this topic to enable BOPIS scenarios.</span></span>

## <a name="configure-the-pos"></a><span data-ttu-id="dd9a8-109">Konfigurowanie punktu sprzedaży POS</span><span class="sxs-lookup"><span data-stu-id="dd9a8-109">Configure the POS</span></span>

### <a name="configure-modern-pos"></a><span data-ttu-id="dd9a8-110">Konfiguracja Modern POS</span><span class="sxs-lookup"><span data-stu-id="dd9a8-110">Configure Modern POS</span></span>

<span data-ttu-id="dd9a8-111">Scenariusze BOPIS, które obejmują płatność kartą kredytową, wymagają stacji sprzętowej.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-111">BOPIS scenarios that involve a credit card payment require a hardware station.</span></span> <span data-ttu-id="dd9a8-112">Stacja sprzętowa jest wbudowana w Modern POS dla systemu Windows i klientach Android.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-112">The hardware station is built into Modern POS for Windows and Android clients.</span></span> <span data-ttu-id="dd9a8-113">Jeśli w systemie iOS jest używany program Cloud POS lub Modern POS, klient punktu sprzedaży (POS) musi być sparowany z udostępnioną stacją sprzętową.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-113">If you're using Cloud POS or Modern POS for iOS, the point of sale (POS) client must be paired with a shared hardware station.</span></span> <span data-ttu-id="dd9a8-114">W tym temacie wyjaśniono, jak skonfigurować BOPIS dla systemu Windows i klientów Android.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-114">This topic explains how to configure BOPIS for Windows and Android clients.</span></span> <span data-ttu-id="dd9a8-115">Aby uzyskać więcej informacji dotyczących sposobu konfiguracji współużytkowanej stacji sprzętowej, zobacz [Konfiguracja i instalacja programu Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="dd9a8-115">For information about how to set up a shared hardware station, see [Configure and install Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span></span>

1. <span data-ttu-id="dd9a8-116">Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Rejestry**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-116">Go to **Retail and Commerce \> Channel setup \> POS setup \> Registers**.</span></span>
2. <span data-ttu-id="dd9a8-117">Wybierz rejestr **SANFRAN-5**, a następnie wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-117">Select register **SANFRAN-5**, and then select **Edit**.</span></span>
3. <span data-ttu-id="dd9a8-118">Zmień wartość pola **Profil sprzętu** z **HW002** na **HW001**, a następnie wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-118">Change the value of the **Hardware profile** field from **HW002** to **HW001**, and then select **Save**.</span></span>
4. <span data-ttu-id="dd9a8-119">Aby zsynchronizować zmiany, przejdź do **Retail i Commerce \> Retail i Commerce — składniki IT \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-119">To synchronize the changes, go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="dd9a8-120">Wybierz harmonogram dystrybucji **1090**, a następnie w okienku akcji wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-120">Select distribution schedule **1090**, and then, on the Action Pane, select **Run now**.</span></span>
6. <span data-ttu-id="dd9a8-121">Wybierz **Tak**, a następnie kliknij przycisk **OK**, aby zainicjować synchronizację danych.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-121">Select **Yes** and then **OK** to initiate data synchronization.</span></span> 

### <a name="install-modern-pos"></a><span data-ttu-id="dd9a8-122">Zainstaluj Modern POS</span><span class="sxs-lookup"><span data-stu-id="dd9a8-122">Install Modern POS</span></span>

1. <span data-ttu-id="dd9a8-123">Wybierz kolejno opcje **Retail i Commerce \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Urządzenia**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-123">Go to **Retail and Commerce \> Channel setup \> POS setup \> Devices**.</span></span>
2. <span data-ttu-id="dd9a8-124">Wybierz urządzenie **SANFRANCIS-5**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-124">Select device **SANFRANCIS-5**.</span></span>
3. <span data-ttu-id="dd9a8-125">W okienku akcji wybierz opcję **Pobierz**, a następnie wybierz opcję **Konfiguracja pliku**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-125">On the Action Pane, select **Download**, and then select **Configuration file**.</span></span>
4. <span data-ttu-id="dd9a8-126">Wybierz kolejno opcje **Pobierz** i **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-126">Select **Download**, and then select **Retail Modern POS**.</span></span> 
5. <span data-ttu-id="dd9a8-127">Po zakończeniu pobierania pliku **ModernPOSSetup.exe** wybierz opcję **Otwórz plik**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-127">When download of the **ModernPOSSetup.exe** file is completed, select **Open file**.</span></span>

    ![Otwórz plik](./dev-itpro/media/PAYMENTS/openfile.png)

6. <span data-ttu-id="dd9a8-129">Wybierz przycisk **Dalej**, aby przejść przez proces instalacji.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-129">Select **Next** to go through the installation process.</span></span> <span data-ttu-id="dd9a8-130">Po zakończeniu instalacji wybierz opcję **Zamknij**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-130">When installation is completed, select **Close**.</span></span>

### <a name="activate-modern-pos"></a><span data-ttu-id="dd9a8-131">Aktywuj Modern POS</span><span class="sxs-lookup"><span data-stu-id="dd9a8-131">Activate Modern POS</span></span>

1. <span data-ttu-id="dd9a8-132">Na pulpicie systemu Windows wybierz przycisk **Start** i wprowadź **Retail Modern POS**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-132">On the Windows desktop, select the **Start** button, and enter **Retail Modern POS**.</span></span>
2. <span data-ttu-id="dd9a8-133">Wybierz aplikację **Retail Modern POS**, aby zainicjować aktywację.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-133">Select the **Retail Modern POS** application to initiate activation.</span></span>
3. <span data-ttu-id="dd9a8-134">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-134">Select **Next**.</span></span> <span data-ttu-id="dd9a8-135">Pola **Adres URL serwera**, **Identyfikator urządzenia** i **Numer rejestru** powinny być wstępnie ustawione przy użyciu informacji z pliku konfiguracji pobranego w poprzedniej procedurze.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-135">The **Server URL**, **Device ID**, and **Register number** fields should be preset by using information from the configuration file that you downloaded in the previous procedure.</span></span>
4. <span data-ttu-id="dd9a8-136">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-136">Select **Activate**.</span></span>
5. <span data-ttu-id="dd9a8-137">Pojawi się okno dialogowe uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-137">An authentication dialog box appears.</span></span> <span data-ttu-id="dd9a8-138">Wybierz konto korzystające z adresu e-mail, który był poprzednio skojarzony z pracownikiem **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-138">Select the account that uses the email address that was previously associated with worker **000713 - Andrew Collette**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dd9a8-139">Jeśli użytkownik nie jest jeszcze skojarzony z tożsamością pracownika, aktywacja nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-139">If you haven't yet associated a worker with your identity, activation will be unsuccessful.</span></span> <span data-ttu-id="dd9a8-140">W takim przypadku należy wykonać kroki opisane w sekcji „Kojarzenie pracownika z Twoją tożsamością” w temacie [Konfigurowanie środowiska oceny wersji zapoznawczej usługi Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).</span><span class="sxs-lookup"><span data-stu-id="dd9a8-140">In this case, follow the steps under the "Associate a worker with your identity" section in the [Configure a Dynamics 365 Commerce evaluation environment](cpe-post-provisioning.md#associate-a-worker-with-your-identity) topic.</span></span>
    
6. <span data-ttu-id="dd9a8-141">Gdy zostanie wyświetlony monit o zarządzanie urządzeniem, wybierz **Tylko ta aplikacja**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-141">When you're prompted to let your organization manage the device, select **This app only**.</span></span>
7. <span data-ttu-id="dd9a8-142">Po zakończeniu aktywacji wybierz opcję **Rozpoczynanie pracy**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-142">When activation is completed, select **Get started**.</span></span>

### <a name="enable-bopis-in-modern-pos"></a><span data-ttu-id="dd9a8-143">Włącz BOPIS w Modern POS</span><span class="sxs-lookup"><span data-stu-id="dd9a8-143">Enable BOPIS in Modern POS</span></span>

1. <span data-ttu-id="dd9a8-144">Zaloguj się do Modern POS, używając **000713** jako identyfikatora operatora i **123** jako hasła.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-144">Sign in to Modern POS by using **000713** as the operator ID and **123** as the password.</span></span>
2. <span data-ttu-id="dd9a8-145">Podczas odtwarzania wideo z instruktażem wprowadzającym należy zaznaczyć dwa pola wyboru w lewym dolnym rogu okna dialogowego, a następnie zamknąć okno dialogowe.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-145">While the introductory walkthrough video is playing, select the two check boxes in the lower-left corner of the dialog box, and then close the dialog box.</span></span>
3. <span data-ttu-id="dd9a8-146">Jeśli nie zostanie wyświetlony monit o zamknięcie zmiany, przewiń tekst do prawej strony **powitalnej**, wybierz opcję **Zamknij zmianę**, a następnie zaloguj się ponownie do punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-146">If you aren't prompted to close the shift, scroll to the right on the **Welcome** page, select **Close shift**, and then sign back in to the POS.</span></span>
4. <span data-ttu-id="dd9a8-147">Po zalogowaniu się, gdy zostanie wyświetlony monit, wybierz opcję **Wykonaj operację bez użycia szuflady**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-147">After you're signed in, when you're prompted, select **Perform a non-drawer operation**.</span></span>
5. <span data-ttu-id="dd9a8-148">Na stronie **powitalnej** przewiń w prawo i wybierz operację **Wybierz stację sprzętową** .</span><span class="sxs-lookup"><span data-stu-id="dd9a8-148">On the **Welcome** page, scroll to the right, and select the **Select hardware station** operation.</span></span>
6. <span data-ttu-id="dd9a8-149">Wybierz **Zarządzaj**, ustaw opcję **Użyj stacji sprzętowej** na **Włączona**, a następnie kliknij **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-149">Select **Manage**, set the **Use hardware station** option to **On**, and then select **OK**.</span></span>
7. <span data-ttu-id="dd9a8-150">Wyloguj się z kasy POS, a następnie ponownie zaloguj.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-150">Sign out of the POS, and then sign back in.</span></span>
8. <span data-ttu-id="dd9a8-151">Po zalogowaniu się wybierz opcję **Otwórz nową zmianę**, a następnie wybierz **Szuflada**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-151">After you're signed in, select **Open a new shift**, and then select **Drawer**.</span></span>

## <a name="complete-a-bopis-scenario"></a><span data-ttu-id="dd9a8-152">Ukończ scenariusz BOPIS</span><span class="sxs-lookup"><span data-stu-id="dd9a8-152">Complete a BOPIS scenario</span></span>

### <a name="create-a-storefront-order-for-in-store-pickup"></a><span data-ttu-id="dd9a8-153">Tworzenie zamówienia sklepu na potrzeby odbioru w sklepie</span><span class="sxs-lookup"><span data-stu-id="dd9a8-153">Create a storefront order for in-store pickup</span></span>

1. <span data-ttu-id="dd9a8-154">Umożliwia przejście do adresu URL, który został określony w kroku [Inicjalizowanie e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) podczas konfigurowania środowiska.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-154">Go to the URL that you specified in the [Initialize e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) step during environment configuration.</span></span>
2. <span data-ttu-id="dd9a8-155">Wybierz towar i wybierz opcję **Dodaj do koszyka**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-155">Select an item, and select **Add to cart**.</span></span>
3. <span data-ttu-id="dd9a8-156">Na stronie koszyka, wybierz **Odbierz tę pozycję** dla dodanego właśnie wiersza zamówienia.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-156">On the shopping bag page, select **Pick this up** for the order line that you just added.</span></span>
4. <span data-ttu-id="dd9a8-157">W oknie dialogowym **Wybierz sklep** wprowadź wartość **San Francisco**, a następnie wybierz przycisk **Wyszukaj**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-157">In the **Select a store** dialog box, enter **San Francisco**, and then select the **Search** button.</span></span>
5. <span data-ttu-id="dd9a8-158">Na liście wyników znajdź sklep Francisco ii wybierz pozycję **Odbierz tu**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-158">In the list of results, find the San Francisco store, and select **Pick up here**.</span></span>
6. <span data-ttu-id="dd9a8-159">Na stronie koszyka wybierz opcję **Realizacja zamówienia jako gość**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-159">On the shopping bag page, select **Checkout as Guest**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="dd9a8-160">Aby kontynuować proces realizacji transakcji, musisz zaakceptować powiadomienie o plikach cookie.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-160">To continue with checkout, you must accept the cookie notice.</span></span> <span data-ttu-id="dd9a8-161">Ta informacja jest wyświetlana jako transparent u góry strony realizacja transakcji.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-161">This notice appears as a banner at the top of the checkout page.</span></span>

7. <span data-ttu-id="dd9a8-162">W przypadku metody płatności kartą kredytową wprowadź następujące informacje:</span><span class="sxs-lookup"><span data-stu-id="dd9a8-162">For the credit card payment method, enter the following details:</span></span>

    - <span data-ttu-id="dd9a8-163">**Nazwa posiadacza karty**: Wprowadź dowolną nazwę.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-163">**Cardholder name:** Enter any name.</span></span>
    - <span data-ttu-id="dd9a8-164">**Numer karty:** Wprowadź **4111-1111-1111-1111**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-164">**Card number:** Enter **4111-1111-1111-1111**.</span></span>
    - <span data-ttu-id="dd9a8-165">**Data ważności:** Wprowadź **10/20**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-165">**Expiration date:** Enter **10/20**.</span></span>
    - <span data-ttu-id="dd9a8-166">**Kod weryfikacji karty (CVV):** Wprowadź **737**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-166">**Card verification value (CVV) code:** Enter **737**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="dd9a8-167">Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-167">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

8. <span data-ttu-id="dd9a8-168">Kontynuuj proces realizacji transakcji, wprowadzając szczegóły adresu fakturowania, a następnie wybierz opcję **Zapisz i kontynuuj**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-168">Continue with checkout by entering details of the billing address, and then select **Save and continue**.</span></span>
9. <span data-ttu-id="dd9a8-169">Gdy zamówienie jest gotowe do umieszczenia, wybierz opcję **Realizacja zamówienia**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-169">When the order is ready to be placed, select **Checkout**.</span></span>

### <a name="synchronize-online-orders-to-the-back-office"></a><span data-ttu-id="dd9a8-170">Synchronizuj zamówienia online w biurze zaplecza</span><span class="sxs-lookup"><span data-stu-id="dd9a8-170">Synchronize online orders to the back office</span></span>

<span data-ttu-id="dd9a8-171">Aby uzyskać informacje na temat synchronizowania zamówień online, zapoznaj się z tematem [Księgowanie sprzedaży i płatności online](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span><span class="sxs-lookup"><span data-stu-id="dd9a8-171">For information about how to synchronize online orders, see [Posting of online sales and payments](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span></span>

### <a name="pick-up-an-order-in-the-store"></a><span data-ttu-id="dd9a8-172">Odbiór zamówienia w sklepie</span><span class="sxs-lookup"><span data-stu-id="dd9a8-172">Pick up an order in the store</span></span>

1. <span data-ttu-id="dd9a8-173">Zaloguj się w kasie POS.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-173">Sign in to the POS.</span></span>
2. <span data-ttu-id="dd9a8-174">Na ekranie **powitalnym** wybierz opcję **Realizacja zamówienia**</span><span class="sxs-lookup"><span data-stu-id="dd9a8-174">On the **Welcome** screen, select **Order fulfillment**</span></span>
3. <span data-ttu-id="dd9a8-175">Na liście towarów do odbioru zaznacz wiersz w zamówieniu, który został umieszczony w trybie online.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-175">In the list of items for pickup, select the line from the order that was placed online.</span></span>
4. <span data-ttu-id="dd9a8-176">Po wybraniu wiersza zamówienia wybierz opcję **Odbierz**.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-176">While the order line is selected, select **Pick up**.</span></span>

    <span data-ttu-id="dd9a8-177">Wiersz towaru jest dodawany do ekranu transakcji, a **$0,00** jest wyświetlane jako saldo należne.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-177">The line item is added to the transaction screen, and **$0.00** is shown as the balance that is due.</span></span>

5. <span data-ttu-id="dd9a8-178">Wybierz saldo należne w wysokości **$0,00** lub wybierz dowolną metodę płatności, aby zawrzeć transakcję.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-178">Select the balance due of **$0.00**, or select any payment method to conclude the transaction.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="dd9a8-179">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="dd9a8-179">Troubleshooting</span></span>

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a><span data-ttu-id="dd9a8-180">Zamówienia online odbierane w punkcie sprzedaży mają niezerowe saldo należne</span><span class="sxs-lookup"><span data-stu-id="dd9a8-180">Online orders that are retrieved in the POS have a non-zero balance due</span></span>

<span data-ttu-id="dd9a8-181">Jeśli zamówienie jest pobierane na potrzeby odbioru w sklepie, jeśli saldo należne nie jest równe 0 (zero), należy się upewnić, że jest używany Modern POS, a stacja sprzętowa jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-181">When an order is retrieved for in-store pickup, if the balance due isn't 0 (zero), make sure that Modern POS is being used, and that the hardware station is active.</span></span> <span data-ttu-id="dd9a8-182">Jeśli jest używane Cloud POS lub Modern POS dla systemu iOS, upewnij się, że udostępniona stacja sprzętowa jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-182">If Cloud POS or Modern POS for iOS is being used, make sure that a shared hardware station is active.</span></span> <span data-ttu-id="dd9a8-183">Niektóre formy aktywnej stacji sprzętowej są wymagane do pobierania płatności, które zostały wprowadzone w trybie online.</span><span class="sxs-lookup"><span data-stu-id="dd9a8-183">Some form of active hardware station is required to retrieve payments that were made online.</span></span>

### <a name="general-issues-with-payment-capture"></a><span data-ttu-id="dd9a8-184">Ogólne problemy z przechwyceniem płatności</span><span class="sxs-lookup"><span data-stu-id="dd9a8-184">General issues with payment capture</span></span>

<span data-ttu-id="dd9a8-185">Aby uzyskać wszystkie ogólne problemy, należy zawsze najpierw zapoznać się z dziennikami zdarzeń Modern POS lub Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="dd9a8-185">For all general issues, you should always consult the Modern POS or Internet Information Services (IIS) Hardware Station event logs as a first step.</span></span> <span data-ttu-id="dd9a8-186">Te dzienniki można znaleźć w następujących węzłach w dzienniku zdarzeń systemu Windows:</span><span class="sxs-lookup"><span data-stu-id="dd9a8-186">You can find these logs under the following nodes in the Windows event log:</span></span>

- <span data-ttu-id="dd9a8-187">Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> Commerce-ModernPOS</span><span class="sxs-lookup"><span data-stu-id="dd9a8-187">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-ModernPOS</span></span>
- <span data-ttu-id="dd9a8-188">Dzienniki aplikacji i usług \> Microsoft \> Dynamics \> Commerce-Hardware Station</span><span class="sxs-lookup"><span data-stu-id="dd9a8-188">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-Hardware Station</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd9a8-189">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="dd9a8-189">Additional resources</span></span>

[<span data-ttu-id="dd9a8-190">Omówienie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dd9a8-190">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="dd9a8-191">Ustanowienie środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dd9a8-191">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="dd9a8-192">Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dd9a8-192">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="dd9a8-193">Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="dd9a8-193">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="dd9a8-194">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="dd9a8-194">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="dd9a8-195">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="dd9a8-195">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="dd9a8-196">Portal Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="dd9a8-196">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="dd9a8-197">Witryna Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="dd9a8-197">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="dd9a8-198">Łącznik płatności Adyen</span><span class="sxs-lookup"><span data-stu-id="dd9a8-198">Adyen payment connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[<span data-ttu-id="dd9a8-199">Zapisywanie instrumentów płatniczych online za pomocą łącznika Adyen</span><span class="sxs-lookup"><span data-stu-id="dd9a8-199">Saving online payment instruments with the Adyen connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[<span data-ttu-id="dd9a8-200">Omówienie płatności wielokanałowych</span><span class="sxs-lookup"><span data-stu-id="dd9a8-200">Omni-channel payments overview</span></span>](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)
