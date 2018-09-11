--- 
title: "Sprawdzanie dostępności zapasów w magazynie"
description: "Ta procedura pokazuje, jak sprawdzić ilość dostępnych i fizycznie dostępnych zapasów towaru o określonym numerze."
author: 
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: 
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: 
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 62338fe11c30781f264e626fad835a2ba9dca837
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="check-the-availability-of-stock"></a>Sprawdzanie dostępności zapasów w magazynie

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak sprawdzić ilość dostępnych i fizycznie dostępnych zapasów towaru o określonym numerze. Przedstawia również, jak uzyskać informacje o podaży towaru. Fizycznie dostępne zapasy to zapasy na stanie, które są dostępne, to znaczy kupione, przyjęte i zarejestrowane. Zapasy na stanie obejmują dostępne zapasy będące na stanie, ale również zapasy, które zostały zamówione i są oczekiwane, ale jeszcze nie zostały przyjęte ani zarejestrowane. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości. Te zadania zazwyczaj wykonuje pracownik magazynu.


## <a name="check-on-hand-inventory-for-an-item"></a>Sprawdzanie ilości dostępnych zapasów towaru
1. Wybierz kolejno opcje Zarządzanie zapasami > Zapytania i raporty > Dostępne zapasy.
2. Zaznacz wiersz Numer towaru.
    * Aby wykonać zapytanie o dostępne zapasy według kodów towarów, zaznacz wiersz, gdzie ustawienie Tabela ma wartość Dostępne zapasy, a ustawienie Pole wartość Numer towaru.  
3. W polu Kryteria wybierz towar, o który chcesz wykonać zapytanie.
    * Jeśli używasz danych firmy demonstracyjnej USMF, można wybrać wartość „M9201”.  
4. Kliknij przycisk OK.
5. Kliknij opcję Wymiary.
    * Karta Wymiary pozwala wybrać ilość szczegółów, jaka będzie wyświetlana o dostępnych zapasach. Aby uzyskać dane dotyczące rezerwacji, należy wyświetlić wszystkie wymiary magazynowe dla towarów używających zaawansowanych procesów magazynowych (WHS).  
6. Kliknij przycisk OK.
7. W okienku akcji kliknij pozycję Informacje pokrewne.
    * Jeśli tego nie widać, może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić dodatkowe opcje okienka akcji.  
8. Kliknij przycisk Przegląd dostaw.
    * Karta Przegląd dostaw zawiera informacje o dostawie określonego towaru, takie jak ilość dostępnych zapasów, czas realizacji i informacje o dostawcy.  
9. Rozwiń sekcję Dostępne.
10. Rozwiń sekcję Dostawcy.
11. Zamknij stronę.
12. Zamknij stronę.

## <a name="check-physical-on-hand-inventory"></a>Sprawdzanie ilości fizycznie dostępnych zapasów
1. Wybierz kolejno opcje Zarządzanie magazynem > Zapytania i raporty > Fizycznie dostępne zapasy.
2. W polu Numer towaru wpisz wartość.
    * Można użyć pól Oddział i Magazyn, aby wyfiltrować listę towarów.  
3. Odśwież stronę.
4. Kliknij opcję Wyświetl wymiary.
    * Karta Wyświetlanie wymiarów pozwala wybrać ilość szczegółów, jaka będzie wyświetlana o dostępnych zapasach.  
5. Kliknij przycisk OK.
6. Zamknij stronę.

## <a name="check-on-hand-inventory-by-location"></a>Sprawdzanie ilości dostępnych zapasów według lokalizacji
1. Wybierz kolejno opcje Zarządzanie magazynem > Zapytania i raporty > Dostępne zapasy według lokalizacji.
2. W polu Magazyn wpisz wartość.
    * Jeśli używasz danych firmy demonstracyjnej USMF, można wybrać wartość „51”.  
3. Odśwież stronę.
4. Kliknij opcję Wyświetl wymiary.
5. Kliknij przycisk OK.
6. Zamknij stronę.


