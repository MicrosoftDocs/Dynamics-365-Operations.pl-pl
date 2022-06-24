---
title: Wymagania wstępne dotyczące konfiguracji kanału
description: W tym artykule przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 84b176ed07de8dd0828ba02cdbefd7a3795d984b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884940"
---
# <a name="channel-setup-prerequisites"></a>Wymagania wstępne dotyczące konfiguracji kanału

[!include [banner](includes/banner.md)]

W tym artykule przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.

Aby można było utworzyć kanał Dynamics 365 Commerce, należy wykonać kilka wymaganych wstępnie zadań. Poniższe listy wstępnie wymaganych zadań uporządkowane według typów kanałów.

> [!NOTE]
> Nadal trwa tworzenie dokumentacji, a łącza zostaną zaktualizowane po opublikowaniu nowej zawartości.

## <a name="initialization"></a>Inicjalizacja

- [Inicjowanie danych początkowych](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Globalne wymagania wstępne dla wszystkich typów kanałów

- [Definiowanie i konfigurowanie struktury firmy](channels-legal-entities.md) 
- [Konfigurowanie hierarchii organizacyjnej](channels-org-hierarchies.md)
- [Ustawianie magazynu](channels-setup-warehouse.md)
- [Konfiguracja podatku warunkowego](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [Konfigurowanie powiadomień pocztą e-mail](email-notification-profiles.md)
- [Konfigurowanie sekwencji numerów](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [Konfigurowanie domyślnego odbiorcy i książki adresowej](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Wymagania wstępne kanału Retail

- [Kody informacji i grupy kodów informacji](info-codes-retail.md)
- [Konfigurowanie profilu funkcji sieci sprzedaży](retail-functionality-profile.md)
- [Konfigurowanie książki adresowej pracowników](new-address-book.md)
- [Konfigurowanie układu ekranu](pos-screen-layouts.md)
- [Konfigurowanie stacji sprzętowej](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a>Wymagania wstępne kanału biura obsługi

- Parametry biura obsługi
- [Zamówienie biura obsługi i metody płatności zwrotnych](work-with-payments.md)
- [Metody dostawy i opłat w biurze obsługi](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a>Wymagania wstępne dotyczące kanału online

- [Tworzenie profilu funkcji online](online-functionality-profile.md)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie kanałów](channels-overview.md)

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Konfigurowanie hierarchii organizacyjnych](channels-org-hierarchies.md)

[Tworzenie firm](channels-legal-entities.md)

[Konfigurowanie kanału sprzedaży](channel-setup-retail.md)
    
[Konfigurowanie kanału internetowego](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
