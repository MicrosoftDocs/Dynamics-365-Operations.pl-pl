---
title: Konfiguruj środowisko wersji zapoznawczej usługi Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania środowiska wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 12d3a86698e9250f5d1645de51e0749c8d929f75
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024713"
---
# <a name="configure-a-dynamics-365-commerce-preview-environment"></a><span data-ttu-id="fb97a-103">Konfiguruj środowisko wersji zapoznawczej usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fb97a-103">Configure a Dynamics 365 Commerce preview environment</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fb97a-104">W tym temacie opisano sposób konfigurowania środowiska wersji zapoznawczej aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.</span><span class="sxs-lookup"><span data-stu-id="fb97a-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce preview environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="fb97a-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="fb97a-105">Overview</span></span>

<span data-ttu-id="fb97a-106">Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji środowiska wersji zapoznawczej usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="fb97a-106">Complete the procedures in this topic only after your Commerce preview environment has been provisioned.</span></span> <span data-ttu-id="fb97a-107">Aby uzyskać informacje dotyczące sposobu aprowizowania środowiska wersji zapoznawczej usługi Commerce, zobacz [Aprowizowanie środowiska wersji zapoznawczej usługi Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="fb97a-107">For information about how to provision your Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

<span data-ttu-id="fb97a-108">Po zakończeniu kompleksowej aprowizacji środowiska wersji zapoznawczej usługi Commerce wykonać dodatkowe czynności konfiguracyjne po aprowizacji, aby można było rozpocząć ocenę środowiska.</span><span class="sxs-lookup"><span data-stu-id="fb97a-108">After your Commerce preview environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="fb97a-109">Aby wykonać te kroki, należy użyć usług Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce i Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="fb97a-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce, and Dynamics 365 Retail.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="fb97a-110">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="fb97a-110">Before you start</span></span>

1. <span data-ttu-id="fb97a-111">Zaloguj się do [portalu usługi LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="fb97a-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="fb97a-112">Przejdź do projektu.</span><span class="sxs-lookup"><span data-stu-id="fb97a-112">Go to your project.</span></span>
1. <span data-ttu-id="fb97a-113">W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="fb97a-114">Wybierz swoje środowisko na liście.</span><span class="sxs-lookup"><span data-stu-id="fb97a-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="fb97a-115">W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-115">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="fb97a-116">Wybierz pozycję **Zaloguj**, aby otworzyć menu, i wybierz opcję **Zaloguj do środowiska**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-116">Select **Login** to open a menu, and then select **Log on to environment**.</span></span>
1. <span data-ttu-id="fb97a-117">Upewnij się, że wybrano firmę **USRT** w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="fb97a-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

## <a name="configure-the-point-of-sale-in-lcs"></a><span data-ttu-id="fb97a-118">Konfigurowanie punktu sprzedaży w usłudze LCS</span><span class="sxs-lookup"><span data-stu-id="fb97a-118">Configure the point of sale in LCS</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="fb97a-119">Kojarzenie pracownika z Twoją tożsamością</span><span class="sxs-lookup"><span data-stu-id="fb97a-119">Associate a worker with your identity</span></span>

<span data-ttu-id="fb97a-120">Aby skojarzyć pracownika z tożsamością w usłudze LCS, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fb97a-120">To associate a worker with your identity in LCS, follow these steps.</span></span>

1. <span data-ttu-id="fb97a-121">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail \> Pracownicy etatowi \> Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-121">Use the menu on the left to go to **Modules \> Retail \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="fb97a-122">Na liście znajdź i wybierz następujący rekord: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="fb97a-123">W okienku akcji wybierz pozycję **Retail**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-123">On the Action Pane, select **Retail**.</span></span>
1. <span data-ttu-id="fb97a-124">Wybierz pozycję **Skojarz istniejącą tożsamość**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="fb97a-125">W polu **Adres e-mail** na prawo od pola **Wyszukaj, używając poczty e-mail** wprowadź swój adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="fb97a-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="fb97a-126">Wybierz opcję **Wyszukaj**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-126">Select **Search**.</span></span>
1. <span data-ttu-id="fb97a-127">Wybierz rekord ze swoją nazwą.</span><span class="sxs-lookup"><span data-stu-id="fb97a-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="fb97a-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-128">Select **OK**.</span></span>
1. <span data-ttu-id="fb97a-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="fb97a-130">Aktywować punkt sprzedaży w chmurze</span><span class="sxs-lookup"><span data-stu-id="fb97a-130">Activate Cloud POS</span></span>

<span data-ttu-id="fb97a-131">Aby aktywować punkt sprzedaży chmury w usłudze LCS, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fb97a-131">To activate Cloud POS in LCS, follow these steps.</span></span>

1. <span data-ttu-id="fb97a-132">W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="fb97a-133">Wybierz swoje środowisko na liście.</span><span class="sxs-lookup"><span data-stu-id="fb97a-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="fb97a-134">W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Pełne szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-134">In the environment information on the right, select **Full details**.</span></span>
1. <span data-ttu-id="fb97a-135">Wybierz pozycję **Zaloguj**, aby otworzyć menu, a następnie wybierz pozycję **Zaloguj się do punktu sprzedaży chmury**, aby otworzyć punkt sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fb97a-135">Select **Login** to open a menu, and then select **Log on to Cloud Point of Sale** to open the point of sale (POS).</span></span>
1. <span data-ttu-id="fb97a-136">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-136">Select **Next**.</span></span>
1. <span data-ttu-id="fb97a-137">Zaloguj się przy użyciu konta usługi Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="fb97a-137">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="fb97a-138">W polu **Nazwa sklepu** wybierz opcję **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-138">Under **Store name**, select **San Francisco**.</span></span>
1. <span data-ttu-id="fb97a-139">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-139">Select **Next**.</span></span>
1. <span data-ttu-id="fb97a-140">W obszarze **Rejestr i urządzenie** wybierz opcję **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="fb97a-141">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-141">Select **Activate**.</span></span> <span data-ttu-id="fb97a-142">Nastąpi wylogowanie i przeniesienia na stronę logowania w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="fb97a-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="fb97a-143">Teraz możesz zalogować się do środowiska punktu sprzedaży w chmurze przy użyciu identyfikatora operatora **000713** i hasła **123**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="fb97a-144">Konfigurowanie witryny w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="fb97a-144">Set up your site in Commerce</span></span>

<span data-ttu-id="fb97a-145">Aby rozpocząć konfigurowanie witryny w wersji zapoznawczej w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fb97a-145">To start to set up your preview site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="fb97a-146">Zaloguj się do narzędzia do zarządzania witryną przy użyciu adresu URL zanotowanego podczas inicjowania usługi e-Commerce w trakcie aprowizacji (zobacz [Inicjowanie usługi e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="fb97a-146">Sign in to the site management tool by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="fb97a-147">Wybierz witrynę **Fabrikam**, aby otworzyć okno dialogowe konfiguracji witryny.</span><span class="sxs-lookup"><span data-stu-id="fb97a-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="fb97a-148">Wybierz domenę, która została wprowadzona podczas inicjowania aplikacji e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="fb97a-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="fb97a-149">Wybierz opcję **Rozszerzony sklep online Fabrikam** jako kanał domyślny.</span><span class="sxs-lookup"><span data-stu-id="fb97a-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="fb97a-150">(Upewnij się, że wybrano **rozszerzony** sklep internetowy).</span><span class="sxs-lookup"><span data-stu-id="fb97a-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="fb97a-151">Wybierz wartość **en-us** jako język domyślny.</span><span class="sxs-lookup"><span data-stu-id="fb97a-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="fb97a-152">Pozostaw niezmienioną wartość pola **Ścieżka**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="fb97a-153">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-153">Select **OK**.</span></span> <span data-ttu-id="fb97a-154">Zostanie wyświetlona lista stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="fb97a-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs-in-retail"></a><span data-ttu-id="fb97a-155">Włączanie zadań w aplikacji Retail</span><span class="sxs-lookup"><span data-stu-id="fb97a-155">Enable jobs in Retail</span></span>

<span data-ttu-id="fb97a-156">Aby włączyć zadania w aplikacji Retail, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fb97a-156">To enable jobs in Retail, follow these steps.</span></span>

1. <span data-ttu-id="fb97a-157">Zaloguj się do środowiska (HQ).</span><span class="sxs-lookup"><span data-stu-id="fb97a-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="fb97a-158">Korzystając z menu po lewej stronie, przejdź do pozycji **Retail \> Zapytania i raporty \> Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-158">Use the menu on the left to go to **Retail \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="fb97a-159">Pozostałe kroki tej procedury muszą zostać zakończone dla każdego z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="fb97a-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="fb97a-160">Przetwarzanie powiadomień pocztą e-mail dla zamówienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="fb97a-160">Process retail order email notification</span></span>
    * <span data-ttu-id="fb97a-161">Dostępność produktu</span><span class="sxs-lookup"><span data-stu-id="fb97a-161">Product availability</span></span>
    * <span data-ttu-id="fb97a-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="fb97a-162">P-0001</span></span>
    * <span data-ttu-id="fb97a-163">Zadanie synchronizowania zamówień</span><span class="sxs-lookup"><span data-stu-id="fb97a-163">Synchronize orders job</span></span>

1. <span data-ttu-id="fb97a-164">Użyj szybkiego filtru, aby wyszukać zadanie według nazwy.</span><span class="sxs-lookup"><span data-stu-id="fb97a-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="fb97a-165">Jeśli stan zadania to **Wstrzymane**, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="fb97a-165">If the status of the job is **Withhold**, follow these steps:</span></span>

    1. <span data-ttu-id="fb97a-166">Wybierz rekord.</span><span class="sxs-lookup"><span data-stu-id="fb97a-166">Select the record.</span></span>
    1. <span data-ttu-id="fb97a-167">W okienku akcji na karcie **Zadanie wsadowe** wybierz pozycję **Zmień status**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="fb97a-168">Wybierz pozycję **Oczekiwanie** i kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-168">Select **Waiting**, and then select **OK**.</span></span>

### <a name="run-full-data-synchronization-in-retail"></a><span data-ttu-id="fb97a-169">Uruchamianie pełnej synchronizacji danych w aplikacji Retail</span><span class="sxs-lookup"><span data-stu-id="fb97a-169">Run full data synchronization in Retail</span></span>

<span data-ttu-id="fb97a-170">Aby uruchomić pełną synchronizację danych w aplikacji Retail, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fb97a-170">To run full data synchronization in Retail, follow these steps.</span></span>

1. <span data-ttu-id="fb97a-171">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Baza danych kanału**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-171">Use the menu on the left to go to **Modules \> Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="fb97a-172">Na liście po lewej stronie jest wybrany kanał **domyślny**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-172">In the list on the left, the **Default** channel is selected.</span></span> <span data-ttu-id="fb97a-173">Wybierz inny dostępny kanał.</span><span class="sxs-lookup"><span data-stu-id="fb97a-173">Select the other available channel.</span></span> <span data-ttu-id="fb97a-174">Ten kanał nosi nazwę **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-174">This channel is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="fb97a-175">W okienku akcji wybierz **Pełna synchronizacja danych**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-175">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="fb97a-176">Wpisz **9999** jako harmonogram dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="fb97a-176">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="fb97a-177">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-177">Select **OK**.</span></span>
1. <span data-ttu-id="fb97a-178">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb97a-178">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="fb97a-179">Testowanie informacji o karcie kredytowej w celu dokonania zakupów testowych</span><span class="sxs-lookup"><span data-stu-id="fb97a-179">Test credit card information to do test purchases</span></span>

<span data-ttu-id="fb97a-180">Aby przeprowadzić transakcje testowe w witrynie, można użyć następujących testowych informacji o karcie kredytowej:</span><span class="sxs-lookup"><span data-stu-id="fb97a-180">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="fb97a-181">**Numer karty:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="fb97a-181">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="fb97a-182">**Data ważności:** 10/20</span><span class="sxs-lookup"><span data-stu-id="fb97a-182">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="fb97a-183">**Kod wartości weryfikacji karty (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="fb97a-183">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb97a-184">Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.</span><span class="sxs-lookup"><span data-stu-id="fb97a-184">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb97a-185">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="fb97a-185">Next steps</span></span>

<span data-ttu-id="fb97a-186">Po zakończeniu aprowizowania i wykonaniu kroków konfiguracji można przystąpić do oceny środowiska wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="fb97a-186">After the provisioning and configuration steps are completed, you're ready to evaluate your preview environment.</span></span> <span data-ttu-id="fb97a-187">Użyj adresu URL narzędzia do zarządzania witryną Commerce, aby przejść do środowiska tworzenia.</span><span class="sxs-lookup"><span data-stu-id="fb97a-187">Use the URL of the Commerce site management tool to go to the authoring experience.</span></span> <span data-ttu-id="fb97a-188">Użyj adresu URL witryny Commerce, aby przejść do środowiska witryny klienta platformy handlu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="fb97a-188">Use the URL of the Commerce site to go to the retail customer site experience.</span></span>

<span data-ttu-id="fb97a-189">Aby skonfigurować opcjonalne funkcje środowiska wersji zapoznawczej usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska wersji zapoznawczej usługi Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="fb97a-189">To configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb97a-190">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fb97a-190">Additional resources</span></span>

[<span data-ttu-id="fb97a-191">Dynamics 365 Commerce omówienie środowiska wersji zapoznawczej</span><span class="sxs-lookup"><span data-stu-id="fb97a-191">Dynamics 365 Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="fb97a-192">Inicjuj środowisko wersji zapoznawczej Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fb97a-192">Provision a Dynamics 365 Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="fb97a-193">Konfiguruj funkcje opcjonalne środowiska wersji zapoznawczej usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fb97a-193">Configure optional features for a Dynamics 365 Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="fb97a-194">Środowisko wersji zapoznawczej Dynamics 365 Commerce— często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="fb97a-194">Dynamics 365 Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="fb97a-195">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="fb97a-195">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="fb97a-196">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="fb97a-196">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="fb97a-197">Portal Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="fb97a-197">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="fb97a-198">Witryna Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fb97a-198">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
