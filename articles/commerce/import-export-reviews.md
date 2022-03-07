---
title: Importowanie i eksportowanie klasyfikacji oraz przeglądów
description: W tym temacie opisano sposób importowania i eksportowania ocen produktów oraz przeglądanych w tej sekcji Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 3ae85f21f7a78d56621aed60527207badcee9c75
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968528"
---
# <a name="import-and-export-ratings-and-reviews"></a>Importowanie i eksportowanie klasyfikacji oraz przeglądów

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób importowania i eksportowania ocen produktów oraz przeglądanych w tej sekcji Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce oferuje [oceny i recenzje](ratings-reviews-overview.md) jako rozwiązanie wielokanałowe. Po przełączeniu na rozwiązanie Dynamics 365 Commerce dotyczące oceny i oceny użytkownik może chcieć przenieść istniejące oceny i przeglądać dane na platformę Commerce. Na podstawie wymagań firmy można również eksportować oceny i przeglądać dane z usług Commerce. Łącznik Power Automate umożliwia importowanie ocen i recenzji do aplikacji Commerce oraz eksportowanie ich z aplikacji Commerce.

> [!NOTE]
> Aby uzyskać informacje o tym, jak rozpocząć pracę z przepływami logicznymi w usłudze Power Automate, zobacz [Tworzenie przepływu w chmurze w usłudze Power Automate](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Wymagania wstępne

Aby było można importować i eksportować oceny i przeglądy, należy spełnić następujące wymagania wstępne:

- W witrynie e-commerce na platformie Commerce muszą być włączone oceny i rozwiązanie przeglądania. Aby uzyskać więcej informacji, zobacz [Temat zgody na używanie ocen i recenzji](opt-in-ratings-reviews.md).
- Program Dynamics 365 Ratings and Reviews Power App Connector musi być skonfigurowany tak, aby umożliwiał akcje „przesyłanie recenzji” lub „eksportowanie recenzji” w Power Automate. Aby uzyskać więcej informacji, zobacz [Dynamics 365 Commerce - Oceny i recenzje (Podgląd)](/connectors/dynamics365ratingsre/).
- Uwierzytelnianie usługa-usługa (S2S) musi być skonfigurowane, aby w bezpieczny sposób wywołać klasyfikacje i przeglądać interfejs programowania aplikacji (API) spoza Commerce. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Skonfiguruj uwierzytelnianie między usługami](service-to-service-auth.md).

## <a name="import-ratings-and-reviews"></a>Importuj oceny i recenzje

Aby zaimportować dane ocen i recenzji z istniejącego systemu do usługi Commerce, należy dodać łącznik Dynamics 365 Oceny i przegląd Power Automate do istniejącego lub nowego przepływu Power Automate. Aby uzyskać więcej informacji, zobacz [Dynamics 365 Commerce - Oceny i recenzje (Podgląd)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Przed wykonaniem tej procedury należy [skonfigurować identyfikatory S2S](service-to-service-auth.md).

Aby zaimportować oceny i przeglądy do handlu za pomocą łącznika Oceny i oceny systemu Dynamics 365 Power Automate, wykonaj następujące kroki.

1. Wybierz **akcję Prześlij przegląd użytkownika**.
1. Ustanowić połączenie przy użyciu informacji o aplikacji Azure Active Directory (Azure AD) utworzonej podczas konfigurowania uwierzytelniania S2S. Aby uzyskać więcej informacji, należy zapoznać się z tematem [Skonfiguruj uwierzytelnianie między usługami](service-to-service-auth.md).
1. Akcja **Prześlij przegląd użytkownika** ma na raz jedną recenzję. W związku z tym powtórz akcję. Użyj źródłowych recenzji jako listy, aby przesłać przeglądy zbiorcze.
    
## <a name="export-ratings-and-reviews"></a>Eksportuj oceny i recenzje

Aby wyeksportować dane ocen i recenzji z usługi Commerce, należy dodać łącznik Dynamics 365 Oceny i przegląd Power Automate do istniejącego lub nowego przepływu Power Automate. Aby uzyskać więcej informacji, zobacz [Dynamics 365 Commerce - Oceny i recenzje (Podgląd)](/connectors/dynamics365ratingsre/).

Aby wyeksportować oceny i recenzje z usługi Commerce przy użyciu łącznika Oceny i oceny systemu Dynamics 365 Power Automate, wykonaj następujące kroki.

1. Wybierz akcję **Eksportuj wszystkie przeglądy**.
1. Dokończ akcję. 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](opt-in-ratings-reviews.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Konfigurowanie ocen i recenzji](configure-ratings-reviews.md)

[Synchronizacja ocen produktów](sync-product-ratings.md)

[Włączanie ręcznego publikowania ocen i recenzji przez moderatora](manual-publish-rating-reviews.md)

[Konfigurowanie uwierzytelniania usługa-usługa](service-to-service-auth.md)

[Oceny i recenzje — często zadawane pytania](ratings-reviews-faq.md)
