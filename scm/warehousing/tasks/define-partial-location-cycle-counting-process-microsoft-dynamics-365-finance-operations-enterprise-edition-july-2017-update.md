--- 
title: "Definiowanie procesu częściowej inwentaryzacji ciągłej w lokalizacji"
description: "Używając planów inwentaryzacji ciągłej do tworzenia pracy inwentaryzacji, można kierować faktycznymi operacjami zliczania poprzez ustawienie żądania, aby były zliczane tylko konkretne produkty i warianty produktów, a nie wszystkie zapasy dostępne w lokalizacji."
author: YuyuScheller
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 507a1147fea62c12490291362d365224efeda97e
ms.contentlocale: pl-pl
ms.lasthandoff: 07/28/2017

---
# <a name="define-partial-location-cycle-counting-process"></a>Definiowanie procesu częściowej inwentaryzacji ciągłej w lokalizacji 

[!include[task guide banner](../../includes/task-guide-banner.md)]

Używając planów inwentaryzacji ciągłej do tworzenia pracy inwentaryzacji, można kierować faktycznymi operacjami zliczania poprzez ustawienie żądania, aby były zliczane tylko konkretne produkty i warianty produktów, a nie wszystkie zapasy dostępne w lokalizacji. Wyfiltrowując określone produkty, kierownik magazynu może zmniejszyć pracochłonność przeglądu, zapobiec błędom konsolidacji i zaoszczędzić czas. Zazwyczaj zadania konfiguracyjne wykonuje kierownik magazynu. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="create-a-cycle-counting-work-template"></a>Tworzenie szablonu pracy inwentaryzacji ciągłej
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Szablony pracy.
2. W polu Typ zlecenia wybierz opcję „Inwentaryzacja ciągła”.
3. Kliknij przycisk Nowy.
4. W polu Numer sekwencyjny wpisz liczbę.
    * Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby. Wartość musi być większa od 0 (zera).  
5. Na liście oznacz wybrany wiersz.
6. W polu Szablon pracy wpisz wartość.
7. W polu Opis szablonu pracy wpisz wartość.
8. W polu Identyfikator puli pracy wprowadź lub wybierz wartość.
9. W polu Priorytet pracy wprowadź liczbę.
10. Kliknij przycisk Zapisz.
11. Kliknij przycisk Nowy.
12. Na liście oznacz wybrany wiersz.
13. W polu Typ pracy zaznacz opcję „Inwentaryzacja”.
14. W polu Identyfikator klasy roboczej wprowadź lub wybierz wartość.
15. Kliknij przycisk Zapisz.
16. Kliknij opcję Podziały wierszy pracy.
17. Kliknij przycisk Nowy.
18. W polu Numer sekwencyjny wpisz liczbę.
    * Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby. Wartość musi być większa od 0 (zera).  
19. Kliknij przycisk Zapisz.
20. Zamknij stronę.
21. Zamknij stronę.

## <a name="create-a-cycle-counting-plan"></a>Tworzenie planu inwentaryzacji ciągłej
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Inwentaryzacja ciągła > Plany inwentaryzacji ciągłej.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator planu inwentaryzacji ciągłej wpisz wartość.
4. W polu Opis wpisz wartość.
5. W polu Maksymalna liczba inwentaryzacji ciągłych wpisz liczbę.
6. W polu Szablon pracy wprowadź lub wybierz wartość.
7. Kliknij przycisk Nowy.
8. W polu Numer sekwencyjny wpisz liczbę.
    * Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby. Wartość musi być większa od 0 (zera).  
9. Wypełnij pole Opis.
10. Kliknij przycisk Zapisz.
11. Kliknij opcję Definiuj zapytanie produktu.
12. Na liście oznacz wybrany wiersz.
13. W polu Kryteria wprowadź lub wybierz wartość.
14. Kliknij przycisk OK.
15. Zamknij stronę.


