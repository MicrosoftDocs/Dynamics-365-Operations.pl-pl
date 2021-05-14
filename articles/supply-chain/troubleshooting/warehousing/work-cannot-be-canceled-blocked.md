---
title: Nie można anulować pracy z powodu blokady
description: Nie można anulować pracy z powodu blokady
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924286"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a>Nie można anulować pracy z powodu blokady

Kod błędu: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Nie można anulować pracy %1, ponieważ jest zablokowana przez typ przyczyny %2. Praca musi zostać odblokowana, aby mogła zostać anulowana.

## <a name="cause"></a>Powód

Praca jest zablokowana i nie można jej anulować.

Na stronie **Praca**, na karcie **Ogólne** opcja **Zablokowano** ma wartość *Tak*. To ustawienie wskazuje, że praca jest zablokowana. Na karcie **Przyczyny blokowania** pokazano, dlaczego praca została zablokowana.

## <a name="resolution"></a>Rozdzielczość

Aby odblokować pracę, wybierz kartę **Przyczyny blokowania**, a następnie wykonaj jedną z poniższych czynności:

- Jeśli w polu **Przyczyna blokowania pracy** jest ustawiona wartość *Niezdefiniowana przyczyna*: w okienku akcji na karcie **Praca** w grupie **Praca** wybierz pozycję **Odblokuj pracę**.
- Jeśli w polu **Przyczyna blokowania pracy** jest ustawiona wartość *Przetwarzanie grupy czynności*: w okienku akcji, na karcie **Informacje pokrewne** w grupie **Informacje pokrewne** wybierz pozycję **Grupa czynności**. Następnie na stronie **Grupa czynności**, w okienku akcji otwórz kartę **Grupa czynności** i z grupy **Grupa czynności** wybierz pozycję **Czyszczenie danych grupy czynności**.

## <a name="workaround"></a>Obejście

Jeśli poprzednie kroki nie rozwiązały problemu, możesz anulować pracę, wykonując następujące kroki.

1. Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.
1. W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować, a obecnie ma wartość pola **Stan pracy** *Otwarta*, *W toku*, *Anulowana*, *Połączona* lub *Zamknięta*.
1. Kliknij przycisk **OK**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.

Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).
