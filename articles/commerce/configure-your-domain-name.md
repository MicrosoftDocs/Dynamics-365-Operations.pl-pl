---
title: Konfigurowanie nazwy domeny
description: W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f73c034563fb1cc6b05091b4c47e2a788d1a8b6
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945543"
---
# <a name="configure-your-domain-name"></a>Konfigurowanie nazwy domeny

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym. 

## <a name="add-domains-during-e-commerce-initialization"></a>Dodawanie domen podczas inicjowania usługi e-Commerce

Aby skojarzyć domeny z środowiskiem handlu elektronicznego, należy zainicjować e-Commerce w sposób opisany [w temacie Wdrażanie nowej witryny e-Commerce](deploy-ecommerce-site.md). Podczas inicjowania użytkownik jest monitowany o podanie informacji, które będą używane w celu zainicjowania obsługi środowiska e-Commerce. W polu **Obsługiwane nazwy hostów** dodaj wszystkie domeny, które mają być używane w tym środowisku. Wiele domen należy oddzielić średnikiem. W ten sposób domeny są konfigurowane we wszystkich wymaganych składnikach e-Commerce i są gotowe do użycia podczas przełączania ruchu z sieci dostarczania zawartości (CDN, Content Delivery Network) lub serwera sieci Web, a następnie na frontony e-Commerce.

## <a name="add-domains-after-e-commerce-initialization"></a>Dodawanie domen po inicjowaniu usługi e-Commerce

Aby skojarzyć nowe domeny ze środowiskiem e-Commerce po zainicjowaniu usługi e-Commerce, należy przesłać żądanie obsługi.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)
