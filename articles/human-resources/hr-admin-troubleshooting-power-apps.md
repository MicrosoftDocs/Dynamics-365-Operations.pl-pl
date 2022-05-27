---
title: Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps
description: W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e50348515f14b543c392c5f9c8637cec5fa037f2
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689614"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Wystawienie**

- Administrator dzierżawy/środowiska nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.
- Użytkownik nie ma licencji, która daje prawo do tworzenia środowisk.

**Rozwiązanie**

Upewnij się, że administrator dzierżawy przypisał prawidłową licencję Power Apps P2 do użytkownika tworzącego środowisko. Następujące plany usług Microsoft Dynamics zapewniają uprawnienia do tworzenia środowisk:

| Ogólna jednostka magazynowa produktu (SKU)       | Power Apps planu usług P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps dla usługi Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | Power Apps dla usługi Dynamics 365 |

Należy zwrócić uwagę, że różne wersje SKU pakietu Microsoft Office także zapewniają to prawo, wraz z autonomicznymi jednostkami SKU Power Apps Plan 2 Istotne jest to, że jedna z tych jednostek SKU musi występować.

1. Przejdź do [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Human Resouces](/dynamics365/unified-operations/talent/provisioning-talent).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
