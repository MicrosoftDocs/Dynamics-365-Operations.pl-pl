---
title: Zarządzanie ocenami i recenzjami
description: W tym temacie opisano sposób zarządzania ocenami i recenzjami za pomocą narzędzia oceny i recenzji Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a7fa2ae3124a0a68b3890987c5dce2730e5c2183
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027249"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="fbcce-103">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="fbcce-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fbcce-104">W tym temacie opisano sposób zarządzania ocenami i recenzjami za pomocą narzędzia oceny i recenzji Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fbcce-104">This topic explains how to manage ratings and reviews by using the Microsoft Dynamics 365 Commerce ratings and reviews moderation tool.</span></span>

## <a name="overview"></a><span data-ttu-id="fbcce-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="fbcce-105">Overview</span></span>

<span data-ttu-id="fbcce-106">Dynamics 365 Commerce uzywa Microsoft Azure Cognitive Service do automatyczniej moderacji tekstu recenzji, redagując wulgaryzmy</span><span class="sxs-lookup"><span data-stu-id="fbcce-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="fbcce-107">Ponadto moderatorzy mogą wykorzystywać narzędzie do oceny i recenzji dla następujących zadań ręcznych:</span><span class="sxs-lookup"><span data-stu-id="fbcce-107">In addition, moderators can use the ratings and reviews moderation tool for the following manual tasks:</span></span>

- <span data-ttu-id="fbcce-108">Moderowanie recenzji, odpowiadając na nie lub usuwaniu.</span><span class="sxs-lookup"><span data-stu-id="fbcce-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="fbcce-109">Usuwanie opini klienta na jego życzenie.</span><span class="sxs-lookup"><span data-stu-id="fbcce-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="fbcce-110">Masowe Importowanie danych ocen i recenzji dotyczących wszystkich produktów w szablonie rozwiązania Microsoft Power BI, dzięki czemu można analizować trendy dotyczące ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="fbcce-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="access-ratings-and-reviews-moderation-features"></a><span data-ttu-id="fbcce-111">Dostęp do funkcji moderowania recenzji i ocen</span><span class="sxs-lookup"><span data-stu-id="fbcce-111">Access ratings and reviews moderation features</span></span>

<span data-ttu-id="fbcce-112">Aby uzyskać dostęp do klasyfikacji i przeglądu funkcji moderowania w narzędziu Zarządzanie serwisem e-Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fbcce-112">To access ratings and reviews moderation features in the e-Commerce site management tool, follow these steps.</span></span>

1. <span data-ttu-id="fbcce-113">Zaloguj się do [Microsoft LifeCycle Services (LCS)](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="fbcce-113">Sign in to [Microsoft Lifecycle Services (LCS)](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="fbcce-114">Otwórz projekt zawierający środowisko, w którym chcesz zainicjować e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="fbcce-114">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="fbcce-115">W sekcji **środowiska** wybierz środowisko.</span><span class="sxs-lookup"><span data-stu-id="fbcce-115">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="fbcce-116">W obszarze **Funkcje środowiska** wybierz pozycję **Zarządzaj sprzedażą detaliczną**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-116">Under **Environment features**, select **Retail manage**.</span></span>
1. <span data-ttu-id="fbcce-117">Na karcie **e-commerce** w obszarze **łącza** wybierz pozycję **narzędzie do zarządzania witryną handlu elektronicznego**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-117">On the **e-Commerce** tab under **Links**, select **e-Commerce Site management tool**.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="fbcce-118">Przeczytaj recenzję</span><span class="sxs-lookup"><span data-stu-id="fbcce-118">Read a review</span></span> 

1. <span data-ttu-id="fbcce-119">Przejdź do **Strona główna \> Recenzje \> Moderacja**</span><span class="sxs-lookup"><span data-stu-id="fbcce-119">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="fbcce-120">Pole wyszukiwania w prawym górnym rogu strony umożliwia filtrowanie recenzji wyświetlanych według identyfikatora produktu, nazwy produktu lub tekstu recenzji.</span><span class="sxs-lookup"><span data-stu-id="fbcce-120">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="fbcce-121">Dodatkowe filtry umożliwiają ograniczenie recenzji według okresu, oceny, kanału lub oddziału (odrzucenia, odpowiedzi lub zgłoszenia).</span><span class="sxs-lookup"><span data-stu-id="fbcce-121">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Strona główna moderacji](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="fbcce-123">Odpowiedz na recenzję</span><span class="sxs-lookup"><span data-stu-id="fbcce-123">Respond to a review</span></span> 

<span data-ttu-id="fbcce-124">Czasami Klienci, którzy zakupili produkt, wyrażają zadowolenie lub niedozadowolenie, lub nie wiedzą, jak skorzystać z produktu.</span><span class="sxs-lookup"><span data-stu-id="fbcce-124">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="fbcce-125">Jako moderatora możesz zaksięgować odpowiedź na recenzję.</span><span class="sxs-lookup"><span data-stu-id="fbcce-125">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="fbcce-126">Ta odpowiedź jest wyświetlana razem z recenzją w witrynie.</span><span class="sxs-lookup"><span data-stu-id="fbcce-126">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="fbcce-127">Aby odpowiedzieć na recenzję, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fbcce-127">To respond to a review, follow these steps.</span></span>

1. <span data-ttu-id="fbcce-128">Przejdź do **Strona główna \> Recenzje \> Moderacja**</span><span class="sxs-lookup"><span data-stu-id="fbcce-128">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="fbcce-129">Znajdź i wybierz recenzję, która wymaga odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="fbcce-129">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="fbcce-130">W panelu właściwości po prawej wybierz **Dodaj odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-130">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="fbcce-131">Wprowadź tekst odpowiedzi i nazwę, która powinna być wyświetlana dla obiektu odpowiadającego.</span><span class="sxs-lookup"><span data-stu-id="fbcce-131">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="fbcce-132">Domyślną nazwą obiektu odpowiadającego jest **moderator**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-132">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="fbcce-133">Po zakończeniu wybierz przycisk **Prześlij odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-133">When you've finished, select **Post response**.</span></span>

![Odpowiedź na recenzję](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="fbcce-135">Zapoznaj się z recenzją</span><span class="sxs-lookup"><span data-stu-id="fbcce-135">Take down a review</span></span> 

<span data-ttu-id="fbcce-136">Niekiedy w firmie istnieje uzasadnienie biznesowe w celu usunięcia recenzji klientów.</span><span class="sxs-lookup"><span data-stu-id="fbcce-136">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="fbcce-137">Aby usunąć recenzję, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fbcce-137">To take down a review, follow these steps.</span></span>

1. <span data-ttu-id="fbcce-138">Przejdź do **Strona główna \> Recenzje \> Moderacja**</span><span class="sxs-lookup"><span data-stu-id="fbcce-138">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="fbcce-139">Znajdź i zaznacz recenzję, która ma zostać przewidziana.</span><span class="sxs-lookup"><span data-stu-id="fbcce-139">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="fbcce-140">W okienku właściwości po prawej stronie wybierz przyczynę usunięcia, a następnie wybierz opcję **usuń**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-140">In the properties pane on the right, select a takedown reason, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="fbcce-141">Usuwanie opini klienta na jego życzenie</span><span class="sxs-lookup"><span data-stu-id="fbcce-141">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="fbcce-142">Czasami klienci chcą trwale usunąć swoje oceny i dane z witryny internetowej e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="fbcce-142">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="fbcce-143">Moderator otrzymujący żądanie usunięcia od odbiorcy może usunąć dane odbiorcy, korzystając z funkcji usuwania recenzji.</span><span class="sxs-lookup"><span data-stu-id="fbcce-143">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="fbcce-144">Aby znaleźć i usunąć dane odbiorcy, moderator wymaga adresu e-mail używanego przez klienta do zalogowania się i dostarczenia recenzji.</span><span class="sxs-lookup"><span data-stu-id="fbcce-144">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="fbcce-145">Aby znaleźć i usunąć dane odbiorcy, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fbcce-145">To find and delete customer data, follow these steps.</span></span>

1. <span data-ttu-id="fbcce-146">Przejdź do **Strona główna \> Recenzje \> Usuń**</span><span class="sxs-lookup"><span data-stu-id="fbcce-146">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="fbcce-147">W polu **Wyszukaj użytkowników według adresu e-mail** wprowadź adres e-mail odbiorcy, a następnie wybierz opcję **Szukaj**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-147">In the **Search for users by email address** field, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="fbcce-148">Jeśli odbiorca ma jakiekolwiek czynności recenzowania (na przykład: wysłane recenzje, głosy na temat użyteczności recenzji innych odbiorców lub komentarze dotyczące recenzji innego odbiorcy), zostaną wyświetlone wyniki.</span><span class="sxs-lookup"><span data-stu-id="fbcce-148">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="fbcce-149">Dla każdego towaru jest dostępny przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-149">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="fbcce-150">Dla każdego towaru, który musi zostać usunięty, wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-150">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="fbcce-151">Po wyświetleniu monitu o potwierdzenie wybierz opcję **tak**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-151">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Usuwanie danych klienta](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="fbcce-153">W celu całkowitego usunięcia danych z systemu może upłynąć nawet do siedmiu dni.</span><span class="sxs-lookup"><span data-stu-id="fbcce-153">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="fbcce-154">Moderatorzy powinni powiadamiać odbiorców o tym opóźnieniu.</span><span class="sxs-lookup"><span data-stu-id="fbcce-154">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="fbcce-155">Jeśli odbiorcy zmienili swoje nazwisko w ustawieniach konta, w wynikach wyszukiwania może pojawić się wiele elementów.</span><span class="sxs-lookup"><span data-stu-id="fbcce-155">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="fbcce-156">W takim przypadku, aby całkowicie usunąć dane odbiorcy, moderator musi wybrać opcję **Usuń** dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="fbcce-156">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="fbcce-157">Pobieranie danych ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="fbcce-157">Download ratings and reviews data</span></span>

<span data-ttu-id="fbcce-158">Moderatorzy narzędzia do oceny i recenzji pozwalają na masowe importowanie ocen i recenzji, dzięki czemu mogą analizować trendy.</span><span class="sxs-lookup"><span data-stu-id="fbcce-158">The ratings and reviews moderation tool lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="fbcce-159">Dostępny jest szablon Power BI zawierający podstawowe miary.</span><span class="sxs-lookup"><span data-stu-id="fbcce-159">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="fbcce-160">Moderatorzy mogą używać tego szablonu do łączenia danych importowanych zbiorczo i przeglądania pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="fbcce-160">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="fbcce-161">Nie muszą oni tworzyć niestandardowych pulpitów nawigacyjnych.</span><span class="sxs-lookup"><span data-stu-id="fbcce-161">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="fbcce-162">Moderatorzy mogą również dostosować szablon Power BI w celu spełnienia określonych wymagań.</span><span class="sxs-lookup"><span data-stu-id="fbcce-162">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="fbcce-163">Aby pobrać klasyfikacje i Recenzje danych, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fbcce-163">To download ratings and reviews data, follow these steps.</span></span>

1. <span data-ttu-id="fbcce-164">Przejdź do **Strona główna \> Recenzje \> Raportowanie**</span><span class="sxs-lookup"><span data-stu-id="fbcce-164">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="fbcce-165">Wybierz opcję **Pobierz dane recenzji**, aby pobrać oceny i recenzje danych luzem w formacie CSV (wartości rozdzielane przecinkami).</span><span class="sxs-lookup"><span data-stu-id="fbcce-165">Select **Download reviews data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="fbcce-166">zobacz trendy ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="fbcce-166">View ratings and reviews trends</span></span>

<span data-ttu-id="fbcce-167">Moderatorzy mogą pobrać szablon Power BI, aby umożliwić wyświetlanie trendów na pulpicie nawigacyjnym.</span><span class="sxs-lookup"><span data-stu-id="fbcce-167">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="fbcce-168">Aby zobaczyć trendy ocen i recenzji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="fbcce-168">To view ratings and reviews trends, follow these steps.</span></span>

1. <span data-ttu-id="fbcce-169">Przejdź do **Strona główna \> Recenzje \> Raportowanie**</span><span class="sxs-lookup"><span data-stu-id="fbcce-169">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="fbcce-170">Wybierz opcję **Szablon usługi PowerBI**, aby pobrać szablon.</span><span class="sxs-lookup"><span data-stu-id="fbcce-170">Select **PowerBI template** to download the template.</span></span>

    ![Pobierz szablon usługi Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="fbcce-172">Otwórz pobrany szablon za pomocą aplikacji Power BI.</span><span class="sxs-lookup"><span data-stu-id="fbcce-172">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="fbcce-173">Zamknij okno dialogowe **Dostęp do zawartości sieci Web**, które zostanie wyświetlone, a następnie zamknij wyświetlony komunikat o błędzie „Odśwież”.</span><span class="sxs-lookup"><span data-stu-id="fbcce-173">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="fbcce-174">Przejdź do **strony głównej**, wybierz opcję **Edytuj kwerendy**, a następnie wybierz **Ustawienia źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-174">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="fbcce-175">W oknie dialogowym **ustawienia źródła danych** wybierz opcję **Zmień źródło**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-175">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="fbcce-176">W polu **adres URL** wprowadź ścieżkę danych recenzji, które zostały pobrane w poprzedniej procedurze (na przykład **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="fbcce-176">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Pole adresu URL w oknie dialogowym wartości rozdzielane przecinkami](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="fbcce-178">Wybierz  **OK** i kliknij przycisk **Zastosuj zmiany**.</span><span class="sxs-lookup"><span data-stu-id="fbcce-178">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="fbcce-179">Zastosowanie zmian w źródle danych będzie trwać jedną do dwóch minut.</span><span class="sxs-lookup"><span data-stu-id="fbcce-179">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="fbcce-180">Wybierz opcję **Arkusz trendów**, aby wyświetlić trendy dotyczące ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="fbcce-180">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Trendy ocen i recenzji](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="fbcce-182">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="fbcce-182">Additional resources</span></span>

[<span data-ttu-id="fbcce-183">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="fbcce-183">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="fbcce-184">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="fbcce-184">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="fbcce-185">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="fbcce-185">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="fbcce-186">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="fbcce-186">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
