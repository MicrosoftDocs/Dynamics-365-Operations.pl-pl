---
title: Konwertowanie klientów asynchronicznych na synchronicznych
description: W tym artykule wyjaśniono sposób konwertowania odbiorców asynchronicznych na odbiorców synchronicznych w aplikacji Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b442bfc0685706359771e4d9e2729565d3652a60
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278200"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Konwertowanie klientów asynchronicznych na synchronicznych

[!include [banner](includes/banner.md)]

W tym artykule wyjaśniono sposób konwertowania odbiorców asynchronicznych na odbiorców synchronicznych w aplikacji Microsoft Dynamics 365 Commerce.

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
