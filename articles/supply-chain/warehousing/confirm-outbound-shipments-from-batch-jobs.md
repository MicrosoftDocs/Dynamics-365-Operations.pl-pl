---
title: Potwierdź wychodzące wysyłki z zadań wsadowych
description: W tym temacie opisano sposób konfigurowania zadania wsadowego, które automatycznie potwierdza wysyłki wychodzących zamówień przeniesienia dla ładunków gotowych do wysyłki.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 41dbfb90b7b19c964e725ee0a4c769402414fb17
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4434988"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Potwierdź wychodzące wysyłki z zadań wsadowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania zadania wsadowego, które automatycznie potwierdza wysyłki wychodzących zamówień przeniesienia dla ładunków gotowych do wysyłki. Opisane tu zadanie wsadowe dotyczy tylko wysyłek zamówień przeniesienia, a nie zamówień sprzedaży.

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a>Włącz funkcję Potwierdź wychodzące wysyłki z zadań wsadowych

Aby móc używać tej funkcji, musi zosyać włączona w systemie. Administratorzy mogą skorzystać ze strony [Zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby. Funkcja jest wyświetlana jako:

- **Moduł** - *Zarządzanie magazynem*
- **Nazwa funkcji** - *Potwierdź wychodzące wysyłki z zadań wsadowych*

## <a name="process-outbound-shipments"></a>Przetwarzanie wysyłek wychodzących

Aby skonfigurować zaplanowane zadanie wsadowe w celu uruchomienia potwierdzenia wysyłki wychodzącej dla ładunków gotowych do wysyłki:

1. Przejdź do **Zarządzanie magazynem \> Zadania okresowe \> Przetwarzanie przesyłek wychodzących**.
1. Zostanie otwarte okno dialogowe **Potwierdzanie wysyłki**. W **Rekordy do uwzględnienia** na skróconej karcie, wybierz opcję **Filtr**.
1. Otworzy się okno dialogowe edytora zapytań. Na karcie **Zakres** dodaj wiersz z następującymi wartościami:
    - **Tabela** - *Ładunki*
    - **Tabela pochodna** - *Ładunki*
    - **Pole** - *Stan ładunku*
    - **Kryterium** - *Załadowano*
1. Wybierz przycisk **OK**, aby powrócić do okna dialogowego **Potwierdzanie wysyłki**.
1. Na skróconej karcie **Uruchom w tle** należy skonfigurować **Przetwarzanie wsadowe** na wartość **Tak**.
1. Na skróconej karcie **Uruchom w tle** wybierz **Cykl**.
1. Zostanie otwarte okno dialogowe **Definiuj cykl**. Umożliwia ustawienie harmonogramu uruchamiania w zależności od potrzeb firmy.
1. Wybierz przycisk **OK**, aby powrócić do okna dialogowego **Potwierdzanie wysyłki**.
1. Aby dodać zadanie wsadowe do kolejki przetwarzania wsadowego, należy wybrać opcję **OK** w oknie dialogowym **Potwierdzanie wysyłki**.

Aby uzyskać więcej informacji, zobacz [Omówienie przetwarzania wsadowego](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
