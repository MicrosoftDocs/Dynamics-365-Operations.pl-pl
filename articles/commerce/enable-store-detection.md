---
title: Włączanie wykrywania sklepu na podstawie lokalizacji
description: W tym temacie opisano sposób włączania wykrywania magazynu opartego na lokalizacji dla witryny Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3f7e9a3acde508f405ce85f125db552c3ae3656b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000733"
---
# <a name="enable-location-based-store-detection"></a>Włączanie wykrywania sklepu na podstawie lokalizacji


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

[Konfigurowanie nazwy domeny](configure-your-domain-name.md)

[Wdrażanie nowej dzierżawy handlu elektronicznego](deploy-ecommerce-site.md)

[Tworzenie witryny handlu elektronicznego](create-ecommerce-site.md)

[Kojarzenie witryny Dynamics 365 Commerce z kanałem online](associate-site-online-store.md)

[Zarządzanie plikami robots.txt](manage-robots-txt-files.md)

[Zbiorowe przekazanie przekierowań adresów URL](upload-bulk-redirects.md)

[Konfigurowanie dzierżawy B2C w usłudze Commerce](set-up-B2C-tenant.md)

[Konfigurowanie stron niestandardowych do logowań użytkowników](custom-pages-user-logins.md)

[Konfigurowanie wielu dzierżawców B2C w środowisku Commerce](configure-multi-B2C-tenants.md)

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]