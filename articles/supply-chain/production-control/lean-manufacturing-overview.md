---
title: Produkcja oszczędna — omówienie
description: Ten artykuł zawiera omówienie i opis funkcji produkcji oszczędnej dostępnych w usłudze Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19371
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6db940548018c9d6bbb31891c21f7c334ba8956
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562399"
---
# <a name="lean-manufacturing-overview"></a>Omówienie wytwarzania typu lean manufacturing

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie i opis funkcji produkcji oszczędnej dostępnych w usłudze Microsoft Dynamics 365 for Finance and Operations.

Lean manufacturing oferuje narzędzia służące do modelowania produkcji oszczędnej. Te narzędzia obsługują i promują stosowanie następujących pojęć i działań:
-   Tworzenie podstaw produkcji oszczędnej (lean manufacturing) przez modelowania procesów produkcji i logistyki jako przepływów produkcji.
-   Implementacja systemu ściągania lean poprzez sygnalizowanie wymagań popytu za pomocą kart Kanban.
-   Monitorowanie i obsługa zadań w systemie Kanban.

Architektura produkcji oszczędnej (lean manufacturing) w programie Finance and Operations składa się z przepływów produkcji, działań i reguł systemu Kanban. Te struktury są pełni zintegrowane z procesami programu Finance and Operations. W środowisku produkcji oszczędnej (lean manufacturing) trybu mieszanego pozwala to łączyć ze sobą różne strategie dostaw, produkcji i pozyskiwania materiałów. Te strategie obejmują zamówienia produkcyjne, zamówienia partii w przemyśle procesowym, zamówienia zakupu i zamówienia przeniesienia.

| **Ważne**                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Program Finance and Operations umożliwia implementację produkcji oszczędnej (lean manufacturing) z kartami Kanban. Powodzenie wprowadzania w życie zasad produkcji oszczędnej (lean manufacturing) zależy jednak od wewnętrznych procesów biznesowych, jakich używasz, oraz rzeczywistych warunki produkcji i środowiska. |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a> Modelowanie procesów produkcji i logistyki jako przepływów produkcji
Aby stworzyć podstawy produkcji oszczędnej (lean manufacturing), trzeba opracować model procesów produkcji i logistyki jako przepływów produkcji. To obejmuje następujące zadania:
1.  Zidentyfikuj procesy, dla których chcesz wdrożyć strategię oszczędnego uzupełnienie zapasów, a następnie stwórz model tych procesów jako przepływów produkcji. Następnie możesz przeanalizować i usprawnić te procesy. Jednym z celów implementacji schematu lean jest ograniczenie odpadów poprzez poprawę przepływu informacji i materiałów.
2.  Zdefiniuj przepływ produkcji jako sekwencję czynności opisującą przepływ materiałów. Działanie przeniesienia określa przesunięcie produktu lub produktów z jednej lokalizacji do innej. Działanie procesu definiuje operację wartości dodanej, która jest stosowana do produktu.
3.  Utwórz wersję przepływu produkcji, która określa wymagania dotyczące czasu taktu przepływu produkcji. Wymagania te są używane do obliczania czasów cyklu każdego działania w procesie produkcji. Można utworzyć wiele wersji przepływów produkcji i następnie użyć tych wersji do poprawy tych procesów.

## <a name="using-kanbans-to-signal-demand-requirements"></a> Sygnalizowanie wymagań popytu za pomocą kart Kanban
System ściągania wytwarza towary tylko wtedy, gdy są one potrzebne. Praktyka ta zmniejsza czasy realizacji dostawy i magazynowych nadwyżki. Można użyć kart Kanban do planowania, śledzenia i przetwarzania wymagań, które są oparte na przepływach produkcji. Aby utworzyć strukturę kanban, utwórz reguły kanban określające, kiedy są tworzone karty Kanban i jak wypełniane są wymagania. Możesz utworzyć dwa typy reguł Kanban. Reguły produkcji tworzą zadania przetwarzania w systemie Kanban, a reguły wycofania w systemie Kanban tworzą zadania przeniesienia w systemie Kanban. Można skonfigurować następujące strategie uzupełniania:
-   Reguły Kanban typu **Stała ilość** są powiązane ze stałą liczbą jednostek obsługi, co oznacza, że liczba aktywnych kart Kanban jest stała. Zawsze gdy wszystkie produkty z karty Kanban są zużywane i jednostki załadunkowe są ręcznie opróżniane, tworzona jest nowa karta Kanban tego samego typu. Podczas tworzenia reguł Kanban ze stałą ilością można obliczyć optymalną liczbę używanych kart Kanban i ilości produktu. Obliczenia uwzględniają prognozę, rzeczywisty popyt z otwartych zamówień, czas realizacji uzupełnienia towarów i historyczne zapotrzebowania.
-   Reguły Kanban typu **Zaplanowane** służą do uzupełniania zapotrzebowań obliczanych podczas planowania głównego. Planowanie główne generuje zaplanowane reguły Kanban, które mogą zostać ustalone na kartach Kanban.
-   Reguły Kanban typu **Zdarzenie** służą do uzupełniania zapotrzebowań pochodzących z wierszy zamówienia sprzedaży, wierszy listy składowej BOM produkcji, wierszy w systemie Kanban lub ustawień minimalnego poziomu zapasów. Kiedy generowane są zdarzenia Kanban, są one ustalane na podstawie wymagań źródłowych.

Po utworzeniu kart kanban, generowane jest jedno lub wiele zadań w systemie, zgodnie z działaniami przepływu kanban, które są zdefiniowane w regułach kanban.

## <a name="monitoring-and-maintaining-kanban-jobs"></a> Monitorowanie i obsługa zadań w systemie Kanban
Produkcja oszczędna (lean manufacturing) zapewnia widoczność bieżącego stanu działań produkcji i logistyki, które są objęte regułami kanban. Dzięki temu można planować i określać priorytety następujących zadań:

-   Przegląd bieżącego harmonogramu zadań Kanban.
-   Planowanie i ponownie planowanie zadań Kanban.
-   Śledzenie i rejestrowanie stanu zadań Kanban.

Poniższa lista opisuje specjalne tablice Kanban:
-   Planowanie zadań Kanban — zapewnia przegląd zadań w systemie Kanban. Tablica pokazuje zadania Kanban i ich stan dla jednej lub wielu komórek roboczych. Zadania są wyświetlane według okresów planowania (dni i tygodni), które są definiowane w modelu przepływu produkcji. Na tablicą są też informacje o zużyciu zdolności produkcyjnych dla według okresu planowania, dzięki czemu można monitorować zaplanowane obciążenie. Można zmienić stan zadania Kanban, ponownie zaplanować zadania Kanban w różnych okresach planowania i wykonywać inne zadania.
-   Tablica Kanban dla zadań przeniesienia — oferuje przegląd bieżących zadań przeniesienia. Można zaktualizować i rejestrować listy pobrania, rozpoczynać i kończyć zadania przeniesienia i wykonywać inne zadania.
-   Tablica Kanban dla zadań procesu — służy do obsługi normalnego przepływu produkcji i wyświetla przegląd bieżącej sytuacji w jednej lub wielu komórkach roboczych. Z tej tablicy zadania Kanban mogą otrzymywać priorytet, można je odbierać lub przekazywać do produkcji. Ta tablica obsługuje też skanowanie kodu kreskowego pod kątem raportowania Kanban.

## <a name="kanban-jobs-and-integration-with-finance-and-operations-processes"></a>Zadania Kanban i integracja z procesami programu Finance and Operations
Zadania Kanban są w pełni zintegrowane z aktualnymi procesami dla transakcji magazynowych w programie Finance and Operations.
-   Można wykonywać działania pobrania w celu uzupełnienia materiałów używanych do wypełniania zapotrzebowania w zadaniach Kanban.
-   Można drukować karty Kanban i listy pobrania pod kątem obsługi zadań kanban. Dokumenty te są używane do reprezentowania, monitorowania i rejestrowania zadań w systemie kanban w magazynie i dla produkcji.
-   Można rejestrować działania pobrania i przenoszenia w magazynie, skanując kody kreskowe.

Oprócz tego produkcja oszczędna (lean manufacturing) obsługuje procesy zakupu i fakturowania dla usług, do których odwołują się działania podwykonawcze.
-   Wiersze umowy zakupu można przypisać do działań podwykonawczych.
-   Można tworzyć okresowe zamówienia zakupu i podsumowania przyjęć pod kątem kupowania i fakturowania usług.





