---
title: Ostatnim zamkniętym wierszem pracy musi być Odłożenie
description: Ostatnim zamkniętym wierszem pracy musi być Odłożenie
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924382"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>Ostatnim zamkniętym wierszem pracy musi być Odłożenie

Kod błędu: WAX1285

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Ostatnim zamkniętym wierszem pracy musi być Odłożenie.

## <a name="cause"></a>Powód

Nie można anulować pracy w jej bieżącym stanie.

W ostatnim wierszu pracy pole **Stan pracy** ma wartość *Zamknięte*, ale pole **Typ pracy** nie ma wartości *Odłożenie*.

## <a name="resolution"></a>Rozdzielczość

Aby anulować pracę, wykonaj następujące kroki.

1. Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.
1. W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować.
1. Kliknij przycisk **OK**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.

Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).
