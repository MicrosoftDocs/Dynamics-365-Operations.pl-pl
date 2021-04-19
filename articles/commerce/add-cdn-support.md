---
title: Dodaj obsługę dla sieci dostarczania zawartości (CDN)
description: W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a56f675b1fb43160625101a067c74e9fcf4f714a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797846"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a>Dodawanie obsługi dla sieci dostarczania zawartości (CDN)

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak dodać sieć dostarczania treści (CDN) do środowiska Microsoft Dynamics 365 Commerce.

Podczas konfigurowania środowiska e-Commerce w Dynamics 365 Commerce można skonfigurować je do pracy z usługą CDN. 

Domenę niestandardową można włączyć podczas procesu zastrzegania dla środowiska e-Commerce. Można również skorzystać z żądania usługi w celu skonfigurowania go po zakończeniu procesu zastrzegania. Proces zastrzegania dla środowiska e-Commerce generuje nazwę hosta skojarzoną ze środowiskiem. Ta nazwa hosta ma następujący format: gdzie \<*e-commerce-tenant-name*\> jest nazwą Twojego środowiska:

&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com

Nazwa hosta lub punkt końcowy, który jest generowany podczas procesu zastrzegania, obsługuje certyfikat SSL (Secure Sockets Layer) tylko dla \*.commerce.dynamics.com. Nie obsługuje on protokołu SSL dla domen niestandardowych. Dlatego należy zamknąć protokół SSL dla domen niestandardowych w sieci CDN i przekazać ruch z sieci CDN do nazwy hosta lub punktu końcowego, który został wygenerowany przez moduł Commerce. 

Ponadto *statystyki* (pliki JavaScript lub kaskadowe arkusze stylów \[CSS\]) z modułu Commerce są doręczane z poziomu punktu końcowego, który jest generowany przez moduł Commerce wygenerowany (\*.commerce.dynamics.com). Statyczne dane mogą być buforowane tylko wtedy, gdy nazwa hosta lub punkt końcowy, który został wygenerowany przez moduł commerce, jest umieszczony za CDN.

## <a name="set-up-ssl"></a>Ustaw format SSL

Po zainicjowaniu obsługi środowiska Commerce w dostarczonej niestandardowej domenie lub po dostarczeniu niestandardowej domeny środowiska za pomocą żądania obsługi, należy współpracować z zespołem wprowadzającym Commerce w celu zaplanowania zmian w systemie DNS.

Jak wcześniej wspomniano, wygenerowana nazwa hosta lub punkt końcowy obsługuje certyfikat SSL tylko dla \*.commerce.dynamics.com. Nie obsługuje on protokołu SSL dla domen niestandardowych.

## <a name="cdn-services"></a>Usługi CDN

Ze środowiskiem Commerce można używać dowolnej usługi CDN. Oto dwa przykłady:

- **Microsoft Azure Front Door Service** — rozwiązanie usługi CDN sieci Azure. Aby uzyskać więcej informacji o usługach Azure Front Door Service, zapoznaj sięz dokumentacją usługi [Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).
- **Akceleratordynamiczny witryny Akamai** — Aby uzyskać więcej informacji, należy zapoznać się z informacjami o [dynamicznym akceleratorze witryny](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).

## <a name="cdn-setup"></a>Ustawienia CDN

Proces konfiguracji sieci CDN składa się z następujących ogólnych kroków:

1. Dodaj hosta frontonu
1. Skonfiguruj pulę zaplecza.
1. Konfigurowanie reguł wyboru trasy.

### <a name="add-a-front-end-host"></a>Dodaj hosta frontonu.

Można użyć dowolnej usługi CDN, ale z przykładu w tym temacie jest używana usługa Azure Front Door Service. 

Aby uzyskać informacje na temat konfigurowania usługi Azure Front Door Service, odwiedź witrynę [Szybki start: Tworzenie drzwi frontowych dla globalnej aplikacji sieci Web o dużej dostępności](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a>Skonfiguruj pulę zaplecza w usłudze Azure Front Door Service

Aby skonfigurować pulę zaplecza w usłudze Azure Front Door Service, wykonaj nastepujące kroki.

1. Dodaj **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** do puli wewnętrznej bazy danych jako niestandardowego hosta, który ma nagłówek hosta wewnętrznej bazy danych, który jest taki sam jak **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.
1. W obszarze **równoważenie obciążenia** pozostaw wartości domyślne.
1. Wyłącz testy kondycji dla puli wewnętrznej bazy danych.

Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie zaplecza** w usłudze Azure Front Door Service z podaną nazwą hosta zaplecza.

![Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool.png)

Na poniższej ilustracji przedstawiono okno dialogowe **Dodawanie puli zaplecza** w usłudze Azure Front Door Service z domyślnymi wartościami równoważenia obciążenia.

![Kontynuacja Okno dialogowe Dodawanie puli wewnętrznej bazy danych](./media/CDN_BackendPool_2.png)

> [!NOTE]
> Pamiętaj, aby wyłączyć **Sondy kondycji** podczas konfigurowania własnej usługi Azure Front Door dla handlu.


### <a name="set-up-rules-in-azure-front-door-service"></a>Konfigurowanie reguł w usłudze Azure Front Door Service

Aby skonfigurować regułę routingu w usłudze Azure Front Door Service, wykonaj następujące kroki.

1. Dodawanie reguły routingu.
1. W polu **Nazwa** wpisz **domyślna**.
1. W polu **zaakceptowane protokoły** wybierz opcję **HTTP i HTTPS**.
1. W polu **hosty frontonu** wprowadź **dynamics-ecom-tenant-name.azurefd.net**.
1. W obszarze **wzory do dopasowania**, w górnym polu wprowadź wartość **/\***.
1. W obszarze **Szczegóły marszruty** ustaw opcję **Typ marszruty** na **Prześlij dalej**.
1. W polu **Pula wewnętrzna** wybierz opcję **ecom-backend**.
1. W grupie pól **protokół przesyłania dalej** wybierz opcję **dopasowywanie żądań**. 
1. Ustawienie opcji **ponownego zapisywania adresów URL** na **wyłączone**.
1. Ustawienie opcji **Buforowanie** na **wyłączone**.


> [!WARNING]
> Jeśli domena, której będziesz korzystać, jest już aktywna i na żywo, Utwórz bilet pomocy technicznej na kafelku **Pomocy technicznej** w usłudze [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/), aby uzyskać pomoc w następnych etapach. Aby uzyskać więcej informacji, przejrzyj temat [Uzyskaj pomoc techniczną dla aplikacji Finance and Operations lub usług Lifecycle Services (usługi LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

Jeśli Twoja domena jest nowa i nie jest wcześniej istniejącą domeną aktywną, możesz dodać swoją domenę niestandardową do konfiguracji usługi Azure Front Door. Umożliwi to kierowanie ruchu internetowego do Twojej witryny za pośrednictwem wystąpienia usługi Azure Front Door. Aby dodać domenę niestandardową (na przykład `www.fabrikam.com`), należy skonfigurować nazwę kanoniczną (CNAME) dla domeny.

Na poniższej ilustracji przedstawiono okno dialogowe **Konfiguracja CNAME** w usłudze Azure Front Door Service.

![Okno dialogowe konfiguracji CNAME](./media/CNAME_Configuration.png)

Za pomocą usługi Azure Front Door Service można zarządzać certyfikatem lub można skorzystać z własnego certyfikatu dla domeny niestandardowej.

Na poniższej ilustracji przedstawiono okno dialogowe **Niestandardowa domena HTTPS** w usłudze Azure Front Door Service.

![Okno dialogowe domeny niestandardowej HTTPS](./media/Custom_Domain_HTTPS.png)

Aby uzyskać szczegółowe instrukcje dotyczące dodawania domeny niestandardowej do Azure Front Door, zamieszczono w temacie [Dodawanie domeny niestandardowej do swoich Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).

Sieć CDN powinna być teraz poprawnie skonfigurowana, aby można było jej używać z witryną Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Opcje implementacji sieci dostarczania zawartości](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
