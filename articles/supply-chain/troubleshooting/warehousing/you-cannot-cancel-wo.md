---
title: Nie można anulować pracy dotyczącej użytkownika
description: Nie można anulować pracy dotyczącej użytkownika
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
ms.openlocfilehash: 1d7b0140d0c2724234a549ca4dfb23109012654abe0e60fcea1f98e8f17c153a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748698"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a>Nie można anulować pracy dotyczącej użytkownika

Kod błędu: WAX708

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Nie można anulować pracy przypisanej do użytkownika.

## <a name="cause"></a>Powód

Praca jest zablokowana przez użytkownika i nie można jej anulować. Aby to potwierdzić, otwórz identyfikator pracy, a następnie otwórz kartę **Ogólne**. Jeśli praca jest zablokowana, pole **Stan pracy** będzie mieć wartość *W toku*, a w polu **Zablokowane przez** będzie identyfikator użytkownika.

## <a name="resolution"></a>Rozdzielczość

Aby anulować pracę, wykonaj następujące kroki.

1. Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.
1. W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować.
1. Kliknij przycisk **OK**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.

Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).
