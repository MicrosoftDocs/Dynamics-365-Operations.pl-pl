---
title: Rozwiązywanie problemów z przepływami pracy związanymi z zaopatrzeniem i sourcingiem
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zaopatrzeniem i sourcingiem.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d5d688c5769a62580e48908117d0562b26eab10a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222832"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a>Rozwiązywanie problemów z przepływami pracy związanymi z zaopatrzeniem i sourcingiem

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z zaopatrzeniem i sourcingiem.

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a>Błąd podczas ponownego przesyłania zamówienia zakupu do przepływu pracy po zmianie: „Zmiany w zamówieniu X są dozwolone tylko w stanie Wersja robocza, gdy zarządzanie zmianami jest aktywne”

Ten problem występuje tylko wtedy, gdy zamówienie zakupu było w stanie *Potwierdzonym* przed zapisaniem zmian. Jeśli zażądasz zmian w czasie, gdy zamówienie zakupu znajduje się w stanie *Zatwierdzone*, przepływ pracy może zostać przetworzony pomyślnie.

### <a name="error-description"></a>Opis błędu

Następujący błąd występuje w przepływie pracy, gdy zamówienie zakupu zostanie ponownie przesłane po zmianie:

> Zatrzymane (błąd): X++ Wyjątek: zmiany w zamówieniu zakupu 0000569 są dozwolone tylko w stanie wersji roboczej, gdy uaktywnione jest zarządzanie zmianami na<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

Ten błąd zostanie rozwiązany za pomocą [niniejszego artykułu z bazy wiedzy Microsoft Knowledge Base (KB)](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Co najmniej jedna dystrybucja księgowa jest rozproszona lub niepełna.

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a>Jeśli reszta dostawy została anulowana w zamówieniu zakupu, w którym jest włączone zarządzanie zmianami, zamówienie zakupu przechodzi do stanu potwierdzonego.

### <a name="issue-description"></a>Opis problemu

W przypadku zamówienia zakupu, które jest związane z zarządzaniem zmianami, jeśli jedyną żądaną zmianą jest anulowanie reszty dostawy w jednym lub kilku wierszach, zamówienie zakupu będzie przechodzić bezpośrednio do stanu *Potwierdzone*, a arkusz nie zostanie utworzony.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Anulowanie reszty dostawy nie wpływa na zawartość arkusza potwierdzeń. Ta funkcja powinna być używana, gdy wiersz został częściowo odebrany, a pozostała jakość powinna zostać anulowana w kroku procesu po potwierdzeniu zamówienia zakupu u dostawcy.

Jeśli powinno to znaleźć odzwierciedlenie w potwierdzeniu zamówienia, ilość powinna zostać dostosowana w wierszu zamówienia, tak aby potwierdzenie było wymagane. Alternatywnie, jeśli nic nie zostało odebrane w wierszu, ilość może zostać usunięta. W takim przypadku będzie wymagane ponowne potwierdzenie.

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a>Anulowane zamówienia zakupu są wyświetlane na liście wersji roboczych w obszarze roboczym Przygotowywania zamówień zakupu.

### <a name="issue-description"></a>Opis problemu

Po anulowaniu zamówień zakupu, które były w stanie *Potwierdzone*, anulowane zamówienia zakupu nadal są wyświetlane na liście wersji roboczych zamówień zakupu w obszarze roboczym **Przygotowanie zamówienia zakupu**.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Ten problem występuje tylko w przypadku zamówień zakupu, które podlegają zarządzaniu zmianami. Dzieje się tak, ponieważ anulowanie jest uznawane za zmianę, która musi zostać zatwierdzona. Zatwierdzenie może być wykonane automatycznie przez system. Dlatego procesowi jest przesłanie anulowanego zamówienia zakupu do przepływu pracy zatwierdzania, aby można było przejść do stanu *Zatwierdzone*. W tym momencie zamówienie zakupu nie będzie już wyświetlane na liście wersji roboczych zamówień zakupu w obszarze roboczym **Przygotowywania zamówienia zakupu**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]