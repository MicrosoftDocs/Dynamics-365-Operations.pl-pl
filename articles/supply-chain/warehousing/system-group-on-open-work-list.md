---
title: Grupowanie systemowe na liście otwartych prac
description: W tym temacie opisano sposób filtrowania listy otwartych prac na urządzeniu przenośnym.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: abb971f2ad81e4e0a4e9cfa6417bb3ddc0cb69cd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239165"
---
# <a name="system-grouping-on-an-open-work-list"></a>Grupowanie systemowe na liście otwartych prac

[!include [banner](../includes/banner.md)]

Za pomocą pola grup systemowych można wyfiltrować listę otwartych prac bez konieczności edytowania elementu menu w urządzeniu komórkowym.
Funkcja grupowania systemowego filtruje listę prac według jednego pola nagłówka pracy. Nie można używać grupowania systemowego do filtrowania według pól na poziomie wierszy.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Konfigurowanie grupowania systemowego listy otwartych prac
Wykonaj poniższe kroki, aby skonfigurować grupowanie systemowego listy otwartych prac.

-   Na urządzeniu komórkowym z menu wybierz opcje **Tryb: Pośrednie** i **Kod działania: Wyświetl listę otwartych prac**. Zostaną udostępnione opcje wymienione poniżej. Te opcje są wymagane przy grupowaniu systemowym listy otwartych prac. 

|        Opcja         |                                                                                                                                                                                                                                                                         opis                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Zezwalaj na grupowanie systemowe |                                                                                                                                                                                                                                                 Umożliwia grupowanie systemowe dla wybranej pozycji listy prac.                                                                                                                                                                                                                                                  |
| Pole grup systemowych | Opcja dostępna tylko wtedy, gdy w polu <strong>Zezwalaj na pracę systemową</strong> zaznaczono wartość <strong>Tak</strong>. Wybierz pole określające, jak praca pobrania będzie grupowana dla pracowników. Na przykład, jeśli wybierzesz pole <strong>ShipmentId</strong>, pracownik będzie skanować identyfikator wysyłki w celu pogrupowania pracy pobrania. Wszystkie prace dla wysyłki są następnie przypisywane do pracownika. To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system. Za pomocą pola <strong>Etykieta grup systemowych</strong> można poinformować pracownika, co ma być skanowane. |
| Etykieta grup systemowych |                       Opcja dostępna tylko wtedy, gdy w polu <strong>Zezwalaj na pracę systemową</strong> zaznaczono wartość <strong>Tak</strong>. Wprowadź informacje dla pracownika o tym, co należy zeskanować podczas grupowania pracy pobrania. Na przykład jeśli używasz pola <strong>ShipmentId</strong> do grupowania pracy pobrania według wysyłki, możesz w polu wpisać Identyfikator wysyłki. To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system. Musisz także wybrać pole, według którego będzie przeprowadzane grupowanie w polu <strong>Grupowanie systemowe</strong>.                       |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]