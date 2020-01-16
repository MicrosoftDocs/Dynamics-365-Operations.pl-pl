---
title: Włączanie wykrywania sklepu na podstawie lokalizacji
description: W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a542d6987280451910b4ff3bcfb3a109a0e028c6
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697619"
---
# <a name="enable-location-based-store-detection"></a>Włączanie wykrywania sklepu na podstawie lokalizacji

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Wykrywanie magazynu opartego na lokalizacji w module Commerce umożliwia dostarczanie klientom odpowiedniej zawartości oddziału na podstawie ich lokalizacji. Jeśli jest włączona funkcja wykrywania magazynu opartego na lokalizacji, usługa renderowanie Commerce będzie korzystać z informacji o kraju/regionie z adresu IP przeglądarki sieci Web klienta, aby skierować odbiorcę do najlepszej dostępnej konfiguracji geograficznej.

## <a name="privacy-notice"></a>Klauzula prywatności

Po włączeniu funkcji wykrywania magazynu opartego na lokalizacji informacje pochodzące z przeglądarki odbiorcy są wysyłane do usługi lokalizacyjnej firmy Microsoft. Te informacje są następnie używane w celu udostępnienia zawartości odbiorcy, która jest odpowiednia dla jego lokalizacji. Zarówno informacje wysyłane z przeglądarki klienta, jak i informacje na temat lokalizacji zwracane klientowi podlegają zasadom zachowania poufności i plików cookie.

## <a name="turn-on-location-based-store-detection"></a>Włączanie wykrywania sklepu na podstawie lokalizacji

Aby włączyć wykrywanie sklepu opartego na lokalizacji w module Commerce, wykonaj następujące kroki.

1. W narzędziu autorskim przejdź do swojej witryny.
1. W okienku nawigacji po lewej stronie zaznacz **Zarządzanie witryną**.
1. Wubierz **Ustawienia witryny**.
1. Ustaw opcję **Włącz wykrywanie sklepu na podstawie lokalizacji** na **Włącz**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie sklepu internetowego](online-store-overview.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Wdrażanie nowej witryny handlu elektronicznego](deploy-ecommerce-site.md)

[Kojarzenie witryny online z kanałem](associate-site-online-store.md)

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Dodaj obsługę dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)