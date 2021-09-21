---
title: Arkusz magazynowy jest zablokowany, a zadanie partii przepływu pracy nie działa
description: Jeden z arkuszy magazynowych jest zablokowany przez operację i nie jest zwalniany
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
ms.openlocfilehash: 8b21ec2e2b3b8546dcb138422c5540053392c179
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477281"
---
# <a name="your-inventory-journal-is-locked-and-the-workflow-batch-job-doesnt-work"></a>Arkusz magazynowy jest zablokowany, a zadanie partii przepływu pracy nie działa

## <a name="symptoms"></a>Objawy

Jeden z arkuszy magazynowych jest zablokowany przez operację i nie jest zwalniany. Jeśli na przykład podczas księgowania wystąpi nieznany błąd (czyli operacja blokowania systemu), arkusz może pozostać w stanie zablokowania systemu. W takim przypadku program obsługi elementów roboczych przepływu pracy wystąpi błąd podczas blokowania weryfikacji.

## <a name="resolution"></a>Rozwiązanie

Zaloguj się do wystąpienia programu SQL Server dla aplikacji Supply Chain Management i sprawdź, czy ustawienie **InventJournalTable.SystemBlocked** ma wartość *1*. Jeśli tak, upewnij się, że arkusz nie powinien być w stanie zablokowania, a następnie zresetuj pozycję **InventJournalTable.SystemBlocked** na *0*.
