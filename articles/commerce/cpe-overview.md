---
title: Omówienie środowiska wersji zapoznawczej Dynamics 365 Commerce
description: Ten temat zawiera omówienie środowiska wersji zapoznawczej usługi Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
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
ms.openlocfilehash: 1ff96aeb5963df9ddee56783a089dad129bbb71c
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024690"
---
# <a name="dynamics-365-commerce-preview-environment-overview"></a>Omówienie środowiska wersji zapoznawczej Dynamics 365 Commerce


[!include [banner](includes/banner.md)]

Ten temat zawiera omówienie środowiska wersji zapoznawczej usługi Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Środowisko wersji zapoznawczej usługi Commerce to opcjonalne kompleksowe środowisko wersji zapoznawczej usługi Dynamics 365 Commerce, które umożliwia potencjalnym klientom wypróbowanie produktu Commerce przed jego wydaniem jako ogólnie dostępnego.

Oprócz niektórych drobnych ograniczeń, które nie wpływają na funkcje lub funkcjonalność, środowisko wersji zapoznawczej usługi Commerce zapewnia kompletne środowisko handlowe i może być używane przez klientów oraz partnerów wdrożeniowych do oceny produktu, dostarczania opinii i analizy dopasowania/luk.

## <a name="limitations-of-the-commerce-preview-environment"></a>Ograniczenia środowiska wersji zapoznawczej usługi Commerce

Chociaż środowisko wersji zapoznawczej usługi Commerce zawiera pełny zestaw funkcji i funkcjonalności platformy handlowej, istnieją pewne drobne ograniczenia:

- Chociaż środowisko wersji zapoznawczej usługi Commerce nie ma żadnych ograniczeń geograficznych, składniki środowiska, takie jak aplikacje Retail Cloud Scale Unit (RCSU) i e-Commerce, mogą być aprowizowane tylko w Stanach Zjednoczonych.
- Użycie środowiska wersji zapoznawczej usługi Commerce jest ograniczone do 30 od daty aprowizacji aplikacji e-Commerce.
- Środowisko wersji zapoznawczej usługi Commerce można pomyślnie wdrożyć i zainicjować tylko w środowisku, które używa topologii pokazów, gdzie wszystkie składniki środowiska są wdrażane w jednej maszynie wirtualnej. Głównym ograniczeniem tej topologii maszyny wirtualnej OneBox jest liczba współbieżnych użytkowników, które środowisko wersji zapoznawczej może obsługiwać.
- Środowisko wersji zapoznawczej usługi Commerce może być oceniane tylko do momentu rozpoczęcia ogólnej dostępności produktu Commerce. Nowe środowiska pokazów będą dostępne po rozpoczęciu ogólnej dostępności.

## <a name="get-started"></a>Wprowadzenie

Aby aprowizować środowisko wersji zapoznawczej usługi Commerce, zobacz [Aprowizowanie środowiska wersji zapoznawczej usługi Commerce](provisioning-guide.md).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Inicjuj środowisko wersji zapoznawczej Dynamics 365 Commerce](provisioning-guide.md)

[Konfiguruj środowisko wersji zapoznawczej usługi Dynamics 365 Commerce](cpe-post-provisioning.md)

[Konfiguruj funkcje opcjonalne środowiska wersji zapoznawczej usługi Dynamics 365 Commerce](cpe-optional-features.md)

[Środowisko wersji zapoznawczej Dynamics 365 Commerce— często zadawane pytania](cpe-faq.md)
