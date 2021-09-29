---
title: Planowanie z nieskończoną zdolnością produkcyjną
description: Ten temat zawiera informacje na temat planowania nieograniczonej wydajności na potrzeby optymalizacji planowania. Opisano w nim także bieżące ograniczenia funkcji.
author: crytt
ms.date: 09/21/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9e1e423aaed06f6bb2b42e27d41c2aef46ffe104
ms.sourcegitcommit: b5f2d88ff4e0a234fa6b9ee33516425e54ff2c3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2021
ms.locfileid: "7506814"
---
# <a name="scheduling-with-infinite-capacity"></a>Planowanie z nieskończoną zdolnością produkcyjną

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Funkcja *Nieskończone planowanie pojemności na potrzeby optymalizacji planowania* wprowadza planowanie oparte na informacjach o trasie. Umożliwia planowanie zadań w oparciu o szeroki zakres konfiguracji tras. Planowanie optymalizacji planowania obejmuje często używane ustawienia marszruty, w tym sekwencję operacji marszruty lub wymagania dotyczące zasobów operacji marszruty.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Włącz funkcję nieskończonego planowania zdolności produkcyjnych

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Planowanie główne*
- **Nazwa funkcji**: *Planowanie nieskończonej zdolności produkcyjnej dla optymalizacji planowania*

Aby uzyskać więcej informacji o tej funkcji, zobacz temat [Planowanie z wyborem zasobu na podstawie funkcji](capability-based-scheduling.md).

## <a name="added-functionality"></a>Dodane funkcje

Funkcja *Nieskończone planowanie pojemności na potrzeby optymalizacji planowania* umożliwia planowanie zadań w oparciu o informacje o trasie. Dlatego ustawienia marszruty mogą być używane do planowania procesów produkcyjnych. Chociaż ta funkcja ma pewne ograniczenia, których nie ma wbudowane planowanie główne, obsługuje ona najbardziej typowe funkcje wymagane w scenariuszach produkcyjnych.

Funkcja uwzględnia zarówno *proste marszruty*, jak i *sieci marszrut*. Korzystając z pola **Dalej** w operacji marszruty, możesz skonfigurować złożone trasy, które mają wiele punktów początkowych i wiele operacji, które działają równolegle. Podczas planowania system uwzględni złożone struktury tras tego typu.

Dodatkowo funkcja obsługuje *równoległe operacje* na marszrutach. Za pomocą opcji *Główny* i *Dodatkowy* w polu **Priorytet** operacji marszruty można zdefiniować strukturę marszruty, w której jedna operacja marszruty jest operacją główną, a inna operacja jest operacją pomocniczą. W takim przypadku system uwzględni strukturę trasy podczas planowania.

Podczas procesu planowania system uwzględnia również *wymagania dotyczące zasobów* określone dla operacji. System wykorzystuje wymagania dotyczące zasobów, aby określić, które zasoby są wymagane do wykonania operacji. Obecnie funkcja *nieskończonego planowania zdolności produkcyjnych na potrzeby optymalizacji planowania* obsługuje następujące typy wymagań dotyczących zasobów:

- Typ zasobu
- Zasób
- Grupa zasobów
- Zdolność (Aby uzyskać więcej informacji, zobacz temat [Planowanie z wyborem zasobu na podstawie funkcji](capability-based-scheduling.md)).

> [!NOTE]
> Wymagania związane z zasobami ludzkimi, takie jak umiejętności lub wymagania dotyczące certyfikatów, nie są jeszcze obsługiwane.

Funkcja obsługuje również właściwości operacyjne **Czas instalacji** i **Czas wykonywania**. Jeśli te właściwości zostaną ustawione dla operacji marszruty, proces planowania utworzy odpowiednie zadania konfiguracji i procesu.

Podsumowując, planowanie optymalizacji planowania obsługuje najczęściej używane scenariusze. Możesz utworzyć trasę, dodać operacje podstawowe i drugorzędne, zdefiniować następne operacje, dodać wymagania dotyczące zasobów oraz dodać czas konfiguracji i czas wykonywania. Podczas planowania system będzie uwzględniał te informacje.

## <a name="limitations"></a>Ograniczenia

W przypadku korzystania z planowania do optymalizacji planowania obowiązują następujące ograniczenia:

- Ta funkcja obsługuje tylko nieskończoną pojemność.
- Funkcja nie obsługuje funkcji ładowania zasobów.
- Funkcja nie uwzględnia odpadków marszruty.
- Funkcja obsługuje funkcję *Czas trwania* tylko jako wybór zasobu głównego.

Pamiętaj, że funkcja *nieskończonego planowania zdolności produkcyjnych dla funkcji optymalizacji planowania* jest poprawiana. Firma Microsoft spodziewa się wprowadzić obsługę dodatkowych ustawień planowania w przyszłych wydaniach.
