---
title: Zunifikowana sekwencja numerów dla identyfikatorów zadań
description: Ta funkcja udostępnia pojedynczą, ujednoliconą sekwencję numerów, która generuje identyfikatory zadań w modułach Kontrola produkcji, Wykonywanie produkcji oraz Czas i frekwencja.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824949"
---
# <a name="unified-number-sequence-for-job-ids"></a>Zunifikowana sekwencja numerów dla identyfikatorów zadań

[!include [banner](../includes/banner.md)]

Ta funkcja udostępnia pojedynczą, ujednoliconą sekwencję numerów, która generuje identyfikatory zadań w modułach Kontrola produkcji, Wykonywanie produkcji oraz Czas i frekwencja. Wcześniej można było wybrać inną sekwencję numerów dla każdego z tych modułów, co może spowodować konflikt identyfikatorów zadań, jeśli co najmniej dwie sekwencje użyły identycznego formatu. Taki konflikt może spowodować uszkodzenie danych.

## <a name="turn-on-this-feature-for-your-system"></a>Włączanie funkcji w systemie

Jeśli Twój system nie zawiera jeszcze funkcji opisanych w tym temacie, przejdź do [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz funkcję *Ujednolicona sekwencja numerów dla identyfikatorów zadań*.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>Skonfiguruj ujednoliconą sekwencję numerów dla identyfikatorów zadań

Po włączeniu tej funkcji istniejące ustawienia sekwencji numerów **identyfikacyjnych zadania** znajdujące się na stronach parametrów dla modułów Kontrola produkcji, Realizacja produkcji oraz Czas i obecność zostaną wycofane i zostanie dodane nowe pole **Ujednoliconego identyfikatora zadania**. Wartość **Ujednoliconego identyfikatora zadania** jest współużytkowana przez wszystkie trzy moduły, dzięki czemu wszystkie moduły odwołują się do tej samej sekwencji numerów. Identyfikatory zadań będą więc unikatowe we wszystkich trzech modułach i nigdy nie wystąpi konflikt.

Skonfiguruj ujednoliconą sekwencję numerów dla identyfikatorów zadań:

1. Włącz tę funkcję, tak jak opisano w poprzedniej sekcji.
1. Określ sekwencję numerów, która ma być użyciu dla identyfikatorów zunifikowanych zadań, lub utwórz nowy. Aby uzyskać więcej informacji, zobacz temat [Omówienie sekwencji identyfikatorów](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).
1. Przejdź do strony **Parametry kontroli produkcji**, **Parametry wykonania produkcji** lub **Strona parametrów czasu i frekwencji**. Nie ma znaczenia, którą z nich wybierzesz, ponieważ po ustawieniu tego ustawienia na dowolnej z tych stron wszystkie pozostałe strony zostaną automatycznie aktualizowane.
1. Otwórz kartę **Sekwencje numerów** na wybranej stronie parametrów.
1. Przypisz **Kod sekwencji numerów**, który wcześniej określono, do wiersza **Ujednoliconych identyfikatorów zadań** w siatce.
