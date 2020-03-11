---
title: Omówienie ocen i recenzji
description: W tym temacie opisano oceny i recenzje w rozwiązaniu Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1248ce660d765ddade1df7d79786202235019990
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057401"
---
# <a name="ratings-and-reviews-overview"></a><span data-ttu-id="655c4-103">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="655c4-103">Ratings and reviews overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="655c4-104">W tym temacie opisano oceny i recenzje w rozwiązaniu Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="655c4-104">This topic covers ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="655c4-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="655c4-105">Overview</span></span>

<span data-ttu-id="655c4-106">Oceny i Recenzje to kluczowe znaczenie dla odbiorców w e-Commerce, którzy chcą wiedzieć, jak inni odbiorcy mogą postrzegać produkt.</span><span class="sxs-lookup"><span data-stu-id="655c4-106">Ratings and reviews are crucial for e-Commerce customers who want to know how other customers perceive a product.</span></span> <span data-ttu-id="655c4-107">Mogą oni również pomagać klientom podejmować decyzje dotyczące zakupu.</span><span class="sxs-lookup"><span data-stu-id="655c4-107">They can also help consumers make purchase decisions.</span></span> <span data-ttu-id="655c4-108">W Dynamics 365 Commerce oceny i recenzje umożliwiają detalistom przechwycenie ocen produktów i recenzji od klientów.</span><span class="sxs-lookup"><span data-stu-id="655c4-108">In Dynamics 365 Commerce, the ratings and reviews solution lets retailers capture product reviews and ratings from customers.</span></span> <span data-ttu-id="655c4-109">Detaliści mogą następnie wyświetlać średnie oceny i przeglądać informacje w całej witrynie internetowej w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="655c4-109">Retailers can then show average ratings and review information across their e-Commerce website.</span></span>

<span data-ttu-id="655c4-110">Informacje o średniej ocenie są wyświetlane w punktach sprzedaży (POS) i kanałach call center.</span><span class="sxs-lookup"><span data-stu-id="655c4-110">Average rating information is shown in point of sale (POS) and call center channels.</span></span> <span data-ttu-id="655c4-111">W związku z tym pracownicy sprzedaży mogą z niego korzystać, aby pomóc użytkownikom w podejmowaniu decyzji.</span><span class="sxs-lookup"><span data-stu-id="655c4-111">Therefore, sales associates can use it to help users make decisions.</span></span> <span data-ttu-id="655c4-112">Oceny i recenzje mogą również służyć jako mechanizm przekazywania opinii, z którego mogą korzystać detaliści w celu poprawy jakości produktu, a tym samym zwiększenia sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="655c4-112">Ratings and reviews can also serve as a feedback mechanism that retailers can use to improve the quality of a product and therefore increase sales.</span></span>

<span data-ttu-id="655c4-113">Funkcje ocen i recenzji w Dynamics 365 Commerce to rozwiązanie wielokanałowe i jest od początku dostępne jako część platformy.</span><span class="sxs-lookup"><span data-stu-id="655c4-113">Ratings and reviews functionality in Dynamics 365 Commerce is an omnichannel solution and is natively available as part of the platform.</span></span> <span data-ttu-id="655c4-114">Oceny i recenzje są tworzone na górnej części Microsoft Azure, co zapewnia wysoką skalowalność i niezawodność.</span><span class="sxs-lookup"><span data-stu-id="655c4-114">The ratings and reviews solution is built on top of Microsoft Azure, which provides high scalability and reliability.</span></span>

<span data-ttu-id="655c4-115">Na poniższej ilustracji przedstawiono sposób działania rozwiązania oceny i recenzji w Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="655c4-115">The following illustration shows how the ratings and reviews solution works in Dynamics 365 Commerce.</span></span>

![Oceny i recenzje w Dynamics 365 for Commerce](media/Dynamics-365-Commerce-Ratings-and-Reviews-Overview.jpg)

<span data-ttu-id="655c4-117">Oceny i recenzje w Dynamics 365 Commerce korzystają z Azure Cognitive Services w celu zaoferowania automatycznego łagodzenia wulgarnych słów w 40 językach.</span><span class="sxs-lookup"><span data-stu-id="655c4-117">The ratings and reviews solution in Dynamics 365 Commerce uses Azure Cognitive Services to offer automatic moderation of profane words in 40 languages.</span></span> <span data-ttu-id="655c4-118">Ponieważ zatwierdzanie przez ludzi nie jest wymagane, koszty moderacji są redukowane.</span><span class="sxs-lookup"><span data-stu-id="655c4-118">Because human approval isn't required, moderation costs are reduced.</span></span> <span data-ttu-id="655c4-119">System oferuje również narzędzia moderatora, których można używać do reagowania na obawy klientów, opinie i żądania usuwania oraz do odpowiadania na żądania danych od użytkowników.</span><span class="sxs-lookup"><span data-stu-id="655c4-119">The system also offers moderator tools that can be used to respond to customer concerns, feedback, and take-down requests, and to address data requests from users.</span></span>

<span data-ttu-id="655c4-120">Rozwiązanie oceny i recenzje zawiera widżety przedstawiające podsumowania ocen na listach produktów, wyniki wyszukiwania, strony szczegółów produktów i w innych miejscach.</span><span class="sxs-lookup"><span data-stu-id="655c4-120">The ratings and reviews solution provides widgets that show rating summaries in product lists, in search results, on product details page, and in other places.</span></span> <span data-ttu-id="655c4-121">Widżety zawierają listę kompletnych przeglądów, a ponadto udostępniają opcje sortowania i filtrowania.</span><span class="sxs-lookup"><span data-stu-id="655c4-121">The widgets show complete review lists, and they also provide sorting and filtering options.</span></span>

<span data-ttu-id="655c4-122">Rozwiązanie oceny i recenzje zawiera również szablon analizy biznesowej (BI), który zawiera zbiór miar zapewniających wgląd w oceny i recenzje.</span><span class="sxs-lookup"><span data-stu-id="655c4-122">The ratings and reviews solution also provides a business intelligence (BI) template that includes a set of metrics to provide insights into ratings and reviews.</span></span> <span data-ttu-id="655c4-123">Można wyeksportować dane dotyczące ocen i recenzji do dalszej analizy.</span><span class="sxs-lookup"><span data-stu-id="655c4-123">Ratings and reviews data can be exported for further analysis.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="655c4-124">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="655c4-124">Additional resources</span></span>

[<span data-ttu-id="655c4-125">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="655c4-125">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="655c4-126">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="655c4-126">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="655c4-127">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="655c4-127">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="655c4-128">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="655c4-128">Sync product ratings in Dynamics 365 Commerce</span></span>](sync-product-ratings.md)
