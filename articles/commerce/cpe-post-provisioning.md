---
title: Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.
author: psimolin
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b291a6515c6a3ae7382ea2ad8024ca036489de19
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2021
ms.locfileid: "5937045"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="9526b-103">Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9526b-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9526b-104">W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.</span><span class="sxs-lookup"><span data-stu-id="9526b-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

<span data-ttu-id="9526b-105">Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji środowiska oceny usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="9526b-105">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="9526b-106">Aby uzyskać informacje dotyczące sposobu aprowizowania środowiska oceny usługi Commerce, zobacz [Aprowizowanie środowiska oceny usługi Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="9526b-106">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="9526b-107">Po zakończeniu kompleksowej aprowizacji środowiska oceny usługi Commerce wykonać dodatkowe czynności konfiguracyjne po aprowizacji, aby można było rozpocząć ocenę środowiska.</span><span class="sxs-lookup"><span data-stu-id="9526b-107">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="9526b-108">Aby wykonać te kroki, należy użyć usług Microsoft Dynamics Lifecycle Services (LCS) i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9526b-108">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9526b-109">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="9526b-109">Before you start</span></span>

1. <span data-ttu-id="9526b-110">Zaloguj się do [portalu usługi LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="9526b-110">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="9526b-111">Przejdź do projektu.</span><span class="sxs-lookup"><span data-stu-id="9526b-111">Go to your project.</span></span>
1. <span data-ttu-id="9526b-112">W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="9526b-112">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="9526b-113">Wybierz swoje środowisko na liście.</span><span class="sxs-lookup"><span data-stu-id="9526b-113">Select your environment in the list.</span></span>
1. <span data-ttu-id="9526b-114">W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do środowiska**.</span><span class="sxs-lookup"><span data-stu-id="9526b-114">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="9526b-115">Nastąpi wysłanie do modułu Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="9526b-115">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="9526b-116">Upewnij się, że wybrano firmę **USRT** w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="9526b-116">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="9526b-117">Podczas wykonywania działań związanych z inicjowaniem obsługi administracyjnej w module Commerce Headquarter należy się upewnić, że firma **USRT** jest zawsze zaznaczona.</span><span class="sxs-lookup"><span data-stu-id="9526b-117">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="9526b-118">Konfigurowanie punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9526b-118">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="9526b-119">Kojarzenie pracownika z Twoją tożsamością</span><span class="sxs-lookup"><span data-stu-id="9526b-119">Associate a worker with your identity</span></span>

<span data-ttu-id="9526b-120">Aby skojarzyć pracownika z tożsamością, wykonaj następujące kroki w Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="9526b-120">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="9526b-121">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Pracownicy etatowi \> Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="9526b-121">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="9526b-122">Na liście znajdź i wybierz następujący rekord: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="9526b-122">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="9526b-123">W okienku akcji wybierz **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="9526b-123">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="9526b-124">Wybierz pozycję **Skojarz istniejącą tożsamość**.</span><span class="sxs-lookup"><span data-stu-id="9526b-124">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="9526b-125">W polu **Adres e-mail** na prawo od pola **Wyszukaj, używając poczty e-mail** wprowadź swój adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="9526b-125">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="9526b-126">Wybierz opcję **Wyszukaj**.</span><span class="sxs-lookup"><span data-stu-id="9526b-126">Select **Search**.</span></span>
1. <span data-ttu-id="9526b-127">Wybierz rekord ze swoją nazwą.</span><span class="sxs-lookup"><span data-stu-id="9526b-127">Select the record that has your name.</span></span>
1. <span data-ttu-id="9526b-128">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9526b-128">Select **OK**.</span></span>
1. <span data-ttu-id="9526b-129">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="9526b-129">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="9526b-130">Aktywować punkt sprzedaży w chmurze</span><span class="sxs-lookup"><span data-stu-id="9526b-130">Activate Cloud POS</span></span>

<span data-ttu-id="9526b-131">Aby aktywować punkt sprzedaży chmury, wykonaj następujące kroki w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="9526b-131">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="9526b-132">W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="9526b-132">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="9526b-133">Wybierz swoje środowisko na liście.</span><span class="sxs-lookup"><span data-stu-id="9526b-133">Select your environment in the list.</span></span>
1. <span data-ttu-id="9526b-134">W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do punktu sprzedaży w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="9526b-134">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="9526b-135">Wybierz przycisk **Dalej**, aby otworzyć okno dialogowe **Przed rozpoczęciem**.</span><span class="sxs-lookup"><span data-stu-id="9526b-135">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="9526b-136">Pole **Serwer URL** powinno pozostać niezmienione.</span><span class="sxs-lookup"><span data-stu-id="9526b-136">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="9526b-137">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="9526b-137">Select **Next**.</span></span>
1. <span data-ttu-id="9526b-138">Zaloguj się przy użyciu konta usługi Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9526b-138">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="9526b-139">W polu **Nazwa sklepu** wybierz opcję **San Francisco**, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="9526b-139">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="9526b-140">W obszarze **Rejestr i urządzenie** wybierz opcję **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="9526b-140">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="9526b-141">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="9526b-141">Select **Activate**.</span></span> <span data-ttu-id="9526b-142">Nastąpi wylogowanie i przeniesienia na stronę logowania w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="9526b-142">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="9526b-143">Teraz możesz zalogować się do środowiska punktu sprzedaży w chmurze przy użyciu identyfikatora operatora **000713** i hasła **123**.</span><span class="sxs-lookup"><span data-stu-id="9526b-143">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="9526b-144">Konfigurowanie witryny w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="9526b-144">Set up your site in Commerce</span></span>

<span data-ttu-id="9526b-145">Aby rozpocząć konfigurowanie witryny oceny w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="9526b-145">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="9526b-146">Zaloguj się do konstruktora witryny przy użyciu adresu URL zanotowanego podczas inicjowania usługi handlu elektronicznego w trakcie aprowizacji (zobacz [Inicjowanie usługi handlu elektronicznego](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="9526b-146">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="9526b-147">Wybierz witrynę **Fabrikam**, aby otworzyć okno dialogowe konfiguracji witryny.</span><span class="sxs-lookup"><span data-stu-id="9526b-147">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="9526b-148">Wybierz domenę, która została wprowadzona podczas inicjowania aplikacji e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="9526b-148">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="9526b-149">Wybierz opcję **Rozszerzony sklep online Fabrikam** jako kanał domyślny.</span><span class="sxs-lookup"><span data-stu-id="9526b-149">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="9526b-150">(Upewnij się, że wybrano **rozszerzony** sklep internetowy).</span><span class="sxs-lookup"><span data-stu-id="9526b-150">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="9526b-151">Wybierz wartość **en-us** jako język domyślny.</span><span class="sxs-lookup"><span data-stu-id="9526b-151">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="9526b-152">Pozostaw niezmienioną wartość pola **Ścieżka**.</span><span class="sxs-lookup"><span data-stu-id="9526b-152">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="9526b-153">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9526b-153">Select **OK**.</span></span> <span data-ttu-id="9526b-154">Zostanie wyświetlona lista stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="9526b-154">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="9526b-155">Włącz zadania</span><span class="sxs-lookup"><span data-stu-id="9526b-155">Enable jobs</span></span>

<span data-ttu-id="9526b-156">Aby włączyć zadania w aplikacji Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="9526b-156">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="9526b-157">Zaloguj się do środowiska (HQ).</span><span class="sxs-lookup"><span data-stu-id="9526b-157">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="9526b-158">Korzystając z menu po lewej stronie, przejdź do pozycji **Retail i Commerce \> Zapytania i raporty \> Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="9526b-158">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="9526b-159">Pozostałe kroki tej procedury muszą zostać zakończone dla każdego z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="9526b-159">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="9526b-160">Przetwarzanie powiadomień pocztą e-mail dla zamówienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9526b-160">Process retail order email notification</span></span>
    * <span data-ttu-id="9526b-161">Dostępność produktu</span><span class="sxs-lookup"><span data-stu-id="9526b-161">Product availability</span></span>
    * <span data-ttu-id="9526b-162">P-0001</span><span class="sxs-lookup"><span data-stu-id="9526b-162">P-0001</span></span>
    * <span data-ttu-id="9526b-163">Zadanie synchronizowania zamówień</span><span class="sxs-lookup"><span data-stu-id="9526b-163">Synchronize orders job</span></span>

1. <span data-ttu-id="9526b-164">Użyj szybkiego filtru, aby wyszukać zadanie według nazwy.</span><span class="sxs-lookup"><span data-stu-id="9526b-164">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="9526b-165">Jeśli stan zadania to **W trakcie**, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9526b-165">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="9526b-166">Wybierz rekord.</span><span class="sxs-lookup"><span data-stu-id="9526b-166">Select the record.</span></span>
    1. <span data-ttu-id="9526b-167">W okienku akcji na karcie **Zadanie wsadowe** wybierz pozycję **Zmień status**.</span><span class="sxs-lookup"><span data-stu-id="9526b-167">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="9526b-168">Wybierz pozycję **Anuluj**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9526b-168">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="9526b-169">Opcjonalnie można również określić interwał cyklu równy jednej (1) minucie dla następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="9526b-169">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="9526b-170">Przetwarzanie zadania powiadomień pocztą e-mail dla zamówienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="9526b-170">Process retail order email notification job</span></span>
* <span data-ttu-id="9526b-171">Zadanie P-0001</span><span class="sxs-lookup"><span data-stu-id="9526b-171">P-0001 job</span></span>
* <span data-ttu-id="9526b-172">Zadanie synchronizowania zamówień</span><span class="sxs-lookup"><span data-stu-id="9526b-172">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="9526b-173">Uruchamianie pełnej synchronizacji danych</span><span class="sxs-lookup"><span data-stu-id="9526b-173">Run full data synchronization</span></span>

<span data-ttu-id="9526b-174">Aby uruchomić pełną synchronizację danych w aplikacji Commerce, wykonaj następujące kroki w Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="9526b-174">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="9526b-175">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Handel detaliczny i inny \> Ustawienia centrali \> Transfer danych w Commerce \> Baza danych kanału**.</span><span class="sxs-lookup"><span data-stu-id="9526b-175">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="9526b-176">Wybierz kanał o nazwie **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="9526b-176">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="9526b-177">W okienku akcji wybierz **Pełna synchronizacja danych**.</span><span class="sxs-lookup"><span data-stu-id="9526b-177">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="9526b-178">Wpisz **9999** jako harmonogram dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="9526b-178">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="9526b-179">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9526b-179">Select **OK**.</span></span>
1. <span data-ttu-id="9526b-180">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="9526b-180">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="9526b-181">Testowanie informacji o karcie kredytowej w celu dokonania zakupów testowych</span><span class="sxs-lookup"><span data-stu-id="9526b-181">Test credit card information to do test purchases</span></span>

<span data-ttu-id="9526b-182">Aby przeprowadzić transakcje testowe w witrynie, można użyć następujących testowych informacji o karcie kredytowej:</span><span class="sxs-lookup"><span data-stu-id="9526b-182">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="9526b-183">**Numer karty:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="9526b-183">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="9526b-184">**Data ważności:** 10/20</span><span class="sxs-lookup"><span data-stu-id="9526b-184">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="9526b-185">**Kod wartości weryfikacji karty (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="9526b-185">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9526b-186">Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.</span><span class="sxs-lookup"><span data-stu-id="9526b-186">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9526b-187">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="9526b-187">Next steps</span></span>

<span data-ttu-id="9526b-188">Po zakończeniu czynności obsługi administracyjnej i konfiguracji można rozpocząć korzystanie ze środowiska oceny.</span><span class="sxs-lookup"><span data-stu-id="9526b-188">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="9526b-189">Użyj adresu URL konstruktora witryn Commerce, aby przejść do środowiska tworzenia.</span><span class="sxs-lookup"><span data-stu-id="9526b-189">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="9526b-190">Użyj adresu URL witryny Commerce, aby przejść do środowiska witryny klienta platformy handlu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="9526b-190">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="9526b-191">Aby skonfigurować opcjonalne funkcje środowiska oceny usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska oceny usługi Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="9526b-191">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9526b-192">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="9526b-192">Additional resources</span></span>

[<span data-ttu-id="9526b-193">Omówienie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9526b-193">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="9526b-194">Ustanowienie środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9526b-194">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="9526b-195">Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9526b-195">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="9526b-196">Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9526b-196">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="9526b-197">Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="9526b-197">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="9526b-198">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="9526b-198">Microsoft Lifecycle Services (LCS)</span></span>](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="9526b-199">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="9526b-199">Retail Cloud Scale Unit (RCSU)</span></span>](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="9526b-200">Portal Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="9526b-200">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="9526b-201">Witryna Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="9526b-201">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]