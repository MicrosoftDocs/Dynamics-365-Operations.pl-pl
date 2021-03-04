---
title: Omówienie środowiska oceny usługi Dynamics 365 Commerce
description: Ten temat zawiera omówienie środowiska oceny usługi Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
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
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 25c0574e8d4502bcb846fba0ddf913d81eded87b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414835"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Omówienie środowiska oceny usługi Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Ten temat zawiera omówienie środowiska oceny usługi Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Środowiska testowe w handlu są zazwyczaj niedostępne i są przyznawane partnerom i odbiorcom na żądanie. Aby uzyskać więcej informacji, skontaktuj się z partnerem firmy Microsoft.

## <a name="overview"></a>Omówienie

Środowisko oceny usługi Commerce to opcjonalne kompleksowe środowisko wersji zapoznawczej usługi Dynamics 365 Commerce, które umożliwia partnerom i potencjalnym klientom wypróbowanie produktu Commerce.

Częściowo wstępnie skonfigurowane środowiska oceny w celu zmniejszenia wymaganych kroków po wykonaniu wstępnej obsługi administracyjnej.

Oprócz niektórych drobnych ograniczeń, które nie wpływają na funkcje lub funkcjonalność, środowisko oceny usługi Commerce zapewnia kompletne środowisko handlowe i może być używane przez klientów oraz partnerów wdrożeniowych do oceny produktu, dostarczania opinii i analizy dopasowania/luk.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>Ograniczenia środowiska oceny usługi Commerce

Chociaż środowisko oceny usługi Commerce zawiera pełny zestaw funkcji i funkcjonalności platformy handlowej, istnieją pewne drobne ograniczenia:

- Chociaż środowisko oceny usługi Commerce nie ma żadnych ograniczeń geograficznych, składniki środowiska, takie jak aplikacje Retail Cloud Scale Unit (RCSU) i handlu elektronicznego, powinny być aprowizowane tylko w Stanach Zjednoczonych.
- Użycie środowiska oceny usługi Commerce jest ograniczone do 30 od daty aprowizacji handlu elektronicznego.
- Środowisko oceny usługi Commerce można pomyślnie wdrożyć i zainicjować tylko w środowisku, które używa topologii pokazów, gdzie wszystkie składniki środowiska są wdrażane w jednej maszynie wirtualnej w chmurze. Głównym ograniczeniem tej topologii maszyny wirtualnej jest liczba współbieżnych użytkowników, które środowisko może obsługiwać.

## <a name="get-started"></a>Rozpocznij

Aby aprowizować środowisko oceny usługi Commerce, zobacz [Aprowizowanie środowiska oceny usługi Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Ustanowienie środowiska oceny Dynamics 365 Commerce](provisioning-guide.md)

[Konfigurowanie środowiska oceny usługi Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfigurowanie BOPIS w środowisku oceny Dynamics 365 Commerce](cpe-bopis.md)

[Konfigurowanie opcjonalnych funkcji środowiska oceny Dynamics 365 Commerce](cpe-optional-features.md)

[Środowiska oceny usługi Dynamics 365 Commerce — często zadawane pytania](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]