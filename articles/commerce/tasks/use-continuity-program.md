---
title: Używanie programu sprzedaży ciągłej
description: Ta procedura przeprowadzi Cię przez proces sprzedawania w programie sprzedaży ciągłej i przetwarzania powiązanych zamówień sprzedaży.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, MCRCustSearch, SalesTable, MCRContinuityCustInfo, MCRCustPaymLookup, CreditCardTokenization, CreditCardLookup, MCRSalesOrderRecap
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2baf0127a35cc62952fd78daaf8204d35ec8d2b3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414970"
---
# <a name="using-continuity-program"></a>Używanie programu sprzedaży ciągłej

[!include [banner](../includes/banner.md)]

Ta procedura przeprowadzi Cię przez proces sprzedawania w programie sprzedaży ciągłej i przetwarzania powiązanych zamówień sprzedaży. Aby wykonać tę procedurę, użytkownik musi być skonfigurowany jako użytkownik biura obsługi. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Odbiorcy > Obsługa klienta.
2. W polu Wyszukiwany tekst wpisz „Karen”, a następnie naciśnij klawisz Tab.
    * Powinno się pojawić okno dialogowe zaawansowanego wyszukiwania. Jeśli tak się nie stanie, kliknij przycisk Szukaj umieszczony na prawo od tego pola.  
3. Na liście oznacz wybrany wiersz.
    * Powinien być wyświetlany tylko jeden wiersz z osobą Karen Berg. Zaznacz wiersz, klikając kolumnę ze znacznikiem wyboru przy lewej krawędzi siatki.  
4. Kliknij opcję Wybierz.
5. Kliknij opcję Nowe zamówienie sprzedaży.
    * Dobrym pomysłem jest zanotowanie numeru zamówienia sprzedaży. Będzie on potrzebny w dalszej części tej procedury.  
6. W polu Numer pozycji wpisz „88000”, a następnie naciśnij klawisz Tab.
    * Jest to pozycja w sprzedaży ciągłej wśród danych firmy demonstracyjnej USRT.  
7. Kliknij przycisk Wykonaj.
8. W polu Metoda płatności wprowadź wartość „Visa”.
9. Kliknij opcję Dodaj kartę kredytową.
    * Na tej stronie wprowadź wymagane dane karty kredytowej.  
10. Kliknij przycisk OK.
11. Rozwiń sekcję Płatność.
    * Aby przesłać zamówienie biura obsługi, muszą zostać wprowadzone płatności dla zamówienia.  
12. Kliknij przycisk OK.
13. Kliknij przycisk Prześlij.
    * Zakończono tworzenie nowego zamówienia ciągłego. Teraz wykonasz dwa procesy wsadowe, które służą do przetwarzania zamówień ciągłych.  
14. Zamknij stronę.
15. Wybierz kolejno opcje Handel detaliczny i inny > Ciągłość > Przetwarzanie płatności w sprzedaży ciągłej.
16. W polu Pozycja w sprzedaży ciągłej wpisz „88000”, a następnie naciśnij klawisz Tab.
17. Kliknij przycisk OK.
18. Wybierz kolejno opcje Handel detaliczny i inny > Ciągłość > Tworzenie zamówień podrzędnych dla sprzedaży ciągłej.
    * Proces spowoduje utworzenie nowych zamówień sprzedaży na podstawie ustawień programów sprzedaży ciągłej.  
19. W polu Pozycja w sprzedaży ciągłej wpisz „88000”, a następnie naciśnij klawisz Tab.
    * Towar „88000” jest pozycją w sprzedaży ciągłej wśród danych firmy demonstracyjnej USRT.  
20. W polu Zamówienie sprzedaży wprowadź lub wybierz wartość.
    * Wprowadź numer zamówienia sprzedaży zanotowany wcześniej w procedurze. Pozwoli to maksymalnie skrócić czas przetwarzania tej procedury. Pole Zamówienia sprzedaży jest opcjonalne — można przetwarzać wszystkie zamówienia z każdego programu.  
21. Kliknij przycisk OK.

