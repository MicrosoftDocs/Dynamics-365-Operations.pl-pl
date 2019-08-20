---
title: Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań
description: Ta procedura skupia się na planowaniu zlecenia produkcyjnego przy użyciu funkcji planowania operacji i planowania zadań.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4932cfa472c34a16249b226aa4a07b8e5f528053
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838494"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Planowanie zlecenia produkcyjnego przy użyciu planowania operacji i zadań

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura skupia się na planowaniu zlecenia produkcyjnego przy użyciu funkcji planowania operacji i planowania zadań. Funkcja planowania operacji nie powoduje utworzenia żadnych zadań, natomiast zadania są tworzone przy użyciu funkcji planowania zadań. Dane wykorzystane do stworzenia tego zadania pochodzą z firmy demonstracyjnej USMF. Ta procedura jest przeznaczona dla kierownika produkcji, planisty produkcji lub kierownika zakładu produkcyjnego w środowisku wytwarzania dyskretnego.


## <a name="create-a-production-order"></a>Tworzenie zlecenia produkcyjnego
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
2. Kliknij opcję Nowe zlecenie produkcyjne.
3. W polu Numer towaru wprowadź lub wybierz wartość.
    * Wybierz towar o numerze D0001.  
4. Kliknij przycisk Utwórz.

## <a name="schedule-operations-for-the-production-order"></a>Planowanie operacji dla zlecenia produkcyjnego
1. Na liście oznacz wybrany wiersz.
    * Zaznacz zlecenie produkcyjne, która właśnie zostało utworzone. Powinno być u góry listy.      
2. W okienku akcji kliknij pozycję Harmonogram.
3. Kliknij opcję Planowanie operacji.
4. W polu Kierunek planowania wybierz opcję „W przód od daty planowania”.
5. W polu Data planowania wprowadź datę.
    * Wybierz przyszłą datę, na przykład dziś plus jeden tydzień. Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.  
6. Kliknij przycisk OK.
7. Na liście oznacz wybrany wiersz.
    * Zwróć uwagę, że stan zmienił się na Zaplanowane.  
8. Na liście kliknij łącze w wybranym wierszu.
9. Kliknij opcję Wszystkie zadania.
    * Należy zauważyć, że planowanie operacji nie powoduje tworzenia żadnych zadań.  
10. Zamknij stronę.

## <a name="schedule-jobs-for-the-production-order"></a>Planowanie zadań dla zlecenia produkcyjnego
1. W okienku akcji kliknij pozycję Harmonogram.
2. Kliknij harmonogram zadań.
3. W polu Kierunek planowania wybierz opcję „W przód od daty planowania”.
4. W polu Data planowania wprowadź datę.
    * Wybierz datę w przyszłości, na przykład dziś plus jeden tydzień. Przy wybranym kierunku planowania zlecenie produkcyjne będzie planowane w przód od tej daty.  
5. Kliknij przycisk OK.
6. W okienku akcji kliknij opcję Zlecenie produkcyjne.
7. Kliknij opcję Wszystkie zadania.
    * Należy zauważyć, że na podstawie aktywnej marszruty planowanie zadań tworzy 5 zadań.  

