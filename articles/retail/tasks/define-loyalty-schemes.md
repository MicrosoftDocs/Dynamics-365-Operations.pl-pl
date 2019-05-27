---
title: Definiowanie schematów lojalnościowych
description: Ta procedura zawiera instruktaż definiowania schematu lojalnościowego.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 362d6cf877c484c438641980d109b3bed4464b68
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564677"
---
# <a name="define-loyalty-schemes"></a>Definiowanie schematów lojalnościowych

[!include [task guide banner](../includes/task-guide-banner.md)]

Ta procedura zawiera instruktaż definiowania schematu lojalnościowego. Schematy lojalnościowe to reguły zdobywania punktów i reguły realizacji dla programu lojalnościowego. Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Handel detaliczny i inny > Odbiorcy > Lojalność > Schematy lojalnościowe.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator programu wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Może istnieć wiele schematów lojalnościowych dla programu lojalnościowego. Schematy lojalnościowe mogą dotyczyć wszystkich kanałów lub jedynie do podzbioru kanałów.  
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. Kliknij przycisk Zapisz.
9. Kliknij przycisk Dodaj wiersz.
10. W polu Typ działania wybierz opcję.
    * Zaznacz opcję Zakup produktów według kwoty, jeśli chcesz, aby klienci zdobywali nagrody w oparciu o to, ile wydadzą. Zaznacz opcję Zakup produktów według ilości, jeśli chcesz, aby klienci zdobywali nagrody w oparciu o to, ile produktów kupią.  Zaznacz opcję Licznik transakcji sprzedaży, jeśli chcesz, aby odbiorcy zdobywali nagrody za każdą transakcję sprzedaży, niezależnie od tego, co ani ile kupią.  
    * Umożliwia wybór kategorii. Kategoria ograniczy produkty, których dotyczy ta reguła zdobywania punktów.  
    * Jeśli chcesz, aby reguła zdobywania punktów miała zastosowanie do wszystkich produktów, pozostaw to pole puste.  
11. W polu Kwota/liczba działań wprowadź liczbę.
    *  Dla działania typu Licznik transakcji sprzedaży należy zawsze używać wartość „1,0”. Dla typów działań Zakup produktów według kwoty i Zakup produktów według ilości każda transakcja na mniej niż wprowadzona wartość nie uruchomi reguły zdobywania punktów. Na przykład jeśli typem działania jest Zakup produktów według kwoty i wprowadzisz „10,00”, transakcja sprzedaży na wartość „9,00” nie spowoduje uzyskania punktów lojalnościowych dla tej reguły zdobywania punktów.  
12. W polu Waluta działań wpisz wartość.
13. W polu Identyfikator punktów lojalnościowych kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
14. Na liście kliknij łącze w wybranym wierszu.
15. W polu Punkty lojalnościowe wpisz liczbę.
    * Dla punktów lojalnościowych typu Kwota uzyskane kwoty są rejestrowane z miejscami dziesiętnymi. Na przykład jeśli reguła zdobywania punktów określa uzyskanie 1 punktu lojalnościowego za każdego wydanego dolara kanadyjskiego, a odbiorca wyda 1,25 dolara kanadyjskiego, odbiorca uzyskuje 1,25 punktu lojalnościowego. Dla punktów lojalnościowych typu Ilość uzyskane kwoty są rejestrowane jako liczby całkowite. Na przykład jeśli reguła zdobywania punktów określa uzyskanie 1 punktu lojalnościowego za każdego wydanego dolara kanadyjskiego, a odbiorca wyda 1,25 dolara kanadyjskiego, odbiorca uzyskuje 1 punkt lojalnościowy.  
16. Kliknij przycisk Zapisz.
17. Kliknij przycisk Dodaj wiersz.
    * Reguły realizacji są używane, gdy jest używana metoda płatności w ramach programu lojalnościowego.  
18. W polu Identyfikator punktów lojalnościowych kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wyświetlane są tylko wymienialne punkty lojalnościowe.  
19. Na liście kliknij łącze w wybranym wierszu.
20. W polu Punkty lojalnościowe wpisz liczbę.
21. W polu Typ realizacji wybierz opcję.
    * Wybór opcji Płatność według kwoty powoduje, że pole Kwota lub ilość jest traktowane jako wartość waluty. W takim przypadku liczba punktów lojalnościowych używanych na jednostkę waluty płatności jest stała. Wybór opcji Płatność według ilości powoduje, że pole Kwota lub ilość jest traktowane jako wartość ilości. W takim przypadku ilość punktów lojalnościowych używanych na ilość towaru jest stała, jednak kwota w walucie może się różnić, jeśli cena towarów opłaconych za pomocą punktów lojalnościowych zmienia się w odniesieniu do tej samej ilości. Typ rabatu Rabat za punkty lojalnościowe działa tylko wtedy, gdy jest włączony klucz konfiguracji Funkcje specyficzne dla kraju/regionu „Rosja”, a profile funkcji punktu sprzedaży mają kod ISO „RU”.  
    * Umożliwia wybór kategorii. Kategoria ograniczy produkty, których dotyczy ta reguła realizacji.  
    * Jeśli chcesz, aby reguła realizacji miała zastosowanie do wszystkich produktów, pozostaw to pole puste.  
22. W polu Kwota lub ilość wprowadź liczbę.
23. W polu Waluta wpisz wartość.
24. Kliknij przycisk Zapisz.
25. Kliknij przycisk Dodaj wiersz.
    * Wybierz jeden lub więcej węzłów na liście Dostępne węzły organizacji i przenieś je do listy Wybrane węzły organizacji, klikając strzałkę między oboma listami.  
26. Kliknij przycisk OK.
27. Kliknij przycisk Zapisz.
    * Po każdej modyfikacji kanałów w schemacie lojalnościowym należy uruchomić funkcję Przetwarzanie programów lojalnościowych. W ten sposób kanały będą używały zaktualizowanych schematów lojalnościowych.  

