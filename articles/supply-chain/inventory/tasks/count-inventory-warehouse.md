--- 
title: "Liczenie zapasów w magazynie"
description: "Ta procedura prowadzi przez proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie."
author: MarkusFogelberg
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fa72cb0d651f5e60797fa41f6e2b2cf1891730b5
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="count-inventory-in-a-warehouse"></a>Liczenie zapasów w magazynie

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura prowadzi przez proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie. Procedura dotyczy funkcji „podstawowego magazynowania” dostępnej w module Zarządzanie zapasami, a nie funkcji magazynowania dostępnej w module Zarządzanie magazynem. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli korzystasz z własnych danych, upewnij się, że masz skonfigurowane produkty i lokalizacje oraz utworzony arkusz magazynowy dla arkuszy inwentaryzacji. Inwentaryzacja jest zwykle przeprowadzana przez pracownika magazynu.


## <a name="create-an-inventory-counting-journal"></a>Tworzenie arkusza inwentaryzacji zapasów
1. Wybierz kolejno opcje Zarządzanie zapasami > Wpisy w arkuszu > Zliczanie towarów > Inwentaryzacja.
2. Kliknij przycisk Nowy.
3. W polu Nazwa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij nazwę arkusza inwentaryzacji zapasów, który ma być używany.
    * Niektóre inne pola zostaną wypełnione zgodnie z ustawieniami wybranego arkusza inwentaryzacji zapasów.  
5. W polu Pracownik kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście zaznacz pracownika, z którego chcesz skorzystać.
7. Kliknij opcję Wybierz.
8. Kliknij przycisk OK.

## <a name="create-journal-lines"></a>Tworzenie wierszy arkusza
1. Kliknij przycisk Nowy.
2. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Jeśli używasz danych firmy demonstracyjnej USMF, wybierz opcję „A0001”.  
4. W polu Oddział kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * Jeśli używasz danych firmy demonstracyjnej USMF, wybierz oddział „2”.  
6. W polu Magazyn kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście znajdź i zaznacz odpowiedni rekord.
    * Jeśli używasz danych firmy demonstracyjnej USMF, wybierz magazyn „24”.  
8. W polu Lokalizacja kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
9. Na liście znajdź i zaznacz odpowiedni rekord.
    * Jeśli używasz danych firmy demonstracyjnej USMF, wybierz lokalizację „BULK-001”.  
10. W polu Policzono wprowadź liczbę.
    * Jeśli wprowadzisz zliczoną liczbę inną niż liczba widoczna w polu Zapasy, pole Ilość zostanie zaktualizowane w celu pokazania niezgodności.  
11. Kliknij przycisk Zapisz.

## <a name="post-the-inventory-counting-journal"></a>Księgowanie arkusza inwentaryzacji zapasów
1. Kliknij przycisk Księguj.
    * Jeśli podczas księgowania arkusza inwentaryzacji zapasów zliczona ilość jest inna niż ilość podana w polu Zapasy, nastąpi zaksięgowanie przyjęcia na magazyn lub wydania, zmiana poziomu i wartości zapasów oraz wygenerowanie transakcji finansowych.  
2. Kliknij przycisk OK.

## <a name="view-inventory-transactions"></a>Wyświetlanie transakcji magazynowych
1. Kliknij opcję Zapasy.
2. Kliknij opcję Transakcje.
    * Tutaj można zobaczyć wszystkie powiązane transakcje, które zostaną utworzone podczas księgowania arkusza inwentaryzacji zapasów.   


