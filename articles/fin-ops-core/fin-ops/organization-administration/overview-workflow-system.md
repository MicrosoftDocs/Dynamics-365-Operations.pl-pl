---
title: Omówienie systemu przepływów pracy
description: W tym temacie opisano system przepływów pracy.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 068f464fe5385486827b2f904114eb663e08b2e8
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2020
ms.locfileid: "3697976"
---
# <a name="workflow-system-overview"></a>Omówienie systemu przepływów pracy

[!include [banner](../includes/banner.md)]

W tym temacie opisano system przepływów pracy.

## <a name="what-is-workflow"></a>Co to jest przepływ pracy?

Termin *przepływ pracy* można definiować na dwa sposoby: jako system i jako proces biznesowy.

### <a name="workflow-is-a-system"></a>Przepływ pracy jest systemem

Przepływ pracy to system uruchomiony na serwerze obiektów aplikacji (AOS). System przepływu pracy zawiera funkcjonalność, której można używać do tworzenia pojedynczych przepływów pracy, czyli procesów biznesowych.

### <a name="workflow-is-a-business-process"></a>Przepływ pracy jest procesem biznesowym

Przepływ pracy reprezentuje proces biznesowy. Definiuje sposób przepływu lub przenoszenia dokumentu przez system, pokazując, kto musi wykonać zadanie, podjąć decyzję lub zatwierdzić dokument. Na przykład poniższa ilustracja pokazuje przepływ pracy dla raportów z wydatków.

![Przepływ pracy z elementami przypisanymi do użytkowników](./media/workflow_user.gif)

Aby lepiej zrozumieć ten przepływ pracy, załóżmy, że Sam przesyła raport z wydatków na 7000 USD. W tym scenariuszu Ivan musi przejrzeć pokwitowania wysłane przez Tomasza. Następnie Wojciech i Magda muszą zatwierdzić raport z wydatków. Teraz załóżmy, że Tomasz przesyła raport z wydatków na kwotę 11 000 USD. W tym scenariuszu Maciej musi przejrzeć pokwitowania, a Wojciech, Magda i Anna muszą zatwierdzić raport z wydatków.

## <a name="benefits-of-using-the-workflow-system"></a> Zalety używania systemu przepływu pracy

Używanie systemu przepływu pracy w organizacji ma kilka zalet:

- **Spójność procesów** — Możesz zdefiniować sposób przetwarzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków. System przepływu pracy zapewnia, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.
- **Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy. Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.
- **Scentralizowana lista prac** — użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy.


## <a name="workflow-content"></a>Zawartość przepływu pracy

+ [Architektura systemu przepływu pracy](workflow-system-architecture.md)
+ [Elementy przepływu pracy](workflow-elements.md)
+ [Akcje w procesach zatwierdzania w przepływie pracy](workflow-actions.md)
+ [Omówienie tworzenia przepływów pracy](create-workflow.md)
+ [Konfigurowanie właściwości przepływu pracy](configure-workflow-properties.md)
+ [Konfigurowanie zadań ręcznych w przepływie pracy](configure-manual-task-workflow.md)
+ [Konfigurowanie zadań wykonywanych automatycznie w przepływie pracy](configure-automated-task-workflow.md)
+ [Konfigurowanie procesów zatwierdzania w przepływie pracy](configure-approval-process-workflow.md)
+ [Konfigurowanie kroków zatwierdzania w przepływie pracy](configure-approval-step-workflow.md)
+ [Konfigurowanie decyzji ręcznych w przepływie pracy](configure-manual-decision-workflow.md)
+ [Konfigurowanie decyzji warunkowych w przepływie pracy](configure-conditional-decision-workflow.md)
+ [Konfigurowanie działań równoległych w przepływie pracy](configure-parallel-activity-workflow.md)
+ [Konfigurowanie odgałęzień równoległych w przepływie pracy](configure-parallel-branch-workflow.md)
+ [Konfigurowanie przepływów pracy dla pozycji w wierszach](configure-line-item-workflow.md)
+ [Przepływ pracy — często zadawane pytania](workflow-FAQ.md)
