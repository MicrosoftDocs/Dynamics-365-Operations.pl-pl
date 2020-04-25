---
title: Tworzenie harmonogramu dla oddziału
description: W tej procedurze pokazano sposób planowania zleceń produkcyjnych, które jeszcze nie zostały rozpoczęte w oddziale.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bc2dc4a03f9d937339ec2470f6a065f77c7036a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209635"
---
# <a name="create-a-schedule-for-a-site"></a>Tworzenie harmonogramu dla oddziału

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób planowania zleceń produkcyjnych, które jeszcze nie zostały rozpoczęte w oddziale.  Dane wykorzystane do wykonania tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="identify-production-orders-that-are-not-started"></a>Identyfikowanie zleceń produkcyjnych, które się jeszcze nie rozpoczęły
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Oddział z wartością „1”.
    * 1 odpowiada oddziałowi w firmie USMF. Jeśli nie używasz firmy USMF, wybierz oddział ze swojej firmy.  
3. Otwórz filtr kolumn Stan.
4. Zastosuj filtr do pola „Stan” z wartością „Zaplanowane” i operatorem „równa się”.

## <a name="create-a-schedule"></a>Tworzenie harmonogramu
1. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
2. W okienku akcji kliknij pozycję Harmonogram.
3. Kliknij opcję Planowanie zadań.
4. W polu Kierunek planowania wybierz opcję "Wstecz od daty dostawy".
5. W polu Ograniczone zdolności produkcyjne wybierz opcję Nie.
6. W polu Ograniczone materiały wybierz opcję Nie.
7. Kliknij przycisk OK.
    * Może to trochę potrwać.  

## <a name="view-the-result-of-scheduled-production-orders"></a>Wyświetlanie rezultatów zaplanowanych zleceń produkcyjnych
1. Na liście oznacz wybrany wiersz.
    * Można oznaczyć dowolny wiersz.  
2. W okienku akcji kliknij opcję Zlecenie produkcyjne.
3. Kliknij opcję Wszystkie zadania.
    * Na tej stronie widać listę zadań. Na karcie Planowanie widać daty rozpoczęcia i zakończenia zadania.  
4. Kliknij opcję Materiały.
    * Na tej stronie widać szacowane zużycie materiału w operacjach zlecenia produkcyjnego oraz aktualnie dostępne zapasy.  

