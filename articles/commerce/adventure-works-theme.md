---
title: Omówienie motywu Adventure Works
description: Ten temat zawiera omówienie motywu Adventure Works i opisuje, jak zastosować go do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7557a36a948de5ae877d74bbbdea78821099b82
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479516"
---
# <a name="adventure-works-theme-overview"></a>Omówienie motywu Adventure Works

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ten temat zawiera omówienie motywu Adventure Works i opisuje, jak zastosować go do stron witryny w Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce ma motyw e-commerce o nazwie Adventure Works. Motyw Adventure Works prezentuje produkty sportowe i rekreacyjne i jest zoptymalizowany pod kątem bogatej i ulepszonej opowieści. Zapewnia nowoczesny wygląd, nowe układy i efekty animacji, aby stworzyć wciągające, wciągające wrażenia z zakupów online dla klientów e-commerce.

Motyw Adventure Works udostępnia następujące nowe przepływy pracy:

- Moduł video player umożliwia teraz obsługę nagłówka, akapitu i łączy.
- Akcja dodaj do koszyka wywołuje mini koszyk zamiast dostarczania powiadomienia.
- Moduł szybkiego podglądu to okienko, które wsuwa się zarówno w rzutniach pulpitu, jak i urządzeń przenośnych.
- Pusty koszyk może teraz korzystać z promocji.

Motyw Adventure Works zawiera następujące moduły opowiadania historii w bibliotece modułów Commerce:

- Moduł listy kafelków
- Interaktywny moduł funkcyjny
- Moduł Subskrybuj
- Moduł aktywnego obrazu
- Moduł listy obrazów

Kompozycja Adventure Works w pełni odpowiada tej aplikacji, a jej działanie jest optymalne dla widoków pulpitu, urządzeń przenośnych i tabletów.

> [!IMPORTANT]
> Motyw Adventure Works i nowe moduły są dostępne od wersji Dynamics 365 Commerce 10.0.20.

Na poniższej ilustracji przedstawiono przykład strony głównej, która używa motywu Adventure Works.

![Przykład strony głównej, na których jest używany motyw Adventure Works](./media/aw_b2c.PNG)

Na poniższej ilustracji przedstawiono przykład strony listy, która używa motywu Adventure Works.

![Przykład strony listy, na których jest używany motyw Adventure Works](./media/Aw_list.PNG)

Na poniższej ilustracji przedstawiono przykład strony szczegółów produktu (PDP), która używa motywu Adventure Works.

![Przykład strony szczegółów produktu (PDP), która korzysta z motywu Adventure Works](./media/aw_pdp.PNG)

## <a name="use-the-adventure-works-theme-for-b2b-sites"></a>Użyj motywu Adventure Works dla witryn B2B

Motyw Adventure Works jest również motywem referencyjnym dla witryn typu business-to-business (B2B). Wszystkie moduły i przepływy pracy B2B są prezentowane w motywie Adventure Works. Aby uzyskać informacje dotyczące konfigurowania strony B2B, zobacz [Konfiguracja strony B2B](./b2b/set-up-b2b-site.md).

Na poniższej ilustracji przedstawiono przykład strony B2B, która używa motywu Adventure Works.

![Przykład strony B2B, na których jest używany motyw Adventure Works](./media/aw_b2b.PNG)

## <a name="theme-extensions"></a>Rozszerzenia motywu

Kompozycja Adventure Works zawiera kilka rozszerzeń motywu, takich jak **Zobacz rozszerzenia** i **Definicja modułu**. Motyw Adventure Works może służyć jako motyw referencyjny do tworzenia podobnych rozszerzeń. Na przykład strona listy w motywie Adventure Works jest zaimplementowana jako rozszerzenie widoku, które ma poziome uściślanie. (Z kolei w motywie Fabrikam użyto rafinera w lewym okienku).

Podobnie inne moduły zawierają rozszerzenia definicji modułów. Na przykład [moduł ikony koszyka](cart-icon-module.md) zawiera dwa dodatkowe miejsca na **pusty koszyk** i **treści promocyjne**, które są implementowane przy użyciu rozszerzeń definicji modułu. Ponadto do modułu nagłówka dodano nową właściwość **Logo mobilne**, aby obsługiwać logo w widokach przenośnych. Ta właściwość jest zaimplementowana jako rozszerzenie definicji modułu nagłówka.

Aby uzyskać więcej informacji o rozszerzeniach motywów, zobacz temat [Rozszerzenia motywów](e-commerce-extensibility/theme-module-extensions.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](starter-kit-overview.md)

[Moduł listy kafelków](tile-list-module.md)

[Interaktywny moduł funkcyjny](interactive-feature-module.md)

[Moduł aktywnego obrazu](active-image-module.md)

[Moduł Subskrybuj](subscribe-module.md)

[Moduł listy obrazów](image-list-module.md)

[Rozszerzenia motywu](e-commerce-extensibility/theme-module-extensions.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Konfigurowanie witryny wykorzystywanej na potrzeby handlu elektronicznego B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]