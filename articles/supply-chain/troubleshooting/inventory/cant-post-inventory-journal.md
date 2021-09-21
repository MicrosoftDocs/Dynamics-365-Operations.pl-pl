---
title: Nigdy nie ukończono przepływu pracy arkusza magazynowego i nie można go przetworzyć
description: Po przesłaniu przepływu pracy zatwierdzania arkusza proces przetwarzania przepływu pracy przestaje odpowiadać i nie można edytować ani przetwarzać arkuszy.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9430068f9c2d92c894817db04143297de6c6aa6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477270"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>Nigdy nie ukończono przepływu pracy arkusza magazynowego i nie można go przetworzyć

## <a name="symptoms"></a>Objawy

Po przesłaniu przepływu pracy zatwierdzania arkusza proces przetwarzania przepływu pracy przestaje odpowiadać i nie można edytować ani przetwarzać arkuszy.

## <a name="resolution"></a>Rozwiązanie

Istnieje kilka przyczyn, dla których przetwarzanie przepływu może nie zostać ukończone. Sprawdź następujące problemy:

- Przejdź do obszaru **Zarządzanie zapasami &gt; Ustawienia &gt; Przepływy pracy zarządzania zapasami** i przejrzyj konfigurację danego przepływu pracy. Aby uzyskać więcej informacji, zobacz temat [Przepływy pracy zatwierdzania arkusza magazynowego](/dynamics365/supply-chain/inventory/inventory-journal-workflow.md).
- Przepływ pracy może napotkać wyjątek lub błąd. Przejrzyj historię elementów roboczych, których dotyczy ten przepływ pracy, aby sprawdzić, czy zawiera on błąd aplikacji, który kończy przepływ pracy.
- Arkusz magazynowy można aktualizować lub edytować tylko wtedy, gdy jest zatwierdzony. Jeśli odwołanie jest aktywne, można spróbować odwołać arkusz. Wykonanie zadania wsadowego przepływu pracy może być zawieszone z wielu przyczyn. Niektóre z tych przyczyn mogą być spowodowane przez problem ze strukturą przepływu pracy.
