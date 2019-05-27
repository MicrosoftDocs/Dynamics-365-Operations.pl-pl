---
title: 'Przepływ pracy: często zadawane pytania'
description: W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509298"
---
# <a name="workflow-system"></a>System przepływu pracy

[!include [banner](../includes/banner.md)]

W tym temacie znajdują się odpowiedzi na często zadawane pytania dotyczące systemu przepływu pracy w Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Powiadomienia

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Dlaczego otrzymuję wiele powiadomień, gdy element pracy został odrzucony?
Gdy element pracy został odrzucony, zostaje zakończony jako odrzucony. Inny element pracy zostanie utworzony i przypisany do inicjatora. Oznacza to, że inicjator otrzyma powiadomienie o odrzuconym elemencie pracy, a osobne powiadomienie zostanie wysłane do użytkownika przypisanego nowego elementu pracy „Zażądano zmiany”. 

Każde powiadomienie dotyczy innego elementu pracy, ale podobieństwa mogą powodować zamieszanie. Szukamy sposobów, aby to poprawić w przyszłej wersji.

### <a name="why-are-my-workflow-exports-failing"></a>Dlaczego moje próby eksportu przepływu pracy kończą się niepowodzeniem?
Obecnie istnieje ograniczenie funkcji eksportu przepływu pracy, które zapobiega przekraczaniu 48 znaków w nazwach przepływów pracy. Użycie nazwy, która jest dłuższa niż 48 znaków może spowodować wyświetlenie komunikatu o błędzie „Serwer nie może uwierzytelnić żądania” lub uniemożliwienie wyeksportowania pliku bez typu pliku. Poniższy wpis w blogu zawiera dodatkowe szczegóły [Rozwiązywanie problemów z eksportowaniem przepływów pracy](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).
