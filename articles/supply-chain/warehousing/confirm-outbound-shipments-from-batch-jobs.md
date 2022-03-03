---
title: Potwierdź wychodzące wysyłki z zadań wsadowych
description: W tym temacie opisano sposób konfigurowania zadania wsadowego, które automatycznie potwierdza wysyłki wychodzących zamówień przeniesienia dla ładunków gotowych do wysyłki.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f68dcfc0c1454ee5b095e186c52faa6c83bf8dc6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103922"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>Potwierdź wychodzące wysyłki z zadań wsadowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób konfigurowania zadania wsadowego, które automatycznie potwierdza wysyłki wychodzących zamówień przeniesienia dla ładunków gotowych do wysyłki. Opisane tu zadanie wsadowe dotyczy tylko wysyłek zamówień przeniesienia, a nie zamówień sprzedaży.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>Włącz lub wyłącz funkcję Potwierdź przesyłki wychodzące z zadań wsadowych

Aby korzystać z funkcji opisanej w tym temacie, w systemie musi być włączona funkcja *Potwierdź przesyłki wychodzące z zadań wsadowych*. Od wersji 10.0.21 Supply Chain Management version ta funkcja jest domyślnie włączona. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Potwierdź przesyłki wychodzące z zadań wsadowych* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]