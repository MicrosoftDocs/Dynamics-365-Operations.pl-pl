---
title: Zarządzanie ocenami i recenzjami
description: W tym temacie wyjaśniono, jak zarządzać klasyfikacjami recenzjami konstruktorze witryn Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0a70d0526fb2443605a6b11df3ee281d4dd12f1d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982573"
---
# <a name="manage-ratings-and-reviews"></a><span data-ttu-id="3570e-103">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="3570e-103">Manage ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3570e-104">W tym temacie wyjaśniono, jak zarządzać klasyfikacjami recenzjami konstruktorze witryn Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3570e-104">This topic explains how to manage ratings and reviews in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="3570e-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="3570e-105">Overview</span></span>

<span data-ttu-id="3570e-106">Dynamics 365 Commerce uzywa Microsoft Azure Cognitive Service do automatyczniej moderacji tekstu recenzji, redagując wulgaryzmy</span><span class="sxs-lookup"><span data-stu-id="3570e-106">Dynamics 365 Commerce uses Microsoft Azure Cognitive Service to automatically moderate review text by redacting profane words.</span></span> <span data-ttu-id="3570e-107">Ponadto za pomocą konstruktora witryn Dynamics 365 Commerce moderatorzy mogą wykonywać następujące zadania ręczne:</span><span class="sxs-lookup"><span data-stu-id="3570e-107">In addition, moderators can use Dynamics 365 Commerce site builder to implement the following manual tasks:</span></span>

- <span data-ttu-id="3570e-108">Moderowanie recenzji, odpowiadając na nie lub usuwaniu.</span><span class="sxs-lookup"><span data-stu-id="3570e-108">Moderate reviews by responding to them or removing them.</span></span>
- <span data-ttu-id="3570e-109">Usuwanie opini klienta na jego życzenie.</span><span class="sxs-lookup"><span data-stu-id="3570e-109">Delete a customer's reviews at the customer's request.</span></span>
- <span data-ttu-id="3570e-110">Masowe Importowanie danych ocen i recenzji dotyczących wszystkich produktów w szablonie rozwiązania Microsoft Power BI, dzięki czemu można analizować trendy dotyczące ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="3570e-110">Bulk-import ratings and reviews data for all products into a Microsoft Power BI template, so that trends for ratings and reviews can be analyzed.</span></span>

## <a name="read-a-review"></a><span data-ttu-id="3570e-111">Przeczytaj recenzję</span><span class="sxs-lookup"><span data-stu-id="3570e-111">Read a review</span></span> 

<span data-ttu-id="3570e-112">Aby przeczytać recenzję w konstruktorze witryn w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3570e-112">To read to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3570e-113">Przejdź do **Strona główna \> Recenzje \> Moderacja**</span><span class="sxs-lookup"><span data-stu-id="3570e-113">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="3570e-114">Pole wyszukiwania w prawym górnym rogu strony umożliwia filtrowanie recenzji wyświetlanych według identyfikatora produktu, nazwy produktu lub tekstu recenzji.</span><span class="sxs-lookup"><span data-stu-id="3570e-114">Use the search field in the upper right of the page to filter the reviews that are shown by product ID, product name, or review text.</span></span>

<span data-ttu-id="3570e-115">Dodatkowe filtry umożliwiają ograniczenie recenzji według okresu, oceny, kanału lub oddziału (odrzucenia, odpowiedzi lub zgłoszenia).</span><span class="sxs-lookup"><span data-stu-id="3570e-115">Additional filters let you limit the reviews by period, rating, channel, or concern status (taken down, responded, or reported).</span></span>

![Strona główna moderacji](media/rnr-moderation-home.png) 

## <a name="respond-to-a-review"></a><span data-ttu-id="3570e-117">Odpowiedz na recenzję</span><span class="sxs-lookup"><span data-stu-id="3570e-117">Respond to a review</span></span> 

<span data-ttu-id="3570e-118">Czasami Klienci, którzy zakupili produkt, wyrażają zadowolenie lub niedozadowolenie, lub nie wiedzą, jak skorzystać z produktu.</span><span class="sxs-lookup"><span data-stu-id="3570e-118">Sometimes, customers who purchased a product express their satisfaction or dissatisfaction, or they don't understand how to use the product.</span></span> <span data-ttu-id="3570e-119">Jako moderatora możesz zaksięgować odpowiedź na recenzję.</span><span class="sxs-lookup"><span data-stu-id="3570e-119">As a moderator, you can post a response to a review.</span></span> <span data-ttu-id="3570e-120">Ta odpowiedź jest wyświetlana razem z recenzją w witrynie.</span><span class="sxs-lookup"><span data-stu-id="3570e-120">This response appears together with the review on the site.</span></span> 

<span data-ttu-id="3570e-121">Aby odpowiedzieć na recenzję w konstruktorze witryn w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3570e-121">To respond to a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3570e-122">Przejdź do **Strona główna \> Recenzje \> Moderacja**</span><span class="sxs-lookup"><span data-stu-id="3570e-122">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="3570e-123">Znajdź i wybierz recenzję, która wymaga odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="3570e-123">Find and select the review that requires a response.</span></span>
1. <span data-ttu-id="3570e-124">W panelu właściwości po prawej wybierz **Dodaj odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="3570e-124">In the properties pane on the right, select **Add a response**.</span></span>
1. <span data-ttu-id="3570e-125">Wprowadź tekst odpowiedzi i nazwę, która powinna być wyświetlana dla obiektu odpowiadającego.</span><span class="sxs-lookup"><span data-stu-id="3570e-125">Enter the response text and the name that should be shown for the responder.</span></span> <span data-ttu-id="3570e-126">Domyślną nazwą obiektu odpowiadającego jest **moderator**.</span><span class="sxs-lookup"><span data-stu-id="3570e-126">The default responder name is **Moderator**.</span></span>
1. <span data-ttu-id="3570e-127">Po zakończeniu wybierz przycisk **Prześlij odpowiedź**.</span><span class="sxs-lookup"><span data-stu-id="3570e-127">When you've finished, select **Post response**.</span></span>

![Odpowiedź na recenzję](media/rnr-moderation-response.png) 

## <a name="take-down-a-review"></a><span data-ttu-id="3570e-129">Zapoznaj się z recenzją</span><span class="sxs-lookup"><span data-stu-id="3570e-129">Take down a review</span></span> 

<span data-ttu-id="3570e-130">Niekiedy w firmie istnieje uzasadnienie biznesowe w celu usunięcia recenzji klientów.</span><span class="sxs-lookup"><span data-stu-id="3570e-130">Sometimes, there is a business justification for moderators to take down customer reviews.</span></span> 

<span data-ttu-id="3570e-131">Aby usunąć recenzję w konstruktorze witryn w usłudze Commerce, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3570e-131">To take down a review in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3570e-132">Przejdź do **Strona główna \> Recenzje \> Moderacja**</span><span class="sxs-lookup"><span data-stu-id="3570e-132">Go to **Home \> Reviews \> Moderation**.</span></span>
1. <span data-ttu-id="3570e-133">Znajdź i zaznacz recenzję, która ma zostać przewidziana.</span><span class="sxs-lookup"><span data-stu-id="3570e-133">Find and select the review that must be taken down.</span></span>
1. <span data-ttu-id="3570e-134">W okienku właściwości po prawej stronie wybierz przyczynę usunięcia w obszarze **Usuń recenzję**, a następnie wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="3570e-134">In the properties pane on the right, select a takedown reason under **Takedown Review**, and then select **Take down**.</span></span>
    
## <a name="delete-a-customers-reviews-at-the-customers-request"></a><span data-ttu-id="3570e-135">Usuwanie opini klienta na jego życzenie</span><span class="sxs-lookup"><span data-stu-id="3570e-135">Delete a customer's reviews at the customer's request</span></span> 

<span data-ttu-id="3570e-136">Czasami klienci chcą trwale usunąć swoje oceny i dane z witryny internetowej e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="3570e-136">Sometimes, customers want their ratings and reviews data to be permanently deleted from an e-Commerce website.</span></span> <span data-ttu-id="3570e-137">Moderator otrzymujący żądanie usunięcia od odbiorcy może usunąć dane odbiorcy, korzystając z funkcji usuwania recenzji.</span><span class="sxs-lookup"><span data-stu-id="3570e-137">A moderator who receives a removal request from a customer can remove the customer's data by using the review deletion feature.</span></span> <span data-ttu-id="3570e-138">Aby znaleźć i usunąć dane odbiorcy, moderator wymaga adresu e-mail używanego przez klienta do zalogowania się i dostarczenia recenzji.</span><span class="sxs-lookup"><span data-stu-id="3570e-138">To find and delete a customer's data, the moderator requires the email address that the customer used to sign in and provide reviews.</span></span> 

<span data-ttu-id="3570e-139">Aby znaleźć i usunąć dane klienta w konstruktorze witryn w module Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3570e-139">To find and delete customer data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3570e-140">Przejdź do **Strona główna \> Recenzje \> Usuń**</span><span class="sxs-lookup"><span data-stu-id="3570e-140">Go to **Home \> Reviews \> Delete**.</span></span>
1. <span data-ttu-id="3570e-141">W polu **Wyszukaj użytkowników według adresu e-mail** wprowadź adres e-mail odbiorcy, a następnie wybierz opcję **Szukaj**.</span><span class="sxs-lookup"><span data-stu-id="3570e-141">In the **Search for users by email address** box, enter the customer's email address, and then select **Search**.</span></span>
1. <span data-ttu-id="3570e-142">Jeśli odbiorca ma jakiekolwiek czynności recenzowania (na przykład: wysłane recenzje, głosy na temat użyteczności recenzji innych odbiorców lub komentarze dotyczące recenzji innego odbiorcy), zostaną wyświetlone wyniki.</span><span class="sxs-lookup"><span data-stu-id="3570e-142">If the customer has any review activity (for example, review submissions, votes about the helpfulness of another customer's reviews, or comments about another customer's review), the results are shown.</span></span> <span data-ttu-id="3570e-143">Dla każdego towaru jest dostępny przycisk **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="3570e-143">For each item, there is a **Delete** button.</span></span>
1. <span data-ttu-id="3570e-144">Dla każdego towaru, który musi zostać usunięty, wybierz opcję **Usuń**.</span><span class="sxs-lookup"><span data-stu-id="3570e-144">For each item that must be deleted, select **Delete**.</span></span> <span data-ttu-id="3570e-145">Po wyświetleniu monitu o potwierdzenie wybierz opcję **tak**.</span><span class="sxs-lookup"><span data-stu-id="3570e-145">When you're prompted for confirmation, select **Yes**.</span></span> 
    
![Usuwanie danych klienta](media/rnr-moderation-delete-reviews.png) 

> [!NOTE]
> - <span data-ttu-id="3570e-147">W celu całkowitego usunięcia danych z systemu może upłynąć nawet do siedmiu dni.</span><span class="sxs-lookup"><span data-stu-id="3570e-147">It can take up to seven days for data to be completely removed from the system.</span></span> <span data-ttu-id="3570e-148">Moderatorzy powinni powiadamiać odbiorców o tym opóźnieniu.</span><span class="sxs-lookup"><span data-stu-id="3570e-148">Moderators should notify customers about this delay.</span></span>
> - <span data-ttu-id="3570e-149">Jeśli odbiorcy zmienili swoje nazwisko w ustawieniach konta, w wynikach wyszukiwania może pojawić się wiele elementów.</span><span class="sxs-lookup"><span data-stu-id="3570e-149">If customers have changed their name in their account settings, multiple items might appear in the search results.</span></span> <span data-ttu-id="3570e-150">W takim przypadku, aby całkowicie usunąć dane odbiorcy, moderator musi wybrać opcję **Usuń** dla każdego towaru.</span><span class="sxs-lookup"><span data-stu-id="3570e-150">In this case, to completely delete the customer's data, the moderator must select **Delete** for each item.</span></span> 

## <a name="download-ratings-and-reviews-data"></a><span data-ttu-id="3570e-151">Pobieranie danych ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3570e-151">Download ratings and reviews data</span></span>

<span data-ttu-id="3570e-152">Konstruktor witryn w module Commerce pozwala moderatorom na masowe importowanie ocen i recenzji, dzięki czemu mogą analizować trendy.</span><span class="sxs-lookup"><span data-stu-id="3570e-152">Commerce site builder lets moderators import ratings and reviews data in bulk, so that they can analyze trends.</span></span> <span data-ttu-id="3570e-153">Dostępny jest szablon Power BI zawierający podstawowe miary.</span><span class="sxs-lookup"><span data-stu-id="3570e-153">A Power BI template that includes basic metrics is available.</span></span> <span data-ttu-id="3570e-154">Moderatorzy mogą używać tego szablonu do łączenia danych importowanych zbiorczo i przeglądania pulpitu nawigacyjnego.</span><span class="sxs-lookup"><span data-stu-id="3570e-154">Moderators can use this template to connect bulk-imported data and view a dashboard.</span></span> <span data-ttu-id="3570e-155">Nie muszą oni tworzyć niestandardowych pulpitów nawigacyjnych.</span><span class="sxs-lookup"><span data-stu-id="3570e-155">They don't have to create a custom dashboard.</span></span> <span data-ttu-id="3570e-156">Moderatorzy mogą również dostosować szablon Power BI w celu spełnienia określonych wymagań.</span><span class="sxs-lookup"><span data-stu-id="3570e-156">Moderators can also customize the Power BI template to meet their specific needs.</span></span> 

<span data-ttu-id="3570e-157">Aby pobrać dane ocen i recenzji w konstruktorze witryn w module Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3570e-157">To download ratings and reviews data in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3570e-158">Przejdź do **Strona główna \> Recenzje \> Raportowanie**</span><span class="sxs-lookup"><span data-stu-id="3570e-158">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="3570e-159">Wybierz opcję **Pobierz dane recenzji**, aby pobrać oceny i recenzje danych luzem w formacie CSV (wartości rozdzielane przecinkami).</span><span class="sxs-lookup"><span data-stu-id="3570e-159">Select **Download review data** to download ratings and reviews data in bulk in comma-separated values (CSV) format.</span></span>

## <a name="view-ratings-and-reviews-trends"></a><span data-ttu-id="3570e-160">zobacz trendy ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3570e-160">View ratings and reviews trends</span></span>

<span data-ttu-id="3570e-161">Moderatorzy mogą pobrać szablon Power BI, aby umożliwić wyświetlanie trendów na pulpicie nawigacyjnym.</span><span class="sxs-lookup"><span data-stu-id="3570e-161">Moderators can download the Power BI template so that they can view trends in a dashboard.</span></span>

<span data-ttu-id="3570e-162">Aby wyświetlić trendy ocen i recenzji w konstruktorze witryn w module Commerce, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="3570e-162">To view ratings and reviews trends in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3570e-163">Przejdź do **Strona główna \> Recenzje \> Raportowanie**</span><span class="sxs-lookup"><span data-stu-id="3570e-163">Go to **Home \> Reviews \> Reporting**.</span></span>
1. <span data-ttu-id="3570e-164">Wybierz opcję **Szablon usługi PowerBI**, aby pobrać szablon.</span><span class="sxs-lookup"><span data-stu-id="3570e-164">Select **PowerBI template** to download the template.</span></span>

    ![Pobieranie szablonu Power BI](media/rnr-moderation-reports.png) 

1. <span data-ttu-id="3570e-166">Otwórz pobrany szablon za pomocą aplikacji Power BI.</span><span class="sxs-lookup"><span data-stu-id="3570e-166">Open the downloaded template by using the Power BI app.</span></span> <span data-ttu-id="3570e-167">Zamknij okno dialogowe **Dostęp do zawartości sieci Web**, które zostanie wyświetlone, a następnie zamknij wyświetlony komunikat o błędzie „Odśwież”.</span><span class="sxs-lookup"><span data-stu-id="3570e-167">Close the **Access to web content** dialog box that appears, and then close the "Refresh" error message that appears.</span></span>
1. <span data-ttu-id="3570e-168">Przejdź do **strony głównej**, wybierz opcję **Edytuj kwerendy**, a następnie wybierz **Ustawienia źródła danych**.</span><span class="sxs-lookup"><span data-stu-id="3570e-168">Go to **Home**, select **Edit queries**, and then select **Data source settings**.</span></span>
1. <span data-ttu-id="3570e-169">W oknie dialogowym **ustawienia źródła danych** wybierz opcję **Zmień źródło**.</span><span class="sxs-lookup"><span data-stu-id="3570e-169">In the **Data source settings** dialog box, select **Change Source**.</span></span>
1. <span data-ttu-id="3570e-170">W polu **adres URL** wprowadź ścieżkę danych recenzji, które zostały pobrane w poprzedniej procedurze (na przykład **c:\\reviews\\ReviewsData.csv**).</span><span class="sxs-lookup"><span data-stu-id="3570e-170">In the **URL** field, enter the path of the reviews data that you downloaded in the previous procedure (for example, **c:\\reviews\\ReviewsData.csv**).</span></span>

    ![Pole adresu URL w oknie dialogowym wartości rozdzielane przecinkami](media/rnr-powerbi-datasource-settings.png) 

1. <span data-ttu-id="3570e-172">Wybierz  **OK** i kliknij przycisk **Zastosuj zmiany**.</span><span class="sxs-lookup"><span data-stu-id="3570e-172">Select **OK**, and then select **Apply changes**.</span></span> <span data-ttu-id="3570e-173">Zastosowanie zmian w źródle danych będzie trwać jedną do dwóch minut.</span><span class="sxs-lookup"><span data-stu-id="3570e-173">It will take one to two minutes to apply your changes to the data source.</span></span>
1. <span data-ttu-id="3570e-174">Wybierz opcję **Arkusz trendów**, aby wyświetlić trendy dotyczące ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="3570e-174">Select **Trends sheet** to view ratings and reviews trends.</span></span>

    ![Trendy ocen i recenzji](media/rnr-powerbi-dashboard-template.png) 
    
## <a name="additional-resources"></a><span data-ttu-id="3570e-176">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="3570e-176">Additional resources</span></span>

[<span data-ttu-id="3570e-177">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3570e-177">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="3570e-178">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3570e-178">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="3570e-179">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="3570e-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="3570e-180">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="3570e-180">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
