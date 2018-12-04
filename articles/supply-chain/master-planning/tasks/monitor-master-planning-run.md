--- 
title: "Monitorowanie przebiegu planowania głównego"
description: "Planista produkcji chce sprawdzić, czy trwa sesja planowania głównego."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="monitor-a-master-planning-run"></a>Monitorowanie przebiegu planowania głównego

[!include [task guide banner](../../includes/task-guide-banner.md)]

Planista produkcji chce sprawdzić, czy trwa sesja planowania głównego. Do wykonania tej procedury użyj danych z firmy demonstracyjnej USMF.


## <a name="run-master-planning"></a>Uruchamianie planowania głównego
1. Kliknij opcję Planowanie główne.
    * Znajdziesz to w domyślnym pulpicie nawigacyjnym.  
2. W polu Plan wprowadź lub wybierz wartość.
    * Przykład: Plan statyczny  
3. Kliknij przycisk Uruchom.
4. W polu Śledź czas przetwarzania zaznacz opcję Tak.
    * Jeśli to pole jest już zaznaczone, pomiń ten krok.  
5. W polu Liczba wątków wprowadź liczbę.
6. Rozwiń sekcję Rekordy do uwzględnienia.
7. Kliknij przycisk Filtr.
8. Na liście oznacz wybrany wiersz.
    * Zaznacz wiersz, w którym Pole = Numer pozycji.  
9. W polu Kryteria wprowadź lub wybierz wartość.
    * Przykład: T0001  
10. Kliknij przycisk OK.
11. Kliknij przycisk OK.

## <a name="monitor-the-master-planning-run"></a>Monitorowanie przebiegu planowania głównego
1. Kliknij przycisk Historia.
2. Kliknij przycisk Informacje.
3. Kliknij opcję Czas trwania zadania procesu.
4. Na liście znajdź i zaznacz odpowiedni rekord.
    * Dla każdego towaru można orientacyjnie sprawdzić, ile czasu zajął każdy etap planowania.  


