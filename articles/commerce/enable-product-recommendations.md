---
title: Włączanie rekomendacji produktów
description: W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
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
ms.openlocfilehash: 879fccb063ca0b74e0f022a9edf6a15f7d1311ae
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127889"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="0433b-103">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="0433b-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0433b-104">W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0433b-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="0433b-105">Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0433b-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="0433b-106">Wstępne sprawdzanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="0433b-106">Recommendations pre-check</span></span>

<span data-ttu-id="0433b-107">Przed włączeniem należy pamiętać, że rekomendacje produktów są obsługiwane tylko dla klientów Commerce, którzy przeprowadzili migrację danych do środowiska Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="0433b-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="0433b-108">Aby uzyskać więcej informacji na temat kroków dotyczących włączania ADLS, zajrzyj do [sposobu włączenia ADLS w środowisku Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0433b-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="0433b-109">Ponadto upewnij się, że zostały włączone pomiary RetailSale.</span><span class="sxs-lookup"><span data-stu-id="0433b-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="0433b-110">Aby dowiedzieć się więcej o tym procesie konfiguracji, przejdź [tutaj.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="0433b-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="0433b-111">Włączanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="0433b-111">Turn on recommendations</span></span>

<span data-ttu-id="0433b-112">Aby włączyć rekomendacje produktu, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="0433b-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="0433b-113">Przejdź do **Handel detaliczny i komercyjny &gt; Rekomendacje produktów &gt; Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="0433b-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="0433b-114">Na liście udostępnionych parametrów wybierz **Listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="0433b-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="0433b-115">Ustaw **Włącz rekomendacje** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="0433b-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![włączanie rekomendacji produktów](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="0433b-117">Ta procedura rozpoczyna proces generowania list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="0433b-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="0433b-118">Zanim listy będą dostępne i mogą być widoczne w punkcie sprzedaży, może upłynąć kilka godzin (POS) lub w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0433b-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="0433b-119">Konfigurowanie parametrów listy rekomendacji</span><span class="sxs-lookup"><span data-stu-id="0433b-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="0433b-120">Domyślnie lista rekomendacji produktów opartych na AI-ML zawiera sugerowane wartości.</span><span class="sxs-lookup"><span data-stu-id="0433b-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="0433b-121">Można zmienić domyślne sugerowane wartości, tak aby odpowiadały przepływowi działalności firmy.</span><span class="sxs-lookup"><span data-stu-id="0433b-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="0433b-122">Aby dowiedzieć się więcej o zmienianiu domyślnych parametrów, należy przejść do obszaru [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="0433b-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="0433b-123">Pokaż rekomendacje dotyczące urządzeń punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="0433b-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="0433b-124">Po włączeniu rekomendacji w bac office Commerce, pannel rekomendacje musi zostać dodany do ekranu kontrolki punktu sprzedaży (POS) za pomocą narzędzia układ.</span><span class="sxs-lookup"><span data-stu-id="0433b-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="0433b-125">Aby dowiedzieć się więcej o tym procesie, zobacz temat [Dodawanie kontroli zaleceń do ekranu transakcji na urządzeniach z punktu sprzedaży](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="0433b-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="0433b-126">Włącz spersonalizowane rekomendacje</span><span class="sxs-lookup"><span data-stu-id="0433b-126">Enable personalized recommendations</span></span>

<span data-ttu-id="0433b-127">Aby uzyskać informacje o spersonalizowanych rekomendacjach produktów, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="0433b-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0433b-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="0433b-128">Additional resources</span></span>

[<span data-ttu-id="0433b-129">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="0433b-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="0433b-130">Włączanie ADLS w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="0433b-130">Enable ADLS in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="0433b-131">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="0433b-131">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="0433b-132">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="0433b-132">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="0433b-133">Dodawanie list rekomendacji produktów do witryny handlu elektronicznego</span><span class="sxs-lookup"><span data-stu-id="0433b-133">Add recommendation lists to an e-Commerce site</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="0433b-134">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="0433b-134">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="0433b-135">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="0433b-135">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="0433b-136">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="0433b-136">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="0433b-137">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="0433b-137">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="0433b-138">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="0433b-138">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="0433b-139">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="0433b-139">Product recommendations FAQ</span></span>](faq-recommendations.md)

