---
title: "Omówienie przepływu pracy"
description: "W tym temacie opisano system przepływów pracy dostępny w programie Microsoft Dynamics 365 for Finance and Operations."
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6622f0e5ed6c38bb8131d13aa02061968862678b
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="workflow-overview"></a>Omówienie przepływu pracy

[!include[banner](../includes/banner.md)]


W tym temacie opisano system przepływów pracy dostępny w programie Microsoft Dynamics 365 for Finance and Operations.

<a name="what-is-workflow"></a>Co to jest przepływ pracy?
-----------------

Termin *przepływ pracy* można definiować na dwa sposoby: jako system i jako proces biznesowy.
### <a name="workflow-is-a-system"></a>Przepływ pracy jest systemem

Przepływ pracy to system instalowany razem z programem Finance and Operations i uruchamiany na serwerze obiektów aplikacji (AOS). System przepływu pracy zawiera funkcjonalność, której można używać do tworzenia pojedynczych przepływów pracy, czyli procesów biznesowych.

### <a name="workflow-is-a-business-process"></a>Przepływ pracy jest procesem biznesowym

Przepływ pracy reprezentuje proces biznesowy. Definiuje sposób przepływu lub przenoszenia dokumentu przez system, pokazując, kto musi wykonać zadanie, podjąć decyzję lub zatwierdzić dokument. Na przykład poniższa ilustracja pokazuje przepływ pracy dla raportów z wydatków. 

![Przepływ pracy z elementami przypisanymi do użytkowników](./media/workflow_user.gif) 

Aby lepiej zrozumieć ten przepływ pracy, załóżmy, że Sam przesyła raport z wydatków na 7000 USD. W tym scenariuszu Ivan musi przejrzeć pokwitowania wysłane przez Tomasza. Następnie Wojciech i Magda muszą zatwierdzić raport z wydatków. Teraz załóżmy, że Tomasz przesyła raport z wydatków na kwotę 11 000 USD. W tym scenariuszu Maciej musi przejrzeć pokwitowania, a Wojciech, Magda i Anna muszą zatwierdzić raport z wydatków.

## <a name="benefits-of-using-the-workflow-system"></a> Zalety używania systemu przepływu pracy

Używanie systemu przepływu pracy w organizacji ma kilka zalet:
-   **Spójność procesów** — Możesz zdefiniować sposób przetwarzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków. System przepływu pracy zapewnia, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.
-   **Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy. Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.
-   **Scentralizowana lista prac** — użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy.


## <a name="workflow-content"></a>Zawartość przepływu pracy

+ [Architektura przepływu pracy](workflow-system-architecture.md)
+ [Elementy przepływu pracy](workflow-elements.md)
+ [Akcje przepływu pracy](workflow-actions.md)
+ [Tworzenie przepływu pracy](create-workflow.md)
+ [Konfigurowanie właściwości przepływu pracy](configure-workflow-properties.md)
+ [Konfigurowanie zadania ręcznego w przepływie pracy](configure-manual-task-workflow.md)
+ [Konfigurowanie zadania wykonywanego automatycznie w przepływie pracy](configure-automated-task-workflow.md)
+ [Konfigurowanie procesu zatwierdzania w przepływie pracy](configure-approval-process-workflow.md)
+ [Konfigurowanie etapu zatwierdzania w przepływie pracy](configure-approval-step-workflow.md)
+ [Konfigurowanie ręcznej decyzji w przepływie pracy](configure-manual-decision-workflow.md)
+ [Konfigurowanie decyzji warunkowej w przepływie pracy](configure-conditional-decision-workflow.md)
+ [Konfigurowanie działania równoległego w przepływie pracy](configure-parallel-activity-workflow.md)
+ [Konfigurowanie odgałęzienia równoległego w przepływie pracy](configure-parallel-branch-workflow.md)
+ [Konfigurowanie przepływu pracy dla pozycji w wierszu](configure-line-item-workflow.md)

