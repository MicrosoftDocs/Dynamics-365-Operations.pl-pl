---
title: Ręczne tworzenie zaleceń pod opieką
description: W tym temacie wyjaśniono, w jaki sposób merchandizers mogą tworzyć i zarządzać ręcznymi listami produktów dla odbiorców Microsoft Dynamics 365 Commerce.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e9ce8887f3cd7da0e250d3b0ffe96b222953de44
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965360"
---
# <a name="manually-create-curated-recommendations"></a><span data-ttu-id="ddaa0-103">Ręczne tworzenie zaleceń pod opieką</span><span class="sxs-lookup"><span data-stu-id="ddaa0-103">Manually create curated recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ddaa0-104">W tym temacie wyjaśniono, w jaki sposób merchandizers mogą tworzyć i zarządzać ręcznymi listami rekomendacji produktów dla odbiorców Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-104">This topic explains how merchandizers can manually create and manage product recommendations lists for Microsoft Dynamics 365 Commerce customers.</span></span>

<span data-ttu-id="ddaa0-105">Wyselekcjonowane listy to zbiory indywidualnych, treści tworzone i dostosowywane przez ludzi.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-105">Curated lists are collections of individual content, created and curated by people.</span></span>  

## <a name="create-a-new-list"></a><span data-ttu-id="ddaa0-106">Utwórz nową listę</span><span class="sxs-lookup"><span data-stu-id="ddaa0-106">Create a new list</span></span>

<span data-ttu-id="ddaa0-107">Aby utworzyć wyselekcjonowaną listę rekomendacji produktów, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-107">To create a curated product recommendation list, follow these steps.</span></span>

1. <span data-ttu-id="ddaa0-108">Przejdź do **Retail i Commerce &gt; Rekomendacje produktów &gt; Listy rekomendacji**.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-108">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation lists**.</span></span>
1. <span data-ttu-id="ddaa0-109">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-109">Select **New**.</span></span>
1. <span data-ttu-id="ddaa0-110">Wprowadź wartość w polu **Identyfikator listy**.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-110">In the **List Id** field, enter a value.</span></span>
1. <span data-ttu-id="ddaa0-111">Wprowadź wartość w polu **Nazwa listy**.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-111">In the **List name** field, enter a value.</span></span>
    - <span data-ttu-id="ddaa0-112">**Nazwa listy** jest tytułem listy, który pojawi się w sekcji list wyselekcjonowanych w module **kolekcja produktów**.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-112">The **List name** is the title of the list that will appear in the curated lists section of the **Product collection** module.</span></span>
1. <span data-ttu-id="ddaa0-113">Aby dodać produkty do listy, wybierz **Dodaj produkty**.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-113">To add products to the list, select **Add products**.</span></span>
1. <span data-ttu-id="ddaa0-114">Aby zmienić kolejność produktów z listy, należy wprowadzić wartość w kolumnie **Kolejność wyświetlania**.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-114">To change the order of the products in the list, enter a value in the **Display order** column.</span></span>
    - <span data-ttu-id="ddaa0-115">Jeśli dwa produkty mają taką samą wartość zamówienia wyświetlania, ostateczna kolejność tych dwóch wyników może się różnić od biura zaplecza.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-115">If two products have the same display order value, then the final order of those two results may differ from the back office.</span></span>
1. <span data-ttu-id="ddaa0-116">Wybierz **Zapisz**, aby zapisać listę.</span><span class="sxs-lookup"><span data-stu-id="ddaa0-116">Select **Save** to save the list.</span></span>

## <a name="example-list"></a><span data-ttu-id="ddaa0-117">Przykładowa lista</span><span class="sxs-lookup"><span data-stu-id="ddaa0-117">Example List</span></span>

![Przykładowa wyselekcjonowana lista w biurze zaplecza](./media/examplecuratedrecolist.png)

## <a name="additional-resources"></a><span data-ttu-id="ddaa0-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="ddaa0-119">Additional resources</span></span>

[<span data-ttu-id="ddaa0-120">Omówienie rekomendacji produktów</span><span class="sxs-lookup"><span data-stu-id="ddaa0-120">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="ddaa0-121">Włączanie Azure Data Lake Storage w środowisku Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ddaa0-121">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="ddaa0-122">Włącz rekomendacje produktów</span><span class="sxs-lookup"><span data-stu-id="ddaa0-122">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="ddaa0-123">Włączanie rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="ddaa0-123">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="ddaa0-124">Rezygnowanie z rekomendacji spersonalizowanych</span><span class="sxs-lookup"><span data-stu-id="ddaa0-124">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="ddaa0-125">Włącz rekomendacje „Kup podobne”</span><span class="sxs-lookup"><span data-stu-id="ddaa0-125">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="ddaa0-126">Dodawanie rekomendacji produktu w punkcie sprzedaży</span><span class="sxs-lookup"><span data-stu-id="ddaa0-126">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="ddaa0-127">Dodawanie rekomendacji do ekranu transakcji</span><span class="sxs-lookup"><span data-stu-id="ddaa0-127">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="ddaa0-128">Dostosowywanie wyników rekomendacji AI-ML</span><span class="sxs-lookup"><span data-stu-id="ddaa0-128">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="ddaa0-129">Tworzenie rekomendacji z danymi demonstracyjnymi</span><span class="sxs-lookup"><span data-stu-id="ddaa0-129">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="ddaa0-130">Rekomendacje produktów — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="ddaa0-130">Product recommendations FAQ</span></span>](faq-recommendations.md)
