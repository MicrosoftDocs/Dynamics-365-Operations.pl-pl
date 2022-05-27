---
title: Konwertowanie klientów asynchronicznych na synchronicznych
description: W tym temacie wyjaśniono sposób konwertowania odbiorców asynchronicznych na odbiorców synchronicznych w aplikacji Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: fc1690ff6068317c748bda0d767a10f306f3debe
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691451"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Konwertowanie klientów asynchronicznych na synchronicznych

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono sposób konwertowania odbiorców asynchronicznych na odbiorców synchronicznych w aplikacji Microsoft Dynamics 365 Commerce.

Aby konwertować odbiorców asynchronicznych na odbiorców synchronicznych, wykonaj następujące kroki.

1. W centrali Commerce Headquarters uruchom **zadanie P**, aby wysłać asynchronicznych odbiorców do centrali Commerce Headquarters.
1. Uruchom zadanie **Synchronizuj odbiorców i partnerów biznesowych z zadania w trybie asynchronicznym**, aby utworzyć identyfikatory kont odbiorców. (To zadanie było znane wcześniej jako **Synchronizuj odbiorców i partnerów biznesowych z trybu asynchronicznego**).
1. Uruchom zadanie **1010**, aby zsynchronizować identyfikatory nowych kont odbiorcy z kanałami.

Jeśli zamówienie odwołuje się do asynchronicznego odbiorcy lub adresu, który nie został jeszcze zsynchronizowany z centralą Commerce, odbiorca lub adres zostanie zsynchronizowany w ramach zadania wsadowego **Synchronizuj zamówienia**. Jeśli transakcja kasowa i gotówkowa odwołuje się do odbiorcy lub adresu asynchronicznego, odbiorca lub adres są synchronizowani przed zaksięgowaniem na koniec dnia (EOD).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzanie klientami w sklepach](customer-mgmt-stores.md)

[Asynchroniczny tryb tworzenia klientów](async-customer-mode.md)

[Atrybuty odbiorcy](dev-itpro/customer-attributes.md)

[Wykluczanie danych w trybie offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
