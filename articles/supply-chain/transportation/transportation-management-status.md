---
title: Stany zarządzania transportem
description: W tym temacie opisano sposób tworzenia stanu transportu i mapowania tego stanu na stan przewoźnika.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3f7d471771ec2b4703d878fbf395cd90902b6669
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "4435686"
---
# <a name="transportation-management-statuses"></a>Stany zarządzania transportem

[!include [banner](../includes/banner.md)]

Ustaw kody główne stanów transportu do zinterpretowania kodów przekazanych przez przewoźników. Pozwala to na integrację z przewoźnikami w celu nadania statusu. Stan transportu podawany dla kodu stanu głównego transportu może ułatwić śledzenie stanu ładunku, wysyłki lub kontenera. Określony stan transportu dla ładunku, wysyłki lub kontenera można aktualizować tylko za pośrednictwem integracji danych, a nie ręcznie za pośrednictwem interfejsu użytkownika.

## <a name="create-a-transportation-status"></a>Tworzenie stanu transportu

Aby utworzyć stan transportu, wykonaj następujące kroki:

1. Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Główne stany transportu**.
1. Wybierz **Nowy** do utworzenia danych głównych stanu transportu.
1. W polu **Główny stan transportu** wprowadź unikatowy kod dla stanu transportu.
1. W polu **Typ transportu** wybierz *Przewoźnik* lub *Centrum* jako typ transportu.
1. Umożliwia wprowadzenie nazwy i stanu transportu.
1. Zamknij stronę.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>Mapuj stan transportu na stan przewoźnika

Aby zamapować stan transportu na stan przewoźnika, wykonaj następujące kroki:

1. Wybierz kolejno opcje **Zarządzanie transportem \> Ustawienia \> Przewoźnicy \> Stan transportu przewoźnika**.
1. Wybierz **Nowy**, aby zmapować kod od przewoźnika do kodu głównego stanu transportu.
1. Wybierz unikatowy identyfikator dla przewoźnika i usługi przewozowej.
1. Wybierz kod stanu transportu, który ma być mapowany do kodu wybranego przewoźnika wysyłki.
1. Wprowadź kod zewnętrzny używany przez przewoźnika.
1. Zamknij stronę.
