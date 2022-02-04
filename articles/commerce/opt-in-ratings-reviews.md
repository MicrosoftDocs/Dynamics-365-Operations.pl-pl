---
# required metadata
title: Zgoda na korzystanie z ocen i recenzji
description: 'W tym temacie wyjaśniono, jak korzystać z klasyfikacji i recenzji w witrynie Microsoft Dynamics 365 Commerce.'
author: gvrmohanreddy
ms.date: 01/30/2020
ms.topic: article
ms.prod: null
ms.technology: null
audience: Application User
ms.reviewer: v-chgri
ms.custom: null
ms.assetid: null
ms.search.region: Global
ms.search.industry: null
ms.author: gmohanv
ms.search.validFrom: '2019-10-31'
ms.dyn365.ops.version: Release 10.0.5
---

# <a name="opt-in-to-use-ratings-and-reviews"></a>Zgoda na korzystanie z ocen i recenzji

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono, jak korzystać z klasyfikacji i recenzji w witrynie Microsoft Dynamics 365 Commerce.

Rozwiązanie oceny i recenzje to rozwiązanie wielokanałowe, które można udostępnić w Dynamics 365 Commerce za pomocą Microsoft Dynamics Lifecycle Services (usługi LCS). LCS jest portalem administracyjnym używanym przez detalistów do zarządzania swoimi środowiskami w celu likwidacji.

Jeśli chcesz używać rozwiązania klasyfikacji i recenzji w witrynie Commerce, musisz korzystać z klasyfikacji i przeglądów podczas wdrażania witryny handlu elektronicznego w systemie Dynamics 365 Commerce.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Zgoda na korzystanie z ocen i recenzji

Aby korzystać z ocen i recenzji w witrynie, wykonaj następujące kroki.

1. Postępuj zgodnie z instrukcjami w [Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md).
1. Gdy wciąż jesteś w usługi LCS, przejdź do **Konfiguracja wdrożenia modułu Retail \> Inne ustawienia**.
1. Ustaw opcję **Włącz obsługę ocen i recenzji** na wartość **Tak**.
1. W grupie zabezpieczeń usługi **AAD na potrzeby moderatora ocen i recenzji (identyfikator obiektu grupy zabezpieczeń)** wprowadź identyfikator grupy zabezpieczeń Microsoft Azure Active Directory (Azure AD), która zawiera moderatorów ocen i recenzji.

    ![Zgoda na korzystanie z ocen i recenzji.](media/LCS_RnR_Preference.png)

1. Zakończ proces inicjowania w e-Commerce.

> [!NOTE] 
> Jeśli użytkownik jest istniejącym odbiorcą Dynamics 365 Commerce, który już wdrożył witrynę handlu elektronicznego bez wyboru w zakresie klasyfikacji i przeglądów, a teraz chce użyć w pakiecie Dynamics 365 Commerce klasyfikacji i recenzji, należy przesłać żądanie usługi. Aby uzyskać informacje dotyczące sposobu przesyłania zlecenia serwisowego, przejrzyj [proces przesyłania wniosków serwisowych](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Konfigurowanie ocen i recenzji](configure-ratings-reviews.md)

[Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Commerce](sync-product-ratings.md)

[Włączanie ręcznego publikowania ocen i recenzji przez moderatora](manual-publish-rating-reviews.md)

[Importowanie i eksportowanie klasyfikacji oraz przeglądów](import-export-reviews.md)

[Konfigurowanie uwierzytelniania usługa-usługa](service-to-service-auth.md)

[Oceny i recenzje — często zadawane pytania](ratings-reviews-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
