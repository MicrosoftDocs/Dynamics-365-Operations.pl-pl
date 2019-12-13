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
# <a name="opt-in-to-use-ratings-and-reviews"></a>Zgoda na korzystanie z ocen i recenzji

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak korzystać z klasyfikacji i recenzji w witrynie Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Rozwiązanie oceny i recenzje to rozwiązanie wielokanałowe, które można udostępnić w Dynamics 365 Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS). LCS jest portalem administracyjnym używanym przez detalistów do zarządzania swoimi środowiskami w celu likwidacji.

Jeśli chcesz używać rozwiązania ocen i recenzji w witrynie Commerce, musisz najpierw wybrać tę opcję.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Zgoda na korzystanie z ocen i recenzji

Aby korzystać z ocen i recenzji w witrynie, wykonaj następujące kroki.

1. Postępuj zgodnie z instrukcjami w [Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md).
1. Gdy wciąż jesteś w usługi LCS, przejdź do **Konfiguracja wdrożenia modułu Retail \> Inne ustawienia**.
1. Ustaw opcję **Włącz obsługę ocen i recenzji** na wartość **Tak**.
1. W grupie zabezpieczeń usługi **AAD na potrzeby moderatora ocen i recenzji (identyfikator obiektu grupy zabezpieczeń)** wprowadź identyfikator grupy zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zawiera moderatorów ocen i recenzji.

    ![Zgoda na korzystanie z ocen i recenzji](media/LCS_RnR_Preference.png)

1. Zakończ proces inicjowania w e-Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Konfigurowanie ocen i recenzji](configure-ratings-reviews.md)

[Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail](sync-product-ratings.md)
