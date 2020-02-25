---
title: Włączanie rekomendacji produktów
description: W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: 2d3f1bc2526eeacb4bd6338a0679eadd95a75989
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024963"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="1851b-103">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="1851b-103">Enable product recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1851b-104">W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1851b-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="1851b-105">Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="1851b-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="1851b-106">Wstępne sprawdzanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="1851b-106">Recommendations pre-check</span></span>

<span data-ttu-id="1851b-107">Przed włączeniem należy pamiętać, że rekomendacje produktów są obsługiwane tylko dla klientów Commerce, którzy przeprowadzili migrację danych do środowiska Azure Data Lake Storage (ADLS).</span><span class="sxs-lookup"><span data-stu-id="1851b-107">Before enabling, please note that product recommendations are only supported for Commerce customers who have migrated their storage to using Azure Data Lake Storage (ADLS).</span></span> 

<span data-ttu-id="1851b-108">Aby uzyskać więcej informacji na temat kroków dotyczących włączania ADLS, zajrzyj do [sposobu włączenia ADLS w środowisku Dynamics 365](enable-ADLS-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1851b-108">For steps on enabling ADLS, see [How to enable ADLS in a Dynamics 365 environment](enable-ADLS-environment.md).</span></span>

<span data-ttu-id="1851b-109">Ponadto upewnij się, że zostały włączone pomiary RetailSale.</span><span class="sxs-lookup"><span data-stu-id="1851b-109">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="1851b-110">Aby dowiedzieć się więcej o tym procesie konfiguracji, przejdź [tutaj.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="1851b-110">To learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="1851b-111">Włączanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="1851b-111">Turn on recommendations</span></span>

<span data-ttu-id="1851b-112">Aby włączyć rekomendacje produktu, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="1851b-112">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="1851b-113">Przejdź do **Handel detaliczny i komercyjny &gt; Rekomendacje produktów &gt; Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="1851b-113">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation parameters**.</span></span>
1. <span data-ttu-id="1851b-114">Na liście udostępnionych parametrów wybierz **Listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="1851b-114">In the list of shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="1851b-115">Ustaw **Włącz rekomendacje** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="1851b-115">Set the **Enable recommendations** option to **Yes**.</span></span>

![włączanie rekomendacji produktów](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="1851b-117">Ta procedura rozpoczyna proces generowania list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="1851b-117">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="1851b-118">Zanim listy będą dostępne i mogą być widoczne w punkcie sprzedaży, może upłynąć kilka godzin (POS) lub w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1851b-118">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="1851b-119">Konfigurowanie parametrów listy rekomendacji</span><span class="sxs-lookup"><span data-stu-id="1851b-119">Configure recommendation list parameters</span></span>

<span data-ttu-id="1851b-120">Domyślnie lista rekomendacji produktów opartych na AI-ML zawiera sugerowane wartości.</span><span class="sxs-lookup"><span data-stu-id="1851b-120">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="1851b-121">Można zmienić domyślne sugerowane wartości, tak aby odpowiadały przepływowi działalności firmy.</span><span class="sxs-lookup"><span data-stu-id="1851b-121">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="1851b-122">Aby dowiedzieć się więcej o zmienianiu domyślnych parametrów, należy przejść do obszaru [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="1851b-122">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="1851b-123">Pokaż rekomendacje dotyczące urządzeń punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="1851b-123">Show recommendations on POS devices</span></span>

<span data-ttu-id="1851b-124">Po włączeniu rekomendacji w bac office Commerce, pannel rekomendacje musi zostać dodany do ekranu kontrolki punktu sprzedaży (POS) za pomocą narzędzia układ.</span><span class="sxs-lookup"><span data-stu-id="1851b-124">After enabling recommendations in Commerce back office, the recommendations panel must be added to the control POS screen using the layout tool.</span></span> <span data-ttu-id="1851b-125">Aby dowiedzieć się więcej o tym procesie, zobacz temat [Dodawanie kontroli zaleceń do ekranu transakcji na urządzeniach z punktu sprzedaży](add-recommendations-control-pos-screen.md).</span><span class="sxs-lookup"><span data-stu-id="1851b-125">To learn about this process, see [Add a recommendations control to the transaction screen on POS devices](add-recommendations-control-pos-screen.md).</span></span> 

## <a name="enable-personalized-recommendations"></a><span data-ttu-id="1851b-126">Włącz spersonalizowane rekomendacje</span><span class="sxs-lookup"><span data-stu-id="1851b-126">Enable personalized recommendations</span></span>

<span data-ttu-id="1851b-127">Aby uzyskać informacje o spersonalizowanych rekomendacjach produktów, zobacz [Włączanie spersonalizowanych rekomendacji](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="1851b-127">To learn more about how to receive personalized recommendations, see [Enable personalized recommendations](personalized-recommendations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1851b-128">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="1851b-128">Additional resources</span></span>

[<span data-ttu-id="1851b-129">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="1851b-129">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="1851b-130">Włącz spersonalizowane rekomendacje</span><span class="sxs-lookup"><span data-stu-id="1851b-130">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="1851b-131">Dodawanie list rekomendacji produktów do stron</span><span class="sxs-lookup"><span data-stu-id="1851b-131">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="1851b-132">Dodaj panel rekomendacji do urządzeń punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="1851b-132">Add recommendations panel to POS devices</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="1851b-133">Omówienie modułu kolekcji produktów</span><span class="sxs-lookup"><span data-stu-id="1851b-133">Product collection module overview</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="1851b-134">Włączanie ADLS w środowisku Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1851b-134">Enable ADLS in Dynamics 365 environment</span></span>](enable-ADLS-environment.md)

