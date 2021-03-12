---
title: Konfigurowanie ocen i recenzji
description: W tym temacie opisano sposób konfigurowania witryny e-Commerce w celu wyświetlania ocen odbiorców i recenzji w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3fcdf571378c25d71b3ef4f3baad062a25390417
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993557"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="905c6-103">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="905c6-103">Configure ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="905c6-104">W tym temacie opisano sposób konfigurowania witryny e-Commerce w celu wyświetlania ocen odbiorców i recenzji w Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="905c6-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="905c6-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="905c6-105">Overview</span></span>

<span data-ttu-id="905c6-106">Oceny i Recenzje w witrynach e-Commerce umożliwiają klientom zapoznanie się z produktami przed podjęciem decyzji o zakupie, kierując ich uwagę na te produkty.</span><span class="sxs-lookup"><span data-stu-id="905c6-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision by showing them what other customers think about those products.</span></span> <span data-ttu-id="905c6-107">W przypadku witryn e-Commerce, oceny i recenzje są również mechanizmami zbierania opinii klientów dotyczących produktów.</span><span class="sxs-lookup"><span data-stu-id="905c6-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="905c6-108">Skonfiguruj witrynę, aby wyświetlała oceny i recenzje</span><span class="sxs-lookup"><span data-stu-id="905c6-108">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="905c6-109">Wartości konfiguracji ocen i recenzji, takie jak identyfikator dzierżawcy, długość tekstu recenzji i długość tytułu recenzji, są konfigurowane na poziomie witryny.</span><span class="sxs-lookup"><span data-stu-id="905c6-109">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="905c6-110">Aby skonfigurować witrynę do wyświetlania ocen i recenzji, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="905c6-110">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="905c6-111">Przejdź do **Widok główny \> Strony**.</span><span class="sxs-lookup"><span data-stu-id="905c6-111">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="905c6-112">Wybierz nazwę swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="905c6-112">Select the name of your site.</span></span> 
1. <span data-ttu-id="905c6-113">Przejdź do **Ustawień witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="905c6-113">Go to **Site settings \> Extensions**.</span></span> 
1. <span data-ttu-id="905c6-114">W polu **Maksymalna długość tekstu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tekst recenzji (na przykład **1000**).</span><span class="sxs-lookup"><span data-stu-id="905c6-114">In the **Review text max length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="905c6-115">W polu **Maksymalna długość tytułu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tytuł recenzji (na przykład **55**).</span><span class="sxs-lookup"><span data-stu-id="905c6-115">In the **Review title max length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="905c6-116">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="905c6-116">Select **Save and Publish**.</span></span> 

<span data-ttu-id="905c6-117">Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="905c6-117">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfigurowanie witryny, aby wyświetlała oceny i recenzje](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="905c6-119">Łączenie oceny produktu z sekcją recenzji w PDP</span><span class="sxs-lookup"><span data-stu-id="905c6-119">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="905c6-120">Ocena produktu jest wyświetlana pod tytułem produktu u góry PDP.</span><span class="sxs-lookup"><span data-stu-id="905c6-120">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="905c6-121">Ocenę produktu można skonfigurować tak, aby była połączona z sekcją **Recenzje** tej samej strony PDP.</span><span class="sxs-lookup"><span data-stu-id="905c6-121">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="905c6-122">Aby połączyć ocenę produktu z sekcją **Recenzje** PDP, należy wykonać następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="905c6-122">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="905c6-123">Otwórz szablon PDP.</span><span class="sxs-lookup"><span data-stu-id="905c6-123">Open the PDP template.</span></span> 
1. <span data-ttu-id="905c6-124">Przejdź do **Ustawienia modułu kontenera pola zakupu**.</span><span class="sxs-lookup"><span data-stu-id="905c6-124">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="905c6-125">W **Polu zakupu** wybierz opcję **Oceny produktów**, a następnie zaznacz pole wyboru **Połącz kliknięcie z modułem pełnych ocen**.</span><span class="sxs-lookup"><span data-stu-id="905c6-125">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="905c6-126">Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="905c6-126">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Łączenie oceny produktu z sekcją recenzji w PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="905c6-128">Konfiguruj łącze do strony prywatność i zasady</span><span class="sxs-lookup"><span data-stu-id="905c6-128">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="905c6-129">Aby skonfigurować link do strony prywatności i zasad, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="905c6-129">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="905c6-130">Przejdź do **Widok główny \> Strony**.</span><span class="sxs-lookup"><span data-stu-id="905c6-130">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="905c6-131">Wybierz nazwę swojej witryny.</span><span class="sxs-lookup"><span data-stu-id="905c6-131">Select the name of your site.</span></span> 
1. <span data-ttu-id="905c6-132">Przejdź do **Ustawień witryny \> Rozszerzenia**.</span><span class="sxs-lookup"><span data-stu-id="905c6-132">Go to **Site settings \> Extensions**.</span></span>
1. <span data-ttu-id="905c6-133">Na karcie **Marszruty** w obszarze **RNR prywatność i zasady** wybierz opcję **Dodaj łącze**.</span><span class="sxs-lookup"><span data-stu-id="905c6-133">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="905c6-134">Jeśli łącze zostało już wprowadzone i ma zostać zamienione, należy zaznaczyć łącze.</span><span class="sxs-lookup"><span data-stu-id="905c6-134">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="905c6-135">W oknie dialogowym **Dodawj łącze** wybierz łącze do strony prywatność i zasady, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="905c6-135">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="905c6-136">Wybierz **Zapisz i opublikuj**.</span><span class="sxs-lookup"><span data-stu-id="905c6-136">Select **Save and Publish**.</span></span> 

<span data-ttu-id="905c6-137">Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="905c6-137">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Konfiguracja łącza do strony prywatność i zasady](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a><span data-ttu-id="905c6-139">Konfiguruj moduły ocen i recenzji na stronach szczegółów produktu</span><span class="sxs-lookup"><span data-stu-id="905c6-139">Configure ratings and reviews modules on product details pages</span></span>

<span data-ttu-id="905c6-140">Aby uzyskać informacje na temat konfigurowania modułów oceny i przeglądu, patrz [moduły oceny i przeglądów](ratings-reviews-modules.md).</span><span class="sxs-lookup"><span data-stu-id="905c6-140">For information on configuring ratings and reviews modules on product details pages, see [Ratings and reviews modules](ratings-reviews-modules.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="905c6-141">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="905c6-141">Additional resources</span></span>

[<span data-ttu-id="905c6-142">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="905c6-142">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="905c6-143">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="905c6-143">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="905c6-144">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="905c6-144">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="905c6-145">Konfiguruj moduły ocen i recenzji na stronach szczegółów produktu</span><span class="sxs-lookup"><span data-stu-id="905c6-145">Configure ratings and reviews modules on product details pages</span></span>](ratings-reviews-modules.md)

[<span data-ttu-id="905c6-146">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="905c6-146">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
