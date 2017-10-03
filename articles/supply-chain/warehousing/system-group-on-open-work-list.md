---
title: "Grupowanie systemowe na liście otwartych prac"
description: "W tym temacie opisano sposób filtrowania listy otwartych prac na urządzeniu przenośnym."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: dbf0e49b1156c54cd37bbbe57ca564cdbc45fb2d
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017

---

# <a name="system-grouping-on-an-open-work-list"></a>Grupowanie systemowe na liście otwartych prac

[!include[banner](../includes/banner.md)]

Za pomocą pola grup systemowych można wyfiltrować listę otwartych prac bez konieczności edytowania elementu menu w urządzeniu komórkowym.
Funkcja grupowania systemowego filtruje listę prac według jednego pola nagłówka pracy. Nie można używać grupowania systemowego do filtrowania według pól na poziomie wierszy.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Konfigurowanie grupowania systemowego listy otwartych prac
Wykonaj poniższe kroki, aby skonfigurować grupowanie systemowego listy otwartych prac.

-   Na urządzeniu komórkowym z menu wybierz opcje **Tryb: Pośrednie** i **Kod działania: Wyświetl listę otwartych prac**. Zostaną udostępnione opcje wymienione poniżej. Te opcje są wymagane przy grupowaniu systemowym listy otwartych prac. 

| Opcja        | opis   | 
| ------------- | ------------- |
| Zezwalaj na grupowanie systemowe   | Umożliwia grupowanie systemowe dla wybranej pozycji listy prac.| 
| Pole grup systemowych   | Opcja dostępna tylko wtedy, gdy w polu **Zezwalaj na pracę systemową** zaznaczono wartość **Tak**. Wybierz pole określające, jak praca pobrania będzie grupowana dla pracowników. Na przykład, jeśli wybierzesz pole **ShipmentId**, pracownik będzie skanować identyfikator wysyłki w celu pogrupowania pracy pobrania. Wszystkie prace dla wysyłki są następnie przypisywane do pracownika. To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system. Za pomocą pola **Etykieta grup systemowych** można poinformować pracownika, co ma być skanowane. |
| Etykieta grup systemowych   | Opcja dostępna tylko wtedy, gdy w polu **Zezwalaj na pracę systemową** zaznaczono wartość **Tak**. Wprowadź informacje dla pracownika o tym, co należy zeskanować podczas grupowania pracy pobrania. Na przykład jeśli używasz pola **ShipmentId** do grupowania pracy pobrania według wysyłki, możesz w polu wpisać Identyfikator wysyłki. To pole wymaga utworzenia elementu menu, który będzie używał istniejącej pracy pogrupowanej przez system. Musisz także wybrać pole, według którego będzie przeprowadzane grupowanie w polu **Grupowanie systemowe**.|
