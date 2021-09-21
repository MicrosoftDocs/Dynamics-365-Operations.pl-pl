---
title: Błąd podczas ponownego przesyłania zamówienia zakupu do przepływu pracy po wykonaniu zmiany
description: Błąd podczas ponownego przesyłania zamówienia zakupu do przepływu pracy po wykonaniu zmiany
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4b8465d198c440f27a4b3cc4268445e0aa450f5b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477355"
---
# <a name="error-on-resubmitting-a-purchase-order-to-a-workflow-after-a-change"></a>Błąd podczas ponownego przesyłania zamówienia zakupu do przepływu pracy po wykonaniu zmiany


## <a name="symptoms"></a>Objawy

Następujący błąd występuje w przepływie pracy, gdy zamówienie zakupu zostanie ponownie przesłane po zmianie:

> Zatrzymane (błąd): X++ Wyjątek: zmiany w zamówieniu zakupu 0000569 są dozwolone tylko w stanie wersji roboczej, gdy uaktywnione jest zarządzanie zmianami na<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

Ten problem występuje tylko wtedy, gdy zamówienie zakupu było w stanie *Potwierdzonym* przed zapisaniem zmian. Jeśli zażądasz zmian w czasie, gdy zamówienie zakupu znajduje się w stanie *Zatwierdzone*, przepływ pracy może zostać przetworzony pomyślnie.

## <a name="resolution"></a>Rozwiązanie

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Ten błąd zostanie rozwiązany za pomocą [niniejszego artykułu z bazy wiedzy Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).
