--- 
title: "Planowanie ładunków i wysyłki za pomocą warsztatu planowania wysyłki ładunku"
description: "W tej procedurze pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 982c746de1329be435d9047d4057cba100475b1b
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planowanie ładunków i wysyłki za pomocą warsztatu planowania wysyłki ładunku

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób używania pulpitu planowania wysyłki ładunku w celu utworzenia ładunku dla zamówienia sprzedaży. Warunkiem wstępnym jest utworzenie zamówienia sprzedaży, co zrobimy najpierw. Ta procedura jest częścią codziennej pracy koordynatora transportu. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-a-sales-order"></a>Utwórz zamówienie sprzedaży
1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Wybierz konto US-004.
5. Kliknij przycisk OK.
6. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Wybierz towar A0001.
    * Towar A0001 jest włączony dla zarządzania transportem.  
8. Na liście kliknij łącze w wybranym wierszu.
9. Wprowadź liczbę w polu Ilość.
10. W polu Magazyn wpisz wartość „24”.
    * W tym przykładzie należy wybrać magazyn 24. Ten magazyn jest włączony dla zarządzania transportem i zaawansowanego zarządzania magazynem.  
11. Kliknij przycisk Zapisz.
12. Zamknij stronę.

## <a name="create-a-new-load"></a>Tworzenie nowego ładunku
1. Wybierz kolejno opcje Zarządzanie transportem > Planowanie > Warsztat planowania wysyłki ładunku.
2. Kliknij kartę Wiersze sprzedaży.
    * Teraz utworzysz ładunek dla utworzonego właśnie zamówienia sprzedaży. Ładunki można tworzyć na podstawie podaży i popytu z zamówień zakupu, zamówień przeniesienia i zamówień sprzedaży.  
3. W okienku akcji kliknij opcję Popyt i podaż.
4. Kliknij opcję Do nowego ładunku.
5. W polu Identyfikator szablonu ładunku kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Szablon Ładunek określa maksymalne parametry wagi i objętości całego ładunku. Na przykład szablon ładunku może reprezentować rozmiar kontenera lub ciężarówki.  
6. Na liście kliknij łącze w wybranym wierszu.
7. Kliknij przycisk OK.

## <a name="rate-and-route-the-load"></a>Ustawiania stawek i wyznaczania trasy dla ładunku
1. Kliknij opcję Ustawianie stawek i wybór trasy.
2. Kliknij opcję Pulpit ustalania stawek i wyznaczania tras.
3. Kliknij opcję Szukanie najlepszej stawki.
4. Na liście znajdź i zaznacz odpowiedni rekord.
5. Kliknij opcję Przypisz.
6. Zamknij stronę.
7. Zamknij stronę.


