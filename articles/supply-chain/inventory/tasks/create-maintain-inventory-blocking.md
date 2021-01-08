---
title: Tworzenie i obsługa blokowania zapasów
description: W tej procedurze pokazano, jak za pomocą funkcji blokowania zapasów zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe dotyczące towarów wychodzących.
author: perlynne
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12c6e047e15aaab157e6de70f4a09f500af2965f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435489"
---
# <a name="create-and-maintain-an-inventory-blocking"></a>Tworzenie i obsługa blokowania zapasów

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano, jak za pomocą funkcji blokowania zapasów zapobiec rezerwowaniu fizycznie dostępnych zapasów przez inne dokumenty źródłowe dotyczące towarów wychodzących. Tę procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF z przykładowymi wartościami, które są wyświetlane. Przed rozpoczęciem tej procedury musisz mieć fizycznie dostępne zapasy towaru.


## <a name="create-an-inventory-blocking"></a>Tworzenie blokowania zapasów
1. W **Okienku nawigacji** otwórz **Moduły > Zarządzanie zapasami > Zadania okresowe > Blokowanie zapasów**.
2. Kliknij przycisk **Nowy**.
3. W polu **Numer towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście zaznacz towar, który chcesz wybrać. Wybierz numer towaru fizycznie dostępnych zapasów, które chcesz zablokować. Jeśli używasz firmy demonstracyjnej USMF, można wybrać towar M9201.  
5. W polu **Ilość** wpisz liczbę. Jeśli używasz towaru M9201, wybierz mniej niż 200.
6. Rozwiń skróconą kartę **Wymiary magazynowe**.
7. W polu **Magazyn** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście znajdź i zaznacz odpowiedni rekord. Jeśli używasz towaru M9201, można wybrać magazyn 51.  
9. Kliknij przycisk **Zapisz**.

## <a name="update-the-conditions-of-the-inventory-blocking"></a>Aktualizowanie warunków blokowania zapasów
1. W skróconej karcie **Ogólne** w polu **Ilość** wprowadź liczbę. Zaktualizuj pole ilości zapasów, aby uwzględniało ilość do zablokowania.  
2. W polu **Oczekiwana data** wprowadź datę. Warto określić, kiedy zablokowane zapasy powinny stać się dostępne do rezerwacji, przypisując im oczekiwaną datę. Jeśli w ustawieniu blokowania zapasów zostanie zaznaczona opcja Przewidywane do przyjęcia, co ma miejsce domyślnie podczas ręcznego tworzenia blokowania, ta data będzie wyświetlana na oczekiwanej transakcji.  
3. Kliknij przycisk **Zapisz**.

## <a name="remove-the-inventory-blocking"></a>Usuwanie blokowania zapasów
1. W **okienku akcji** kliknij pozycję **Usuń**.
2. Kliknij przycisk **Tak**.
3. Zamknij stronę.

