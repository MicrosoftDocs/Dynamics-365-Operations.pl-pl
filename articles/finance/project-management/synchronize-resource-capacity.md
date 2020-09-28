---
title: Synchronizacja zdolności produkcyjnych zasobu
description: Ten temat zawiera informacje o sposobach synchronizowania zdolności produkcyjnych zasobu w kalendarzach i projektach.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760632"
---
# <a name="synchronize-resource-capacity"></a>Synchronizacja zdolności produkcyjnych zasobu

[!include [banner](../includes/banner.md)]

Procesy synchronizacji zasobów pomagają zagwarantować, że informacje dotyczące kalendarza i kalendarza podstawowego są przekazywane do czynności planowania zasobów projektu. Jeśli kalendarz zostanie zmieniony, procesy dokonują wymaganych aktualizacji harmonogramów zasobów projektu. Procesy pomagają także zwiększyć wydajność, ponieważ informacje o zasobie kalendarza są synchronizowane z wyprzedzeniem. Dlatego aktualizacje informacji o planowaniu zasobów są dokonywane szybciej. Zaleca się planowanie procesów jako zadanie wsadowe, a nie jednostkowe. W przeciwnym razie istnieje ryzyko, że ktoś może zapomnieć włącznych dat ostatniej synchronizacji. Jeśli nie są używane daty włączne, mogą występować przerwy podczas synchronizacji dat.

![Synchronizacja kalendarza](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a>Synchronizuj zestawienia zdolności produkcyjnych zasobów

Proces synchronizacji jest zaprojektowany do synchronizowania wszystkich informacji w kalendarzu zasobów. Informacje te obejmują dane kalendarza podstawowego o wszelkich zmianach w tabeli zdolności produkcyjnych kalendarza zasobów projektu. Jeśli w projekcie są dodawane nowe zasoby, synchronizacja pomaga zagwarantować dostępność zaktualizowanych informacji kalendarza. Tę synchronizację można wykonać w dowolnym czasie.

Zaleca się używanie procesu wsadowego. Odpowiednie opcje są dostępne podczas synchronizowania rezerwacji zdolności produkcyjnych.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** &gt; **Okresowe** &gt; **Synchronizacja zdolności produkcyjnych** &gt; **Synchronizuj zestawienia zdolności produkcyjnych zasobów**.
2. Ustaw opcje w następującej tabeli.

    | Opcja      | opis |
    |-------------|-------------|
    | Kod okresu | Opcjonalnie wybierz kod interwału daty księgi głównej w celu ustawienia daty rozpoczęcia i zakończenia procesu synchronizacji zestawień zdolności produkcyjnych zasobów. |
    | Rozpoczęcie  | Wprowadź datę rozpoczęcia procesu synchronizacji zestawienia zdolności produkcyjnych zasobów. |
    | Data zakończenia    | Wprowadź datę zakończenia procesu synchronizacji zestawienia zdolności produkcyjnych zasobów. |

[![Proces synchronizacji](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)
