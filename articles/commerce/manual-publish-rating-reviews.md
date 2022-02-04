---
# required metadata
title: Włączanie ręcznego publikowania ocen i recenzji przez moderatora
description: W tym temacie opisano sposób włączania ręcznego publikowania ocen i recenzji przez moderatora w aplikacji Microsoft Dynamics 365 Commerce oraz ręcznego publikowania ocen i recenzji.
author: gvrmohanreddy
manager: annbe
ms.date: 09/03/2021
ms.topic: article
ms.prod: null
ms.service: dynamics-365-commerce
ms.technology: null
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: 'Retail, Core, Operations'
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: '2021-09-03'
ms.dyn365.ops.version: 10.0.22
---

# <a name="enable-manual-publishing-of-ratings-and-reviews-by-a-moderator"></a>Włączanie ręcznego publikowania ocen i recenzji przez moderatora

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączania ręcznego publikowania ocen i recenzji przez moderatora w aplikacji Microsoft Dynamics 365 Commerce oraz ręcznego publikowania ocen i recenzji.

W rozwiązaniu „oceny i przeglądy” w aplikacji Dynamics 365 Commerce jest używana usługa Azure Cognitive Services do automatycznego redagowania przekleństw w tytułach i zawartości recenzji oraz do publikowania ocen i recenzji. Dlatego nie jest wymagane ręczne sprawdzanie przed przeglądaniem i publikowaniem ocen i recenzji w witrynie e-commerce.

Jednak niektóre firmy mogą preferować ręczne przeglądanie i zatwierdzanie recenzji przed ich opublikowaniem. Aby umożliwić ręczne publikowanie ocen i recenzji przez moderatora, należy włączyć funkcję **Wymagaj moderatora dla ocen i recenzji** w konstruktorze witryn Commerce.

## <a name="enable-the-require-moderator-for-ratings-and-reviews-feature-in-commerce-site-builder"></a>Włącz funkcję Wymagaj moderatora dla ocen i recenzji w konstruktorze witryn rozwiązania Commerce

Aby włączyć funkcję **Wymagaj moderatora dla ocen i recenzji** w konstruktorze witryn rozwiązania Commerce, wykonaj następujące kroki.

1. Przejdź do **Strona główna \> Recenzje \> Ustawienia**.
1. Ustaw opcję **Wymagaj moderatora dla ocen i recenzji** na **Wł.**

> [!NOTE]
> Włączenie funkcji **Wymagaj moderatora dla ocen i recenzji** umożliwia zatrzymanie automatycznego publikowania ocen i recenzji, tak aby było wymagane publikowanie ręczne. Jednak usługi Azure Cognitive Services będą nadal redagować przekleństwa w tytułach i zawartości recenzji.

<!--![Require moderator for ratings and reviews setting in Commerce site builder.](media/Ratings-reviews-settings-human-moderation.png)-->

## <a name="publish-ratings-and-reviews"></a>Publikowanie ocen i recenzji

Po włączeniu funkcji **Wymagaj moderatora dla ocen i recenzji** moderator musi ręcznie przejrzeć i opublikować oceny i recenzje, aby były wyświetlane w witrynie e-commerce.

Aby przejrzeć i opublikować oceny i recenzje w konstruktorze witryn w module Commerce, należy wykonać następujące kroki.

1. Przejdź do **Recenzje \> Moderacja**.
1. Jeśli w polu **Stan** wiersza ustawiono wartość **Nieopublikowany**, ocena i przegląd w tym wierszu nie zostały jeszcze opublikowane. Aby wyświetlić tylko nieopublikowane oceny i recenzje, wybierz pozycję **Stan: Wymaga recenzji** w filtrze stanu nad siatką.
1. Wybierz co najmniej jedną ocenę i recenzję o stanie **Nieopublikowane**, a następnie wybierz pozycję **Publikuj** na pasku poleceń. Wybrane oceny i recenzje są dodawane do kolejki publikowania i będą wyświetlane w witrynie e-commerce po ich opublikowaniu.

> [!NOTE]
> - Po opublikowaniu oceny i recenzji wartość stanu zmienia się z **Nieopublikowane** na wartość null (puste pole).
> - Jeśli wybierzesz wiele ocen i recenzji o stanie mieszanym, a następnie wybierzesz opcję **Publikuj**, oceny i recenzje, które nie zostały jeszcze opublikowane, zostaną opublikowane. Oceny i recenzje, które już zostały opublikowane, nie zostaną jednak opublikowane ponownie.

Na poniższej ilustracji pokazano przykład, w którym trzy nieopublikowane oceny i recenzje są wybierane na stronie **Moderacja** w konstruktorze witryn rozwiązania Commerce.

![Trzy nieopublikowane oceny i recenzje wybrane na stronie Moderacja w konstruktorze witryn rozwiązania Commerce.](media/Ratings-reviews-publishing-reviews.png)

<!--![Dynamics 365 Commerce - Ratings and Review configuration 2](media/Ratings-reviews-published-reviews.png)-->
<!--![Status filter](media/Ratings-reviews-published-reviews-status-filter.png)-->

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](opt-in-ratings-reviews.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Konfigurowanie ocen i recenzji](configure-ratings-reviews.md)

[Synchronizacja ocen produktów](sync-product-ratings.md)

[Importowanie i eksportowanie klasyfikacji oraz przeglądów](import-export-reviews.md)

[Konfigurowanie uwierzytelniania usługa-usługa](service-to-service-auth.md)

[Oceny i recenzje — często zadawane pytania](ratings-reviews-faq.md)
