---
title: Planowanie z nieskończoną zdolnością produkcyjną
description: Ten artykuł zawiera informacje o planowaniu nieskończonej pojemności. Opisano w nim także bieżące ograniczenia funkcji.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7249734e5d2644145a36276dbc818a40b5962805
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740013"
---
# <a name="scheduling-with-infinite-capacity"></a>Planowanie z nieskończoną zdolnością produkcyjną

[!include [banner](../../includes/banner.md)]

Funkcja *Nieskończone planowanie pojemności na potrzeby optymalizacji planowania* wprowadza planowanie oparte na informacjach o trasie. Umożliwia planowanie zadań w oparciu o szeroki zakres konfiguracji tras. Planowanie obejmuje często używane ustawienia marszruty, w tym sekwencję operacji marszruty lub wymagania dotyczące zasobów operacji marszruty.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>Włącz lub wyłącz funkcję nieskończonego planowania zdolności produkcyjnych

Aby używać tej funkcji, należy ją włączyć dla systemu. Od wersji 10.0.29 Supply Chain Management funkcja jest domyślnie włączona. Administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Planowanie nieskończonych zdolności produkcyjnych dla optymalizacji planowania* w obszarze roboczym [Zarządzanie funkcjami](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Aby uzyskać więcej informacji o tej funkcji, zobacz temat [Planowanie z wyborem zasobu na podstawie funkcji](capability-based-scheduling.md).

## <a name="added-functionality"></a>Dodane funkcje

Funkcja *Nieskończone planowanie pojemności na potrzeby optymalizacji planowania* umożliwia planowanie zadań w oparciu o informacje o trasie. Dlatego ustawienia marszruty mogą być używane do planowania procesów produkcyjnych. Chociaż ta funkcja ma pewne ograniczenia, których nie posiada zdeprecjonowany silnik planowania głównego, obsługuje ona najczęstszą funkcjonalność, która jest wymagana w scenariuszach produkcyjnych.

Funkcja uwzględnia zarówno *proste marszruty*, jak i *sieci marszrut*. Korzystając z pola **Dalej** w operacji marszruty, możesz skonfigurować złożone trasy, które mają wiele punktów początkowych i wiele operacji, które działają równolegle. Podczas planowania system uwzględni złożone struktury tras tego typu.

Dodatkowo funkcja obsługuje *równoległe operacje* na marszrutach. Za pomocą opcji *Główny* i *Dodatkowy* w polu **Priorytet** operacji marszruty można zdefiniować strukturę marszruty, w której jedna operacja marszruty jest operacją główną, a inna operacja jest operacją pomocniczą. W takim przypadku system uwzględni strukturę trasy podczas planowania.

Podczas procesu planowania system uwzględnia również *wymagania dotyczące zasobów* określone dla operacji. System wykorzystuje wymagania dotyczące zasobów, aby określić, które zasoby są wymagane do wykonania operacji. Obecnie funkcja *nieskończonego planowania zdolności produkcyjnych na potrzeby optymalizacji planowania* obsługuje następujące typy wymagań dotyczących zasobów:

- Typ zasobu
- Zasób
- Grupa zasobów
- Zdolność (Aby uzyskać więcej informacji, zobacz temat [Planowanie z wyborem zasobu na podstawie funkcji](capability-based-scheduling.md)).

> [!NOTE]
>
> - Jeśli dla zasobu i/lub grupy zasobów ustawiono nieskończoną zdolność produkcyjną, planowanie główne uzna je za nieskończoną zdolność produkcyjną.
> - Wymagania związane z zasobami ludzkimi, takie jak umiejętności lub wymagania dotyczące certyfikatów, nie są jeszcze obsługiwane.

Funkcja obsługuje również właściwości operacyjne **Czas instalacji** i **Czas wykonywania**. Jeśli te właściwości zostaną ustawione dla operacji marszruty, proces planowania utworzy odpowiednie zadania konfiguracji i procesu.

Podsumowując, planowanie obsługuje najczęściej używane scenariusze. Możesz utworzyć trasę, dodać operacje podstawowe i drugorzędne, zdefiniować następne operacje, dodać wymagania dotyczące zasobów oraz dodać czas konfiguracji i czas wykonywania. Podczas planowania system będzie uwzględniał te informacje.

## <a name="limitations"></a>Ograniczenia

W przypadku korzystania z funkcji *Planowanie nieskończonych zdolności produkcyjnych dla optymalizacji planowania* obowiązują następujące ograniczenia:

- Ta funkcja obsługuje tylko nieskończoną pojemność.
- Funkcja nie obsługuje funkcji ładowania zasobów.
- Funkcja nie uwzględnia odpadków marszruty.
- Funkcja obsługuje funkcję *Czas trwania* tylko jako wybór zasobu głównego.
