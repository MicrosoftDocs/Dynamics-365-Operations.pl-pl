---
title: Przepływy pracy mające zastosowanie do umów z modułu Zarządzanie rabatami
description: W tym temacie opisano sposób skonfigurowania przepływu pracy umowy dotyczącej zarządzania rabatami, aby zatwierdzić i aktywować transakcje.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f18c3bd95901303379c460d026bc944cee809b7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576671"
---
# <a name="rebate-management-deal-workflows"></a>Przepływy pracy mające zastosowanie do umów z modułu Zarządzanie rabatami

[!include [banner](../includes/banner.md)]

Aby zatwierdzić transakcje rabatowe, w zarządzaniu rabatami jest używana ta sama platforma przepływu pracy co inne aplikacje Finance and Operations. Dwa procesy zadań są skojarzone z każdym przepływem pracy:

- Jeden element przepływu pracy zatwierdza umowę.
- Jeden element przepływu pracy aktywuje umowę, dzięki czemu użytkownik lub proces przepływu pracy może zatwierdzić transakcje.

Aby można było użyć umowy rabatowej, należy ją aktywnego w module **Zarządzanie rabatami**. Aby aktywować umowę, należy najpierw utworzyć i skonfigurować *Przepływ pracy umowy w zarządzaniu rabatami*.

Użytkownicy nie mogą ręcznie zatwierdzać transakcji. Przepływ pracy musi być zawsze używany.

## <a name="create-and-manage-rebate-management-deal-workflows"></a>Twórz przepływy pracy związane z zarządzaniem rabatami i zarządzaj nimi

Aby pracować z przepływami pracy umów w zarządzaniu rabatami, przejdź do **Zarządzanie rabatami \> Ustawienia \> Przepływy pracy zarządzania rabatami**. W tym miejscu można w razie potrzeby wyświetlać, tworzyć i aktualizować przepływy pracy. W danym momencie może być aktywny tylko jeden przepływ pracy tego typu. Aby uzyskać więcej informacji na temat przepływów pracy, sposobu pracy ze stroną **Przepływy pracy zarządzania rabatami** oraz sposobu tworzenia przepływów pracy, zobacz [Omówienie systemu przepływu pracy](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) i powiązane tematy.

## <a name="use-a-workflow-to-activate-a-deal"></a>Aktywowanie umowy przy użyciu przepływu pracy

Aby aktywować umowę za pomocą przepływu pracy, otwórz umowę (na przykład na stronie **Wszystkie umowy zarządzania rabatami**). W okienku akcji wybierz **Przepływ pracy \> Prześlij**. Po przetworzeniu i zatwierdzeniu nowej umowy za pomocą przepływu pracy będzie ona aktywna i gotowa do użycia.

Po aktywowaniu umowy nie można zmienić większości jej konfiguracji. Jeśli trzeba zmienić aktywną umowę, najpierw trzeba ją dezaktywować, a następnie utworzyć nową umowę. Jeśli nowa umowa przypomina starą umowę, można ją utworzyć, kopiując starą umowę.

Po aktywowaniu umowy można zmieniać następujące ustawienia:

- Uzgodnienie według
- Gwarancja skumulowana
- Profil księgowania
- Profil księgowania dla gwarancji
- Notatki dotyczące dokumentu
- Waluta
- Data rozpoczęcia
- Data zakończenia

Ponadto wiersze rabatów mogą zostać usunięte.
