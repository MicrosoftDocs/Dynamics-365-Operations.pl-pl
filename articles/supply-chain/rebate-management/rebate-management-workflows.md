---
title: Przepływy pracy mające zastosowanie do umów z modułu Zarządzanie rabatami
description: W tym temacie opisano sposób skonfigurowania przepływu pracy umowy dotyczącej zarządzania rabatami, aby zatwierdzić i aktywować transakcje.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 37b8022633e61c4d98d6f5d129bcf494a9ed92e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831729"
---
# <a name="rebate-management-deal-workflows"></a>Przepływy pracy mające zastosowanie do umów z modułu Zarządzanie rabatami

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Aby zatwierdzić transakcje rabatowe, w zarządzaniu rabatami jest używana ta sama platforma przepływu pracy co inne aplikacje Finance and Operations. Dwa procesy zadań są skojarzone z każdym przepływem pracy:

- Jeden element przepływu pracy aktywuje umowę, dzięki czemu użytkownik lub proces przepływu pracy może zatwierdzić transakcje.
- Jeden element przepływu pracy zatwierdza umowę.

Aby można było użyć umowy rabatowej, należy ją aktywnego w module **Zarządzanie rabatami**. Aby aktywować umowę, należy najpierw utworzyć i skonfigurować *Przepływ pracy umowy w zarządzaniu rabatami*.

Po uaktywnieniu przepływu pracy w celu zarządzania rabatami użytkownicy nie mogą ręcznie zatwierdzać transakcji. Przepływ pracy musi być zawsze używany.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Twórz przepływy pracy związane z zarządzaniem rabatami i zarządzaj nimi

Aby pracować z przepływami pracy umów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia \> Przepływy pracy zarządzania rabatami**. W tym miejscu można w razie potrzeby wyświetlać, tworzyć i aktualizować przepływy pracy. W danym momencie może być aktywny tylko jeden przepływ pracy tego typu. Aby uzyskać więcej informacji na temat przepływów pracy, sposobu pracy ze stroną **Przepływy pracy zarządzania rabatami** oraz sposobu tworzenia przepływów pracy, zobacz [Omówienie systemu przepływu pracy](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) i powiązane tematy.

## <a name="use-a-workflow-to-activate-a-deal"></a>Aktywowanie umowy przy użyciu przepływu pracy

Aby aktywować umowę za pomocą przepływu pracy, otwórz umowę (na przykład na stronie **Wszystkie umowy zarządzania rabatami**). W okienku akcji wybierz **Przepływ pracy \> Prześlij**. Po przetworzeniu i zatwierdzeniu nowej umowy za pomocą przepływu pracy będzie ona aktywna i gotowa do użycia.

Po aktywowaniu umowy nie można zmienić jej konfiguracji. Jeśli trzeba zmienić aktywną umowę, ją dezaktywować, a następnie utworzyć nową umowę. Jeśli nowa umowa przypomina starą umowę, można ją utworzyć, kopiując starą umowę.
