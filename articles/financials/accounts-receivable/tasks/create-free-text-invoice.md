--- 
title: "Tworzenie faktury niezależnej"
description: "W tym przewodniku po zadaniach zilustrowano tworzenie faktury niezależnej."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ef3cad6538d9efbd1c1881f4b7d771382d9b1ba8
ms.openlocfilehash: 87e293008fd748aa0dcc6b3caa94a4889bed35de
ms.contentlocale: pl-pl
ms.lasthandoff: 10/26/2017

---
# <a name="create-a-free-text-invoice"></a>Tworzenie faktury niezależnej

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach zilustrowano tworzenie faktury niezależnej. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne.
2. Kliknij przycisk Nowy.
3. W polu Konto odbiorcy wybierz wartość.
    * Kontem faktury domyślnie będzie konto odbiorcy.   
    * Jeśli faktura nie jest zaksięgowana, stan księgowania zaczyna się od stanu W trakcie przetwarzania.   
    * Identyfikator faktury zostanie przypisany podczas księgowania faktury.  
    * Jeśli używasz pozwoleń SEPA, zgoda na polecenie zapłaty będzie automatycznie wypełniana po wybraniu konta odbiorcy.  
4. Wypełnij pole Opis.
5. W polu Konto główne określ numer konta bez wymiarów.
    * Można również wpisać jeden lub więcej znaków konta głównego, a następnie za pomocą funkcji wyszukiwania znaleźć konto. Wymiar wprowadza się na dalszym etapie procesu w przewodniku.  
6. Rozwiń skróconą kartę Szczegóły wiersza, tak aby dodać wymiary do konta głównego.
7. Kliknij kartę Wiersz wymiarów finansowych.
    * Wymiary dotyczą tylko wybranego wiersza.    
    * Grupa podatków jest wypełniana danymi od odbiorcy. Jeśli odbiorca nie ma zdefiniowanej grupy podatków, jest używana grupa podatków z konta głównego.  
    * Grupa podatków dla pozycji jest wypełniana na podstawie konta głównego. Jeśli konto główne nie ma zdefiniowanej grupy podatków dla pozycji, jest używana grupa podatków dla pozycji określona w parametrach podatków w Księdze głównej.    
8. Wprowadź liczbę w polu Ilość.
    * Ilość jest opcjonalna.  
9. Wprowadź liczbę w polu Cena jednostkowa.
    * Cena jednostkowa jest opcjonalna.  
    * Kwota jest obliczana jako ilość pomnożona przez cenę jednostkową. Można jednak zastąpić wynik tego obliczenia i wprowadzić kwotę samodzielnie.  
10. Kliknij opcję Podatek, aby wyświetlić podatek obliczony dla faktury.
    * Można wyświetlić kwoty podatków na tej stronie albo zastąpić kwoty na karcie Korekta.  
11. Kliknij przycisk OK.
12. Kliknij opcję Opłaty, aby dodać opłatę do faktury. 
13. W polu Kod opłat wpisz wartość.
14. W polu Kod opłat wprowadź liczbę.
15. Zamknij stronę.
16. Kliknij opcję Sumy, aby wyświetlić szczegóły i sumy faktury zbiorczej.
17. Kliknij przycisk Zamknij.
18. Kliknij przycisk Księguj, aby zaksięgować fakturę. Przed zaksięgowaniem będzie można anulować operację.
    * Aby zmienić harmonogram drukowania faktur: zaznacz opcję Bieżąca, aby drukować każdą fakturę po jej aktualizacji, lub Po, aby drukować po zaktualizowaniu wszystkich faktur.  
    * Jeśli chcesz zmienić sposób sprawdzania limitu kredytowego odbiorcy przed zaksięgowaniem, zmień typu limitu kredytu.  
    * Jeśli chcesz wydrukować fakturę, zaznacz opcję Tak.  
    * Jeśli chcesz zaksięgować fakturę, zaznacz opcję Tak. Fakturę można wydrukować bez księgowania.  
19. Kliknij przycisk OK.


