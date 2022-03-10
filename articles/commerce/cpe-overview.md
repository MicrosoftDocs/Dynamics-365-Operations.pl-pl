---
title: Omówienie środowiska oceny rozwiązania Dynamics 365 Commerce
description: Ten temat zawiera omówienie środowiska oceny usługi Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 07/16/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 35cd06070ff73af1c97706bb1cdb67045715d458
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982646"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Omówienie środowiska oceny rozwiązania Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Ten temat zawiera omówienie środowiska oceny usługi Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Środowiska testowe w handlu są zazwyczaj niedostępne i są przyznawane partnerom i odbiorcom na żądanie. Aby uzyskać więcej informacji, skontaktuj się z partnerem firmy Microsoft.

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
