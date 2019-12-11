---
title: Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail
description: W tym temacie opisano sposób synchronizowania ocen produktów w Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
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
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698172"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a><span data-ttu-id="3da6f-103">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="3da6f-103">Sync product ratings in Dynamics 365 Retail</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="3da6f-104">W tym temacie opisano sposób synchronizowania ocen produktów w Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="3da6f-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="3da6f-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="3da6f-105">Overview</span></span>

<span data-ttu-id="3da6f-106">W celu użycia ocen produktów w wielu kanałach, na przykład w punkt sprzedaży (POS) i w biurach obsługi, oceny produktów z usługi ocen i recenzji muszą zostać zaimportowane do bazy danych kanału Retail.</span><span class="sxs-lookup"><span data-stu-id="3da6f-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Retail channel database.</span></span> <span data-ttu-id="3da6f-107">Po udostępnieniu ocen produktów w wielu kanałach mogą one pomóc klientom w pośredniej interakcji ze sprzedawcą.</span><span class="sxs-lookup"><span data-stu-id="3da6f-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="3da6f-108">W tym temacie opisano następujące zadania:</span><span class="sxs-lookup"><span data-stu-id="3da6f-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="3da6f-109">Skonfiguruj zadanie wsadowe Retail, aby zaimportować klasyfikacje produktów.</span><span class="sxs-lookup"><span data-stu-id="3da6f-109">Configure a Retail batch job to import product ratings.</span></span>
1. <span data-ttu-id="3da6f-110">Sprawdź, czy zadanie wsadowe synchronizacji oceny produktu zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="3da6f-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="3da6f-111">Umożliwia udostępnienie ocen produktów w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3da6f-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a><span data-ttu-id="3da6f-112">Skonfiguruj zadanie wsadowe Retail, aby zaimportować oceny produktów</span><span class="sxs-lookup"><span data-stu-id="3da6f-112">Configure a Retail batch job to import product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3da6f-113">Przed rozpoczęciem należy się upewnić, że jest zainstalowana wersja 10.0.6 lub nowsza Retail.</span><span class="sxs-lookup"><span data-stu-id="3da6f-113">Before you start, make sure that version 10.0.6 or later of Retail is installed.</span></span>

### <a name="initialize-the-retail-scheduler"></a><span data-ttu-id="3da6f-114">Zainicjuj harmonogram aplikacji Retail</span><span class="sxs-lookup"><span data-stu-id="3da6f-114">Initialize the retail scheduler</span></span>

<span data-ttu-id="3da6f-115">Aby zainicjować harmonogram sieci sprzedaży, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3da6f-115">To initialize the retail scheduler, follow these steps.</span></span>

1. <span data-ttu-id="3da6f-116">Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Zainicjuj harmonogram aplikacji Retail**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-116">Go to **Retail \> Headquarters setup \> Retail scheduler \> Initialize retail scheduler**.</span></span> <span data-ttu-id="3da6f-117">Alternatywnie można wyszukać wartość „Inicjuj transfer danych w sieci sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-117">Alternatively, search for "Initialize retail scheduler."</span></span>
1. <span data-ttu-id="3da6f-118">W oknie dialogowym **Inicjowanie transferuw sieci sprzedaży** upewnij się, że opcja **Usuń istniejącą konfigurację** jest ustawiona na wartość **nie**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-118">In the **Initialize retail scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="3da6f-119">Sprawdź podzadanie RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="3da6f-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="3da6f-120">Aby sprawdzić, czy istnieje podzadania **RetailProductRating**, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3da6f-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="3da6f-121">Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Podzadania harmonogramu**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-121">Go to **Retail \> Headquarters setup \> Retail scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="3da6f-122">Alternatywnie można wyszukać frazę „podzadania harmonogramu”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="3da6f-123">Na liście podzadania Znajdź lub Wyszukaj podzadanie **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="3da6f-124">Na poniższej ilustracji pokazano przykład strony szczegóły podzadania w Retail.</span><span class="sxs-lookup"><span data-stu-id="3da6f-124">The following illustration shows an example of the subjob details in Retail.</span></span>

![Szczegóły podzadania RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="3da6f-126">Jeśli nie znajdziesz podzadania **RetailProductRating**, możesz już wcześniej uruchomić zadanie **Synchronizuj oceny produktów** i zadanie **1040 CDX** przed zainicjowaniem procesu transferu danych w sieci sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3da6f-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the retail scheduler.</span></span> <span data-ttu-id="3da6f-127">W takim przypadku należy wykonać następujące kroki w celu uruchomienia zadania **Pełnej synchronizacji danych**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-127">In this case, follow these steps to run the **Full data sync** job.</span></span>
>
> 1. <span data-ttu-id="3da6f-128">Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Baza danych kanału**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-128">Go to **Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span> <span data-ttu-id="3da6f-129">Alternatywna metoda polega na wyszukaniu „bazy danych kanału”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="3da6f-130">Wybierz bazę danych kanału do zsynchronizowania.</span><span class="sxs-lookup"><span data-stu-id="3da6f-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="3da6f-131">W okienku akcji wybierz **Pełna synchronizacja danych**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-131">On the Action Pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="3da6f-132">W oknie dialogowym **Wybierz harmonogram dystrybucji** wybierz pozycję **1040 - produkty**, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="3da6f-133">Powtórz kroki poprzedniej procedury, aby sprawdzić, czy utworzono podzadanie **RetailProductRating**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="3da6f-134">Import ocen produktów</span><span class="sxs-lookup"><span data-stu-id="3da6f-134">Import product ratings</span></span>

<span data-ttu-id="3da6f-135">Aby zaimportować oceny produktów do Retail z usługi ocen i recenzji, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3da6f-135">To import product ratings into Retail from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="3da6f-136">Przejdź do **Retail \> Ustawienia centrali \> Transfer danych w sieci sprzedaży \> Zadanie synchronizacji ocen produktu**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-136">Go to **Retail \> Headquarters setup \> Retail scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="3da6f-137">Możesz również wyszukać frazę „Zadanie synchronizacji ocen produktu”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="3da6f-138">W oknie dialogowym **Pobierz oceny produktu**, na skróconej karcie **Uruchom w tle** wybierz pozycję **Wielokrotnie**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="3da6f-139">W oknie dialogowym **Definiuj cykl** ustaw wzorzec cyklu.</span><span class="sxs-lookup"><span data-stu-id="3da6f-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="3da6f-140">(Sugerowana wartość wynosi dwie godziny.) Nie planuj cyklu krótszego niż jedna godzina.</span><span class="sxs-lookup"><span data-stu-id="3da6f-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="3da6f-141">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-141">Select **OK**.</span></span>
1. <span data-ttu-id="3da6f-142">W opcji **Przetwarzanie wsadowe** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="3da6f-143">To ustawienie pomaga zagwarantować, że dzienniki będą mogły być poddawane inspekcji i sprawdzać stan uruchomienia zadania wsadowego.</span><span class="sxs-lookup"><span data-stu-id="3da6f-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="3da6f-144">Kliknij przycisk **OK**, aby zaplanować zadanie wsadowe.</span><span class="sxs-lookup"><span data-stu-id="3da6f-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="3da6f-145">Na poniższej ilustracji pokazano przykład strony konfiguracji zadania wsadowego w Retail.</span><span class="sxs-lookup"><span data-stu-id="3da6f-145">The following illustration shows an example of batch job configuration in Retail.</span></span>

![Konfiguracja zadania wsadowego Synchronizuj oceny produktów](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="3da6f-147">Sprawdź, czy zadanie wsadowe synchronizacji ocen produktu zakończyło się pomyślnie</span><span class="sxs-lookup"><span data-stu-id="3da6f-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="3da6f-148">Aby sprawdzić, czy zadanie wsadowe **Synchronizacja ocen produktów w rozwiązaniu** zostało wykonane pomyślnie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3da6f-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="3da6f-149">Przejdź do **Retail \> Administrator systemu \> Zapytania \> Zadania wsadowe** lub, jeśli jest używana jednostka magazynowa detaliczna (SKU) dostępna tylko w Retail, **Retail \> Zapytania i raporty \> Zadania wsadowe**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-149">Go to **Retail \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Retail-only stock keeping unit (SKU), **Retail \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="3da6f-150">Alternatywnie można wyszukać frazę „zadania wsadowe”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="3da6f-151">Aby wyświetlić szczegóły zadania wsadowego, na liście zadań wsadowych w kolumnie **Opis zadania** należy wyszukać opis zawierający ciąg „Pobierz oceny produktu”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="3da6f-152">Umożliwia wybranie identyfikatora zadania w celu wyświetlenia szczegółów zadania wsadowego, np. zaplanowanej daty/godziny i tekstu cyklu.</span><span class="sxs-lookup"><span data-stu-id="3da6f-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="3da6f-153">Na poniższej ilustracji przedstawiono przykładowe szczegóły zadania wsadowego w Reyail, gdy zaplanowano uruchomienie zadania wsadowego w odstępach dwugodzinnych.</span><span class="sxs-lookup"><span data-stu-id="3da6f-153">The following illustration shows an example of the batch job details in Retail when the batch job is scheduled to run at two-hour intervals.</span></span>

![Szczegóły zadania wsadowego Synchronizuj oceny produktów](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="3da6f-155">Umożliwia udostępnienie ocen produktów w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="3da6f-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="3da6f-156">Rozwiązanie oceny i recenzje w Dynamics 365 Commerce jest rozwiązaniem wielokanałowym.</span><span class="sxs-lookup"><span data-stu-id="3da6f-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="3da6f-157">Jednak oceny produktów domyślnie nie są wyświetlane w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3da6f-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="3da6f-158">Aby ułatwić klientom w sklepach korzystanie z ocen i recenzji, gdy są one pomocne przez partnerów sprzedaży, należy włączyć oceny produktów w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3da6f-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="3da6f-159">Aby włączyć oceny produktu w punkcie sprzedazy, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="3da6f-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="3da6f-160">Kliknij kolejno opcje **Retail \> Ustawienia Retail \> Parametry \> Parametry sieci sprzedaży**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-160">Go to **Retail \> Retail setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="3da6f-161">Alternatywna metoda polega na wyszukaniu frazy „parametry Retail”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-161">Alternatively, search for "Retail parameters."</span></span>
1. <span data-ttu-id="3da6f-162">Na karcie **Parametry konfiguracji** wybierz opcję **Nowe**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="3da6f-163">Wprowadź nazwę, na przykład **RatingsAndReviews.EnableProductRatingsForRetailStores**, i nadaj jej wartość **prawda**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="3da6f-164">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-164">Select **Save**.</span></span>
1. <span data-ttu-id="3da6f-165">Wybierz kolejno opcje **Handel detaliczny \> Dane IT sieci sprzedaży \> Harmonogram dystrybucji**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-165">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span> <span data-ttu-id="3da6f-166">Alternatywna metoda polega na wyszukaniu terminu „harmonogram dystrybucji”.</span><span class="sxs-lookup"><span data-stu-id="3da6f-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="3da6f-167">Na liście zadań wybierz pozycję **1110** (**konfiguracja globalna**), a następnie wybierz opcję **Uruchom teraz**.</span><span class="sxs-lookup"><span data-stu-id="3da6f-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="3da6f-168">Po pomyślnym uruchomieniu zadania sprawdź, czy oceny produktów są teraz widoczne w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3da6f-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="3da6f-169">Na poniższej ilustracji przedstawiono przykład konfiguracji parametrów Retail w celu włączenia ocen produktów w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="3da6f-169">The following illustration shows an example of the configuration of the Retail parameters to turn on product ratings at the POS.</span></span>

![Konfiguracja parametrów retail dla ocen produktów w punkcie sprzedaży](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="3da6f-171">Na poniższej ilustracji przedstawiono przykład ocen produktów w POS.</span><span class="sxs-lookup"><span data-stu-id="3da6f-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Oceny produktu w POS](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="3da6f-173">Na poniższej ilustracji przedstawiono przykład ocen produktów w kanałach biura obsługi.</span><span class="sxs-lookup"><span data-stu-id="3da6f-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Oceny produktu w kanale biura obsługi](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="3da6f-175">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3da6f-175">Additional resources</span></span>

[<span data-ttu-id="3da6f-176">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3da6f-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="3da6f-177">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3da6f-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="3da6f-178">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="3da6f-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="3da6f-179">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3da6f-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)
