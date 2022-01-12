---
title: Ulepszenia wydajności oczyszczania historii sprzedaży
description: W tym temacie opisano historię sprzedaży oraz sposób jej włączania.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 610f0d4e0448dd21d10765400f25cd89e3c7a84b
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920280"
---
# <a name="sales-history-cleanup-performance-improvements"></a>Ulepszenia wydajności oczyszczania historii sprzedaży

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.24 -->

Okresowe zadanie wsadowe **Czyszczenie historii sprzedaży** może trwać długo, jeśli jest wykonywane rzadko w środowiskach z dużą ilością aktualizacji sprzedaży. W takich sytuacjach funkcja *Ulepszeń wydajności oczyszczania historii sprzedaży* może pomóc w skróceniu czasu trwania działania i poprawieniu niezawodności.

Ta funkcja usprawnia istniejące zadanie oczyszczania w następujący sposób:

- Proces oczyszczania jest dzielony na partie (rozmiar partii można zmieniać za pomocą dostosowań).
- Będzie on uruchamiany maksymalnie na 2 godziny (można zmienić czas trwania za pomocą dostosowań).
- Tam, gdzie to możliwe, będą wykorzystane możliwości bazy danych, aby zminimalizować rywalizację o blokowanie i uniknąć łączenia tabel transakcyjnych podczas czyszczenia.

Po włączeniu tej funkcji zadanie wsadowe **Oczyszczania historii aktualizacji sprzedaży** (**Sprzedaż i marketing \> Zadania okresowe \> Czyszczenie \> Oczyszczanie historii aktualizacji sprzedaży**) będzie uruchamiane tak jak poprzednio, ale z lepszą wydajnością i przez maksymalnie 2 godziny. Oznacza to, że może być konieczne uruchomienie go kilka razy w celu oczyszczenia wszystkich danych w określonym horyzoncie czasowym przechowywania.

## <a name="turn-on-the-sales-history-cleanup-performance-improvements-feature"></a>Włącz funkcję ulepszeń wydajności oczyszczania historii sprzedaży

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Sprzedaż i marketing*
- **Nazwa funkcji:** *Ulepszenie wydajności oczyszczania historii sprzedaży*
