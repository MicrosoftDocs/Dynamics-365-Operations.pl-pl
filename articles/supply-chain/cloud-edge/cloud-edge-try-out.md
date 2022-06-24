---
title: Wypróbowanie jednostki skalowania w dystrybuowanej topologii hybrydowej
description: Ten artykuł zawiera informacje o tym, jak wypróbować jednostki w chmurze i skali brzegowej na potrzeby obciążeń związanych z zarządzaniem produkcją i magazynem.
author: perlynne
ms.date: 05/02/2022
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-03-03
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 5645955109e7a942e617b3b90a27065c2a8fe4a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893592"
---
# <a name="try-out-scale-units-in-a-distributed-hybrid-topology"></a>Wypróbowanie jednostki skalowania w dystrybuowanej topologii hybrydowej

[!include [banner](../includes/banner.md)]

Proces testowania rozproszonej topologii hybrydowej jest prosty. Na pierwszym etapie należy sprawdzić poprawność dostosowań, aby upewnić się, że działają w rozproszonej topologii. Masz do wyboru dwie opcje.

## <a name="option-1-evaluate-customizations-in-development-environments"></a>Opcja 1: Oceń dostosowania w środowiskach programistycznych

Zanim zaczniesz wdrażać swoje piaskownice, zalecamy zbadanie jednostek skalowania w konfiguracji programistycznej, takiej jak środowisko typu one-box (znane również jako środowisko warstwy 1), aby można było weryfikować procesy, dostosowania, i rozwiązania. Na tym etapie dane i dostosowania zostaną zastosowane w środowiskach typu „one-box”. Można uruchomić na jednym środowisku, które może pełnić rolę centrum przedsiębiorstwa i jednostki skalowania. Można również mieć dwa środowiska programowe, z których jedno pełni rolę centrum, a drugie pełni rolę jednostki skalowania. Te ustawienia zapewniają najlepszą identyfikację i rozwiązywanie problemów. Do ukończenia tego etapu można również użyć [Podgląd kompilacji](../../fin-ops-core/fin-ops/get-started/one-version.md#how-can-i-get-early-access-to-non-released-platform-updates).

Aby zainstalować i konserwować środowiska, należy użyć [narzędzi do wdrażania jednostek skali dla jednoelementowych środowisk programistycznych](https://github.com/microsoft/SCMScaleUnitDevTools). Te narzędzia umożliwiają konfigurowanie centrów i jednostek skalowania w jednym lub dwóch oddzielnych środowiskach typu one-box. Narzędzia są dostarczane zarówno w wersji binarnej, jak i w kodzie źródłowym na GitHub. Przejmij stronę typu wiki projektu, która zawiera [Przewodnik krok po kroku](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide), w którym opisano sposób korzystania z tych narzędzi. Jeśli wdrażasz jednostki skalowania [krawędzi na niestandardowym sprzęcie przy użyciu lokalnych danych biznesowych (LBD),](cloud-edge-edge-scale-units-lbd.md) musisz wykonać inny proces.

## <a name="option-2-acquire-add-ins-and-deploy-in-your-sandbox-environments"></a>Opcja 2: Zdobądź dodatki i wdrażaj je w środowiskach piaskownicy

Aby wypróbować rozproszoną topologię hybrydową, musisz mieć dwa środowiska piaskownicy (warstwa 2), z których jedno zawiera dane (centrum przedsiębiorstwa), a drugie jest przeznaczone dla jednostki skalowania i zawiera „puste dane”.

Należy uzyskać dodatki dla co najmniej jednej jednostki wagi chmury lub krawędzi. Odpowiednie miejsca na projekty i środowiska zostaną następnie przyznane w [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), aby środowiska jednostek skalowania mogły być wdrażane za pomocą [portalu Scale Unit Manager](https://aka.ms/SCMSUM).

Skontaktuj się z pomocą techniczną firmy Microsoft, aby zażądać, aby środowiska piaskownicy było włączone.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
