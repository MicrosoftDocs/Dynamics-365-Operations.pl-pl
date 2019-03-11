---
title: Uzupełnianie zapasów za pomocą kart Kanban wypłat
description: W tym temacie opisano, jak zadanie Kanban wycofania służy do uzupełnienia zapasów materiałów dla działań produkcyjnych.
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanFlow, KanbanRules
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7fe3ebe3c27c380d95cbc12b864264e9538d433f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "320933"
---
# <a name="replenishment-with-withdrawal-kanbans"></a>Uzupełnianie zapasów za pomocą kart Kanban wypłat

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak zadanie Kanban wycofania służy do uzupełnienia zapasów materiałów dla działań produkcyjnych.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>Przepływ pracy uzupełnienia materiałów wykorzystującego zadanie Kanban wycofania
-------------------------------------------------------------------

Zadanie Kanban wycofania może służyć do przenoszenia jednego towaru w systemie Kanban między lokalizacjami w magazynie i na produkcji, gdzie materiał zostanie zużyty. Zadanie Kanban wycofania obsługuje uzupełnianie materiałów w systemie ssania, gdzie sygnał ssania jest wymagany do zainicjowania dostawy dla określonego popytu. 

Następujący scenariusz przedstawia system uzupełniania zapasów wykorzystujący mechanizm ssania, gdzie sygnał ssania inicjuje tworzenie zadania Kanban w celu uzupełnienia materiałów procesu produkcyjnego. 

[![Sygnał ssania inicjuje tworzenie zadania Kanban w celu uzupełnienia materiałów procesu produkcyjnego](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  Kanban wycofania
2.  Lokalizacja źródłowa zadania Kanban i lokalizacja odłożenia dla pracy magazynowej
3.  Lokalizacja docelowa zadania Kanban i lokalizacja wejściowa produkcji
4.  Proces produkcji
5.  Praca magazynowa dla pobrania Kanban
6.  Lokalizacje w magazynie dla surowców
7.  Magazyn materiałów
8.  Magazyn produkcji

W tym scenariuszu proces produkcji (4) zużywa materiał z lokalizacji wejściowej produkcji (3) w magazynie produkcji (8). Po zużyciu jednostki załadunkowej materiału (w zadaniu Kanban) jest ona rejestrowana jako pusta. Jest generowany sygnał uzupełniania zapasów dla źródła towaru i tworzona nowa karta Kanban (1). W tym przypadku źródłem towaru są lokalizacje w magazynie materiałów [7]. Materiał dla zadania Kanban jest pobierany i odkładany do lokalizacji (2) w tym samym magazynie. Materiał po pobraniu jest gotowy do przeniesienia z lokalizacji 2 do lokalizacji wejściowej produkcji (3) w magazynie produkcji (8).

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>Konfigurowanie pracy magazynowej pobrania Kanban dla zadania Kanban wycofania

Aby umożliwić pobranie surowca dla zadania Kanban wycofania, należy skonfigurować szablony grup czynności, szablony pracy i dyrektywy lokalizacji dla zlecenia pracy typu **Pobieranie Kanban**. Ten typ zlecenia pracy obsługuje nie tylko proces pobrania dla zadania Kanban wycofania. Obsługuje również proces pobrania dla zadania Kanban produkcji. Można jednak skonfigurować oddzielny proces pobrania dla każdego typu zadania Kanban, rozdzielając szablony grup czynności, szablony pracy i dyrektywy lokalizacji. Aby rozdzielić szablony grup czynności, szablony pracy i dyrektywy lokalizacji, ustaw dla typu działania (**Przetwarzanie** lub **Przeniesienie**) w zapytaniach dla tych jednostek.

## <a name="configure-the-withdrawal-kanban"></a>Konfigurowanie zadania Kanban wycofania

Działanie przeniesienia używane do zadania Kanban wycofania jest konfigurowane jako część aktywowanego planu działań w przepływie produkcji oszczędnej. W ramach konfiguracji działania przeniesienia określasz lokalizacje źródłową i docelową przeniesienia. Po skonfigurowaniu działania przeniesienia przypisujesz je do reguły Kanban o typie **Wycofanie**. Reguła Kanban ustawia zasady i konfiguracje dla zadania Kanban wycofania. Ilość w zadaniu Kanban określa, ile jednostek załadunkowych zostanie przemieszczonych za pomocą karty Kanban w procesie przenoszenia. Stała ilość w zadaniu Kanban jest używana po wybraniu strategii stałego uzupełnienia zapasów. Ta ilość określa liczbę kart Kanban, które są niezbędne, aby zapobiec wyczerpaniu zapasów w miejscu źródłowym popytu. Stałą ilość można obliczyć na podstawie rzeczywistego popytu, historycznego popytu i poziomów usług. Poniższe dwa scenariusze ilustrują, jak można zarządzać uzupełnianiem materiałów przy użyciu zadania Kanban wycofania.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>Scenariusz 1: Uzupełnienie lokalizacji wejściowej produkcji za pomocą zadania Kanban wycofania o stałej ilości

Proces produkcji zużywa kupiony surowiec z lokalizacji wejściowej produkcji znajdującej się w magazynie produkcji. Surowiec odbierany od dostawcy jest przechowywany w lokalizacji w magazynie materiałów. Ponieważ popyt na materiał jest uważany za stabilny w dłuższym przedziale czasu, został skonfigurowany do zaopatrywania produkcji za pomocą przepływu Kanban o stałej ilości. Po zużyciu ilości Kanban w lokalizacji wejściowej produkcji jest rejestrowany sygnał pustej ilości i do przepływu jest dodawana nowa karta Kanban tego samego typu. 

Sygnał pustej ilości można skonfigurować w taki sposób, aby był generowany automatycznie po zakończeniu zadania Kanban. Alternatywnie sygnał pustej ilości można skonfigurować jako ręczną interakcję wykonywaną z tablicy Kanban przeniesienia lub z menu w urządzeniu podręcznym. Tablica Kanban przeniesienia jest obszarem roboczym, w którym zarządza się wszystkimi działaniami w cyklu życia procesu Kanban. 

Po utworzeniu zadania Kanban jest dodawany wiersz grupy czynności na surowcu do grupy czynności Kanban dla magazynu materiałów. W sekcji listy pobrania na tablicy Kanban przeniesienia stan materiału i pokrewnych procesów magazynowych można monitorować na etapach od utworzenia grupy czynności do utworzenia pracy, aż materiał znajdzie się w dostępnych zapasach w lokalizacji źródłowej przeniesienia i będzie gotowy na przeniesienie do lokalizacji wejściowych produkcji. Zadanie Kanban można wykonać z tablicy Kanban przeniesienia albo z menu w urządzeniu podręcznym. 

W tym scenariuszu praca pobrania w magazynie materiałów jest przetwarzana jako jedno działanie. Działanie przeniesienia między magazynem materiałów a magazynem produkcji jest przetwarzane jako odrębne działanie. Takie rozwiązanie może być przydatne, jeśli na przykład istnieje duża fizyczna odległość między tymi dwoma magazynami. W takim przypadku działanie przeniesienia Kanban może reprezentować ładunek w ciężarówce. 

Jeśli odległość między lokalizacjami w magazynie a lokalizacją wejściową produkcji jest mała, bardziej wydajnym rozwiązaniem może być uwzględnienie działania przeniesienia w procesie pobrania. Pobrany materiał można go odłożyć bezpośrednio do lokalizacji wejściowej produkcji. Aby umożliwić ten proces, należy skonfigurować działanie przeniesienia w taki sposób, aby było wykonywane automatycznie w trakcie przetwarzania pracy pobrania w zadaniu Kanban wycofania.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>Scenariusz 2: Automatyczne wykonywanie działania przeniesienia w trakcie przetwarzania pracy pobrania w zadaniu Kanban

W poniższym scenariuszu działanie przeniesienia w zadaniu Kanban wycofania jest skonfigurowane w taki sposób, aby przeniesienie następowało między dwoma lokalizacjami w tym samym magazynie. Działanie przeniesienia w zadaniu Kanban wycofania jest skonfigurowane tak, aby było wykonywane automatycznie. 

[![Działanie przeniesienia jest wykonywane automatycznie w trakcie przetwarzania pracy pobrania w zadaniu Kanban](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  Wspólny magazyn surowców i produkcji
2.  Lokalizacje w magazynie dla surowców
3.  Lokalizacja źródłowa zadania Kanban i lokalizacja odłożenia dla pracy magazynowej
4.  Kanban wycofania
5.  Lokalizacja przyjęcia z produkcji
6.  Proces produkcji

Po zużyciu ilości Kanban w lokalizacji wejściowej produkcji ilość Kanban jest zgłaszana jako pusta i do przepływu jest dodawana nowa karta Kanban. Po utworzeniu zadania Kanban jest dodawany wiersz grupy czynności do grupy czynności Kanban. Podczas przetwarzania grupy czynności Kanban jest tworzona praca magazynowa dla pobrania Kanban. Pracownik magazynu przetwarza pracę pobrania Kanban i otrzymuje instrukcję, aby pobrać materiał dla zadania Kanban z lokalizacji w magazynie. Gdy ten pracownik magazynu potwierdzi pobranie, zadanie Kanban jest automatycznie wypełniane i pracownik otrzymuje instrukcję, aby odłożyć materiał do lokalizacji wejściowej produkcji.

