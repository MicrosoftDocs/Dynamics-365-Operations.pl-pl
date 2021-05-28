---
title: Opcje implementacji sieci dostarczania zawartości
description: W tym temacie przeglądane są różne opcje implementacji sieci dostarczania zawartości (CDN), które mogą być używane w środowiskach Microsoft Dynamics 365 Commerce. Te opcje obejmują natywne wystąpieni Azure Front Door dostarczone w ramach handlu oraz wystąpienia Azure Front Door należące do odbiorcy.
author: BrianShook
ms.date: 03/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f6e8fb2baf85be0eaecfffcc7ec6cbb457c3bb04
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021897"
---
# <a name="content-delivery-network-implementation-options"></a>Opcje implementacji sieci dostarczania zawartości

[!include [banner](includes/banner.md)]

W tym temacie przeglądane są różne opcje implementacji sieci dostarczania zawartości (CDN), które mogą być używane w środowiskach Microsoft Dynamics 365 Commerce. Te opcje obejmują natywne wystąpieni Azure Front Door dostarczone w ramach handlu oraz wystąpienia Azure Front Door należące do odbiorcy.

Odbiorcy handlowi mają kilka opcji, jeśli są pod uwagę, która usługa CDN ma być używać w swoim środowisku Commerce. Usługa Commerce jest zwolniona z podstawową obsługą Azure Front Door, która obejmuje podstawowe wymagania dotyczące obsługi i niestandardowych domen. W przypadku firm, które chcą mieć większą kontrolę i bardziej szczegółowe funkcje zabezpieczeń, takie jak zapora aplikacji sieci Web (WAF), najlepszą opcją może być użycie należącego do klienta wystąpienia usługi Azure Front Door lub zewnętrznej usługi CDN.

W środowiskach Commerce można używać następujących trzech opcji implementacji usługi CDN:

- Wystąpienie usługi Azure Front Door udostępniane przez Commerce
- Wystąpienie usługi Azure Front Door należące do klienta (w celu zwiększenia kontroli i dodatkowych funkcji zabezpieczeń)
- Zewnętrzna usługa CDN

Wszystkie trzy opcje implementacji usługi CDN dostarczają tylko dynamicznej zawartości HTML z domen niestandardowych. Commerce automatycznie obsługuje wszystkie skrypty JavaScript, kaskadowe arkusze stylów (CSS), obrazy, wideo i inną zawartość statyczną za pośrednictwem sieci CDN zarządzanych przez firmę Microsoft. Wybór tej opcji określa dostępne możliwości operacyjne, możliwości kontroli oraz dodatkowe dostępne możliwości zabezpieczeń.

Na poniższej ilustracji przedstawiono przegląd architektury Commerce.

![Omówienie architektury Commerce](media/Commerce_CDN-Option_ComparisonModels.png)

Aby uzyskać więcej informacji na temat konfigurowania wystąpienia usługi Azure Front Door dla witryny handlowej, zobacz [Dodawanie obsługi CDN](add-cdn-support.md).

## <a name="use-the-commerce-provided-azure-front-door-instance"></a>Użyj wystąpienia usługi Azure Front Door udostępnionego w handlu

W poniższej tabeli wymieniono zalety i wady używania udostępnionego w handlu wystąpienia usługi Azure Front Door do zarządzania punktami końcowymi zawartości.

| Plusy | Minusy |
|------|------|
| <ul><li>To wystąpienie jest uwzględnione w kosztach w Commerce.</li><li>Ponieważ instancja jest zarządzana przez zespół ds. Handlu, wymagana jest mniejsza konserwacja i dostępne są wspólne kroki konfiguracji.</li><li>Infrastruktura hostowana w systemie Azure jest skalowalna, bezpieczna i pewna.</li><li>Certyfikat Secure Sockets Layer (SSL) wymaga jednorazowej konfiguracji i jest automatycznie odnawiany.</li><li>Wystąpienie jest monitorowane pod kątem błędów i anomalii przez zespół Commerce.</li></ul> | <ul><li>WAF nie jest obsługiwana.</li><li>Nie ma konkretnych dostosowań ani korekt ustawień.</li><li>To wystąpienie zależy od zespołu usługi Commerce, jeśli są aktualizacje lub zmiany.</li><li>Oddzielne wystąpienie usługi Azure Front Door jest wymagane w przypadku domen wierzchołkowych, a integracja domen wierzchołkowych z usługą Azure DNS wymaga dodatkowej pracy.</li><li>Brak telemetrii odpowiedzi na sekundę (RPS) lub stawka błędu jest dostarczana odbiorcy.</li></ul> |

Na poniższej ilustracji przedstawiono architekturę wystąpienia Azure Front Door dostarczonego z portalu Commerce.

![Użyj wystąpienia usługi Azure Front Door udostępnionego w Commerce](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a>Użyj wystąpienia usługi Azure Front Door należącego do klienta

W poniższej tabeli wymieniono zalety i wady korzystania z należącego do klienta wystąpienia usługi Azure Front Door do zarządzania punktami końcowymi zawartości.

| Plusy | Minusy |
|------|------|
| <ul><li>Konfiguracja jest bezpieczna i łatwa do zarządzania.</li><li>Infrastruktura hostowana w systemie Azure jest skalowalna, bezpieczna i pewna.</li><li>To wystąpienie umożliwia kontrole reguł integracji WAF i szczegółowej kontroli reguł dla bardziej szczegółowych zabezpieczeń, które zostały dostrojone specjalnie dla witryny.</li><li>To wystąpienie umożliwia precyzyjne sterowanie certyfikatami SSL (zarządzanymi przez klienta i Azure Front Door) oraz łączenie domen.</li><li>To wystąpienie oferuje rozwiązanie domenowe, jeśli jest ono sparowane bezpośrednio z serwerem DNS systemu Azure.</li><li>Podano telemetrię i alerty.</li><li>Certyfikat SSL wymaga jednorazowej konfiguracji i jest automatycznie odnawiany.</li></ul> | <ul><li>To wystąpienie jest zarządzane samodzielnie.</li><li>Wymagane jest wstępne zdobycie wiedzy.</li></ul> |

Na poniższej ilustracji przedstawiono infrastrukturę Commerce, która zawiera należące do klienta wystąpienie usługi Azure Front Door.

![Infrastruktura Commerce, która zawiera należące do klienta wystąpienie usługi Azure Front Door](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a>Korzystanie z zewnętrznej usługi CDN

W poniższej tabeli wymieniono plusz i minusy używania zewnętrznej usługi CDN do zarządzania punktami końcowymi zawartości.

| Plusy | Minusy |
|------|------|
| <ul><li>Ta opcja jest przydatna, gdy istniejąca domena jest już hostowana w zewnętrznym pliku CDN.</li><li>Konkurencja CDNs (na przykład Akamai) może mieć więcej możliwości WAF.</li></ul> | <ul><li>Wymagana jest osobna umowa i dodatkowa wycena.</li><li>Protokół SSL może powiązać się z dodatkowymi kosztami.</li><li>Ponieważ usługa jest osobna od struktury chmury systemu Azure, musi być zarządzana dodatkowa infrastruktura.</li><li>Usługa może wymagać dłuższych inwestycji w punkty końcowe i ustawienia zabezpieczeń.</li><li>Ta usługa jest zarządzana samodzielnie.</li><li>Ta usługa jest monitorowana samodzielnie.</li></ul> |

Na poniższej ilustracji przedstawiono infrastrukturę Commerce, która obejmuje zewnętrzną usługę CDN.

![Infrastruktura Commerce, która zawiera zewnętrzną usługę CDN](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Dodawanie obsługi dla sieci dostarczania zawartości (CDN)](add-cdn-support.md)
