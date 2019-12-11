---
title: Omówienie rekomendacji produktów
description: Ten temat zawiera ogólne informacje o rekomendacjach produktu. Rekomendacje produktów umożliwiają łatwe i szybkie znajdowanie produktów, które są potrzebne, a nawet produktów, których klient nie zamierzał pierwotnie kupić.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770054"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="e6676-104">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="e6676-104">Product recommendations overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e6676-105">Microsoft Dynamics 365 Commerce może posłużyć do pokazywania zaleceń dotyczących produktów w witrynie e-Commerce i urządzeniach punktu sprzedaży (POS).</span><span class="sxs-lookup"><span data-stu-id="e6676-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="e6676-106">Rekomendacje produktów to przedmioty, które mogą być interesujące dla odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="e6676-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="e6676-107">Rekomendacje są oparte na trendach zakupu innych odbiorców w sklepach internetowych oraz w sklepach tradycyjnych.</span><span class="sxs-lookup"><span data-stu-id="e6676-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="e6676-108">Zalecenia dotyczące produktów pozwalają klientom łatwo i szybko znaleźć produkty, których chcą, mając doświadczenie, które im dobrze służy.</span><span class="sxs-lookup"><span data-stu-id="e6676-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="e6676-109">Można nawet użyć sprzedaży powiązanej i oferowanie droższego produktu, aby ułatwić klientom znalezienie dodatkowych produktów niż pierwotnie zamierzone.</span><span class="sxs-lookup"><span data-stu-id="e6676-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="e6676-110">Kiedy rekomendacje są pomocne w odkrywaniu produktów, mogą stworzyć więcej możliwości konwersji, pomóc zwiększyć przychody ze sprzedaży, a nawet pomóc zwiększyć satysfakcję i utrzymanie klientów.</span><span class="sxs-lookup"><span data-stu-id="e6676-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="e6676-111">W Commerce rekomendacje produktów są oparte na technologiach uczenia maszynowego rekomendacji Microsoft na dużą skalę.</span><span class="sxs-lookup"><span data-stu-id="e6676-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="e6676-112">Scenariusze</span><span class="sxs-lookup"><span data-stu-id="e6676-112">Scenarios</span></span>

<span data-ttu-id="e6676-113">Rekomendacje produktów są dostępne w opisanych niżej scenariuszach:</span><span class="sxs-lookup"><span data-stu-id="e6676-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="e6676-114">**Na dowolnej stronie sklepu lub stronie magazynowej w e-Commerce:** Jeśli klient lub sprzedawca odwiedza stronę sklepu, aparat rekomendacji może sugerować produkty na listach **Nowości**, **Bestsellery** i **Trendy**.</span><span class="sxs-lookup"><span data-stu-id="e6676-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="e6676-115">**Na stronie Szczegóły produktu:** Jeśli klienci lub sprzedawcy odwiedzają stronę **Szczegóły produktu**, aparat rekomendacji sugeruje dodatkowe towary, które również prawdopodobnie zostaną nabyte.</span><span class="sxs-lookup"><span data-stu-id="e6676-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="e6676-116">Pozycje te pojawiają się również na liście osoby **Klientom podoba się również**.</span><span class="sxs-lookup"><span data-stu-id="e6676-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="e6676-117">**Na stronie transakcja lub stronie realizacja transakcji:** aparat rekomendacji sugeruje pozycje na podstawie całej listy towarów w koszyku.</span><span class="sxs-lookup"><span data-stu-id="e6676-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="e6676-118">Te pozycje są wyświetlane na liście **Często kupowane razem**.</span><span class="sxs-lookup"><span data-stu-id="e6676-118">These items appear in the **Frequently bought together** list.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="e6676-119">Usługa rekomendacji</span><span class="sxs-lookup"><span data-stu-id="e6676-119">Recommendation service</span></span>

<span data-ttu-id="e6676-120">Zalecenia dotyczące produktu wykorzystują technologie uczenia maszynowego Rekomendacji w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="e6676-120">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="e6676-121">Dane w formacie wymaganym przez usługę rekomendacji są pobierane z operacyjnej bazy danych Commerce i wysyłane do magazynu jednostek.</span><span class="sxs-lookup"><span data-stu-id="e6676-121">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="e6676-122">Usługa rekomendacji korzysta z danych w celu wytrenowania modeli rekomendacji dla list **Klientom podoba się również**, **Często kupowane razem**, **Nowości**, **Bestsellery** i **Trendy**.</span><span class="sxs-lookup"><span data-stu-id="e6676-122">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6676-123">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="e6676-123">Additional resources</span></span>

[<span data-ttu-id="e6676-124">Włączanie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="e6676-124">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="e6676-125">Tworzenie list zaleceń dotyczących produktów pod opieką</span><span class="sxs-lookup"><span data-stu-id="e6676-125">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="e6676-126">Zarządzanie wynikami rekomendacji produktów na podstawie plików AI-ML</span><span class="sxs-lookup"><span data-stu-id="e6676-126">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="e6676-127">Dodawanie list rekomendacji produktów do stron</span><span class="sxs-lookup"><span data-stu-id="e6676-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
