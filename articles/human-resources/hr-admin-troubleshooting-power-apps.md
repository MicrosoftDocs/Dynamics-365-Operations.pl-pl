---
title: Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps
description: W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft Power Apps.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 664c644c9b34e3489b4134040e165d26202dbd38
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113853"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Nie można utworzyć środowiska w centrum administracyjnym usługi Power Apps

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
2. Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Human Resouces](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).
