---
title: "Omówienie systemu przepływu pracy"
description: W tym artykule opisano system obiegu pracy w programie Microsoft Dynamics 365 dla operacji.
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 08c36f02f88fef7508730b6c01a1c99a0f77fb0c
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-system-overview"></a>Omówienie systemu przepływu pracy

W tym artykule opisano system obiegu pracy w programie Microsoft Dynamics 365 dla operacji.

<a name="what-is-workflow"></a>Co to jest przepływ pracy?
-----------------

Termin *przepływ pracy* można definiować na dwa sposoby: jako system i jako proces biznesowy.
### <a name="workflow-is-a-system"></a>Przepływ pracy jest systemem

Przepływ pracy jest system, który jest instalowany z systemu Dynamics 365 dla operacji i uruchamiany na serwerze obiektów aplikacji (AOS). System przepływu pracy zawiera funkcjonalność, której można używać do tworzenia pojedynczych przepływów pracy, czyli procesów biznesowych.

### <a name="workflow-is-a-business-process"></a>Przepływ pracy jest procesem biznesowym

Przepływ pracy reprezentuje proces biznesowy. Definiuje sposób przepływu lub przenoszenia dokumentu przez system, pokazując, kto musi wykonać zadanie, podjąć decyzję lub zatwierdzić dokument. Na przykład poniższa ilustracja pokazuje przepływ pracy dla raportów z wydatków. ![Przepływ pracy z elementami przypisanymi do użytkowników](./media/workflow_user.gif) Aby lepiej zrozumieć ten przepływ pracy, załóżmy, że Sam przesyła raport z wydatków na 7000 USD. W tym scenariuszu Ivan musi przejrzeć pokwitowania wysłane przez Tomasza. Następnie Wojciech i Magda muszą zatwierdzić raport z wydatków. Teraz załóżmy, że Tomasz przesyła raport z wydatków na kwotę 11 000 USD. W tym scenariuszu Maciej musi przejrzeć pokwitowania, a Wojciech, Magda i Anna muszą zatwierdzić raport z wydatków.
 Zalety używania systemu przepływu pracy
-------------------------------------

Używanie systemu przepływu pracy w organizacji ma kilka zalet:
-   **Spójność procesów** — Możesz zdefiniować sposób przetwarzania określonych dokumentów, takich jak zapotrzebowania zakupu i raporty z wydatków. System przepływu pracy zapewnia, że dokumenty będą przetwarzane i zatwierdzane w spójny i wydajny sposób.
-   **Widoczność procesu** — Możesz śledzić stan, historię i miary wydajności określonego wystąpienia przepływu pracy. Pozwala to na określanie, czy zmiany powinny zostać wprowadzone do przepływu pracy w celu poprawienia wydajności.
-   **Scentralizowana lista prac** — użytkownicy mogą wyświetlić scentralizowaną listę prac, aby przeglądać przypisane do nich zadania i zatwierdzenia przepływu pracy.




