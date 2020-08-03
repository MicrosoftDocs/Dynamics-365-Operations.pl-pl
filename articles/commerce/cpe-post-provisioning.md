---
title: Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce
description: W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.
author: psimolin
manager: annbe
ms.date: 07/16/2020
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
ms.openlocfilehash: 6a1ae960f0f530104af7bdea9a8fcb78b01571f5
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599731"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="8319d-103">Konfigurowanie środowiska oceny rozwiązania Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8319d-103">Configure a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8319d-104">W tym temacie opisano sposób konfigurowania środowiska oceny aplikacji Microsoft Dynamics 365 Commerce po jego aprowizacji.</span><span class="sxs-lookup"><span data-stu-id="8319d-104">This topic explains how to configure a Microsoft Dynamics 365 Commerce evaluation environment after it's provisioned.</span></span>

## <a name="overview"></a><span data-ttu-id="8319d-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="8319d-105">Overview</span></span>

<span data-ttu-id="8319d-106">Procedury opisane w tym temacie należy wykonać dopiero po zakończeniu aprowizacji środowiska oceny usługi Commerce.</span><span class="sxs-lookup"><span data-stu-id="8319d-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned.</span></span> <span data-ttu-id="8319d-107">Aby uzyskać informacje dotyczące sposobu aprowizowania środowiska oceny usługi Commerce, zobacz [Aprowizowanie środowiska oceny usługi Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="8319d-107">For information about how to provision your Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

<span data-ttu-id="8319d-108">Po zakończeniu kompleksowej aprowizacji środowiska oceny usługi Commerce wykonać dodatkowe czynności konfiguracyjne po aprowizacji, aby można było rozpocząć ocenę środowiska.</span><span class="sxs-lookup"><span data-stu-id="8319d-108">After your Commerce evaluation environment has been provisioned end to end, additional post-provisioning configuration steps must be completed before you can start to evaluate the environment.</span></span> <span data-ttu-id="8319d-109">Aby wykonać te kroki, należy użyć usług Microsoft Dynamics Lifecycle Services (LCS) i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8319d-109">To complete these steps, you must use Microsoft Dynamics Lifecycle Services (LCS) and Dynamics 365 Commerce.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="8319d-110">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="8319d-110">Before you start</span></span>

1. <span data-ttu-id="8319d-111">Zaloguj się do [portalu usługi LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8319d-111">Sign in to the [LCS portal](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="8319d-112">Przejdź do projektu.</span><span class="sxs-lookup"><span data-stu-id="8319d-112">Go to your project.</span></span>
1. <span data-ttu-id="8319d-113">W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="8319d-113">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="8319d-114">Wybierz swoje środowisko na liście.</span><span class="sxs-lookup"><span data-stu-id="8319d-114">Select your environment in the list.</span></span>
1. <span data-ttu-id="8319d-115">W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do środowiska**.</span><span class="sxs-lookup"><span data-stu-id="8319d-115">In the environment information on the right, select **Log on to environment**.</span></span> <span data-ttu-id="8319d-116">Nastąpi wysłanie do modułu Commerce Headquarter.</span><span class="sxs-lookup"><span data-stu-id="8319d-116">You will be sent to Commerce headquarters.</span></span>
1. <span data-ttu-id="8319d-117">Upewnij się, że wybrano firmę **USRT** w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="8319d-117">Make sure that the **USRT** legal entity is selected in the upper-right corner.</span></span>

<span data-ttu-id="8319d-118">Podczas wykonywania działań związanych z inicjowaniem obsługi administracyjnej w module Commerce Headquarter należy się upewnić, że firma **USRT** jest zawsze zaznaczona.</span><span class="sxs-lookup"><span data-stu-id="8319d-118">During post-provisioning activities in Commerce headquarters, make sure that the **USRT** legal entity is always selected.</span></span>

## <a name="configure-the-point-of-sale"></a><span data-ttu-id="8319d-119">Konfigurowanie punktu sprzedaży</span><span class="sxs-lookup"><span data-stu-id="8319d-119">Configure the point of sale</span></span>

### <a name="associate-a-worker-with-your-identity"></a><span data-ttu-id="8319d-120">Kojarzenie pracownika z Twoją tożsamością</span><span class="sxs-lookup"><span data-stu-id="8319d-120">Associate a worker with your identity</span></span>

<span data-ttu-id="8319d-121">Aby skojarzyć pracownika z tożsamością, wykonaj następujące kroki w Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="8319d-121">To associate a worker with your identity, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="8319d-122">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Retail i Commerce \> Pracownicy etatowi \> Pracownicy**.</span><span class="sxs-lookup"><span data-stu-id="8319d-122">Use the menu on the left to go to **Modules \> Retail and commerce \> Employees \> Workers**.</span></span>
1. <span data-ttu-id="8319d-123">Na liście znajdź i wybierz następujący rekord: **000713 - Andrew Collette**.</span><span class="sxs-lookup"><span data-stu-id="8319d-123">In the list, find and select the following record: **000713 - Andrew Collette**.</span></span>
1. <span data-ttu-id="8319d-124">W okienku akcji wybierz **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="8319d-124">On the Action Pane, select **Commerce**.</span></span>
1. <span data-ttu-id="8319d-125">Wybierz pozycję **Skojarz istniejącą tożsamość**.</span><span class="sxs-lookup"><span data-stu-id="8319d-125">Select **Associate existing identity**.</span></span>
1. <span data-ttu-id="8319d-126">W polu **Adres e-mail** na prawo od pola **Wyszukaj, używając poczty e-mail** wprowadź swój adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="8319d-126">In the **Email** field to the right of **Search using email**, enter your email address.</span></span>
1. <span data-ttu-id="8319d-127">Wybierz opcję **Wyszukaj**.</span><span class="sxs-lookup"><span data-stu-id="8319d-127">Select **Search**.</span></span>
1. <span data-ttu-id="8319d-128">Wybierz rekord ze swoją nazwą.</span><span class="sxs-lookup"><span data-stu-id="8319d-128">Select the record that has your name.</span></span>
1. <span data-ttu-id="8319d-129">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8319d-129">Select **OK**.</span></span>
1. <span data-ttu-id="8319d-130">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="8319d-130">Select **Save**.</span></span>

### <a name="activate-cloud-pos"></a><span data-ttu-id="8319d-131">Aktywować punkt sprzedaży w chmurze</span><span class="sxs-lookup"><span data-stu-id="8319d-131">Activate Cloud POS</span></span>

<span data-ttu-id="8319d-132">Aby aktywować punkt sprzedaży chmury, wykonaj następujące kroki w usłudze LCS.</span><span class="sxs-lookup"><span data-stu-id="8319d-132">To activate Cloud POS, follow these steps in LCS.</span></span>

1. <span data-ttu-id="8319d-133">W menu górnym wybierz opcję **Środowiska hostowane w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="8319d-133">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="8319d-134">Wybierz swoje środowisko na liście.</span><span class="sxs-lookup"><span data-stu-id="8319d-134">Select your environment in the list.</span></span>
1. <span data-ttu-id="8319d-135">W obszarze informacji o środowisku po prawej stronie wybierz pozycję **Zaloguj do punktu sprzedaży w chmurze**.</span><span class="sxs-lookup"><span data-stu-id="8319d-135">In the environment information on the right, select **Log on to Cloud Point of Sale**.</span></span>
1. <span data-ttu-id="8319d-136">Wybierz przycisk **Dalej**, aby otworzyć okno dialogowe **Przed rozpoczęciem**.</span><span class="sxs-lookup"><span data-stu-id="8319d-136">Select **Next** to open the **Before you start** dialog box.</span></span>
1. <span data-ttu-id="8319d-137">Pole **Serwer URL** powinno pozostać niezmienione.</span><span class="sxs-lookup"><span data-stu-id="8319d-137">Leave the **Server URL** field as it is.</span></span> <span data-ttu-id="8319d-138">Wybierz pozycję **Następny**.</span><span class="sxs-lookup"><span data-stu-id="8319d-138">Select **Next**.</span></span>
1. <span data-ttu-id="8319d-139">Zaloguj się przy użyciu konta usługi Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8319d-139">Sign in by using your Microsoft Azure Active Directory (Azure AD) account.</span></span>
1. <span data-ttu-id="8319d-140">W polu **Nazwa sklepu** wybierz opcję **San Francisco**, a następnie wybierz przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="8319d-140">Under **Store name**, select **San Francisco**, and then select **Next**.</span></span>
1. <span data-ttu-id="8319d-141">W obszarze **Rejestr i urządzenie** wybierz opcję **SANFRAN-1**.</span><span class="sxs-lookup"><span data-stu-id="8319d-141">Under **Register and device**, select **SANFRAN-1**.</span></span>
1. <span data-ttu-id="8319d-142">Wybierz **Aktywuj**.</span><span class="sxs-lookup"><span data-stu-id="8319d-142">Select **Activate**.</span></span> <span data-ttu-id="8319d-143">Nastąpi wylogowanie i przeniesienia na stronę logowania w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="8319d-143">You're signed out and taken to the POS sign-in page.</span></span>
1. <span data-ttu-id="8319d-144">Teraz możesz zalogować się do środowiska punktu sprzedaży w chmurze przy użyciu identyfikatora operatora **000713** i hasła **123**.</span><span class="sxs-lookup"><span data-stu-id="8319d-144">You can now sign in to the Cloud POS experience by using operator ID **000713** and password **123**.</span></span>

## <a name="set-up-your-site-in-commerce"></a><span data-ttu-id="8319d-145">Konfigurowanie witryny w usłudze Commerce</span><span class="sxs-lookup"><span data-stu-id="8319d-145">Set up your site in Commerce</span></span>

<span data-ttu-id="8319d-146">Aby rozpocząć konfigurowanie witryny oceny w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8319d-146">To start to set up your evaluation site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8319d-147">Zaloguj się do konstruktora witryny przy użyciu adresu URL zanotowanego podczas inicjowania usługi handlu elektronicznego w trakcie aprowizacji (zobacz [Inicjowanie usługi handlu elektronicznego](provisioning-guide.md#initialize-e-commerce)).</span><span class="sxs-lookup"><span data-stu-id="8319d-147">Sign in to site builder by using the URL that you made a note of when you initialized e-Commerce during provisioning (see [Initialize e-Commerce](provisioning-guide.md#initialize-e-commerce)).</span></span>
1. <span data-ttu-id="8319d-148">Wybierz witrynę **Fabrikam**, aby otworzyć okno dialogowe konfiguracji witryny.</span><span class="sxs-lookup"><span data-stu-id="8319d-148">Select the **Fabrikam** site to open the site setup dialog box.</span></span>
1. <span data-ttu-id="8319d-149">Wybierz domenę, która została wprowadzona podczas inicjowania aplikacji e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="8319d-149">Select the domain that you entered when you initialized e-Commerce.</span></span>
1. <span data-ttu-id="8319d-150">Wybierz opcję **Rozszerzony sklep online Fabrikam** jako kanał domyślny.</span><span class="sxs-lookup"><span data-stu-id="8319d-150">Select **Fabrikam extended online store** as the default channel.</span></span> <span data-ttu-id="8319d-151">(Upewnij się, że wybrano **rozszerzony** sklep internetowy).</span><span class="sxs-lookup"><span data-stu-id="8319d-151">(Make sure that you select the **extended** online store.)</span></span>
1. <span data-ttu-id="8319d-152">Wybierz wartość **en-us** jako język domyślny.</span><span class="sxs-lookup"><span data-stu-id="8319d-152">Select **en-us** as the default language.</span></span>
1. <span data-ttu-id="8319d-153">Pozostaw niezmienioną wartość pola **Ścieżka**.</span><span class="sxs-lookup"><span data-stu-id="8319d-153">Leave the value of the **Path** field as it is.</span></span>
1. <span data-ttu-id="8319d-154">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8319d-154">Select **OK**.</span></span> <span data-ttu-id="8319d-155">Zostanie wyświetlona lista stron w witrynie.</span><span class="sxs-lookup"><span data-stu-id="8319d-155">The list of pages on the site appears.</span></span>

## <a name="enable-jobs"></a><span data-ttu-id="8319d-156">Włącz zadania</span><span class="sxs-lookup"><span data-stu-id="8319d-156">Enable jobs</span></span>

<span data-ttu-id="8319d-157">Aby włączyć zadania w aplikacji Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="8319d-157">To enable jobs in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="8319d-158">Zaloguj się do środowiska (HQ).</span><span class="sxs-lookup"><span data-stu-id="8319d-158">Sign in to the environment (HQ).</span></span>
1. <span data-ttu-id="8319d-159">Korzystając z menu po lewej stronie, przejdź do pozycji **Retail i Commerce \> Zapytania i raporty \> Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="8319d-159">Use the menu on the left to go to **Retail and commerce \> Inquiries and reports \> Batch jobs**.</span></span>

    <span data-ttu-id="8319d-160">Pozostałe kroki tej procedury muszą zostać zakończone dla każdego z następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="8319d-160">The remaining steps of this procedure must be completed for each of the following jobs:</span></span>

    * <span data-ttu-id="8319d-161">Przetwarzanie powiadomień pocztą e-mail dla zamówienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="8319d-161">Process retail order email notification</span></span>
    * <span data-ttu-id="8319d-162">Dostępność produktu</span><span class="sxs-lookup"><span data-stu-id="8319d-162">Product availability</span></span>
    * <span data-ttu-id="8319d-163">P-0001</span><span class="sxs-lookup"><span data-stu-id="8319d-163">P-0001</span></span>
    * <span data-ttu-id="8319d-164">Zadanie synchronizowania zamówień</span><span class="sxs-lookup"><span data-stu-id="8319d-164">Synchronize orders job</span></span>

1. <span data-ttu-id="8319d-165">Użyj szybkiego filtru, aby wyszukać zadanie według nazwy.</span><span class="sxs-lookup"><span data-stu-id="8319d-165">Use the Quick Filter to search for the job by name.</span></span>
1. <span data-ttu-id="8319d-166">Jeśli stan zadania to **W trakcie**, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="8319d-166">If the status of the job is **Executing**, follow these steps:</span></span>

    1. <span data-ttu-id="8319d-167">Wybierz rekord.</span><span class="sxs-lookup"><span data-stu-id="8319d-167">Select the record.</span></span>
    1. <span data-ttu-id="8319d-168">W okienku akcji na karcie **Zadanie wsadowe** wybierz pozycję **Zmień status**.</span><span class="sxs-lookup"><span data-stu-id="8319d-168">On the Action Pane, on **Batch job** tab, select **Change status**.</span></span>
    1. <span data-ttu-id="8319d-169">Wybierz pozycję **Anuluj**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8319d-169">Select **Canceling**, and then select **OK**.</span></span>

<span data-ttu-id="8319d-170">Opcjonalnie można również określić interwał cyklu równy jednej (1) minucie dla następujących zadań:</span><span class="sxs-lookup"><span data-stu-id="8319d-170">Optionally, you can also set the recurrence interval to one (1) minute for the following jobs:</span></span>

* <span data-ttu-id="8319d-171">Przetwarzanie zadania powiadomień pocztą e-mail dla zamówienia sieci sprzedaży</span><span class="sxs-lookup"><span data-stu-id="8319d-171">Process retail order email notification job</span></span>
* <span data-ttu-id="8319d-172">Zadanie P-0001</span><span class="sxs-lookup"><span data-stu-id="8319d-172">P-0001 job</span></span>
* <span data-ttu-id="8319d-173">Zadanie synchronizowania zamówień</span><span class="sxs-lookup"><span data-stu-id="8319d-173">Synchronize orders job</span></span>

### <a name="run-full-data-synchronization"></a><span data-ttu-id="8319d-174">Uruchamianie pełnej synchronizacji danych</span><span class="sxs-lookup"><span data-stu-id="8319d-174">Run full data synchronization</span></span>

<span data-ttu-id="8319d-175">Aby uruchomić pełną synchronizację danych w aplikacji Commerce, wykonaj następujące kroki w Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="8319d-175">To run full data synchronization in Commerce, follow these steps in Commerce headquarters.</span></span>

1. <span data-ttu-id="8319d-176">Korzystając z menu po lewej stronie, przejdź do pozycji **Moduły \> Handel detaliczny i inny \> Ustawienia centrali \> Transfer danych w Commerce \> Baza danych kanału**.</span><span class="sxs-lookup"><span data-stu-id="8319d-176">Use the menu on the left to go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce scheduler \> Channel database**.</span></span>
1. <span data-ttu-id="8319d-177">Wybierz kanał o nazwie **scXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="8319d-177">Select the channel that is named **scXXXXXXXXX**.</span></span>
1. <span data-ttu-id="8319d-178">W okienku akcji wybierz **Pełna synchronizacja danych**.</span><span class="sxs-lookup"><span data-stu-id="8319d-178">On the Action Pane, select **Full data sync**.</span></span>
1. <span data-ttu-id="8319d-179">Wpisz **9999** jako harmonogram dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="8319d-179">Enter **9999** as the distribution schedule.</span></span>
1. <span data-ttu-id="8319d-180">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8319d-180">Select **OK**.</span></span>
1. <span data-ttu-id="8319d-181">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="8319d-181">Select **OK**.</span></span>

### <a name="test-credit-card-information-to-do-test-purchases"></a><span data-ttu-id="8319d-182">Testowanie informacji o karcie kredytowej w celu dokonania zakupów testowych</span><span class="sxs-lookup"><span data-stu-id="8319d-182">Test credit card information to do test purchases</span></span>

<span data-ttu-id="8319d-183">Aby przeprowadzić transakcje testowe w witrynie, można użyć następujących testowych informacji o karcie kredytowej:</span><span class="sxs-lookup"><span data-stu-id="8319d-183">To perform test transactions on the site, you can use the following test credit card information:</span></span>

- <span data-ttu-id="8319d-184">**Numer karty:** 4111-1111-1111-1111</span><span class="sxs-lookup"><span data-stu-id="8319d-184">**Card number:** 4111-1111-1111-1111</span></span>
- <span data-ttu-id="8319d-185">**Data ważności:** 10/20</span><span class="sxs-lookup"><span data-stu-id="8319d-185">**Expiration date:** 10/20</span></span>
- <span data-ttu-id="8319d-186">**Kod wartości weryfikacji karty (CVV):** 737</span><span class="sxs-lookup"><span data-stu-id="8319d-186">**Card verification value (CVV) code:** 737</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8319d-187">Nigdy w żadnym wypadku nie próbuj używać rzeczywistych informacji o karcie kredytowej w witrynie testowej.</span><span class="sxs-lookup"><span data-stu-id="8319d-187">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8319d-188">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="8319d-188">Next steps</span></span>

<span data-ttu-id="8319d-189">Po zakończeniu czynności obsługi administracyjnej i konfiguracji można rozpocząć korzystanie ze środowiska oceny.</span><span class="sxs-lookup"><span data-stu-id="8319d-189">After the provisioning and configuration steps are completed, you can start to use your evaluation environment.</span></span> <span data-ttu-id="8319d-190">Użyj adresu URL konstruktora witryn Commerce, aby przejść do środowiska tworzenia.</span><span class="sxs-lookup"><span data-stu-id="8319d-190">Use the Commerce site builder URL to go to the authoring experience.</span></span> <span data-ttu-id="8319d-191">Użyj adresu URL witryny Commerce, aby przejść do środowiska witryny klienta platformy handlu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="8319d-191">Use the Commerce site URL to go to the retail customer site experience.</span></span>

<span data-ttu-id="8319d-192">Aby skonfigurować opcjonalne funkcje środowiska oceny usługi Commerce, zobacz [Konfigurowanie funkcji opcjonalnych środowiska oceny usługi Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="8319d-192">To configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8319d-193">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="8319d-193">Additional resources</span></span>

[<span data-ttu-id="8319d-194">Omówienie środowiska oceny usługi Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8319d-194">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="8319d-195">Ustanowienie środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8319d-195">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="8319d-196">Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8319d-196">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="8319d-197">Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8319d-197">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="8319d-198">Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="8319d-198">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="8319d-199">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="8319d-199">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="8319d-200">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="8319d-200">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="8319d-201">Portal Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="8319d-201">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="8319d-202">Witryna Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8319d-202">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
