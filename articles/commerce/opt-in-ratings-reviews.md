---
title: Zgoda na korzystanie z ocen i recenzji
description: W tym temacie wyjaśniono, jak korzystać z klasyfikacji i recenzji w witrynie Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697987"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="5905b-103">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="5905b-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="5905b-104">W tym temacie wyjaśniono, jak korzystać z klasyfikacji i recenzji w witrynie Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5905b-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="5905b-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="5905b-105">Overview</span></span>

<span data-ttu-id="5905b-106">Rozwiązanie oceny i recenzje to rozwiązanie wielokanałowe, które można udostępnić w Dynamics 365 Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS).</span><span class="sxs-lookup"><span data-stu-id="5905b-106">The ratings and reviews solution is an omnichannel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="5905b-107">LCS jest portalem administracyjnym używanym przez detalistów do zarządzania swoimi środowiskami w celu likwidacji.</span><span class="sxs-lookup"><span data-stu-id="5905b-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="5905b-108">Jeśli chcesz używać rozwiązania ocen i recenzji w witrynie Commerce, musisz najpierw wybrać tę opcję.</span><span class="sxs-lookup"><span data-stu-id="5905b-108">If you want to use the ratings and reviews solution on your Commerce website, you must first opt in.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="5905b-109">Zgoda na korzystanie z ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="5905b-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="5905b-110">Aby korzystać z ocen i recenzji w witrynie, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="5905b-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="5905b-111">Postępuj zgodnie z instrukcjami w [Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="5905b-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="5905b-112">Gdy wciąż jesteś w usługi LCS, przejdź do **Konfiguracja wdrożenia modułu Retail \> Inne ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="5905b-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="5905b-113">Ustaw opcję **Włącz obsługę ocen i recenzji** na wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="5905b-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="5905b-114">W grupie zabezpieczeń usługi **AAD na potrzeby moderatora ocen i recenzji (identyfikator obiektu grupy zabezpieczeń)** wprowadź identyfikator grupy zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zawiera moderatorów ocen i recenzji.</span><span class="sxs-lookup"><span data-stu-id="5905b-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Zgoda na korzystanie z ocen i recenzji](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="5905b-116">Zakończ proces inicjowania w e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="5905b-116">Complete the e-Commerce initialization process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5905b-117">Dodatkowe zasoby</span><span class="sxs-lookup"><span data-stu-id="5905b-117">Additional resources</span></span>

[<span data-ttu-id="5905b-118">Omówienie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="5905b-118">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="5905b-119">Zarządzanie ocenami i recenzjami</span><span class="sxs-lookup"><span data-stu-id="5905b-119">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="5905b-120">Konfigurowanie ocen i recenzji</span><span class="sxs-lookup"><span data-stu-id="5905b-120">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="5905b-121">Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="5905b-121">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
