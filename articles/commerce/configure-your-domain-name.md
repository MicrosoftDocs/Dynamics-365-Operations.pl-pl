---
title: Konfigurowanie nazwy domeny
description: W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym.
author: psimolin
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3df563b62b40970509340802a09bb36dda14777
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001007"
---
# <a name="configure-your-domain-name"></a>Konfigurowanie nazwy domeny


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób konfigurowania nazwy domeny dla witryny Microsoft Dynamics 365 w handlu elektronicznym. 

## <a name="add-domains-during-e-commerce-initialization"></a>Dodawanie domen podczas inicjowania usługi e-Commerce

Aby skojarzyć domeny z środowiskiem handlu elektronicznego Dynamics 365 Commerce, należy zainicjować e-Commerce w sposób opisany w temacie [Wdrażanie nowej witryny e-Commerce](deploy-ecommerce-site.md). Podczas inicjowania użytkownik jest monitowany o podanie informacji, które będą używane w celu zainicjowania obsługi środowiska e-Commerce. W polu **Obsługiwane nazwy hostów** dodaj wszystkie domeny, które mają być używane w tym środowisku. Wiele domen należy oddzielić średnikiem. W ten sposób domeny są konfigurowane we wszystkich wymaganych składnikach e-Commerce i są gotowe do użycia podczas przełączania ruchu z sieci dostarczania zawartości (CDN, Content Delivery Network) lub serwera sieci Web, a następnie na frontony e-Commerce.

## <a name="add-domains-after-e-commerce-initialization"></a>Dodawanie domen po inicjowaniu usługi e-Commerce

Aby skojarzyć nowe domeny ze środowiskiem e-Commerce po zainicjowaniu usługi e-Commerce, należy przesłać żądanie obsługi.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Włączanie wykrywania sklepu na podstawie lokalizacji](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]