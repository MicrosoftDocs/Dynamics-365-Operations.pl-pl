---
title: "Nie można utworzyć środowiska w centrum administracyjnym usługi PowerApps"
description: "W tym temacie wyjaśniono, co zrobić, jeśli administrator nie może utworzyć środowiska w Centrum administracyjnym Microsoft PowerApps."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 6f9b7ceef6895b295e6ae5a50d8ac7970497efe5
ms.contentlocale: pl-pl
ms.lasthandoff: 12/04/2018

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
| Plan Microsoft Dynamics 365 — Enterprise Edition | PowerApps dla Dynamics 365 |

Należy zwrócić uwagę, że różne wersje SKU pakietu Microsoft Office także zapewniają to prawo, wraz z autonomicznymi jednostkami SKU PowerApps Plan 2 Istotne jest to, że jedna z tych jednostek SKU musi występować.

1. Przejdź do [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Utwórz środowiska, postępując zgodnie z instrukcjami w [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

