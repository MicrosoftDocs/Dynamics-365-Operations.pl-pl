---
title: Sprawdzanie dostępności zapasów w magazynie
description: Ta procedura pokazuje, jak sprawdzić ilość dostępnych i fizycznie dostępnych zapasów towaru o określonym numerze.
author: ShylaThompson
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand, InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 28446e32c8f126e76b13f41f379ecf994a7b7a0d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435492"
---
# <a name="check-the-availability-of-stock"></a>Sprawdzanie dostępności zapasów w magazynie

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak sprawdzić ilość dostępnych i fizycznie dostępnych zapasów towaru o określonym numerze. Przedstawia również, jak uzyskać informacje o podaży towaru. Fizycznie dostępne zapasy to zapasy na stanie, które są dostępne, to znaczy kupione, przyjęte i zarejestrowane. Zapasy na stanie obejmują dostępne zapasy będące na stanie, ale również zapasy, które zostały zamówione i są oczekiwane, ale jeszcze nie zostały przyjęte ani zarejestrowane. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli używasz firmy USMF, można wybrać wyświetlone przykładowe wartości. Te zadania zazwyczaj wykonuje pracownik magazynu.


## <a name="check-on-hand-inventory-for-an-item"></a>Sprawdzanie ilości dostępnych zapasów towaru
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Zarządzanie zapasami > Zapytania i raporty > Dostępne zapasy**.
2. Zaznacz wiersz **Numer towaru**. Aby wykonać zapytanie o dostępne zapasy według kodów towarów, zaznacz wiersz, gdzie ustawienie Tabela ma wartość **Dostępne zapasy**, a ustawienie Pole ma wartość numer **Towaru**.
3. W polu **Kryteria** wybierz towar, o który chcesz wykonać zapytanie. Jeśli używasz danych firmy demonstracyjnej USMF, można wybrać wartość „M9201”.  
4. Kliknij przycisk **OK**.
5. W **okienku akcji** kliknij pozycję **Wymiary**. Karta **Wymiary** pozwala wybrać ilość szczegółów, jaka będzie wyświetlana o dostępnych zapasach. Aby uzyskać dane dotyczące rezerwacji, należy wyświetlić wszystkie wymiary magazynowe dla towarów używających zaawansowanych procesów magazynowych (WMS).
6. Kliknij przycisk **OK**.
7. W **Okienku akcji** kliknij pozycję **Informacje pokrewne**. Jeśli nie widać tej opcji, może być konieczne kliknięcie przycisku wielokropka (...), aby wyświetlić dodatkowe opcje okienka akcji.
8. Kliknij przycisk **Przegląd dostaw**. Karta **Przegląd dostaw** zawiera informacje o dostawie określonego towaru, takie jak ilość dostępnych zapasów, czas realizacji i informacje o dostawcy.  
9. Rozwiń sekcję **Dostępne**.
10. Rozwiń sekcję **Dostawcy**.
11. Zamknij stronę.
12. Zamknij stronę.

## <a name="check-physical-on-hand-inventory"></a>Sprawdzanie ilości fizycznie dostępnych zapasów
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Zarządzanie magazynem > Zapytania i raporty > Fizycznie dostępne zapasy**.
2. W polu **Numer towaru** wpisz wartość. Można użyć pól Oddział i Magazyn, aby wyfiltrować listę towarów. 
3. Odśwież stronę.
4. W **okienku akcji** kliknij pozycję **Wyświetl wymiary**. Karta Wyświetlanie wymiarów pozwala wybrać ilość szczegółów, jaka będzie wyświetlana o dostępnych zapasach.
5. Kliknij przycisk **OK**.
6. Zamknij stronę.

## <a name="check-on-hand-inventory-by-location"></a>Sprawdzanie ilości dostępnych zapasów według lokalizacji
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Zarządzanie magazynem > Zapytania i raporty > Dostępne zapasy według lokalizacji**.
2. W polu **Magazyn** wpisz wartość. Jeśli używasz danych firmy demonstracyjnej USMF, można wybrać wartość „51”.  
3. Odśwież stronę.
4. Kliknij opcję **Wyświetl wymiary**.
5. Kliknij przycisk **OK**.
6. Zamknij stronę.

