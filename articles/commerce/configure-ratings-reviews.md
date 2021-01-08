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
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: edd2082b5d2cafcb955f8e3c7762bcba523ac479
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414843"
---
# <a name="configure-ratings-and-reviews"></a>Konfigurowanie ocen i recenzji

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania witryny e-Commerce w celu wyświetlania ocen odbiorców i recenzji w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Oceny i Recenzje w witrynach e-Commerce umożliwiają klientom zapoznanie się z produktami przed podjęciem decyzji o zakupie, kierując ich uwagę na te produkty. W przypadku witryn e-Commerce, oceny i recenzje są również mechanizmami zbierania opinii klientów dotyczących produktów. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Skonfiguruj witrynę, aby wyświetlała oceny i recenzje

Wartości konfiguracji ocen i recenzji, takie jak identyfikator dzierżawcy, długość tekstu recenzji i długość tytułu recenzji, są konfigurowane na poziomie witryny. 

Aby skonfigurować witrynę do wyświetlania ocen i recenzji, wykonaj następujące kroki. 

1. Przejdź do **Widok główny \> Strony**.
1. Wybierz nazwę swojej witryny. 
1. Przejdź do **Ustawień witryny \> Rozszerzenia**. 
1. W polu **Maksymalna długość tekstu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tekst recenzji (na przykład **1000**). 
1. W polu **Maksymalna długość tytułu recenzji**, wpisz maksymalną liczbę znaków, jaką może zawierać tytuł recenzji (na przykład **55**). 
1. Wybierz **Zapisz i opublikuj**. 

Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.

![Konfigurowanie witryny, aby wyświetlała oceny i recenzje](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Łączenie oceny produktu z sekcją recenzji w PDP

Ocena produktu jest wyświetlana pod tytułem produktu u góry PDP. Ocenę produktu można skonfigurować tak, aby była połączona z sekcją **Recenzje** tej samej strony PDP. 

Aby połączyć ocenę produktu z sekcją **Recenzje** PDP, należy wykonać następujące kroki.

1. Otwórz szablon PDP. 
1. Przejdź do **Ustawienia modułu kontenera pola zakupu**.
1. W **Polu zakupu** wybierz opcję **Oceny produktów**, a następnie zaznacz pole wyboru **Połącz kliknięcie z modułem pełnych ocen**.

Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.

![Łączenie oceny produktu z sekcją recenzji w PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Konfiguruj łącze do strony prywatność i zasady

Aby skonfigurować link do strony prywatności i zasad, wykonaj następujące kroki.

1. Przejdź do **Widok główny \> Strony**.
1. Wybierz nazwę swojej witryny. 
1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. Na karcie **Marszruty** w obszarze **RNR prywatność i zasady** wybierz opcję **Dodaj łącze**. Jeśli łącze zostało już wprowadzone i ma zostać zamienione, należy zaznaczyć łącze. 
1. W oknie dialogowym **Dodawj łącze** wybierz łącze do strony prywatność i zasady, a następnie kliknij przycisk **OK**. 
1. Wybierz **Zapisz i opublikuj**. 

Na poniższej ilustracji przedstawiono, jak wygląda konfiguracja w Dynamics 365 Commerce.

![Konfiguracja łącza do strony prywatność i zasady](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>Konfiguruj moduły ocen i recenzji na stronach szczegółów produktu

Aby uzyskać informacje na temat konfigurowania modułów oceny i przeglądu, patrz [moduły oceny i przeglądów](ratings-reviews-modules.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie ocen i recenzji](ratings-reviews-overview.md)

[Zgoda na korzystanie z ocen i recenzji](opt-in-ratings-reviews.md)

[Zarządzanie ocenami i recenzjami](manage-reviews.md)

[Konfiguruj moduły ocen i recenzji na stronach szczegółów produktu](ratings-reviews-modules.md)

[Synchronizacja ocen produktów w rozwiązaniu Dynamics 365 Retail](sync-product-ratings.md)
