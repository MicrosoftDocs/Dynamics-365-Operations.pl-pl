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
ms.openlocfilehash: ecda571a356c6968196d09cc19923105cf4544ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770146"
---
# <a name="enable-product-recommendations"></a><span data-ttu-id="abed1-103">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="abed1-103">Enable product recommendations</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="abed1-104">W tym temacie wyjaśniono, jak udostępnić rekomendacje produktów oparte na sztucznym uczeniu maszynowym (AI-ML) dostępne dla klientów Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="abed1-104">This topic explains how to make product recommendations that are based on artificial intelligence-machine learning (AI-ML) available for Microsoft Dynamics 365 Commerce customers.</span></span> <span data-ttu-id="abed1-105">Aby uzyskać więcej informacji na temat zaleceń dotyczących listy rekomendacji, zapoznaj się z [Omówienie rekomendacji produktów](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="abed1-105">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="recommendations-pre-check"></a><span data-ttu-id="abed1-106">Wstępne sprawdzanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="abed1-106">Recommendations pre-check</span></span>
<span data-ttu-id="abed1-107">Przed włączeniem należy pamiętać, że rekomendacje produktów są obsługiwane tylko dla klientów F&O obsługujących wersję 10.0.6 i którzy przeprowadzili migrację pamięci do BDL.</span><span class="sxs-lookup"><span data-stu-id="abed1-107">Before enabling, please note that product recommendations are only supported for F&O customers supporting build 10.0.6 and have migrated their storage to using BDL.</span></span> 

<span data-ttu-id="abed1-108">Ponadto upewnij się, że zostały włączone pomiary RetailSale.</span><span class="sxs-lookup"><span data-stu-id="abed1-108">Additionally, ensure that RetailSale measurements have been enabled.</span></span> <span data-ttu-id="abed1-109">Aby dowiedzieć się więcej o tym procesie konfiguracji, przejdź [tutaj.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span><span class="sxs-lookup"><span data-stu-id="abed1-109">To Learn more about this set up process, go [here.](https://docs.microsoft.com/en-us/dynamics365/ai/customer-insights/pm-measures)</span></span>


## <a name="turn-on-recommendations"></a><span data-ttu-id="abed1-110">Włączanie rekomendacji</span><span class="sxs-lookup"><span data-stu-id="abed1-110">Turn on recommendations</span></span>

<span data-ttu-id="abed1-111">Aby włączyć rekomendacje produktu, wykonaj następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="abed1-111">To turn on product recommendations, follow these steps.</span></span>

1. <span data-ttu-id="abed1-112">Przejdź do **Retail** &gt; **Rekomendacje produktów** &gt; **Właściwości rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="abed1-112">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation parameters**.</span></span>
1. <span data-ttu-id="abed1-113">Na liście udostępnionych parametrów sieci sprzedaży wybierz **listę rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="abed1-113">In the list of retail shared parameters, select **Recommendation Lists**.</span></span>
1. <span data-ttu-id="abed1-114">Ustaw **Włącz rekomendacje** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="abed1-114">Set the **Enable recommendations** option to **Yes**.</span></span>

![włączanie rekomendacji produktów](./media/enableproductrecommendations.png)

> [!NOTE]
> <span data-ttu-id="abed1-116">Ta procedura rozpoczyna proces generowania list rekomendacji produktów.</span><span class="sxs-lookup"><span data-stu-id="abed1-116">This procedure starts the process of generating product recommendation lists.</span></span> <span data-ttu-id="abed1-117">Zanim listy będą dostępne i mogą być widoczne w punkcie sprzedaży, może upłynąć kilka godzin (POS) lub w Dynamics 365 for Commerce.</span><span class="sxs-lookup"><span data-stu-id="abed1-117">Up to several hours might be required before the lists are available and can be seen at the point of sale (POS) or in Dynamics 365 for Commerce.</span></span>

## <a name="configure-recommendation-list-parameters"></a><span data-ttu-id="abed1-118">Konfigurowanie parametrów listy rekomendacji</span><span class="sxs-lookup"><span data-stu-id="abed1-118">Configure recommendation list parameters</span></span>
<span data-ttu-id="abed1-119">Domyślnie lista rekomendacji produktów opartych na AI-ML zawiera sugerowane wartości.</span><span class="sxs-lookup"><span data-stu-id="abed1-119">By default, the AI-ML-based product recommendation list provides suggested values.</span></span> <span data-ttu-id="abed1-120">Można zmienić domyślne sugerowane wartości, tak aby odpowiadały przepływowi działalności firmy.</span><span class="sxs-lookup"><span data-stu-id="abed1-120">You can change the default suggested values to suit the flow of your business.</span></span> <span data-ttu-id="abed1-121">Aby dowiedzieć się więcej o zmienianiu domyślnych parametrów, należy przejść do obszaru [Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML](modify-product-recommendation-results.md).</span><span class="sxs-lookup"><span data-stu-id="abed1-121">To learn more about how to change the default parameters, go to [Manage AI-ML-based product recommendation results](modify-product-recommendation-results.md).</span></span>

## <a name="show-recommendations-on-pos-devices"></a><span data-ttu-id="abed1-122">Pokaż rekomendacje dotyczące urządzeń punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="abed1-122">Show recommendations on POS devices</span></span>
<span data-ttu-id="abed1-123">Po włączeniu rekomendacji w biurze zaplecza, pannel rekomendacje musi zostać dodany do ekranu kontrolki punktu sprzedaży (POS) za pomocą narzędzia układ.</span><span class="sxs-lookup"><span data-stu-id="abed1-123">After enabling recommendations in the back office, the recommendations pannel must be added to the control POS screen via the layout tool.</span></span> <span data-ttu-id="abed1-124">Aby dowiedzieć się o tym procesie konfiguracji, przejdź [tutaj.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span><span class="sxs-lookup"><span data-stu-id="abed1-124">To learn about this process, go [here.](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)</span></span>


## <a name="additional-resources"></a><span data-ttu-id="abed1-125">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="abed1-125">Additional resources</span></span>

[<span data-ttu-id="abed1-126">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="abed1-126">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="abed1-127">Dodawanie list rekomendacji produktów do stron</span><span class="sxs-lookup"><span data-stu-id="abed1-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)

[<span data-ttu-id="abed1-128">Dodaj panel rekomendacji do urządzeń punktu sprzedaży (POS)</span><span class="sxs-lookup"><span data-stu-id="abed1-128">Add recommendations panel to POS devices</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/add-recommendations-control-pos-screen)


