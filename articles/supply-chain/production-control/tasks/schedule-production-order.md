---
title: Planowanie zlecenia produkcyjnego
description: W tej procedurze pokazano sposób planowania zlecenia produkcyjnego.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2fa0f0f38dcb93aff9b3a1d8130fba0a0c836b3b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981113"
---
# <a name="schedule-a-production-order"></a>Planowanie zlecenia produkcyjnego

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób planowania zlecenia produkcyjnego. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Jest to trzecia z siedmiu procedur, które wyjaśniają cykl życia zlecenia produkcyjnego.


## <a name="schedule-a-production-order"></a>Planowanie zlecenia produkcyjnego
1. Wybierz kolejno opcje Kontrola produkcji > Zlecenia produkcyjne > Wszystkie zlecenia produkcyjne.
    * Zaznacz zlecenie produkcyjne, które ma stan Szacowane.  
2. W okienku akcji kliknij pozycję Harmonogram.
3. Kliknij harmonogram zadań.
    * Na tej stronie konfiguruje się parametry planowania. Można skonfigurować parametry dla określonych użytkowników lub wszystkich użytkowników.  
4. W polu Kierunek planowania wybierz opcję „W przód od dzisiaj”.
5. W polu Data planowania wprowadź datę.
6. Zaznacz lub wyczyść pole wyboru Ograniczone zdolności produkcyjne.
7. Zaznacz lub wyczyść pole wyboru Ograniczone materiały.
8. Kliknij przycisk OK.

## <a name="view-the-scheduling-results"></a>Wyświetlanie wyników planowania
1. W okienku akcji kliknij opcję Zlecenie produkcyjne.
2. Kliknij opcję Wszystkie zadania.
    * Ta strona służy do wyświetlania zaplanowanych zadań, które właśnie utworzono.  
3. Rozwiń lub zwiń sekcję Planowanie.
    * Na skróconej karcie Planowanie można obejrzeć zaplanowaną datę i godzinę.  
4. Kliknij przycisk Informacje.
5. Kliknij opcję Obciążenie zdolności produkcyjnych.
    * Strony Obciążenie zdolności produkcyjnych pokazuje zdolności produkcyjne zarezerwowane wskutek planowania zadań, aktualną łączną liczbę godzin rezerwacji zasobu oraz liczbę godzin, które są dostępne na potrzeby zaplanowania zasobu dla zadań.  
6. Zamknij stronę.
7. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]