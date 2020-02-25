---
title: Zgoda na korzystanie z ocen i recenzji
description: W tym temacie wyjaśniono, jak korzystać z klasyfikacji i recenzji w witrynie Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
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
ms.openlocfilehash: eda7fbaeea8d3c1a07f7b43cafe44886d149a211
ms.sourcegitcommit: 1e6c8163da5818196769eb278afb3a2335d0cbe3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027272"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="f07c1-103">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="f07c1-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f07c1-104">W tym temacie wyjaśniono, jak korzystać z klasyfikacji i recenzji w witrynie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f07c1-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="f07c1-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="f07c1-105">Overview</span></span>

<span data-ttu-id="f07c1-106">Rozwiązanie oceny i recenzje to rozwiązanie wielokanałowe, które można udostępnić w Dynamics 365 Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="f07c1-106">The ratings and reviews solution is an omni-channel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="f07c1-107">LCS jest portalem administracyjnym używanym przez detalistów do zarządzania swoimi środowiskami w celu likwidacji.</span><span class="sxs-lookup"><span data-stu-id="f07c1-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="f07c1-108">Jeśli chcesz używać rozwiązania klasyfikacji i recenzji w witrynie Commerce, musisz korzystać z klasyfikacji i przeglądów podczas wdrażania witryny handlu elektronicznego w systemie Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f07c1-108">If you want to use the ratings and reviews solution on your Commerce website, you must opt in for ratings and reviews during deployment of your e-Commerce site on Dynamics 365 Commerce.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="f07c1-109">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="f07c1-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="f07c1-110">Aby korzystać z ocen i recenzji w witrynie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f07c1-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="f07c1-111">Postępuj zgodnie z instrukcjami w [Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="f07c1-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="f07c1-112">Gdy wciąż jesteś w usługi LCS, przejdź do **Konfiguracja wdrożenia modułu Retail \> Inne ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="f07c1-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="f07c1-113">Ustaw opcję **Włącz obsługę ocen i recenzji** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="f07c1-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="f07c1-114">W grupie zabezpieczeń usługi **AAD na potrzeby moderatora ocen i recenzji (identyfikator obiektu grupy zabezpieczeń)** wprowadź identyfikator grupy zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zawiera moderatorów ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="f07c1-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Zgoda na korzystanie z ocen i recenzji](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="f07c1-116">Zakończ proces inicjowania w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="f07c1-116">Complete the e-Commerce initialization process.</span></span>

> [!NOTE] 
> <span data-ttu-id="f07c1-117">Jeśli użytkownik jest istniejącym odbiorcą Dynamics 365 Commerce, który już wdrożył witrynę handlu elektronicznego bez wyboru w zakresie klasyfikacji i przeglądów, a teraz chce użyć w pakiecie Dynamics 365 Commerce klasyfikacji i recenzji, należy przesłać żądanie usługi.</span><span class="sxs-lookup"><span data-stu-id="f07c1-117">If you are an existing Dynamics 365 Commerce customer who has already deployed an e-Commerce site without having opted in for ratings and reviews and now want to use ratings and reviews from the Dynamics 365 Commerce package, please submit a service request.</span></span> <span data-ttu-id="f07c1-118">Aby uzyskać informacje dotyczące sposobu przesyłania zlecenia serwisowego, przejrzyj [proces przesyłania wniosków serwisowych](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f07c1-118">For information about how to submit a service request, see [Submit service requests process](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="f07c1-119">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="f07c1-119">Additional resources</span></span>

[<span data-ttu-id="f07c1-120">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="f07c1-120">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="f07c1-121">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="f07c1-121">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="f07c1-122">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="f07c1-122">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="f07c1-123">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="f07c1-123">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)


