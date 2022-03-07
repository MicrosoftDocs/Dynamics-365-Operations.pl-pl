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
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: fb0d98729046330037f96ab7e13a1bf897e35a1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233350"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]