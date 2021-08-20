---
title: Nie można anulować pracy z powodu stanu
description: Nie można anulować pracy z powodu stanu
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
ms.openlocfilehash: f983501b490c5516525b4d5904603ed62e8799f9e6124e5672b36a12804ecb0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755985"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a>Nie można anulować pracy z powodu stanu

Kod błędu: WAX2190

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Nie możesz anulować pracy %1, ponieważ jej stanem jest %2.

## <a name="cause"></a>Powód

Nie można anulować pracy w jej bieżącym stanie.

Nagłówek pracy lub wiersze pracy nie mają oczekiwanej wartości **Stan pracy**. Pole **Stan pracy** w nagłówku pracy nie jest ustawione na *Otwarte* ani *W toku*.

## <a name="resolution"></a>Rozdzielczość

Aby anulować pracę, wykonaj następujące kroki.

1. Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.
1. W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować.
1. Kliknij przycisk **OK**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.

Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).
