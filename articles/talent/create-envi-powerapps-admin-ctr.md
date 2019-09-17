---
title: Nie można utworzyć środowiska w centrum administracyjnym usługi PowerApps
description: W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft PowerApps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 96119ca869cbbb15ed8d8d5d0fe3b0f94b5f36cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742849"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a>Nie można utworzyć środowiska w centrum administracyjnym usługi PowerApps

[!include [banner](includes/banner.md)]

**Wydaj**

- Administrator dzierżawy/środowiska nie może utworzyć środowiska w Centrum administracyjnym Microsoft PowerApps.
- Licencja, która daje użytkownikom prawo do wykonywania kroku tworzenia środowiska nie została przypisana bezpośrednio do użytkownika, który wykonuje ten krok.

**Rozwiązanie**

Upewnij się, że administrator dzierżawy ma przypisaną prawidłową licencję usługi PowerApps P2 bezpośrednio do użytkownika, który wykona krok tworzenia środowiska. Poniżej przedstawiono plany usługowe Microsoft Dynamics, które zapewniają te prawa.

| Ogólna jednostka magazynowa produktu (SKU)       | Plan usług PowerApps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | PowerApps dla Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | PowerApps dla Dynamics 365 |

Należy zwrócić uwagę, że różne wersje SKU pakietu Microsoft Office także zapewniają to prawo, wraz z autonomicznymi jednostkami SKU PowerApps Plan 2 Istotne jest to, że jedna z tych jednostek SKU musi występować.

1. Przejdź do [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).
