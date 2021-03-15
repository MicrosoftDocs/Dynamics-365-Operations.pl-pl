---
title: Definiowanie inwentaryzacji ciągłej
description: Inwentaryzacja cykliczna jest procesem magazynowym, który służy do inspekcji pozycji magazynowych.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1424bc4c4ff0f8528d6577e80324082cb2ec7f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977170"
---
# <a name="define-cycle-counting"></a>Definiowanie inwentaryzacji ciągłej 

[!include [banner](../../includes/banner.md)]

Inwentaryzacja cykliczna jest procesem magazynowym, który służy do inspekcji pozycji magazynowych. To nagranie zadania pokazuje, jak ustawić domyślny priorytet pracy inwentaryzacji, włączyć element menu urządzenia przenośnego do przetwarzania operacji zarówno pobrania, jak i inwentaryzacji, włączyć wyzwalacz progowy inwentaryzacji, gdy lokalizacja się opróżni, oraz włączyć plan inwentaryzacji ciągłej dla określonego towaru w określonym magazynie. Zazwyczaj te zadania wykonuje kierownik magazynu. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-the-priority-of-counting-work"></a>Ustawianie priorytetu pracy inwentaryzacji
1. Otwórz **Okienko nawigacji**, **Moduły > Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem**.
2. Kliknij kartę **Inwentaryzacja ciągła**.
3. W polu **Domyślny priorytet pracy inwentaryzacji ciągłej** wprowadź liczbę. Ten krok spowoduje zmianę priorytetu pracy inwentaryzacji ciągłej względem innych typów pracy w magazynie. Wpisując liczbę niższą niż dla innych typów prac, podwyższasz priorytet pracy inwentaryzacji ciągłej.  
4. Kliknij przycisk **Zapisz**.
5. Zamknij stronę.

## <a name="enable-the-mobile-device"></a>Włączanie obsługi urządzenia przenośnego
1. W **okienku nawigacji** wybierz kolejno opcje **Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Elementy menu urządzenia przenośnego**.
2. Kliknij przycisk **Nowy**.
3. W polu **Nazwa elementu menu** wpisz wartość.
4. W polu **Tytuł** wpisz wartość.
5. W polu **Tryb** wybierz opcję „Praca”.
6. W opcji **Użyj istniejącej pracy** zaznacz wartość Tak. Gdy w tej opcji ustawisz wartość Tak, system będzie szukał istniejącej pracy w przypadku użycia elementu menu urządzenia przenośnego.  
7. W polu **Sterowane przez** wybierz opcję „Sterowane przez system”. Jeżeli zaznaczysz opcję „Sterowane przez system”, pracownik magazynu zostanie skierowany do otwartej pracy należącej do zdefiniowanych klas pracy. (Te klasy pracy zostaną utworzone w następnym kroku).  
8. Rozwiń skróconą kartę **Klasy robocze**. Następnie utworzymy dwie klasy pracy, które będą używane z tym elementem menu urządzenia przenośnego. Użycie elementu menu spowoduje wykonanie zapytania o te klasy pracy i wyświetlenie użytkownikowi pracy o najwyższym priorytecie.  
9. Kliknij przycisk **Nowy**.
10. W polu **Identyfikator klasy roboczej** wybierz wartość.
11. Kliknij przycisk **Nowy**.
12. W polu **Identyfikator klasy roboczej** wybierz wartość.
13. W **okienku akcji** kliknij pozycję **Zapisz**.
14. Zamknij stronę.
15. W **okienku nawigacji** wybierz kolejno **Moduły > Zarządzanie magazynem > Ustawienia > Urządzenie przenośne > Menu urządzeń przenośnych**.
16. Na liście znajdź i zaznacz odpowiedni rekord.
17. W drzewie wybierz element menu, który został właśnie utworzony.
18. Kliknij przycisk **Edytuj**.
19. Kliknij strzałkę, aby dodać element menu do menu.
20. Kliknij przycisk **Zapisz**.

## <a name="create-a-counting-threshold"></a>Tworzenie progu inwentaryzacji
1. W **okienku nawigacji** przejdź do **Moduły > Zarządzenie magazynem > Ustawienia > Inwentaryzacja ciągła > Progi inwentaryzacji ciągłej**.
2. Kliknij przycisk **Nowy**.
3. W polu **Identyfikator progu inwentaryzacji ciągłej** wpisz wartość.
4. Ustaw opcję **Przetwarzaj natychmiast inwentaryzację ciągłą** na Tak.
5. W polu **Opis** wpisz wartość.
6. Kliknij przycisk **Zapisz**.
7. Kliknij opcję **Wybierz lokalizacje**.
8. Na liście oznacz wybrany wiersz.
9. W polu **Kryteria** wybierz wartość.
10. Kliknij przycisk **OK**.
11. Zamknij stronę.

## <a name="create-a-cycle-count-plan"></a>Tworzenie planu inwentaryzacji ciągłej
1. W **okienku nawigacji** przejdź do **Moduły > Zarządzenie magazynem > Ustawienia > Inwentaryzacja ciągła > Plany inwentaryzacji ciągłej**.
2. Kliknij przycisk **Nowy**.
3. W polu **Identyfikator planu inwentaryzacji ciągłej** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Maksymalna liczba inwentaryzacji ciągłych** wpisz liczbę.
6. Kliknij przycisk **Zapisz**.
7. Kliknij opcję **Wybierz lokalizacje**.
8. Na liście oznacz wybrany wiersz.
9. W polu **Kryteria** wybierz wartość.
10. Kliknij przycisk **OK**.
11. W polu **Dni między inwentaryzacją ciągłą** wprowadź liczbę. Na przykład jeśli wartość ustawiona w polu **Dni między inwentaryzacją ciągłą** to 5, praca inwentaryzacji ciągłej będzie tworzona co pięć dni. Jednak jeśli praca inwentaryzacji ciągłej jest przetwarzania w trzecim dniu, następna praca inwentaryzacji ciągłej zostanie utworzona 5 dni po przetworzeniu ostatniej inwentaryzacji ciągłej, czyli w dniu ósmym.  
12. Kliknij przycisk **Zapisz**.
13. Kliknij przycisk **Nowy**.
14. W polu **Numer sekwencyjny** wpisz liczbę. Sortowanie odbywa się w porządku od najmniejszej liczby do największej liczby. Wartość musi być większa od 0 (zera).  
15. Na liście oznacz wybrany wiersz.
16. W polu **Opis** wpisz wartość.
17. Kliknij przycisk **Zapisz**.
18. Kliknij opcję **Definiuj zapytanie produktu**.
19. Na liście oznacz wybrany wiersz.
20. W polu **Kryteria** wprowadź lub wybierz wartość.
21. Kliknij przycisk **OK**.
22. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]