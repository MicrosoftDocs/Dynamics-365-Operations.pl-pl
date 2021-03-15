---
title: Wymagania wstępne konfiguracji kanałów
description: W tym temacie przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanałów w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0705efac4659f96ebca1c67f6f0ab8d23c99d81e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997707"
---
# <a name="channel-setup-prerequisites"></a>Wymagania wstępne konfiguracji kanałów


[!include [banner](includes/banner.md)]

W tym temacie przedstawiono omówienie wymagań wstępnych dotyczących konfiguracji kanału w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

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