---
title: 'Przepływ pracy: często zadawane pytania'
description: W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/01/2019
ms.locfileid: "773227"
---
# <a name="workflow-system"></a>System przepływu pracy

[!include [banner](../includes/banner.md)]

W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Powiadomienia

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Dlaczego otrzymuję wiele powiadomień, gdy element pracy został odrzucony?
Gdy element pracy został odrzucony, zostaje zakończony jako odrzucony. Inny element pracy zostanie utworzony i przypisany do inicjatora. Oznacza to, że inicjator otrzyma powiadomienie o odrzuconym elemencie pracy, a osobne powiadomienie zostanie wysłane do użytkownika przypisanego nowego elementu pracy „Zażądano zmiany”. 

Każde powiadomienie dotyczy innego elementu pracy, ale podobieństwa mogą powodować zamieszanie. Szukamy sposobów, aby to poprawić w przyszłej wersji.
