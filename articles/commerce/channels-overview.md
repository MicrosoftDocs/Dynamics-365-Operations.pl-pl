---
title: Omówienie kanałów
description: W tym temacie omówiono kanały w Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
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
ms.openlocfilehash: 7f5d527dd14d24c06aef874de0088bb07c49849b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800550"
---
# <a name="channels-overview"></a>Omówienie kanałów


[!include [banner](includes/banner.md)]

W tym temacie omówiono kanały w Microsoft Dynamics 365 Commerce. Znajdują się tu informacje o zadaniach, które należy wykonać przed i po skonfigurowaniu każdego kanału.

## <a name="types-of-channels"></a>Typy kanałów

Dynamics 365 Commerce obsługuje trzy różne typy kanałów: sieć sprzedaży, biuro obsługi i kanały online.

### <a name="retail-channels"></a>Kanały sprzedaży detalicznej

Kanały sieć sprzedaży reprezentują standardowe sklepy. Każdy sklep ma własne kasy punktów sprzedaży (POS), konta przychodów i wydatków oraz personel. 

### <a name="call-center-channels"></a>Kanały biura obsługi

Kanały biura obsługi reprezentują kolejność biur obsługi i zarządzanie odbiorcami.

### <a name="online-channels"></a>Kanały online

Kanały online reprezentują sklepy e-commerce w trybie online. Po utworzeniu kanału online witryna musi zostać utworzona przy użyciu narzędzia Kreatora witryn Microsoft Dynamics 365 Commerce lub innego rozwiązania e-commerce jednostki zewnętrznej.

## <a name="channel-setup-basics"></a>Podstawy ustawień kanału

Konfiguracja kanału jest wykonywana w narzędziu Commerce. Każdy kanał może mieć własne metody płatności, grupy cenowe, hierarchie produktów, asortymenty i zestawy produktów. Po utworzeniu kanału, można przypisać produkty, które mają trafić do sklepu i je sprzedawać. Każdy typ kanału ma unikatowy zbiór funkcji, które mogą wymagać skonfigurowania. Na przykład kanał sprzedaży detalicznej potrzebuje przypisanych pracowników, kas i odbiorców. Po utworzeniu nowego kanału należy go przypisać do hierarchii organizacyjnej.

## <a name="channel-setup-prerequisites"></a>Wymagania wstępne konfiguracji kanałów

Aby można było skonfigurować kanał, należy wykonać pewne wymagane zadania wstępne na podstawie typu kanału. Aby uzyskać więcej informacji, zajrzyj do [Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md).

## <a name="set-up-a-channel"></a>Konfigurowanie kanału

Po wykonaniu wymaganych zadań wstepnych, aby uzyskać więcej instrukcji konfiguracyjnych, należy skorzystać z następujących łączy:

- [Konfigurowanie kanału sprzedaży](channel-setup-retail.md)
- [Konfigurowanie kanału biura obsługi](channel-setup-callcenter.md)
- [Konfigurowanie kanału internetowego](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a>Dodatkowe zasoby

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Konfigurowanie kanału sprzedaży](channel-setup-retail.md)
    
[Konfigurowanie kanału internetowego](channel-setup-online.md)

[Konfigurowanie kanału biura obsługi](channel-setup-callcenter.md)

[Konfigurowanie hierarchii organizacyjnych](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]