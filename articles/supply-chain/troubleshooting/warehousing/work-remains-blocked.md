---
title: Praca pozostaje zablokowana
description: Praca pozostaje zablokowana
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924137"
---
# <a name="work-remains-blocked"></a>Praca pozostaje zablokowana

Kod błędu: WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Praca %1 pozostaje zablokowana, ponieważ powiązana grupa czynności %2 ma stan %3.

## <a name="cause"></a>Powód

Praca jest obecnie przetwarzana w grupy czynności i nie można jej odblokować, co sygnalizuje jeden z następujących warunków:

- Na karcie **Przyczyny blokowania** pole **Przyczyna blokady pracy** dla co najmniej jednego wiersza ma wartość *Przetwarzanie grupy czynności*.
- Po wybraniu opcji **Grupa czynności** w grupie **Informacje pokrewne** na karcie **Informacje pokrewne** w okienku akcji pole **Stan grupy czynności** ma wartość *Przetwarzanie*.

## <a name="resolution"></a>Rozdzielczość

W okienku akcji, na karcie **Informacje pokrewne**, w grupie **Informacje pokrewne** wybierz opcję **Grupa czynności**. Następnie na stronie **Grupa czynności**, w okienku akcji otwórz kartę **Grupa czynności** i z grupy **Grupa czynności** wybierz pozycję **Czyszczenie danych grupy czynności**.

## <a name="workaround"></a>Obejście

Jeśli poprzednie kroki nie rozwiązały problemu, możesz anulować pracę, wykonując następujące kroki.

1. Przejdź do lokalizacji **Zarządzanie magazynem \> Zadania okresowe \> Oczyszczanie \> Anuluj pracę**.
1. W polu **Identyfikator pracy** określ identyfikator pracy, którą chcesz anulować, a obecnie ma wartość pola **Stan pracy** *Otwarta*, *W toku*, *Anulowana*, *Połączona* lub *Zamknięta*.
1. Kliknij przycisk **OK**.
1. Zaznacz **Tak**, aby potwierdzić, że chcesz anulować pracę.

Aby uzyskać więcej informacji, zobacz temat [Anulowanie pracy magazynowej w celu obsługi wyjątków](../../warehousing/cancel-warehouse-work.md).
