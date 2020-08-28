---
title: Włączanie rekomendacji produktów
description: W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2dacd4a94f706be5aa65947c0b6a92e281733ca
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665033"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="0dea3-103">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="0dea3-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0dea3-104">W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0dea3-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="0dea3-105">Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0dea3-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="0dea3-106">Wstępne sprawdzanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="0dea3-106">Recommendations pre-check</span></span>

<span data-ttu-id="0dea3-107">Przed włączeniem należy pamiętać, że rekomendacje produktów są obsługiwane tylko dla klientów Commerce, którzy przeprowadzili migrację danych za pomocą Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="0dea3-107">Before enabling, note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage.</span></span> 

<span data-ttu-id="0dea3-108">Przed włączeniem rekomendacji należy włączyć w biurze zaplecza następujące konfiguracje:</span><span class="sxs-lookup"><span data-stu-id="0dea3-108">The following configurations must be enabled in the back office before enabling recommendations:</span></span>

1. <span data-ttu-id="0dea3-109">Upewnij się, że Azure Data Lake Storage został zakupiony i pomyślnie zweryfikowany w środowisku.</span><span class="sxs-lookup"><span data-stu-id="0dea3-109">Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment.</span></span> <span data-ttu-id="0dea3-110">Aby uzyskać więcej informacji, zobacz [Upewnij się, że Azure Data Lake Storage został zakupiony i pomyślnie zweryfikowany w środowisku](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0dea3-110">For more information, see [Ensure that Azure Data Lake Storage has been purchased and successfully verified in the environment](enable-ADLS-environment.md).</span></span>
2. <span data-ttu-id="0dea3-111">Upewnij się, że odświeżanie magazynu jednostek zostało zautomatyzowane.</span><span class="sxs-lookup"><span data-stu-id="0dea3-111">Ensure that the entity store refresh has been automated.</span></span> <span data-ttu-id="0dea3-112">Aby uzyskać więcej informacji, zobacz [Upewnij się, że odświeżanie magazynu jednostek zostało zautomatyzowane. ](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="0dea3-112">For more information, see [Ensure that the Entity store refresh has been automated](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).</span></span>
3. <span data-ttu-id="0dea3-113">Potwierdź, że konfiguracja tożsamości Azure AD zawiera wpis do Rekomendacji.</span><span class="sxs-lookup"><span data-stu-id="0dea3-113">Confirm that Azure AD Identity configuration contains an entry for Recommendations.</span></span> <span data-ttu-id="0dea3-114">Poniżej znajduje się więcej informacji dotyczących wykonywania tej akcji.</span><span class="sxs-lookup"><span data-stu-id="0dea3-114">More information on how to do this action is below.</span></span>

<span data-ttu-id="0dea3-115">Ponadto upewnij się, że zostały włączone pomiary RetailSale.</span><span class="sxs-lookup"><span data-stu-id="0dea3-115">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="0dea3-116">Aby dowiedzieć się więcej o tym procesie konfiguracji, zobacz [Praca z pomiarami](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span><span class="sxs-lookup"><span data-stu-id="0dea3-116">To learn more about this set up process, see [Work with measures](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures).</span></span>

## <a name="azure-ad-identity-configuration"></a><span data-ttu-id="0dea3-117">Identyfikator konfiguracji Azure AD</span><span class="sxs-lookup"><span data-stu-id="0dea3-117">Azure AD Identity configuration</span></span>

<span data-ttu-id="0dea3-118">Ten krok jest wymagany dla wszystkich klientów, którzy uruchamiają strukturę podsieciową jako konfigurację usługi (IaaS).</span><span class="sxs-lookup"><span data-stu-id="0dea3-118">This step is required for all customers running an infra-structure as a service (IaaS) configuration.</span></span> <span data-ttu-id="0dea3-119">W przypadku klientów korzystających z service fabric (SF) ten krok powinien być automatyczny i zaleca się sprawdzenie, czy ustawienie zostało skonfigurowane zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="0dea3-119">For customers running on service fabric (SF), this step should be automatic and we recommend verifying the setting is configured as expected.</span></span>

### <a name="setup"></a><span data-ttu-id="0dea3-120">Konfiguracja</span><span class="sxs-lookup"><span data-stu-id="0dea3-120">Setup</span></span>

1. <span data-ttu-id="0dea3-121">W zapleczu do biura wyszukaj stronę **Aplikacje Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0dea3-121">From the back office, search for the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="0dea3-122">Sprawdź, czy istnieje wpis „RecommendationSystemApplication-1”.</span><span class="sxs-lookup"><span data-stu-id="0dea3-122">Verify if an entry exists for "RecommendationSystemApplication-1".</span></span>

<span data-ttu-id="0dea3-123">Jeśli wpis nie istnieje, dodaj nowy wpis z następującymi informacjami:</span><span class="sxs-lookup"><span data-stu-id="0dea3-123">If the entry does not exist, add a new entry with the following information:</span></span>

- <span data-ttu-id="0dea3-124">**Identyfikator klienta** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span><span class="sxs-lookup"><span data-stu-id="0dea3-124">**Client Id** - d37b07e8-dd1c-4514-835d-8b918e6f9727</span></span>
- <span data-ttu-id="0dea3-125">**Nazwa** - RecommendationSystemApplication-1</span><span class="sxs-lookup"><span data-stu-id="0dea3-125">**Name** - RecommendationSystemApplication-1</span></span>
- <span data-ttu-id="0dea3-126">**Identyfikator użytkownika** — RetailServiceAccount</span><span class="sxs-lookup"><span data-stu-id="0dea3-126">**User Id** - RetailServiceAccount</span></span>

<span data-ttu-id="0dea3-127">Zapisz i zamknij stronę.</span><span class="sxs-lookup"><span data-stu-id="0dea3-127">Save and close the page.</span></span> 

## <a name="turn-on-recommendations"></a><span data-ttu-id="0dea3-128">Włączanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="0dea3-128">Turn on recommendations</span></span>

<span data-ttu-id="0dea3-129">Aby włączyć rekomendacje produktu, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="0dea3-129">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="0dea3-130">Przejdź do **Handel detaliczny i komercyjny &gt; Rekomendacje produktów &gt; Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="0dea3-130">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="0dea3-131">Na liście udostępnionych parametrów wybierz **Listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="0dea3-131">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="0dea3-132">Ustaw **Włącz rekomendacje** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0dea3-132">Set the **Enable recommendations** option to **Yes**.</span></span>

![Włączanie rekomendacji](./media/enablepersonalization.png)

> [!NOTE]
> <span data-ttu-id="0dea3-134">Ta procedura rozpoczyna proces generowania list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="0dea3-134">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="0dea3-135">Może upłynąć kilka godzin zanim listy będą dostępne i mogą być widoczne w punkcie sprzedaży (POS) lub w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0dea3-135">It may take several hours before the lists are available and can be viewed at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="0dea3-136">Konfigurowanie parametrów listy rekomendacji</span><span class="sxs-lookup"><span data-stu-id="0dea3-136">Configure recommendation list parameters</span></span>

<span data-ttu-id="0dea3-137">Domyślnie lista rekomendacji produktów opartych na AI-ML zawiera sugerowane wartości.</span><span class="sxs-lookup"><span data-stu-id="0dea3-137">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="0dea3-138">Można zmienić domyślne sugerowane wartości, tak aby odpowiadały przepływowi działalności firmy.</span><span class="sxs-lookup"><span data-stu-id="0dea3-138">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="0dea3-139">Aby dowiedzieć się więcej o zmienianiu domyślnych parametrów, należy przejść do obszaru [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="0dea3-139">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="0dea3-140">Pokaż rekomendacje dotyczące urządzeń punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="0dea3-140">Show recommendations on POS devices</span></span>

<span data-ttu-id="0dea3-141">Po włączeniu rekomendacji w bac office Commerce, pannel rekomendacje musi zostać dodany do ekranu kontrolki punktu sprzedaży (POS) za pomocą narzędzia układ.</span><span class="sxs-lookup"><span data-stu-id="0dea3-141">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="0dea3-142">Aby dowiedzieć się więcej o tym procesie, zobacz temat [Dodawanie kontroli zaleceń do ekranu transakcji na urządzeniach z punktu sprzedaży](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="0dea3-142">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="0dea3-143">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="0dea3-143">Enable personalized recommendations</span></span>

<span data-ttu-id="0dea3-144">W systemie Dynamics 365 Commerce detaliści mogą udostępniać spersonalizowane rekomendacje dotyczące produktów (znane także jako Personalizacja).</span><span class="sxs-lookup"><span data-stu-id="0dea3-144">In Dynamics 365 Commerce, retailers can make personalized product recommendations (also known as personalization) available.</span></span> <span data-ttu-id="0dea3-145">Dzięki temu spersonalizowane rekomendacje mogą być włączane do obsługi klienta w trybie online i w punkcie sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="0dea3-145">In this way, personalized recommendations can be incorporated into the online customer experience and at the point of sale.</span></span> <span data-ttu-id="0dea3-146">Gdy jest włączona funkcja personalizacji, system może skojarzyć informacje o zakupie i produkcie użytkownika w celu wygenerowania poszczególnych zaleceń dotyczących produktu.</span><span class="sxs-lookup"><span data-stu-id="0dea3-146">When the personalization functionality is turned on, the system can associate a user's purchase and product information to generate individualized product recommendations.</span></span>

<span data-ttu-id="0dea3-147">Aby uzyskać informacje o spersonalizowanych rekomendacjach, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0dea3-147">To learn more about personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0dea3-148">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0dea3-148">Additional resources</span></span>

[<span data-ttu-id="0dea3-149">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="0dea3-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="0dea3-150">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0dea3-150">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="0dea3-151">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="0dea3-151">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="0dea3-152">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="0dea3-152">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="0dea3-153">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="0dea3-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="0dea3-154">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="0dea3-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="0dea3-155">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="0dea3-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="0dea3-156">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="0dea3-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="0dea3-157">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="0dea3-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="0dea3-158">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="0dea3-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="0dea3-159">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="0dea3-159">Product recommendations FAQ</span></span>](faq-recommendations.md)

